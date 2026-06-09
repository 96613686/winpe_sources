# _CManagerThread::StartTargetVolumeTracking_::_1_::dtor$1

- ea: `0x180011d5e`
- end: `0x180011d6a`
- name: `_CManagerThread::StartTargetVolumeTracking_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000ac14`

## pseudocode

```c
__int64 __fastcall CManagerThread::StartTargetVolumeTracking_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((_QWORD *)(a2 + 88));
}

```

## disassembly

```asm
0x180011d5e  lea     rcx, [rdx+58h]
0x180011d65  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
