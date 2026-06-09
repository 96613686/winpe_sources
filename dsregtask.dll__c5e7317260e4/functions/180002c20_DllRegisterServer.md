# DllRegisterServer

- ea: `0x180002c20`
- end: `0x180002c25`
- name: `DllRegisterServer`
- size: `5`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002218`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall DllRegisterServer()
{
  return CWinTaskModuleT<CDsregTaskHandler,&_GUID const CLSID_DsregTask>::DllRegisterServer();
}

```

## disassembly

```asm
0x180002c20  jmp     ?DllRegisterServer@?$CWinTaskModuleT@VCDsregTaskHandler@@$1?CLSID_DsregTask@@3U_GUID@@B@@QEAAJXZ; CWinTaskModuleT<CDsregTaskHandler,&_GUID const CLSID_DsregTask>::DllRegisterServer(void)
```
