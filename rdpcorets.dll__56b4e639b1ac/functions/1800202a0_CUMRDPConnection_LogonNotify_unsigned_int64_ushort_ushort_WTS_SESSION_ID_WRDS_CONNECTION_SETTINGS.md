# CUMRDPConnection::LogonNotify(unsigned __int64,ushort *,ushort *,_WTS_SESSION_ID *,_WRDS_CONNECTION_SETTINGS *)

- ea: `0x1800202a0`
- end: `0x1800207be`
- name: `?LogonNotify@CUMRDPConnection@@UEAAJ_KPEAG1PEAU_WTS_SESSION_ID@@PEAU_WRDS_CONNECTION_SETTINGS@@@Z`
- size: `1310`
- prototype: `__int64 __fastcall(CUMRDPConnection *__hidden this, unsigned __int64, unsigned __int16 *, unsigned __int16 *, struct _WTS_SESSION_ID *, struct _WRDS_CONNECTION_SETTINGS *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800013e8`
- `0x1800015f0`
- `0x180002ea4`
- `0x1800071c0`
- `0x1800071f0`
- `0x180009088`
- `0x18000ee00`
- `0x18000f784`
- `0x180012200`
- `0x18001e49c`
- `0x1800202a0`
- `0x180033da0`
- `0x1800549a8`
- `0x18014d010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180020305`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002077b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180020305`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002077b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800206d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800206d5`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18002031d`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18002031d`
- `RDPBASE!RDPServerStackDiagnostics_LogCheckpoint` at `0x1800204b3`
- `RDPBASE!RDPServerStackDiagnostics_LogCheckpoint` at `0x1800204b3`
- `RDPBASE!RDPServerStackDiagnostics_LogContext` at `0x1800204d2`
- `RDPBASE!RDPServerStackDiagnostics_LogContext` at `0x1800204d2`

## string_xrefs

- `0x180020420`: `IWRdsProtocolConnection`
- `0x1800204fe`: `Failed to start RAIL Ready Event Monitor`
- `0x1800206f7`: `m_spCommandMgr is not initialized!`
- `0x1800206bd`: `GdxPlugin->LogonNotify`

## pseudocode

```c

```
