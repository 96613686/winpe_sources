# _dynamic_initializer_for__ATL::IDispEventImpl_1_CIsoBurn_&IID_DDiscFormat2DataEvents_&LIBID_IMAPI2_1_0_ATL::CComTypeInfoHolder_::m_InnerIid__

- ea: `0x1400019a0`
- end: `0x1400019b0`
- name: `_dynamic_initializer_for__ATL::IDispEventImpl_1_CIsoBurn_&IID_DDiscFormat2DataEvents_&LIBID_IMAPI2_1_0_ATL::CComTypeInfoHolder_::m_InnerIid__`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
void dynamic_initializer_for__ATL::IDispEventImpl_1_CIsoBurn__IID_DDiscFormat2DataEvents__LIBID_IMAPI2_1_0_ATL::CComTypeInfoHolder_::m_InnerIid__()
{
  ATL::IDispEventImpl<1,CIsoBurn,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerIid = GUID_NULL;
}

```

## disassembly

```asm
0x1400019a0  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1400019a7  movdqu  xmmword ptr cs:?m_InnerIid@?$IDispEventImpl@$00VCIsoBurn@@$1?IID_DDiscFormat2DataEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1U_GUID@@A.Data1, xmm0; _GUID ATL::IDispEventImpl<1,CIsoBurn,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerIid ...
0x1400019af  retn
```
