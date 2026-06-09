# ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CPair::~CPair(void)

- ea: `0x18000ee9c`
- end: `0x18000eebb`
- name: `??1CPair@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@IEAA@XZ`
- size: `31`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b6f0`

## callees

- `0x18000ac14`
- `0x18000be90`

## pseudocode

```c
__int64 __fastcall ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CPair::~CPair(
        _QWORD *a1)
{
  SmartPtr<CVolumeTrackingDescriptor>::~SmartPtr<CVolumeTrackingDescriptor>(a1 + 1);
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(a1);
}

```

## disassembly

```asm
0x18000ee9c  push    rbx
0x18000ee9e  sub     rsp, 20h
0x18000eea2  mov     rbx, rcx
0x18000eea5  add     rcx, 8
0x18000eea9  call    ??1?$SmartPtr@VCVolumeTrackingDescriptor@@@@QEAA@XZ; SmartPtr<CVolumeTrackingDescriptor>::~SmartPtr<CVolumeTrackingDescriptor>(void)
0x18000eeae  mov     rcx, rbx
0x18000eeb1  add     rsp, 20h
0x18000eeb5  pop     rbx
0x18000eeb6  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
