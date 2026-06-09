# CLogonTaskFramework::s_PerformSignInSuggestionsWaitMethod(CLogonTaskFramework *,LogonFrameworkTelemetry::LogonTask *)

- ea: `0x1400452c0`
- end: `0x140045481`
- name: `?s_PerformSignInSuggestionsWaitMethod@CLogonTaskFramework@@CAJPEAV1@PEAVLogonTask@LogonFrameworkTelemetry@@@Z`
- size: `449`
- prototype: `__int64 __fastcall(struct CLogonTaskFramework *, struct LogonFrameworkTelemetry::LogonTask *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1400452c0`
- `0x1400460b0`
- `0x14009de4c`
- `0x140108218`
- `0x140143904`
- `0x140143964`
- `0x1401439c4`
- `0x140191f0c`
- `0x1401a80e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14004539a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400453cf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14004539a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400453cf`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140045334`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140045334`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1400452eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14004540a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1400452eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14004540a`
- `api-ms-win-core-biplmapi-l1-1-0!BiChangeSessionState` at `0x140045441`
- `api-ms-win-core-biplmapi-l1-1-0!BiChangeSessionState` at `0x140045441`

## string_xrefs

- `0x140045358`: `shell\lib\logontasks\logontasks.cpp`
- `0x140045451`: `shell\lib\logontasks\logontasks.cpp`
- `0x140045326`: `SignInSuggestionsReadyEvent`
- `0x140045460`: `Failed to change BI session state to SessionOemPreinstallComplete`

## pseudocode

```c

```
