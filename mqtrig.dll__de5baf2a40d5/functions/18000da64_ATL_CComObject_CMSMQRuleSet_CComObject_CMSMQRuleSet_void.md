# ATL::CComObject<CMSMQRuleSet>::~CComObject<CMSMQRuleSet>(void)

- ea: `0x18000da64`
- end: `0x18000daa9`
- name: `??1?$CComObject@VCMSMQRuleSet@@@ATL@@QEAA@XZ`
- size: `69`
- prototype: `void __fastcall(CMSMQRuleSet *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000dc6c`

## callees

- `0x18000a22c`
- `0x18000fab4`

## pseudocode

```c
void __fastcall ATL::CComObject<CMSMQRuleSet>::~CComObject<CMSMQRuleSet>(CMSMQRuleSet *this)
{
  *(_QWORD *)this = &ATL::CComObject<CMSMQRuleSet>::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CMSMQRuleSet>::`vftable'{for `ATL::IDispatchImpl<IMSMQRuleSet,&_GUID const IID_IMSMQRuleSet,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>'};
  *((_DWORD *)this + 4) = 1;
  ATL::CComPtr<IUnknown>::Release((char *)this + 1184);
  _InterlockedDecrement(&dword_18002CFF8);
  CMSMQRuleSet::~CMSMQRuleSet(this);
}

```

## disassembly

```asm
0x18000da64  push    rbx
0x18000da66  sub     rsp, 20h
0x18000da6a  mov     rbx, rcx
0x18000da6d  lea     rax, ??_7?$CComObject@VCMSMQRuleSet@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMSMQRuleSet>::`vftable'{for `ISupportErrorInfo'}
0x18000da74  mov     [rcx], rax
0x18000da77  lea     rax, ??_7?$CComObject@VCMSMQRuleSet@@@ATL@@6B?$IDispatchImpl@UIMSMQRuleSet@@$1?IID_IMSMQRuleSet@@3U_GUID@@B$1?LIBID_MSMQTriggerObjects@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMSMQRuleSet>::`vftable'{for `ATL::IDispatchImpl<IMSMQRuleSet,&_GUID const IID_IMSMQRuleSet,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>'}
0x18000da7e  mov     [rcx+8], rax
0x18000da82  mov     dword ptr [rcx+10h], 1
0x18000da89  add     rcx, 4A0h
0x18000da90  call    ?Release@?$CComPtr@UIUnknown@@@ATL@@QEAAXXZ; ATL::CComPtr<IUnknown>::Release(void)
0x18000da95  lock dec cs:dword_18002CFF8
0x18000da9c  mov     rcx, rbx; this
0x18000da9f  add     rsp, 20h
0x18000daa3  pop     rbx
0x18000daa4  jmp     ??1CMSMQRuleSet@@QEAA@XZ; CMSMQRuleSet::~CMSMQRuleSet(void)
```
