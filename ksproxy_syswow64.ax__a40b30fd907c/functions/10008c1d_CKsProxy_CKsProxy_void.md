# CKsProxy::~CKsProxy(void)

- ea: `0x10008c1d`
- end: `0x1000903a`
- name: `??1CKsProxy@@UAE@XZ`
- size: `1053`
- prototype: `void __thiscall(CKsProxy *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x10008bf0`

## callees

- `0x10007630`
- `0x10007823`
- `0x10008c1d`
- `0x1000f598`
- `0x1000f5b7`
- `0x1000f5dc`
- `0x1000f70b`
- `0x10021391`
- `0x1002d510`
- `0x1002e852`
- `0x1002fe5e`
- `0x10030836`
- `0x1003a6f2`
- `0x1003aba0`

## import_xrefs

- `KERNEL32!SetEvent` at `0x10008d59`
- `KERNEL32!SetEvent` at `0x10008db6`
- `KERNEL32!SetEvent` at `0x10008f24`
- `KERNEL32!SetEvent` at `0x10008d59`
- `KERNEL32!SetEvent` at `0x10008db6`
- `KERNEL32!SetEvent` at `0x10008f24`
- `KERNEL32!WaitForSingleObjectEx` at `0x10008d71`
- `KERNEL32!WaitForSingleObjectEx` at `0x10008dca`
- `KERNEL32!WaitForSingleObjectEx` at `0x10008f33`
- `KERNEL32!WaitForSingleObjectEx` at `0x10008d71`
- `KERNEL32!WaitForSingleObjectEx` at `0x10008dca`
- `KERNEL32!WaitForSingleObjectEx` at `0x10008f33`
- `KERNEL32!CloseHandle` at `0x10008d7d`
- `KERNEL32!CloseHandle` at `0x10008e16`
- `KERNEL32!CloseHandle` at `0x10008e41`
- `KERNEL32!CloseHandle` at `0x10008e6f`
- `KERNEL32!CloseHandle` at `0x10008e86`
- `KERNEL32!CloseHandle` at `0x10008f3f`
- `KERNEL32!CloseHandle` at `0x10008f63`
- `KERNEL32!CloseHandle` at `0x10008fa5`
- `KERNEL32!CloseHandle` at `0x10008fd2`
- `KERNEL32!CloseHandle` at `0x10008d7d`
- `KERNEL32!CloseHandle` at `0x10008e16`
- `KERNEL32!CloseHandle` at `0x10008e41`
- `KERNEL32!CloseHandle` at `0x10008e6f`
- `KERNEL32!CloseHandle` at `0x10008e86`
- `KERNEL32!CloseHandle` at `0x10008f3f`
- `KERNEL32!CloseHandle` at `0x10008f63`
- `KERNEL32!CloseHandle` at `0x10008fa5`
- `KERNEL32!CloseHandle` at `0x10008fd2`
- `KERNEL32!DeleteCriticalSection` at `0x10008fb8`
- `KERNEL32!DeleteCriticalSection` at `0x10009025`
- `KERNEL32!DeleteCriticalSection` at `0x10008fb8`
- `KERNEL32!DeleteCriticalSection` at `0x10009025`
- `KERNEL32!LeaveCriticalSection` at `0x10008d60`
- `KERNEL32!LeaveCriticalSection` at `0x10008dbd`
- `KERNEL32!LeaveCriticalSection` at `0x10008d60`
- `KERNEL32!LeaveCriticalSection` at `0x10008dbd`
- `KERNEL32!EnterCriticalSection` at `0x10008d41`
- `KERNEL32!EnterCriticalSection` at `0x10008da0`
- `KERNEL32!EnterCriticalSection` at `0x10008d41`
- `KERNEL32!EnterCriticalSection` at `0x10008da0`
- `KERNEL32!GetSystemTime` at `0x10008cef`
- `KERNEL32!GetSystemTime` at `0x10008cef`
- `ADVAPI32!RegCloseKey` at `0x10008edb`
- `ADVAPI32!RegCloseKey` at `0x10008edb`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10008f06`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10008f06`

## pseudocode

```c
void __thiscall CKsProxy::~CKsProxy(CKsProxy *this)
{
  struct CAggregateDShowKsProxyTelemetry *m_pDShowKsProxyEvents; // edi
  void **m_IoEvents; // eax
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__stdcall*)(void *),&CloseHandle> > > *p_m_uhAccessDeniedWaitThreadHandle; // edi
  struct IKsProxyCameraAccessHandler *v5; // ecx
  void **v6; // eax
  CBaseList::CNode *i; // edi
  void *m_pObject; // eax
  IPersistStream *m_PersistStreamDevice; // ecx
  void **m_WaitEvents; // eax
  void **v11; // eax
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__stdcall*)(void *),&CloseHandle> > > *v12; // eax
  void *m_ptr; // [esp-4h] [ebp-44h]
  void *v14; // [esp+0h] [ebp-40h]
  struct _SYSTEMTIME SystemTime; // [esp+20h] [ebp-20h] BYREF
  int v16; // [esp+30h] [ebp-10h]
  int v17; // [esp+34h] [ebp-Ch]
  int v18; // [esp+38h] [ebp-8h]

  this->CBaseFilter::CUnknown::INonDelegatingUnknown::__vftable = (CKsProxy_vtbl *)&CKsProxy::`vftable'{for `CUnknown'};
  this->CBaseFilter::IBaseFilter::IMediaFilter::IPersist::IUnknown::__vftable = (IBaseFilter_vtbl *)&CKsProxy::`vftable'{for `IBaseFilter'};
  this->CBaseFilter::IAMovieSetup::IUnknown::__vftable = (IAMovieSetup_vtbl *)&CKsProxy::`vftable'{for `IAMovieSetup'};
  this->CPersistStream::IPersistStream::IPersist::IUnknown::__vftable = (CPersistStream_vtbl *)&CKsProxy::`vftable'{for `CPersistStream'};
  this->ISpecifyPropertyPages::IUnknown::__vftable = (ISpecifyPropertyPages_vtbl *)&CKsProxy::`vftable'{for `ISpecifyPropertyPages'};
  this->IPersistPropertyBag::IPersist::IUnknown::__vftable = (IPersistPropertyBag_vtbl *)&CKsProxy::`vftable'{for `IPersistPropertyBag'};
  this->IReferenceClock::IUnknown::__vftable = (IReferenceClock_vtbl *)&CKsProxy::`vftable'{for `IReferenceClock'};
  this->IMediaSeeking::IUnknown::__vftable = (IMediaSeeking_vtbl *)&CKsProxy::`vftable'{for `IMediaSeeking'};
  this->IKsObject::IUnknown::__vftable = (IKsObject_vtbl *)&CKsProxy::`vftable'{for `IKsObject'};
  this->IKsClock::IUnknown::__vftable = (IKsClock_vtbl *)&CKsProxy::`vftable'{for `IKsClock'};
  this->IKsPropertySet::IUnknown::__vftable = (IKsPropertySet_vtbl *)&CKsProxy::`vftable'{for `IKsPropertySet'};
  this->IKsClockPropertySet::IUnknown::__vftable = (IKsClockPropertySet_vtbl *)&CKsProxy::`vftable'{for `IKsClockPropertySet'};
  this->IAMFilterMiscFlags::IUnknown::__vftable = (IAMFilterMiscFlags_vtbl *)&CKsProxy::`vftable'{for `IAMFilterMiscFlags'};
  this->IKsControl::IUnknown::__vftable = (IKsControl_vtbl *)&CKsProxy::`vftable'{for `IKsControl'};
  this->IKsTopology::IUnknown::__vftable = (IKsTopology_vtbl *)&CKsProxy::`vftable'{for `IKsTopology'};
  this->IKsAggregateControl::IUnknown::__vftable = (IKsAggregateControl_vtbl *)&CKsProxy::`vftable'{for `IKsAggregateControl'};
  this->IAMDeviceRemoval::IUnknown::__vftable = (IAMDeviceRemoval_vtbl *)&CKsProxy::`vftable'{for `IAMDeviceRemoval'};
  this->IKsNotifyEvent::IUnknown::__vftable = (IKsNotifyEvent_vtbl *)&CKsProxy::`vftable'{for `IKsNotifyEvent'};
  ++this->m_cRef;
  if ( this->m_pDShowKsProxyEvents )
  {
    v17 = 0;
    v18 = 0;
    memset(&SystemTime, 0, sizeof(SystemTime));
    v16 = 0;
    GetSystemTime(&SystemTime);
    CAggregateDShowKsProxyTelemetry::AddData(this->m_pDShowKsProxyEvents, 4, &SystemTime);
    m_pDShowKsProxyEvents = this->m_pDShowKsProxyEvents;
    if ( m_pDShowKsProxyEvents )
      (**(void (__thiscall ***)(struct CAggregateDShowKsProxyTelemetry *, int))m_pDShowKsProxyEvents)(
        m_pDShowKsProxyEvents,
        1);
    this->m_pDShowKsProxyEvents = 0;
    DShowKsProxyTelemetryValue::~DShowKsProxyTelemetryValue((BSTR *)&SystemTime);
  }
  if ( this->m_IoThreadHandle )
  {
    EnterCriticalSection(&this->m_IoThreadCriticalSection);
    m_IoEvents = this->m_IoEvents;
    this->m_IoThreadShutdown = 1;
    SetEvent(*m_IoEvents);
    LeaveCriticalSection(&this->m_IoThreadCriticalSection);
    WaitForSingleObjectEx(this->m_IoThreadHandle, 0xFFFFFFFF, 0);
    CloseHandle(this->m_IoThreadHandle);
    this->m_IoThreadHandle = 0;
  }
  p_m_uhAccessDeniedWaitThreadHandle = &this->m_uhAccessDeniedWaitThreadHandle;
  if ( this->m_uhAccessDeniedWaitThreadHandle.m_ptr && p_m_uhAccessDeniedWaitThreadHandle->m_ptr != (void *)-1 )
  {
    EnterCriticalSection(&this->m_IoThreadCriticalSection);
    m_ptr = this->m_uhAccessDeniedEvent.m_ptr;
    this->m_IoThreadShutdown = 1;
    SetEvent(m_ptr);
    LeaveCriticalSection(&this->m_IoThreadCriticalSection);
    WaitForSingleObjectEx(p_m_uhAccessDeniedWaitThreadHandle->m_ptr, 0xFFFFFFFF, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__stdcall *)(void *),&int CloseHandle(void *)>>::reset(0);
  }
  v5 = this->m_spKsProxyCameraAccessHandler.m_ptr;
  if ( v5 )
  {
    (*(void (__thiscall **)(_DWORD, struct IKsProxyCameraAccessHandler *))(*(_DWORD *)v5 + 20))(
      *(_DWORD *)(*(_DWORD *)v5 + 20),
      this->m_spKsProxyCameraAccessHandler.m_ptr);
    wil::com_ptr_t<IKsProxyCameraAccessHandler,wil::err_returncode_policy>::reset(&this->m_spKsProxyCameraAccessHandler);
  }
  v6 = this->m_IoEvents;
  if ( v6 )
  {
    if ( this->m_ActiveIoEventCount && *v6 )
    {
      CloseHandle(*v6);
      *this->m_IoEvents = 0;
    }
    operator delete[](this->m_IoEvents);
    this->m_IoEvents = 0;
  }
  if ( this->m_IoFreeSlotSemaphore )
  {
    CloseHandle(this->m_IoFreeSlotSemaphore);
    this->m_IoFreeSlotSemaphore = 0;
  }
  if ( this->m_IoSegments )
  {
    operator delete[](this->m_IoSegments);
    this->m_IoSegments = 0;
  }
  if ( this->m_PinClockHandle )
  {
    CloseHandle(this->m_PinClockHandle);
    this->m_PinClockHandle = 0;
  }
  if ( this->m_FilterHandle )
  {
    CloseHandle(this->m_FilterHandle);
    this->m_FilterHandle = 0;
  }
  for ( i = this->m_PinList.m_pFirst; i; i = i->m_pNext )
  {
    m_pObject = i->m_pObject;
    if ( m_pObject )
      (*(void (__thiscall **)(void *, int))(*(_DWORD *)m_pObject + 12))(m_pObject, 1);
  }
  FreeMarshalers(&this->m_MarshalerList);
  if ( this->m_DeviceRegKey )
    RegCloseKey(this->m_DeviceRegKey);
  m_PersistStreamDevice = this->m_PersistStreamDevice;
  if ( m_PersistStreamDevice )
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IPersistStream *))m_PersistStreamDevice->Release)(
      m_PersistStreamDevice->Release,
      this->m_PersistStreamDevice);
  if ( this->m_SymbolicLink )
    SysFreeString(this->m_SymbolicLink);
  if ( this->m_WaitThreadHandle )
  {
    m_WaitEvents = this->m_WaitEvents;
    this->m_WaitMessage.Message = 0;
    SetEvent(*m_WaitEvents);
    WaitForSingleObjectEx(this->m_WaitThreadHandle, 0xFFFFFFFF, 0);
    CloseHandle(this->m_WaitThreadHandle);
    this->m_WaitThreadHandle = 0;
  }
  v11 = this->m_WaitEvents;
  if ( v11 )
  {
    if ( this->m_ActiveWaitEventCount && *v11 )
    {
      CloseHandle(*v11);
      *this->m_WaitEvents = 0;
    }
    operator delete[](this->m_WaitEvents);
    this->m_WaitEvents = 0;
  }
  if ( this->m_WaitPins )
  {
    operator delete[](this->m_WaitPins);
    this->m_WaitPins = 0;
  }
  if ( this->m_WaitReplyHandle )
  {
    CloseHandle(this->m_WaitReplyHandle);
    this->m_WaitReplyHandle = 0;
  }
  DeleteCriticalSection(&this->m_IoThreadCriticalSection);
  v12 = &this->m_uhAccessDeniedWaitThreadHandle;
  this->m_cRef = 0;
  if ( this->m_uhAccessDeniedWaitThreadHandle.m_ptr && v12->m_ptr != (void *)-1 )
    CloseHandle(v12->m_ptr);
  if ( this->m_uhAccessDeniedEvent.m_ptr )
    wil::details::CloseHandle(this->m_uhAccessDeniedEvent.m_ptr, v14);
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(&this->m_spKsProxyCameraAccessHandler);
  wistd::unique_ptr<KsControlWnfNotify,wistd::default_delete<KsControlWnfNotify>>::~unique_ptr<KsControlWnfNotify,wistd::default_delete<KsControlWnfNotify>>(&this->m_pKsWnfNotify);
  CBaseList::~CBaseList(&this->m_MarshalerList);
  CBaseList::~CBaseList(&this->m_PinList);
  this->CPersistStream::IPersistStream::IPersist::IUnknown::__vftable = (CPersistStream_vtbl *)&CPersistStream::`vftable';
  CBaseFilter::~CBaseFilter(this);
  DeleteCriticalSection(&this->m_CritSec);
}

```

## disassembly

```asm
0x10008c1d  mov     edi, edi
0x10008c1f  push    ebp
0x10008c20  mov     ebp, esp
0x10008c22  sub     esp, 34h
0x10008c25  mov     eax, ___security_cookie
0x10008c2a  xor     eax, ebp
0x10008c2c  mov     [ebp+var_4], eax
0x10008c2f  push    ebx
0x10008c30  mov     ebx, ecx
0x10008c32  push    esi
0x10008c33  xor     esi, esi
0x10008c35  push    edi; void *
0x10008c36  mov     dword ptr [ebx], offset ??_7CKsProxy@@6BCUnknown@@@; const CKsProxy::`vftable'{for `CUnknown'}
0x10008c3c  mov     dword ptr [ebx+0Ch], offset ??_7CKsProxy@@6BIBaseFilter@@@; const CKsProxy::`vftable'{for `IBaseFilter'}
0x10008c43  mov     dword ptr [ebx+10h], offset ??_7CKsProxy@@6BIAMovieSetup@@@; const CKsProxy::`vftable'{for `IAMovieSetup'}
0x10008c4a  mov     dword ptr [ebx+50h], offset ??_7CKsProxy@@6BCPersistStream@@@; const CKsProxy::`vftable'{for `CPersistStream'}
0x10008c51  mov     dword ptr [ebx+5Ch], offset ??_7CKsProxy@@6BISpecifyPropertyPages@@@; const CKsProxy::`vftable'{for `ISpecifyPropertyPages'}
0x10008c58  mov     dword ptr [ebx+60h], offset ??_7CKsProxy@@6BIPersistPropertyBag@@@; const CKsProxy::`vftable'{for `IPersistPropertyBag'}
0x10008c5f  mov     dword ptr [ebx+64h], offset ??_7CKsProxy@@6BIReferenceClock@@@; const CKsProxy::`vftable'{for `IReferenceClock'}
0x10008c66  mov     dword ptr [ebx+68h], offset ??_7CKsProxy@@6BIMediaSeeking@@@; const CKsProxy::`vftable'{for `IMediaSeeking'}
0x10008c6d  mov     dword ptr [ebx+6Ch], offset ??_7CKsProxy@@6BIKsObject@@@; const CKsProxy::`vftable'{for `IKsObject'}
0x10008c74  mov     dword ptr [ebx+70h], offset ??_7CKsProxy@@6BIKsClock@@@; const CKsProxy::`vftable'{for `IKsClock'}
0x10008c7b  mov     dword ptr [ebx+74h], offset ??_7CKsProxy@@6BIKsPropertySet@@@; const CKsProxy::`vftable'{for `IKsPropertySet'}
0x10008c82  mov     dword ptr [ebx+78h], offset ??_7CKsProxy@@6BIKsClockPropertySet@@@; const CKsProxy::`vftable'{for `IKsClockPropertySet'}
0x10008c89  mov     dword ptr [ebx+7Ch], offset ??_7CKsProxy@@6BIAMFilterMiscFlags@@@; const CKsProxy::`vftable'{for `IAMFilterMiscFlags'}
0x10008c90  mov     dword ptr [ebx+80h], offset ??_7CKsProxy@@6BIKsControl@@@; const CKsProxy::`vftable'{for `IKsControl'}
0x10008c9a  mov     dword ptr [ebx+84h], offset ??_7CKsProxy@@6BIKsTopology@@@; const CKsProxy::`vftable'{for `IKsTopology'}
0x10008ca4  mov     dword ptr [ebx+88h], offset ??_7CKsProxy@@6BIKsAggregateControl@@@; const CKsProxy::`vftable'{for `IKsAggregateControl'}
0x10008cae  mov     dword ptr [ebx+8Ch], offset ??_7CKsProxy@@6BIAMDeviceRemoval@@@; const CKsProxy::`vftable'{for `IAMDeviceRemoval'}
0x10008cb8  mov     dword ptr [ebx+90h], offset ??_7CKsProxy@@6BIKsNotifyEvent@@@; const CKsProxy::`vftable'{for `IKsNotifyEvent'}
0x10008cc2  inc     dword ptr [ebx+8]
0x10008cc5  cmp     [ebx+170h], esi
0x10008ccb  jz      short loc_10008D32
0x10008ccd  xor     eax, eax
0x10008ccf  mov     [ebp+var_C], esi
0x10008cd2  lea     edi, [ebp+var_34]
0x10008cd5  mov     [ebp+var_8], esi
0x10008cd8  stosd
0x10008cd9  lea     esi, [ebp+var_34]
0x10008cdc  stosd
0x10008cdd  stosd
0x10008cde  stosd
0x10008cdf  lea     eax, [ebp+SystemTime]
0x10008ce2  lea     edi, [ebp+SystemTime]
0x10008ce5  movsd
0x10008ce6  push    eax; lpSystemTime
0x10008ce7  movsd
0x10008ce8  movsd
0x10008ce9  movsd
0x10008cea  xor     esi, esi
0x10008cec  mov     [ebp+var_10], esi
0x10008cef  call    ds:__imp__GetSystemTime@4; GetSystemTime(x)
0x10008cf5  mov     ecx, [ebx+170h]
0x10008cfb  lea     eax, [ebp+SystemTime]
0x10008cfe  push    eax
0x10008cff  push    4
0x10008d01  call    ?AddData@CAggregateDShowKsProxyTelemetry@@QAEXW4DShowKsProxyTelemetryType@@ABUDShowKsProxyTelemetryValue@@@Z; CAggregateDShowKsProxyTelemetry::AddData(DShowKsProxyTelemetryType,DShowKsProxyTelemetryValue const &)
0x10008d06  mov     edi, [ebx+170h]
0x10008d0c  test    edi, edi
0x10008d0e  jz      short loc_10008D24
0x10008d10  mov     eax, [edi]
0x10008d12  push    1
0x10008d14  mov     esi, [eax]
0x10008d16  mov     ecx, esi; this
0x10008d18  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10008d1e  mov     ecx, edi
0x10008d20  call    esi
0x10008d22  xor     esi, esi
0x10008d24  lea     ecx, [ebp+SystemTime]; this
0x10008d27  mov     [ebx+170h], esi
0x10008d2d  call    ??1DShowKsProxyTelemetryValue@@QAE@XZ; DShowKsProxyTelemetryValue::~DShowKsProxyTelemetryValue(void)
0x10008d32  cmp     [ebx+0E8h], esi
0x10008d38  jz      short loc_10008D89
0x10008d3a  lea     esi, [ebx+0F4h]
0x10008d40  push    esi; lpCriticalSection
0x10008d41  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10008d47  mov     eax, [ebx+110h]
0x10008d4d  mov     dword ptr [ebx+0F0h], 1
0x10008d57  push    dword ptr [eax]; hEvent
0x10008d59  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10008d5f  push    esi; lpCriticalSection
0x10008d60  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10008d66  xor     esi, esi
0x10008d68  push    esi; bAlertable
0x10008d69  push    0FFFFFFFFh; dwMilliseconds
0x10008d6b  push    dword ptr [ebx+0E8h]; hHandle
0x10008d71  call    ds:__imp__WaitForSingleObjectEx@12; WaitForSingleObjectEx(x,x,x)
0x10008d77  push    dword ptr [ebx+0E8h]; hObject
0x10008d7d  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10008d83  mov     [ebx+0E8h], esi
0x10008d89  lea     edi, [ebx+180h]
0x10008d8f  cmp     dword ptr [edi], 0
0x10008d92  jz      short loc_10008DD8
0x10008d94  cmp     dword ptr [edi], 0FFFFFFFFh
0x10008d97  jz      short loc_10008DD8
0x10008d99  lea     esi, [ebx+0F4h]
0x10008d9f  push    esi; lpCriticalSection
0x10008da0  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10008da6  push    dword ptr [ebx+17Ch]; hEvent
0x10008dac  mov     dword ptr [ebx+0F0h], 1
0x10008db6  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10008dbc  push    esi; lpCriticalSection
0x10008dbd  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10008dc3  xor     esi, esi
0x10008dc5  push    esi; bAlertable
0x10008dc6  push    0FFFFFFFFh; dwMilliseconds
0x10008dc8  push    dword ptr [edi]; hHandle
0x10008dca  call    ds:__imp__WaitForSingleObjectEx@12; WaitForSingleObjectEx(x,x,x)
0x10008dd0  push    esi
0x10008dd1  mov     ecx, edi
0x10008dd3  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6GHPAX@Z$1?CloseHandle@@YGH0@Z@details@wil@@@details@wil@@QAEXPAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x10008dd8  lea     edi, [ebx+178h]
0x10008dde  mov     ecx, [edi]
0x10008de0  test    ecx, ecx
0x10008de2  jz      short loc_10008DFD
0x10008de4  mov     eax, [ecx]
0x10008de6  push    ecx
0x10008de7  mov     esi, [eax+14h]
0x10008dea  mov     ecx, esi; this
0x10008dec  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10008df2  call    esi
0x10008df4  mov     ecx, edi
0x10008df6  call    ?reset@?$com_ptr_t@UIKsProxyCameraAccessHandler@@Uerr_returncode_policy@wil@@@wil@@QAEXXZ; wil::com_ptr_t<IKsProxyCameraAccessHandler,wil::err_returncode_policy>::reset(void)
0x10008dfb  xor     esi, esi
0x10008dfd  mov     eax, [ebx+110h]
0x10008e03  test    eax, eax
0x10008e05  jz      short loc_10008E36
0x10008e07  cmp     [ebx+118h], esi
0x10008e0d  jz      short loc_10008E24
0x10008e0f  cmp     dword ptr [eax], 0
0x10008e12  jz      short loc_10008E24
0x10008e14  push    dword ptr [eax]; hObject
0x10008e16  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10008e1c  mov     eax, [ebx+110h]
0x10008e22  mov     [eax], esi
0x10008e24  push    dword ptr [ebx+110h]; Block
0x10008e2a  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10008e2f  pop     ecx
0x10008e30  mov     [ebx+110h], esi
0x10008e36  mov     eax, [ebx+10Ch]
0x10008e3c  test    eax, eax
0x10008e3e  jz      short loc_10008E4D
0x10008e40  push    eax; hObject
0x10008e41  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10008e47  mov     [ebx+10Ch], esi
0x10008e4d  mov     eax, [ebx+114h]
0x10008e53  test    eax, eax
0x10008e55  jz      short loc_10008E64
0x10008e57  push    eax; Block
0x10008e58  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10008e5d  pop     ecx
0x10008e5e  mov     [ebx+114h], esi
0x10008e64  mov     eax, [ebx+0E4h]
0x10008e6a  test    eax, eax
0x10008e6c  jz      short loc_10008E7B
0x10008e6e  push    eax; hObject
0x10008e6f  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10008e75  mov     [ebx+0E4h], esi
0x10008e7b  mov     eax, [ebx+0DCh]
0x10008e81  test    eax, eax
0x10008e83  jz      short loc_10008E92
0x10008e85  push    eax; hObject
0x10008e86  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10008e8c  mov     [ebx+0DCh], esi
0x10008e92  mov     edi, [ebx+0ACh]
0x10008e98  test    edi, edi
0x10008e9a  jz      short loc_10008EC3
0x10008e9c  mov     eax, [edi+8]
0x10008e9f  mov     [ebp+var_24], eax
0x10008ea2  test    eax, eax
0x10008ea4  jz      short loc_10008EBA
0x10008ea6  mov     eax, [eax]
0x10008ea8  push    1
0x10008eaa  mov     esi, [eax+0Ch]
0x10008ead  mov     ecx, esi; this
0x10008eaf  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10008eb5  mov     ecx, [ebp+var_24]
0x10008eb8  call    esi
0x10008eba  mov     eax, [edi+4]
0x10008ebd  mov     edi, eax
0x10008ebf  test    eax, eax
0x10008ec1  jnz     short loc_10008E9C
0x10008ec3  lea     edi, [ebx+0C4h]
0x10008ec9  mov     ecx, edi
0x10008ecb  call    ?FreeMarshalers@@YGXPAV?$CGenericList@VCAggregateMarshaler@@@@@Z; FreeMarshalers(CGenericList<CAggregateMarshaler> *)
0x10008ed0  mov     eax, [ebx+128h]
0x10008ed6  test    eax, eax
0x10008ed8  jz      short loc_10008EE1
0x10008eda  push    eax; hKey
0x10008edb  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10008ee1  mov     ecx, [ebx+12Ch]
0x10008ee7  test    ecx, ecx
0x10008ee9  jz      short loc_10008EFB
0x10008eeb  mov     eax, [ecx]
0x10008eed  push    ecx
0x10008eee  mov     esi, [eax+8]
0x10008ef1  mov     ecx, esi; this
0x10008ef3  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10008ef9  call    esi
0x10008efb  mov     eax, [ebx+154h]
0x10008f01  test    eax, eax
0x10008f03  jz      short loc_10008F0C
0x10008f05  push    eax; bstrString
0x10008f06  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x10008f0c  xor     esi, esi
0x10008f0e  cmp     [ebx+130h], esi
0x10008f14  jz      short loc_10008F4B
0x10008f16  mov     eax, [ebx+134h]
0x10008f1c  mov     [ebx+144h], esi
0x10008f22  push    dword ptr [eax]; hEvent
0x10008f24  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10008f2a  push    esi; bAlertable
0x10008f2b  push    0FFFFFFFFh; dwMilliseconds
0x10008f2d  push    dword ptr [ebx+130h]; hHandle
0x10008f33  call    ds:__imp__WaitForSingleObjectEx@12; WaitForSingleObjectEx(x,x,x)
0x10008f39  push    dword ptr [ebx+130h]; hObject
0x10008f3f  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10008f45  mov     [ebx+130h], esi
0x10008f4b  mov     eax, [ebx+134h]
0x10008f51  test    eax, eax
0x10008f53  jz      short loc_10008F83
0x10008f55  cmp     [ebx+13Ch], esi
0x10008f5b  jz      short loc_10008F71
0x10008f5d  cmp     [eax], esi
0x10008f5f  jz      short loc_10008F71
0x10008f61  push    dword ptr [eax]; hObject
0x10008f63  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10008f69  mov     eax, [ebx+134h]
0x10008f6f  mov     [eax], esi
0x10008f71  push    dword ptr [ebx+134h]; Block
0x10008f77  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10008f7c  pop     ecx
0x10008f7d  mov     [ebx+134h], esi
0x10008f83  mov     eax, [ebx+138h]
0x10008f89  test    eax, eax
0x10008f8b  jz      short loc_10008F9A
0x10008f8d  push    eax; Block
0x10008f8e  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10008f93  pop     ecx
0x10008f94  mov     [ebx+138h], esi
0x10008f9a  mov     eax, [ebx+140h]
0x10008fa0  test    eax, eax
0x10008fa2  jz      short loc_10008FB1
0x10008fa4  push    eax; hObject
0x10008fa5  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10008fab  mov     [ebx+140h], esi
0x10008fb1  lea     eax, [ebx+0F4h]
0x10008fb7  push    eax; lpCriticalSection
0x10008fb8  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x10008fbe  lea     eax, [ebx+180h]
0x10008fc4  mov     [ebx+8], esi
0x10008fc7  cmp     [eax], esi
0x10008fc9  jz      short loc_10008FD8
0x10008fcb  cmp     dword ptr [eax], 0FFFFFFFFh
0x10008fce  jz      short loc_10008FD8
0x10008fd0  push    dword ptr [eax]; hObject
0x10008fd2  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10008fd8  mov     eax, [ebx+17Ch]
0x10008fde  test    eax, eax
0x10008fe0  jz      short loc_10008FE8
0x10008fe2  push    eax; hObject
0x10008fe3  call    ?CloseHandle@details@wil@@YGXPAX@Z; wil::details::CloseHandle(void *)
0x10008fe8  lea     ecx, [ebx+178h]
0x10008fee  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x10008ff3  lea     ecx, [ebx+174h]
0x10008ff9  call    ??1?$unique_ptr@VKsControlWnfNotify@@U?$default_delete@VKsControlWnfNotify@@@wistd@@@wistd@@QAE@XZ; wistd::unique_ptr<KsControlWnfNotify,wistd::default_delete<KsControlWnfNotify>>::~unique_ptr<KsControlWnfNotify,wistd::default_delete<KsControlWnfNotify>>(void)
0x10008ffe  mov     ecx, edi; this
0x10009000  call    ??1CBaseList@@QAE@XZ; CBaseList::~CBaseList(void)
0x10009005  lea     ecx, [ebx+0ACh]; this
0x1000900b  call    ??1CBaseList@@QAE@XZ; CBaseList::~CBaseList(void)
0x10009010  mov     ecx, ebx; this
0x10009012  mov     dword ptr [ebx+50h], offset ??_7CPersistStream@@6B@; const CPersistStream::`vftable'
0x10009019  call    ??1CBaseFilter@@UAE@XZ; CBaseFilter::~CBaseFilter(void)
0x1000901e  lea     eax, [ebx+94h]
0x10009024  push    eax; lpCriticalSection
0x10009025  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x1000902b  mov     ecx, [ebp+var_4]
0x1000902e  pop     edi
0x1000902f  pop     esi
0x10009030  xor     ecx, ebp; StackCookie
0x10009032  pop     ebx
0x10009033  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10009038  leave
0x10009039  retn
```
