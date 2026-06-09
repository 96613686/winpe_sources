# CRevOrderCaseInsensitiveCStringWTraits::CompareElements(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x1800175c8`
- end: `0x1800175f3`
- name: `?CompareElements@CRevOrderCaseInsensitiveCStringWTraits@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z`
- size: `43`
- prototype: `bool __fastcall(LPCWCH *, LPCWCH *)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180018c6c`
- `0x180018da0`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1800175e2`
- `KERNEL32!CompareStringOrdinal` at `0x1800175e2`

## pseudocode

```c
bool __fastcall CRevOrderCaseInsensitiveCStringWTraits::CompareElements(LPCWCH *a1, LPCWCH *a2)
{
  return CompareStringOrdinal(*a1, -1, *a2, -1, 1) == 2;
}

```

## disassembly

```asm
0x1800175c8  sub     rsp, 38h
0x1800175cc  mov     r8, [rdx]; lpString2
0x1800175cf  or      eax, 0FFFFFFFFh
0x1800175d2  mov     rcx, [rcx]; lpString1
0x1800175d5  mov     r9d, eax; cchCount2
0x1800175d8  mov     edx, eax; cchCount1
0x1800175da  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800175e2  call    cs:__imp_CompareStringOrdinal
0x1800175e8  cmp     eax, 2
0x1800175eb  setz    al
0x1800175ee  add     rsp, 38h
0x1800175f2  retn
```
