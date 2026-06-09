# ATL::CComObject<CMSMQRuleHandler>::~CComObject<CMSMQRuleHandler>(void)

- ea: `0x18000da1c`
- end: `0x18000da5e`
- name: `??1?$CComObject@VCMSMQRuleHandler@@@ATL@@QEAA@XZ`
- size: `66`
- prototype: `void __fastcall(CMSMQRuleHandler *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000dc44`

## callees

- `0x18000561c`
- `0x18000fab4`

## pseudocode

```c
void __fastcall ATL::CComObject<CMSMQRuleHandler>::~CComObject<CMSMQRuleHandler>(CMSMQRuleHandler *this)
{
  *(_QWORD *)this = &ATL::CComObject<CMSMQRuleHandler>::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CMSMQRuleHandler>::`vftable'{for `ATL::IDispatchImpl<IMSMQRuleHandler,&_GUID const IID_IMSMQRuleHandler,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>'};
  *((_DWORD *)this + 4) = 1;
  ATL::CComPtr<IUnknown>::Release((char *)this + 72);
  _InterlockedDecrement(&dword_18002CFF8);
  CMSMQRuleHandler::~CMSMQRuleHandler(this);
}

```

## disassembly

```asm
0x18000da1c  push    rbx
0x18000da1e  sub     rsp, 20h
0x18000da22  mov     rbx, rcx
0x18000da25  lea     rax, ??_7?$CComObject@VCMSMQRuleHandler@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMSMQRuleHandler>::`vftable'{for `ISupportErrorInfo'}
0x18000da2c  mov     [rcx], rax
0x18000da2f  lea     rax, ??_7?$CComObject@VCMSMQRuleHandler@@@ATL@@6B?$IDispatchImpl@UIMSMQRuleHandler@@$1?IID_IMSMQRuleHandler@@3U_GUID@@B$1?LIBID_MSMQTriggerObjects@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMSMQRuleHandler>::`vftable'{for `ATL::IDispatchImpl<IMSMQRuleHandler,&_GUID const IID_IMSMQRuleHandler,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>'}
0x18000da36  mov     [rcx+8], rax
0x18000da3a  mov     dword ptr [rcx+10h], 1
0x18000da41  add     rcx, 48h ; 'H'
0x18000da45  call    ?Release@?$CComPtr@UIUnknown@@@ATL@@QEAAXXZ; ATL::CComPtr<IUnknown>::Release(void)
0x18000da4a  lock dec cs:dword_18002CFF8
0x18000da51  mov     rcx, rbx; this
0x18000da54  add     rsp, 20h
0x18000da58  pop     rbx
0x18000da59  jmp     ??1CMSMQRuleHandler@@QEAA@XZ; CMSMQRuleHandler::~CMSMQRuleHandler(void)
```
