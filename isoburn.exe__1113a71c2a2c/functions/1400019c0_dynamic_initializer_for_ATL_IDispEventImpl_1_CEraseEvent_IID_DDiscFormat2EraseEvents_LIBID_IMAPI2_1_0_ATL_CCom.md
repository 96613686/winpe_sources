# _dynamic_initializer_for__ATL::IDispEventImpl_1_CEraseEvent_&IID_DDiscFormat2EraseEvents_&LIBID_IMAPI2_1_0_ATL::CComTypeInfoHolder_::m_InnerLibid__

- ea: `0x1400019c0`
- end: `0x1400019d0`
- name: `_dynamic_initializer_for__ATL::IDispEventImpl_1_CEraseEvent_&IID_DDiscFormat2EraseEvents_&LIBID_IMAPI2_1_0_ATL::CComTypeInfoHolder_::m_InnerLibid__`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
void dynamic_initializer_for__ATL::IDispEventImpl_1_CEraseEvent__IID_DDiscFormat2EraseEvents__LIBID_IMAPI2_1_0_ATL::CComTypeInfoHolder_::m_InnerLibid__()
{
  ATL::IDispEventImpl<1,CEraseEvent,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerLibid = GUID_NULL;
}

```

## disassembly

```asm
0x1400019c0  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1400019c7  movdqu  xmmword ptr cs:?m_InnerLibid@?$IDispEventImpl@$00VCEraseEvent@@$1?IID_DDiscFormat2EraseEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1U_GUID@@A.Data1, xmm0; _GUID ATL::IDispEventImpl<1,CEraseEvent,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerLibid ...
0x1400019cf  retn
```
