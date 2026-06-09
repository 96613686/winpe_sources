# Microsoft::Diagnostics::IAsimovEvent::RecordSystemStateFlags(bool,unsigned __int64)

- ea: `0x180054564`
- end: `0x18005499f`
- name: `?RecordSystemStateFlags@IAsimovEvent@Diagnostics@Microsoft@@QEAAX_N_K@Z`
- size: `1083`
- prototype: `void __fastcall(Microsoft::Diagnostics::IAsimovEvent *__hidden this, bool, unsigned __int64)`
- caller_count: `3`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18005f660`
- `0x1800adbd8`
- `0x1801822a4`

## callees

- `0x180054564`
- `0x180054a74`
- `0x1800552c0`
- `0x1800552d8`
- `0x180055730`
- `0x1800557d8`
- `0x180118e1c`
- `0x18014cff0`
- `0x1801bbc78`
- `0x18024a250`
- `0x180369010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180054898`
- `msvcp_win!_Mtx_unlock` at `0x1800548b0`
- `msvcp_win!_Mtx_unlock` at `0x1800548ee`
- `msvcp_win!_Mtx_unlock` at `0x180054920`
- `msvcp_win!_Mtx_unlock` at `0x180054898`
- `msvcp_win!_Mtx_unlock` at `0x1800548b0`
- `msvcp_win!_Mtx_unlock` at `0x1800548ee`
- `msvcp_win!_Mtx_unlock` at `0x180054920`
- `ntdll!NtPowerInformation` at `0x180054947`
- `ntdll!NtPowerInformation` at `0x180054947`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800547bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005495a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800547bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005495a`

## string_xrefs

- `0x18005498d`: `onecore\base\telemetry\utc\service\engine\systemstatemanager.cpp`
- `0x180054824`: `onecore\base\telemetry\utc\service\include\LifetimeManager.h`
- `0x18005483a`: `onecore\base\telemetry\utc\service\include\LifetimeManager.h`

## pseudocode

```c

```
