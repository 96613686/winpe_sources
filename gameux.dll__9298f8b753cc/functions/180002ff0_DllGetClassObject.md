# DllGetClassObject

- ea: `0x180002ff0`
- end: `0x180002ffe`
- name: `DllGetClassObject`
- size: `14`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002db8`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  return ATL::AtlComModuleGetClassObject((struct ATL::_ATL_COM_MODULE70 *)rclsid, rclsid, riid, ppv);
}

```

## disassembly

```asm
0x180002ff0  mov     r9, r8; void **
0x180002ff3  mov     r8, rdx; struct _GUID *
0x180002ff6  mov     rdx, rcx; struct _GUID *
0x180002ff9  jmp     ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
```
