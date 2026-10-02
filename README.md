# campus-event-management
# Group Laboratory Examination Submission
**Course:** Applied Generative AI for IT Solution Development
**Project:** Online Campus Event Management System

## 1. Team Roster
| Member | Name | Assigned Role | Responsibilities |
|---|---|---|---|
| Member 1 | [Kin Alejandro Ramos] | Systems Architect & Prompt Lead | Task 1, Task 5 |
| Member 2 | [Kenneth Nasser Nocon] | Frontend Engineer | Task 2 |
| Member 3 | [Justine Dave Ocampo] | Database & Backend Engineer | Task 3 |
| Member 4 | [Justine Dave Ocampo] | QA & Security Engineer | Task 4 |

## 2. Setup Instructions
1. Clone the repository: `git clone [repo-url]`
2. **Frontend:** open `/frontend/index.html` in any browser (no build step).
3. **Database:** open SQL Server Management Studio, connect to your instance, and run `/database/schema.sql`.
4. **ERD:** view the Mermaid diagram below on GitHub (rendered automatically).
5. **Tests:** `cd tests`, then `dotnet test` (requires .NET SDK, xUnit, Moq).
6. **Backend:** `/backend/RegistrationService.cs` takes the connection string via constructor injection.

## Task 1: Requirements Analysis & Prompt Architecture
### Exact Prompt
[paste the Task 1 PROMPT]

### AI Output
[paste the Task 1 OUTPUT]

### Manual Grounding Evaluation
[paste the 3-4 sentence evaluation]

## Task 2: AI-Assisted Frontend
- Files: `/frontend/index.html`, `styles.css`, `app.js`
- Semantic tags used: header, nav, main, section, article, footer
- WCAG: labels, aria-label, 4.5:1 contrast, alt text, skip link, aria-live messages

## Task 3: Database Design
### ERD (Mermaid)
```mermaid
[paste the Mermaid block]
```
DDL script: `/database/schema.sql`

## Task 4: Testing, Security & Refactoring
- Tests: `/tests/RegistrationValidatorTests.cs` (xUnit + Moq)
- Diagnosis: SQL injection, unmanaged connection/command, hardcoded credentials, null reference
- Refactored code: `/backend/RegistrationService.cs`

## 3. AI Disclosure Statement
AI tools used: [Claude (Anthropic) / v0 / other tools you actually used] for generating the system design, frontend code, SQL schema and ERD, unit tests, and the security refactor.
Verification: all outputs were reviewed by the member responsible. The frontend was opened and tested in a browser, the SQL script was executed on SQL Server, unit tests were run with `dotnet test`, and the refactored C# was reviewed against the original vulnerabilities.

## 4. Group Verification Log
| Task # | Identified AI Flaw / Limitation | Manual Correction Applied | Member Responsible |
|---|---|---|---|
| Task 1 | Design assumed a fully integrated API + DB, too ambitious for 3 hours | Reduced scope, frontend demos with mock data, API integration optional | Member 1 |
| Task 2 | Missing aria-label on inputs; low-contrast button color | Added aria-label to every input, changed colors to meet 4.5:1 contrast | Member 2 |
| Task 3 | No non-clustered indexes on foreign key columns | Added CREATE NONCLUSTERED INDEX for every FK column | Member 3 |
| Task 4 | Refactor queried `Registrations.Email`, but Email lives in `Users` (3NF); null result caused NullReferenceException | Added JOIN to Users and null-safe `?.ToString()`; kept `using` blocks for disposal | Member 4 |
