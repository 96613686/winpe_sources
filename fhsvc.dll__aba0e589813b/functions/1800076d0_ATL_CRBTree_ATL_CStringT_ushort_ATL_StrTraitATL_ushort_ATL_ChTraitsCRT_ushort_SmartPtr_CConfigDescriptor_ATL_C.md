# ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Successor(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)

- ea: `0x1800076d0`
- end: `0x180007714`
- name: `?Successor@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@IEBAPEAVCNode@12@PEAV312@@Z`
- size: `68`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800020c0`
- `0x180003f00`
- `0x18000ac48`
- `0x18000f14c`
- `0x18000f2c0`
- `0x18000f7c8`

## callees

- `0x180007300`
- `0x1800076d0`

## pseudocode

```c
__int64 __fastcall ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Successor(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax
  __int64 v3; // rax
  __int64 i; // rcx
  char v5; // dl

  if ( !a2 )
    return 0;
  v3 = *(_QWORD *)(a1 + 40);
  if ( *(_QWORD *)(a2 + 32) != v3 )
    return ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Minimum(
             a1,
             *(_QWORD *)(a2 + 32));
  for ( i = *(_QWORD *)(a2 + 40); i != v3; i = *(_QWORD *)(i + 40) )
  {
    if ( a2 != *(_QWORD *)(i + 32) )
    {
      v5 = 0;
      goto LABEL_11;
    }
    a2 = i;
  }
  v5 = 1;
LABEL_11:
  result = 0;
  if ( !v5 )
    return i;
  return result;
}

```

## disassembly

```asm
0x1800076d0  test    rdx, rdx
0x1800076d3  jnz     short loc_1800076D8
0x1800076d5  xor     eax, eax
0x1800076d7  retn
0x1800076d8  mov     rax, [rcx+28h]
0x1800076dc  mov     r8, [rdx+20h]
0x1800076e0  cmp     r8, rax
0x1800076e3  jz      short loc_1800076ED
0x1800076e5  mov     rdx, r8
0x1800076e8  jmp     ?Minimum@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@IEBAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Minimum(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)
0x1800076ed  mov     rcx, [rdx+28h]
0x1800076f1  cmp     rcx, rax
0x1800076f4  jz      short loc_180007709
0x1800076f6  cmp     rdx, [rcx+20h]
0x1800076fa  jnz     short loc_180007705
0x1800076fc  mov     rdx, rcx
0x1800076ff  mov     rcx, [rcx+28h]
0x180007703  jmp     short loc_1800076F1
0x180007705  xor     dl, dl
0x180007707  jmp     short loc_18000770B
0x180007709  mov     dl, 1
0x18000770b  xor     eax, eax
0x18000770d  test    dl, dl
0x18000770f  cmovz   rax, rcx
0x180007713  retn
```
