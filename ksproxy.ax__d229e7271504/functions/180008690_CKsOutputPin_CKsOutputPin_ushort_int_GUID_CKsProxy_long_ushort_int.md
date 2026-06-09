# CKsOutputPin::CKsOutputPin(ushort *,int,_GUID,CKsProxy *,long *,ushort *,int)

- ea: `0x180008690`
- end: `0x180009093`
- name: `??0CKsOutputPin@@QEAA@PEAGHU_GUID@@PEAVCKsProxy@@PEAJ0H@Z`
- size: `2563`
- prototype: `CKsOutputPin *__fastcall(CKsOutputPin *this, unsigned __int16 *, unsigned int, struct _GUID *, struct CKsProxy *, int *, unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000d4b0`
- `0x18002cac4`

## callees

- `0x1800042b0`
- `0x180008690`
- `0x18000909c`
- `0x180009128`
- `0x180009c4c`
- `0x18000b2e4`
- `0x1800192a0`
- `0x18001f1d0`
- `0x18001f210`
- `0x18001f620`
- `0x18001ffb0`
- `0x180028fc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008c46`
- `KERNEL32!GetLastError` at `0x180008dcb`
- `KERNEL32!GetLastError` at `0x180008e18`
- `KERNEL32!GetLastError` at `0x180008e3c`
- `KERNEL32!GetLastError` at `0x180008c46`
- `KERNEL32!GetLastError` at `0x180008dcb`
- `KERNEL32!GetLastError` at `0x180008e18`
- `KERNEL32!GetLastError` at `0x180008e3c`
- `KERNEL32!CreateEventW` at `0x18000888c`
- `KERNEL32!CreateEventW` at `0x180008b6a`
- `KERNEL32!CreateEventW` at `0x180008bdf`
- `KERNEL32!CreateEventW` at `0x18000888c`
- `KERNEL32!CreateEventW` at `0x180008b6a`
- `KERNEL32!CreateEventW` at `0x180008bdf`
- `KERNEL32!CloseHandle` at `0x180008c71`
- `KERNEL32!CloseHandle` at `0x180008c71`
- `KERNEL32!InitializeCriticalSection` at `0x180008876`
- `KERNEL32!InitializeCriticalSection` at `0x180008a62`
- `KERNEL32!InitializeCriticalSection` at `0x180008876`
- `KERNEL32!InitializeCriticalSection` at `0x180008a62`
- `KERNEL32!GetOverlappedResult` at `0x180008e01`
- `KERNEL32!GetOverlappedResult` at `0x180008e01`
- `KERNEL32!DeviceIoControl` at `0x180008c32`
- `KERNEL32!DeviceIoControl` at `0x180008c32`
- `ADVAPI32!RegQueryValueExW` at `0x180008fc2`
- `ADVAPI32!RegQueryValueExW` at `0x180008fc2`
- `ADVAPI32!RegCloseKey` at `0x180008f22`
- `ADVAPI32!RegCloseKey` at `0x180008fd5`
- `ADVAPI32!RegCloseKey` at `0x18000906c`
- `ADVAPI32!RegCloseKey` at `0x18000907d`
- `ADVAPI32!RegCloseKey` at `0x180008f22`
- `ADVAPI32!RegCloseKey` at `0x180008fd5`
- `ADVAPI32!RegCloseKey` at `0x18000906c`
- `ADVAPI32!RegCloseKey` at `0x18000907d`
- `ADVAPI32!RegOpenKeyExW` at `0x180008ce3`
- `ADVAPI32!RegOpenKeyExW` at `0x180008f0d`
- `ADVAPI32!RegOpenKeyExW` at `0x180008f81`
- `ADVAPI32!RegOpenKeyExW` at `0x180008ce3`
- `ADVAPI32!RegOpenKeyExW` at `0x180008f0d`
- `ADVAPI32!RegOpenKeyExW` at `0x180008f81`
- `ADVAPI32!RegEnumKeyW` at `0x180008f51`
- `ADVAPI32!RegEnumKeyW` at `0x180009053`
- `ADVAPI32!RegEnumKeyW` at `0x180008f51`
- `ADVAPI32!RegEnumKeyW` at `0x180009053`
- `ole32!IIDFromString` at `0x180009011`
- `ole32!IIDFromString` at `0x180009011`

## pseudocode

```c
CKsOutputPin *__fastcall CKsOutputPin::CKsOutputPin(
        CKsOutputPin *this,
        unsigned __int16 *a2,
        unsigned int a3,
        struct _GUID *a4,
        struct CKsProxy *a5,
        int *a6,
        unsigned __int16 *a7,
        int a8)
{
  int *v8; // rsi
  CCritSec *v11; // rcx
  unsigned __int16 *v12; // rbx
  __int64 v13; // rcx
  unsigned __int16 *v14; // rax
  unsigned __int64 v15; // rsi
  wchar_t *v16; // rax
  wchar_t *v17; // rdx
  __int64 v18; // rcx
  wchar_t *v19; // rcx
  HANDLE EventW; // rax
  IKsPinEx *v21; // r14
  unsigned int v22; // ebx
  HANDLE v23; // rax
  char *m_FilterHandle; // rsi
  signed int LastError; // eax
  int *v26; // rsi
  KSPIN_COMMUNICATION m_OriginalCommunication; // eax
  HKEY__ *m_DeviceRegKey; // rcx
  bool v29; // zf
  int v31; // eax
  signed int v32; // eax
  signed int v33; // eax
  signed int v34; // eax
  int MediaType; // eax
  DWORD i; // esi
  LSTATUS v37; // ebx
  GUID *v38; // rax
  GUID *v39; // rbx
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  int *v42; // [rsp+50h] [rbp-B0h]
  HKEY v43; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  GUID InBuffer; // [rsp+68h] [rbp-98h] BYREF
  int v46; // [rsp+78h] [rbp-88h]
  int v47; // [rsp+7Ch] [rbp-84h]
  unsigned int m_PinFactoryId; // [rsp+80h] [rbp-80h]
  int v49; // [rsp+84h] [rbp-7Ch]
  struct _OVERLAPPED Overlapped; // [rsp+88h] [rbp-78h] BYREF
  struct _AMMediaType Name; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR SubKey[64]; // [rsp+130h] [rbp+30h] BYREF

  v8 = a6;
  LODWORD(phkResult) = a3;
  v42 = a6;
  v11 = &a5->CCritSec;
  if ( !a5 )
    v11 = 0;
  _InterlockedIncrement(&CBaseObject::m_cObjects);
  this->m_pLock = v11;
  this->m_pUnknown = (IUnknown *const)this;
  this->m_cRef = 0;
  this->m_pName = 0;
  this->m_Connected = 0;
  this->m_dir = PINDIR_OUTPUT;
  *(_WORD *)&this->m_bRunTimeError = 0;
  this->m_bTryMyTypesFirst = 0;
  this->m_pFilter = a5;
  this->m_pQSink = 0;
  this->m_TypeVersion = 1;
  memset_0(&this->m_mt, 0, sizeof(this->m_mt));
  v12 = a7;
  this->m_mt.lSampleSize = 1;
  this->m_mt.bFixedSizeSamples = 1;
  this->m_tStart.m_time = 0;
  this->m_tStop.m_time = 0x7FFFFFFFFFFFFFFFLL;
  this->m_dRate = 1.0;
  if ( a7 )
  {
    v13 = 0x7FFFFFFF;
    v14 = a7;
    while ( *v14 )
    {
      ++v14;
      if ( !--v13 )
        goto LABEL_19;
    }
    v15 = 0x80000000LL - v13;
    v16 = (wchar_t *)operator new[](saturated_mul(0x80000000LL - v13, 2u));
    this->m_pName = v16;
    v17 = v16;
    if ( v16 && v15 )
    {
      if ( v15 > 0x7FFFFFFF )
      {
        *v16 = 0;
      }
      else
      {
        v18 = 2147483646;
        do
        {
          if ( !v18 )
            break;
          if ( !*v12 )
            break;
          *v17++ = *v12++;
          --v18;
          --v15;
        }
        while ( v15 );
        v19 = v17 - 1;
        if ( v15 )
          v19 = v17;
        *v19 = 0;
      }
    }
    v8 = v42;
  }
LABEL_19:
  this->m_pAllocator = 0;
  this->m_pInputPin = 0;
  this->CBaseStreamControl::IAMStreamControl::IUnknown::__vftable = (CBaseStreamControl_vtbl *)&CBaseStreamControl::`vftable';
  this->m_StreamState = STREAM_FLOWING;
  this->m_StreamStateOnStop = STREAM_FLOWING;
  this->m_tStartTime = 0x7FFFFFFFFFFFFFFFLL;
  this->m_tStopTime = 0x7FFFFFFFFFFFFFFFLL;
  *(_QWORD *)&this->m_dwStartCookie = 0;
  this->m_bIsFlushing = 0;
  this->m_bStopSendExtra = 0;
  InitializeCriticalSection(&this->m_CritSec.m_CritSec);
  EventW = CreateEventW(0, 0, 0, 0);
  this->m_StreamEvent.m_hEvent = EventW;
  if ( !EventW && v8 && *v8 >= 0 )
    *v8 = -2147024882;
  this->m_pRefClock = 0;
  this->m_FilterState = State_Stopped;
  v21 = &this->IKsPinEx;
  this->CBaseOutputPin::CBasePin::CUnknown::INonDelegatingUnknown::__vftable = (CKsOutputPin_vtbl *)&CKsOutputPin::`vftable'{for `CUnknown'};
  this->m_PinFactoryId = a3;
  this->CBaseOutputPin::CBasePin::IPin::IUnknown::__vftable = (IPin_vtbl *)&CKsOutputPin2::`vftable'{for `IPin'};
  this->m_PinHandle = 0;
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
  this->m_IoThreadHandle = 0;
  this->m_IoThreadSemaphore = 0;
  this->m_IoThreadId = 0;
  this->m_DataTypeHandler = 0;
  this->m_UnkInner = 0;
  this->m_InterfaceHandler = 0;
  *(_QWORD *)&this->m_MarshalData = 1;
  this->m_UsingThisAllocator = 0;
  this->m_PendingIoCompletedEvent = 0;
  this->m_PendingIoCount = 0;
  this->m_MarshalerList.m_pFirst = 0;
  this->m_MarshalerList.m_pLast = 0;
  this->m_MarshalerList.m_Count = 0;
  *(_QWORD *)&this->m_MarshalerList.m_Cache.m_iCacheSize = 10;
  this->m_MarshalerList.m_Cache.m_pHead = 0;
  this->m_IoQueue.m_pFirst = 0;
  this->m_IoQueue.m_pLast = 0;
  this->m_IoQueue.m_Count = 0;
  *(_QWORD *)&this->m_IoQueue.m_Cache.m_iCacheSize = 10;
  this->m_IoQueue.m_Cache.m_pHead = 0;
  InitializeCriticalSection(&this->m_IoCriticalSection.m_CritSec);
  this->m_IoThreadQueue.m_pFirst = 0;
  this->m_IoThreadQueue.m_pLast = 0;
  this->m_IoThreadQueue.m_Count = 0;
  *(_QWORD *)&this->m_IoThreadQueue.m_Cache.m_iCacheSize = 10;
  this->m_IoThreadQueue.m_Cache.m_pHead = 0;
  this->m_QualitySupport = 0;
  this->m_LastSampleDiscarded = 1;
  this->m_ConfigAmMediaType = 0;
  *(_QWORD *)&this->m_DeliveryError = 0;
  this->m_pKsAllocator = 0;
  this->m_fPipeAllocator = 0;
  *(_QWORD *)&this->m_PinBusCacheInit = 0;
  this->m_hMarshalEvent = 0;
  this->m_hFlushEvent = 0;
  this->m_hFlushCompleteEvent = 0;
  v22 = 0;
  this->m_hEOSevent = 0;
  this->m_FlushMode = FLUSH_NONE;
  this->m_pAsyncItemHandler = 0;
  this->m_AdapterIndex = -1;
  this->m_pDirect3DDeviceManager9 = 0;
  this->m_AdapterGUID = GUID_00000000_0000_0000_0000_000000000000;
  this->m_ResetToken = 0;
  this->m_spCapUsageHelper.ptr_ = 0;
  this->m_fIsCamera = a8;
  this->m_RelativeRefCount = 1;
  *(_QWORD *)this->m_FramingProp = 0;
  this->m_FramingProp[2] = FramingProp_Uninitialized;
  *(_OWORD *)this->m_AllocatorFramingEx = 0;
  this->m_AllocatorFramingEx[2] = 0;
  if ( *v8 >= 0 )
  {
    v23 = CreateEventW(0, 0, 0, 0);
    this->m_PendingIoCompletedEvent = v23;
    if ( v23 )
    {
      m_FilterHandle = (char *)a5->m_FilterHandle;
      m_PinFactoryId = this->m_PinFactoryId;
      BytesReturned = 0;
      v46 = 7;
      v47 = 1;
      v49 = 0;
      InBuffer = GUID_8c134960_51ad_11cf_878a_94f801c10000;
      if ( (unsigned __int64)(m_FilterHandle - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        v22 = -2147024890;
      }
      else
      {
        memset(&Overlapped, 0, 24);
        Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
        if ( Overlapped.hEvent )
        {
          if ( DeviceIoControl(
                 m_FilterHandle,
                 0x2F0003u,
                 &InBuffer,
                 0x20u,
                 &this->m_OriginalCommunication,
                 4u,
                 &BytesReturned,
                 &Overlapped) )
          {
            switch ( Overlapped.Internal )
            {
              case 0x101uLL:
                v22 = -2147024875;
                break;
              case 0x105uLL:
                v22 = -2147024662;
                break;
              case 0x107uLL:
                v22 = -2147023595;
                break;
            }
          }
          else
          {
            LastError = GetLastError();
            v22 = LastError;
            if ( LastError > 0 )
              v22 = (unsigned __int16)LastError | 0x80070000;
            if ( v22 == -2147023899 )
            {
              if ( GetOverlappedResult(m_FilterHandle, &Overlapped, &BytesReturned, 1) )
              {
                v22 = 0;
              }
              else
              {
                v33 = GetLastError();
                v22 = v33;
                if ( v33 > 0 )
                  v22 = (unsigned __int16)v33 | 0x80070000;
              }
            }
          }
          CloseHandle(Overlapped.hEvent);
        }
        else
        {
          v32 = GetLastError();
          v22 = v32;
          if ( v32 > 0 )
            v22 = (unsigned __int16)v32 | 0x80070000;
        }
      }
      v26 = v42;
      *v42 = v22;
      m_OriginalCommunication = this->m_OriginalCommunication;
      this->m_CurrentCommunication = m_OriginalCommunication;
      if ( m_OriginalCommunication == KSPIN_COMMUNICATION_NONE )
      {
        memset_0((void *)&Name, 0, sizeof(Name));
        Name.lSampleSize = 1;
        Name.bFixedSizeSamples = 1;
        MediaType = CKsOutputPin::GetMediaType(this, 0, (struct CMediaType *)&Name);
        *v26 = MediaType;
        if ( MediaType >= 0 )
          CKsOutputPin::SetMediaType(this, (struct CMediaType *)&Name);
        FreeMediaType(&Name);
      }
      StringCchPrintfW(SubKey, 0x40u, L"PinFactory\\%u\\Interfaces", (unsigned int)phkResult);
      m_DeviceRegKey = a5->m_DeviceRegKey;
      phkResult = 0;
      hKey = 0;
      if ( !this )
        v21 = 0;
      if ( !RegOpenKeyExW(m_DeviceRegKey, SubKey, 0, 0x20019u, &phkResult) )
      {
        if ( RegOpenKeyExW(
               HKEY_LOCAL_MACHINE,
               L"SYSTEM\\CurrentControlSet\\Control\\MediaInterfaces",
               0,
               0x20019u,
               &hKey) )
        {
          RegCloseKey(phkResult);
        }
        else
        {
          BytesReturned = 0;
          v43 = 0;
          *(_OWORD *)&Overlapped.Internal = 0;
          for ( i = 0; !RegEnumKeyW(phkResult, i, (LPWSTR)&Name, 0x40u); *(_OWORD *)&Overlapped.Internal = 0 )
          {
            if ( !RegOpenKeyExW(hKey, (LPCWSTR)&Name, 0, 0x20019u, &v43) )
            {
              BytesReturned = 16;
              v37 = RegQueryValueExW(v43, L"iid", 0, 0, (LPBYTE)&Overlapped, &BytesReturned);
              RegCloseKey(v43);
              if ( v37 )
                *(GUID *)&Overlapped.Internal = GUID_00000000_0000_0000_0000_000000000000;
              v38 = (GUID *)operator new(0x38u);
              v39 = v38;
              if ( !v38 )
                break;
              *v38 = *(GUID *)&Overlapped.Internal;
              IIDFromString((LPCOLESTR)&Name, v38 + 1);
              AddAggregateObject(&this->m_MarshalerList, v39, v21);
            }
            BytesReturned = 0;
            ++i;
            v43 = 0;
          }
          RegCloseKey(hKey);
          RegCloseKey(phkResult);
          v26 = v42;
        }
      }
      v29 = this->m_fIsCamera == 1;
      *(_QWORD *)&this->m_SuggestedProperties.cBuffers = -1;
      *(_QWORD *)&this->m_SuggestedProperties.cbAlign = -1;
      if ( v29 && *v26 >= 0 )
      {
        v31 = Microsoft::WRL::Details::MakeAndInitialize<CapabilityUsageHelper,CapabilityUsageHelper,>(&this->m_spCapUsageHelper);
        *v26 = v31;
        if ( v31 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            10,
            (unsigned int)&WPP_673e2124b19330a2d80119fad92a0606_Traceguids,
            a5->m_pName,
            (__int64)this->m_pName,
            v31);
      }
    }
    else
    {
      v34 = GetLastError();
      if ( v34 > 0 )
        v34 = (unsigned __int16)v34 | 0x80070000;
      *v8 = v34;
    }
  }
  return this;
}

```

## disassembly

```asm
0x180008690  mov     [rsp-8+arg_8], rbx
0x180008695  push    rbp
0x180008696  push    rsi
0x180008697  push    rdi
0x180008698  push    r12
0x18000869a  push    r13
0x18000869c  push    r14
0x18000869e  push    r15
0x1800086a0  lea     rbp, [rsp-0C0h]
0x1800086a8  sub     rsp, 1C0h
0x1800086af  mov     rax, cs:__security_cookie
0x1800086b6  xor     rax, rsp
0x1800086b9  mov     [rbp+0F0h+var_40], rax
0x1800086c0  mov     r15, [rbp+0F0h+arg_20]
0x1800086c7  xor     r13d, r13d
0x1800086ca  mov     rsi, [rbp+0F0h+arg_28]
0x1800086d1  mov     rdi, rcx
0x1800086d4  test    r15, r15
0x1800086d7  mov     dword ptr [rsp+1F0h+phkResult], r8d
0x1800086dc  mov     r12d, r8d
0x1800086df  mov     [rsp+1F0h+var_1A0], rsi
0x1800086e4  lea     rcx, [r15+0F8h]
0x1800086eb  cmovz   rcx, r13
0x1800086ef  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x1800086f6  mov     [rdi+40h], rcx
0x1800086fa  xor     edx, edx; Val
0x1800086fc  mov     [rdi+8], rdi
0x180008700  lea     rcx, [rdi+68h]; void *
0x180008704  mov     r8d, 58h ; 'X'; Size
0x18000870a  mov     [rdi+10h], r13d
0x18000870e  mov     [rdi+28h], r13
0x180008712  mov     [rdi+30h], r13
0x180008716  mov     dword ptr [rdi+38h], 1
0x18000871d  mov     [rdi+48h], r13w
0x180008722  mov     [rdi+4Ah], r13b
0x180008726  mov     [rdi+50h], r15
0x18000872a  mov     [rdi+58h], r13
0x18000872e  mov     dword ptr [rdi+60h], 1
0x180008735  call    memset_0
0x18000873a  mov     rbx, [rbp+0F0h+arg_30]
0x180008741  mov     r14, 7FFFFFFFFFFFFFFFh
0x18000874b  mov     dword ptr [rdi+90h], 1
0x180008755  mov     rax, 3FF0000000000000h
0x18000875f  mov     dword ptr [rdi+88h], 1
0x180008769  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180008770  mov     [rdi+0C0h], r13
0x180008777  mov     [rdi+0C8h], r14
0x18000877e  mov     [rdi+0D0h], rax
0x180008785  test    rbx, rbx
0x180008788  jz      loc_18000881C
0x18000878e  mov     ecx, 7FFFFFFFh
0x180008793  mov     rax, rbx
0x180008796  cmp     [rax], r13w
0x18000879a  jz      short loc_1800087A8
0x18000879c  add     rax, 2
0x1800087a0  sub     rcx, 1
0x1800087a4  jnz     short loc_180008796
0x1800087a6  jmp     short loc_18000881C
0x1800087a8  mov     esi, 80000000h
0x1800087ad  mov     eax, 2
0x1800087b2  sub     rsi, rcx
0x1800087b5  mul     rsi
0x1800087b8  cmovb   rax, r8
0x1800087bc  mov     rcx, rax; unsigned __int64
0x1800087bf  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800087c4  mov     [rdi+28h], rax
0x1800087c8  mov     rdx, rax
0x1800087cb  test    rax, rax
0x1800087ce  jz      short loc_180008817
0x1800087d0  test    rsi, rsi
0x1800087d3  jz      short loc_180008817
0x1800087d5  cmp     rsi, 7FFFFFFFh
0x1800087dc  ja      loc_180008E5B
0x1800087e2  mov     ecx, 7FFFFFFEh
0x1800087e7  test    rcx, rcx
0x1800087ea  jz      short loc_180008808
0x1800087ec  movzx   eax, word ptr [rbx]
0x1800087ef  test    ax, ax
0x1800087f2  jz      short loc_180008808
0x1800087f4  mov     [rdx], ax
0x1800087f7  add     rbx, 2
0x1800087fb  add     rdx, 2
0x1800087ff  dec     rcx
0x180008802  sub     rsi, 1
0x180008806  jnz     short loc_1800087E7
0x180008808  test    rsi, rsi
0x18000880b  lea     rcx, [rdx-2]
0x18000880f  cmovnz  rcx, rdx
0x180008813  mov     [rcx], r13w
0x180008817  mov     rsi, [rsp+1F0h+var_1A0]
0x18000881c  mov     [rdi+0D8h], r13
0x180008823  lea     rax, ??_7CBaseStreamControl@@6B@; const CBaseStreamControl::`vftable'
0x18000882a  mov     [rdi+0E0h], r13
0x180008831  lea     rcx, [rdi+120h]; lpCriticalSection
0x180008838  mov     [rdi+0E8h], rax
0x18000883f  mov     dword ptr [rdi+0F0h], 1000h
0x180008849  mov     dword ptr [rdi+0F4h], 1000h
0x180008853  mov     [rdi+0F8h], r14
0x18000885a  mov     [rdi+100h], r14
0x180008861  mov     [rdi+108h], r13
0x180008868  mov     [rdi+110h], r13d
0x18000886f  mov     [rdi+114h], r13d
0x180008876  call    cs:__imp_InitializeCriticalSection
0x18000887d  nop     dword ptr [rax+rax+00h]
0x180008882  xor     r9d, r9d; lpName
0x180008885  xor     r8d, r8d; bInitialState
0x180008888  xor     edx, edx; bManualReset
0x18000888a  xor     ecx, ecx; lpEventAttributes
0x18000888c  call    cs:__imp_CreateEventW
0x180008893  nop     dword ptr [rax+rax+00h]
0x180008898  mov     [rdi+148h], rax
0x18000889f  test    rax, rax
0x1800088a2  jz      loc_180008E64
0x1800088a8  mov     [rdi+150h], r13
0x1800088af  lea     rax, ??_7CKsOutputPin@@6BCUnknown@@@; const CKsOutputPin::`vftable'{for `CUnknown'}
0x1800088b6  mov     [rdi+160h], r13d
0x1800088bd  lea     r14, [rdi+180h]
0x1800088c4  mov     [rdi], rax
0x1800088c7  lea     rcx, [rdi+2F8h]; lpCriticalSection
0x1800088ce  mov     [rdi+248h], r12d
0x1800088d5  lea     rax, ??_7CKsOutputPin2@@6BIPin@@@; const CKsOutputPin2::`vftable'{for `IPin'}
0x1800088dc  mov     [rdi+18h], rax
0x1800088e0  lea     r12, [rdi+2A8h]
0x1800088e7  mov     [rdi+208h], r13
0x1800088ee  lea     rax, ??_7CKsOutputPin2@@6BIQualityControl@@@; const CKsOutputPin2::`vftable'{for `IQualityControl'}
0x1800088f5  mov     [rdi+20h], rax
0x1800088f9  lea     rax, ??_7CKsOutputPin2@@6BCBaseStreamControl@@@; const CKsOutputPin2::`vftable'{for `CBaseStreamControl'}
0x180008900  mov     [rdi+0E8h], rax
0x180008907  lea     rax, ??_7CKsOutputPin@@6BIMediaSeeking@@@; const CKsOutputPin::`vftable'{for `IMediaSeeking'}
0x18000890e  mov     [rdi+170h], rax
0x180008915  lea     rax, ??_7CKsOutputPin2@@6BIKsObject@@@; const CKsOutputPin2::`vftable'{for `IKsObject'}
0x18000891c  mov     [rdi+178h], rax
0x180008923  lea     rax, ??_7CKsOutputPin@@6BIKsPinEx@@@; const CKsOutputPin::`vftable'{for `IKsPinEx'}
0x18000892a  mov     [r14], rax
0x18000892d  lea     rax, ??_7CKsOutputPin@@6BIKsPinPipe@@@; const CKsOutputPin::`vftable'{for `IKsPinPipe'}
0x180008934  mov     [rdi+188h], rax
0x18000893b  lea     rax, ??_7CKsOutputPin@@6BISpecifyPropertyPages@@@; const CKsOutputPin::`vftable'{for `ISpecifyPropertyPages'}
0x180008942  mov     [rdi+190h], rax
0x180008949  lea     rax, ??_7CKsOutputPin@@6BIStreamBuilder@@@; const CKsOutputPin::`vftable'{for `IStreamBuilder'}
0x180008950  mov     [rdi+198h], rax
0x180008957  lea     rax, ??_7CKsOutputPin2@@6BIKsPropertySet@@@; const CKsOutputPin2::`vftable'{for `IKsPropertySet'}
0x18000895e  mov     [rdi+1A0h], rax
0x180008965  lea     rax, ??_7CKsOutputPin2@@6BIKsPinFactory@@@; const CKsOutputPin2::`vftable'{for `IKsPinFactory'}
0x18000896c  mov     [rdi+1A8h], rax
0x180008973  lea     rax, ??_7CKsOutputPin@@6BIAMBufferNegotiation@@@; const CKsOutputPin::`vftable'{for `IAMBufferNegotiation'}
0x18000897a  mov     [rdi+1B0h], rax
0x180008981  lea     rax, ??_7CKsOutputPin@@6BIAMStreamConfig@@@; const CKsOutputPin::`vftable'{for `IAMStreamConfig'}
0x180008988  mov     [rdi+1B8h], rax
0x18000898f  lea     rax, ??_7CKsOutputPin2@@6BIKsControl@@@; const CKsOutputPin2::`vftable'{for `IKsControl'}
0x180008996  mov     [rdi+1C0h], rax
0x18000899d  lea     rax, ??_7CKsOutputPin2@@6BIKsAggregateControl@@@; const CKsOutputPin2::`vftable'{for `IKsAggregateControl'}
0x1800089a4  mov     [rdi+1C8h], rax
0x1800089ab  lea     rax, ??_7CKsOutputPin@@6BIMemAllocatorNotifyCallbackTemp@@@; const CKsOutputPin::`vftable'{for `IMemAllocatorNotifyCallbackTemp'}
0x1800089b2  mov     [rdi+1D0h], rax
0x1800089b9  lea     rax, ??_7CKsOutputPin2@@6BIKsPinPrivate@@@; const CKsOutputPin2::`vftable'{for `IKsPinPrivate'}
0x1800089c0  mov     [rdi+1D8h], rax
0x1800089c7  lea     rax, ??_7CKsOutputPin@@6BIKsD3DPin@@@; const CKsOutputPin::`vftable'{for `IKsD3DPin'}
0x1800089ce  mov     [rdi+1E0h], rax
0x1800089d5  mov     [rdi+218h], r13
0x1800089dc  mov     [rdi+220h], r13
0x1800089e3  mov     [rdi+228h], r13d
0x1800089ea  mov     [rdi+230h], r13
0x1800089f1  mov     [rdi+238h], r13
0x1800089f8  mov     [rdi+240h], r13
0x1800089ff  mov     qword ptr [rdi+288h], 1
0x180008a0a  mov     [rdi+290h], r13d
0x180008a11  mov     [rdi+298h], r13
0x180008a18  mov     [rdi+2A0h], r13d
0x180008a1f  mov     [r12], r13
0x180008a23  mov     [r12+8], r13
0x180008a28  mov     [r12+10h], r13d
0x180008a2d  mov     qword ptr [r12+18h], 0Ah
0x180008a36  mov     [r12+20h], r13
0x180008a3b  mov     [rdi+2D0h], r13
0x180008a42  mov     [rdi+2D8h], r13
0x180008a49  mov     [rdi+2E0h], r13d
0x180008a50  mov     qword ptr [rdi+2E8h], 0Ah
0x180008a5b  mov     [rdi+2F0h], r13
0x180008a62  call    cs:__imp_InitializeCriticalSection
0x180008a69  nop     dword ptr [rax+rax+00h]
0x180008a6e  mov     [rdi+320h], r13
0x180008a75  mov     [rdi+328h], r13
0x180008a7c  mov     [rdi+330h], r13d
0x180008a83  mov     qword ptr [rdi+338h], 0Ah
0x180008a8e  mov     [rdi+340h], r13
0x180008a95  mov     [rdi+348h], r13d
0x180008a9c  mov     dword ptr [rdi+34Ch], 1
0x180008aa6  mov     [rdi+350h], r13
0x180008aad  mov     [rdi+358h], r13
0x180008ab4  mov     [rdi+368h], r13
0x180008abb  mov     [rdi+394h], r13d
0x180008ac2  mov     [rdi+3A8h], r13
0x180008ac9  mov     [rdi+3B0h], r13
0x180008ad0  mov     [rdi+3B8h], r13
0x180008ad7  mov     [rdi+3C0h], r13
0x180008ade  mov     eax, [rbp+0F0h+arg_38]
0x180008ae4  xor     ebx, ebx
0x180008ae6  mov     [rdi+3C8h], r13
0x180008aed  mov     [rdi+3D0h], r13d
0x180008af4  mov     [rdi+3D8h], r13
0x180008afb  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180008b02  mov     dword ptr [rdi+3F8h], 0FFFFFFFFh
0x180008b0c  mov     [rdi+400h], r13
0x180008b13  movups  xmmword ptr [rdi+3E8h], xmm0
0x180008b1a  mov     [rdi+408h], r13d
0x180008b21  mov     [rdi+410h], rbx
0x180008b28  xorps   xmm0, xmm0
0x180008b2b  mov     [rdi+418h], eax
0x180008b31  xor     eax, eax
0x180008b33  mov     dword ptr [rdi+41Ch], 1
0x180008b3d  mov     [rdi+388h], rax
0x180008b44  mov     [rdi+390h], eax
0x180008b4a  movups  xmmword ptr [rdi+370h], xmm0
0x180008b51  mov     [rdi+380h], rax
0x180008b58  cmp     [rsi], eax
0x180008b5a  jl      loc_180008D1B
0x180008b60  xor     r9d, r9d; lpName
0x180008b63  xor     r8d, r8d; bInitialState
0x180008b66  xor     edx, edx; bManualReset
0x180008b68  xor     ecx, ecx; lpEventAttributes
0x180008b6a  call    cs:__imp_CreateEventW
0x180008b71  nop     dword ptr [rax+rax+00h]
0x180008b76  mov     [rdi+298h], rax
0x180008b7d  test    rax, rax
0x180008b80  jz      loc_180008E3C
0x180008b86  mov     eax, [rdi+248h]
0x180008b8c  mov     rsi, [r15+170h]
0x180008b93  movups  xmm0, xmmword ptr cs:_GUID_8c134960_51ad_11cf_878a_94f801c10000.Data1
0x180008b9a  mov     [rbp+0F0h+var_170], eax
0x180008b9d  mov     [rsp+1F0h+BytesReturned], ebx
0x180008ba1  lea     rax, [rsi-1]
0x180008ba5  mov     [rsp+1F0h+var_178], 7
0x180008bad  mov     [rsp+1F0h+var_174], 1
0x180008bb5  mov     [rbp+0F0h+var_16C], ebx
0x180008bb8  movups  [rsp+1F0h+InBuffer], xmm0
0x180008bbd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180008bc1  ja      loc_180008E95
0x180008bc7  xorps   xmm0, xmm0
0x180008bca  xor     r9d, r9d; lpName
0x180008bcd  xor     r8d, r8d; bInitialState
0x180008bd0  mov     edx, 1; bManualReset
0x180008bd5  xor     ecx, ecx; lpEventAttributes
0x180008bd7  movups  xmmword ptr [rbp+0F0h+Overlapped.Internal], xmm0
0x180008bdb  movups  xmmword ptr [rbp+0F0h+Overlapped.10h], xmm0
0x180008bdf  call    cs:__imp_CreateEventW
0x180008be6  nop     dword ptr [rax+rax+00h]
0x180008beb  mov     [rbp+0F0h+Overlapped.hEvent], rax
0x180008bef  test    rax, rax
0x180008bf2  jz      loc_180008DCB
0x180008bf8  lea     rcx, [rbp+0F0h+Overlapped]
0x180008bfc  mov     r9d, 20h ; ' '; nInBufferSize
0x180008c02  mov     [rsp+1F0h+lpOverlapped], rcx; lpOverlapped
0x180008c07  lea     rax, [rdi+24Ch]
0x180008c0e  lea     rcx, [rsp+1F0h+BytesReturned]
0x180008c13  mov     edx, 2F0003h; dwIoControlCode
0x180008c18  mov     [rsp+1F0h+lpBytesReturned], rcx; lpBytesReturned
0x180008c1d  lea     r8, [rsp+1F0h+InBuffer]; lpInBuffer
0x180008c22  mov     [rsp+1F0h+nOutBufferSize], 4; nOutBufferSize
0x180008c2a  mov     rcx, rsi; hDevice
0x180008c2d  mov     [rsp+1F0h+lpOutBuffer], rax; lpOutBuffer
0x180008c32  call    cs:__imp_DeviceIoControl
0x180008c39  nop     dword ptr [rax+rax+00h]
0x180008c3e  test    eax, eax
0x180008c40  jnz     loc_180008D49
0x180008c46  call    cs:__imp_GetLastError
0x180008c4d  nop     dword ptr [rax+rax+00h]
0x180008c52  mov     ebx, eax
0x180008c54  test    eax, eax
0x180008c56  jle     short loc_180008C61
0x180008c58  movzx   ebx, ax
0x180008c5b  or      ebx, 80070000h
0x180008c61  cmp     ebx, 800703E5h
0x180008c67  jz      loc_180008DEF
0x180008c6d  mov     rcx, [rbp+0F0h+Overlapped.hEvent]; hObject
0x180008c71  call    cs:__imp_CloseHandle
0x180008c78  nop     dword ptr [rax+rax+00h]
0x180008c7d  mov     rsi, [rsp+1F0h+var_1A0]
0x180008c82  mov     [rsi], ebx
0x180008c84  mov     eax, [rdi+24Ch]
0x180008c8a  mov     [rdi+250h], eax
0x180008c90  test    eax, eax
0x180008c92  jz      loc_180008E9F
0x180008c98  mov     r9d, dword ptr [rsp+1F0h+phkResult]
0x180008c9d  lea     r8, aPinfactoryUInt; "PinFactory\\%u\\Interfaces"
0x180008ca4  mov     edx, 40h ; '@'; unsigned __int64
0x180008ca9  lea     rcx, [rbp+0F0h+SubKey]; unsigned __int16 *
0x180008cad  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008cb2  mov     rcx, [r15+1F8h]; hKey
0x180008cb9  lea     rax, [rsp+1F0h+phkResult]
0x180008cbe  xor     ebx, ebx
0x180008cc0  mov     [rsp+1F0h+lpOutBuffer], rax; phkResult
0x180008cc5  test    rdi, rdi
0x180008cc8  mov     [rsp+1F0h+phkResult], rbx
0x180008ccd  mov     r9d, 20019h; samDesired
0x180008cd3  mov     [rsp+1F0h+hKey], rbx
0x180008cd8  cmovz   r14, rbx
0x180008cdc  lea     rdx, [rbp+0F0h+SubKey]; lpSubKey
0x180008ce0  xor     r8d, r8d; ulOptions
0x180008ce3  call    cs:__imp_RegOpenKeyExW
0x180008cea  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
