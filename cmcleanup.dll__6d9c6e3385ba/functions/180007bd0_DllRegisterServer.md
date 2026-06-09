# DllRegisterServer

- ea: `0x180007bd0`
- end: `0x180007bd5`
- name: `DllRegisterServer`
- size: `5`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003e04`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall DllRegisterServer()
{
  return CWinTaskModuleT<CmCleanupWim,&_GUID const CLSID_CmCleanup>::DllRegisterServer();
}

```

## disassembly

```asm
0x180007bd0  jmp     ?DllRegisterServer@?$CWinTaskModuleT@VCmCleanupWim@@$1?CLSID_CmCleanup@@3U_GUID@@B@@QEAAJXZ; CWinTaskModuleT<CmCleanupWim,&_GUID const CLSID_CmCleanup>::DllRegisterServer(void)
```
