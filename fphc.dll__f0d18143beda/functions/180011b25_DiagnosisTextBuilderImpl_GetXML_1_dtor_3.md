# _DiagnosisTextBuilderImpl::GetXML_::_1_::dtor$3

- ea: `0x180011b25`
- end: `0x180011b31`
- name: `_DiagnosisTextBuilderImpl::GetXML_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000d73c`

## pseudocode

```c
__int64 __fastcall DiagnosisTextBuilderImpl::GetXML_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(a2 + 32);
}

```

## disassembly

```asm
0x180011b25  lea     rcx, [rdx+20h]
0x180011b2c  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
