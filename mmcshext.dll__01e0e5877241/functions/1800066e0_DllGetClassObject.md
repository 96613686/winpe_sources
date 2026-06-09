# DllGetClassObject

- ea: `0x1800066e0`
- end: `0x1800066ee`
- name: `DllGetClassObject`
- size: `14`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003604`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  return ATL::AtlModuleGetClassObject((struct ATL::_ATL_MODULE *)rclsid, rclsid, riid, ppv);
}

```

## disassembly

```asm
0x1800066e0  mov     r9, r8; void **
0x1800066e3  mov     r8, rdx; struct _GUID *
0x1800066e6  mov     rdx, rcx; struct _GUID *
0x1800066e9  jmp     ?AtlModuleGetClassObject@ATL@@YAJPEAU_ATL_MODULE@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlModuleGetClassObject(ATL::_ATL_MODULE *,_GUID const &,_GUID const &,void * *)
```
