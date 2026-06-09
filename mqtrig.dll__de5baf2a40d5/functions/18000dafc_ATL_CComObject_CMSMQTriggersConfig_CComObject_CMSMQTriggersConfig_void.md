# ATL::CComObject<CMSMQTriggersConfig>::~CComObject<CMSMQTriggersConfig>(void)

- ea: `0x18000dafc`
- end: `0x18000db3e`
- name: `??1?$CComObject@VCMSMQTriggersConfig@@@ATL@@QEAA@XZ`
- size: `66`
- prototype: `void __fastcall(CMSMQTriggersConfig *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000dcbc`

## callees

- `0x18000db7c`
- `0x18000fab4`

## pseudocode

```c
void __fastcall ATL::CComObject<CMSMQTriggersConfig>::~CComObject<CMSMQTriggersConfig>(CMSMQTriggersConfig *this)
{
  *(_QWORD *)this = &ATL::CComObject<CMSMQTriggersConfig>::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CMSMQTriggersConfig>::`vftable'{for `ATL::IDispatchImpl<IMSMQTriggersConfig,&_GUID const IID_IMSMQTriggersConfig,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>'};
  *((_DWORD *)this + 4) = 1;
  ATL::CComPtr<IUnknown>::Release((char *)this + 72);
  _InterlockedDecrement(&dword_18002CFF8);
  CMSMQTriggersConfig::~CMSMQTriggersConfig(this);
}

```

## disassembly

```asm
0x18000dafc  push    rbx
0x18000dafe  sub     rsp, 20h
0x18000db02  mov     rbx, rcx
0x18000db05  lea     rax, ??_7?$CComObject@VCMSMQTriggersConfig@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMSMQTriggersConfig>::`vftable'{for `ISupportErrorInfo'}
0x18000db0c  mov     [rcx], rax
0x18000db0f  lea     rax, ??_7?$CComObject@VCMSMQTriggersConfig@@@ATL@@6B?$IDispatchImpl@UIMSMQTriggersConfig@@$1?IID_IMSMQTriggersConfig@@3U_GUID@@B$1?LIBID_MSMQTriggerObjects@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMSMQTriggersConfig>::`vftable'{for `ATL::IDispatchImpl<IMSMQTriggersConfig,&_GUID const IID_IMSMQTriggersConfig,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>'}
0x18000db16  mov     [rcx+8], rax
0x18000db1a  mov     dword ptr [rcx+10h], 1
0x18000db21  add     rcx, 48h ; 'H'
0x18000db25  call    ?Release@?$CComPtr@UIUnknown@@@ATL@@QEAAXXZ; ATL::CComPtr<IUnknown>::Release(void)
0x18000db2a  lock dec cs:dword_18002CFF8
0x18000db31  mov     rcx, rbx; this
0x18000db34  add     rsp, 20h
0x18000db38  pop     rbx
0x18000db39  jmp     ??1CMSMQTriggersConfig@@QEAA@XZ; CMSMQTriggersConfig::~CMSMQTriggersConfig(void)
```
