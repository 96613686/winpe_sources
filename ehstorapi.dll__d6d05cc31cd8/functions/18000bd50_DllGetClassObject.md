# DllGetClassObject

- ea: `0x18000bd50`
- end: `0x18000bd5e`
- name: `DllGetClassObject`
- size: `14`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a21c`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  return ATL::CComModule::GetClassObject((ATL::CComModule *)rclsid, rclsid, riid, ppv);
}

```

## disassembly

```asm
0x18000bd50  mov     r9, r8; void **
0x18000bd53  mov     r8, rdx; struct _GUID *
0x18000bd56  mov     rdx, rcx; struct _GUID *
0x18000bd59  jmp     ?GetClassObject@CComModule@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z; ATL::CComModule::GetClassObject(_GUID const &,_GUID const &,void * *)
```
