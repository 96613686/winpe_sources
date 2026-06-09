# CRevOrderCaseInsensitiveCStringWTraits::CompareElementsOrdered(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x1800175fc`
- end: `0x18001762a`
- name: `?CompareElementsOrdered@CRevOrderCaseInsensitiveCStringWTraits@@SAHAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z`
- size: `46`
- prototype: `__int64 __fastcall(LPCWCH *, LPCWCH *)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180018c6c`
- `0x180018da0`
- `0x18001a3e4`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x180017616`
- `KERNEL32!CompareStringOrdinal` at `0x180017616`

## pseudocode

```c
__int64 __fastcall CRevOrderCaseInsensitiveCStringWTraits::CompareElementsOrdered(LPCWCH *a1, LPCWCH *a2)
{
  return (unsigned int)(2 - CompareStringOrdinal(*a1, -1, *a2, -1, 1));
}

```

## disassembly

```asm
0x1800175fc  sub     rsp, 38h
0x180017600  mov     r8, [rdx]; lpString2
0x180017603  or      eax, 0FFFFFFFFh
0x180017606  mov     rcx, [rcx]; lpString1
0x180017609  mov     r9d, eax; cchCount2
0x18001760c  mov     edx, eax; cchCount1
0x18001760e  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180017616  call    cs:__imp_CompareStringOrdinal
0x18001761c  mov     ecx, 2
0x180017621  sub     ecx, eax
0x180017623  mov     eax, ecx
0x180017625  add     rsp, 38h
0x180017629  retn
```
