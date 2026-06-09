# _CEnhancedStorageSilo::InvokeExternalCommand_::_1_::dtor$0

- ea: `0x18000cc7b`
- end: `0x18000cc87`
- name: `_CEnhancedStorageSilo::InvokeExternalCommand_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002128`

## pseudocode

```c
__int64 __fastcall CEnhancedStorageSilo::InvokeExternalCommand_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(a2 + 104);
}

```

## disassembly

```asm
0x18000cc7b  lea     rcx, [rdx+68h]
0x18000cc82  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
