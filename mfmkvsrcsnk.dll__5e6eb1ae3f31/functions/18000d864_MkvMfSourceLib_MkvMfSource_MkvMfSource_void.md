# MkvMfSourceLib::MkvMfSource::~MkvMfSource(void)

- ea: `0x18000d864`
- end: `0x18000daa7`
- name: `??1MkvMfSource@MkvMfSourceLib@@UEAA@XZ`
- size: `579`
- prototype: `void __fastcall(MkvMfSourceLib::MkvMfSource *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000dca0`

## callees

- `0x1800023e0`
- `0x180005ab8`
- `0x1800080b8`
- `0x1800097f0`
- `0x18000c22c`
- `0x18000c81c`
- `0x18000cfb4`
- `0x18000d3e8`
- `0x18000d5d4`
- `0x18000d704`
- `0x18000d7cc`
- `0x18000d864`
- `0x180014814`
- `0x180014838`
- `0x18004227c`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000da73`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000da73`
- `MFPlat!MFUnlockWorkQueue` at `0x18000d96b`
- `MFPlat!MFUnlockWorkQueue` at `0x18000d96b`

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
0x18000d864  mov     [rsp+arg_8], rbx
0x18000d869  mov     [rsp+arg_10], rsi
0x18000d86e  push    rdi
0x18000d86f  sub     rsp, 40h
0x18000d873  mov     rax, cs:__security_cookie
0x18000d87a  xor     rax, rsp
0x18000d87d  mov     [rsp+48h+var_10], rax
0x18000d882  mov     rsi, rcx
0x18000d885  lea     rax, ??_7MkvMfSource@MkvMfSourceLib@@6B@; const MkvMfSourceLib::MkvMfSource::`vftable'
0x18000d88c  mov     [rcx], rax
0x18000d88f  lea     rax, ??_7MkvMfSource@MkvMfSourceLib@@6BIMFMediaSourceEx@@@; const MkvMfSourceLib::MkvMfSource::`vftable'{for `IMFMediaSourceEx'}
0x18000d896  mov     [rcx+8], rax
0x18000d89a  lea     rax, ??_7MkvMfSource@MkvMfSourceLib@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMFRateSupport@@UIMFRateControl@@UIMFGetService@@UIMFMediaEventGenerator@@UIMFRealTimeClientEx@@UIMFTelemetryComponent@@VFtmBase@23@@Details@WRL@Microsoft@@@; const MkvMfSourceLib::MkvMfSource::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMFRateSupport,IMFRateControl,IMFGetService,IMFMediaEventGenerator,IMFRealTimeClientEx,IMFTelemetryComponent,Microsoft::WRL::FtmBase>'}
0x18000d8a1  mov     [rcx+10h], rax
0x18000d8a5  lea     rax, ??_7MkvMfSource@MkvMfSourceLib@@6BIMFRateControl@@@; const MkvMfSourceLib::MkvMfSource::`vftable'{for `IMFRateControl'}
0x18000d8ac  mov     [rcx+18h], rax
0x18000d8b0  lea     rax, ??_7MkvMfSource@MkvMfSourceLib@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMFGetService@@UIMFMediaEventGenerator@@UIMFRealTimeClientEx@@UIMFTelemetryComponent@@VFtmBase@23@@Details@WRL@Microsoft@@@; const MkvMfSourceLib::MkvMfSource::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMFGetService,IMFMediaEventGenerator,IMFRealTimeClientEx,IMFTelemetryComponent,Microsoft::WRL::FtmBase>'}
0x18000d8b7  mov     [rcx+20h], rax
0x18000d8bb  lea     rax, ??_7MkvMfSource@MkvMfSourceLib@@6BIMFMediaEventGenerator@@@; const MkvMfSourceLib::MkvMfSource::`vftable'{for `IMFMediaEventGenerator'}
0x18000d8c2  mov     [rcx+28h], rax
0x18000d8c6  lea     rax, ??_7MkvMfSource@MkvMfSourceLib@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMFRealTimeClientEx@@UIMFTelemetryComponent@@VFtmBase@23@@Details@WRL@Microsoft@@@; const MkvMfSourceLib::MkvMfSource::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMFRealTimeClientEx,IMFTelemetryComponent,Microsoft::WRL::FtmBase>'}
0x18000d8cd  mov     [rcx+30h], rax
0x18000d8d1  lea     rax, ??_7MkvMfSource@MkvMfSourceLib@@6BIMFTelemetryComponent@@@; const MkvMfSourceLib::MkvMfSource::`vftable'{for `IMFTelemetryComponent'}
0x18000d8d8  mov     [rcx+38h], rax
0x18000d8dc  lea     rax, ??_7MkvMfSource@MkvMfSourceLib@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const MkvMfSourceLib::MkvMfSource::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000d8e3  mov     [rcx+40h], rax
0x18000d8e7  mov     r8d, 8Dh; int
0x18000d8ed  lea     rdx, aMkvmfsourcelib_114; "MkvMfSourceLib::MkvMfSource::~MkvMfSour"...
0x18000d8f4  lea     rcx, [rsp+48h+var_28]; this
0x18000d8f9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18000d8fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18000d905  cmp     byte ptr [rcx+8], 0
0x18000d909  jz      short loc_18000D961
0x18000d90b  cmp     qword ptr [rsi+2B0h], 0
0x18000d913  jz      short loc_18000D961
0x18000d915  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000d91a  mov     rdi, rax
0x18000d91d  mov     rcx, [rsi+2B0h]
0x18000d924  mov     rdx, [rcx]
0x18000d927  mov     rax, [rdx+128h]
0x18000d92e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d933  mov     ebx, eax
0x18000d935  mov     rcx, [rsi+2B0h]
0x18000d93c  mov     rdx, [rcx]
0x18000d93f  mov     rax, [rdx+118h]
0x18000d946  lea     rdx, [rsp+48h+var_20]
0x18000d94b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d950  movups  xmm0, xmmword ptr [rax]
0x18000d953  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18000d95b  mov     [rdi+7E0h], ebx
0x18000d961  mov     ecx, [rsi+1C0h]; dwWorkQueue
0x18000d967  test    ecx, ecx
0x18000d969  jz      short loc_18000D971
0x18000d96b  call    cs:__imp_MFUnlockWorkQueue
0x18000d971  lea     rcx, [rsp+48h+var_28]; this
0x18000d976  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18000d97b  lea     rcx, [rsi+2D0h]
0x18000d982  call    ??1?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@UEAA@XZ; CMFAttributesImpl<IMFAttributes,CMFCSLock>::~CMFAttributesImpl<IMFAttributes,CMFCSLock>(void)
0x18000d987  lea     rcx, [rsi+2C0h]
0x18000d98e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000d993  lea     rcx, [rsi+2B8h]
0x18000d99a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000d99f  lea     rcx, [rsi+2B0h]
0x18000d9a6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000d9ab  lea     rcx, [rsi+2A8h]
0x18000d9b2  call    ?InternalRelease@?$ComPtr@VMkvSourceTelemetryLogger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<MkvSourceTelemetryLogger>::InternalRelease(void)
0x18000d9b7  mov     rdx, [rsi+298h]
0x18000d9be  call    ??$_Free_non_head@V?$allocator@U?$_List_node@VCommand@MkvMfSource@MkvMfSourceLib@@PEAX@std@@@std@@@?$_List_node@VCommand@MkvMfSource@MkvMfSourceLib@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@VCommand@MkvMfSource@MkvMfSourceLib@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<MkvMfSourceLib::MkvMfSource::Command,void *>::_Free_non_head<std::allocator<std::_List_node<MkvMfSourceLib::MkvMfSource::Command,void *>>>(std::allocator<std::_List_node<MkvMfSourceLib::MkvMfSource::Command,void *>> &,std::_List_node<MkvMfSourceLib::MkvMfSource::Command,void *> *)
0x18000d9c3  mov     edx, 48h ; 'H'
0x18000d9c8  mov     rcx, [rsi+298h]
0x18000d9cf  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000d9d4  lea     rcx, [rsi+240h]
0x18000d9db  call    ??1?$_Tree@V?$_Tmap_traits@KV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>,std::less<ulong>,std::allocator<std::pair<ulong const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>,0>>::~_Tree<std::_Tmap_traits<ulong,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>,std::less<ulong>,std::allocator<std::pair<ulong const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>,0>>(void)
0x18000d9e0  lea     rcx, [rsi+1B8h]
0x18000d9e7  call    ?InternalRelease@?$ComPtr@VMkvTimedText@MkvMfSourceLib@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvTimedText>::InternalRelease(void)
0x18000d9ec  lea     rcx, [rsi+1A0h]
0x18000d9f3  call    ??1?$unique_ptr@VSegment@mkvparser@@U?$default_delete@VSegment@mkvparser@@@std@@@std@@QEAA@XZ; std::unique_ptr<mkvparser::Segment>::~unique_ptr<mkvparser::Segment>(void)
0x18000d9f8  lea     rcx, [rsi+0B8h]; this
0x18000d9ff  call    ??1MkvReader@@UEAA@XZ; MkvReader::~MkvReader(void)
0x18000da04  mov     rcx, [rsi+0A0h]
0x18000da0b  test    rcx, rcx
0x18000da0e  jz      short loc_18000DA57
0x18000da10  mov     rdx, [rsi+0A8h]
0x18000da17  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@UIMFStreamDescriptor@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@UIMFStreamDescriptor@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@UIMFStreamDescriptor@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<IMFStreamDescriptor>>>(Microsoft::WRL::ComPtr<IMFStreamDescriptor> *,Microsoft::WRL::ComPtr<IMFStreamDescriptor> * const,std::allocator<Microsoft::WRL::ComPtr<IMFStreamDescriptor>> &)
0x18000da1c  mov     rcx, [rsi+0A0h]
0x18000da23  mov     rdx, [rsi+0B0h]
0x18000da2a  sub     rdx, rcx
0x18000da2d  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000da31  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000da36  mov     qword ptr [rsi+0A0h], 0
0x18000da41  mov     qword ptr [rsi+0A8h], 0
0x18000da4c  mov     qword ptr [rsi+0B0h], 0
0x18000da57  lea     rcx, [rsi+98h]
0x18000da5e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000da63  lea     rcx, [rsi+90h]
0x18000da6a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000da6f  lea     rcx, [rsi+68h]; lpCriticalSection
0x18000da73  call    cs:__imp_DeleteCriticalSection
0x18000da79  mov     dword ptr [rsi+64h], 0C0000001h
0x18000da80  lea     rcx, [rsi+58h]
0x18000da84  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000da89  nop
0x18000da8a  mov     rcx, [rsp+48h+var_10]
0x18000da8f  xor     rcx, rsp; StackCookie
0x18000da92  call    __security_check_cookie
0x18000da97  mov     rbx, [rsp+48h+arg_8]
0x18000da9c  mov     rsi, [rsp+48h+arg_10]
0x18000daa1  add     rsp, 40h
0x18000daa5  pop     rdi
0x18000daa6  retn
```
