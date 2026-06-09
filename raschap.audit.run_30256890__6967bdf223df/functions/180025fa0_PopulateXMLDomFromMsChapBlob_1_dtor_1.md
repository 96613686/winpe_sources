# _PopulateXMLDomFromMsChapBlob_::_1_::dtor$1

- ea: `0x180025fa0`
- end: `0x180025fac`
- name: `_PopulateXMLDomFromMsChapBlob_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000e524`

## pseudocode

```c
__int64 __fastcall PopulateXMLDomFromMsChapBlob_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IXMLDOMParseError2>::~CComPtr<IXMLDOMParseError2>((__int64 *)(a2 + 208));
}

```

## disassembly

```asm
0x180025fa0  lea     rcx, [rdx+0D0h]
0x180025fa7  jmp     ??1?$CComPtr@UIXMLDOMParseError2@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMParseError2>::~CComPtr<IXMLDOMParseError2>(void)
```
