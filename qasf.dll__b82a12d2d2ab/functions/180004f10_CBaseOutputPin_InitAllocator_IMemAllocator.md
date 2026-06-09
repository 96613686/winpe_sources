# CBaseOutputPin::InitAllocator(IMemAllocator * *)

- ea: `0x180004f10`
- end: `0x180004f38`
- name: `?InitAllocator@CBaseOutputPin@@UEAAJPEAPEAUIMemAllocator@@@Z`
- size: `40`
- prototype: `int(CBaseOutputPin *__hidden this, struct IMemAllocator **)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180004f2d`
- `ole32!CoCreateInstance` at `0x180004f2d`

## pseudocode

```c
HRESULT __fastcall CBaseOutputPin::InitAllocator(CBaseOutputPin *this, LPVOID *ppv)
{
  return CoCreateInstance(&CLSID_MemoryAllocator, 0, 1u, &IID_IMemAllocator, ppv);
}

```

## disassembly

```asm
0x180004f10  sub     rsp, 38h
0x180004f14  mov     [rsp+38h+ppv], rdx; ppv
0x180004f19  lea     r9, IID_IMemAllocator; riid
0x180004f20  xor     edx, edx; pUnkOuter
0x180004f22  lea     rcx, CLSID_MemoryAllocator; rclsid
0x180004f29  lea     r8d, [rdx+1]; dwClsContext
0x180004f2d  call    cs:__imp_CoCreateInstance
0x180004f33  add     rsp, 38h
0x180004f37  retn
```
