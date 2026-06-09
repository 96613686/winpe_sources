# DllRegisterServer

- ea: `0x180002f60`
- end: `0x180002f65`
- name: `DllRegisterServer`
- size: `5`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001df0`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall DllRegisterServer()
{
  return CWinTaskModuleT<CEnergyTaskHandler,&_GUID const CLSID_EnergyTask>::DllRegisterServer();
}

```

## disassembly

```asm
0x180002f60  jmp     ?DllRegisterServer@?$CWinTaskModuleT@VCEnergyTaskHandler@@$1?CLSID_EnergyTask@@3U_GUID@@B@@QEAAJXZ; CWinTaskModuleT<CEnergyTaskHandler,&_GUID const CLSID_EnergyTask>::DllRegisterServer(void)
```
