# ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Minimum(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)

- ea: `0x180007300`
- end: `0x180007323`
- name: `?Minimum@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@IEBAPEAVCNode@12@PEAV312@@Z`
- size: `35`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180003190`
- `0x180003f00`
- `0x1800062b0`
- `0x1800076d0`
- `0x18000ac48`
- `0x18000f14c`
- `0x18000f2c0`

## callees

- `0x180007300`

## pseudocode

```c
__int64 __fastcall ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Minimum(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rax

  if ( !a2 )
    return 0;
  v2 = *(_QWORD *)(a1 + 40);
  if ( a2 == v2 )
    return 0;
  while ( *(_QWORD *)(a2 + 24) != v2 )
    a2 = *(_QWORD *)(a2 + 24);
  return a2;
}

```

## disassembly

```asm
0x180007300  test    rdx, rdx
0x180007303  jz      short loc_180007320
0x180007305  mov     rax, [rcx+28h]
0x180007309  cmp     rdx, rax
0x18000730c  jz      short loc_180007320
0x18000730e  mov     rcx, [rdx+18h]
0x180007312  cmp     rcx, rax
0x180007315  jz      short loc_18000731C
0x180007317  mov     rdx, rcx
0x18000731a  jmp     short loc_18000730E
0x18000731c  mov     rax, rdx
0x18000731f  retn
0x180007320  xor     eax, eax
0x180007322  retn
```
