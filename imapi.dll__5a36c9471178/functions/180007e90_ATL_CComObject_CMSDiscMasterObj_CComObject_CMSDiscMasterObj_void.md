# ATL::CComObject<CMSDiscMasterObj>::~CComObject<CMSDiscMasterObj>(void)

- ea: `0x180007e90`
- end: `0x180007f09`
- name: `??1?$CComObject@VCMSDiscMasterObj@@@ATL@@UEAA@XZ`
- size: `121`
- prototype: `__int64 __fastcall(CMSDiscMasterObj *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007ff0`

## callees

- `0x18000b394`
- `0x18000c080`
- `0x180019010`

## pseudocode

```c
void __fastcall ATL::CComObject<CMSDiscMasterObj>::~CComObject<CMSDiscMasterObj>(CMSDiscMasterObj *this)
{
  *((_DWORD *)this + 32) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CMSDiscMasterObj>::`vftable'{for `IDiscMaster'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CMSDiscMasterObj>::`vftable'{for `IJolietDiscMaster'};
  *((_QWORD *)this + 2) = &ATL::CComObject<CMSDiscMasterObj>::`vftable'{for `IRedbookDiscMaster'};
  *((_QWORD *)this + 3) = &ATL::CComObject<CMSDiscMasterObj>::`vftable'{for `ATL::IDispEventSimpleImpl<1,CMSDiscMasterObj,&_GUID const IID_DDiscFormat2DataEvents>'};
  *((_QWORD *)this + 9) = &ATL::CComObject<CMSDiscMasterObj>::`vftable'{for `ATL::IDispEventSimpleImpl<2,CMSDiscMasterObj,&_GUID const IID_DDiscMaster2Events>'};
  *((_QWORD *)this + 15) = &ATL::CComObject<CMSDiscMasterObj>::`vftable'{for `ISupportErrorInfo'};
  CMSDiscMasterObj::FinalRelease(this);
  (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CMSDiscMasterObj::~CMSDiscMasterObj(this);
}

```

## disassembly

```asm
0x180007e90  push    rbx
0x180007e92  sub     rsp, 20h
0x180007e96  lea     rax, ??_7?$CComObject@VCMSDiscMasterObj@@@ATL@@6BIDiscMaster@@@; const ATL::CComObject<CMSDiscMasterObj>::`vftable'{for `IDiscMaster'}
0x180007e9d  mov     dword ptr [rcx+80h], 0C0000001h
0x180007ea7  mov     [rcx], rax
0x180007eaa  mov     rbx, rcx
0x180007ead  lea     rax, ??_7?$CComObject@VCMSDiscMasterObj@@@ATL@@6BIJolietDiscMaster@@@; const ATL::CComObject<CMSDiscMasterObj>::`vftable'{for `IJolietDiscMaster'}
0x180007eb4  mov     [rcx+8], rax
0x180007eb8  lea     rax, ??_7?$CComObject@VCMSDiscMasterObj@@@ATL@@6BIRedbookDiscMaster@@@; const ATL::CComObject<CMSDiscMasterObj>::`vftable'{for `IRedbookDiscMaster'}
0x180007ebf  mov     [rcx+10h], rax
0x180007ec3  lea     rax, ??_7?$CComObject@VCMSDiscMasterObj@@@ATL@@6B?$IDispEventSimpleImpl@$00VCMSDiscMasterObj@@$1?IID_DDiscFormat2DataEvents@@3U_GUID@@B@1@@; const ATL::CComObject<CMSDiscMasterObj>::`vftable'{for `ATL::IDispEventSimpleImpl<1,CMSDiscMasterObj,&_GUID const IID_DDiscFormat2DataEvents>'}
0x180007eca  mov     [rcx+18h], rax
0x180007ece  lea     rax, ??_7?$CComObject@VCMSDiscMasterObj@@@ATL@@6B?$IDispEventSimpleImpl@$01VCMSDiscMasterObj@@$1?IID_DDiscMaster2Events@@3U_GUID@@B@1@@; const ATL::CComObject<CMSDiscMasterObj>::`vftable'{for `ATL::IDispEventSimpleImpl<2,CMSDiscMasterObj,&_GUID const IID_DDiscMaster2Events>'}
0x180007ed5  mov     [rcx+48h], rax
0x180007ed9  lea     rax, ??_7?$CComObject@VCMSDiscMasterObj@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMSDiscMasterObj>::`vftable'{for `ISupportErrorInfo'}
0x180007ee0  mov     [rcx+78h], rax
0x180007ee4  call    ?FinalRelease@CMSDiscMasterObj@@QEAAXXZ; CMSDiscMasterObj::FinalRelease(void)
0x180007ee9  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007ef0  mov     rax, [rcx]
0x180007ef3  mov     rax, [rax+10h]
0x180007ef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007efc  mov     rcx, rbx; this
0x180007eff  add     rsp, 20h
0x180007f03  pop     rbx
0x180007f04  jmp     ??1CMSDiscMasterObj@@QEAA@XZ; CMSDiscMasterObj::~CMSDiscMasterObj(void)
```
