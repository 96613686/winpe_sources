# [thunk]:ATL::CComObject<CRAHelperClass>::QueryInterface`adjustor{56}' (_GUID const &,void * *)

- ea: `0x18000af00`
- end: `0x18000af09`
- name: `?QueryInterface@?$CComObject@VCRAHelperClass@@@ATL@@WDI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `int __fastcall(__int64, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000aed0`

## pseudocode

```c
int __fastcall ATL::CComObject<CRAHelperClass>::QueryInterface(__int64 a1, const struct _GUID *a2, void **a3)
{
  return ATL::CComObject<CRAHelperClass>::QueryInterface((void *)(a1 - 56), a2, a3);
}

```

## disassembly

```asm
0x18000af00  sub     rcx, 38h ; '8'
0x18000af04  jmp     ?QueryInterface@?$CComObject@VCRAHelperClass@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CRAHelperClass>::QueryInterface(_GUID const &,void * *)
```
