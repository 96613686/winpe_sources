# CBaseOutputPin::InitAllocator(IMemAllocator * *)

- ea: `0x18003f210`
- end: `0x18003f23f`
- name: `?InitAllocator@CBaseOutputPin@@UEAAJPEAPEAUIMemAllocator@@@Z`
- size: `47`
- prototype: `HRESULT __fastcall(CBaseOutputPin *this, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18003f22d`
- `ole32!CoCreateInstance` at `0x18003f22d`

## pseudocode

```c
HRESULT __fastcall CBaseOutputPin::InitAllocator(CBaseOutputPin *this, LPVOID *ppv)
{
  return CoCreateInstance(&CLSID_MemoryAllocator, 0, 1u, &IID_IMemAllocator, ppv);
}

```

## disassembly

```asm
0x18003f210  sub     rsp, 38h
0x18003f214  mov     [rsp+38h+ppv], rdx; ppv
0x18003f219  lea     r9, IID_IMemAllocator; riid
0x18003f220  xor     edx, edx; pUnkOuter
0x18003f222  lea     rcx, CLSID_MemoryAllocator; rclsid
0x18003f229  lea     r8d, [rdx+1]; dwClsContext
0x18003f22d  call    cs:__imp_CoCreateInstance
0x18003f234  nop     dword ptr [rax+rax+00h]
0x18003f239  add     rsp, 38h
0x18003f23d  retn
```
