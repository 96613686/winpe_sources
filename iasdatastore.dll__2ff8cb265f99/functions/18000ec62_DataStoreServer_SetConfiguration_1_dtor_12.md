# _DataStoreServer::SetConfiguration_::_1_::dtor$12

- ea: `0x18000ec62`
- end: `0x18000ec6e`
- name: `_DataStoreServer::SetConfiguration_::_1_::dtor$12`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800068a4`

## pseudocode

```c
__int64 __fastcall DataStoreServer::SetConfiguration_::_1_::dtor_12(__int64 a1, __int64 a2)
{
  return _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::~_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>((__int64 *)(a2 + 264));
}

```

## disassembly

```asm
0x18000ec62  lea     rcx, [rdx+108h]
0x18000ec69  jmp     ??1?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::~_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>(void)
```
