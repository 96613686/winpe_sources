# _CConfigDescriptor::CConfigDescriptor_::_1_::dtor$0

- ea: `0x18001203d`
- end: `0x180012049`
- name: `_CConfigDescriptor::CConfigDescriptor_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000ac14`

## pseudocode

```c
__int64 __fastcall CConfigDescriptor::CConfigDescriptor_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(*(_QWORD **)(a2 + 48));
}

```

## disassembly

```asm
0x18001203d  mov     rcx, [rdx+30h]
0x180012044  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
