# _MsChapV2CreateConnectionProperties_::_1_::dtor$5

- ea: `0x180026000`
- end: `0x18002600c`
- name: `_MsChapV2CreateConnectionProperties_::_1_::dtor$5`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000e524`

## pseudocode

```c
__int64 __fastcall MsChapV2CreateConnectionProperties_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IXMLDOMParseError2>::~CComPtr<IXMLDOMParseError2>((__int64 *)(a2 + 40));
}

```

## disassembly

```asm
0x180026000  lea     rcx, [rdx+28h]
0x180026007  jmp     ??1?$CComPtr@UIXMLDOMParseError2@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMParseError2>::~CComPtr<IXMLDOMParseError2>(void)
```
