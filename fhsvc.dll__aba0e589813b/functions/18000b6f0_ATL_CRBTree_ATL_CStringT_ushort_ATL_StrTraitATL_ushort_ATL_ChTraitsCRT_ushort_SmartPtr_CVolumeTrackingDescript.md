# ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::FreeNode(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)

- ea: `0x18000b6f0`
- end: `0x18000b733`
- name: `?FreeNode@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@AEAAXPEAVCNode@12@@Z`
- size: `67`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b6a8`
- `0x18000f8cc`

## callees

- `0x18000b48c`
- `0x18000b6f0`
- `0x18000ee9c`

## pseudocode

```c
__int64 __fastcall ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::FreeNode(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax

  if ( !a2 )
    ATL::AtlThrowImpl(-2147467259);
  ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CPair::~CPair(a2);
  result = *(_QWORD *)(a1 + 16);
  a2[3] = result;
  *(_QWORD *)(a1 + 16) = a2;
  --*(_QWORD *)(a1 + 8);
  return result;
}

```

## disassembly

```asm
0x18000b6f0  mov     [rsp+arg_0], rbx
0x18000b6f5  push    rdi
0x18000b6f6  sub     rsp, 20h
0x18000b6fa  mov     rbx, rdx
0x18000b6fd  mov     rdi, rcx
0x18000b700  test    rdx, rdx
0x18000b703  jnz     short loc_18000B710
0x18000b705  mov     ecx, 80004005h; int
0x18000b70a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000b710  mov     rcx, rbx
0x18000b713  call    ??1CPair@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@IEAA@XZ; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CPair::~CPair(void)
0x18000b718  mov     rax, [rdi+10h]
0x18000b71c  mov     [rbx+18h], rax
0x18000b720  mov     [rdi+10h], rbx
0x18000b724  dec     qword ptr [rdi+8]
0x18000b728  mov     rbx, [rsp+28h+arg_0]
0x18000b72d  add     rsp, 20h
0x18000b731  pop     rdi
0x18000b732  retn
```
