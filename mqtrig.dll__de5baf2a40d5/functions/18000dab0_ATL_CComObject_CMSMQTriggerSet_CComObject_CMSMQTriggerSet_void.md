# ATL::CComObject<CMSMQTriggerSet>::~CComObject<CMSMQTriggerSet>(void)

- ea: `0x18000dab0`
- end: `0x18000daf5`
- name: `??1?$CComObject@VCMSMQTriggerSet@@@ATL@@QEAA@XZ`
- size: `69`
- prototype: `void __fastcall(CMSMQTriggerSet *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000dc94`

## callees

- `0x18000fab4`
- `0x1800104f8`

## pseudocode

```c
void __fastcall ATL::CComObject<CMSMQTriggerSet>::~CComObject<CMSMQTriggerSet>(CMSMQTriggerSet *this)
{
  *(_QWORD *)this = &ATL::CComObject<CMSMQTriggerSet>::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CMSMQTriggerSet>::`vftable'{for `ATL::IDispatchImpl<IMSMQTriggerSet,&_GUID const IID_IMSMQTriggerSet,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>'};
  *((_DWORD *)this + 4) = 1;
  ATL::CComPtr<IUnknown>::Release((char *)this + 1184);
  _InterlockedDecrement(&dword_18002CFF8);
  CMSMQTriggerSet::~CMSMQTriggerSet(this);
}

```

## disassembly

```asm
0x18000dab0  push    rbx
0x18000dab2  sub     rsp, 20h
0x18000dab6  mov     rbx, rcx
0x18000dab9  lea     rax, ??_7?$CComObject@VCMSMQTriggerSet@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMSMQTriggerSet>::`vftable'{for `ISupportErrorInfo'}
0x18000dac0  mov     [rcx], rax
0x18000dac3  lea     rax, ??_7?$CComObject@VCMSMQTriggerSet@@@ATL@@6B?$IDispatchImpl@UIMSMQTriggerSet@@$1?IID_IMSMQTriggerSet@@3U_GUID@@B$1?LIBID_MSMQTriggerObjects@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMSMQTriggerSet>::`vftable'{for `ATL::IDispatchImpl<IMSMQTriggerSet,&_GUID const IID_IMSMQTriggerSet,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>'}
0x18000daca  mov     [rcx+8], rax
0x18000dace  mov     dword ptr [rcx+10h], 1
0x18000dad5  add     rcx, 4A0h
0x18000dadc  call    ?Release@?$CComPtr@UIUnknown@@@ATL@@QEAAXXZ; ATL::CComPtr<IUnknown>::Release(void)
0x18000dae1  lock dec cs:dword_18002CFF8
0x18000dae8  mov     rcx, rbx; this
0x18000daeb  add     rsp, 20h
0x18000daef  pop     rbx
0x18000daf0  jmp     ??1CMSMQTriggerSet@@QEAA@XZ; CMSMQTriggerSet::~CMSMQTriggerSet(void)
```
