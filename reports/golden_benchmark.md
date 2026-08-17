# Lab 17 Golden Set Report

- Implementation: `student`
- Kind: `golden`
- Cases: **20**
- Passed: **14/20**
- Evidence hit rate: **70.0%**
- Average retrieval latency: **1106.7 ms**
- Average token reduction vs full source context: **4.2%**
- Golden bonus: **0/10** (100% required)

| Case | Layer | Pass | Latency ms | Retrieved tokens | Token reduction | Missing / Error |
| --- | --- | --- | ---: | ---: | ---: | --- |
| G01 | short_term | PASS | 0.3 | 227 | 0.0% |  |
| G02 | short_term | PASS | 0.1 | 133 | 0.0% |  |
| G06 | long_term | PASS | 1531.9 | 859 | 0.0% |  |
| G09 | semantic | PASS | 253.7 | 418 | 8.9% |  |
| G10 | semantic | PASS | 248.2 | 270 | 41.2% |  |
| G14 | mixed | PASS | 1588.7 | 581 | 0.0% |  |
| G03 | long_term | PASS | 1744.3 | 1415 | 0.0% |  |
| G04 | long_term | FAIL | 1378.3 | 1410 | 0.0% | missing=LAB-REPORT-1600 |
| G07 | episodic | PASS | 339.3 | 365 | 0.0% |  |
| G08 | episodic | PASS | 292.3 | 383 | 0.0% |  |
| G11 | mixed | PASS | 1688.6 | 581 | 0.0% |  |
| G13 | mixed | FAIL | 562.3 | 500 | 11.5% | missing=ClientSession |
| G15 | mixed | FAIL | 2133.9 | 831 | 0.0% | missing=ASYNC-FIX-20 |
| G16 | mixed | FAIL | 1749.1 | 581 | 0.0% | missing=LAB-REPORT-1600 |
| G17 | mixed | PASS | 1722.7 | 581 | 0.0% |  |
| G18 | mixed | FAIL | 552.8 | 500 | 11.5% | missing=connection churn, BUDGET-10-4-3-3 |
| G19 | mixed | FAIL | 1767.7 | 581 | 0.0% | missing=ClientSession, ASYNC-FIX-20 |
| G05 | long_term | PASS | 1322.1 | 1406 | 0.0% |  |
| G12 | mixed | PASS | 1631.2 | 560 | 11.4% |  |
| G20 | mixed | PASS | 1627.1 | 756 | 0.0% |  |

## Evidence excerpts

### G01 - short_term

`<SESSION_SUMMARY> user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. | assistant: Noted standup constraint. | user: Constraint HOLD-BETA-STAGING: writes go to staging DB only. | assistant: Noted staging constraint. | user: Filler A about button padding. | assistant: Filler A. | user: Filler B about color tokens. | assistant: Filler B. | user: Filler C about copy tone. | assistant: Filler C. </SESSION_SUMMARY> <DURABLE_NOTES> - user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. - assistant: Noted standup constraint. - user: Constraint HOLD-BETA-STAGING: writes go to staging DB only. - assistant: Noted staging constraint. </DURA`

### G02 - short_term

`<RECENT_TURNS> user: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. assistant: Da hieu: demo ca nhan ORCHID-27, uu tien Python, tranh Java, vi du ngan. user: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. assistant: Toi se uu tien timeline khi giai thich coroutine va Task. user: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. </RECENT_TURNS>`

### G06 - long_term

`<USER_SUMMARY> Lan's main pursuit is the LOTUS-88 project, for which they are using Java and Spring Boot for backend examples. They explicitly avoid Python in this context.  Lan prefers using Java and Spring Boot for backend development and does not want to use Python for this purpose. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-01 11:00:00     Source: message     Content: [user] {   "user_id": "lan-lab17",   "first_name": "Lan",   "last_name": "Tran",   "user_alias": "Lan Tran" }: Toi la Lan. Du an cua toi la LOTUS-88. Toi uu tien Java va Spring Boot, va khong dung Python trong vi du backend.   - Created At: `

### G09 - semantic

`EPISODE: {"id":"kb-payment-retry","entity":"Payment API Retry Policy","summary":"For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3.","source":"internal-api-guideline-v3","updated_at":"2026-08-10T00:00:00Z"} metadata= EPISODE: For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3. metadata= EPISODE: {"id":"kb-memory-privacy","entity":"Agent Memory Privacy Rule","summary":"Do not persist personal `

### G10 - semantic

`EPISODE: {"id":"kb-memory-privacy","entity":"Agent Memory Privacy Rule","summary":"Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL.","source":"memory-governance-policy","updated_at":"2026-08-12T00:00:00Z"} metadata= EPISODE: Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL. metadata= EPISODE: {"id":"kb-context-budget","entity":"Memory Context Budget","summary":"Reserve bounded context for memory. This lab uses short-term 10 percent, long-term 4 percent, episodi`

### G14 - mixed

`<LONG_TERM> <USER_SUMMARY> Lan's main pursuit is the LOTUS-88 project, for which they are using Java and Spring Boot for backend examples. They explicitly avoid Python in this context.  Lan prefers using Java and Spring Boot for backend development and does not want to use Python for this purpose. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-17 10:38:46     Source: message     Content: [user] {   "user_id": "lan-lab17",   "first_name": "Lan",   "last_name": "Tran",   "user_alias": "Evaluation User" }: Lan uu tien stack backend nao cho LOTUS-88?   - Created At: 2026-08-01 11:00:20     Source: message     Content`

### G03 - long_term

`<USER_SUMMARY> For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python should not be used for this project. The user still prefers Python for their personal demo project, ORCHID-27.  The user prefers Python and dislikes Java. They prefer short code examples. The user is learning about async/await and sometimes confuses coroutines with Tasks. When this topic arises, they want explanations provided via a timeline. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS; Python is not to be used for this project. However, the user's preference for Python remains for their personal demo project ORCHID-27.  The assistant will prioritiz`

### G04 - long_term

`<USER_SUMMARY> For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python should not be used for this project. The user still prefers Python for their personal demo project, ORCHID-27.  The user prefers Python and dislikes Java. They prefer short code examples. The user is learning about async/await and sometimes confuses coroutines with Tasks. When this topic arises, they want explanations provided via a timeline. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS; Python is not to be used for this project. However, the user's preference for Python remains for their personal demo project ORCHID-27.  The assistant will prioritiz`

### G07 - episodic

`EPISODE: Cap nhat moi: voi du an cong ty BLUEBIRD-42, backend bat buoc dung TypeScript voi NestJS; khong dung Python cho backend du an nay. Preference Python van dung cho demo ca nhan ORCHI EPISODE: Voi demo ca nhan cua Minh, ngon ngu uu tien la gi? EPISODE: Minh con open loop hay deadline nao chua hoan thanh? EPISODE: Backend cua BLUEBIRD-42 bat buoc dung stack gi? EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: Da hieu: demo ca nhan ORCHID-27, uu tien Python, tranh Java, vi du ngan. EPISODE: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeli`

### G08 - episodic

`EPISODE: Cap nhat moi: voi du an cong ty BLUEBIRD-42, backend bat buoc dung TypeScript voi NestJS; khong dung Python cho backend du an nay. Preference Python van dung cho demo ca nhan ORCHI EPISODE: Da tach scope: BLUEBIRD-42 dung TypeScript/NestJS; ORCHID-27 van uu tien Python. EPISODE: Voi demo ca nhan cua Minh, ngon ngu uu tien la gi? EPISODE: Minh con open loop hay deadline nao chua hoan thanh? EPISODE: Backend cua BLUEBIRD-42 bat buoc dung stack gi? EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich ban`

### G11 - mixed

`<LONG_TERM> <USER_SUMMARY> For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python should not be used for this project. The user still prefers Python for their personal demo project, ORCHID-27.  The user prefers Python and dislikes Java. They prefer short code examples. The user is learning about async/await and sometimes confuses coroutines with Tasks. When this topic arises, they want explanations provided via a timeline. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS; Python is not to be used for this project. However, the user's preference for Python remains for their personal demo project ORCHID-27.  The assistant wi`

### G13 - mixed

`<EPISODIC> EPISODE: Cap nhat moi: voi du an cong ty BLUEBIRD-42, backend bat buoc dung TypeScript voi NestJS; khong dung Python cho backend du an nay. Preference Python van dung cho demo ca nhan ORCHI EPISODE: Da tach scope: BLUEBIRD-42 dung TypeScript/NestJS; ORCHID-27 van uu tien Python. EPISODE: Minh con open loop hay deadline nao chua hoan thanh? EPISODE: Backend cua BLUEBIRD-42 bat buoc dung stack gi? EPISODE: Mai hop mentor, toi nay minh muon don open-loop. Liet ke viec chua dong, deadline, va ma dinh danh task. Can du ba manh de ghi vao note hop. EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: Da`

### G15 - mixed

`<LONG_TERM> <USER_SUMMARY> For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python should not be used for this project. The user still prefers Python for their personal demo project, ORCHID-27.  The user prefers Python and dislikes Java. They prefer short code examples. The user is learning about async/await and sometimes confuses coroutines with Tasks. When this topic arises, they want explanations provided via a timeline. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS; Python is not to be used for this project. However, the user's preference for Python remains for their personal demo project ORCHID-27.  The assistant wi`

### G16 - mixed

`<LONG_TERM> <USER_SUMMARY> For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python should not be used for this project. The user still prefers Python for their personal demo project, ORCHID-27.  The user prefers Python and dislikes Java. They prefer short code examples. The user is learning about async/await and sometimes confuses coroutines with Tasks. When this topic arises, they want explanations provided via a timeline. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS; Python is not to be used for this project. However, the user's preference for Python remains for their personal demo project ORCHID-27.  The assistant wi`

### G17 - mixed

`<LONG_TERM> <USER_SUMMARY> For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python should not be used for this project. The user still prefers Python for their personal demo project, ORCHID-27.  The user prefers Python and dislikes Java. They prefer short code examples. The user is learning about async/await and sometimes confuses coroutines with Tasks. When this topic arises, they want explanations provided via a timeline. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS; Python is not to be used for this project. However, the user's preference for Python remains for their personal demo project ORCHID-27.  The assistant wi`

### G18 - mixed

`<EPISODIC> EPISODE: Cap nhat moi: voi du an cong ty BLUEBIRD-42, backend bat buoc dung TypeScript voi NestJS; khong dung Python cho backend du an nay. Preference Python van dung cho demo ca nhan ORCHI EPISODE: Voi demo ca nhan cua Minh, ngon ngu uu tien la gi? EPISODE: Mai hop mentor, toi nay minh muon don open-loop. Liet ke viec chua dong, deadline, va ma dinh danh task. Can du ba manh de ghi vao note hop. EPISODE: Minh sap viet script ca nhan de tai hien su co latency, muon code dung ngon ngu minh thich khi lam mot minh, dong thoi bam sat playbook incident cua lab chu dung vo tang timeout. G EPISODE: Minh con mot open-loop phai nop truoc deadline, dong thoi muon ghi chu retry payment dung `

### G19 - mixed

`<LONG_TERM> <USER_SUMMARY> For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python should not be used for this project. The user still prefers Python for their personal demo project, ORCHID-27.  The user prefers Python and dislikes Java. They prefer short code examples. The user is learning about async/await and sometimes confuses coroutines with Tasks. When this topic arises, they want explanations provided via a timeline. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS; Python is not to be used for this project. However, the user's preference for Python remains for their personal demo project ORCHID-27.  The assistant wi`

### G05 - long_term

`<USER_SUMMARY> For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python should not be used for this project. The user still prefers Python for their personal demo project, ORCHID-27.  The user prefers Python and dislikes Java. They prefer short code examples. The user is learning about async/await and sometimes confuses coroutines with Tasks. When this topic arises, they want explanations provided via a timeline. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS; Python is not to be used for this project. However, the user's preference for Python remains for their personal demo project ORCHID-27.  The assistant will prioritiz`

### G12 - mixed

`<LONG_TERM> <USER_SUMMARY> For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python should not be used for this project. The user still prefers Python for their personal demo project, ORCHID-27.  The user prefers Python and dislikes Java. They prefer short code examples. The user is learning about async/await and sometimes confuses coroutines with Tasks. When this topic arises, they want explanations provided via a timeline. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS; Python is not to be used for this project. However, the user's preference for Python remains for their personal demo project ORCHID-27.  The assistant wi`

### G20 - mixed

`<SHORT_TERM> <SESSION_SUMMARY> user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. | assistant: Noted standup constraint. | user: Filler about dashboard widgets. | assistant: Filler. | user: Filler about CSS variables. | assistant: Filler. | user: Filler about copy review. | assistant: Filler. </SESSION_SUMMARY> <DURABLE_NOTES> - user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. - assistant: Noted standup constraint. </DURABLE_NOTES> <RECENT_TURNS> user: Filler about empty charts. assistant: Filler. user: Filler about telemetry. assistant: Filler. user: Filler about a11y labels. assistant: Filler. </RECENT_TURNS> </SHORT_TERM>`
