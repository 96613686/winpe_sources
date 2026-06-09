# _CEnhancedStorageSilo::CreateClientInformation_::_1_::dtor$2

- ea: `0x18000cb11`
- end: `0x18000cb1d`
- name: `_CEnhancedStorageSilo::CreateClientInformation_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002128`

## pseudocode

```c
__int64 __fastcall CEnhancedStorageSilo::CreateClientInformation_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(a2 + 56);
}

```

## disassembly

```asm
0x18000cb11  lea     rcx, [rdx+38h]
0x18000cb18  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
