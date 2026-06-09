# CKsProxy::Load(IPropertyBag *,IErrorLog *)

- ea: `0x1000cf60`
- end: `0x1000d72c`
- name: `?Load@CKsProxy@@UAGJPAUIPropertyBag@@PAUIErrorLog@@@Z`
- size: `1996`
- prototype: `int(CKsProxy *__hidden this, struct IPropertyBag *, struct IErrorLog *)`
- caller_count: `0`
- callee_count: `25`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1000647a`
- `0x100064e5`
- `0x10007823`
- `0x10009f60`
- `0x1000b1eb`
- `0x1000cf60`
- `0x1000f089`
- `0x1000f5b7`
- `0x1000f5dc`
- `0x1001f2b0`
- `0x1001f3b0`
- `0x10020ce6`
- `0x10020e70`
- `0x10021163`
- `0x1002c653`
- `0x1002d510`
- `0x1002e852`
- `0x1002e886`
- `0x100373a0`
- `0x10037431`
- `0x100375df`
- `0x1003a6f2`
- `0x1003aba0`
- `0x1003abb4`
- `0x1003af9d`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1000d22f`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1000d22f`
- `KERNEL32!ProcessIdToSessionId` at `0x1000d253`
- `KERNEL32!ProcessIdToSessionId` at `0x1000d253`
- `KERNEL32!GetLastError` at `0x1000d192`
- `KERNEL32!GetLastError` at `0x1000d29c`
- `KERNEL32!GetLastError` at `0x1000d4be`
- `KERNEL32!GetLastError` at `0x1000d4db`
- `KERNEL32!GetLastError` at `0x1000d192`
- `KERNEL32!GetLastError` at `0x1000d29c`
- `KERNEL32!GetLastError` at `0x1000d4be`
- `KERNEL32!GetLastError` at `0x1000d4db`
- `KERNEL32!CloseHandle` at `0x1000d59c`
- `KERNEL32!CloseHandle` at `0x1000d59c`
- `KERNEL32!GetCurrentProcessId` at `0x1000d24c`
- `KERNEL32!GetCurrentProcessId` at `0x1000d24c`
- `KERNEL32!CreateFileW` at `0x1000d4a3`
- `KERNEL32!CreateFileW` at `0x1000d4a3`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1000d3f0`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1000d3f0`
- `KERNEL32!GetModuleFileNameW` at `0x1000d1f2`
- `KERNEL32!GetModuleFileNameW` at `0x1000d1f2`
- `KERNEL32!GetSystemTime` at `0x1000d395`
- `KERNEL32!GetSystemTime` at `0x1000d6e7`
- `KERNEL32!GetSystemTime` at `0x1000d395`
- `KERNEL32!GetSystemTime` at `0x1000d6e7`
- `ADVAPI32!RegQueryValueExW` at `0x1000d0fd`
- `ADVAPI32!RegQueryValueExW` at `0x1000d525`
- `ADVAPI32!RegQueryValueExW` at `0x1000d0fd`
- `ADVAPI32!RegQueryValueExW` at `0x1000d525`
- `ADVAPI32!RegCloseKey` at `0x1000d113`
- `ADVAPI32!RegCloseKey` at `0x1000d113`
- `OLEAUT32!__imp__VariantInit@4` at `0x1000cfeb`
- `OLEAUT32!__imp__VariantInit@4` at `0x1000d04a`
- `OLEAUT32!__imp__VariantInit@4` at `0x1000cfeb`
- `OLEAUT32!__imp__VariantInit@4` at `0x1000d04a`
- `OLEAUT32!__imp__VariantClear@4` at `0x1000d03f`
- `OLEAUT32!__imp__VariantClear@4` at `0x1000d509`
- `OLEAUT32!__imp__VariantClear@4` at `0x1000d6a7`
- `OLEAUT32!__imp__VariantClear@4` at `0x1000d03f`
- `OLEAUT32!__imp__VariantClear@4` at `0x1000d509`
- `OLEAUT32!__imp__VariantClear@4` at `0x1000d6a7`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1000d47d`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1000d47d`
- `SETUPAPI!SetupDiOpenDeviceInterfaceRegKey` at `0x1000d0c2`
- `SETUPAPI!SetupDiOpenDeviceInterfaceRegKey` at `0x1000d153`
- `SETUPAPI!SetupDiOpenDeviceInterfaceRegKey` at `0x1000d0c2`
- `SETUPAPI!SetupDiOpenDeviceInterfaceRegKey` at `0x1000d153`
- `SETUPAPI!SetupDiGetDeviceInterfaceAlias` at `0x1000d139`
- `SETUPAPI!SetupDiGetDeviceInterfaceAlias` at `0x1000d139`
- `SETUPAPI!SetupDiCreateDeviceInfoListExW` at `0x1000d078`
- `SETUPAPI!SetupDiCreateDeviceInfoListExW` at `0x1000d078`
- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x1000d0a4`
- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x1000d0a4`

## string_xrefs

- `0x1000cfbe`: `DevicePath`
- `0x1000d0f7`: `InterfaceLink`

## pseudocode

```c
int __stdcall CKsProxy::Load(CKsProxy *this, struct IPropertyBag *a2, struct IErrorLog *a3)
{
  IPropertyBag_vtbl *v3; // eax
  signed int PinInstances; // esi
  IReferenceClock *p_m_IoEvents; // eax
  void **m_IoEvents; // ecx
  CCritSec *m_pLock; // esi
  IUnknown *DeviceInfoList; // edi
  HKEY v9; // eax
  CBaseList::CNode *v10; // eax
  bool v11; // zf
  signed int v12; // eax
  DWORD CurrentProcessId; // eax
  signed int v14; // eax
  char v15; // cl
  void **v16; // ecx
  char *v17; // edx
  _KSSTREAM_SEGMENT **v18; // eax
  _KSSTREAM_SEGMENT **m_IoSegments; // edi
  _KSSTREAM_SEGMENT **v20; // ecx
  _KSSTREAM_SEGMENT **v21; // edi
  IAMFilterMiscFlags *v22; // ecx
  CBaseList::CNode **p_m_pLast; // eax
  signed int v24; // eax
  signed int LastError; // eax
  void *v26; // esi
  IBaseFilter *v27; // eax
  IBaseFilter *v28; // eax
  IBaseFilter *v29; // eax
  IReferenceClock_vtbl *v30; // ecx
  void *v32; // [esp+28h] [ebp-2B0h]
  CKsProxy *v33; // [esp+28h] [ebp-2B0h]
  int *v34; // [esp+2Ch] [ebp-2ACh]
  int v35; // [esp+2Ch] [ebp-2ACh]
  DWORD pSessionId; // [esp+34h] [ebp-2A4h] BYREF
  CKsProxy lpFileName; // [esp+38h] [ebp-2A0h] BYREF

  *(_WORD *)lpFileName.m_clsid.Data4 = 8;
  lpFileName.m_cRef = (volatile int)a2;
  dword_1003D2F4 = 1;
  dword_1003D2FC = 1;
  v3 = a2->__vftable;
  lpFileName.m_State = State_Stopped;
  dword_1003D2F8 = 4096;
  PinInstances = ((int (__thiscall *)(HRESULT (__stdcall *)(IPropertyBag *, const wchar_t *, tagVARIANT *, IErrorLog *), struct IPropertyBag *, const wchar_t *, unsigned __int8 *, struct IErrorLog *))v3->Read)(
                   v3->Read,
                   a2,
                   L"DevicePath",
                   lpFileName.m_clsid.Data4,
                   a3);
  p_m_IoEvents = (IReferenceClock *)&this->m_IoEvents;
  pSessionId = PinInstances;
  lpFileName.m_pClock = (IReferenceClock *)&this->m_IoEvents;
  if ( PinInstances >= 0 )
  {
    VariantInit((VARIANTARG *)&lpFileName.m_tStart);
    this->m_IoThreadCriticalSection.DebugInfo = (_RTL_CRITICAL_SECTION_DEBUG *)lpFileName.m_pLock;
    LOWORD(lpFileName.m_tStart.m_time) = 8;
    (*(void (__thiscall **)(_DWORD, volatile int, const wchar_t *, CRefTime *, struct IErrorLog *))(*(_DWORD *)lpFileName.m_cRef
                                                                                                  + 12))(
      *(_DWORD *)(*(_DWORD *)lpFileName.m_cRef + 12),
      lpFileName.m_cRef,
      L"FriendlyName",
      &lpFileName.m_tStart,
      a3);
    m_IoEvents = this->m_IoEvents;
    if ( m_IoEvents )
      CAggregateDShowKsProxyTelemetry::AddSymlinkAndFriendlyName(
        (CAggregateDShowKsProxyTelemetry *)m_IoEvents,
        &this->m_IoThreadCriticalSection.DebugInfo->Type,
        (const unsigned __int16 *)lpFileName.m_clsid.Data1);
    VariantClear((VARIANTARG *)&lpFileName.m_tStart);
    VariantInit((VARIANTARG *)&lpFileName.m_tStart);
    m_pLock = lpFileName.m_pLock;
    lpFileName.CBaseFilter::CUnknown::INonDelegatingUnknown::__vftable = (CKsProxy_vtbl *)lpFileName.m_pLock;
    (&lpFileName.m_pClock)[1] = (IReferenceClock *)wcslen((const unsigned __int16 *)lpFileName.m_pLock);
    DeviceInfoList = (IUnknown *)SetupDiCreateDeviceInfoListExW(0, 0, 0, 0);
    lpFileName.m_pUnknown = DeviceInfoList;
    if ( DeviceInfoList == (IUnknown *)-1 )
    {
      LastError = GetLastError();
      v22 = &this->IAMFilterMiscFlags;
      PinInstances = (unsigned __int16)LastError | 0x80070000;
      lpFileName.m_pUnknown = &this->IAMFilterMiscFlags;
      if ( LastError <= 0 )
        PinInstances = LastError;
      p_m_pLast = &this->m_MarshalerList.m_pLast;
      lpFileName.CBaseFilter::IAMovieSetup::IUnknown::__vftable = (IAMovieSetup_vtbl *)&this->m_MarshalerList.m_pLast;
      if ( PinInstances >= 0 )
        goto LABEL_52;
      goto LABEL_59;
    }
    lpFileName.IKsPropertySet::IUnknown::__vftable = (IKsPropertySet_vtbl *)28;
    if ( SetupDiOpenDeviceInterfaceW(
           DeviceInfoList,
           (PCWSTR)m_pLock,
           0,
           (PSP_DEVICE_INTERFACE_DATA)&lpFileName.IKsPropertySet) )
    {
      v9 = SetupDiOpenDeviceInterfaceRegKey(
             DeviceInfoList,
             (PSP_DEVICE_INTERFACE_DATA)&lpFileName.IKsPropertySet,
             0,
             0x20019u);
      this->m_MarshalerList.m_pLast = (CBaseList::CNode *)v9;
      if ( v9 == (HKEY)-1 )
      {
        this->m_MarshalerList.m_pLast = 0;
      }
      else
      {
        lpFileName.CBaseFilter::IBaseFilter::IMediaFilter::IPersist::IUnknown::__vftable = (IBaseFilter_vtbl *)16;
        if ( !RegQueryValueExW(
                v9,
                L"InterfaceLink",
                0,
                0,
                (LPBYTE)&lpFileName.m_pGraph,
                (LPDWORD)&lpFileName.IBaseFilter)
          && lpFileName.CBaseFilter::IBaseFilter::IMediaFilter::IPersist::IUnknown::__vftable == (IBaseFilter_vtbl *)16 )
        {
          RegCloseKey((HKEY)this->m_MarshalerList.m_pLast);
          this->m_MarshalerList.m_pLast = 0;
          if ( SetupDiGetDeviceInterfaceAlias(
                 DeviceInfoList,
                 (PSP_DEVICE_INTERFACE_DATA)&lpFileName.IKsPropertySet,
                 (const GUID *)&lpFileName.m_pGraph,
                 (PSP_DEVICE_INTERFACE_DATA)&lpFileName.IKsPropertySet) )
          {
            v10 = (CBaseList::CNode *)SetupDiOpenDeviceInterfaceRegKey(
                                        DeviceInfoList,
                                        (PSP_DEVICE_INTERFACE_DATA)&lpFileName.IKsPropertySet,
                                        0,
                                        0x20019u);
            this->m_MarshalerList.m_pLast = v10;
            if ( v10 == (CBaseList::CNode *)-1 )
              this->m_MarshalerList.m_pLast = 0;
          }
        }
        this->m_IoThreadCriticalSection.LockCount = (int)lpFileName.IKsClockPropertySet::IUnknown::__vftable;
        this->m_IoThreadCriticalSection.RecursionCount = (int)lpFileName.IAMFilterMiscFlags::IUnknown::__vftable;
        this->m_IoThreadCriticalSection.OwningThread = lpFileName.IKsControl::IUnknown::__vftable;
        this->m_IoThreadCriticalSection.LockSemaphore = lpFileName.IKsTopology::IUnknown::__vftable;
      }
    }
    v11 = this->m_MarshalerList.m_pLast == 0;
    lpFileName.CBaseFilter::IAMovieSetup::IUnknown::__vftable = (IAMovieSetup_vtbl *)&this->m_MarshalerList.m_pLast;
    if ( v11 )
    {
      v12 = GetLastError();
      PinInstances = (unsigned __int16)v12 | 0x80070000;
      if ( v12 <= 0 )
        PinInstances = v12;
      if ( PinInstances < 0 )
        goto LABEL_50;
    }
    PinInstances = IsVideoCameraFilter(&lpFileName.m_State, v32, v34);
    if ( PinInstances < 0 || lpFileName.m_State == State_Stopped )
    {
LABEL_50:
      SetupDiDestroyDeviceInfoList(lpFileName.m_pUnknown);
      if ( PinInstances >= 0 )
      {
        lpFileName.m_pUnknown = &this->IAMFilterMiscFlags;
        this->IAMFilterMiscFlags::IUnknown::__vftable = (IAMFilterMiscFlags_vtbl *)CreateFileW(
                                                                                     (LPCWSTR)lpFileName.CBaseFilter::CUnknown::INonDelegatingUnknown::__vftable,
                                                                                     0xC0000000,
                                                                                     0,
                                                                                     0,
                                                                                     3u,
                                                                                     0x40000080u,
                                                                                     0);
        v22 = &this->IAMFilterMiscFlags;
        p_m_pLast = &this->m_MarshalerList.m_pLast;
LABEL_52:
        if ( v22->__vftable == (IAMFilterMiscFlags_vtbl *)-1 )
        {
          v22->__vftable = 0;
          v24 = GetLastError();
          PinInstances = (unsigned __int16)v24 | 0x80070000;
          if ( v24 <= 0 )
            PinInstances = v24;
          pSessionId = PinInstances;
        }
        else
        {
          if ( (RegQueryValueExW((HKEY)*p_m_pLast, L"FilterData", 0, 0, 0, (LPDWORD)&lpFileName.IBaseFilter)
             || !lpFileName.CBaseFilter::IBaseFilter::IMediaFilter::IPersist::IUnknown::__vftable)
            && KsOpenDefaultDevice(&_GUID_3c0d501a_140b_11d1_b40f_00a0c9223196, -1073741824, (int)&pSessionId) >= 0 )
          {
            lpFileName.CBaseFilter::CUnknown::INonDelegatingUnknown::__vftable = 0;
            *(GUID *)&lpFileName.m_pGraph = _GUID_3c0d501b_140b_11d1_b40f_00a0c9223196;
            v26 = (void *)pSessionId;
            lpFileName.CPersistStream::IPersistStream::IPersist::IUnknown::__vftable = 0;
            lpFileName.mPS_dwFileVersion = 2;
            KsSynchronousDeviceControl(
              (HANDLE)pSessionId,
              0x2F0003u,
              &lpFileName.m_pGraph,
              0x18u,
              lpFileName.m_pLock,
              2 * (int)(&lpFileName.m_pClock)[1] + 2,
              (LPDWORD)&lpFileName);
            if ( v26 )
              CloseHandle(v26);
          }
          v27 = &this->IBaseFilter;
          if ( this == (CKsProxy *)96 )
            v27 = 0;
          AggregateMarshalers((HKEY)lpFileName.QueryInterface, L"Interfaces", (int)&this->IReferenceClock, (int)v27);
          if ( CKsProxy::QueryTopologyItems(&lpFileName, (unsigned int)v32, (struct KSMULTIPLE_ITEM **)v34) >= 0 )
          {
            v28 = &this->IBaseFilter;
            if ( this == (CKsProxy *)96 )
              v28 = 0;
            AggregateTopology(&this->IReferenceClock, v28);
            operator delete[](lpFileName.CBaseFilter::CUnknown::INonDelegatingUnknown::__vftable);
          }
          v29 = 0;
          if ( this != (CKsProxy *)96 )
            v29 = &this->IBaseFilter;
          AggregateSets(
            lpFileName.m_pUnknown->CBaseFilter::CUnknown::__vftable,
            lpFileName.QueryInterface,
            &this->IReferenceClock,
            v29);
          (**(void (__thiscall ***)(_DWORD, volatile int, GUID *, int *))lpFileName.m_cRef)(
            **(_DWORD **)lpFileName.m_cRef,
            lpFileName.m_cRef,
            &IID_IPersistStream,
            &this->m_MarshalerList.m_Count);
          PinInstances = CKsProxy::GeneratePinInstances(v33, v35);
          pSessionId = PinInstances;
          if ( PinInstances >= 0 )
          {
            lpFileName.m_cRef = 0;
            lpFileName.m_pGraph = (IFilterGraph *)-1968178535;
            lpFileName.m_pSink = (IMediaEventSink *)dword_1000382C[1];
            *(_QWORD *)&lpFileName.m_PinVersion = *(_QWORD *)&dword_1000382C[2];
            lpFileName.CPersistStream::IPersistStream::IPersist::IUnknown::__vftable = 0;
            lpFileName.mPS_dwFileVersion = 1;
            if ( KsSynchronousDeviceControl(
                   lpFileName.m_pUnknown->CBaseFilter::CUnknown::__vftable,
                   0x2F0003u,
                   &lpFileName.m_pGraph,
                   0x18u,
                   &this->m_IoFreeSlotSemaphore,
                   4u,
                   (LPDWORD)&lpFileName.m_cRef) < 0
              || lpFileName.m_cRef != 4 )
            {
              this->m_IoFreeSlotSemaphore = 0;
            }
            PinInstances = pSessionId;
          }
        }
        VariantClear((VARIANTARG *)&lpFileName.m_tStart);
        p_m_IoEvents = lpFileName.m_pClock;
        goto LABEL_80;
      }
LABEL_59:
      VariantClear((VARIANTARG *)&lpFileName.m_tStart);
      return PinInstances;
    }
    wil::com_ptr_t<IKsProxyCameraAccessHandler,wil::err_returncode_policy>::reset(&this->m_ActiveIoEventCount);
    GetModuleFileNameW(0, (LPWSTR)&lpFileName.IKsNotifyEvent, 0x104u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *(_DWORD *)&this[-1].m_InterfaceClassGuid.Data4[4],
        (int)&lpFileName.IKsNotifyEvent);
    if ( _wcsstr((const wchar_t *)&lpFileName.IKsNotifyEvent, L"RealSenseDCM") )
    {
      pSessionId = 0;
      CurrentProcessId = GetCurrentProcessId();
      if ( ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          WPP_SF_SD(
            0x1Au,
            &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids,
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            *(_DWORD *)&this[-1].m_InterfaceClassGuid.Data4[4],
            pSessionId);
        if ( !pSessionId )
          goto LABEL_41;
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        v14 = GetLastError();
        v15 = v14;
        if ( v14 <= 0 )
          v15 = v14;
        WPP_SF_SD(
          0x1Bu,
          &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids,
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *(_DWORD *)&this[-1].m_InterfaceClassGuid.Data4[4],
          v15);
      }
    }
    wil::com_ptr_t<IKsProxyCameraAccessHandler,wil::err_returncode_policy>::reset(&this->m_ActiveIoEventCount);
    PinInstances = KsProxyCreateCameraAccessHandler(&this->m_ActiveIoEventCount);
    pSessionId = PinInstances;
    if ( PinInstances >= 0 )
    {
      PinInstances = CKsProxy::InitializeCameraAccessDeniedThread((CKsProxy *)((char *)this - 96));
      pSessionId = PinInstances;
      if ( PinInstances >= 0 )
      {
        PinInstances = (*(int (__thiscall **)(_DWORD, int, CBasePin *))(*(_DWORD *)this->m_ActiveIoEventCount + 12))(
                         *(_DWORD *)(*(_DWORD *)this->m_ActiveIoEventCount + 12),
                         this->m_ActiveIoEventCount,
                         this->m_PinClockSource);
        pSessionId = PinInstances;
        if ( PinInstances >= 0 )
        {
LABEL_41:
          v17 = (char *)operator new(0x20u, &std::nothrow);
          v18 = 0;
          pSessionId = (DWORD)v17;
          if ( v17 )
          {
            memset(v17, 0, 0x20u);
            InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v17 + 4), 0, 0);
            v18 = (_KSSTREAM_SEGMENT **)pSessionId;
            *(_BYTE *)(pSessionId + 28) = 0;
          }
          m_IoSegments = this->m_IoSegments;
          pSessionId = 0;
          this->m_IoSegments = v18;
          if ( m_IoSegments )
          {
            KsControlWnfNotify::~KsControlWnfNotify((KsControlWnfNotify *)m_IoSegments);
            operator delete(m_IoSegments, 0x20u);
          }
          wistd::unique_ptr<KsControlWnfNotify,wistd::default_delete<KsControlWnfNotify>>::~unique_ptr<KsControlWnfNotify,wistd::default_delete<KsControlWnfNotify>>(&pSessionId);
          v20 = this->m_IoSegments;
          if ( v20 )
          {
            PinInstances = KsControlWnfNotify::Initialize(
                             (KsControlWnfNotify *)v20,
                             (const unsigned __int16 *)lpFileName.CBaseFilter::CUnknown::INonDelegatingUnknown::__vftable);
            if ( PinInstances < 0 )
            {
              v21 = this->m_IoSegments;
              this->m_IoSegments = 0;
              if ( v21 )
              {
                KsControlWnfNotify::~KsControlWnfNotify((KsControlWnfNotify *)v21);
                operator delete(v21, 0x20u);
              }
            }
          }
          else
          {
            PinInstances = -2147024882;
          }
          goto LABEL_50;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          WPP_SF_SD(
            0x1Du,
            &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids,
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            *(_DWORD *)&this[-1].m_InterfaceClassGuid.Data4[4],
            PinInstances);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      WPP_SF_SD(
        0x1Cu,
        &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids,
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *(_DWORD *)&this[-1].m_InterfaceClassGuid.Data4[4],
        PinInstances);
    }
    if ( !this->m_IoEvents )
      goto LABEL_50;
    memset(&lpFileName.m_pGraph, 0, 16);
    memset(&lpFileName.mPS_fDirty, 0, 28);
    GetSystemTime((LPSYSTEMTIME)&lpFileName.mPS_fDirty);
    PinInstances = pSessionId;
    v16 = this->m_IoEvents;
    lpFileName.IMediaSeeking::IUnknown::__vftable = (IMediaSeeking_vtbl *)pSessionId;
    CAggregateDShowKsProxyTelemetry::AddData(v16, 5, &lpFileName.mPS_fDirty);
    DShowKsProxyTelemetryValue::~DShowKsProxyTelemetryValue((DShowKsProxyTelemetryValue *)&lpFileName.mPS_fDirty);
    if ( PinInstances < 0 )
      goto LABEL_50;
    goto LABEL_41;
  }
  lpFileName.m_pClock = (IReferenceClock *)&this->m_IoEvents;
LABEL_80:
  if ( p_m_IoEvents->__vftable )
  {
    memset(&lpFileName.m_pGraph, 0, 16);
    memset(&lpFileName.mPS_fDirty, 0, 28);
    GetSystemTime((LPSYSTEMTIME)&lpFileName.mPS_fDirty);
    PinInstances = pSessionId;
    v30 = lpFileName.m_pClock->CBaseFilter::__vftable;
    lpFileName.IMediaSeeking::IUnknown::__vftable = (IMediaSeeking_vtbl *)pSessionId;
    CAggregateDShowKsProxyTelemetry::AddData(v30, 1, &lpFileName.mPS_fDirty);
    DShowKsProxyTelemetryValue::~DShowKsProxyTelemetryValue((DShowKsProxyTelemetryValue *)&lpFileName.mPS_fDirty);
  }
  return PinInstances;
}

```

## disassembly

```asm
0x1000cf60  mov     edi, edi
0x1000cf62  push    ebp
0x1000cf63  mov     ebp, esp
0x1000cf65  and     esp, 0FFFFFFF8h
0x1000cf68  sub     esp, 2A4h
0x1000cf6e  mov     eax, ___security_cookie
0x1000cf73  xor     eax, esp
0x1000cf75  mov     [esp+2A4h+var_4], eax
0x1000cf7c  mov     ecx, [ebp+arg_4]
0x1000cf7f  push    ebx
0x1000cf80  push    esi; int
0x1000cf81  push    edi; this
0x1000cf82  mov     edi, [ebp+arg_8]
0x1000cf85  mov     ebx, [ebp+this]
0x1000cf88  push    8
0x1000cf8a  pop     eax
0x1000cf8b  mov     [esp+2B0h+var_270], ax
0x1000cf90  xor     eax, eax
0x1000cf92  inc     eax
0x1000cf93  mov     [esp+2B0h+BytesReturned], ecx
0x1000cf97  mov     dword_1003D2F4, eax
0x1000cf9c  mov     dword_1003D2FC, eax
0x1000cfa1  mov     eax, [ecx]
0x1000cfa3  push    edi
0x1000cfa4  mov     [esp+2B4h+var_28C], 0
0x1000cfac  mov     dword_1003D2F8, 1000h
0x1000cfb6  mov     esi, [eax+0Ch]
0x1000cfb9  lea     eax, [esp+2B4h+var_270]
0x1000cfbd  push    eax
0x1000cfbe  push    offset aDevicepath; "DevicePath"
0x1000cfc3  push    ecx
0x1000cfc4  mov     ecx, esi; this
0x1000cfc6  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000cfcc  call    esi
0x1000cfce  mov     esi, eax
0x1000cfd0  lea     eax, [ebx+110h]
0x1000cfd6  mov     [esp+2B0h+pSessionId], esi
0x1000cfda  mov     [esp+2B0h+var_288], eax
0x1000cfde  test    esi, esi
0x1000cfe0  js      loc_1000D6B3
0x1000cfe6  lea     eax, [esp+2B0h+pvarg]
0x1000cfea  push    eax; pvarg
0x1000cfeb  call    ds:__imp__VariantInit@4; VariantInit(x)
0x1000cff1  mov     eax, [esp+2B0h+DevicePath]
0x1000cff5  lea     ecx, [esp+2B0h+pvarg]
0x1000cff9  push    8
0x1000cffb  mov     [ebx+0F4h], eax
0x1000d001  pop     eax
0x1000d002  mov     word ptr [esp+2B0h+pvarg.___u0], ax
0x1000d007  mov     eax, [esp+2B0h+BytesReturned]
0x1000d00b  push    edi
0x1000d00c  push    ecx
0x1000d00d  push    offset aFriendlyname; "FriendlyName"
0x1000d012  mov     esi, [eax]
0x1000d014  push    eax
0x1000d015  mov     ecx, [esi+0Ch]; this
0x1000d018  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000d01e  call    dword ptr [esi+0Ch]
0x1000d021  mov     ecx, [ebx+110h]; this
0x1000d027  test    ecx, ecx
0x1000d029  jz      short loc_1000D03A
0x1000d02b  push    dword ptr [esp+2B0h+pvarg.___u0+8]; unsigned __int16 *
0x1000d02f  push    dword ptr [ebx+0F4h]; psz
0x1000d035  call    ?AddSymlinkAndFriendlyName@CAggregateDShowKsProxyTelemetry@@QAEXPBG0@Z; CAggregateDShowKsProxyTelemetry::AddSymlinkAndFriendlyName(ushort const *,ushort const *)
0x1000d03a  lea     eax, [esp+2B0h+pvarg]
0x1000d03e  push    eax; pvarg
0x1000d03f  call    ds:__imp__VariantClear@4; VariantClear(x)
0x1000d045  lea     eax, [esp+2B0h+pvarg]
0x1000d049  push    eax; pvarg
0x1000d04a  call    ds:__imp__VariantInit@4; VariantInit(x)
0x1000d050  mov     esi, [esp+2B0h+DevicePath]
0x1000d054  xor     edi, edi
0x1000d056  mov     ecx, esi
0x1000d058  mov     [esp+2B0h+lpFileName], esi
0x1000d05c  lea     edx, [ecx+2]
0x1000d05f  mov     ax, [ecx]
0x1000d062  add     ecx, 2
0x1000d065  cmp     ax, di
0x1000d068  jnz     short loc_1000D05F
0x1000d06a  xor     eax, eax
0x1000d06c  sub     ecx, edx
0x1000d06e  push    eax; Reserved
0x1000d06f  push    eax; MachineName
0x1000d070  push    eax; hwndParent
0x1000d071  sar     ecx, 1
0x1000d073  push    eax; ClassGuid
0x1000d074  mov     [esp+2C0h+var_284], ecx
0x1000d078  call    ds:__imp__SetupDiCreateDeviceInfoListExW@16; SetupDiCreateDeviceInfoListExW(x,x,x,x)
0x1000d07e  mov     edi, eax
0x1000d080  mov     [esp+2B0h+DeviceInfoSet], edi
0x1000d084  cmp     edi, 0FFFFFFFFh
0x1000d087  jz      loc_1000D4DB
0x1000d08d  lea     eax, [esp+2B0h+DeviceInterfaceData]
0x1000d094  mov     [esp+2B0h+DeviceInterfaceData.cbSize], 1Ch
0x1000d09f  push    eax; DeviceInterfaceData
0x1000d0a0  push    0; OpenFlags
0x1000d0a2  push    esi; DevicePath
0x1000d0a3  push    edi; DeviceInfoSet
0x1000d0a4  call    ds:__imp__SetupDiOpenDeviceInterfaceW@16; SetupDiOpenDeviceInterfaceW(x,x,x,x)
0x1000d0aa  test    eax, eax
0x1000d0ac  jz      loc_1000D183
0x1000d0b2  push    20019h; samDesired
0x1000d0b7  push    0; Reserved
0x1000d0b9  lea     eax, [esp+2B8h+DeviceInterfaceData]
0x1000d0c0  push    eax; DeviceInterfaceData
0x1000d0c1  push    edi; DeviceInfoSet
0x1000d0c2  call    ds:__imp__SetupDiOpenDeviceInterfaceRegKey@16; SetupDiOpenDeviceInterfaceRegKey(x,x,x,x)
0x1000d0c8  mov     [ebx+0C8h], eax
0x1000d0ce  cmp     eax, 0FFFFFFFFh
0x1000d0d1  jnz     short loc_1000D0E2
0x1000d0d3  mov     dword ptr [ebx+0C8h], 0
0x1000d0dd  jmp     loc_1000D183
0x1000d0e2  push    10h
0x1000d0e4  pop     esi
0x1000d0e5  lea     ecx, [esp+2B0h+cbData]
0x1000d0e9  mov     [esp+2B0h+cbData], esi
0x1000d0ed  push    ecx; lpcbData
0x1000d0ee  lea     ecx, [esp+2B4h+Data]
0x1000d0f2  push    ecx; lpData
0x1000d0f3  xor     ecx, ecx
0x1000d0f5  push    ecx; lpType
0x1000d0f6  push    ecx; lpReserved
0x1000d0f7  push    offset ValueName; "InterfaceLink"
0x1000d0fc  push    eax; hKey
0x1000d0fd  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x1000d103  test    eax, eax
0x1000d105  jnz     short loc_1000D16E
0x1000d107  cmp     [esp+2B0h+cbData], esi
0x1000d10b  jnz     short loc_1000D16E
0x1000d10d  push    dword ptr [ebx+0C8h]; hKey
0x1000d113  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x1000d119  lea     eax, [esp+2B0h+DeviceInterfaceData]
0x1000d120  mov     dword ptr [ebx+0C8h], 0
0x1000d12a  push    eax; AliasDeviceInterfaceData
0x1000d12b  lea     eax, [esp+2B4h+Data]
0x1000d12f  push    eax; AliasInterfaceClassGuid
0x1000d130  lea     eax, [esp+2B8h+DeviceInterfaceData]
0x1000d137  push    eax; DeviceInterfaceData
0x1000d138  push    edi; DeviceInfoSet
0x1000d139  call    ds:__imp__SetupDiGetDeviceInterfaceAlias@16; SetupDiGetDeviceInterfaceAlias(x,x,x,x)
0x1000d13f  test    eax, eax
0x1000d141  jz      short loc_1000D16E
0x1000d143  push    20019h; samDesired
0x1000d148  push    0; Reserved
0x1000d14a  lea     eax, [esp+2B8h+DeviceInterfaceData]
0x1000d151  push    eax; DeviceInterfaceData
0x1000d152  push    edi; DeviceInfoSet
0x1000d153  call    ds:__imp__SetupDiOpenDeviceInterfaceRegKey@16; SetupDiOpenDeviceInterfaceRegKey(x,x,x,x)
0x1000d159  mov     [ebx+0C8h], eax
0x1000d15f  cmp     eax, 0FFFFFFFFh
0x1000d162  jnz     short loc_1000D16E
0x1000d164  mov     dword ptr [ebx+0C8h], 0
0x1000d16e  lea     edi, [ebx+0F8h]
0x1000d174  lea     esi, [esp+2B0h+DeviceInterfaceData.InterfaceClassGuid]
0x1000d17b  movsd
0x1000d17c  movsd
0x1000d17d  movsd
0x1000d17e  movsd
0x1000d17f  mov     edi, [esp+2B0h+DeviceInfoSet]
0x1000d183  lea     eax, [ebx+0C8h]
0x1000d189  cmp     dword ptr [eax], 0
0x1000d18c  mov     [esp+2B0h+var_290], eax
0x1000d190  jnz     short loc_1000D1AE
0x1000d192  call    ds:__imp__GetLastError@0; GetLastError()
0x1000d198  movzx   esi, ax
0x1000d19b  or      esi, 80070000h
0x1000d1a1  test    eax, eax
0x1000d1a3  cmovle  esi, eax
0x1000d1a6  test    esi, esi
0x1000d1a8  js      loc_1000D479
0x1000d1ae  lea     eax, [esp+2B0h+var_28C]
0x1000d1b2  mov     ecx, edi
0x1000d1b4  push    eax; void *
0x1000d1b5  lea     edx, [esp+2B4h+DeviceInterfaceData]
0x1000d1bc  call    ?IsVideoCameraFilter@@YGJPAX0PAH@Z; IsVideoCameraFilter(void *,void *,int *)
0x1000d1c1  mov     esi, eax
0x1000d1c3  test    esi, esi
0x1000d1c5  js      loc_1000D479
0x1000d1cb  cmp     [esp+2B0h+var_28C], 0
0x1000d1d0  jz      loc_1000D479
0x1000d1d6  lea     edi, [ebx+118h]
0x1000d1dc  mov     ecx, edi
0x1000d1de  call    ?reset@?$com_ptr_t@UIKsProxyCameraAccessHandler@@Uerr_returncode_policy@wil@@@wil@@QAEXXZ; wil::com_ptr_t<IKsProxyCameraAccessHandler,wil::err_returncode_policy>::reset(void)
0x1000d1e3  push    104h; nSize
0x1000d1e8  lea     eax, [esp+2B4h+Filename]
0x1000d1ef  push    eax; lpFilename
0x1000d1f0  push    0; hModule
0x1000d1f2  call    ds:__imp__GetModuleFileNameW@12; GetModuleFileNameW(x,x,x)
0x1000d1f8  mov     eax, _WPP_GLOBAL_Control
0x1000d1fd  cmp     eax, offset _WPP_GLOBAL_Control
0x1000d202  jz      short loc_1000D222
0x1000d204  lea     ecx, [esp+2B0h+Filename]
0x1000d20b  mov     edx, offset _WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids
0x1000d210  push    ecx; int
0x1000d211  push    dword ptr [ebx-24h]; int
0x1000d214  push    dword ptr [eax+14h]
0x1000d217  push    dword ptr [eax+10h]; LoggerHandle
0x1000d21a  push    19h
0x1000d21c  pop     ecx
0x1000d21d  call    _WPP_SF_SS@24; WPP_SF_SS(x,x,x,x,x,x)
0x1000d222  lea     eax, [esp+2B0h+Filename]
0x1000d229  push    offset aRealsensedcm; "RealSenseDCM"
0x1000d22e  push    eax; Str
0x1000d22f  call    ds:__imp__wcsstr
0x1000d235  pop     ecx
0x1000d236  pop     ecx
0x1000d237  test    eax, eax
0x1000d239  jz      loc_1000D2CC
0x1000d23f  lea     eax, [esp+2B0h+pSessionId]
0x1000d243  mov     [esp+2B0h+pSessionId], 0
0x1000d24b  push    eax; pSessionId
0x1000d24c  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x1000d252  push    eax; dwProcessId
0x1000d253  call    ds:__imp__ProcessIdToSessionId@8; ProcessIdToSessionId(x,x)
0x1000d259  cmp     eax, 1
0x1000d25c  jnz     short loc_1000D290
0x1000d25e  mov     eax, _WPP_GLOBAL_Control
0x1000d263  cmp     eax, offset _WPP_GLOBAL_Control
0x1000d268  jz      short loc_1000D284
0x1000d26a  push    [esp+2B0h+pSessionId]; char
0x1000d26e  mov     edx, offset _WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids; MessageGuid
0x1000d273  push    dword ptr [ebx-24h]; int
0x1000d276  push    dword ptr [eax+14h]
0x1000d279  push    dword ptr [eax+10h]; LoggerHandle
0x1000d27c  push    1Ah
0x1000d27e  pop     ecx; MessageNumber
0x1000d27f  call    _WPP_SF_SD@24; WPP_SF_SD(x,x,x,x,x,x)
0x1000d284  cmp     [esp+2B0h+pSessionId], 0
0x1000d289  jnz     short loc_1000D2CC
0x1000d28b  jmp     loc_1000D3C9
0x1000d290  cmp     _WPP_GLOBAL_Control, offset _WPP_GLOBAL_Control
0x1000d29a  jz      short loc_1000D2CC
0x1000d29c  call    ds:__imp__GetLastError@0; GetLastError()
0x1000d2a2  movzx   ecx, ax
0x1000d2a5  mov     edx, offset _WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids; MessageGuid
0x1000d2aa  or      ecx, 80070000h
0x1000d2b0  test    eax, eax
0x1000d2b2  cmovle  ecx, eax
0x1000d2b5  mov     eax, _WPP_GLOBAL_Control
0x1000d2ba  push    ecx; char
0x1000d2bb  push    dword ptr [ebx-24h]; int
0x1000d2be  push    dword ptr [eax+14h]
0x1000d2c1  push    dword ptr [eax+10h]; LoggerHandle
0x1000d2c4  push    1Bh
0x1000d2c6  pop     ecx; MessageNumber
0x1000d2c7  call    _WPP_SF_SD@24; WPP_SF_SD(x,x,x,x,x,x)
0x1000d2cc  mov     ecx, edi
0x1000d2ce  call    ?reset@?$com_ptr_t@UIKsProxyCameraAccessHandler@@Uerr_returncode_policy@wil@@@wil@@QAEXXZ; wil::com_ptr_t<IKsProxyCameraAccessHandler,wil::err_returncode_policy>::reset(void)
0x1000d2d3  mov     ecx, edi
0x1000d2d5  call    _KsProxyCreateCameraAccessHandler@4; KsProxyCreateCameraAccessHandler(x)
0x1000d2da  mov     esi, eax
0x1000d2dc  mov     [esp+2B0h+pSessionId], esi
0x1000d2e0  test    esi, esi
0x1000d2e2  jns     short loc_1000D2FE
0x1000d2e4  mov     eax, _WPP_GLOBAL_Control
0x1000d2e9  cmp     eax, offset _WPP_GLOBAL_Control
0x1000d2ee  jz      short loc_1000D35D
0x1000d2f0  push    esi
0x1000d2f1  push    dword ptr [ebx-24h]
0x1000d2f4  push    dword ptr [eax+14h]
0x1000d2f7  push    dword ptr [eax+10h]
0x1000d2fa  push    1Ch
0x1000d2fc  jmp     short loc_1000D352
0x1000d2fe  lea     ecx, [ebx-60h]; this
0x1000d301  call    ?InitializeCameraAccessDeniedThread@CKsProxy@@AAEJXZ; CKsProxy::InitializeCameraAccessDeniedThread(void)
0x1000d306  mov     esi, eax
0x1000d308  mov     [esp+2B0h+pSessionId], eax
0x1000d30c  test    esi, esi
0x1000d30e  js      short loc_1000D35D
0x1000d310  mov     ecx, [ebx+118h]
0x1000d316  push    dword ptr [ebx+11Ch]
0x1000d31c  push    ecx
0x1000d31d  mov     eax, [ecx]
0x1000d31f  mov     esi, [eax+0Ch]
0x1000d322  mov     ecx, esi; this
0x1000d324  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000d32a  call    esi
0x1000d32c  mov     esi, eax
0x1000d32e  mov     [esp+2B0h+pSessionId], esi
0x1000d332  test    esi, esi
0x1000d334  jns     loc_1000D3C9
0x1000d33a  mov     eax, _WPP_GLOBAL_Control
0x1000d33f  cmp     eax, offset _WPP_GLOBAL_Control
0x1000d344  jz      short loc_1000D35D
0x1000d346  push    esi; char
0x1000d347  push    dword ptr [ebx-24h]; int
0x1000d34a  push    dword ptr [eax+14h]
0x1000d34d  push    dword ptr [eax+10h]; LoggerHandle
0x1000d350  push    1Dh
0x1000d352  mov     edx, offset _WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids; MessageGuid
0x1000d357  pop     ecx; MessageNumber
0x1000d358  call    _WPP_SF_SD@24; WPP_SF_SD(x,x,x,x,x,x)
0x1000d35d  xor     ecx, ecx
0x1000d35f  cmp     [ebx+110h], ecx
0x1000d365  jz      loc_1000D479
0x1000d36b  xor     eax, eax
0x1000d36d  mov     [esp+2B0h+var_234], ecx
0x1000d371  lea     edi, [esp+2B0h+Data]
0x1000d375  mov     dword ptr [esp+2B0h+var_230], ecx
0x1000d37c  stosd
  ... truncated ...
```
