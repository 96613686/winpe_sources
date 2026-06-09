# _DataStoreServer::SetConfiguration_::_1_::dtor$0

- ea: `0x18000ec3e`
- end: `0x18000ec4a`
- name: `_DataStoreServer::SetConfiguration_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800068a4`

## pseudocode

```c
__int64 __fastcall DataStoreServer::SetConfiguration_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::~_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>((__int64 *)(a2 + 152));
}

```

## disassembly

```asm
0x18000ec3e  lea     rcx, [rdx+98h]
0x18000ec45  jmp     ??1?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::~_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>(void)
```
