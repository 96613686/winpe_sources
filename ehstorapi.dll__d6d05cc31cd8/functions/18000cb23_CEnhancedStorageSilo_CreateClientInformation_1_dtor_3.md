# _CEnhancedStorageSilo::CreateClientInformation_::_1_::dtor$3

- ea: `0x18000cb23`
- end: `0x18000cb2f`
- name: `_CEnhancedStorageSilo::CreateClientInformation_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002128`

## pseudocode

```c
__int64 __fastcall CEnhancedStorageSilo::CreateClientInformation_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(a2 + 80);
}

```

## disassembly

```asm
0x18000cb23  lea     rcx, [rdx+50h]
0x18000cb2a  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
