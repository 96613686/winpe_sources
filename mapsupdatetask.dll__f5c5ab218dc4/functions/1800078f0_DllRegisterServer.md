# DllRegisterServer

- ea: `0x1800078f0`
- end: `0x1800078f5`
- name: `DllRegisterServer`
- size: `5`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180004020`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall DllRegisterServer()
{
  return CWinTaskModuleT<CMapsUpdateTaskHandler,&_GUID const CLSID_MapUpdateTask>::DllRegisterServer();
}

```

## disassembly

```asm
0x1800078f0  jmp     ?DllRegisterServer@?$CWinTaskModuleT@VCMapsUpdateTaskHandler@@$1?CLSID_MapUpdateTask@@3U_GUID@@B@@QEAAJXZ; CWinTaskModuleT<CMapsUpdateTaskHandler,&_GUID const CLSID_MapUpdateTask>::DllRegisterServer(void)
```
