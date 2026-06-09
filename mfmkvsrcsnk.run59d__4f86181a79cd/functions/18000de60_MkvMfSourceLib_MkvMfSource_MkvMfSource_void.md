# MkvMfSourceLib::MkvMfSource::~MkvMfSource(void)

- ea: `0x18000de60`
- end: `0x18000e0b0`
- name: `??1MkvMfSource@MkvMfSourceLib@@UEAA@XZ`
- size: `592`
- prototype: `void __fastcall(MkvMfSourceLib::MkvMfSource *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e2a0`

## callees

- `0x180002400`
- `0x180005c68`
- `0x180008344`
- `0x180009b04`
- `0x18000c70c`
- `0x18000cdac`
- `0x18000d554`
- `0x18000d9b8`
- `0x18000dbb8`
- `0x18000dcec`
- `0x18000ddc0`
- `0x18000de60`
- `0x1800151c8`
- `0x1800151f0`
- `0x180044014`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e075`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e075`
- `MFPlat!MFUnlockWorkQueue` at `0x18000df67`
- `MFPlat!MFUnlockWorkQueue` at `0x18000df67`

## pseudocode

```c
void __fastcall MkvMfSourceLib::MkvMfSource::~MkvMfSource(MkvMfSourceLib::MkvMfSource *this)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v3; // ebx
  DWORD v4; // ecx
  __int64 v5; // rcx
  __int64 v6; // rcx
  _BYTE v7[8]; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v8[16]; // [rsp+28h] [rbp-20h] BYREF

  *(_QWORD *)this = &MkvMfSourceLib::MkvMfSource::`vftable';
  *((_QWORD *)this + 1) = &MkvMfSourceLib::MkvMfSource::`vftable'{for `IMFMediaSourceEx'};
  *((_QWORD *)this + 2) = &MkvMfSourceLib::MkvMfSource::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMFRateSupport,IMFRateControl,IMFGetService,IMFMediaEventGenerator,IMFRealTimeClientEx,IMFTelemetryComponent,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 3) = &MkvMfSourceLib::MkvMfSource::`vftable'{for `IMFRateControl'};
  *((_QWORD *)this + 4) = &MkvMfSourceLib::MkvMfSource::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMFGetService,IMFMediaEventGenerator,IMFRealTimeClientEx,IMFTelemetryComponent,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 5) = &MkvMfSourceLib::MkvMfSource::`vftable'{for `IMFMediaEventGenerator'};
  *((_QWORD *)this + 6) = &MkvMfSourceLib::MkvMfSource::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMFRealTimeClientEx,IMFTelemetryComponent,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 7) = &MkvMfSourceLib::MkvMfSource::`vftable'{for `IMFTelemetryComponent'};
  *((_QWORD *)this + 8) = &MkvMfSourceLib::MkvMfSource::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v7, "MkvMfSourceLib::MkvMfSource::~MkvMfSource", 141);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 86) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 86) + 296LL))(*((_QWORD *)this + 86));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 86) + 280LL))(
                                                            *((_QWORD *)this + 86),
                                                            v8);
    *((_DWORD *)ThreadRelativeContext + 504) = v3;
  }
  v4 = *((_DWORD *)this + 112);
  if ( v4 )
    MFUnlockWorkQueue(v4);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v7);
  CMFAttributesImpl<IMFAttributes,CMFCSLock>::~CMFAttributesImpl<IMFAttributes,CMFCSLock>((char *)this + 720);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 704);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 696);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 688);
  Microsoft::WRL::ComPtr<MkvSourceTelemetryLogger>::InternalRelease((char *)this + 680);
  std::_List_node<MkvMfSourceLib::MkvMfSource::Command,void *>::_Free_non_head<std::allocator<std::_List_node<MkvMfSourceLib::MkvMfSource::Command,void *>>>(
    v5,
    *((_QWORD *)this + 83));
  std::_Deallocate<16>(*((_QWORD *)this + 83), 72);
  std::_Tree<std::_Tmap_traits<unsigned long,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>,0>>((char *)this + 576);
  Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvTimedText>::InternalRelease((char *)this + 440);
  std::unique_ptr<mkvparser::Segment>::~unique_ptr<mkvparser::Segment>((char *)this + 416);
  MkvReader::~MkvReader((MkvMfSourceLib::MkvMfSource *)((char *)this + 184));
  v6 = *((_QWORD *)this + 20);
  if ( v6 )
  {
    std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<IMFStreamDescriptor>>>(v6, *((_QWORD *)this + 21));
    std::_Deallocate<16>(
      *((_QWORD *)this + 20),
      (*((_QWORD *)this + 22) - *((_QWORD *)this + 20)) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 20) = 0;
    *((_QWORD *)this + 21) = 0;
    *((_QWORD *)this + 22) = 0;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 152);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 144);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  *((_DWORD *)this + 25) = -1073741823;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 88);
}

```

## disassembly

```asm
0x18000de60  mov     [rsp+arg_8], rbx
0x18000de65  mov     [rsp+arg_10], rsi
0x18000de6a  push    rdi
0x18000de6b  sub     rsp, 40h
0x18000de6f  mov     rax, cs:__security_cookie
0x18000de76  xor     rax, rsp
0x18000de79  mov     [rsp+48h+var_10], rax
0x18000de7e  mov     rsi, rcx
0x18000de81  lea     rax, ??_7MkvMfSource@MkvMfSourceLib@@6B@; const MkvMfSourceLib::MkvMfSource::`vftable'
0x18000de88  mov     [rcx], rax
0x18000de8b  lea     rax, ??_7MkvMfSource@MkvMfSourceLib@@6BIMFMediaSourceEx@@@; const MkvMfSourceLib::MkvMfSource::`vftable'{for `IMFMediaSourceEx'}
0x18000de92  mov     [rcx+8], rax
0x18000de96  lea     rax, ??_7MkvMfSource@MkvMfSourceLib@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMFRateSupport@@UIMFRateControl@@UIMFGetService@@UIMFMediaEventGenerator@@UIMFRealTimeClientEx@@UIMFTelemetryComponent@@VFtmBase@23@@Details@WRL@Microsoft@@@; const MkvMfSourceLib::MkvMfSource::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMFRateSupport,IMFRateControl,IMFGetService,IMFMediaEventGenerator,IMFRealTimeClientEx,IMFTelemetryComponent,Microsoft::WRL::FtmBase>'}
0x18000de9d  mov     [rcx+10h], rax
0x18000dea1  lea     rax, ??_7MkvMfSource@MkvMfSourceLib@@6BIMFRateControl@@@; const MkvMfSourceLib::MkvMfSource::`vftable'{for `IMFRateControl'}
0x18000dea8  mov     [rcx+18h], rax
0x18000deac  lea     rax, ??_7MkvMfSource@MkvMfSourceLib@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMFGetService@@UIMFMediaEventGenerator@@UIMFRealTimeClientEx@@UIMFTelemetryComponent@@VFtmBase@23@@Details@WRL@Microsoft@@@; const MkvMfSourceLib::MkvMfSource::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMFGetService,IMFMediaEventGenerator,IMFRealTimeClientEx,IMFTelemetryComponent,Microsoft::WRL::FtmBase>'}
0x18000deb3  mov     [rcx+20h], rax
0x18000deb7  lea     rax, ??_7MkvMfSource@MkvMfSourceLib@@6BIMFMediaEventGenerator@@@; const MkvMfSourceLib::MkvMfSource::`vftable'{for `IMFMediaEventGenerator'}
0x18000debe  mov     [rcx+28h], rax
0x18000dec2  lea     rax, ??_7MkvMfSource@MkvMfSourceLib@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMFRealTimeClientEx@@UIMFTelemetryComponent@@VFtmBase@23@@Details@WRL@Microsoft@@@; const MkvMfSourceLib::MkvMfSource::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMFRealTimeClientEx,IMFTelemetryComponent,Microsoft::WRL::FtmBase>'}
0x18000dec9  mov     [rcx+30h], rax
0x18000decd  lea     rax, ??_7MkvMfSource@MkvMfSourceLib@@6BIMFTelemetryComponent@@@; const MkvMfSourceLib::MkvMfSource::`vftable'{for `IMFTelemetryComponent'}
0x18000ded4  mov     [rcx+38h], rax
0x18000ded8  lea     rax, ??_7MkvMfSource@MkvMfSourceLib@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const MkvMfSourceLib::MkvMfSource::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000dedf  mov     [rcx+40h], rax
0x18000dee3  mov     r8d, 8Dh; int
0x18000dee9  lea     rdx, aMkvmfsourcelib_114; "MkvMfSourceLib::MkvMfSource::~MkvMfSour"...
0x18000def0  lea     rcx, [rsp+48h+var_28]; this
0x18000def5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18000defa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18000df01  cmp     byte ptr [rcx+8], 0
0x18000df05  jz      short loc_18000DF5D
0x18000df07  cmp     qword ptr [rsi+2B0h], 0
0x18000df0f  jz      short loc_18000DF5D
0x18000df11  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000df16  mov     rdi, rax
0x18000df19  mov     rcx, [rsi+2B0h]
0x18000df20  mov     rdx, [rcx]
0x18000df23  mov     rax, [rdx+128h]
0x18000df2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df2f  mov     ebx, eax
0x18000df31  mov     rcx, [rsi+2B0h]
0x18000df38  mov     rdx, [rcx]
0x18000df3b  mov     rax, [rdx+118h]
0x18000df42  lea     rdx, [rsp+48h+var_20]
0x18000df47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df4c  movups  xmm0, xmmword ptr [rax]
0x18000df4f  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18000df57  mov     [rdi+7E0h], ebx
0x18000df5d  mov     ecx, [rsi+1C0h]; dwWorkQueue
0x18000df63  test    ecx, ecx
0x18000df65  jz      short loc_18000DF73
0x18000df67  call    cs:__imp_MFUnlockWorkQueue
0x18000df6e  nop     dword ptr [rax+rax+00h]
0x18000df73  lea     rcx, [rsp+48h+var_28]; this
0x18000df78  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18000df7d  lea     rcx, [rsi+2D0h]
0x18000df84  call    ??1?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@UEAA@XZ; CMFAttributesImpl<IMFAttributes,CMFCSLock>::~CMFAttributesImpl<IMFAttributes,CMFCSLock>(void)
0x18000df89  lea     rcx, [rsi+2C0h]
0x18000df90  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000df95  lea     rcx, [rsi+2B8h]
0x18000df9c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000dfa1  lea     rcx, [rsi+2B0h]
0x18000dfa8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000dfad  lea     rcx, [rsi+2A8h]
0x18000dfb4  call    ?InternalRelease@?$ComPtr@VMkvSourceTelemetryLogger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<MkvSourceTelemetryLogger>::InternalRelease(void)
0x18000dfb9  mov     rdx, [rsi+298h]
0x18000dfc0  call    ??$_Free_non_head@V?$allocator@U?$_List_node@VCommand@MkvMfSource@MkvMfSourceLib@@PEAX@std@@@std@@@?$_List_node@VCommand@MkvMfSource@MkvMfSourceLib@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@VCommand@MkvMfSource@MkvMfSourceLib@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<MkvMfSourceLib::MkvMfSource::Command,void *>::_Free_non_head<std::allocator<std::_List_node<MkvMfSourceLib::MkvMfSource::Command,void *>>>(std::allocator<std::_List_node<MkvMfSourceLib::MkvMfSource::Command,void *>> &,std::_List_node<MkvMfSourceLib::MkvMfSource::Command,void *> *)
0x18000dfc5  mov     edx, 48h ; 'H'
0x18000dfca  mov     rcx, [rsi+298h]
0x18000dfd1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000dfd6  lea     rcx, [rsi+240h]
0x18000dfdd  call    ??1?$_Tree@V?$_Tmap_traits@KV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>,std::less<ulong>,std::allocator<std::pair<ulong const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>,0>>::~_Tree<std::_Tmap_traits<ulong,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>,std::less<ulong>,std::allocator<std::pair<ulong const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>,0>>(void)
0x18000dfe2  lea     rcx, [rsi+1B8h]
0x18000dfe9  call    ?InternalRelease@?$ComPtr@VMkvTimedText@MkvMfSourceLib@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvTimedText>::InternalRelease(void)
0x18000dfee  lea     rcx, [rsi+1A0h]
0x18000dff5  call    ??1?$unique_ptr@VSegment@mkvparser@@U?$default_delete@VSegment@mkvparser@@@std@@@std@@QEAA@XZ; std::unique_ptr<mkvparser::Segment>::~unique_ptr<mkvparser::Segment>(void)
0x18000dffa  lea     rcx, [rsi+0B8h]; this
0x18000e001  call    ??1MkvReader@@UEAA@XZ; MkvReader::~MkvReader(void)
0x18000e006  mov     rcx, [rsi+0A0h]
0x18000e00d  test    rcx, rcx
0x18000e010  jz      short loc_18000E059
0x18000e012  mov     rdx, [rsi+0A8h]
0x18000e019  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@UIMFStreamDescriptor@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@UIMFStreamDescriptor@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@UIMFStreamDescriptor@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<IMFStreamDescriptor>>>(Microsoft::WRL::ComPtr<IMFStreamDescriptor> *,Microsoft::WRL::ComPtr<IMFStreamDescriptor> * const,std::allocator<Microsoft::WRL::ComPtr<IMFStreamDescriptor>> &)
0x18000e01e  mov     rcx, [rsi+0A0h]
0x18000e025  mov     rdx, [rsi+0B0h]
0x18000e02c  sub     rdx, rcx
0x18000e02f  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000e033  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000e038  mov     qword ptr [rsi+0A0h], 0
0x18000e043  mov     qword ptr [rsi+0A8h], 0
0x18000e04e  mov     qword ptr [rsi+0B0h], 0
0x18000e059  lea     rcx, [rsi+98h]
0x18000e060  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000e065  lea     rcx, [rsi+90h]
0x18000e06c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000e071  lea     rcx, [rsi+68h]; lpCriticalSection
0x18000e075  call    cs:__imp_DeleteCriticalSection
0x18000e07c  nop     dword ptr [rax+rax+00h]
0x18000e081  mov     dword ptr [rsi+64h], 0C0000001h
0x18000e088  lea     rcx, [rsi+58h]
0x18000e08c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000e091  nop
0x18000e092  mov     rcx, [rsp+48h+var_10]
0x18000e097  xor     rcx, rsp; StackCookie
0x18000e09a  call    __security_check_cookie
0x18000e09f  mov     rbx, [rsp+48h+arg_8]
0x18000e0a4  mov     rsi, [rsp+48h+arg_10]
0x18000e0a9  add     rsp, 40h
0x18000e0ad  pop     rdi
0x18000e0ae  retn
```
