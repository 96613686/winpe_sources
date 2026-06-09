# ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CPair::~CPair(void)

- ea: `0x18000ee74`
- end: `0x18000ee93`
- name: `??1CPair@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@IEAA@XZ`
- size: `31`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000b7ec`

## callees

- `0x18000ac14`
- `0x18000b5f8`

## pseudocode

```c
__int64 __fastcall ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CPair::~CPair(
        _QWORD *a1)
{
  SmartPtr<CConfigDescriptor>::~SmartPtr<CConfigDescriptor>(a1 + 1);
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(a1);
}

```

## disassembly

```asm
0x18000ee74  push    rbx
0x18000ee76  sub     rsp, 20h
0x18000ee7a  mov     rbx, rcx
0x18000ee7d  add     rcx, 8
0x18000ee81  call    ??1?$SmartPtr@VCConfigDescriptor@@@@QEAA@XZ; SmartPtr<CConfigDescriptor>::~SmartPtr<CConfigDescriptor>(void)
0x18000ee86  mov     rcx, rbx
0x18000ee89  add     rsp, 20h
0x18000ee8d  pop     rbx
0x18000ee8e  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
