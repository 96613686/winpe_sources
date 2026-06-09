# _CManagerThread::AddRemoveRegisteredConfig_::_1_::dtor$0

- ea: `0x180012530`
- end: `0x18001253c`
- name: `_CManagerThread::AddRemoveRegisteredConfig_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000ac14`

## pseudocode

```c
__int64 __fastcall CManagerThread::AddRemoveRegisteredConfig_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(*(_QWORD **)(a2 + 136));
}

```

## disassembly

```asm
0x180012530  mov     rcx, [rdx+88h]
0x180012537  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
