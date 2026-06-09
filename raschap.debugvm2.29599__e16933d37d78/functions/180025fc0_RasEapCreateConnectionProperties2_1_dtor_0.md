# _RasEapCreateConnectionProperties2_::_1_::dtor$0

- ea: `0x180025fc0`
- end: `0x180025fcc`
- name: `_RasEapCreateConnectionProperties2_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000e524`

## pseudocode

```c
__int64 __fastcall RasEapCreateConnectionProperties2_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IXMLDOMParseError2>::~CComPtr<IXMLDOMParseError2>((__int64 *)(a2 + 56));
}

```

## disassembly

```asm
0x180025fc0  lea     rcx, [rdx+38h]
0x180025fc7  jmp     ??1?$CComPtr@UIXMLDOMParseError2@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMParseError2>::~CComPtr<IXMLDOMParseError2>(void)
```
