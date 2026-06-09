# CEffectCompilationService::OnTaskCompleted_AnyThread(CEffectCompilationTask *,bool)

- ea: `0x1801a09a0`
- end: `0x1801a0a57`
- name: `?OnTaskCompleted_AnyThread@CEffectCompilationService@@AEAAXPEAVCEffectCompilationTask@@_N@Z`
- size: `183`
- prototype: `void __fastcall(CEffectCompilationService *this, struct CEffectCompilationTask *, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801a07f4`
- `0x180242388`

## callees

- `0x1801a09a0`
- `0x1801a0a60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801a0a37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801a0a37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801a09b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801a09b9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1801a0a29`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1801a0a29`

## pseudocode

```c

```
