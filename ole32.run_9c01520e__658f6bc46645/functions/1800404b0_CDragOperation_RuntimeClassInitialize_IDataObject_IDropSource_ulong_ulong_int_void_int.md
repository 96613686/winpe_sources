# CDragOperation::RuntimeClassInitialize(IDataObject *,IDropSource *,ulong,ulong *,int,void * *,int)

- ea: `0x1800404b0`
- end: `0x18004189d`
- name: `?RuntimeClassInitialize@CDragOperation@@QEAAJPEAUIDataObject@@PEAUIDropSource@@KPEAKHPEAPEAXH@Z`
- size: `5101`
- prototype: `HRESULT __fastcall(CDragOperation *this, IDataObject *pDataObject, IDropSource *pDropSource, unsigned int dwOKEffects, unsigned int *pdwEffect, int fWinRTDrag, void **phClientToken, int fBackgroundContainerDrag)`
- caller_count: `2`
- callee_count: `30`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000aaf0`
- `0x1800921cc`

## callees

- `0x18000a690`
- `0x18000b858`
- `0x18001217c`
- `0x18001ad50`
- `0x18001c300`
- `0x18001e25c`
- `0x1800220b8`
- `0x18002a198`
- `0x18003674c`
- `0x180039564`
- `0x18003c53c`
- `0x1800404b0`
- `0x180042074`
- `0x1800445bc`
- `0x180046460`
- `0x180046854`
- `0x18004ab1c`
- `0x180061854`
- `0x180062038`
- `0x180087a24`
- `0x1800899e4`
- `0x18009217c`
- `0x18009237c`
- `0x180092430`
- `0x180093b9c`
- `0x180093c68`
- `0x180093d94`
- `0x180094558`
- `0x18009464c`
- `0x1800d8010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18004121f`
- `msvcp_win!_Mtx_unlock` at `0x18004126c`
- `msvcp_win!_Mtx_unlock` at `0x18004121f`
- `msvcp_win!_Mtx_unlock` at `0x18004126c`
- `msvcp_win!_Mtx_lock` at `0x18004113d`
- `msvcp_win!_Mtx_lock` at `0x18004113d`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180041152`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004117a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180041152`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004117a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180040cad`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180040cad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040694`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800406cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040861`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040895`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040b50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040b84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040e6d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800415f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180041703`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180041737`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040694`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800406cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040861`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040895`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040b50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040b84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040e6d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800415f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180041703`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180041737`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180040676`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004083c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180040b32`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800416e1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180040676`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004083c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180040b32`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800416e1`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800407af`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800407af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040daa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040e07`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800416a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040daa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040e07`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800416a1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180040d76`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180040d76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800407cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040a0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800407cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040a0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004148d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004148d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180040c89`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180040c89`
- `USER32!SetCapture` at `0x180040f11`
- `USER32!SetCapture` at `0x180040f11`
- `USER32!SetThreadDpiAwarenessContext` at `0x1800410c8`
- `USER32!SetThreadDpiAwarenessContext` at `0x1800410ea`
- `USER32!SetThreadDpiAwarenessContext` at `0x1800410c8`
- `USER32!SetThreadDpiAwarenessContext` at `0x1800410ea`
- `USER32!GetCursor` at `0x180040c0b`
- `USER32!GetCursor` at `0x180040c0b`
- `USER32!GetCursorPos` at `0x1800410db`
- `USER32!GetCursorPos` at `0x1800410db`
- `USER32!GetForegroundWindow` at `0x180041342`
- `USER32!GetForegroundWindow` at `0x180041342`
- `USER32!PeekMessageW` at `0x180040f9a`
- `USER32!PeekMessageW` at `0x180040fca`
- `USER32!PeekMessageW` at `0x180040ff4`
- `USER32!PeekMessageW` at `0x180041029`
- `USER32!PeekMessageW` at `0x180040f9a`
- `USER32!PeekMessageW` at `0x180040fca`
- `USER32!PeekMessageW` at `0x180040ff4`
- `USER32!PeekMessageW` at `0x180041029`
- `USER32!__imp_LogicalToPhysicalDpiPointForWindow` at `0x180041096`
- `USER32!__imp_LogicalToPhysicalDpiPointForWindow` at `0x180041096`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180040d14`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180040d14`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800411d0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800411d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800412a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800414e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004153b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004158e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800412a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800414e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004153b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004158e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800407fd`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800407fd`
- `ext-ms-win-edputil-policy-l1-1-0!EdpFreeContext` at `0x180041527`
- `ext-ms-win-edputil-policy-l1-1-0!EdpFreeContext` at `0x18004156e`
- `ext-ms-win-edputil-policy-l1-1-0!EdpFreeContext` at `0x180041527`
- `ext-ms-win-edputil-policy-l1-1-0!EdpFreeContext` at `0x18004156e`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForProcess` at `0x18004149e`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForProcess` at `0x18004149e`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x180040609`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x180040609`

## string_xrefs

- `0x180041283`: `com\ole32\ole232\drag\drag.cpp`
- `0x1800412f2`: `com\ole32\ole232\drag\drag.cpp`
- `0x180041506`: `com\ole32\ole232\drag\drag.cpp`
- `0x1800411e9`: `com\ole32\ole232\drag\hostdragoperation.cpp`

## pseudocode

```c
__int64 __fastcall CDragOperation::RuntimeClassInitialize(
        CDragOperation *this,
        _RTL_SRWLOCK *pDataObject,
        IDropSource *pDropSource,
        unsigned int dwOKEffects,
        unsigned int *pdwEffect,
        int fWinRTDrag,
        void **phClientToken,
        int fBackgroundContainerDrag)
{
  unsigned int v8; // ebx
  PSRWLOCK v10; // r13
  signed int v12; // esi
  char v13; // di
  wil::details::shared_object<wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType> >::RefAndObject *m_pCopy; // rax
  wil::srwlock *p_m_lock; // rbx
  wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType> *m_pActivityData; // rdx
  HRESULT hr; // ecx
  int m_stopCountExpected; // eax
  wil::details::shared_object<wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType> >::RefAndObject *v19; // rbx
  HANDLE Event; // rax
  DWORD v21; // eax
  _TOKEN_INFORMATION_CLASS v22; // edx
  char v23; // di
  wil::srwlock *v24; // rbx
  wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType> *v25; // rdx
  HRESULT v26; // ecx
  int v27; // eax
  int WinRtExtension; // eax
  EDP_CONTEXT *m_ptr; // rbx
  IUnknown *ptr; // rcx
  __int64 (__fastcall *v32)(EDP_CONTEXT *, Microsoft::WRL::ComPtr<IUnknown> *); // r13
  signed int v33; // eax
  EDP_CONTEXT *v34; // rcx
  signed int LastError; // eax
  void *v36; // rcx
  _MCGEN_TRACE_CONTEXT *v37; // rcx
  const _GUID *v38; // r8
  char v39; // di
  wil::srwlock *v40; // rbx
  unsigned int *p_dwEffect; // rax
  bool v42; // zf
  HRESULT v43; // eax
  unsigned int v44; // r15d
  unsigned int cbBufferSize; // edx
  CDragDefaultCursors *v46; // rax
  char v47; // bl
  wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType> *v48; // rdx
  HRESULT v49; // ecx
  int v50; // eax
  HWND PrivateClipboardWindow; // rax
  void *SharedDragFormats; // rax
  CDragOperation *v53; // rbx
  unsigned __int64 v54; // rcx
  unsigned __int16 ControlKeysState; // ax
  __int64 v56; // rbx
  IDropTarget *v57; // rcx
  __int64 (__fastcall ***v58)(_QWORD, GUID *, Microsoft::WRL::ComPtr<IDropTarget> *); // rcx
  int Instance; // eax
  HRESULT v60; // ebx
  __int64 (__fastcall ***v61)(_QWORD, GUID *, Microsoft::WRL::ComPtr<IDropTarget> *); // rcx
  HRESULT v62; // eax
  __int64 (__fastcall ***v63)(_QWORD, GUID *, Microsoft::WRL::ComPtr<IDropTarget> *); // rcx
  unsigned __int16 dwAspect; // si
  unsigned int v65; // edx
  IDragDropContainerProxy *v66; // rcx
  unsigned int ForegroundWindow; // eax
  IDragDropContainerProxy *v68; // rcx
  IDataObject v69; // rax
  ULONG (__stdcall *Release)(IUnknown *); // rax
  int v71; // eax
  wchar_t *pszStringData; // rsi
  wchar_t *v73; // rdx
  IDataObject v74; // rax
  ULONG (__stdcall *v75)(IUnknown *); // rax
  int v76; // eax
  EDP_CONTEXT **v77; // rbx
  DWORD CurrentProcessId; // eax
  int ContextForProcess; // eax
  unsigned __int64 v80; // r8
  EDP_CONTEXT *v81; // rcx
  wchar_t *enterpriseIdForUIEnforcement; // rdx
  char v83; // bl
  HRESULT v84; // edx
  char v85; // di
  wil::srwlock *v86; // rbx
  wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType> *v87; // rdx
  HRESULT v88; // ecx
  int v89; // eax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int cbData[2]; // [rsp+38h] [rbp-C8h] BYREF
  Microsoft::WRL::ComPtr<IDragDropContainerProxy> proxy; // [rsp+40h] [rbp-C0h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (__cdecl*)(EDP_CONTEXT *),&EdpFreeContext,wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t> > > edpContext; // [rsp+48h] [rbp-B8h] BYREF
  tagPOINT pt; // [rsp+50h] [rbp-B0h] BYREF
  CWriteInterfaceDataMarshalingStream objectStream; // [rsp+58h] [rbp-A8h] BYREF
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short> > spszDataFormats; // [rsp+88h] [rbp-78h] BYREF
  wil::FailureInfo failure; // [rsp+A0h] [rbp-60h] BYREF
  DragDropTelemetry::DragDropSession_Initialize dndInitActivity; // [rsp+140h] [rbp+40h] BYREF
  _EVENT_DATA_DESCRIPTOR Descriptor; // [rsp+290h] [rbp+190h] BYREF
  tagFORMATETC formatetc; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int128 v101; // [rsp+2C0h] [rbp+1C0h]
  void *retaddr; // [rsp+318h] [rbp+218h]

  dndInitActivity.m_activityData.m_callContext.contextName = "DragDropSession_Initialize";
  SRWLock = pDataObject;
  dndInitActivity.m_activityData.m_State = TlgStateCreated;
  v8 = dwOKEffects;
  dndInitActivity.m_activityData.m_lock.m_lock.Value = 0;
  cbData[0] = dwOKEffects;
  dndInitActivity.m_pActivityData = &dndInitActivity.m_activityData;
  dndInitActivity.m_activityData.m_HasRelatedId = 0;
  dndInitActivity.m_callbackHolder.m_pCallback = &dndInitActivity;
  v10 = pDataObject;
  dndInitActivity.m_activityData.m_callContext.m_ownsMessage = 0;
  dndInitActivity.m_callbackHolder.m_pCallContext = &dndInitActivity.m_activityData.m_callContext;
  dndInitActivity.m_activityData.m_callContext.contextId = 0;
  dndInitActivity.__vftable = (DragDropTelemetry::DragDropSession_Initialize_vtbl *)DragDropTelemetry::DragDropSession_Initialize::`vftable';
  dndInitActivity.m_activityData.m_callContext.contextMessage = 0;
  dndInitActivity.m_activityData.m_result = 0;
  memset(&dndInitActivity.m_activityData.m_failure, 0, sizeof(dndInitActivity.m_activityData.m_failure));
  dndInitActivity.m_activityData.m_stopCountExpected = 1;
  dndInitActivity.m_sharedActivityData.m_pCopy = 0;
  dndInitActivity.m_callbackHolder.m_ppThreadList = 0;
  dndInitActivity.m_callbackHolder.m_pNext = 0;
  dndInitActivity.m_callbackHolder.m_threadId = 0;
  DragDropTelemetry::DragDropSession_Initialize::StartActivity(&dndInitActivity, L"DragOperationInit", L"OleDragDrop");
  g_forcedDropTarget._fDragDropActive = 1;
  g_forcedDropTarget._hwndFDTCurrent = 0;
  if ( fWinRTDrag || !(unsigned int)EdpGetIsManaged() )
  {
    this->m_isEdpActive = 0;
    if ( fWinRTDrag )
      goto LABEL_27;
  }
  else
  {
    this->m_isEdpActive = 1;
  }
  if ( !v10 )
  {
    v12 = -2147024809;
    wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
      &dndInitActivity,
      -2147024809);
    dndInitActivity.__vftable = (DragDropTelemetry::DragDropSession_Initialize_vtbl *)DragDropTelemetry::DragDropSession_Initialize::`vftable';
    v13 = 1;
    m_pCopy = dndInitActivity.m_sharedActivityData.m_pCopy;
    if ( !dndInitActivity.m_sharedActivityData.m_pCopy )
      goto LABEL_13;
    p_m_lock = &dndInitActivity.m_sharedActivityData.m_pCopy->m_object.m_lock;
    AcquireSRWLockExclusive(&dndInitActivity.m_sharedActivityData.m_pCopy->m_object.m_lock.m_lock);
    SRWLock = 0;
    m_pCopy = dndInitActivity.m_sharedActivityData.m_pCopy;
    if ( !dndInitActivity.m_sharedActivityData.m_pCopy || dndInitActivity.m_sharedActivityData.m_pCopy->m_refCount != 1 )
    {
      v13 = 0;
      wil::details::shared_object<wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&dndInitActivity.m_sharedActivityData);
      m_pCopy = dndInitActivity.m_sharedActivityData.m_pCopy;
    }
    if ( p_m_lock )
    {
      ReleaseSRWLockExclusive(&p_m_lock->m_lock);
      m_pCopy = dndInitActivity.m_sharedActivityData.m_pCopy;
    }
    if ( v13 )
    {
LABEL_13:
      m_pActivityData = dndInitActivity.m_pActivityData;
      if ( dndInitActivity.m_pActivityData->m_State == TlgStateStarted )
      {
        hr = -2147024322;
        if ( dndInitActivity.m_pActivityData->m_failure.m_failureInfo.hr < 0 )
          hr = dndInitActivity.m_pActivityData->m_failure.m_failureInfo.hr;
        m_stopCountExpected = dndInitActivity.m_pActivityData->m_stopCountExpected;
        if ( m_stopCountExpected < 1 )
        {
          memset(&failure, 0, sizeof(failure));
          wil::details::WilFailFast(&failure);
        }
        if ( dndInitActivity.m_pActivityData->m_result >= 0 )
          dndInitActivity.m_pActivityData->m_result = hr;
        m_pActivityData->m_stopCountExpected = m_stopCountExpected - 1;
        dndInitActivity.StopActivity(&dndInitActivity);
        m_pCopy = dndInitActivity.m_sharedActivityData.m_pCopy;
      }
    }
    if ( dndInitActivity.m_callbackHolder.m_threadId )
    {
      wil::details::ThreadFailureCallbackHolder::StopWatching(&dndInitActivity.m_callbackHolder);
      m_pCopy = dndInitActivity.m_sharedActivityData.m_pCopy;
    }
    if ( m_pCopy )
    {
      if ( _InterlockedExchangeAdd(&m_pCopy->m_refCount, 0xFFFFFFFF) == 1 )
      {
        v19 = dndInitActivity.m_sharedActivityData.m_pCopy;
        if ( dndInitActivity.m_sharedActivityData.m_pCopy )
        {
          wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>(&dndInitActivity.m_sharedActivityData.m_pCopy->m_object);
          operator delete(v19, 0x110u);
        }
      }
      dndInitActivity.m_sharedActivityData.m_pCopy = 0;
    }
LABEL_48:
    wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>(&dndInitActivity.m_activityData);
    return (unsigned int)v12;
  }
LABEL_27:
  Event = CreateEventExW(0, L"Local\\OLEDragSynchronizationMutex", 0, 0x1F0003u);
  this->_hDragInProgress = Event;
  if ( !Event )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
LABEL_65:
    if ( v12 < 0 )
      goto LABEL_31;
    goto LABEL_66;
  }
  v21 = GetLastError();
  this->_fConcurrentDrag = v21 == 183;
  if ( v21 != 183 )
  {
    if ( !fWinRTDrag )
      CDragOperation::s_fDoDragDropInFlight = 1;
    edpContext.m_ptr = 0;
    WinRtExtension = CDragOperation::GetWinRtExtension(this, (IDragDropExtensionForOLE **)&edpContext);
    v12 = WinRtExtension;
    if ( WinRtExtension < 0 )
    {
      if ( WinRtExtension == -2147221164 || (unsigned int)(WinRtExtension + 2147024894) <= 1 )
        v12 = 0;
    }
    else
    {
      m_ptr = edpContext.m_ptr;
      ptr = this->_spWinRtExclusionToken.ptr_;
      v32 = *(__int64 (__fastcall **)(EDP_CONTEXT *, Microsoft::WRL::ComPtr<IUnknown> *))(*(_QWORD *)&edpContext.m_ptr->contextStates
                                                                                        + 48LL);
      if ( ptr )
      {
        this->_spWinRtExclusionToken.ptr_ = 0;
        ((void (__fastcall *)(IUnknown *))ptr->lpVtbl->Release)(ptr);
      }
      v33 = v32(m_ptr, &this->_spWinRtExclusionToken);
      v10 = SRWLock;
      v12 = v33;
      v8 = cbData[0];
    }
    v34 = edpContext.m_ptr;
    if ( edpContext.m_ptr )
    {
      edpContext.m_ptr = 0;
      (*(void (__fastcall **)(EDP_CONTEXT *))(*(_QWORD *)&v34->contextStates + 16LL))(v34);
    }
    goto LABEL_65;
  }
  if ( fWinRTDrag || !CDragOperation::s_fDoDragDropInFlight && !IsContainerDragOperation() )
  {
    v12 = -2147221245;
    RoOriginateError(2147746051LL, 0);
LABEL_31:
    wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(&dndInitActivity, v12);
    v23 = 1;
    dndInitActivity.__vftable = (DragDropTelemetry::DragDropSession_Initialize_vtbl *)DragDropTelemetry::DragDropSession_Initialize::`vftable';
    if ( dndInitActivity.m_sharedActivityData.m_pCopy )
    {
      v24 = &dndInitActivity.m_sharedActivityData.m_pCopy->m_object.m_lock;
      AcquireSRWLockExclusive(&dndInitActivity.m_sharedActivityData.m_pCopy->m_object.m_lock.m_lock);
      Descriptor.Ptr = 0;
      if ( !dndInitActivity.m_sharedActivityData.m_pCopy
        || dndInitActivity.m_sharedActivityData.m_pCopy->m_refCount != 1 )
      {
        v23 = 0;
        wil::details::shared_object<wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&dndInitActivity.m_sharedActivityData);
      }
      if ( v24 )
        ReleaseSRWLockExclusive(&v24->m_lock);
      if ( !v23 )
        goto LABEL_45;
    }
    v25 = dndInitActivity.m_pActivityData;
    if ( dndInitActivity.m_pActivityData->m_State != TlgStateStarted )
      goto LABEL_45;
    v26 = -2147024322;
    if ( dndInitActivity.m_pActivityData->m_failure.m_failureInfo.hr < 0 )
      v26 = dndInitActivity.m_pActivityData->m_failure.m_failureInfo.hr;
    v27 = dndInitActivity.m_pActivityData->m_stopCountExpected;
    if ( v27 < 1 )
    {
      memset(&failure, 0, sizeof(failure));
      wil::details::WilFailFast(&failure);
    }
LABEL_42:
    if ( v25->m_result >= 0 )
      v25->m_result = v26;
    v25->m_stopCountExpected = v27 - 1;
    dndInitActivity.StopActivity(&dndInitActivity);
LABEL_45:
    if ( dndInitActivity.m_callbackHolder.m_threadId )
      wil::details::ThreadFailureCallbackHolder::StopWatching(&dndInitActivity.m_callbackHolder);
    wil::details::shared_object<wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&dndInitActivity.m_sharedActivityData);
    goto LABEL_48;
  }
LABEL_66:
  if ( phClientToken )
    v36 = *phClientToken;
  else
    v36 = 0;
  v12 = IsTokenBoolPresent(v36, v22, &this->_fSourceIsAppContainer);
  if ( v12 < 0 )
    goto LABEL_31;
  this->_fWinRTDrag = fWinRTDrag;
  this->m_backgroundContainerDrag = fBackgroundContainerDrag != 0;
  if ( phClientToken )
  {
    this->_hDragSourceToken = *phClientToken;
    *phClientToken = 0;
  }
  if ( (Microsoft_Windows_OLE_PerfEnableBits[0] & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v37, &OLE_DragDrop_DragOperation_SetDataObject_Start, v38, 1u, &Descriptor);
  v12 = 0;
  if ( this->_pDataObject || this->_fDropCompleted )
  {
    v12 = -2147483634;
  }
  else if ( v10 )
  {
    this->_pDataObject = (IDataObject *)v10;
    (*(void (__fastcall **)(PSRWLOCK))(v10->Value + 8))(v10);
  }
  else
  {
    v12 = -2147024809;
  }
  if ( (Microsoft_Windows_OLE_PerfEnableBits[0] & 1) != 0 )
    McTemplateU0d_EventWriteTransfer(v37, &OLE_DragDrop_DragOperation_SetDataObject_Stop, v12);
  if ( v12 < 0 )
  {
    wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(&dndInitActivity, v12);
    v39 = 1;
    dndInitActivity.__vftable = (DragDropTelemetry::DragDropSession_Initialize_vtbl *)DragDropTelemetry::DragDropSession_Initialize::`vftable';
    if ( dndInitActivity.m_sharedActivityData.m_pCopy )
    {
      v40 = &dndInitActivity.m_sharedActivityData.m_pCopy->m_object.m_lock;
      AcquireSRWLockExclusive(&dndInitActivity.m_sharedActivityData.m_pCopy->m_object.m_lock.m_lock);
      SRWLock = 0;
      if ( !dndInitActivity.m_sharedActivityData.m_pCopy
        || dndInitActivity.m_sharedActivityData.m_pCopy->m_refCount != 1 )
      {
        v39 = 0;
        wil::details::shared_object<wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&dndInitActivity.m_sharedActivityData);
      }
      if ( v40 )
        ReleaseSRWLockExclusive(&v40->m_lock);
      if ( !v39 )
        goto LABEL_45;
    }
    v25 = dndInitActivity.m_pActivityData;
    if ( dndInitActivity.m_pActivityData->m_State != TlgStateStarted )
      goto LABEL_45;
    v26 = -2147024322;
    if ( dndInitActivity.m_pActivityData->m_failure.m_failureInfo.hr < 0 )
      v26 = dndInitActivity.m_pActivityData->m_failure.m_failureInfo.hr;
    v27 = dndInitActivity.m_pActivityData->m_stopCountExpected;
    if ( v27 < 1 )
    {
      memset(&failure, 0, sizeof(failure));
      wil::details::WilFailFast(&failure);
    }
    goto LABEL_42;
  }
  this->_pDropSource = pDropSource;
  if ( pDropSource && this->_fWinRTDrag )
    ((void (__fastcall *)(IDropSource *))pDropSource->lpVtbl->AddRef)(pDropSource);
  p_dwEffect = pdwEffect;
  this->_dwOKEffects = v8;
  if ( !pdwEffect )
    p_dwEffect = &this->_dwEffect;
  v42 = this->_fWinRTDrag == 0;
  this->_pdwEffect = p_dwEffect;
  if ( v42 )
    this->_curOld = GetCursor();
  this->_cptFinalCursorPos = 0;
  if ( pDropSource )
    ((void (__fastcall *)(IDropSource *, GUID *, IDropSourceNotify **))pDropSource->lpVtbl->QueryInterface)(
      pDropSource,
      &GUID_0000012b_0000_0000_c000_000000000046,
      &this->_pDSNotify);
  if ( (CDragOperation::s_wScrollInt & 0x80000000) != 0 )
  {
    CDragOperation::s_wScrollInt = 50;
    cbData[0] = 40;
    if ( !RegQueryValueExW(
            HKEY_CURRENT_USER,
            L"Control Panel\\Mouse\\DragScrollDelay",
            0,
            0,
            (LPBYTE)&formatetc,
            cbData) )
    {
      WORD4(v101) = 0;
      CDragOperation::s_wScrollInt = wcstol(&formatetc.cfFormat, 0, 0);
    }
  }
  *((_DWORD *)&objectStream._cRefs + 1) = 0;
  objectStream.lpVtbl = (struct IStreamVtbl *)CReadInterfaceDataFromInternalSourceMarshalingStream::`vftable';
  objectStream._cRefs = 1;
  *(_QWORD *)&objectStream._lOffset = 0;
  objectStream._cbBufferSize = 0;
  objectStream._pMInterfacePointer = 0;
  objectStream._fFree = 1;
  v43 = CoMarshalInterface(&objectStream, &IID_IDataObject, (LPUNKNOWN)v10, 1u, 0, 1u);
  v44 = v43;
  if ( v43 )
  {
    wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(&dndInitActivity, v43);
    objectStream.lpVtbl = (struct IStreamVtbl *)CBaseMInterfacePointerMarshalingStream::`vftable';
    if ( objectStream._fFree )
      HeapFree(g_hHeap, 0, objectStream._pMInterfacePointer);
    v85 = 1;
    objectStream.lpVtbl = (struct IStreamVtbl *)CAbstractStream::`vftable';
    dndInitActivity.__vftable = (DragDropTelemetry::DragDropSession_Initialize_vtbl *)DragDropTelemetry::DragDropSession_Initialize::`vftable';
    if ( dndInitActivity.m_sharedActivityData.m_pCopy )
    {
      v86 = &dndInitActivity.m_sharedActivityData.m_pCopy->m_object.m_lock;
      AcquireSRWLockExclusive(&dndInitActivity.m_sharedActivityData.m_pCopy->m_object.m_lock.m_lock);
      Descriptor.Ptr = 0;
      if ( !dndInitActivity.m_sharedActivityData.m_pCopy
        || dndInitActivity.m_sharedActivityData.m_pCopy->m_refCount != 1 )
      {
        v85 = 0;
        wil::details::shared_object<wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&dndInitActivity.m_sharedActivityData);
      }
      if ( v86 )
        ReleaseSRWLockExclusive(&v86->m_lock);
      if ( !v85 )
        goto LABEL_211;
    }
    v87 = dndInitActivity.m_pActivityData;
    if ( dndInitActivity.m_pActivityData->m_State != TlgStateStarted )
      goto LABEL_211;
    v88 = -2147024322;
    if ( dndInitActivity.m_pActivityData->m_failure.m_failureInfo.hr < 0 )
      v88 = dndInitActivity.m_pActivityData->m_failure.m_failureInfo.hr;
    v89 = dndInitActivity.m_pActivityData->m_stopCountExpected;
    if ( v89 < 1 )
    {
      memset(&failure, 0, sizeof(failure));
      wil::details::WilFailFast(&failure);
    }
    if ( dndInitActivity.m_pActivityData->m_result >= 0 )
      dndInitActivity.m_pActivityData->m_result = v88;
    v87->m_stopCountExpected = v89 - 1;
    goto LABEL_210;
  }
  cbBufferSize = objectStream._cbBufferSize;
  if ( objectStream._cbDataSize )
    cbBufferSize = objectStream._cbDataSize;
  objectStream._pMInterfacePointer->ulCntData = cbBufferSize;
  this->_DOBuffer = (tagInterfaceData *)objectStream._pMInterfacePointer;
  objectStream._pMInterfacePointer = 0;
  objectStream._fFree = 0;
  if ( !this->_fWinRTDrag )
  {
    v46 = cddcDefault32;
    if ( !cddcDefault32 )
    {
      v46 = (CDragDefaultCursors *)HeapAlloc(g_hHeap, 0, v44 + 64);
      cddcDefault32 = v46;
      if ( v46 )
      {
        if ( CDragDefaultCursors::Init(v46) )
        {
          v46 = cddcDefault32;
        }
        else
        {
          HeapFree(g_hHeap, 0, cddcDefault32);
          v46 = 0;
          cddcDefault32 = 0;
        }
      }
    }
    this->_pcddcDefault = v46;
    if ( !v46 )
    {
      wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        &dndInitActivity,
        -2147467259);
      objectStream.lpVtbl = (struct IStreamVtbl *)CBaseMInterfacePointerMarshalingStream::`vftable';
      if ( objectStream._fFree )
        HeapFree(g_hHeap, 0, objectStream._pMInterfacePointer);
      objectStream.lpVtbl = (struct IStreamVtbl *)CAbstractStream::`vftable';
      v47 = 1;
      dndInitActivity.__vftable = (DragDropTelemetry::DragDropSession_Initialize_vtbl *)DragDropTelemetry::DragDropSession_Initialize::`vftable';
      if ( !dndInitActivity.m_sharedActivityData.m_pCopy )
        goto LABEL_126;
      wil::ActivityBase<DragDropLogging,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        &dndInitActivity,
        (wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (__cdecl*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive,wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t> > > *)&SRWLock);
      if ( !dndInitActivity.m_sharedActivityData.m_pCopy
        || dndInitActivity.m_sharedActivityData.m_pCopy->m_refCount != 1 )
      {
        v47 = 0;
        wil::details::shared_object<wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&dndInitActivity.m_sharedActivityData);
      }
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
      if ( v47 )
      {
LABEL_126:
        v48 = dndInitActivity.m_pActivityData;
        if ( dndInitActivity.m_pActivityData->m_State == TlgStateStarted )
        {
          v49 = -2147024322;
          if ( dndInitActivity.m_pActivityData->m_failure.m_failureInfo.hr < 0 )
            v49 = dndInitActivity.m_pActivityData->m_failure.m_failureInfo.hr;
          v50 = dndInitActivity.m_pActivityData->m_stopCountExpected;
          if ( v50 < 1 )
          {
            memset(&failure, 0, sizeof(failure));
            wil::details::WilFailFast(&failure);
          }
          if ( dndInitActivity.m_pActivityData->m_result >= 0 )
            dndInitActivity.m_pActivityData->m_result = v49;
          v48->m_stopCountExpected = v50 - 1;
          dndInitActivity.StopActivity(&dndInitActivity);
        }
      }
      if ( dndInitActivity.m_callbackHolder.m_threadId )
        wil::details::ThreadFailureCallbackHolder::StopWatching(&dndInitActivity.m_callbackHolder);
      wil::details::shared_object<wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&dndInitActivity.m_sharedActivityData);
      wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>(&dndInitActivity.m_activityData);
      return 2147500037LL;
    }
    PrivateClipboardWindow = GetPrivateClipboardWindow(CLIP_CREATEIFNOTTHERE);
    if ( !PrivateClipboardWindow )
    {
      this->_fMouseCaptured = 0;
      wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        &dndInitActivity,
        -2147467259);
      CBaseMInterfacePointerMarshalingStream::~CBaseMInterfacePointerMarshalingStream(&objectStream);
      DragDropTelemetry::DragDropSession_Initialize::~DragDropSession_Initialize(&dndInitActivity);
      return 2147500037LL;
    }
    SetCapture(PrivateClipboardWindow);
    v44 = 0;
    this->_fMouseCaptured = 1;
  }
  spszDataFormats._pszStringData = 0;
  spszDataFormats._cchStringData = -1;
  spszDataFormats._cchStringDataCapacity = -1;
  SharedDragFormats = CreateSharedDragFormats((IDataObject *)v10, &spszDataFormats._pszStringData);
  v42 = this->_fWinRTDrag == 0;
  this->_hFormats = SharedDragFormats;
  if ( v42 && !this->m_backgroundContainerDrag )
  {
    memset(&formatetc, 0, sizeof(formatetc));
    v101 = 0;
    if ( !PeekMessageW((LPMSG)&formatetc, 0, 0x200u, 0x20Eu, 1u) )
    {
      while ( !PeekMessageW((LPMSG)&formatetc, 0, 0x100u, 0x100u, 1u)
           && !PeekMessageW((LPMSG)&formatetc, 0, 0x104u, 0x104u, 1u)
           || *(_QWORD *)&formatetc.dwAspect != 27 )
      {
        if ( PeekMessageW((LPMSG)&formatetc, 0, 0x200u, 0x20Eu, 1u) )
          goto LABEL_148;
      }
      this->_fEscapePressed = 1;
    }
LABEL_148:
    if ( this->_fEscapePressed )
    {
      v56 = SetThreadDpiAwarenessContext(-3);
      GetCursorPos(&this->_cpt._pt);
      SetThreadDpiAwarenessContext(v56);
      v53 = this;
      ControlKeysState = GetControlKeysState(1);
    }
    else
    {
      pt = *(tagPOINT *)((char *)&v101 + 4);
      LogicalToPhysicalDpiPointForWindow(*(_QWORD *)&formatetc.cfFormat, &pt);
      v53 = this;
      v54 = *(_QWORD *)&formatetc.dwAspect;
      this->_cpt._pt = pt;
      ControlKeysState = GetControlKeysStateOfParam(v54);
    }
    v53->_grfKeyState = ControlKeysState;
    if ( IsContainerDragOperation() )
    {
      v57 = this->m_nonRPCSSRegisteredDropTarget.ptr_;
      if ( v57 )
      {
        this->m_nonRPCSSRegisteredDropTarget.ptr_ = 0;
        ((void (__fastcall *)(IDropTarget *))v57->lpVtbl->Release)(v57);
      }
      this->m_nonRPCSSRegisteredDropTarget.ptr_ = 0;
      if ( _Mtx_lock(&g_containerProxyLock._Mtx_storage) )
      {
        std::_Throw_Cpp_error(5);
        __debugbreak();
      }
      if ( g_containerProxyLock._Mtx_storage._Count == 0x7FFFFFFF )
      {
        g_containerProxyLock._Mtx_storage._Count = 2147483646;
        std::_Throw_Cpp_error(6);
        __debugbreak();
      }
      *(_QWORD *)cbData = g_containerProxy;
      if ( !g_containerProxy
        || (((void (__fastcall *)(IDragDropContainerProxy *))g_containerProxy->lpVtbl->AddRef)(g_containerProxy),
            (v58 = *(__int64 (__fastcall ****)(_QWORD, GUID *, Microsoft::WRL::ComPtr<IDropTarget> *))cbData) == 0) )
      {
        Instance = CoCreateInstance(
                     &CLSID_HostOperationDropTarget,
                     0,
                     1u,
                     &GUID_e2f15d97_b5f6_4e82_a44b_1c0d664999f3,
                     (LPVOID *)cbData);
        v60 = Instance;
        if ( Instance < 0 )
        {
          wil::details::in1diag3::Return_Hr(retaddr, 0x34u, "com\\ole32\\ole232\\drag\\hostdragoperation.cpp", Instance);
          v61 = *(__int64 (__fastcall ****)(_QWORD, GUID *, Microsoft::WRL::ComPtr<IDropTarget> *))cbData;
          if ( *(_QWORD *)cbData )
          {
            *(_QWORD *)cbData = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, Microsoft::WRL::ComPtr<IDropTarget> *)))(*v61)[2])(v61);
          }
          _Mtx_unlock(&g_containerProxyLock._Mtx_storage);
LABEL_168:
          wil::details::in1diag3::Return_Hr(retaddr, 0x5DEu, "com\\ole32\\ole232\\drag\\drag.cpp", v60);
LABEL_169:
          if ( spszDataFormats._pszStringData )
            CoTaskMemFree(spszDataFormats._pszStringData);
          CBaseMInterfacePointerMarshalingStream::~CBaseMInterfacePointerMarshalingStream(&objectStream);
          DragDropTelemetry::DragDropSession_Initialize::~DragDropSession_Initialize(&dndInitActivity);
          return (unsigned int)v60;
        }
        v58 = *(__int64 (__fastcall ****)(_QWORD, GUID *, Microsoft::WRL::ComPtr<IDropTarget> *))cbData;
      }
      v62 = (**v58)(v58, &GUID_00000122_0000_0000_c000_000000000046, &this->m_nonRPCSSRegisteredDropTarget);
      v63 = *(__int64 (__fastcall ****)(_QWORD, GUID *, Microsoft::WRL::ComPtr<IDropTarget> *))cbData;
      v60 = v62;
      if ( *(_QWORD *)cbData )
      {
        *(_QWORD *)cbData = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, Microsoft::WRL::ComPtr<IDropTarget> *)))(*v63)[2])(v63);
      }
      _Mtx_unlock(&g_containerProxyLock._Mtx_storage);
      if ( v60 < 0 )
        goto LABEL_168;
      dwAspect = formatetc.dwAspect;
      proxy.ptr_ = 0;
      v60 = Microsoft::WRL::ComPtr<IDropTarget>::As<IDragDropContainerProxy>(
              &this->m_nonRPCSSRegisteredDropTarget,
              (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDragDropContainerProxy> >)&proxy);
      if ( v60 < 0 )
      {
        v65 = 1511;
        goto LABEL_174;
      }
      v60 = ((__int64 (__fastcall *)(IDragDropContainerProxy *, _QWORD))proxy.ptr_->lpVtbl[1].QueryInterface)(
              proxy.ptr_,
              dwAspect);
      if ( v60 < 0 )
      {
        v65 = 1512;
        goto LABEL_174;
      }
      ForegroundWindow = (unsigned int)GetForegroundWindow();
      v60 = ((__int64 (__fastcall *)(IDragDropContainerProxy *, _QWORD))proxy.ptr_->lpVtbl[1].AddRef)(
              proxy.ptr_,
              ForegroundWindow);
      if ( v60 < 0 )
      {
        v65 = 1517;
LABEL_174:
        wil::details::in1diag3::Return_Hr(retaddr, v65, "com\\ole32\\ole232\\drag\\drag.cpp", v60);
        v66 = proxy.ptr_;
        if ( proxy.ptr_ )
        {
          proxy.ptr_ = 0;
          ((void (__fastcall *)(IDragDropContainerProxy *))v66->lpVtbl->Release)(v66);
        }
        goto LABEL_169;
      }
      v68 = proxy.ptr_;
      if ( proxy.ptr_ )
      {
        proxy.ptr_ = 0;
        ((void (__fastcall *)(IDragDropContainerProxy *))v68->lpVtbl->Release)(v68);
      }
    }
  }
  *(_DWORD *)(&formatetc.cfFormat + 1) = 0;
  formatetc.cfFormat = 15;
  v69.lpVtbl = (struct IUnknownVtbl *)v10->Value;
  *(&formatetc.cfFormat + 3) = 0;
  *(_QWORD *)&formatetc.tymed = 1;
  formatetc.ptd = 0;
  Release = v69.lpVtbl[1].Release;
  formatetc.lindex = -1;
  formatetc.dwAspect = 1;
  v71 = ((__int64 (__fastcall *)(PSRWLOCK, tagFORMATETC *))Release)(v10, &formatetc);
  pszStringData = spszDataFormats._pszStringData;
  v73 = spszDataFormats._pszStringData;
  this->m_hasHDROPClipboardFormat = v71 == 0;
  DragDropTelemetry::DragDropSession::DragStarted(&this->_telemetrySession, v73);
  if ( this->m_isEdpActive )
  {
    formatetc.cfFormat = g_cfEnterpriseDataProtectionId;
    v74.lpVtbl = (struct IUnknownVtbl *)v10->Value;
    *(_DWORD *)(&formatetc.cfFormat + 1) = 0;
    *(&formatetc.cfFormat + 3) = 0;
    *(_QWORD *)&formatetc.tymed = 1;
    v75 = v74.lpVtbl[1].Release;
    formatetc.ptd = 0;
    formatetc.lindex = -1;
    formatetc.dwAspect = 1;
    v76 = ((__int64 (__fastcall *)(PSRWLOCK, tagFORMATETC *))v75)(v10, &formatetc);
    edpContext.m_ptr = 0;
    this->m_dataObjectHasEnterpriseId = v76 == 0;
    v77 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>>::operator&(&edpContext);
    CurrentProcessId = GetCurrentProcessId();
    ContextForProcess = EdpGetContextForProcess(CurrentProcessId, v77);
    v81 = edpContext.m_ptr;
    if ( ContextForProcess >= 0 )
    {
      enterpriseIdForUIEnforcement = edpContext.m_ptr->enterpriseIdForUIEnforcement;
      if ( enterpriseIdForUIEnforcement )
      {
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          (wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > *)&SRWLock,
          enterpriseIdForUIEnforcement,
          v80);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          &this->m_sourceEnterpriseId,
          (wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > *)&SRWLock);
        if ( SRWLock )
          CoTaskMemFree(SRWLock);
        if ( !this->m_sourceEnterpriseId.m_ptr )
        {
          wil::details::in1diag3::Return_Hr(retaddr, 0x606u, "com\\ole32\\ole232\\drag\\drag.cpp", -2147024882);
          if ( edpContext.m_ptr )
            EdpFreeContext();
          if ( pszStringData )
            CoTaskMemFree(pszStringData);
          CBaseMInterfacePointerMarshalingStream::~CBaseMInterfacePointerMarshalingStream(&objectStream);
          DragDropTelemetry::DragDropSession_Initialize::~DragDropSession_Initialize(&dndInitActivity);
          return 2147942414LL;
        }
        v81 = edpContext.m_ptr;
      }
    }
    if ( v81 )
      EdpFreeContext();
  }
  wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(&dndInitActivity, v44);
  if ( pszStringData )
    CoTaskMemFree(pszStringData);
  CBaseMInterfacePointerMarshalingStream::~CBaseMInterfacePointerMarshalingStream(&objectStream);
  dndInitActivity.__vftable = (DragDropTelemetry::DragDropSession_Initialize_vtbl *)DragDropTelemetry::DragDropSession_Initialize::`vftable';
  v83 = 1;
  if ( !dndInitActivity.m_sharedActivityData.m_pCopy )
    goto LABEL_206;
  wil::ActivityBase<DragDropLogging,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    &dndInitActivity,
    (wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (__cdecl*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive,wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t> > > *)&Descriptor);
  if ( !dndInitActivity.m_sharedActivityData.m_pCopy || dndInitActivity.m_sharedActivityData.m_pCopy->m_refCount != 1 )
  {
    v83 = 0;
    wil::details::shared_object<wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&dndInitActivity.m_sharedActivityData);
  }
  if ( Descriptor.Ptr )
    ReleaseSRWLockExclusive((PSRWLOCK)Descriptor.Ptr);
  if ( v83 )
  {
LABEL_206:
    if ( dndInitActivity.m_pActivityData->m_State == TlgStateStarted )
    {
      cbData[0] = dndInitActivity.m_pActivityData->m_failure.m_failureInfo.hr;
      v84 = -2147024322;
      if ( (cbData[0] & 0x80000000) != 0 )
        v84 = cbData[0];
      wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        dndInitActivity.m_pActivityData,
        v84,
        (HRESULT *)cbData);
LABEL_210:
      dndInitActivity.StopActivity(&dndInitActivity);
    }
  }
LABEL_211:
  if ( dndInitActivity.m_callbackHolder.m_threadId )
    wil::details::ThreadFailureCallbackHolder::StopWatching(&dndInitActivity.m_callbackHolder);
  wil::details::shared_object<wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&dndInitActivity.m_sharedActivityData);
  wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>(&dndInitActivity.m_activityData);
  return v44;
}

```

## disassembly

```asm
0x1800404b0  mov     [rsp-8+arg_18], rbx
0x1800404b5  push    rbp
0x1800404b6  push    rsi
0x1800404b7  push    rdi
0x1800404b8  push    r12
0x1800404ba  push    r13
0x1800404bc  push    r14
0x1800404be  push    r15
0x1800404c0  lea     rbp, [rsp-1E0h]
0x1800404c8  sub     rsp, 2E0h
0x1800404cf  mov     rax, cs:__security_cookie
0x1800404d6  xor     rax, rsp
0x1800404d9  mov     [rbp+210h+var_40], rax
0x1800404e0  mov     r15, [rbp+210h+arg_30]
0x1800404e7  lea     rax, aDragdropsessio_0; "DragDropSession_Initialize"
0x1800404ee  xor     esi, esi
0x1800404f0  mov     [rbp+210h+dndInitActivity.m_activityData.m_callContext.contextName], rax
0x1800404f4  xorps   xmm1, xmm1
0x1800404f7  mov     [rsp+310h+SRWLock], pDataObject
0x1800404fc  xor     eax, eax
0x1800404fe  mov     [rbp+210h+dndInitActivity.m_activityData.m_State], esi
0x180040501  mov     [rbp+210h+dndInitActivity.m_activityData.m_failure.m_failureInfo.callerReturnAddress], rax
0x180040508  mov     ebx, dwOKEffects
0x18004050b  mov     qword ptr [rbp+210h+dndInitActivity.m_activityData.m_lock.m_lock.___u0], rax
0x180040512  mov     r14, pDropSource
0x180040515  lea     rax, [rbp+210h+dndInitActivity.m_activityData]
0x180040519  mov     [rsp+310h+cbData], ebx
0x18004051d  mov     [rbp+210h+dndInitActivity.m_pActivityData], rax
0x180040524  lea     pDropSource, aOledragdrop; "OleDragDrop"
0x18004052b  lea     rax, [rbp+210h+dndInitActivity]
0x18004052f  mov     [rbp+210h+dndInitActivity.m_activityData.m_HasRelatedId], sil
0x180040533  mov     [rbp+210h+dndInitActivity.m_callbackHolder.m_pCallback], rax
0x18004053a  mov     r13, pDataObject
0x18004053d  lea     rax, [rbp+210h+dndInitActivity.m_activityData.m_callContext]
0x180040541  mov     [rbp+210h+dndInitActivity.m_activityData.m_callContext.m_ownsMessage], sil
0x180040548  mov     [rbp+210h+dndInitActivity.m_callbackHolder.m_pCallContext], rax
0x18004054f  lea     pDataObject, aDragoperationi; "DragOperationInit"
0x180040556  lea     rax, ??_7DragDropSession_Initialize@DragDropTelemetry@@6B@; const DragDropTelemetry::DragDropSession_Initialize::`vftable'
0x18004055d  mov     [rbp+210h+dndInitActivity.m_activityData.m_callContext.contextId], esi
0x180040560  mov     rdi, this
0x180040563  mov     [rbp+210h+dndInitActivity.__vftable], rax
0x180040567  xorps   xmm0, xmm0
0x18004056a  mov     [rbp+210h+dndInitActivity.m_activityData.m_callContext.contextMessage], rsi
0x180040571  lea     this, [rbp+210h+dndInitActivity]; this
0x180040575  mov     [rbp+210h+dndInitActivity.m_activityData.m_result], esi
0x18004057b  movdqa  xmmword ptr [rbp+210h+dndInitActivity.m_activityData.m_failure.m_spStrings.m_pCopy], xmm0
0x180040583  movups  xmmword ptr [rbp+210h+dndInitActivity.m_activityData.m_failure.m_failureInfo.type], xmm1
0x18004058a  mov     [rbp+210h+dndInitActivity.m_activityData.m_stopCountExpected], 1
0x180040594  movups  xmmword ptr [rbp+210h+dndInitActivity.m_activityData.m_failure.m_failureInfo.failureId], xmm1
0x18004059b  mov     [rbp+210h+dndInitActivity.m_sharedActivityData.m_pCopy], rsi
0x1800405a2  movups  xmmword ptr [rbp+210h+dndInitActivity.m_activityData.m_failure.m_failureInfo.threadId], xmm1
0x1800405a9  mov     [rbp+210h+dndInitActivity.m_callbackHolder.m_ppThreadList], rsi
0x1800405b0  movups  xmmword ptr [rbp+210h+dndInitActivity.m_activityData.m_failure.m_failureInfo.pszFunction], xmm1
0x1800405b7  mov     [rbp+210h+dndInitActivity.m_callbackHolder.m_pNext], rsi
0x1800405be  movups  xmmword ptr [rbp+210h+dndInitActivity.m_activityData.m_failure.m_failureInfo.uLineNumber], xmm1
0x1800405c5  mov     [rbp+210h+dndInitActivity.m_callbackHolder.m_threadId], esi
0x1800405cb  movups  xmmword ptr [rbp+210h+dndInitActivity.m_activityData.m_failure.m_failureInfo.callContextOriginating.contextId], xmm1
0x1800405d2  movups  xmmword ptr [rbp+210h+dndInitActivity.m_activityData.m_failure.m_failureInfo.callContextOriginating.contextMessage], xmm1
0x1800405d9  movups  xmmword ptr [rbp+210h+dndInitActivity.m_activityData.m_failure.m_failureInfo.callContextCurrent.contextName], xmm1
0x1800405e0  movups  xmmword ptr [rbp+210h+dndInitActivity.m_activityData.m_failure.m_failureInfo.pszModule], xmm1
0x1800405e7  call    ?StartActivity@DragDropSession_Initialize@DragDropTelemetry@@QEAAXPEBG0@Z; DragDropTelemetry::DragDropSession_Initialize::StartActivity(ushort const *,ushort const *)
0x1800405ec  mov     r12d, [rbp+210h+arg_28]; __annotation("_TlgProviderLink:|172|Key|"this"=DragDropSession_Initialize")
0x1800405f3  mov     cs:?g_forcedDropTarget@@3VCForcedDropTarget@@A._fDragDropActive, 1; CForcedDropTarget g_forcedDropTarget ...
0x1800405fd  mov     cs:?g_forcedDropTarget@@3VCForcedDropTarget@@A._hwndFDTCurrent, rsi; CForcedDropTarget g_forcedDropTarget ...
0x180040604  test    r12d, r12d
0x180040607  jnz     short loc_180040622
0x180040609  call    cs:__imp_EdpGetIsManaged
0x180040610  nop     dword ptr [rax+rax+00h]
0x180040615  test    eax, eax
0x180040617  jz      short loc_180040622
0x180040619  mov     byte ptr [rdi+228h], 1
0x180040620  jmp     short loc_180040632
0x180040622  mov     [rdi+228h], sil
0x180040629  test    r12d, r12d
0x18004062c  jnz     loc_18004079D
0x180040632  test    r13, r13
0x180040635  jnz     loc_18004079D
0x18004063b  mov     esi, 80070057h
0x180040640  lea     this, [rbp+210h+dndInitActivity]; this
0x180040644  mov     edx, esi; hr
0x180040646  call    ?Stop@?$ActivityBase@VDragDropLogging@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18004064b  lea     rax, ??_7DragDropSession_Initialize@DragDropTelemetry@@6B@; const DragDropTelemetry::DragDropSession_Initialize::`vftable'
0x180040652  xor     r15d, r15d
0x180040655  mov     [rbp+210h+dndInitActivity.__vftable], rax
0x180040659  mov     dil, 1
0x18004065c  mov     rax, [rbp+210h+dndInitActivity.m_sharedActivityData.m_pCopy]
0x180040663  test    rax, rax
0x180040666  jz      short loc_1800406E7
0x180040668  lea     rbx, [rax+8]
0x18004066c  add     rbx, 100h
0x180040673  mov     this, rbx; SRWLock
0x180040676  call    cs:__imp_AcquireSRWLockExclusive
0x18004067d  nop     dword ptr [rax+rax+00h]
0x180040682  lea     rax, [rsp+310h+SRWLock]
0x180040687  mov     [rax], r15
0x18004068a  mov     this, [rsp+310h+SRWLock]; SRWLock
0x18004068f  test    this, this
0x180040692  jz      short loc_1800406A0
0x180040694  call    cs:__imp_ReleaseSRWLockExclusive
0x18004069b  nop     dword ptr [rax+rax+00h]
0x1800406a0  mov     rax, [rbp+210h+dndInitActivity.m_sharedActivityData.m_pCopy]
0x1800406a7  test    rax, rax
0x1800406aa  jz      short loc_1800406B1
0x1800406ac  cmp     dword ptr [rax], 1
0x1800406af  jz      short loc_1800406C7
0x1800406b1  xor     dil, dil
0x1800406b4  lea     this, [rbp+210h+dndInitActivity.m_sharedActivityData]; this
0x1800406bb  call    ?reset@?$shared_object@V?$ActivityData@VDragDropLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDragDropLogging@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x1800406c0  mov     rax, [rbp+210h+dndInitActivity.m_sharedActivityData.m_pCopy]
0x1800406c7  test    rbx, rbx
0x1800406ca  jz      short loc_1800406E2
0x1800406cc  mov     this, rbx; SRWLock
0x1800406cf  call    cs:__imp_ReleaseSRWLockExclusive
0x1800406d6  nop     dword ptr [rax+rax+00h]
0x1800406db  mov     rax, [rbp+210h+dndInitActivity.m_sharedActivityData.m_pCopy]
0x1800406e2  test    dil, dil
0x1800406e5  jz      short loc_180040738
0x1800406e7  mov     pDataObject, [rbp+210h+dndInitActivity.m_pActivityData]
0x1800406ee  cmp     dword ptr [pDataObject], 1
0x1800406f1  jnz     short loc_180040738
0x1800406f3  mov     eax, [pDataObject+58h]
0x1800406f6  mov     ecx, 8007023Eh
0x1800406fb  test    eax, eax
0x1800406fd  cmovs   ecx, eax
0x180040700  mov     eax, [pDataObject+0F8h]
0x180040706  cmp     eax, 1
0x180040709  jl      loc_1800417F8
0x18004070f  cmp     dword ptr [pDataObject+48h], 0
0x180040713  jl      short loc_180040718
0x180040715  mov     [pDataObject+48h], ecx
0x180040718  dec     eax
0x18004071a  lea     this, [rbp+210h+dndInitActivity]
0x18004071e  mov     [pDataObject+0F8h], eax
0x180040724  mov     rax, [rbp+210h+dndInitActivity.__vftable]
0x180040728  mov     rax, [rax+8]
0x18004072c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040731  mov     rax, [rbp+210h+dndInitActivity.m_sharedActivityData.m_pCopy]
0x180040738  cmp     [rbp+210h+dndInitActivity.m_callbackHolder.m_threadId], 0
0x18004073f  jz      short loc_180040754
0x180040741  lea     this, [rbp+210h+dndInitActivity.m_callbackHolder]; this
0x180040748  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18004074d  mov     rax, [rbp+210h+dndInitActivity.m_sharedActivityData.m_pCopy]
0x180040754  test    rax, rax
0x180040757  jz      loc_180040911
0x18004075d  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180040764  lock xadd [rax], r14d
0x180040769  cmp     r14d, 1
0x18004076d  jnz     short loc_180040791
0x18004076f  mov     rbx, [rbp+210h+dndInitActivity.m_sharedActivityData.m_pCopy]
0x180040776  test    rbx, rbx
0x180040779  jz      short loc_180040791
0x18004077b  lea     this, [rbx+8]; this
0x18004077f  call    ??1?$ActivityData@VDragDropLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDragDropLogging@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x180040784  mov     edx, 110h; __formal
0x180040789  mov     this, rbx; block
0x18004078c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180040791  mov     [rbp+210h+dndInitActivity.m_sharedActivityData.m_pCopy], r15
0x180040798  jmp     loc_180040911
0x18004079d  mov     dwOKEffects, 1F0003h; dwDesiredAccess
0x1800407a3  lea     pDataObject, aLocalOledragsy; "Local\\OLEDragSynchronizationMutex"
0x1800407aa  xor     r8d, r8d; dwFlags
0x1800407ad  xor     ecx, ecx; lpEventAttributes
0x1800407af  call    cs:__imp_CreateEventExW
0x1800407b6  nop     dword ptr [rax+rax+00h]
0x1800407bb  mov     [rdi+0B0h], rax
0x1800407c2  test    rax, rax
0x1800407c5  jz      loc_180040A0A
0x1800407cb  call    cs:__imp_GetLastError
0x1800407d2  nop     dword ptr [rax+rax+00h]
0x1800407d7  cmp     eax, 0B7h
0x1800407dc  setz    cl
0x1800407df  mov     [rdi+0CCh], cl
0x1800407e5  jnz     loc_180040966
0x1800407eb  test    r12d, r12d
0x1800407ee  jz      loc_180040947
0x1800407f4  mov     esi, 80040103h
0x1800407f9  xor     edx, edx
0x1800407fb  mov     ecx, esi
0x1800407fd  call    cs:__imp_RoOriginateError
0x180040804  nop     dword ptr [rax+rax+00h]
0x180040809  mov     edx, esi; hr
0x18004080b  lea     this, [rbp+210h+dndInitActivity]; this
0x18004080f  call    ?Stop@?$ActivityBase@VDragDropLogging@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180040814  lea     rax, ??_7DragDropSession_Initialize@DragDropTelemetry@@6B@; const DragDropTelemetry::DragDropSession_Initialize::`vftable'
0x18004081b  mov     dil, 1
0x18004081e  mov     [rbp+210h+dndInitActivity.__vftable], rax
0x180040822  mov     rax, [rbp+210h+dndInitActivity.m_sharedActivityData.m_pCopy]
0x180040829  test    rax, rax
0x18004082c  jz      short loc_1800408A6
0x18004082e  lea     rbx, [rax+8]
0x180040832  add     rbx, 100h
0x180040839  mov     this, rbx; SRWLock
0x18004083c  call    cs:__imp_AcquireSRWLockExclusive
0x180040843  nop     dword ptr [rax+rax+00h]
0x180040848  xor     r15d, r15d
0x18004084b  lea     rax, [rbp+210h+var_80]
0x180040852  mov     [rax], r15
0x180040855  mov     this, qword ptr [rbp+210h+var_80]; SRWLock
0x18004085c  test    this, this
0x18004085f  jz      short loc_18004086D
0x180040861  call    cs:__imp_ReleaseSRWLockExclusive
0x180040868  nop     dword ptr [rax+rax+00h]
0x18004086d  mov     rax, [rbp+210h+dndInitActivity.m_sharedActivityData.m_pCopy]
0x180040874  test    rax, rax
0x180040877  jz      short loc_18004087E
0x180040879  cmp     dword ptr [rax], 1
0x18004087c  jz      short loc_18004088D
0x18004087e  xor     dil, dil
0x180040881  lea     this, [rbp+210h+dndInitActivity.m_sharedActivityData]; this
0x180040888  call    ?reset@?$shared_object@V?$ActivityData@VDragDropLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDragDropLogging@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18004088d  test    rbx, rbx
0x180040890  jz      short loc_1800408A1
0x180040892  mov     this, rbx; SRWLock
0x180040895  call    cs:__imp_ReleaseSRWLockExclusive
0x18004089c  nop     dword ptr [rax+rax+00h]
0x1800408a1  test    dil, dil
0x1800408a4  jz      short loc_1800408F0
0x1800408a6  mov     pDataObject, [rbp+210h+dndInitActivity.m_pActivityData]
0x1800408ad  cmp     dword ptr [pDataObject], 1
0x1800408b0  jnz     short loc_1800408F0
0x1800408b2  mov     eax, [pDataObject+58h]
0x1800408b5  mov     ecx, 8007023Eh
0x1800408ba  test    eax, eax
0x1800408bc  cmovs   ecx, eax
0x1800408bf  mov     eax, [pDataObject+0F8h]
0x1800408c5  cmp     eax, 1
0x1800408c8  jl      loc_18004182F
0x1800408ce  cmp     dword ptr [pDataObject+48h], 0
0x1800408d2  jl      short loc_1800408D7
0x1800408d4  mov     [pDataObject+48h], ecx
0x1800408d7  dec     eax
0x1800408d9  lea     this, [rbp+210h+dndInitActivity]
0x1800408dd  mov     [pDataObject+0F8h], eax
0x1800408e3  mov     rax, [rbp+210h+dndInitActivity.__vftable]
0x1800408e7  mov     rax, [rax+8]
0x1800408eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800408f0  cmp     [rbp+210h+dndInitActivity.m_callbackHolder.m_threadId], 0
0x1800408f7  jz      short loc_180040905
0x1800408f9  lea     this, [rbp+210h+dndInitActivity.m_callbackHolder]; this
0x180040900  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180040905  lea     this, [rbp+210h+dndInitActivity.m_sharedActivityData]; this
0x18004090c  call    ?reset@?$shared_object@V?$ActivityData@VDragDropLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDragDropLogging@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180040911  lea     this, [rbp+210h+dndInitActivity.m_activityData]; this
0x180040915  call    ??1?$ActivityData@VDragDropLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDragDropLogging@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x18004091a  mov     eax, esi
0x18004091c  mov     this, [rbp+210h+var_40]
0x180040923  xor     this, rsp; StackCookie
0x180040926  call    __security_check_cookie
0x18004092b  mov     rbx, [rsp+310h+arg_18]
0x180040933  add     rsp, 2E0h
0x18004093a  pop     r15
0x18004093c  pop     r14
0x18004093e  pop     r13
0x180040940  pop     r12
0x180040942  pop     rdi
0x180040943  pop     rsi
0x180040944  pop     rbp
0x180040945  retn
0x180040947  cmp     cs:?s_fDoDragDropInFlight@CDragOperation@@0_NA, sil; bool CDragOperation::s_fDoDragDropInFlight
0x18004094e  jnz     loc_180040A2F
0x180040954  call    ?IsContainerDragOperation@@YA_NXZ; IsContainerDragOperation(void)
0x180040959  test    al, al
0x18004095b  jnz     loc_180040A2F
0x180040961  jmp     loc_1800407F4
0x180040966  test    r12d, r12d
0x180040969  jnz     short loc_180040972
0x18004096b  mov     cs:?s_fDoDragDropInFlight@CDragOperation@@0_NA, 1; bool CDragOperation::s_fDoDragDropInFlight
0x180040972  lea     pDataObject, [rsp+310h+edpContext]; ppExtension
0x180040977  mov     [rsp+310h+edpContext.m_ptr], rsi
0x18004097c  mov     this, rdi; this
0x18004097f  call    ?GetWinRtExtension@CDragOperation@@AEAAJPEAPEAUIDragDropExtensionForOLE@@@Z; CDragOperation::GetWinRtExtension(IDragDropExtensionForOLE * *)
0x180040984  mov     esi, eax
0x180040986  test    eax, eax
0x180040988  js      short loc_1800409F3
0x18004098a  mov     rbx, [rsp+310h+edpContext.m_ptr]
0x18004098f  mov     this, [rdi+0D8h]
0x180040996  mov     rax, [rbx]
0x180040999  mov     r13, [rax+30h]
0x18004099d  test    this, this
0x1800409a0  jz      short loc_1800409B7
0x1800409a2  xor     eax, eax
0x1800409a4  mov     [rdi+0D8h], rax
0x1800409ab  mov     pDropSource, [this]
0x1800409ae  mov     rax, [pDropSource+10h]
0x1800409b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800409b7  lea     pDataObject, [rdi+0D8h]
0x1800409be  mov     this, rbx
0x1800409c1  mov     rax, r13
0x1800409c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800409c9  mov     r13, [rsp+310h+SRWLock]
0x1800409ce  mov     esi, eax
0x1800409d0  mov     ebx, [rsp+310h+cbData]
0x1800409d4  xor     eax, eax
0x1800409d6  mov     this, [rsp+310h+edpContext.m_ptr]
0x1800409db  test    this, this
0x1800409de  jz      short loc_180040A25
0x1800409e0  mov     [rsp+310h+edpContext.m_ptr], rax
0x1800409e5  mov     rax, [this]
0x1800409e8  mov     rax, [rax+10h]
0x1800409ec  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
