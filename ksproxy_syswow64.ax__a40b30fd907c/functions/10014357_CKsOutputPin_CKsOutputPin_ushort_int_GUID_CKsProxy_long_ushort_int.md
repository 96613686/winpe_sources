# CKsOutputPin::CKsOutputPin(ushort *,int,_GUID,CKsProxy *,long *,ushort *,int)

- ea: `0x10014357`
- end: `0x10014778`
- name: `??0CKsOutputPin@@QAE@PAGHU_GUID@@PAVCKsProxy@@PAJ0H@Z`
- size: `1057`
- prototype: `CKsOutputPin *__thiscall(CKsOutputPin *this, unsigned __int16 *, unsigned int, struct _GUID, struct CKsProxy *, int *, unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1001a323`
- `0x1001a516`

## callees

- `0x10006937`
- `0x10009f00`
- `0x10010c0e`
- `0x10014357`
- `0x100163d0`
- `0x10016700`
- `0x100197bb`
- `0x10020ce6`
- `0x1002fe3c`
- `0x1003035c`
- `0x10031f9c`
- `0x100335ef`
- `0x1003aba0`
- `0x1003b5e4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1001474f`
- `KERNEL32!GetLastError` at `0x1001474f`
- `KERNEL32!CreateEventW` at `0x1001461b`
- `KERNEL32!CreateEventW` at `0x1001461b`
- `KERNEL32!InitializeCriticalSection` at `0x10014401`
- `KERNEL32!InitializeCriticalSection` at `0x10014547`
- `KERNEL32!InitializeCriticalSection` at `0x10014401`
- `KERNEL32!InitializeCriticalSection` at `0x10014547`

## pseudocode

```c
CKsOutputPin *__thiscall CKsOutputPin::CKsOutputPin(
        CKsOutputPin *this,
        unsigned __int16 *a2,
        unsigned int a3,
        struct _GUID a4,
        struct CKsProxy *a5,
        int *a6,
        unsigned __int16 *a7,
        int a8)
{
  int v9; // ecx
  const unsigned __int16 *v10; // ecx
  const unsigned __int16 *v11; // ecx
  const unsigned __int16 *v12; // ecx
  HANDLE EventW; // eax
  KSPIN_COMMUNICATION m_OriginalCommunication; // eax
  int MediaType; // eax
  IKsPinEx *v16; // eax
  bool v17; // zf
  int v18; // eax
  signed int LastError; // eax
  unsigned int v20; // ecx
  unsigned int v22; // [esp+0h] [ebp-E8h]
  struct _AMMediaType *v23; // [esp+0h] [ebp-E8h]
  enum KSPIN_COMMUNICATION *v24; // [esp+4h] [ebp-E4h]
  struct CMediaType v25; // [esp+18h] [ebp-D0h] BYREF
  WCHAR SubKey[66]; // [esp+60h] [ebp-88h] BYREF

  CBaseOutputPin::CBaseOutputPin(
    this,
    a4.Data1 != 0 ? (const unsigned __int16 *)(a4.Data1 + 148) : 0,
    (struct CBaseFilter *)a4.Data1,
    a4.Data1 != 0 ? (struct CCritSec *)(a4.Data1 + 148) : 0,
    (int *)this,
    *(const unsigned __int16 **)a4.Data4);
  this->CBaseStreamControl::IAMStreamControl::IUnknown::__vftable = (CBaseStreamControl_vtbl *)&CBaseStreamControl::`vftable';
  this->m_StreamState = STREAM_FLOWING;
  this->m_StreamStateOnStop = STREAM_FLOWING;
  HIDWORD(this->m_tStartTime) = 0x7FFFFFFF;
  HIDWORD(this->m_tStopTime) = 0x7FFFFFFF;
  LODWORD(this->m_tStartTime) = -1;
  LODWORD(this->m_tStopTime) = -1;
  this->m_dwStartCookie = 0;
  this->m_dwStopCookie = 0;
  this->m_bIsFlushing = 0;
  this->m_bStopSendExtra = 0;
  InitializeCriticalSection(&this->m_CritSec.m_CritSec);
  CAMEvent::CAMEvent(&this->m_StreamEvent, v9, *(int **)&a4.Data2);
  this->m_pRefClock = 0;
  this->m_FilterState = State_Stopped;
  this->CBaseOutputPin::CBasePin::CUnknown::INonDelegatingUnknown::__vftable = (CKsOutputPin_vtbl *)&CKsOutputPin::`vftable'{for `CUnknown'};
  this->CBaseOutputPin::CBasePin::IPin::IUnknown::__vftable = (IPin_vtbl *)&CKsOutputPin2::`vftable'{for `IPin'};
  this->CBaseOutputPin::CBasePin::IQualityControl::IUnknown::__vftable = (IQualityControl_vtbl *)&CKsOutputPin2::`vftable'{for `IQualityControl'};
  this->CBaseStreamControl::IAMStreamControl::IUnknown::__vftable = (CBaseStreamControl_vtbl *)&CKsOutputPin2::`vftable'{for `CBaseStreamControl'};
  this->IMediaSeeking::IUnknown::__vftable = (IMediaSeeking_vtbl *)&CKsOutputPin::`vftable'{for `IMediaSeeking'};
  this->IKsObject::IUnknown::__vftable = (IKsObject_vtbl *)&CKsOutputPin2::`vftable'{for `IKsObject'};
  this->IKsPinEx::IKsPin::IUnknown::__vftable = (IKsPinEx_vtbl *)&CKsOutputPin::`vftable'{for `IKsPinEx'};
  this->IKsPinPipe::IUnknown::__vftable = (IKsPinPipe_vtbl *)&CKsOutputPin::`vftable'{for `IKsPinPipe'};
  this->ISpecifyPropertyPages::IUnknown::__vftable = (ISpecifyPropertyPages_vtbl *)&CKsOutputPin::`vftable'{for `ISpecifyPropertyPages'};
  this->IStreamBuilder::IUnknown::__vftable = (IStreamBuilder_vtbl *)&CKsOutputPin::`vftable'{for `IStreamBuilder'};
  this->IKsPropertySet::IUnknown::__vftable = (IKsPropertySet_vtbl *)&CKsOutputPin2::`vftable'{for `IKsPropertySet'};
  this->IKsPinFactory::IUnknown::__vftable = (IKsPinFactory_vtbl *)&CKsOutputPin2::`vftable'{for `IKsPinFactory'};
  this->IAMBufferNegotiation::IUnknown::__vftable = (IAMBufferNegotiation_vtbl *)&CKsOutputPin::`vftable'{for `IAMBufferNegotiation'};
  this->IAMStreamConfig::IUnknown::__vftable = (IAMStreamConfig_vtbl *)&CKsOutputPin::`vftable'{for `IAMStreamConfig'};
  this->IKsControl::IUnknown::__vftable = (IKsControl_vtbl *)&CKsOutputPin2::`vftable'{for `IKsControl'};
  this->IKsAggregateControl::IUnknown::__vftable = (IKsAggregateControl_vtbl *)&CKsOutputPin2::`vftable'{for `IKsAggregateControl'};
  this->IMemAllocatorNotifyCallbackTemp::IUnknown::__vftable = (IMemAllocatorNotifyCallbackTemp_vtbl *)&CKsOutputPin::`vftable'{for `IMemAllocatorNotifyCallbackTemp'};
  this->IKsPinPrivate::IUnknown::__vftable = (IKsPinPrivate_vtbl *)&CKsOutputPin2::`vftable'{for `IKsPinPrivate'};
  this->IKsD3DPin::IUnknown::__vftable = (IKsD3DPin_vtbl *)&CKsOutputPin::`vftable'{for `IKsD3DPin'};
  this->m_PinHandle = 0;
  this->m_IoThreadHandle = 0;
  this->m_IoThreadSemaphore = 0;
  this->m_IoThreadId = 0;
  this->m_DataTypeHandler = 0;
  this->m_UnkInner = 0;
  this->m_InterfaceHandler = 0;
  this->m_PinFactoryId = a3;
  this->m_MarshalData = 1;
  this->m_PropagatingAcquire = 0;
  this->m_UsingThisAllocator = 0;
  this->m_PendingIoCompletedEvent = 0;
  this->m_PendingIoCount = 0;
  CBaseList::CBaseList(&this->m_MarshalerList, v10);
  CBaseList::CBaseList(&this->m_IoQueue, v11);
  InitializeCriticalSection(&this->m_IoCriticalSection.m_CritSec);
  CBaseList::CBaseList(&this->m_IoThreadQueue, v12);
  this->m_QualitySupport = 0;
  this->m_LastSampleDiscarded = 1;
  this->m_ConfigAmMediaType = 0;
  this->m_DeliveryError = 0;
  this->m_EndOfStream = 0;
  this->m_pKsAllocator = 0;
  this->m_fPipeAllocator = 0;
  this->m_PinBusCacheInit = 0;
  this->m_bFlushing = 0;
  this->m_hMarshalEvent = 0;
  this->m_hFlushEvent = 0;
  this->m_hFlushCompleteEvent = 0;
  this->m_hEOSevent = 0;
  this->m_FlushMode = FLUSH_NONE;
  this->m_pAsyncItemHandler = 0;
  this->m_AdapterGUID = _GUID_00000000_0000_0000_0000_000000000000;
  this->m_spCapUsageHelper.ptr_ = 0;
  this->m_fIsCamera = *(_DWORD *)&a4.Data4[4];
  this->m_AdapterIndex = -1;
  this->m_pDirect3DDeviceManager9 = 0;
  this->m_ResetToken = 0;
  this->m_RelativeRefCount = 1;
  this->m_FramingProp[0] = FramingProp_Uninitialized;
  this->m_FramingProp[1] = FramingProp_Uninitialized;
  this->m_FramingProp[2] = FramingProp_Uninitialized;
  this->m_AllocatorFramingEx[0] = 0;
  this->m_AllocatorFramingEx[1] = 0;
  this->m_AllocatorFramingEx[2] = 0;
  if ( (int)**(_DWORD **)&a4.Data2 >= 0 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    this->m_PendingIoCompletedEvent = EventW;
    if ( EventW )
    {
      **(_DWORD **)&a4.Data2 = CKsProxy::GetPinFactoryCommunication(
                                 this->m_PinFactoryId,
                                 a4.Data1,
                                 (CKsProxy *)&this->m_OriginalCommunication,
                                 v22,
                                 v24);
      m_OriginalCommunication = this->m_OriginalCommunication;
      this->m_CurrentCommunication = m_OriginalCommunication;
      if ( m_OriginalCommunication == KSPIN_COMMUNICATION_NONE )
      {
        memset(&v25, 0, sizeof(v25));
        v25.lSampleSize = 1;
        v25.bFixedSizeSamples = 1;
        MediaType = CKsOutputPin::GetMediaType(this, 0, &v25);
        **(_DWORD **)&a4.Data2 = MediaType;
        if ( MediaType >= 0 )
          CKsOutputPin::SetMediaType(this, &v25);
        FreeMediaType(v23);
      }
      StringCchPrintfW(SubKey, 0x40u, L"PinFactory\\%u\\Interfaces", a3);
      v16 = &this->IKsPinEx;
      if ( !this )
        v16 = 0;
      AggregateMarshalers(*(HKEY *)(a4.Data1 + 296), SubKey, (int)&this->m_MarshalerList, (int)v16);
      v17 = this->m_fIsCamera == 1;
      this->m_SuggestedProperties.cBuffers = -1;
      this->m_SuggestedProperties.cbBuffer = -1;
      this->m_SuggestedProperties.cbPrefix = -1;
      this->m_SuggestedProperties.cbAlign = -1;
      if ( v17 && (int)**(_DWORD **)&a4.Data2 >= 0 )
      {
        v18 = Microsoft::WRL::Details::MakeAndInitialize<CapabilityUsageHelper,CapabilityUsageHelper,>(&this->m_spCapUsageHelper);
        **(_DWORD **)&a4.Data2 = v18;
        if ( v18 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          WPP_SF_SSd(
            0xAu,
            &WPP_673e2124b19330a2d80119fad92a0606_Traceguids,
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            *(const unsigned __int16 **)(a4.Data1 + 60),
            this->m_pName,
            v18);
      }
    }
    else
    {
      LastError = GetLastError();
      v20 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v20 = LastError;
      **(_DWORD **)&a4.Data2 = v20;
    }
  }
  return this;
}

```

## disassembly

```asm
0x10014357  mov     edi, edi
0x10014359  push    ebp
0x1001435a  mov     ebp, esp
0x1001435c  sub     esp, 0DCh
0x10014362  mov     eax, ___security_cookie
0x10014367  xor     eax, ebp
0x10014369  mov     [ebp+var_4], eax
0x1001436c  mov     edx, [ebp+arg_8.Data1]
0x1001436f  mov     eax, dword ptr [ebp+arg_8.Data4]
0x10014372  push    ebx
0x10014373  push    esi; enum KSPIN_COMMUNICATION *
0x10014374  mov     esi, dword ptr [ebp+arg_8.Data2]
0x10014377  mov     ebx, ecx
0x10014379  push    edi; struct _AMMediaType *
0x1001437a  push    eax; unsigned __int16 *
0x1001437b  push    ecx; int *
0x1001437c  mov     ecx, edx
0x1001437e  mov     [ebp+var_D4], edx
0x10014384  neg     ecx
0x10014386  mov     [ebp+var_D8], esi
0x1001438c  lea     eax, [edx+94h]
0x10014392  sbb     ecx, ecx
0x10014394  and     ecx, eax
0x10014396  push    ecx; struct CCritSec *
0x10014397  push    edx; struct CBaseFilter *
0x10014398  push    ecx; unsigned __int16 *
0x10014399  mov     ecx, ebx; this
0x1001439b  call    ??0CBaseOutputPin@@QAE@PBGPAVCBaseFilter@@PAVCCritSec@@PAJ0@Z; CBaseOutputPin::CBaseOutputPin(ushort const *,CBaseFilter *,CCritSec *,long *,ushort const *)
0x100143a0  mov     eax, 1000h
0x100143a5  mov     dword ptr [ebx+0A0h], offset ??_7CBaseStreamControl@@6B@; const CBaseStreamControl::`vftable'
0x100143af  mov     [ebx+0A4h], eax
0x100143b5  xor     edi, edi
0x100143b7  mov     [ebx+0A8h], eax
0x100143bd  mov     eax, 7FFFFFFFh
0x100143c2  mov     [ebx+0B4h], eax
0x100143c8  mov     [ebx+0BCh], eax
0x100143ce  lea     eax, [ebx+0D4h]
0x100143d4  mov     dword ptr [ebx+0B0h], 0FFFFFFFFh
0x100143de  mov     dword ptr [ebx+0B8h], 0FFFFFFFFh
0x100143e8  mov     [ebx+0C0h], edi
0x100143ee  mov     [ebx+0C4h], edi
0x100143f4  mov     [ebx+0C8h], edi
0x100143fa  push    eax; lpCriticalSection
0x100143fb  mov     [ebx+0CCh], edi
0x10014401  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x10014407  push    esi; int *
0x10014408  push    ecx; int
0x10014409  lea     ecx, [ebx+0ECh]; this
0x1001440f  call    ??0CAMEvent@@QAE@HPAJ@Z; CAMEvent::CAMEvent(int,long *)
0x10014414  mov     eax, [ebp+arg_4]
0x10014417  xor     esi, esi
0x10014419  mov     [ebx+0F0h], edi
0x1001441f  inc     esi
0x10014420  mov     [ebx+0F8h], edi
0x10014426  push    ecx; unsigned __int16 *
0x10014427  mov     dword ptr [ebx], offset ??_7CKsOutputPin@@6BCUnknown@@@; const CKsOutputPin::`vftable'{for `CUnknown'}
0x1001442d  lea     ecx, [ebx+1D4h]; this
0x10014433  mov     dword ptr [ebx+0Ch], offset ??_7CKsOutputPin2@@6BIPin@@@; const CKsOutputPin2::`vftable'{for `IPin'}
0x1001443a  mov     dword ptr [ebx+10h], offset ??_7CKsOutputPin2@@6BIQualityControl@@@; const CKsOutputPin2::`vftable'{for `IQualityControl'}
0x10014441  mov     dword ptr [ebx+0A0h], offset ??_7CKsOutputPin2@@6BCBaseStreamControl@@@; const CKsOutputPin2::`vftable'{for `CBaseStreamControl'}
0x1001444b  mov     dword ptr [ebx+108h], offset ??_7CKsOutputPin@@6BIMediaSeeking@@@; const CKsOutputPin::`vftable'{for `IMediaSeeking'}
0x10014455  mov     dword ptr [ebx+10Ch], offset ??_7CKsOutputPin2@@6BIKsObject@@@; const CKsOutputPin2::`vftable'{for `IKsObject'}
0x1001445f  mov     dword ptr [ebx+110h], offset ??_7CKsOutputPin@@6BIKsPinEx@@@; const CKsOutputPin::`vftable'{for `IKsPinEx'}
0x10014469  mov     dword ptr [ebx+114h], offset ??_7CKsOutputPin@@6BIKsPinPipe@@@; const CKsOutputPin::`vftable'{for `IKsPinPipe'}
0x10014473  mov     dword ptr [ebx+118h], offset ??_7CKsOutputPin@@6BISpecifyPropertyPages@@@; const CKsOutputPin::`vftable'{for `ISpecifyPropertyPages'}
0x1001447d  mov     dword ptr [ebx+11Ch], offset ??_7CKsOutputPin@@6BIStreamBuilder@@@; const CKsOutputPin::`vftable'{for `IStreamBuilder'}
0x10014487  mov     dword ptr [ebx+120h], offset ??_7CKsOutputPin2@@6BIKsPropertySet@@@; const CKsOutputPin2::`vftable'{for `IKsPropertySet'}
0x10014491  mov     dword ptr [ebx+124h], offset ??_7CKsOutputPin2@@6BIKsPinFactory@@@; const CKsOutputPin2::`vftable'{for `IKsPinFactory'}
0x1001449b  mov     dword ptr [ebx+128h], offset ??_7CKsOutputPin@@6BIAMBufferNegotiation@@@; const CKsOutputPin::`vftable'{for `IAMBufferNegotiation'}
0x100144a5  mov     dword ptr [ebx+12Ch], offset ??_7CKsOutputPin@@6BIAMStreamConfig@@@; const CKsOutputPin::`vftable'{for `IAMStreamConfig'}
0x100144af  mov     dword ptr [ebx+130h], offset ??_7CKsOutputPin2@@6BIKsControl@@@; const CKsOutputPin2::`vftable'{for `IKsControl'}
0x100144b9  mov     dword ptr [ebx+134h], offset ??_7CKsOutputPin2@@6BIKsAggregateControl@@@; const CKsOutputPin2::`vftable'{for `IKsAggregateControl'}
0x100144c3  mov     dword ptr [ebx+138h], offset ??_7CKsOutputPin@@6BIMemAllocatorNotifyCallbackTemp@@@; const CKsOutputPin::`vftable'{for `IMemAllocatorNotifyCallbackTemp'}
0x100144cd  mov     dword ptr [ebx+13Ch], offset ??_7CKsOutputPin2@@6BIKsPinPrivate@@@; const CKsOutputPin2::`vftable'{for `IKsPinPrivate'}
0x100144d7  mov     dword ptr [ebx+140h], offset ??_7CKsOutputPin@@6BIKsD3DPin@@@; const CKsOutputPin::`vftable'{for `IKsD3DPin'}
0x100144e1  mov     [ebx+164h], edi
0x100144e7  mov     [ebx+16Ch], edi
0x100144ed  mov     [ebx+170h], edi
0x100144f3  mov     [ebx+174h], edi
0x100144f9  mov     [ebx+178h], edi
0x100144ff  mov     [ebx+17Ch], edi
0x10014505  mov     [ebx+180h], edi
0x1001450b  mov     [ebx+184h], eax
0x10014511  mov     [ebx+1C0h], esi
0x10014517  mov     [ebx+1C4h], edi
0x1001451d  mov     [ebx+1C8h], edi
0x10014523  mov     [ebx+1CCh], edi
0x10014529  mov     [ebx+1D0h], edi
0x1001452f  call    ??0CBaseList@@QAE@PBG@Z; CBaseList::CBaseList(ushort const *)
0x10014534  push    ecx; unsigned __int16 *
0x10014535  lea     ecx, [ebx+1ECh]; this
0x1001453b  call    ??0CBaseList@@QAE@PBG@Z; CBaseList::CBaseList(ushort const *)
0x10014540  lea     eax, [ebx+204h]
0x10014546  push    eax; lpCriticalSection
0x10014547  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x1001454d  push    ecx; unsigned __int16 *
0x1001454e  lea     ecx, [ebx+21Ch]; this
0x10014554  call    ??0CBaseList@@QAE@PBG@Z; CBaseList::CBaseList(ushort const *)
0x10014559  mov     [ebx+234h], edi
0x1001455f  xor     ecx, ecx
0x10014561  mov     [ebx+238h], esi
0x10014567  mov     esi, offset __GUID_00000000_0000_0000_0000_000000000000
0x1001456c  mov     [ebx+23Ch], edi
0x10014572  mov     [ebx+240h], edi
0x10014578  mov     [ebx+244h], edi
0x1001457e  mov     [ebx+24Ch], edi
0x10014584  mov     [ebx+268h], edi
0x1001458a  mov     [ebx+27Ch], edi
0x10014590  mov     [ebx+280h], edi
0x10014596  mov     [ebx+284h], edi
0x1001459c  mov     [ebx+288h], edi
0x100145a2  mov     [ebx+28Ch], edi
0x100145a8  mov     [ebx+290h], edi
0x100145ae  mov     [ebx+294h], edi
0x100145b4  mov     [ebx+298h], edi
0x100145ba  lea     edi, [ebx+2A0h]
0x100145c0  movsd
0x100145c1  mov     eax, dword ptr [ebp+arg_8.Data4+4]
0x100145c4  movsd
0x100145c5  movsd
0x100145c6  movsd
0x100145c7  mov     [ebx+2BCh], ecx
0x100145cd  lea     edi, [ebx+25Ch]
0x100145d3  mov     [ebx+2C0h], eax
0x100145d9  xor     eax, eax
0x100145db  mov     dword ptr [ebx+2B0h], 0FFFFFFFFh
0x100145e5  mov     [ebx+2B4h], ecx
0x100145eb  mov     [ebx+2B8h], ecx
0x100145f1  mov     dword ptr [ebx+2C4h], 1
0x100145fb  stosd
0x100145fc  stosd
0x100145fd  stosd
0x100145fe  xor     eax, eax
0x10014600  lea     edi, [ebx+250h]
0x10014606  stosd
0x10014607  stosd
0x10014608  stosd
0x10014609  mov     edi, [ebp+var_D8]
0x1001460f  cmp     [edi], ecx
0x10014611  jl      loc_10014765
0x10014617  push    ecx; lpName
0x10014618  push    ecx; bInitialState
0x10014619  push    ecx; bManualReset
0x1001461a  push    ecx; lpEventAttributes
0x1001461b  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x10014621  mov     [ebx+1CCh], eax
0x10014627  test    eax, eax
0x10014629  jz      loc_1001474F
0x1001462f  mov     edx, [ebx+184h]
0x10014635  lea     esi, [ebx+188h]
0x1001463b  mov     ecx, [ebp+var_D4]
0x10014641  push    esi; this
0x10014642  call    ?GetPinFactoryCommunication@CKsProxy@@QAGJKPAW4KSPIN_COMMUNICATION@@@Z; CKsProxy::GetPinFactoryCommunication(ulong,KSPIN_COMMUNICATION *)
0x10014647  mov     [edi], eax
0x10014649  mov     eax, [esi]
0x1001464b  mov     [ebx+18Ch], eax
0x10014651  test    eax, eax
0x10014653  jnz     short loc_100146A5
0x10014655  push    48h ; 'H'; Size
0x10014657  push    eax; Val
0x10014658  lea     eax, [ebp+var_D0]
0x1001465e  push    eax; void *
0x1001465f  call    _memset
0x10014664  xor     eax, eax
0x10014666  add     esp, 0Ch
0x10014669  inc     eax
0x1001466a  mov     ecx, ebx; this
0x1001466c  mov     [ebp+var_D0.lSampleSize], eax
0x10014672  mov     [ebp+var_D0.bFixedSizeSamples], eax
0x10014678  lea     eax, [ebp+var_D0]
0x1001467e  push    eax; struct CMediaType *
0x1001467f  push    0; int
0x10014681  call    ?GetMediaType@CKsOutputPin@@UAEJHPAVCMediaType@@@Z; CKsOutputPin::GetMediaType(int,CMediaType *)
0x10014686  mov     [edi], eax
0x10014688  test    eax, eax
0x1001468a  js      short loc_1001469A
0x1001468c  lea     eax, [ebp+var_D0]
0x10014692  mov     ecx, ebx; this
0x10014694  push    eax; struct CMediaType *
0x10014695  call    ?SetMediaType@CKsOutputPin@@UAEJPBVCMediaType@@@Z; CKsOutputPin::SetMediaType(CMediaType const *)
0x1001469a  lea     ecx, [ebp+var_D0]
0x100146a0  call    ?FreeMediaType@@YGXAAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x100146a5  push    [ebp+arg_4]
0x100146a8  lea     eax, [ebp+SubKey]
0x100146ae  push    offset aPinfactoryUInt; "PinFactory\\%u\\Interfaces"
0x100146b3  push    40h ; '@'; unsigned int
0x100146b5  push    eax; unsigned __int16 *
0x100146b6  call    ?StringCchPrintfW@@YAJPAGIPBGZZ; StringCchPrintfW(ushort *,uint,ushort const *,...)
0x100146bb  mov     esi, [ebp+var_D4]
0x100146c1  lea     eax, [ebx+110h]
0x100146c7  add     esp, 10h
0x100146ca  lea     edx, [ebp+SubKey]; lpSubKey
0x100146d0  xor     ecx, ecx
0x100146d2  test    ebx, ebx
0x100146d4  cmovz   eax, ecx
0x100146d7  mov     ecx, [esi+128h]; hKey
0x100146dd  push    eax; int
0x100146de  lea     eax, [ebx+1D4h]
0x100146e4  push    eax; int
0x100146e5  call    ?AggregateMarshalers@@YGJPAUHKEY__@@PBGPAV?$CGenericList@VCAggregateMarshaler@@@@PAUIUnknown@@@Z; AggregateMarshalers(HKEY__ *,ushort const *,CGenericList<CAggregateMarshaler> *,IUnknown *)
0x100146ea  or      eax, 0FFFFFFFFh
0x100146ed  cmp     dword ptr [ebx+2C0h], 1
0x100146f4  mov     [ebx+154h], eax
0x100146fa  mov     [ebx+158h], eax
0x10014700  mov     [ebx+160h], eax
0x10014706  mov     [ebx+15Ch], eax
0x1001470c  jnz     short loc_10014765
0x1001470e  cmp     dword ptr [edi], 0
0x10014711  jl      short loc_10014765
0x10014713  lea     eax, [ebx+2BCh]
0x10014719  push    eax
0x1001471a  call    ??$MakeAndInitialize@VCapabilityUsageHelper@@V1@$$V@Details@WRL@Microsoft@@YGJV?$ComPtrRef@V?$ComPtr@VCapabilityUsageHelper@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<CapabilityUsageHelper,CapabilityUsageHelper,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<CapabilityUsageHelper>>)
0x1001471f  mov     [edi], eax
0x10014721  test    eax, eax
0x10014723  jns     short loc_10014765
0x10014725  mov     ecx, _WPP_GLOBAL_Control
0x1001472b  cmp     ecx, offset _WPP_GLOBAL_Control
0x10014731  jz      short loc_10014765
0x10014733  push    eax; char
0x10014734  push    dword ptr [ebx+14h]; int
0x10014737  mov     edx, offset _WPP_673e2124b19330a2d80119fad92a0606_Traceguids
0x1001473c  push    dword ptr [esi+3Ch]; int
0x1001473f  push    dword ptr [ecx+14h]
0x10014742  push    dword ptr [ecx+10h]; LoggerHandle
0x10014745  push    0Ah
0x10014747  pop     ecx
0x10014748  call    _WPP_SF_SSd@28; WPP_SF_SSd(x,x,x,x,x,x,x)
0x1001474d  jmp     short loc_10014765
0x1001474f  call    ds:__imp__GetLastError@0; GetLastError()
0x10014755  movzx   ecx, ax
0x10014758  or      ecx, 80070000h
0x1001475e  test    eax, eax
0x10014760  cmovle  ecx, eax
0x10014763  mov     [edi], ecx
0x10014765  mov     ecx, [ebp+var_4]
0x10014768  mov     eax, ebx
0x1001476a  pop     edi
0x1001476b  pop     esi
0x1001476c  xor     ecx, ebp; StackCookie
0x1001476e  pop     ebx
0x1001476f  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10014774  leave
0x10014775  retn    28h ; '('
```
