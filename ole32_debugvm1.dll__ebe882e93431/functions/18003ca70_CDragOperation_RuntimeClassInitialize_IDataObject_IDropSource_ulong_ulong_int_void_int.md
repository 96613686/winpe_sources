# CDragOperation::RuntimeClassInitialize(IDataObject *,IDropSource *,ulong,ulong *,int,void * *,int)

- ea: `0x18003ca70`
- end: `0x18003df6a`
- name: `?RuntimeClassInitialize@CDragOperation@@QEAAJPEAUIDataObject@@PEAUIDropSource@@KPEAKHPEAPEAXH@Z`
- size: `5370`
- prototype: `HRESULT __fastcall(CDragOperation *this, IDataObject *pDataObject, IDropSource *pDropSource, unsigned int dwOKEffects, unsigned int *pdwEffect, int fWinRTDrag, void **phClientToken, int fBackgroundContainerDrag)`
- caller_count: `2`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c430`
- `0x1800470fc`

## callees

- `0x18000c3dc`
- `0x18000cabc`
- `0x18000d38c`
- `0x180010be8`
- `0x1800185ec`
- `0x18001b3cc`
- `0x1800340d8`
- `0x1800359c8`
- `0x18003c554`
- `0x18003ca70`
- `0x18003df70`
- `0x180040660`
- `0x180040698`
- `0x180041564`
- `0x1800425ec`
- `0x180052390`
- `0x180052760`
- `0x180057178`
- `0x18008c6a8`
- `0x18008e468`
- `0x18009325c`
- `0x18009334c`
- `0x1800933ec`
- `0x180094f8c`
- `0x1800950b0`
- `0x180095894`
- `0x18009595c`
- `0x1800ce010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18003d650`
- `msvcp_win!_Mtx_unlock` at `0x18003d697`
- `msvcp_win!_Mtx_unlock` at `0x18003d650`
- `msvcp_win!_Mtx_unlock` at `0x18003d697`
- `msvcp_win!_Mtx_lock` at `0x18003d588`
- `msvcp_win!_Mtx_lock` at `0x18003d588`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003d597`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003d5b9`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003d597`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003d5b9`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18003d10d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18003d10d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003cc2a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003cdac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003cfc3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d294`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003dcc2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003cc2a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003cdac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003cfc3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d294`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003dcc2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003cc5d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003cff6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d2c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003dbd8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003dcf5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003dd6d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003cc5d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003cff6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d2c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003dbd8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003dcf5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003dd6d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003cd2b`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003cd2b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d205`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d25d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d4c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d6ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d7a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d851`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d905`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003db02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003db72`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003dc8b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d205`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d25d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d4c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d6ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d7a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d851`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d905`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003db02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003db72`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003dc8b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003d1d7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003d1d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cd41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ce9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cd41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ce9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003da41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003da41`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003d0ef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003d0ef`
- `USER32!SetCapture` at `0x18003d366`
- `USER32!SetCapture` at `0x18003d366`
- `USER32!SetThreadDpiAwarenessContext` at `0x18003d528`
- `USER32!SetThreadDpiAwarenessContext` at `0x18003d53e`
- `USER32!SetThreadDpiAwarenessContext` at `0x18003d528`
- `USER32!SetThreadDpiAwarenessContext` at `0x18003d53e`
- `USER32!GetCursor` at `0x18003d078`
- `USER32!GetCursor` at `0x18003d078`
- `USER32!GetCursorPos` at `0x18003d535`
- `USER32!GetCursorPos` at `0x18003d535`
- `USER32!GetForegroundWindow` at `0x18003d871`
- `USER32!GetForegroundWindow` at `0x18003d871`
- `USER32!PeekMessageW` at `0x18003d3f7`
- `USER32!PeekMessageW` at `0x18003d42a`
- `USER32!PeekMessageW` at `0x18003d44e`
- `USER32!PeekMessageW` at `0x18003d47f`
- `USER32!PeekMessageW` at `0x18003d3f7`
- `USER32!PeekMessageW` at `0x18003d42a`
- `USER32!PeekMessageW` at `0x18003d44e`
- `USER32!PeekMessageW` at `0x18003d47f`
- `USER32!__imp_LogicalToPhysicalDpiPointForWindow` at `0x18003d504`
- `USER32!__imp_LogicalToPhysicalDpiPointForWindow` at `0x18003d504`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18003d177`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18003d177`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003d607`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003d607`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d6c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d77e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d82a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d8de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003da91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dadb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d6c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d77e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d82a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d8de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003da91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dadb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db4b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18003cd69`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18003cd69`
- `ext-ms-win-edputil-policy-l1-1-0!EdpFreeContext` at `0x18003dacd`
- `ext-ms-win-edputil-policy-l1-1-0!EdpFreeContext` at `0x18003db31`
- `ext-ms-win-edputil-policy-l1-1-0!EdpFreeContext` at `0x18003dacd`
- `ext-ms-win-edputil-policy-l1-1-0!EdpFreeContext` at `0x18003db31`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForProcess` at `0x18003da4c`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForProcess` at `0x18003da4c`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18003cbc1`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18003cbc1`

## string_xrefs

- `0x18003d6a8`: `com\ole32\ole232\drag\drag.cpp`
- `0x18003d73f`: `com\ole32\ole232\drag\drag.cpp`
- `0x18003d7eb`: `com\ole32\ole232\drag\drag.cpp`
- `0x18003d89f`: `com\ole32\ole232\drag\drag.cpp`
- `0x18003daac`: `com\ole32\ole232\drag\drag.cpp`
- `0x18003d61a`: `com\ole32\ole232\drag\hostdragoperation.cpp`

## pseudocode

```c
__int64 __fastcall CDragOperation::RuntimeClassInitialize(
        CDragOperation *this,
        IDataObject *pDataObject,
        IDropSource *pDropSource,
        unsigned int dwOKEffects,
        unsigned int *pdwEffect,
        int fWinRTDrag,
        void **phClientToken,
        int fBackgroundContainerDrag)
{
  IDataObject *pszStringData; // r13
  unsigned int v11; // r12d
  signed int v12; // ebx
  wil::srwlock *p_m_lock; // rdi
  char v14; // si
  wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType> *m_pActivityData; // rdx
  HRESULT hr; // ecx
  int m_stopCountExpected; // eax
  wil::details::shared_object<wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType> >::RefAndObject *m_pCopy; // rdi
  HANDLE Event; // rax
  DWORD v20; // eax
  _TOKEN_INFORMATION_CLASS v21; // edx
  wil::srwlock *v22; // rdi
  char v23; // si
  int WinRtExtension; // eax
  EDP_CONTEXT *m_ptr; // r12
  IUnknown *ptr; // rcx
  __int64 (__fastcall *v27)(EDP_CONTEXT *, Microsoft::WRL::ComPtr<IUnknown> *); // r13
  signed int v28; // eax
  EDP_CONTEXT *v29; // rcx
  signed int LastError; // eax
  void *v31; // rcx
  _MCGEN_TRACE_CONTEXT *v32; // rcx
  const _GUID *v33; // r8
  wil::srwlock *v34; // rdi
  char v35; // si
  wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType> *v36; // rdx
  HRESULT v37; // ecx
  int v38; // eax
  unsigned int *p_dwEffect; // rax
  HRESULT v40; // eax
  unsigned int v41; // r15d
  unsigned int cbBufferSize; // edx
  CDragDefaultCursors *v43; // rax
  wil::srwlock *v44; // rbx
  char v45; // di
  wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType> *v46; // rdx
  HRESULT v47; // ecx
  int v48; // eax
  HWND PrivateClipboardWindow; // rax
  unsigned __int64 v51; // rcx
  unsigned __int16 ControlKeysState; // ax
  __int64 v53; // rbx
  IDropTarget *v54; // rcx
  __int64 (__fastcall ***v55)(_QWORD, GUID *, Microsoft::WRL::ComPtr<IDropTarget> *); // rcx
  int Instance; // eax
  __int64 (__fastcall ***v57)(_QWORD, GUID *, Microsoft::WRL::ComPtr<IDropTarget> *); // rcx
  signed int v58; // eax
  __int64 (__fastcall ***v59)(_QWORD, GUID *, Microsoft::WRL::ComPtr<IDropTarget> *); // rcx
  unsigned __int16 dwAspect; // r12
  HRESULT v61; // eax
  EDP_CONTEXT *v62; // rcx
  HRESULT v63; // eax
  EDP_CONTEXT *v64; // rcx
  unsigned int ForegroundWindow; // eax
  HRESULT v66; // eax
  EDP_CONTEXT *v67; // rcx
  EDP_CONTEXT *v68; // rcx
  IDataObject v69; // rax
  ULONG (__stdcall *Release)(IUnknown *); // rax
  int v71; // eax
  wchar_t *v72; // r14
  wchar_t *v73; // rdx
  IDataObject v74; // rax
  ULONG (__stdcall *v75)(IUnknown *); // rax
  int v76; // eax
  EDP_CONTEXT **v77; // rbx
  DWORD CurrentProcessId; // eax
  unsigned __int64 v79; // r8
  EDP_CONTEXT *v80; // rcx
  wchar_t *enterpriseIdForUIEnforcement; // rdx
  char v82; // bl
  wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType> *v83; // rdx
  HRESULT v84; // ecx
  int v85; // eax
  bool v86; // zf
  wil::srwlock *v87; // rbx
  char v88; // di
  wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType> *v89; // rdx
  HRESULT v90; // ecx
  int v91; // eax
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (__cdecl*)(EDP_CONTEXT *),&EdpFreeContext,wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t> > > edpContext; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int cbData[2]; // [rsp+38h] [rbp-C8h] BYREF
  CWriteInterfaceDataMarshalingStream objectStream; // [rsp+40h] [rbp-C0h] BYREF
  wil::FailureInfo failure; // [rsp+70h] [rbp-90h] BYREF
  DragDropTelemetry::DragDropSession_Initialize dndInitActivity; // [rsp+110h] [rbp+10h] BYREF
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short> > spszDataFormats; // [rsp+260h] [rbp+160h] BYREF
  tagFORMATETC formatetc; // [rsp+278h] [rbp+178h] BYREF
  __int128 v99; // [rsp+298h] [rbp+198h]
  void *retaddr; // [rsp+2E8h] [rbp+1E8h]

  dndInitActivity.m_activityData.m_callContext.contextName = "DragDropSession_Initialize";
  spszDataFormats._pszStringData = (wchar_t *)pDataObject;
  cbData[0] = dwOKEffects;
  dndInitActivity.m_activityData.m_lock.m_lock.Value = 0;
  dndInitActivity.m_activityData.m_State = TlgStateCreated;
  dndInitActivity.m_pActivityData = &dndInitActivity.m_activityData;
  pszStringData = pDataObject;
  dndInitActivity.m_activityData.m_HasRelatedId = 0;
  dndInitActivity.m_callbackHolder.m_pCallback = &dndInitActivity;
  dndInitActivity.m_activityData.m_callContext.m_ownsMessage = 0;
  dndInitActivity.m_callbackHolder.m_pCallContext = &dndInitActivity.m_activityData.m_callContext;
  dndInitActivity.m_activityData.m_callContext.contextId = 0;
  dndInitActivity.__vftable = (DragDropTelemetry::DragDropSession_Initialize_vtbl *)DragDropTelemetry::DragDropSession_Initialize::`vftable';
  dndInitActivity.m_activityData.m_callContext.contextMessage = 0;
  v11 = dwOKEffects;
  dndInitActivity.m_activityData.m_result = 0;
  memset(&dndInitActivity.m_activityData.m_failure, 0, sizeof(dndInitActivity.m_activityData.m_failure));
  dndInitActivity.m_activityData.m_stopCountExpected = 1;
  dndInitActivity.m_sharedActivityData.m_pCopy = 0;
  dndInitActivity.m_callbackHolder.m_ppThreadList = 0;
  dndInitActivity.m_callbackHolder.m_pNext = 0;
  dndInitActivity.m_callbackHolder.m_threadId = 0;
  dndInitActivity.m_callbackHolder.m_handlingNotify = 0;
  DragDropTelemetry::DragDropSession_Initialize::StartActivity(&dndInitActivity, L"DragOperationInit", L"OleDragDrop");
  g_forcedDropTarget._fDragDropActive = 1;
  g_forcedDropTarget._hwndFDTCurrent = 0;
  if ( fWinRTDrag || !(unsigned int)EdpGetIsManaged() )
  {
    this->m_isEdpActive = 0;
    if ( fWinRTDrag )
      goto LABEL_28;
  }
  else
  {
    this->m_isEdpActive = 1;
  }
  if ( !pszStringData )
  {
    v12 = -2147024809;
    wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
      &dndInitActivity,
      -2147024809);
    dndInitActivity.__vftable = (DragDropTelemetry::DragDropSession_Initialize_vtbl *)DragDropTelemetry::DragDropSession_Initialize::`vftable';
    if ( !dndInitActivity.m_sharedActivityData.m_pCopy )
      goto LABEL_14;
    p_m_lock = &dndInitActivity.m_sharedActivityData.m_pCopy->m_object.m_lock;
    AcquireSRWLockExclusive(&dndInitActivity.m_sharedActivityData.m_pCopy->m_object.m_lock.m_lock);
    if ( dndInitActivity.m_sharedActivityData.m_pCopy && dndInitActivity.m_sharedActivityData.m_pCopy->m_refCount == 1 )
    {
      v14 = 1;
    }
    else
    {
      v14 = 0;
      wil::details::shared_object<wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&dndInitActivity.m_sharedActivityData);
    }
    if ( p_m_lock )
      ReleaseSRWLockExclusive(&p_m_lock->m_lock);
    if ( v14 )
    {
LABEL_14:
      m_pActivityData = dndInitActivity.m_pActivityData;
      if ( dndInitActivity.m_pActivityData->m_State == TlgStateStarted )
      {
        hr = -2147024322;
        if ( dndInitActivity.m_pActivityData->m_failure.m_failureInfo.hr < 0 )
          hr = dndInitActivity.m_pActivityData->m_failure.m_failureInfo.hr;
        m_stopCountExpected = dndInitActivity.m_pActivityData->m_stopCountExpected;
        if ( m_stopCountExpected < 1 )
        {
          memset((void *)&failure, 0, sizeof(failure));
          wil::details::WilFailFast(&failure);
        }
        if ( dndInitActivity.m_pActivityData->m_result >= 0 )
          dndInitActivity.m_pActivityData->m_result = hr;
        m_pActivityData->m_stopCountExpected = m_stopCountExpected - 1;
        dndInitActivity.StopActivity(&dndInitActivity);
      }
    }
    if ( dndInitActivity.m_callbackHolder.m_threadId )
      wil::details::ThreadFailureCallbackHolder::StopWatching(&dndInitActivity.m_callbackHolder);
    if ( dndInitActivity.m_sharedActivityData.m_pCopy )
    {
      if ( _InterlockedExchangeAdd(&dndInitActivity.m_sharedActivityData.m_pCopy->m_refCount, 0xFFFFFFFF) == 1 )
      {
        m_pCopy = dndInitActivity.m_sharedActivityData.m_pCopy;
        if ( dndInitActivity.m_sharedActivityData.m_pCopy )
        {
          wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>(&dndInitActivity.m_sharedActivityData.m_pCopy->m_object);
          operator delete(m_pCopy, 0x110u);
        }
      }
      dndInitActivity.m_sharedActivityData.m_pCopy = 0;
    }
LABEL_262:
    wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>(&dndInitActivity.m_activityData);
    return (unsigned int)v12;
  }
LABEL_28:
  Event = CreateEventExW(0, L"Local\\OLEDragSynchronizationMutex", 0, 0x1F0003u);
  this->_hDragInProgress = Event;
  if ( !Event )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
LABEL_52:
    if ( v12 < 0 )
      goto LABEL_32;
    goto LABEL_53;
  }
  v20 = GetLastError();
  this->_fConcurrentDrag = v20 == 183;
  if ( v20 != 183 )
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
      v27 = *(__int64 (__fastcall **)(EDP_CONTEXT *, Microsoft::WRL::ComPtr<IUnknown> *))(*(_QWORD *)&edpContext.m_ptr->contextStates
                                                                                        + 48LL);
      if ( ptr )
      {
        this->_spWinRtExclusionToken.ptr_ = 0;
        ((void (__fastcall *)(IUnknown *))ptr->lpVtbl->Release)(ptr);
      }
      v28 = v27(m_ptr, &this->_spWinRtExclusionToken);
      pszStringData = (IDataObject *)spszDataFormats._pszStringData;
      v12 = v28;
      v11 = cbData[0];
    }
    v29 = edpContext.m_ptr;
    if ( edpContext.m_ptr )
    {
      edpContext.m_ptr = 0;
      (*(void (__fastcall **)(EDP_CONTEXT *))(*(_QWORD *)&v29->contextStates + 16LL))(v29);
    }
    goto LABEL_52;
  }
  if ( fWinRTDrag || !CDragOperation::s_fDoDragDropInFlight && !IsContainerDragOperation() )
  {
    v12 = -2147221245;
    RoOriginateError(2147746051LL, 0);
LABEL_32:
    wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(&dndInitActivity, v12);
    dndInitActivity.__vftable = (DragDropTelemetry::DragDropSession_Initialize_vtbl *)DragDropTelemetry::DragDropSession_Initialize::`vftable';
    if ( dndInitActivity.m_sharedActivityData.m_pCopy )
    {
      v22 = &dndInitActivity.m_sharedActivityData.m_pCopy->m_object.m_lock;
      AcquireSRWLockExclusive(&dndInitActivity.m_sharedActivityData.m_pCopy->m_object.m_lock.m_lock);
      if ( dndInitActivity.m_sharedActivityData.m_pCopy && dndInitActivity.m_sharedActivityData.m_pCopy->m_refCount == 1 )
      {
        v23 = 1;
      }
      else
      {
        v23 = 0;
        wil::details::shared_object<wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&dndInitActivity.m_sharedActivityData);
      }
      if ( v22 )
        ReleaseSRWLockExclusive(&v22->m_lock);
      if ( !v23 )
        goto LABEL_259;
    }
    v36 = dndInitActivity.m_pActivityData;
    if ( dndInitActivity.m_pActivityData->m_State != TlgStateStarted )
      goto LABEL_259;
    v37 = -2147024322;
    if ( dndInitActivity.m_pActivityData->m_failure.m_failureInfo.hr < 0 )
      v37 = dndInitActivity.m_pActivityData->m_failure.m_failureInfo.hr;
    v38 = dndInitActivity.m_pActivityData->m_stopCountExpected;
    if ( v38 < 1 )
    {
      memset((void *)&failure, 0, sizeof(failure));
      wil::details::WilFailFast(&failure);
    }
LABEL_256:
    if ( v36->m_result >= 0 )
      v36->m_result = v37;
    v36->m_stopCountExpected = v38 - 1;
    dndInitActivity.StopActivity(&dndInitActivity);
LABEL_259:
    if ( dndInitActivity.m_callbackHolder.m_threadId )
      wil::details::ThreadFailureCallbackHolder::StopWatching(&dndInitActivity.m_callbackHolder);
    wil::details::shared_object<wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&dndInitActivity.m_sharedActivityData);
    goto LABEL_262;
  }
LABEL_53:
  if ( phClientToken )
    v31 = *phClientToken;
  else
    v31 = 0;
  v12 = IsTokenBoolPresent(v31, v21, &this->_fSourceIsAppContainer);
  if ( v12 < 0 )
    goto LABEL_32;
  this->_fWinRTDrag = fWinRTDrag;
  this->m_backgroundContainerDrag = fBackgroundContainerDrag != 0;
  if ( phClientToken )
  {
    this->_hDragSourceToken = *phClientToken;
    *phClientToken = 0;
  }
  if ( (Microsoft_Windows_OLE_PerfEnableBits[0] & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      v32,
      &OLE_DragDrop_DragOperation_SetDataObject_Start,
      v33,
      1u,
      (_EVENT_DATA_DESCRIPTOR *)&spszDataFormats);
  if ( this->_pDataObject || this->_fDropCompleted )
  {
    v12 = -2147483634;
  }
  else if ( pszStringData )
  {
    this->_pDataObject = pszStringData;
    v12 = 0;
    ((void (__fastcall *)(IDataObject *))pszStringData->lpVtbl->AddRef)(pszStringData);
  }
  else
  {
    v12 = -2147024809;
  }
  if ( (Microsoft_Windows_OLE_PerfEnableBits[0] & 1) != 0 )
    McTemplateU0d_EventWriteTransfer(v32, &OLE_DragDrop_DragOperation_SetDataObject_Stop, v12);
  if ( v12 < 0 )
  {
    wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(&dndInitActivity, v12);
    dndInitActivity.__vftable = (DragDropTelemetry::DragDropSession_Initialize_vtbl *)DragDropTelemetry::DragDropSession_Initialize::`vftable';
    if ( dndInitActivity.m_sharedActivityData.m_pCopy )
    {
      v34 = &dndInitActivity.m_sharedActivityData.m_pCopy->m_object.m_lock;
      AcquireSRWLockExclusive(&dndInitActivity.m_sharedActivityData.m_pCopy->m_object.m_lock.m_lock);
      if ( dndInitActivity.m_sharedActivityData.m_pCopy && dndInitActivity.m_sharedActivityData.m_pCopy->m_refCount == 1 )
      {
        v35 = 1;
      }
      else
      {
        v35 = 0;
        wil::details::shared_object<wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&dndInitActivity.m_sharedActivityData);
      }
      if ( v34 )
        ReleaseSRWLockExclusive(&v34->m_lock);
      if ( !v35 )
        goto LABEL_259;
    }
    v36 = dndInitActivity.m_pActivityData;
    if ( dndInitActivity.m_pActivityData->m_State != TlgStateStarted )
      goto LABEL_259;
    v37 = -2147024322;
    if ( dndInitActivity.m_pActivityData->m_failure.m_failureInfo.hr < 0 )
      v37 = dndInitActivity.m_pActivityData->m_failure.m_failureInfo.hr;
    v38 = dndInitActivity.m_pActivityData->m_stopCountExpected;
    if ( v38 < 1 )
    {
      memset((void *)&failure, 0, sizeof(failure));
      wil::details::WilFailFast(&failure);
    }
    goto LABEL_256;
  }
  this->_pDropSource = pDropSource;
  if ( pDropSource && this->_fWinRTDrag )
    ((void (__fastcall *)(IDropSource *))pDropSource->lpVtbl->AddRef)(pDropSource);
  p_dwEffect = pdwEffect;
  this->_dwOKEffects = v11;
  if ( !pdwEffect )
    p_dwEffect = &this->_dwEffect;
  v86 = this->_fWinRTDrag == 0;
  this->_pdwEffect = p_dwEffect;
  if ( v86 )
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
      WORD4(v99) = 0;
      CDragOperation::s_wScrollInt = wcstol(&formatetc.cfFormat, 0, 0);
    }
  }
  *((_DWORD *)&objectStream._cRefs + 1) = 0;
  objectStream._cRefs = 1;
  objectStream.lpVtbl = (struct IStreamVtbl *)CReadInterfaceDataFromInternalSourceMarshalingStream::`vftable';
  *(_QWORD *)&objectStream._lOffset = 0;
  objectStream._cbBufferSize = 0;
  objectStream._pMInterfacePointer = 0;
  objectStream._fFree = 1;
  v40 = CoMarshalInterface(&objectStream, &IID_IDataObject, pszStringData, 1u, 0, 1u);
  v41 = v40;
  if ( v40 )
  {
    wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(&dndInitActivity, v40);
    objectStream.lpVtbl = (struct IStreamVtbl *)CBaseMInterfacePointerMarshalingStream::`vftable';
    if ( objectStream._fFree )
      HeapFree(g_hHeap, 0, objectStream._pMInterfacePointer);
    objectStream.lpVtbl = (struct IStreamVtbl *)CAbstractStream::`vftable';
    dndInitActivity.__vftable = (DragDropTelemetry::DragDropSession_Initialize_vtbl *)DragDropTelemetry::DragDropSession_Initialize::`vftable';
    if ( !dndInitActivity.m_sharedActivityData.m_pCopy )
      goto LABEL_240;
    v87 = &dndInitActivity.m_sharedActivityData.m_pCopy->m_object.m_lock;
    AcquireSRWLockExclusive(&dndInitActivity.m_sharedActivityData.m_pCopy->m_object.m_lock.m_lock);
    if ( dndInitActivity.m_sharedActivityData.m_pCopy && dndInitActivity.m_sharedActivityData.m_pCopy->m_refCount == 1 )
    {
      v88 = 1;
    }
    else
    {
      v88 = 0;
      wil::details::shared_object<wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&dndInitActivity.m_sharedActivityData);
    }
    if ( v87 )
      ReleaseSRWLockExclusive(&v87->m_lock);
    if ( v88 )
    {
LABEL_240:
      v89 = dndInitActivity.m_pActivityData;
      if ( dndInitActivity.m_pActivityData->m_State == TlgStateStarted )
      {
        v90 = -2147024322;
        if ( dndInitActivity.m_pActivityData->m_failure.m_failureInfo.hr < 0 )
          v90 = dndInitActivity.m_pActivityData->m_failure.m_failureInfo.hr;
        v91 = dndInitActivity.m_pActivityData->m_stopCountExpected;
        if ( v91 < 1 )
        {
          memset((void *)&failure, 0, sizeof(failure));
          wil::details::WilFailFast(&failure);
        }
        if ( dndInitActivity.m_pActivityData->m_result >= 0 )
          dndInitActivity.m_pActivityData->m_result = v90;
        v89->m_stopCountExpected = v91 - 1;
        dndInitActivity.StopActivity(&dndInitActivity);
      }
    }
    v86 = dndInitActivity.m_callbackHolder.m_threadId == 0;
    goto LABEL_227;
  }
  cbBufferSize = objectStream._cbBufferSize;
  if ( objectStream._cbDataSize )
    cbBufferSize = objectStream._cbDataSize;
  objectStream._pMInterfacePointer->ulCntData = cbBufferSize;
  this->_DOBuffer = (tagInterfaceData *)objectStream._pMInterfacePointer;
  objectStream._pMInterfacePointer = 0;
  objectStream._fFree = 0;
  if ( this->_fWinRTDrag )
  {
LABEL_127:
    spszDataFormats._pszStringData = 0;
    spszDataFormats._cchStringData = -1;
    spszDataFormats._cchStringDataCapacity = -1;
    this->_hFormats = CreateSharedDragFormats(pszStringData, &spszDataFormats._pszStringData);
    if ( !this->_fWinRTDrag && !this->m_backgroundContainerDrag )
    {
      memset(&formatetc, 0, sizeof(formatetc));
      v99 = 0;
      if ( !PeekMessageW((LPMSG)&formatetc, 0, 0x200u, 0x20Eu, 1u) )
      {
        while ( !PeekMessageW((LPMSG)&formatetc, 0, 0x100u, 0x100u, 1u)
             && !PeekMessageW((LPMSG)&formatetc, 0, 0x104u, 0x104u, 1u)
             || *(_QWORD *)&formatetc.dwAspect != 27 )
        {
          if ( PeekMessageW((LPMSG)&formatetc, 0, 0x200u, 0x20Eu, 1u) )
            goto LABEL_139;
        }
        this->_fEscapePressed = 1;
      }
LABEL_139:
      if ( this->_fEscapePressed )
      {
        v53 = SetThreadDpiAwarenessContext(-3);
        GetCursorPos(&this->_cpt._pt);
        SetThreadDpiAwarenessContext(v53);
        ControlKeysState = GetControlKeysState(1);
      }
      else
      {
        edpContext.m_ptr = *(EDP_CONTEXT **)((char *)&v99 + 4);
        LogicalToPhysicalDpiPointForWindow(*(_QWORD *)&formatetc.cfFormat, &edpContext);
        v51 = *(_QWORD *)&formatetc.dwAspect;
        this->_cpt = (CPoint)edpContext.m_ptr;
        ControlKeysState = GetControlKeysStateOfParam(v51);
      }
      this->_grfKeyState = ControlKeysState;
      if ( IsContainerDragOperation() )
      {
        v54 = this->m_nonRPCSSRegisteredDropTarget.ptr_;
        if ( v54 )
        {
          this->m_nonRPCSSRegisteredDropTarget.ptr_ = 0;
          ((void (__fastcall *)(IDropTarget *))v54->lpVtbl->Release)(v54);
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
              (v55 = *(__int64 (__fastcall ****)(_QWORD, GUID *, Microsoft::WRL::ComPtr<IDropTarget> *))cbData) == 0) )
        {
          Instance = CoCreateInstance(
                       &CLSID_HostOperationDropTarget,
                       0,
                       1u,
                       &GUID_e2f15d97_b5f6_4e82_a44b_1c0d664999f3,
                       (LPVOID *)cbData);
          v12 = Instance;
          if ( Instance < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              0x34u,
              "com\\ole32\\ole232\\drag\\hostdragoperation.cpp",
              Instance);
            v57 = *(__int64 (__fastcall ****)(_QWORD, GUID *, Microsoft::WRL::ComPtr<IDropTarget> *))cbData;
            if ( *(_QWORD *)cbData )
            {
              *(_QWORD *)cbData = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, Microsoft::WRL::ComPtr<IDropTarget> *)))(*v57)[2])(v57);
            }
            _Mtx_unlock(&g_containerProxyLock._Mtx_storage);
LABEL_159:
            wil::details::in1diag3::Return_Hr(retaddr, 0x5DEu, "com\\ole32\\ole232\\drag\\drag.cpp", v12);
            if ( spszDataFormats._pszStringData )
              CoTaskMemFree(spszDataFormats._pszStringData);
            objectStream.lpVtbl = (struct IStreamVtbl *)CBaseMInterfacePointerMarshalingStream::`vftable';
            if ( objectStream._fFree )
              HeapFree(g_hHeap, 0, objectStream._pMInterfacePointer);
LABEL_187:
            objectStream.lpVtbl = (struct IStreamVtbl *)CAbstractStream::`vftable';
            DragDropTelemetry::DragDropSession_Initialize::~DragDropSession_Initialize(&dndInitActivity);
            return (unsigned int)v12;
          }
          v55 = *(__int64 (__fastcall ****)(_QWORD, GUID *, Microsoft::WRL::ComPtr<IDropTarget> *))cbData;
        }
        v58 = (**v55)(v55, &GUID_00000122_0000_0000_c000_000000000046, &this->m_nonRPCSSRegisteredDropTarget);
        v59 = *(__int64 (__fastcall ****)(_QWORD, GUID *, Microsoft::WRL::ComPtr<IDropTarget> *))cbData;
        v12 = v58;
        if ( *(_QWORD *)cbData )
        {
          *(_QWORD *)cbData = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, Microsoft::WRL::ComPtr<IDropTarget> *)))(*v59)[2])(v59);
        }
        _Mtx_unlock(&g_containerProxyLock._Mtx_storage);
        if ( v12 < 0 )
          goto LABEL_159;
        dwAspect = formatetc.dwAspect;
        edpContext.m_ptr = 0;
        v61 = Microsoft::WRL::ComPtr<IDropTarget>::As<IDragDropContainerProxy>(
                &this->m_nonRPCSSRegisteredDropTarget,
                (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDragDropContainerProxy> >)&edpContext);
        v12 = v61;
        if ( v61 < 0 )
        {
          wil::details::in1diag3::Return_Hr(retaddr, 0x5E7u, "com\\ole32\\ole232\\drag\\drag.cpp", v61);
          v62 = edpContext.m_ptr;
          if ( edpContext.m_ptr )
          {
            edpContext.m_ptr = 0;
            (*(void (__fastcall **)(EDP_CONTEXT *))(*(_QWORD *)&v62->contextStates + 16LL))(v62);
          }
          if ( spszDataFormats._pszStringData )
            CoTaskMemFree(spszDataFormats._pszStringData);
          objectStream.lpVtbl = (struct IStreamVtbl *)CBaseMInterfacePointerMarshalingStream::`vftable';
          if ( objectStream._fFree )
            HeapFree(g_hHeap, 0, objectStream._pMInterfacePointer);
          goto LABEL_187;
        }
        v63 = (*(__int64 (__fastcall **)(EDP_CONTEXT *, _QWORD))(*(_QWORD *)&edpContext.m_ptr->contextStates + 24LL))(
                edpContext.m_ptr,
                dwAspect);
        v12 = v63;
        if ( v63 < 0 )
        {
          wil::details::in1diag3::Return_Hr(retaddr, 0x5E8u, "com\\ole32\\ole232\\drag\\drag.cpp", v63);
          v64 = edpContext.m_ptr;
          if ( edpContext.m_ptr )
          {
            edpContext.m_ptr = 0;
            (*(void (__fastcall **)(EDP_CONTEXT *))(*(_QWORD *)&v64->contextStates + 16LL))(v64);
          }
          if ( spszDataFormats._pszStringData )
            CoTaskMemFree(spszDataFormats._pszStringData);
          objectStream.lpVtbl = (struct IStreamVtbl *)CBaseMInterfacePointerMarshalingStream::`vftable';
          if ( objectStream._fFree )
            HeapFree(g_hHeap, 0, objectStream._pMInterfacePointer);
          goto LABEL_187;
        }
        ForegroundWindow = (unsigned int)GetForegroundWindow();
        v66 = (*(__int64 (__fastcall **)(EDP_CONTEXT *, _QWORD))(*(_QWORD *)&edpContext.m_ptr->contextStates + 32LL))(
                edpContext.m_ptr,
                ForegroundWindow);
        v12 = v66;
        if ( v66 < 0 )
        {
          wil::details::in1diag3::Return_Hr(retaddr, 0x5EDu, "com\\ole32\\ole232\\drag\\drag.cpp", v66);
          v67 = edpContext.m_ptr;
          if ( edpContext.m_ptr )
          {
            edpContext.m_ptr = 0;
            (*(void (__fastcall **)(EDP_CONTEXT *))(*(_QWORD *)&v67->contextStates + 16LL))(v67);
          }
          if ( spszDataFormats._pszStringData )
            CoTaskMemFree(spszDataFormats._pszStringData);
          objectStream.lpVtbl = (struct IStreamVtbl *)CBaseMInterfacePointerMarshalingStream::`vftable';
          if ( objectStream._fFree )
            HeapFree(g_hHeap, 0, objectStream._pMInterfacePointer);
          goto LABEL_187;
        }
        v68 = edpContext.m_ptr;
        if ( edpContext.m_ptr )
        {
          edpContext.m_ptr = 0;
          (*(void (__fastcall **)(EDP_CONTEXT *))(*(_QWORD *)&v68->contextStates + 16LL))(v68);
        }
      }
    }
    *(_DWORD *)(&formatetc.cfFormat + 1) = 0;
    formatetc.cfFormat = 15;
    v69.lpVtbl = pszStringData->lpVtbl;
    *(&formatetc.cfFormat + 3) = 0;
    *(_QWORD *)&formatetc.tymed = 1;
    formatetc.ptd = 0;
    Release = v69.lpVtbl[1].Release;
    formatetc.lindex = -1;
    formatetc.dwAspect = 1;
    v71 = ((__int64 (__fastcall *)(IDataObject *, tagFORMATETC *))Release)(pszStringData, &formatetc);
    v72 = spszDataFormats._pszStringData;
    v73 = spszDataFormats._pszStringData;
    this->m_hasHDROPClipboardFormat = v71 == 0;
    DragDropTelemetry::DragDropSession::DragStarted(&this->_telemetrySession, v73);
    if ( !this->m_isEdpActive )
      goto LABEL_207;
    formatetc.cfFormat = g_cfEnterpriseDataProtectionId;
    v74.lpVtbl = pszStringData->lpVtbl;
    *(_DWORD *)(&formatetc.cfFormat + 1) = 0;
    *(&formatetc.cfFormat + 3) = 0;
    *(_QWORD *)&formatetc.tymed = 1;
    v75 = v74.lpVtbl[1].Release;
    formatetc.ptd = 0;
    formatetc.lindex = -1;
    formatetc.dwAspect = 1;
    v76 = ((__int64 (__fastcall *)(IDataObject *, tagFORMATETC *))v75)(pszStringData, &formatetc);
    edpContext.m_ptr = 0;
    this->m_dataObjectHasEnterpriseId = v76 == 0;
    v77 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>>::operator&(&edpContext);
    CurrentProcessId = GetCurrentProcessId();
    if ( (int)EdpGetContextForProcess(CurrentProcessId, v77) >= 0 )
    {
      v80 = edpContext.m_ptr;
      enterpriseIdForUIEnforcement = edpContext.m_ptr->enterpriseIdForUIEnforcement;
      if ( !enterpriseIdForUIEnforcement )
        goto LABEL_205;
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        (wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > *)cbData,
        enterpriseIdForUIEnforcement,
        v79);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        &this->m_sourceEnterpriseId,
        (wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > *)cbData);
      if ( *(_QWORD *)cbData )
        CoTaskMemFree(*(LPVOID *)cbData);
      if ( !this->m_sourceEnterpriseId.m_ptr )
      {
        wil::details::in1diag3::Return_Hr(retaddr, 0x606u, "com\\ole32\\ole232\\drag\\drag.cpp", -2147024882);
        if ( edpContext.m_ptr )
          EdpFreeContext();
        if ( v72 )
          CoTaskMemFree(v72);
        objectStream.lpVtbl = (struct IStreamVtbl *)CBaseMInterfacePointerMarshalingStream::`vftable';
        if ( objectStream._fFree )
          HeapFree(g_hHeap, 0, objectStream._pMInterfacePointer);
        objectStream.lpVtbl = (struct IStreamVtbl *)CAbstractStream::`vftable';
        DragDropTelemetry::DragDropSession_Initialize::~DragDropSession_Initialize(&dndInitActivity);
        return 2147942414LL;
      }
    }
    v80 = edpContext.m_ptr;
LABEL_205:
    if ( v80 )
      EdpFreeContext();
LABEL_207:
    wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(&dndInitActivity, v41);
    if ( v72 )
      CoTaskMemFree(v72);
    objectStream.lpVtbl = (struct IStreamVtbl *)CBaseMInterfacePointerMarshalingStream::`vftable';
    if ( objectStream._fFree )
      HeapFree(g_hHeap, 0, objectStream._pMInterfacePointer);
    objectStream.lpVtbl = (struct IStreamVtbl *)CAbstractStream::`vftable';
    dndInitActivity.__vftable = (DragDropTelemetry::DragDropSession_Initialize_vtbl *)DragDropTelemetry::DragDropSession_Initialize::`vftable';
    if ( !dndInitActivity.m_sharedActivityData.m_pCopy )
      goto LABEL_219;
    wil::ActivityBase<DragDropLogging,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      &dndInitActivity,
      (wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (__cdecl*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive,wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t> > > *)&spszDataFormats);
    if ( dndInitActivity.m_sharedActivityData.m_pCopy && dndInitActivity.m_sharedActivityData.m_pCopy->m_refCount == 1 )
    {
      v82 = 1;
    }
    else
    {
      v82 = 0;
      wil::details::shared_object<wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&dndInitActivity.m_sharedActivityData);
    }
    if ( spszDataFormats._pszStringData )
      ReleaseSRWLockExclusive((PSRWLOCK)spszDataFormats._pszStringData);
    if ( v82 )
    {
LABEL_219:
      v83 = dndInitActivity.m_pActivityData;
      if ( dndInitActivity.m_pActivityData->m_State == TlgStateStarted )
      {
        v84 = -2147024322;
        if ( dndInitActivity.m_pActivityData->m_failure.m_failureInfo.hr < 0 )
          v84 = dndInitActivity.m_pActivityData->m_failure.m_failureInfo.hr;
        v85 = dndInitActivity.m_pActivityData->m_stopCountExpected;
        if ( v85 < 1 )
        {
          memset((void *)&failure, 0, sizeof(failure));
          wil::details::WilFailFast(&failure);
        }
        if ( dndInitActivity.m_pActivityData->m_result >= 0 )
          dndInitActivity.m_pActivityData->m_result = v84;
        v83->m_stopCountExpected = v85 - 1;
        dndInitActivity.StopActivity(&dndInitActivity);
      }
    }
    v86 = dndInitActivity.m_callbackHolder.m_threadId == 0;
LABEL_227:
    if ( !v86 )
      wil::details::ThreadFailureCallbackHolder::StopWatching(&dndInitActivity.m_callbackHolder);
    wil::details::shared_object<wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&dndInitActivity.m_sharedActivityData);
    wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>(&dndInitActivity.m_activityData);
    return v41;
  }
  v43 = cddcDefault32;
  if ( !cddcDefault32 )
  {
    v43 = (CDragDefaultCursors *)HeapAlloc(g_hHeap, 0, 0x40u);
    cddcDefault32 = v43;
    if ( v43 )
    {
      if ( CDragDefaultCursors::Init(v43) )
      {
        v43 = cddcDefault32;
      }
      else
      {
        HeapFree(g_hHeap, 0, cddcDefault32);
        v43 = 0;
        cddcDefault32 = 0;
      }
    }
  }
  this->_pcddcDefault = v43;
  if ( !v43 )
  {
    wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
      &dndInitActivity,
      -2147467259);
    objectStream.lpVtbl = (struct IStreamVtbl *)CBaseMInterfacePointerMarshalingStream::`vftable';
    if ( objectStream._fFree )
      HeapFree(g_hHeap, 0, objectStream._pMInterfacePointer);
    objectStream.lpVtbl = (struct IStreamVtbl *)CAbstractStream::`vftable';
    dndInitActivity.__vftable = (DragDropTelemetry::DragDropSession_Initialize_vtbl *)DragDropTelemetry::DragDropSession_Initialize::`vftable';
    if ( !dndInitActivity.m_sharedActivityData.m_pCopy )
      goto LABEL_115;
    v44 = &dndInitActivity.m_sharedActivityData.m_pCopy->m_object.m_lock;
    AcquireSRWLockExclusive(&dndInitActivity.m_sharedActivityData.m_pCopy->m_object.m_lock.m_lock);
    if ( dndInitActivity.m_sharedActivityData.m_pCopy && dndInitActivity.m_sharedActivityData.m_pCopy->m_refCount == 1 )
    {
      v45 = 1;
    }
    else
    {
      v45 = 0;
      wil::details::shared_object<wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&dndInitActivity.m_sharedActivityData);
    }
    if ( v44 )
      ReleaseSRWLockExclusive(&v44->m_lock);
    if ( v45 )
    {
LABEL_115:
      v46 = dndInitActivity.m_pActivityData;
      if ( dndInitActivity.m_pActivityData->m_State == TlgStateStarted )
      {
        v47 = -2147024322;
        if ( dndInitActivity.m_pActivityData->m_failure.m_failureInfo.hr < 0 )
          v47 = dndInitActivity.m_pActivityData->m_failure.m_failureInfo.hr;
        v48 = dndInitActivity.m_pActivityData->m_stopCountExpected;
        if ( v48 < 1 )
        {
          memset((void *)&failure, 0, sizeof(failure));
          wil::details::WilFailFast(&failure);
        }
        if ( dndInitActivity.m_pActivityData->m_result >= 0 )
          dndInitActivity.m_pActivityData->m_result = v47;
        v46->m_stopCountExpected = v48 - 1;
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
  if ( PrivateClipboardWindow )
  {
    SetCapture(PrivateClipboardWindow);
    this->_fMouseCaptured = 1;
    v41 = 0;
    goto LABEL_127;
  }
  this->_fMouseCaptured = 0;
  wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
    &dndInitActivity,
    -2147467259);
  objectStream.lpVtbl = (struct IStreamVtbl *)CBaseMInterfacePointerMarshalingStream::`vftable';
  if ( objectStream._fFree )
    HeapFree(g_hHeap, 0, objectStream._pMInterfacePointer);
  objectStream.lpVtbl = (struct IStreamVtbl *)CAbstractStream::`vftable';
  DragDropTelemetry::DragDropSession_Initialize::~DragDropSession_Initialize(&dndInitActivity);
  return 2147500037LL;
}

```

## disassembly

```asm
0x18003ca70  mov     [rsp-8+arg_18], rbx
0x18003ca75  push    rbp
0x18003ca76  push    rsi
0x18003ca77  push    rdi
0x18003ca78  push    r12
0x18003ca7a  push    r13
0x18003ca7c  push    r14
0x18003ca7e  push    r15
0x18003ca80  lea     rbp, [rsp-1B0h]
0x18003ca88  sub     rsp, 2B0h
0x18003ca8f  mov     rax, cs:__security_cookie
0x18003ca96  xor     rax, rsp
0x18003ca99  mov     [rbp+1E0h+var_38], rax
0x18003caa0  mov     r14, [rbp+1E0h+arg_30]
0x18003caa7  lea     rax, aDragdropsessio_0; "DragDropSession_Initialize"
0x18003caae  xor     ebx, ebx
0x18003cab0  mov     [rbp+1E0h+dndInitActivity.m_activityData.m_callContext.contextName], rax
0x18003cab4  xorps   xmm1, xmm1
0x18003cab7  mov     [rbp+1E0h+spszDataFormats._pszStringData], pDataObject
0x18003cabe  xor     eax, eax
0x18003cac0  mov     [rsp+2E0h+cbData], dwOKEffects
0x18003cac5  mov     [rbp+1E0h+dndInitActivity.m_activityData.m_failure.m_failureInfo.callerReturnAddress], rax
0x18003cacc  mov     rsi, pDropSource
0x18003cacf  mov     qword ptr [rbp+1E0h+dndInitActivity.m_activityData.m_lock.m_lock.___u0], rax
0x18003cad6  lea     pDropSource, aOledragdrop; "OleDragDrop"
0x18003cadd  lea     rax, [rbp+1E0h+dndInitActivity.m_activityData]
0x18003cae1  mov     [rbp+1E0h+dndInitActivity.m_activityData.m_State], ebx
0x18003cae4  mov     [rbp+1E0h+dndInitActivity.m_pActivityData], rax
0x18003caeb  mov     r13, pDataObject
0x18003caee  lea     rax, [rbp+1E0h+dndInitActivity]
0x18003caf2  mov     [rbp+1E0h+dndInitActivity.m_activityData.m_HasRelatedId], bl
0x18003caf5  mov     [rbp+1E0h+dndInitActivity.m_callbackHolder.m_pCallback], rax
0x18003cafc  lea     pDataObject, aDragoperationi; "DragOperationInit"
0x18003cb03  lea     rax, [rbp+1E0h+dndInitActivity.m_activityData.m_callContext]
0x18003cb07  mov     [rbp+1E0h+dndInitActivity.m_activityData.m_callContext.m_ownsMessage], bl
0x18003cb0a  mov     [rbp+1E0h+dndInitActivity.m_callbackHolder.m_pCallContext], rax
0x18003cb11  mov     rdi, this
0x18003cb14  lea     rax, ??_7DragDropSession_Initialize@DragDropTelemetry@@6B@; const DragDropTelemetry::DragDropSession_Initialize::`vftable'
0x18003cb1b  mov     [rbp+1E0h+dndInitActivity.m_activityData.m_callContext.contextId], ebx
0x18003cb1e  xorps   xmm0, xmm0
0x18003cb21  mov     [rbp+1E0h+dndInitActivity.__vftable], rax
0x18003cb25  lea     this, [rbp+1E0h+dndInitActivity]; this
0x18003cb29  mov     [rbp+1E0h+dndInitActivity.m_activityData.m_callContext.contextMessage], rbx
0x18003cb2d  mov     r12d, dwOKEffects
0x18003cb30  mov     [rbp+1E0h+dndInitActivity.m_activityData.m_result], ebx
0x18003cb33  movdqa  xmmword ptr [rbp+1E0h+dndInitActivity.m_activityData.m_failure.m_spStrings.m_pCopy], xmm0
0x18003cb3b  movups  xmmword ptr [rbp+1E0h+dndInitActivity.m_activityData.m_failure.m_failureInfo.type], xmm1
0x18003cb3f  mov     [rbp+1E0h+dndInitActivity.m_activityData.m_stopCountExpected], 1
0x18003cb49  movups  xmmword ptr [rbp+1E0h+dndInitActivity.m_activityData.m_failure.m_failureInfo.failureId], xmm1
0x18003cb4d  mov     [rbp+1E0h+dndInitActivity.m_sharedActivityData.m_pCopy], rbx
0x18003cb54  movups  xmmword ptr [rbp+1E0h+dndInitActivity.m_activityData.m_failure.m_failureInfo.threadId], xmm1
0x18003cb5b  mov     [rbp+1E0h+dndInitActivity.m_callbackHolder.m_ppThreadList], rbx
0x18003cb62  movups  xmmword ptr [rbp+1E0h+dndInitActivity.m_activityData.m_failure.m_failureInfo.pszFunction], xmm1
0x18003cb69  mov     [rbp+1E0h+dndInitActivity.m_callbackHolder.m_pNext], rbx
0x18003cb70  movups  xmmword ptr [rbp+1E0h+dndInitActivity.m_activityData.m_failure.m_failureInfo.uLineNumber], xmm1
0x18003cb77  mov     [rbp+1E0h+dndInitActivity.m_callbackHolder.m_threadId], ebx
0x18003cb7d  movups  xmmword ptr [rbp+1E0h+dndInitActivity.m_activityData.m_failure.m_failureInfo.callContextOriginating.contextId], xmm1
0x18003cb84  mov     [rbp+1E0h+dndInitActivity.m_callbackHolder.m_handlingNotify], bl
0x18003cb8a  movups  xmmword ptr [rbp+1E0h+dndInitActivity.m_activityData.m_failure.m_failureInfo.callContextOriginating.contextMessage], xmm1
0x18003cb91  movups  xmmword ptr [rbp+1E0h+dndInitActivity.m_activityData.m_failure.m_failureInfo.callContextCurrent.contextName], xmm1
0x18003cb98  movups  xmmword ptr [rbp+1E0h+dndInitActivity.m_activityData.m_failure.m_failureInfo.pszModule], xmm1
0x18003cb9f  call    ?StartActivity@DragDropSession_Initialize@DragDropTelemetry@@QEAAXPEBG0@Z; DragDropTelemetry::DragDropSession_Initialize::StartActivity(ushort const *,ushort const *)
0x18003cba4  mov     r15d, [rbp+1E0h+arg_28]; __annotation("_TlgProviderLink:|"172"|Key|"\"this\""="DragDropSession_Initialize"")
0x18003cbab  mov     cs:?g_forcedDropTarget@@3VCForcedDropTarget@@A._fDragDropActive, 1; CForcedDropTarget g_forcedDropTarget ...
0x18003cbb5  mov     cs:?g_forcedDropTarget@@3VCForcedDropTarget@@A._hwndFDTCurrent, rbx; CForcedDropTarget g_forcedDropTarget ...
0x18003cbbc  test    r15d, r15d
0x18003cbbf  jnz     short loc_18003CBD4
0x18003cbc1  call    cs:__imp_EdpGetIsManaged
0x18003cbc7  test    eax, eax
0x18003cbc9  jz      short loc_18003CBD4
0x18003cbcb  mov     byte ptr [rdi+230h], 1
0x18003cbd2  jmp     short loc_18003CBE3
0x18003cbd4  mov     [rdi+230h], bl
0x18003cbda  test    r15d, r15d
0x18003cbdd  jnz     loc_18003CD19
0x18003cbe3  test    r13, r13
0x18003cbe6  jnz     loc_18003CD19
0x18003cbec  mov     ebx, 80070057h
0x18003cbf1  lea     this, [rbp+1E0h+dndInitActivity]; this
0x18003cbf5  mov     edx, ebx; hr
0x18003cbf7  call    ?Stop@?$ActivityBase@VDragDropLogging@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18003cbfc  mov     pDataObject, [rbp+1E0h+dndInitActivity.m_sharedActivityData.m_pCopy]
0x18003cc03  lea     rax, ??_7DragDropSession_Initialize@DragDropTelemetry@@6B@; const DragDropTelemetry::DragDropSession_Initialize::`vftable'
0x18003cc0a  mov     [rbp+1E0h+dndInitActivity.__vftable], rax
0x18003cc0e  test    pDataObject, pDataObject
0x18003cc11  jz      short loc_18003CC68
0x18003cc13  xor     ecx, ecx
0x18003cc15  lea     rax, [pDataObject+8]
0x18003cc19  test    pDataObject, pDataObject
0x18003cc1c  cmovnz  this, rax
0x18003cc20  lea     rdi, [this+100h]
0x18003cc27  mov     this, rdi; SRWLock
0x18003cc2a  call    cs:__imp_AcquireSRWLockExclusive
0x18003cc30  mov     rax, [rbp+1E0h+dndInitActivity.m_sharedActivityData.m_pCopy]
0x18003cc37  test    rax, rax
0x18003cc3a  jz      short loc_18003CC46
0x18003cc3c  cmp     dword ptr [rax], 1
0x18003cc3f  jnz     short loc_18003CC46
0x18003cc41  mov     sil, 1
0x18003cc44  jmp     short loc_18003CC55
0x18003cc46  xor     sil, sil
0x18003cc49  lea     this, [rbp+1E0h+dndInitActivity.m_sharedActivityData]; this
0x18003cc50  call    ?reset@?$shared_object@V?$ActivityData@VDragDropLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDragDropLogging@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18003cc55  test    rdi, rdi
0x18003cc58  jz      short loc_18003CC63
0x18003cc5a  mov     this, rdi; SRWLock
0x18003cc5d  call    cs:__imp_ReleaseSRWLockExclusive
0x18003cc63  test    sil, sil
0x18003cc66  jz      short loc_18003CCB2
0x18003cc68  mov     pDataObject, [rbp+1E0h+dndInitActivity.m_pActivityData]
0x18003cc6f  cmp     dword ptr [pDataObject], 1
0x18003cc72  jnz     short loc_18003CCB2
0x18003cc74  mov     eax, [pDataObject+58h]
0x18003cc77  mov     ecx, 8007023Eh
0x18003cc7c  test    eax, eax
0x18003cc7e  cmovs   ecx, eax
0x18003cc81  mov     eax, [pDataObject+0F8h]
0x18003cc87  cmp     eax, 1
0x18003cc8a  jl      loc_18003DE86
0x18003cc90  cmp     dword ptr [pDataObject+48h], 0
0x18003cc94  jl      short loc_18003CC99
0x18003cc96  mov     [pDataObject+48h], ecx
0x18003cc99  dec     eax
0x18003cc9b  lea     this, [rbp+1E0h+dndInitActivity]
0x18003cc9f  mov     [pDataObject+0F8h], eax
0x18003cca5  mov     rax, [rbp+1E0h+dndInitActivity.__vftable]
0x18003cca9  mov     rax, [rax+8]
0x18003ccad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ccb2  cmp     [rbp+1E0h+dndInitActivity.m_callbackHolder.m_threadId], 0
0x18003ccb9  jz      short loc_18003CCC7
0x18003ccbb  lea     this, [rbp+1E0h+dndInitActivity.m_callbackHolder]; this
0x18003ccc2  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18003ccc7  mov     rax, [rbp+1E0h+dndInitActivity.m_sharedActivityData.m_pCopy]
0x18003ccce  test    rax, rax
0x18003ccd1  jz      loc_18003DDDF
0x18003ccd7  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18003ccde  lock xadd [rax], esi
0x18003cce2  cmp     esi, 1
0x18003cce5  jnz     short loc_18003CD09
0x18003cce7  mov     rdi, [rbp+1E0h+dndInitActivity.m_sharedActivityData.m_pCopy]
0x18003ccee  test    rdi, rdi
0x18003ccf1  jz      short loc_18003CD09
0x18003ccf3  lea     this, [rdi+8]; this
0x18003ccf7  call    ??1?$ActivityData@VDragDropLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDragDropLogging@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x18003ccfc  mov     edx, 110h; __formal
0x18003cd01  mov     this, rdi; block
0x18003cd04  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003cd09  mov     [rbp+1E0h+dndInitActivity.m_sharedActivityData.m_pCopy], 0
0x18003cd14  jmp     loc_18003DDDF
0x18003cd19  mov     dwOKEffects, 1F0003h; dwDesiredAccess
0x18003cd1f  lea     pDataObject, aLocalOledragsy; "Local\\OLEDragSynchronizationMutex"
0x18003cd26  xor     r8d, r8d; dwFlags
0x18003cd29  xor     ecx, ecx; lpEventAttributes
0x18003cd2b  call    cs:__imp_CreateEventExW
0x18003cd31  mov     [rdi+0B0h], rax
0x18003cd38  test    rax, rax
0x18003cd3b  jz      loc_18003CE9B
0x18003cd41  call    cs:__imp_GetLastError
0x18003cd47  cmp     eax, 0B7h
0x18003cd4c  setz    cl
0x18003cd4f  mov     [rdi+0CCh], cl
0x18003cd55  jnz     loc_18003CDF1
0x18003cd5b  test    r15d, r15d
0x18003cd5e  jz      short loc_18003CDD3
0x18003cd60  mov     ebx, 80040103h
0x18003cd65  xor     edx, edx
0x18003cd67  mov     ecx, ebx
0x18003cd69  call    cs:__imp_RoOriginateError
0x18003cd6f  mov     edx, ebx; hr
0x18003cd71  lea     this, [rbp+1E0h+dndInitActivity]; this
0x18003cd75  call    ?Stop@?$ActivityBase@VDragDropLogging@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18003cd7a  mov     pDataObject, [rbp+1E0h+dndInitActivity.m_sharedActivityData.m_pCopy]
0x18003cd81  lea     rax, ??_7DragDropSession_Initialize@DragDropTelemetry@@6B@; const DragDropTelemetry::DragDropSession_Initialize::`vftable'
0x18003cd88  mov     [rbp+1E0h+dndInitActivity.__vftable], rax
0x18003cd8c  test    pDataObject, pDataObject
0x18003cd8f  jz      loc_18003DD78
0x18003cd95  xor     ecx, ecx
0x18003cd97  lea     rax, [pDataObject+8]
0x18003cd9b  test    pDataObject, pDataObject
0x18003cd9e  cmovnz  this, rax
0x18003cda2  lea     rdi, [this+100h]
0x18003cda9  mov     this, rdi; SRWLock
0x18003cdac  call    cs:__imp_AcquireSRWLockExclusive
0x18003cdb2  mov     rax, [rbp+1E0h+dndInitActivity.m_sharedActivityData.m_pCopy]
0x18003cdb9  test    rax, rax
0x18003cdbc  jz      loc_18003DD56
0x18003cdc2  cmp     dword ptr [rax], 1
0x18003cdc5  jnz     loc_18003DD56
0x18003cdcb  mov     sil, 1
0x18003cdce  jmp     loc_18003DD65
0x18003cdd3  cmp     cs:?s_fDoDragDropInFlight@CDragOperation@@0_NA, bl; bool CDragOperation::s_fDoDragDropInFlight
0x18003cdd9  jnz     loc_18003CEBA
0x18003cddf  call    ?IsContainerDragOperation@@YA_NXZ; IsContainerDragOperation(void)
0x18003cde4  test    al, al
0x18003cde6  jnz     loc_18003CEBA
0x18003cdec  jmp     loc_18003CD60
0x18003cdf1  test    r15d, r15d
0x18003cdf4  jnz     short loc_18003CDFD
0x18003cdf6  mov     cs:?s_fDoDragDropInFlight@CDragOperation@@0_NA, 1; bool CDragOperation::s_fDoDragDropInFlight
0x18003cdfd  lea     pDataObject, [rsp+2E0h+edpContext]; ppExtension
0x18003ce02  mov     [rsp+2E0h+edpContext.m_ptr], rbx
0x18003ce07  mov     this, rdi; this
0x18003ce0a  call    ?GetWinRtExtension@CDragOperation@@AEAAJPEAPEAUIDragDropExtensionForOLE@@@Z; CDragOperation::GetWinRtExtension(IDragDropExtensionForOLE * *)
0x18003ce0f  mov     ebx, eax
0x18003ce11  test    eax, eax
0x18003ce13  js      short loc_18003CE67
0x18003ce15  mov     r12, [rsp+2E0h+edpContext.m_ptr]
0x18003ce1a  mov     this, [rdi+0D8h]
0x18003ce21  mov     rax, [r12]
0x18003ce25  mov     r13, [rax+30h]
0x18003ce29  test    this, this
0x18003ce2c  jz      short loc_18003CE45
0x18003ce2e  mov     qword ptr [rdi+0D8h], 0
0x18003ce39  mov     pDropSource, [this]
0x18003ce3c  mov     rax, [pDropSource+10h]
0x18003ce40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ce45  lea     pDataObject, [rdi+0D8h]
0x18003ce4c  mov     this, r12
0x18003ce4f  mov     rax, r13
0x18003ce52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ce57  mov     r13, [rbp+1E0h+spszDataFormats._pszStringData]
0x18003ce5e  mov     ebx, eax
0x18003ce60  mov     r12d, [rsp+2E0h+cbData]
0x18003ce65  jmp     short loc_18003CE7A
0x18003ce67  cmp     eax, 80040154h
0x18003ce6c  jz      short loc_18003CE78
0x18003ce6e  add     eax, 7FF8FFFEh
0x18003ce73  cmp     eax, 1
0x18003ce76  ja      short loc_18003CE7A
0x18003ce78  xor     ebx, ebx
0x18003ce7a  mov     this, [rsp+2E0h+edpContext.m_ptr]
0x18003ce7f  test    this, this
0x18003ce82  jz      short loc_18003CEB0
0x18003ce84  mov     [rsp+2E0h+edpContext.m_ptr], 0
0x18003ce8d  mov     rax, [this]
0x18003ce90  mov     rax, [rax+10h]
0x18003ce94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ce99  jmp     short loc_18003CEB0
0x18003ce9b  call    cs:__imp_GetLastError
0x18003cea1  mov     ebx, eax
0x18003cea3  test    eax, eax
0x18003cea5  jle     short loc_18003CEB0
0x18003cea7  movzx   ebx, ax
0x18003ceaa  or      ebx, 80070000h
0x18003ceb0  test    ebx, ebx
0x18003ceb2  js      loc_18003CD6F
0x18003ceb8  xor     ebx, ebx
0x18003ceba  test    r14, r14
0x18003cebd  jz      short loc_18003CEC4
0x18003cebf  mov     this, [r14]
0x18003cec2  jmp     short loc_18003CEC7
0x18003cec4  mov     this, rbx; hToken
0x18003cec7  lea     pDropSource, [rdi+0C8h]; hToken
0x18003cece  call    ?IsTokenBoolPresent@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAH@Z; IsTokenBoolPresent(void *,_TOKEN_INFORMATION_CLASS,int *)
0x18003ced3  mov     ebx, eax
0x18003ced5  test    eax, eax
0x18003ced7  js      loc_18003CD6F
0x18003cedd  cmp     [rbp+1E0h+arg_38], 0
0x18003cee4  mov     [rdi+0A8h], r15d
0x18003ceeb  setnz   al
0x18003ceee  mov     [rdi+249h], al
0x18003cef4  test    r14, r14
0x18003cef7  jz      short loc_18003CF0A
0x18003cef9  mov     rax, [r14]
0x18003cefc  mov     [rdi+0C0h], rax
0x18003cf03  mov     qword ptr [r14], 0
0x18003cf0a  test    byte ptr cs:Microsoft_Windows_OLE_PerfEnableBits, 1
0x18003cf11  jz      short loc_18003CF31
0x18003cf13  lea     rax, [rbp+1E0h+spszDataFormats]
0x18003cf1a  mov     dwOKEffects, 1; Context
0x18003cf20  lea     pDataObject, OLE_DragDrop_DragOperation_SetDataObject_Start; EventDataCount
0x18003cf27  mov     [rsp+2E0h+Descriptor], rax; Descriptor
0x18003cf2c  call    McGenEventWrite_EventWriteTransfer
0x18003cf31  cmp     qword ptr [rdi+10h], 0
0x18003cf36  jnz     short loc_18003CF65
0x18003cf38  cmp     byte ptr [rdi+0B8h], 0
0x18003cf3f  jnz     short loc_18003CF65
0x18003cf41  test    r13, r13
0x18003cf44  jnz     short loc_18003CF4D
0x18003cf46  mov     ebx, 80070057h
0x18003cf4b  jmp     short loc_18003CF6A
0x18003cf4d  mov     [rdi+10h], r13
0x18003cf51  xor     ebx, ebx
0x18003cf53  mov     rax, [r13+0]
0x18003cf57  mov     this, r13
0x18003cf5a  mov     rax, [rax+8]
0x18003cf5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf63  jmp     short loc_18003CF6A
0x18003cf65  mov     ebx, 8000000Eh
0x18003cf6a  test    byte ptr cs:Microsoft_Windows_OLE_PerfEnableBits, 1
0x18003cf71  jz      short loc_18003CF82
0x18003cf73  mov     r8d, ebx; Context
0x18003cf76  lea     pDataObject, OLE_DragDrop_DragOperation_SetDataObject_Stop; _Arg0
0x18003cf7d  call    McTemplateU0d_EventWriteTransfer
0x18003cf82  test    ebx, ebx
0x18003cf84  jns     loc_18003D036
0x18003cf8a  mov     edx, ebx; hr
0x18003cf8c  lea     this, [rbp+1E0h+dndInitActivity]; this
0x18003cf90  call    ?Stop@?$ActivityBase@VDragDropLogging@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18003cf95  mov     pDataObject, [rbp+1E0h+dndInitActivity.m_sharedActivityData.m_pCopy]
  ... truncated ...
```
