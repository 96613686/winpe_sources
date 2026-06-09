# CBaseOutputPin::InitAllocator(IMemAllocator * *)

- ea: `0x100320d0`
- end: `0x100320f0`
- name: `?InitAllocator@CBaseOutputPin@@UAEJPAPAUIMemAllocator@@@Z`
- size: `32`
- prototype: `int __thiscall(CBaseOutputPin *__hidden this, struct IMemAllocator **)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `ole32!CoCreateInstance` at `0x100320e6`
- `ole32!CoCreateInstance` at `0x100320e6`

## pseudocode

```c
HRESULT __thiscall CBaseOutputPin::InitAllocator(CBaseOutputPin *this, LPVOID *ppv)
{
  return CoCreateInstance(&CLSID_MemoryAllocator, 0, 1u, &IID_IMemAllocator, ppv);
}

```

## disassembly

```asm
0x100320d0  mov     edi, edi
0x100320d2  push    ebp
0x100320d3  mov     ebp, esp
0x100320d5  push    [ebp+ppv]; ppv
0x100320d8  push    offset _IID_IMemAllocator; riid
0x100320dd  push    1; dwClsContext
0x100320df  push    0; pUnkOuter
0x100320e1  push    offset _CLSID_MemoryAllocator; rclsid
0x100320e6  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x100320ec  pop     ebp
0x100320ed  retn    4
```
