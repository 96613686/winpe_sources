# CKsProxy::~CKsProxy(void)

- ea: `0x180013d70`
- end: `0x18001452e`
- name: `??1CKsProxy@@UEAA@XZ`
- size: `1982`
- prototype: `void __fastcall(CKsProxy *this, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, loader_planting, installer_update`

## callers

- `0x180013d30`

## callees

- `0x180009654`
- `0x180013d70`
- `0x18001f1c4`
- `0x18001f620`
- `0x180025724`
- `0x180045010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001403b`
- `KERNEL32!GetLastError` at `0x18001403b`
- `KERNEL32!SetEvent` at `0x180013f64`
- `KERNEL32!SetEvent` at `0x180013ff0`
- `KERNEL32!SetEvent` at `0x180014203`
- `KERNEL32!SetEvent` at `0x180013f64`
- `KERNEL32!SetEvent` at `0x180013ff0`
- `KERNEL32!SetEvent` at `0x180014203`
- `KERNEL32!WaitForSingleObjectEx` at `0x180013f92`
- `KERNEL32!WaitForSingleObjectEx` at `0x18001401e`
- `KERNEL32!WaitForSingleObjectEx` at `0x18001421e`
- `KERNEL32!WaitForSingleObjectEx` at `0x180013f92`
- `KERNEL32!WaitForSingleObjectEx` at `0x18001401e`
- `KERNEL32!WaitForSingleObjectEx` at `0x18001421e`
- `KERNEL32!CloseHandle` at `0x180013fa5`
- `KERNEL32!CloseHandle` at `0x18001404c`
- `KERNEL32!CloseHandle` at `0x1800140c0`
- `KERNEL32!CloseHandle` at `0x1800140f5`
- `KERNEL32!CloseHandle` at `0x18001412c`
- `KERNEL32!CloseHandle` at `0x18001414b`
- `KERNEL32!CloseHandle` at `0x180014231`
- `KERNEL32!CloseHandle` at `0x180014260`
- `KERNEL32!CloseHandle` at `0x1800142ad`
- `KERNEL32!CloseHandle` at `0x1800142e7`
- `KERNEL32!CloseHandle` at `0x1800142ff`
- `KERNEL32!CloseHandle` at `0x180013fa5`
- `KERNEL32!CloseHandle` at `0x18001404c`
- `KERNEL32!CloseHandle` at `0x1800140c0`
- `KERNEL32!CloseHandle` at `0x1800140f5`
- `KERNEL32!CloseHandle` at `0x18001412c`
- `KERNEL32!CloseHandle` at `0x18001414b`
- `KERNEL32!CloseHandle` at `0x180014231`
- `KERNEL32!CloseHandle` at `0x180014260`
- `KERNEL32!CloseHandle` at `0x1800142ad`
- `KERNEL32!CloseHandle` at `0x1800142e7`
- `KERNEL32!CloseHandle` at `0x1800142ff`
- `KERNEL32!DeleteCriticalSection` at `0x1800142c7`
- `KERNEL32!DeleteCriticalSection` at `0x1800143be`
- `KERNEL32!DeleteCriticalSection` at `0x1800144f1`
- `KERNEL32!DeleteCriticalSection` at `0x1800142c7`
- `KERNEL32!DeleteCriticalSection` at `0x1800143be`
- `KERNEL32!DeleteCriticalSection` at `0x1800144f1`
- `KERNEL32!LeaveCriticalSection` at `0x180013f77`
- `KERNEL32!LeaveCriticalSection` at `0x180014003`
- `KERNEL32!LeaveCriticalSection` at `0x180013f77`
- `KERNEL32!LeaveCriticalSection` at `0x180014003`
- `KERNEL32!EnterCriticalSection` at `0x180013f44`
- `KERNEL32!EnterCriticalSection` at `0x180013fd3`
- `KERNEL32!EnterCriticalSection` at `0x180013f44`
- `KERNEL32!EnterCriticalSection` at `0x180013fd3`
- `KERNEL32!SetLastError` at `0x18001405a`
- `KERNEL32!SetLastError` at `0x18001405a`
- `KERNEL32!GetSystemTime` at `0x180013eab`
- `KERNEL32!GetSystemTime` at `0x180013eab`
- `ADVAPI32!RegCloseKey` at `0x1800141ae`
- `ADVAPI32!RegCloseKey` at `0x1800141ae`
- `OLEAUT32!__imp_SysFreeString` at `0x180013f12`
- `OLEAUT32!__imp_SysFreeString` at `0x180013f28`
- `OLEAUT32!__imp_SysFreeString` at `0x1800141de`
- `OLEAUT32!__imp_SysFreeString` at `0x180013f12`
- `OLEAUT32!__imp_SysFreeString` at `0x180013f28`
- `OLEAUT32!__imp_SysFreeString` at `0x1800141de`
- `MFPlat!MFShutdown` at `0x1800143ae`
- `MFPlat!MFShutdown` at `0x1800143ae`

## string_xrefs

- `0x18001451c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall CKsProxy::~CKsProxy(CKsProxy *this, unsigned __int64 a2)
{
  __int64 v3; // r9
  __int64 v4; // rcx
  struct CAggregateDShowKsProxyTelemetry *m_pDShowKsProxyEvents; // rcx
  OLECHAR *v6; // rcx
  void **m_IoEvents; // rcx
  void *m_ptr; // rcx
  char *v9; // rsi
  DWORD LastError; // edi
  struct IKsProxyCameraAccessHandler *v11; // rcx
  struct IKsProxyCameraAccessHandler *v12; // rcx
  void **v13; // rax
  void *m_IoFreeSlotSemaphore; // rcx
  _KSSTREAM_SEGMENT **m_IoSegments; // rcx
  void *m_PinClockHandle; // rcx
  void *m_FilterHandle; // rcx
  CBaseList::CNode *i; // rdi
  void *m_pObject; // rcx
  unsigned __int64 v20; // rdx
  HKEY__ *m_DeviceRegKey; // rcx
  IPersistStream *m_PersistStreamDevice; // rcx
  wchar_t *m_SymbolicLink; // rcx
  void **m_WaitEvents; // rcx
  void **v25; // rax
  void **m_WaitPins; // rcx
  void *m_WaitReplyHandle; // rcx
  unsigned __int64 v28; // rdx
  char *v29; // rcx
  void *v30; // rcx
  const char *v31; // r9
  struct IKsProxyCameraAccessHandler *v32; // rcx
  struct KsControlWnfNotify *value; // rdi
  int (__fastcall ***v34)(_QWORD, GUID *, __int64 *); // rcx
  int (__fastcall ***v35)(_QWORD, GUID *, __int64 *); // rcx
  CBaseList::CNode *m_pFirst; // rdi
  CBaseList::CNode *v37; // rcx
  CBaseList::CNode *m_pHead; // rdi
  CBaseList::CNode *v39; // rcx
  CBaseList::CNode *v40; // rdi
  CBaseList::CNode *v41; // rcx
  CBaseList::CNode *v42; // rdi
  CBaseList::CNode *v43; // rcx
  wchar_t *m_pName; // rcx
  IReferenceClock *m_pClock; // rcx
  char v46; // [rsp+20h] [rbp-78h]
  __int64 v47; // [rsp+30h] [rbp-68h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+38h] [rbp-60h] BYREF
  int v49; // [rsp+48h] [rbp-50h]
  BSTR bstrString[2]; // [rsp+50h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

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
    v49 = 0;
    *(_OWORD *)bstrString = 0;
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    v4 = *((_QWORD *)this->m_pDShowKsProxyEvents + 1);
    if ( v4 )
    {
      LOBYTE(v3) = 1;
      v46 = 1;
      (*(void (__fastcall **)(__int64, __int64, _SYSTEMTIME *, __int64, char))(*(_QWORD *)v4 + 56LL))(
        v4,
        4,
        &SystemTime,
        v3,
        v46);
    }
    m_pDShowKsProxyEvents = this->m_pDShowKsProxyEvents;
    if ( m_pDShowKsProxyEvents )
      (**(void (__fastcall ***)(struct CAggregateDShowKsProxyTelemetry *, __int64))m_pDShowKsProxyEvents)(
        m_pDShowKsProxyEvents,
        1);
    v6 = bstrString[1];
    this->m_pDShowKsProxyEvents = 0;
    if ( v6 )
      SysFreeString(v6);
    if ( bstrString[0] )
      SysFreeString(bstrString[0]);
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
  if ( (unsigned __int64)this->m_uhAccessDeniedWaitThreadHandle.m_ptr - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    EnterCriticalSection(&this->m_IoThreadCriticalSection);
    m_ptr = this->m_uhAccessDeniedEvent.m_ptr;
    this->m_IoThreadShutdown = 1;
    SetEvent(m_ptr);
    LeaveCriticalSection(&this->m_IoThreadCriticalSection);
    WaitForSingleObjectEx(this->m_uhAccessDeniedWaitThreadHandle.m_ptr, 0xFFFFFFFF, 0);
    v9 = (char *)this->m_uhAccessDeniedWaitThreadHandle.m_ptr;
    if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      CloseHandle(v9);
      SetLastError(LastError);
    }
    this->m_uhAccessDeniedWaitThreadHandle.m_ptr = 0;
  }
  v11 = this->m_spKsProxyCameraAccessHandler.m_ptr;
  if ( v11 )
  {
    (*(void (__fastcall **)(struct IKsProxyCameraAccessHandler *))(*(_QWORD *)v11 + 40LL))(v11);
    v12 = this->m_spKsProxyCameraAccessHandler.m_ptr;
    this->m_spKsProxyCameraAccessHandler.m_ptr = 0;
    if ( v12 )
      (*(void (__fastcall **)(struct IKsProxyCameraAccessHandler *))(*(_QWORD *)v12 + 16LL))(v12);
  }
  v13 = this->m_IoEvents;
  if ( v13 )
  {
    if ( this->m_ActiveIoEventCount && *v13 )
    {
      CloseHandle(*v13);
      *this->m_IoEvents = 0;
    }
    operator delete(this->m_IoEvents, a2);
    this->m_IoEvents = 0;
  }
  m_IoFreeSlotSemaphore = this->m_IoFreeSlotSemaphore;
  if ( m_IoFreeSlotSemaphore )
  {
    CloseHandle(m_IoFreeSlotSemaphore);
    this->m_IoFreeSlotSemaphore = 0;
  }
  m_IoSegments = this->m_IoSegments;
  if ( m_IoSegments )
  {
    operator delete(m_IoSegments, a2);
    this->m_IoSegments = 0;
  }
  m_PinClockHandle = this->m_PinClockHandle;
  if ( m_PinClockHandle )
  {
    CloseHandle(m_PinClockHandle);
    this->m_PinClockHandle = 0;
  }
  m_FilterHandle = this->m_FilterHandle;
  if ( m_FilterHandle )
  {
    CloseHandle(m_FilterHandle);
    this->m_FilterHandle = 0;
  }
  for ( i = this->m_PinList.m_pFirst; i; i = i->m_pNext )
  {
    m_pObject = i->m_pObject;
    if ( m_pObject )
      (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)m_pObject + 24LL))(m_pObject, 1);
  }
  FreeMarshalers((__int64)&this->m_MarshalerList);
  m_DeviceRegKey = this->m_DeviceRegKey;
  if ( m_DeviceRegKey )
    RegCloseKey(m_DeviceRegKey);
  m_PersistStreamDevice = this->m_PersistStreamDevice;
  if ( m_PersistStreamDevice )
    m_PersistStreamDevice->Release(m_PersistStreamDevice);
  m_SymbolicLink = this->m_SymbolicLink;
  if ( m_SymbolicLink )
    SysFreeString(m_SymbolicLink);
  if ( this->m_WaitThreadHandle )
  {
    m_WaitEvents = this->m_WaitEvents;
    this->m_WaitMessage.Message = 0;
    SetEvent(*m_WaitEvents);
    WaitForSingleObjectEx(this->m_WaitThreadHandle, 0xFFFFFFFF, 0);
    CloseHandle(this->m_WaitThreadHandle);
    this->m_WaitThreadHandle = 0;
  }
  v25 = this->m_WaitEvents;
  if ( v25 )
  {
    if ( this->m_ActiveWaitEventCount && *v25 )
    {
      CloseHandle(*v25);
      *this->m_WaitEvents = 0;
    }
    operator delete(this->m_WaitEvents, v20);
    this->m_WaitEvents = 0;
  }
  m_WaitPins = this->m_WaitPins;
  if ( m_WaitPins )
  {
    operator delete(m_WaitPins, v20);
    this->m_WaitPins = 0;
  }
  m_WaitReplyHandle = this->m_WaitReplyHandle;
  if ( m_WaitReplyHandle )
  {
    CloseHandle(m_WaitReplyHandle);
    this->m_WaitReplyHandle = 0;
  }
  DeleteCriticalSection(&this->m_IoThreadCriticalSection);
  this->m_cRef = 0;
  v29 = (char *)this->m_uhAccessDeniedWaitThreadHandle.m_ptr;
  if ( (unsigned __int64)(v29 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v29);
  v30 = this->m_uhAccessDeniedEvent.m_ptr;
  if ( v30 && !CloseHandle(v30) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v31);
  v32 = this->m_spKsProxyCameraAccessHandler.m_ptr;
  if ( v32 )
    (*(void (__fastcall **)(struct IKsProxyCameraAccessHandler *))(*(_QWORD *)v32 + 16LL))(v32);
  value = this->m_pKsWnfNotify.__ptr_.__value_;
  this->m_pKsWnfNotify.__ptr_.__value_ = 0;
  if ( value )
  {
    v34 = *(int (__fastcall ****)(_QWORD, GUID *, __int64 *))value;
    if ( *(_QWORD *)value )
    {
      v47 = 0;
      if ( (**v34)(v34, &GUID_97ec2ea4_0e42_4937_97ac_9d6d328824e1, &v47) >= 0 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 24LL))(v47);
      v35 = *(int (__fastcall ****)(_QWORD, GUID *, __int64 *))value;
      *(_QWORD *)value = 0;
      if ( v35 )
        ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v35)[2])(v35);
      if ( v47 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    }
    if ( *((_BYTE *)value + 48) )
      MFShutdown();
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)value + 8));
    if ( *(_QWORD *)value )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)value + 16LL))(*(_QWORD *)value);
    operator delete(value, 0x38u);
  }
  m_pFirst = this->m_MarshalerList.m_pFirst;
  while ( m_pFirst )
  {
    v37 = m_pFirst;
    m_pFirst = m_pFirst->m_pNext;
    operator delete(v37, 0x18u);
  }
  m_pHead = this->m_MarshalerList.m_Cache.m_pHead;
  this->m_MarshalerList.m_Count = 0;
  this->m_MarshalerList.m_pLast = 0;
  this->m_MarshalerList.m_pFirst = 0;
  while ( m_pHead )
  {
    v39 = m_pHead;
    m_pHead = m_pHead->m_pNext;
    operator delete(v39, 0x18u);
  }
  v40 = this->m_PinList.m_pFirst;
  while ( v40 )
  {
    v41 = v40;
    v40 = v40->m_pNext;
    operator delete(v41, 0x18u);
  }
  v42 = this->m_PinList.m_Cache.m_pHead;
  this->m_PinList.m_Count = 0;
  this->m_PinList.m_pLast = 0;
  this->m_PinList.m_pFirst = 0;
  while ( v42 )
  {
    v43 = v42;
    v42 = v42->m_pNext;
    operator delete(v43, 0x18u);
  }
  m_pName = this->m_pName;
  this->CPersistStream::IPersistStream::IPersist::IUnknown::__vftable = (CPersistStream_vtbl *)&CPersistStream::`vftable';
  operator delete(m_pName, v28);
  m_pClock = this->m_pClock;
  if ( m_pClock )
  {
    m_pClock->Release(m_pClock);
    this->m_pClock = 0;
  }
  _InterlockedDecrement(&CBaseObject::m_cObjects);
  DeleteCriticalSection(&this->m_CritSec);
}

```

## disassembly

```asm
0x180013d70  push    rbx
0x180013d72  push    rbp
0x180013d73  push    rsi
0x180013d74  push    rdi
0x180013d75  sub     rsp, 78h
0x180013d79  mov     rax, cs:__security_cookie
0x180013d80  xor     rax, rsp
0x180013d83  mov     [rsp+98h+var_38], rax
0x180013d88  lea     rax, ??_7CKsProxy@@6BCUnknown@@@; const CKsProxy::`vftable'{for `CUnknown'}
0x180013d8f  xor     ebp, ebp
0x180013d91  mov     [rcx], rax
0x180013d94  mov     rbx, rcx
0x180013d97  lea     rax, ??_7CKsProxy@@6BIBaseFilter@@@; const CKsProxy::`vftable'{for `IBaseFilter'}
0x180013d9e  mov     [rcx+18h], rax
0x180013da2  lea     rax, ??_7CKsProxy@@6BIAMovieSetup@@@; const CKsProxy::`vftable'{for `IAMovieSetup'}
0x180013da9  mov     [rcx+20h], rax
0x180013dad  lea     rax, ??_7CKsProxy@@6BCPersistStream@@@; const CKsProxy::`vftable'{for `CPersistStream'}
0x180013db4  mov     [rcx+78h], rax
0x180013db8  lea     rax, ??_7CKsProxy@@6BISpecifyPropertyPages@@@; const CKsProxy::`vftable'{for `ISpecifyPropertyPages'}
0x180013dbf  mov     [rcx+88h], rax
0x180013dc6  lea     rax, ??_7CKsProxy@@6BIPersistPropertyBag@@@; const CKsProxy::`vftable'{for `IPersistPropertyBag'}
0x180013dcd  mov     [rcx+90h], rax
0x180013dd4  lea     rax, ??_7CKsProxy@@6BIReferenceClock@@@; const CKsProxy::`vftable'{for `IReferenceClock'}
0x180013ddb  mov     [rcx+98h], rax
0x180013de2  lea     rax, ??_7CKsProxy@@6BIMediaSeeking@@@; const CKsProxy::`vftable'{for `IMediaSeeking'}
0x180013de9  mov     [rcx+0A0h], rax
0x180013df0  lea     rax, ??_7CKsProxy@@6BIKsObject@@@; const CKsProxy::`vftable'{for `IKsObject'}
0x180013df7  mov     [rcx+0A8h], rax
0x180013dfe  lea     rax, ??_7CKsProxy@@6BIKsClock@@@; const CKsProxy::`vftable'{for `IKsClock'}
0x180013e05  mov     [rcx+0B0h], rax
0x180013e0c  lea     rax, ??_7CKsProxy@@6BIKsPropertySet@@@; const CKsProxy::`vftable'{for `IKsPropertySet'}
0x180013e13  mov     [rcx+0B8h], rax
0x180013e1a  lea     rax, ??_7CKsProxy@@6BIKsClockPropertySet@@@; const CKsProxy::`vftable'{for `IKsClockPropertySet'}
0x180013e21  mov     [rcx+0C0h], rax
0x180013e28  lea     rax, ??_7CKsProxy@@6BIAMFilterMiscFlags@@@; const CKsProxy::`vftable'{for `IAMFilterMiscFlags'}
0x180013e2f  mov     [rcx+0C8h], rax
0x180013e36  lea     rax, ??_7CKsProxy@@6BIKsControl@@@; const CKsProxy::`vftable'{for `IKsControl'}
0x180013e3d  mov     [rcx+0D0h], rax
0x180013e44  lea     rax, ??_7CKsProxy@@6BIKsTopology@@@; const CKsProxy::`vftable'{for `IKsTopology'}
0x180013e4b  mov     [rcx+0D8h], rax
0x180013e52  lea     rax, ??_7CKsProxy@@6BIKsAggregateControl@@@; const CKsProxy::`vftable'{for `IKsAggregateControl'}
0x180013e59  mov     [rcx+0E0h], rax
0x180013e60  lea     rax, ??_7CKsProxy@@6BIAMDeviceRemoval@@@; const CKsProxy::`vftable'{for `IAMDeviceRemoval'}
0x180013e67  mov     [rcx+0E8h], rax
0x180013e6e  lea     rax, ??_7CKsProxy@@6BIKsNotifyEvent@@@; const CKsProxy::`vftable'{for `IKsNotifyEvent'}
0x180013e75  mov     [rcx+0F0h], rax
0x180013e7c  mov     eax, [rcx+10h]
0x180013e7f  inc     eax
0x180013e81  mov     [rcx+10h], eax
0x180013e84  cmp     [rcx+268h], rbp
0x180013e8b  jz      loc_180013F34
0x180013e91  xorps   xmm0, xmm0
0x180013e94  mov     [rsp+98h+var_50], ebp
0x180013e98  xorps   xmm1, xmm1
0x180013e9b  lea     rcx, [rsp+98h+SystemTime]; lpSystemTime
0x180013ea0  movdqu  xmmword ptr [rsp+98h+bstrString], xmm0
0x180013ea6  movups  xmmword ptr [rsp+98h+SystemTime.wYear], xmm1
0x180013eab  call    cs:__imp_GetSystemTime
0x180013eb2  nop     dword ptr [rax+rax+00h]
0x180013eb7  mov     rax, [rbx+268h]
0x180013ebe  mov     rcx, [rax+8]
0x180013ec2  test    rcx, rcx
0x180013ec5  jz      short loc_180013EE5
0x180013ec7  mov     rax, [rcx]
0x180013eca  lea     r8, [rsp+98h+SystemTime]
0x180013ecf  mov     r9b, 1
0x180013ed2  mov     [rsp+98h+var_78], 1
0x180013ed7  mov     edx, 4
0x180013edc  mov     rax, [rax+38h]
0x180013ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ee5  mov     rcx, [rbx+268h]
0x180013eec  test    rcx, rcx
0x180013eef  jz      short loc_180013F01
0x180013ef1  mov     rax, [rcx]
0x180013ef4  mov     edx, 1
0x180013ef9  mov     rax, [rax]
0x180013efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f01  mov     rcx, [rsp+98h+bstrString+8]; bstrString
0x180013f06  mov     [rbx+268h], rbp
0x180013f0d  test    rcx, rcx
0x180013f10  jz      short loc_180013F1E
0x180013f12  call    cs:__imp_SysFreeString
0x180013f19  nop     dword ptr [rax+rax+00h]
0x180013f1e  mov     rcx, [rsp+98h+bstrString]; bstrString
0x180013f23  test    rcx, rcx
0x180013f26  jz      short loc_180013F34
0x180013f28  call    cs:__imp_SysFreeString
0x180013f2f  nop     dword ptr [rax+rax+00h]
0x180013f34  cmp     [rbx+188h], rbp
0x180013f3b  jz      short loc_180013FB8
0x180013f3d  lea     rcx, [rbx+198h]; lpCriticalSection
0x180013f44  call    cs:__imp_EnterCriticalSection
0x180013f4b  nop     dword ptr [rax+rax+00h]
0x180013f50  mov     rcx, [rbx+1C8h]
0x180013f57  mov     dword ptr [rbx+194h], 1
0x180013f61  mov     rcx, [rcx]; hEvent
0x180013f64  call    cs:__imp_SetEvent
0x180013f6b  nop     dword ptr [rax+rax+00h]
0x180013f70  lea     rcx, [rbx+198h]; lpCriticalSection
0x180013f77  call    cs:__imp_LeaveCriticalSection
0x180013f7e  nop     dword ptr [rax+rax+00h]
0x180013f83  mov     rcx, [rbx+188h]; hHandle
0x180013f8a  xor     r8d, r8d; bAlertable
0x180013f8d  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180013f92  call    cs:__imp_WaitForSingleObjectEx
0x180013f99  nop     dword ptr [rax+rax+00h]
0x180013f9e  mov     rcx, [rbx+188h]; hObject
0x180013fa5  call    cs:__imp_CloseHandle
0x180013fac  nop     dword ptr [rax+rax+00h]
0x180013fb1  mov     [rbx+188h], rbp
0x180013fb8  mov     rax, [rbx+288h]
0x180013fbf  dec     rax
0x180013fc2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180013fc6  ja      loc_18001406D
0x180013fcc  lea     rcx, [rbx+198h]; lpCriticalSection
0x180013fd3  call    cs:__imp_EnterCriticalSection
0x180013fda  nop     dword ptr [rax+rax+00h]
0x180013fdf  mov     rcx, [rbx+280h]; hEvent
0x180013fe6  mov     dword ptr [rbx+194h], 1
0x180013ff0  call    cs:__imp_SetEvent
0x180013ff7  nop     dword ptr [rax+rax+00h]
0x180013ffc  lea     rcx, [rbx+198h]; lpCriticalSection
0x180014003  call    cs:__imp_LeaveCriticalSection
0x18001400a  nop     dword ptr [rax+rax+00h]
0x18001400f  mov     rcx, [rbx+288h]; hHandle
0x180014016  xor     r8d, r8d; bAlertable
0x180014019  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18001401e  call    cs:__imp_WaitForSingleObjectEx
0x180014025  nop     dword ptr [rax+rax+00h]
0x18001402a  mov     rsi, [rbx+288h]
0x180014031  lea     rax, [rsi-1]
0x180014035  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180014039  ja      short loc_180014066
0x18001403b  call    cs:__imp_GetLastError
0x180014042  nop     dword ptr [rax+rax+00h]
0x180014047  mov     rcx, rsi; hObject
0x18001404a  mov     edi, eax
0x18001404c  call    cs:__imp_CloseHandle
0x180014053  nop     dword ptr [rax+rax+00h]
0x180014058  mov     ecx, edi; dwErrCode
0x18001405a  call    cs:__imp_SetLastError
0x180014061  nop     dword ptr [rax+rax+00h]
0x180014066  mov     [rbx+288h], rbp
0x18001406d  mov     rcx, [rbx+278h]
0x180014074  test    rcx, rcx
0x180014077  jz      short loc_1800140A4
0x180014079  mov     rax, [rcx]
0x18001407c  mov     rax, [rax+28h]
0x180014080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014085  mov     rcx, [rbx+278h]
0x18001408c  mov     [rbx+278h], rbp
0x180014093  test    rcx, rcx
0x180014096  jz      short loc_1800140A4
0x180014098  mov     rax, [rcx]
0x18001409b  mov     rax, [rax+10h]
0x18001409f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140a4  mov     rax, [rbx+1C8h]
0x1800140ab  test    rax, rax
0x1800140ae  jz      short loc_1800140E9
0x1800140b0  cmp     [rbx+1D8h], ebp
0x1800140b6  jz      short loc_1800140D6
0x1800140b8  mov     rcx, [rax]; hObject
0x1800140bb  test    rcx, rcx
0x1800140be  jz      short loc_1800140D6
0x1800140c0  call    cs:__imp_CloseHandle
0x1800140c7  nop     dword ptr [rax+rax+00h]
0x1800140cc  mov     rax, [rbx+1C8h]
0x1800140d3  mov     [rax], rbp
0x1800140d6  mov     rcx, [rbx+1C8h]; void *
0x1800140dd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800140e2  mov     [rbx+1C8h], rbp
0x1800140e9  mov     rcx, [rbx+1C0h]; hObject
0x1800140f0  test    rcx, rcx
0x1800140f3  jz      short loc_180014108
0x1800140f5  call    cs:__imp_CloseHandle
0x1800140fc  nop     dword ptr [rax+rax+00h]
0x180014101  mov     [rbx+1C0h], rbp
0x180014108  mov     rcx, [rbx+1D0h]; void *
0x18001410f  test    rcx, rcx
0x180014112  jz      short loc_180014120
0x180014114  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014119  mov     [rbx+1D0h], rbp
0x180014120  mov     rcx, [rbx+180h]; hObject
0x180014127  test    rcx, rcx
0x18001412a  jz      short loc_18001413F
0x18001412c  call    cs:__imp_CloseHandle
0x180014133  nop     dword ptr [rax+rax+00h]
0x180014138  mov     [rbx+180h], rbp
0x18001413f  mov     rcx, [rbx+170h]; hObject
0x180014146  test    rcx, rcx
0x180014149  jz      short loc_18001415E
0x18001414b  call    cs:__imp_CloseHandle
0x180014152  nop     dword ptr [rax+rax+00h]
0x180014157  mov     [rbx+170h], rbp
0x18001415e  mov     rdi, [rbx+120h]
0x180014165  test    rdi, rdi
0x180014168  jz      short loc_180014196
0x18001416a  nop     word ptr [rax+rax+00h]
0x180014170  mov     rcx, [rdi+10h]
0x180014174  test    rcx, rcx
0x180014177  jz      short loc_18001418A
0x180014179  mov     rax, [rcx]
0x18001417c  mov     edx, 1
0x180014181  mov     rax, [rax+18h]
0x180014185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001418a  mov     rax, [rdi+8]
0x18001418e  mov     rdi, rax
0x180014191  test    rax, rax
0x180014194  jnz     short loc_180014170
0x180014196  lea     rcx, [rbx+148h]
0x18001419d  call    ?FreeMarshalers@@YAXPEAV?$CGenericList@VCAggregateMarshaler@@@@@Z; FreeMarshalers(CGenericList<CAggregateMarshaler> *)
0x1800141a2  mov     rcx, [rbx+1F8h]; hKey
0x1800141a9  test    rcx, rcx
0x1800141ac  jz      short loc_1800141BA
0x1800141ae  call    cs:__imp_RegCloseKey
0x1800141b5  nop     dword ptr [rax+rax+00h]
0x1800141ba  mov     rcx, [rbx+200h]
0x1800141c1  test    rcx, rcx
0x1800141c4  jz      short loc_1800141D2
0x1800141c6  mov     rax, [rcx]
0x1800141c9  mov     rax, [rax+10h]
0x1800141cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141d2  mov     rcx, [rbx+248h]; bstrString
0x1800141d9  test    rcx, rcx
0x1800141dc  jz      short loc_1800141EA
0x1800141de  call    cs:__imp_SysFreeString
0x1800141e5  nop     dword ptr [rax+rax+00h]
0x1800141ea  cmp     [rbx+208h], rbp
0x1800141f1  jz      short loc_180014244
0x1800141f3  mov     rcx, [rbx+210h]
0x1800141fa  mov     [rbx+230h], ebp
0x180014200  mov     rcx, [rcx]; hEvent
0x180014203  call    cs:__imp_SetEvent
0x18001420a  nop     dword ptr [rax+rax+00h]
0x18001420f  mov     rcx, [rbx+208h]; hHandle
0x180014216  xor     r8d, r8d; bAlertable
0x180014219  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18001421e  call    cs:__imp_WaitForSingleObjectEx
0x180014225  nop     dword ptr [rax+rax+00h]
0x18001422a  mov     rcx, [rbx+208h]; hObject
0x180014231  call    cs:__imp_CloseHandle
0x180014238  nop     dword ptr [rax+rax+00h]
0x18001423d  mov     [rbx+208h], rbp
0x180014244  mov     rax, [rbx+210h]
0x18001424b  test    rax, rax
0x18001424e  jz      short loc_180014289
0x180014250  cmp     [rbx+220h], ebp
0x180014256  jz      short loc_180014276
0x180014258  mov     rcx, [rax]; hObject
0x18001425b  test    rcx, rcx
0x18001425e  jz      short loc_180014276
0x180014260  call    cs:__imp_CloseHandle
0x180014267  nop     dword ptr [rax+rax+00h]
0x18001426c  mov     rax, [rbx+210h]
0x180014273  mov     [rax], rbp
0x180014276  mov     rcx, [rbx+210h]; void *
0x18001427d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014282  mov     [rbx+210h], rbp
0x180014289  mov     rcx, [rbx+218h]; void *
0x180014290  test    rcx, rcx
0x180014293  jz      short loc_1800142A1
0x180014295  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001429a  mov     [rbx+218h], rbp
0x1800142a1  mov     rcx, [rbx+228h]; hObject
0x1800142a8  test    rcx, rcx
0x1800142ab  jz      short loc_1800142C0
0x1800142ad  call    cs:__imp_CloseHandle
0x1800142b4  nop     dword ptr [rax+rax+00h]
0x1800142b9  mov     [rbx+228h], rbp
0x1800142c0  lea     rcx, [rbx+198h]; lpCriticalSection
0x1800142c7  call    cs:__imp_DeleteCriticalSection
0x1800142ce  nop     dword ptr [rax+rax+00h]
0x1800142d3  mov     [rbx+10h], ebp
0x1800142d6  mov     rcx, [rbx+288h]; hObject
0x1800142dd  lea     rax, [rcx-1]
0x1800142e1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800142e5  ja      short loc_1800142F3
0x1800142e7  call    cs:__imp_CloseHandle
0x1800142ee  nop     dword ptr [rax+rax+00h]
0x1800142f3  mov     rcx, [rbx+280h]; hObject
0x1800142fa  test    rcx, rcx
0x1800142fd  jz      short loc_180014313
0x1800142ff  call    cs:__imp_CloseHandle
0x180014306  nop     dword ptr [rax+rax+00h]
0x18001430b  test    eax, eax
0x18001430d  jz      loc_180014514
0x180014313  mov     rcx, [rbx+278h]
0x18001431a  test    rcx, rcx
0x18001431d  jz      short loc_18001432B
0x18001431f  mov     rax, [rcx]
0x180014322  mov     rax, [rax+10h]
0x180014326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001432b  mov     rdi, [rbx+270h]
0x180014332  mov     [rbx+270h], rbp
0x180014339  test    rdi, rdi
0x18001433c  jz      loc_1800143EB
0x180014342  mov     rcx, [rdi]
0x180014345  test    rcx, rcx
0x180014348  jz      short loc_1800143A8
0x18001434a  mov     [rsp+98h+var_68], rbp
  ... truncated ...
```
