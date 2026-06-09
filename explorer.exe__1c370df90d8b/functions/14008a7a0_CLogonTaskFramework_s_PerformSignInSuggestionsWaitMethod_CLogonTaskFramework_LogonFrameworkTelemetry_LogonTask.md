# CLogonTaskFramework::s_PerformSignInSuggestionsWaitMethod(CLogonTaskFramework *,LogonFrameworkTelemetry::LogonTask *)

- ea: `0x14008a7a0`
- end: `0x14008a93c`
- name: `?s_PerformSignInSuggestionsWaitMethod@CLogonTaskFramework@@CAJPEAV1@PEAVLogonTask@LogonFrameworkTelemetry@@@Z`
- size: `412`
- prototype: `__int64 __fastcall(struct CLogonTaskFramework *, struct LogonFrameworkTelemetry::LogonTask *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x14001d5b8`
- `0x14008a7a0`
- `0x1400987b8`
- `0x1400ff590`
- `0x1401377a4`
- `0x140137800`
- `0x14013785c`
- `0x140185dcc`
- `0x1401a78f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14008a86e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14008a89d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14008a86e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14008a89d`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14008a80e`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14008a80e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14008a7cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14008a8d2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14008a7cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14008a8d2`
- `api-ms-win-core-biplmapi-l1-1-0!BiChangeSessionState` at `0x14008a903`
- `api-ms-win-core-biplmapi-l1-1-0!BiChangeSessionState` at `0x14008a903`

## string_xrefs

- `0x14008a82c`: `shell\lib\logontasks\logontasks.cpp`
- `0x14008a90d`: `shell\lib\logontasks\logontasks.cpp`
- `0x14008a800`: `SignInSuggestionsReadyEvent`
- `0x14008a91c`: `Failed to change BI session state to SessionOemPreinstallComplete`

## pseudocode

```c

```
