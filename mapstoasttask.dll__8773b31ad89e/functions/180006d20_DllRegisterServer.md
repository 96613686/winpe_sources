# DllRegisterServer

- ea: `0x180006d20`
- end: `0x180006d25`
- name: `DllRegisterServer`
- size: `5`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003560`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall DllRegisterServer()
{
  return CWinTaskModuleT<CMapsToastTaskHandler,&_GUID const CLSID_MapsToastTask>::DllRegisterServer();
}

```

## disassembly

```asm
0x180006d20  jmp     ?DllRegisterServer@?$CWinTaskModuleT@VCMapsToastTaskHandler@@$1?CLSID_MapsToastTask@@3U_GUID@@B@@QEAAJXZ; CWinTaskModuleT<CMapsToastTaskHandler,&_GUID const CLSID_MapsToastTask>::DllRegisterServer(void)
```
