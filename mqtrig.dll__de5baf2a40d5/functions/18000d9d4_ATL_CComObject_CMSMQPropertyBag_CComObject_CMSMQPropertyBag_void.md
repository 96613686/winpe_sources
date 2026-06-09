# ATL::CComObject<CMSMQPropertyBag>::~CComObject<CMSMQPropertyBag>(void)

- ea: `0x18000d9d4`
- end: `0x18000da16`
- name: `??1?$CComObject@VCMSMQPropertyBag@@@ATL@@QEAA@XZ`
- size: `66`
- prototype: `void __fastcall(CMSMQPropertyBag *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000dc1c`

## callees

- `0x180003198`
- `0x18000fab4`

## pseudocode

```c
void __fastcall ATL::CComObject<CMSMQPropertyBag>::~CComObject<CMSMQPropertyBag>(CMSMQPropertyBag *this)
{
  *(_QWORD *)this = &ATL::CComObject<CMSMQPropertyBag>::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CMSMQPropertyBag>::`vftable'{for `ATL::IDispatchImpl<IMSMQPropertyBag,&_GUID const IID_IMSMQPropertyBag,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>'};
  *((_DWORD *)this + 4) = 1;
  ATL::CComPtr<IUnknown>::Release((char *)this + 24);
  _InterlockedDecrement(&dword_18002CFF8);
  CMSMQPropertyBag::~CMSMQPropertyBag(this);
}

```

## disassembly

```asm
0x18000d9d4  push    rbx
0x18000d9d6  sub     rsp, 20h
0x18000d9da  mov     rbx, rcx
0x18000d9dd  lea     rax, ??_7?$CComObject@VCMSMQPropertyBag@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMSMQPropertyBag>::`vftable'{for `ISupportErrorInfo'}
0x18000d9e4  mov     [rcx], rax
0x18000d9e7  lea     rax, ??_7?$CComObject@VCMSMQPropertyBag@@@ATL@@6B?$IDispatchImpl@UIMSMQPropertyBag@@$1?IID_IMSMQPropertyBag@@3U_GUID@@B$1?LIBID_MSMQTriggerObjects@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMSMQPropertyBag>::`vftable'{for `ATL::IDispatchImpl<IMSMQPropertyBag,&_GUID const IID_IMSMQPropertyBag,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>'}
0x18000d9ee  mov     [rcx+8], rax
0x18000d9f2  mov     dword ptr [rcx+10h], 1
0x18000d9f9  add     rcx, 18h
0x18000d9fd  call    ?Release@?$CComPtr@UIUnknown@@@ATL@@QEAAXXZ; ATL::CComPtr<IUnknown>::Release(void)
0x18000da02  lock dec cs:dword_18002CFF8
0x18000da09  mov     rcx, rbx; this
0x18000da0c  add     rsp, 20h
0x18000da10  pop     rbx
0x18000da11  jmp     ??1CMSMQPropertyBag@@QEAA@XZ; CMSMQPropertyBag::~CMSMQPropertyBag(void)
```
