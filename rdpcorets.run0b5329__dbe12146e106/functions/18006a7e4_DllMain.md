# DllMain

- ea: `0x18006a7e4`
- end: `0x18006aa54`
- name: `DllMain`
- size: `624`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180033c14`

## callees

- `0x180002150`
- `0x180002208`
- `0x180003be0`
- `0x18001bf80`
- `0x180039b80`
- `0x18006a7e4`
- `0x18006ab1c`
- `0x18006ab54`
- `0x18006ac18`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18006a92b`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18006a92b`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18006aa20`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18006aa20`
- `RDPBASE!?RdpPerfLoggerStaticTerminate@@YAXXZ` at `0x18006aa39`
- `RDPBASE!?RdpPerfLoggerStaticTerminate@@YAXXZ` at `0x18006aa39`
- `RDPBASE!RDPServerStackDiagnostics_Register` at `0x18006a89d`
- `RDPBASE!RDPServerStackDiagnostics_Register` at `0x18006a89d`
- `RDPBASE!?RdpPerfLoggerStaticInitialize@@YAXXZ` at `0x18006a922`
- `RDPBASE!?RdpPerfLoggerStaticInitialize@@YAXXZ` at `0x18006a922`
- `RDPBASE!RDPServerStackDiagnostics_Unregister` at `0x18006a9f0`
- `RDPBASE!RDPServerStackDiagnostics_Unregister` at `0x18006a9f0`
- `RDPSERVERBASE!ImgClassifierTrainingDataProvider_Unregister` at `0x18006a9fc`
- `RDPSERVERBASE!ImgClassifierTrainingDataProvider_Unregister` at `0x18006a9fc`
- `RDPSERVERBASE!?RDPGraphicsTraceLogging_Unregister@RDPGraphicsTraceLogging@@YAXXZ` at `0x18006a9d6`
- `RDPSERVERBASE!?RDPGraphicsTraceLogging_Unregister@RDPGraphicsTraceLogging@@YAXXZ` at `0x18006a9d6`
- `RDPSERVERBASE!RDPEncryptionTraceLogging_Unregister` at `0x18006a9d0`
- `RDPSERVERBASE!RDPEncryptionTraceLogging_Unregister` at `0x18006a9d0`
- `RDPSERVERBASE!ImgClassifierTrainingDataProvider_Register` at `0x18006a8a9`
- `RDPSERVERBASE!ImgClassifierTrainingDataProvider_Register` at `0x18006a8a9`
- `RDPSERVERBASE!?RDPServerStackQOE_Register@@YAJXZ` at `0x18006a8a3`
- `RDPSERVERBASE!?RDPServerStackQOE_Register@@YAJXZ` at `0x18006a8a3`
- `RDPSERVERBASE!?RDPGraphicsTraceLogging_Register@RDPGraphicsTraceLogging@@YAJXZ` at `0x18006a880`
- `RDPSERVERBASE!?RDPGraphicsTraceLogging_Register@RDPGraphicsTraceLogging@@YAJXZ` at `0x18006a880`
- `RDPSERVERBASE!RDPEncryptionTraceLogging_Register` at `0x18006a87a`
- `RDPSERVERBASE!RDPEncryptionTraceLogging_Register` at `0x18006a87a`
- `RDPSERVERBASE!?RDPServerStackQOE_Unregister@@YAXXZ` at `0x18006a9f6`
- `RDPSERVERBASE!?RDPServerStackQOE_Unregister@@YAXXZ` at `0x18006a9f6`

## pseudocode

```c

```
