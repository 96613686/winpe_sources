# _DiagnosisTextBuilderImpl::GetXML_::_1_::dtor$0

- ea: `0x180011b01`
- end: `0x180011b0d`
- name: `_DiagnosisTextBuilderImpl::GetXML_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000d73c`

## pseudocode

```c
__int64 __fastcall DiagnosisTextBuilderImpl::GetXML_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(a2 + 136);
}

```

## disassembly

```asm
0x180011b01  lea     rcx, [rdx+88h]
0x180011b08  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
