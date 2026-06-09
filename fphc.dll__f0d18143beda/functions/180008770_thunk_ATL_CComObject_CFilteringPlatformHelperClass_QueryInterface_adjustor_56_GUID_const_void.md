# [thunk]:ATL::CComObject<CFilteringPlatformHelperClass>::QueryInterface`adjustor{56}' (_GUID const &,void * *)

- ea: `0x180008770`
- end: `0x180008779`
- name: `?QueryInterface@?$CComObject@VCFilteringPlatformHelperClass@@@ATL@@WDI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008740`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CFilteringPlatformHelperClass>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        char **a3)
{
  return ATL::CComObject<CFilteringPlatformHelperClass>::QueryInterface((char *)(a1 - 56), a2, a3);
}

```

## disassembly

```asm
0x180008770  sub     rcx, 38h ; '8'
0x180008774  jmp     ?QueryInterface@?$CComObject@VCFilteringPlatformHelperClass@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CFilteringPlatformHelperClass>::QueryInterface(_GUID const &,void * *)
```
