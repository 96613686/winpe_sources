# _CManagerThread::ValidateAndCountRegisteredConfigs_::_1_::dtor$3

- ea: `0x180011a90`
- end: `0x180011a9c`
- name: `_CManagerThread::ValidateAndCountRegisteredConfigs_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000ac14`

## pseudocode

```c
__int64 __fastcall CManagerThread::ValidateAndCountRegisteredConfigs_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((_QWORD *)(a2 + 80));
}

```

## disassembly

```asm
0x180011a90  lea     rcx, [rdx+50h]
0x180011a97  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
