# [thunk]:ATL::CComObject<CFilteringPlatformHelperClass>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180008760`
- end: `0x180008769`
- name: `?QueryInterface@?$CComObject@VCFilteringPlatformHelperClass@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
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
  return ATL::CComObject<CFilteringPlatformHelperClass>::QueryInterface((char *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x180008760  sub     rcx, 8
0x180008764  jmp     ?QueryInterface@?$CComObject@VCFilteringPlatformHelperClass@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CFilteringPlatformHelperClass>::QueryInterface(_GUID const &,void * *)
```
