# OleGetClipboardWithEnterpriseInfo

- ea: `0x180089a50`
- end: `0x180089ee1`
- name: `OleGetClipboardWithEnterpriseInfo`
- size: `1169`
- prototype: `HRESULT __fastcall(IDataObject **dataObject, wchar_t **dataEnterpriseId, wchar_t **sourceDescription, wchar_t **targetDescription, wchar_t **dataDescription)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800085a8`
- `0x180009c20`
- `0x18001217c`
- `0x18002a618`
- `0x180049dd4`
- `0x180049edc`
- `0x18004a1c0`
- `0x180061854`
- `0x180062038`
- `0x18008798c`
- `0x1800879ac`
- `0x180088044`
- `0x180088884`
- `0x180089a50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180089c34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180089c34`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForWindow` at `0x180089ace`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForWindow` at `0x180089ace`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x180089a85`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x180089a85`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetDataInfoFromDataObject` at `0x180089c87`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetDataInfoFromDataObject` at `0x180089c87`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetAppLockerUniqueAppIdentifier` at `0x180089c46`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetAppLockerUniqueAppIdentifier` at `0x180089c46`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetSourceAppIdForClipboard` at `0x180089bfb`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetSourceAppIdForClipboard` at `0x180089bfb`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetEnterpriseIdForClipboard` at `0x180089bbb`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetEnterpriseIdForClipboard` at `0x180089bbb`

## string_xrefs

- `0x180089aab`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x180089b19`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x180089b52`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x180089bd1`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x180089c11`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x180089c5c`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x180089c9d`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x180089cf8`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x180089d58`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x180089db5`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x180089e14`: `com\ole32\ole232\clipbrd\clipapi.cpp`

## pseudocode

```c
__int64 __fastcall OleGetClipboardWithEnterpriseInfo(
        IDataObject **dataObject,
        wchar_t **dataEnterpriseId,
        wchar_t **sourceDescription,
        wchar_t **targetDescription,
        wchar_t **dataDescription)
{
  wchar_t **v5; // rax
  wchar_t *v6; // rdi
  int v11; // eax
  unsigned int v12; // ebx
  int ContextForWindow; // eax
  unsigned int v14; // edx
  int Clipboard; // eax
  wchar_t *m_ptr; // rbx
  HRESULT EnterpriseIdForClipboard; // eax
  HRESULT SourceAppIdForClipboard; // eax
  DWORD CurrentProcessId; // eax
  HRESULT AppLockerUniqueAppIdentifier; // eax
  HRESULT DataInfoFromDataObject; // eax
  unsigned __int64 v22; // r8
  wchar_t *v23; // rbx
  wchar_t *v24; // rsi
  wchar_t *v25; // rcx
  IDataObject *ptr; // rax
  wchar_t **v27; // rax
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > coTaskDataEnterpriseId; // [rsp+20h] [rbp-48h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&wil::details::FreeProcessHeap,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > heapDataDescription; // [rsp+28h] [rbp-40h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > coTaskSourceDescription; // [rsp+30h] [rbp-38h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > coTaskTargetDescription; // [rsp+38h] [rbp-30h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > coTaskDataDescription; // [rsp+40h] [rbp-28h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (__cdecl*)(EDP_CONTEXT *),&EdpFreeContext,wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t> > > edpContext; // [rsp+48h] [rbp-20h] BYREF
  wil::last_error_context v35; // [rsp+50h] [rbp-18h] BYREF
  void *retaddr; // [rsp+A8h] [rbp+40h]
  Microsoft::WRL::ComPtr<IDataObject> localDataObject; // [rsp+B0h] [rbp+48h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&wil::details::FreeProcessHeap,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > heapDataEnterpriseId; // [rsp+B8h] [rbp+50h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&wil::details::FreeProcessHeap,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > heapSourceDescription; // [rsp+C0h] [rbp+58h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&wil::details::FreeProcessHeap,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > heapTargetDescription; // [rsp+C8h] [rbp+60h] BYREF

  v5 = dataDescription;
  v6 = 0;
  *dataObject = 0;
  *dataEnterpriseId = 0;
  *sourceDescription = 0;
  *targetDescription = 0;
  *v5 = 0;
  if ( (unsigned int)EdpGetIsManaged() )
  {
    edpContext.m_ptr = 0;
    ContextForWindow = EdpGetContextForWindow(0, &edpContext);
    v12 = ContextForWindow;
    if ( ContextForWindow < 0 )
    {
      v14 = 2706;
LABEL_11:
      wil::details::in1diag3::Return_Hr(retaddr, v14, "com\\ole32\\ole232\\clipbrd\\clipapi.cpp", ContextForWindow);
      goto LABEL_46;
    }
    if ( (edpContext.m_ptr->contextStates & 1) != 0
      || (edpContext.m_ptr->contextStates & 2) != 0 && edpContext.m_ptr->allowedEnterpriseIdCount )
    {
      EdpInlSetCurrentThreadPolicyEvaluation(1);
      localDataObject.ptr_ = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&localDataObject);
      Clipboard = OleGetClipboard(&localDataObject.ptr_);
      v12 = Clipboard;
      if ( Clipboard >= 0 )
      {
        heapDataEnterpriseId.m_ptr = 0;
        if ( GetDataObjectEnterpriseId(localDataObject.ptr_, &heapDataEnterpriseId.m_ptr) >= 0 )
          goto LABEL_21;
        m_ptr = heapDataEnterpriseId.m_ptr;
        if ( heapDataEnterpriseId.m_ptr )
        {
          wil::last_error_context::last_error_context(&v35);
          wil::details::FreeProcessHeap(m_ptr);
          wil::last_error_context::~last_error_context(&v35);
        }
        heapDataEnterpriseId.m_ptr = 0;
        EnterpriseIdForClipboard = EdpGetEnterpriseIdForClipboard(&heapDataEnterpriseId);
        v12 = EnterpriseIdForClipboard;
        if ( EnterpriseIdForClipboard >= 0 )
        {
LABEL_21:
          heapSourceDescription.m_ptr = 0;
          SourceAppIdForClipboard = EdpGetSourceAppIdForClipboard(&heapSourceDescription);
          v12 = SourceAppIdForClipboard;
          if ( SourceAppIdForClipboard >= 0 )
          {
            heapTargetDescription.m_ptr = 0;
            CurrentProcessId = GetCurrentProcessId();
            AppLockerUniqueAppIdentifier = EdpGetAppLockerUniqueAppIdentifier(CurrentProcessId, &heapTargetDescription);
            v12 = AppLockerUniqueAppIdentifier;
            if ( AppLockerUniqueAppIdentifier >= 0 )
            {
              heapDataDescription.m_ptr = 0;
              DataInfoFromDataObject = EdpGetDataInfoFromDataObject(localDataObject.ptr_, &heapDataDescription);
              v12 = DataInfoFromDataObject;
              if ( DataInfoFromDataObject >= 0 )
              {
                v23 = 0;
                coTaskDataEnterpriseId.m_ptr = 0;
                if ( !heapDataEnterpriseId.m_ptr
                  || (wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                        &coTaskDataDescription,
                        heapDataEnterpriseId.m_ptr,
                        v22),
                      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                        &coTaskDataEnterpriseId,
                        &coTaskDataDescription),
                      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&coTaskDataDescription),
                      (v23 = coTaskDataEnterpriseId.m_ptr) != 0) )
                {
                  v24 = 0;
                  coTaskSourceDescription.m_ptr = 0;
                  if ( !heapSourceDescription.m_ptr
                    || (wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                          &coTaskDataDescription,
                          heapSourceDescription.m_ptr,
                          v22),
                        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                          &coTaskSourceDescription,
                          &coTaskDataDescription),
                        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&coTaskDataDescription),
                        (v24 = coTaskSourceDescription.m_ptr) != 0) )
                  {
                    coTaskTargetDescription.m_ptr = 0;
                    if ( !heapTargetDescription.m_ptr
                      || (wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                            &coTaskDataDescription,
                            heapTargetDescription.m_ptr,
                            v22),
                          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                            &coTaskTargetDescription,
                            &coTaskDataDescription),
                          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&coTaskDataDescription),
                          (v6 = coTaskTargetDescription.m_ptr) != 0) )
                    {
                      v25 = 0;
                      coTaskDataDescription.m_ptr = 0;
                      if ( !heapDataDescription.m_ptr
                        || (wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                              (wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > *)&v35,
                              heapDataDescription.m_ptr,
                              v22),
                            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                              &coTaskDataDescription,
                              (wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > *)&v35),
                            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > *)&v35),
                            (v25 = coTaskDataDescription.m_ptr) != 0) )
                      {
                        ptr = localDataObject.ptr_;
                        localDataObject.ptr_ = 0;
                        coTaskDataEnterpriseId.m_ptr = 0;
                        coTaskSourceDescription.m_ptr = 0;
                        coTaskTargetDescription.m_ptr = 0;
                        coTaskDataDescription.m_ptr = 0;
                        *dataObject = ptr;
                        v27 = dataDescription;
                        *dataEnterpriseId = v23;
                        *sourceDescription = v24;
                        *targetDescription = v6;
                        *v27 = v25;
                        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&coTaskDataDescription);
                        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&coTaskTargetDescription);
                        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&coTaskSourceDescription);
                        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&coTaskDataEnterpriseId);
                        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&heapDataDescription);
                        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&heapTargetDescription);
                        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&heapSourceDescription);
                        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&heapDataEnterpriseId);
                        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&localDataObject);
                        EdpInlSetCurrentThreadPolicyEvaluation(0);
                        v12 = 0;
                        goto LABEL_46;
                      }
                      v12 = -2147024882;
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        0xACDu,
                        "com\\ole32\\ole232\\clipbrd\\clipapi.cpp",
                        -2147024882);
                      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&coTaskDataDescription);
                    }
                    else
                    {
                      v12 = -2147024882;
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        0xAC7u,
                        "com\\ole32\\ole232\\clipbrd\\clipapi.cpp",
                        -2147024882);
                    }
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&coTaskTargetDescription);
                  }
                  else
                  {
                    v12 = -2147024882;
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      0xAC1u,
                      "com\\ole32\\ole232\\clipbrd\\clipapi.cpp",
                      -2147024882);
                  }
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&coTaskSourceDescription);
                }
                else
                {
                  v12 = -2147024882;
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    0xABBu,
                    "com\\ole32\\ole232\\clipbrd\\clipapi.cpp",
                    -2147024882);
                }
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&coTaskDataEnterpriseId);
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  0xAB4u,
                  "com\\ole32\\ole232\\clipbrd\\clipapi.cpp",
                  DataInfoFromDataObject);
              }
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&heapDataDescription);
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                0xAB1u,
                "com\\ole32\\ole232\\clipbrd\\clipapi.cpp",
                AppLockerUniqueAppIdentifier);
            }
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&heapTargetDescription);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              0xAAEu,
              "com\\ole32\\ole232\\clipbrd\\clipapi.cpp",
              SourceAppIdForClipboard);
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&heapSourceDescription);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            0xAAAu,
            "com\\ole32\\ole232\\clipbrd\\clipapi.cpp",
            EnterpriseIdForClipboard);
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&heapDataEnterpriseId);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(retaddr, 0xAA4u, "com\\ole32\\ole232\\clipbrd\\clipapi.cpp", Clipboard);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&localDataObject);
      EdpInlSetCurrentThreadPolicyEvaluation(0);
    }
    else
    {
      ContextForWindow = OleGetClipboard(dataObject);
      v12 = ContextForWindow;
      if ( ContextForWindow < 0 )
      {
        v14 = 2716;
        goto LABEL_11;
      }
    }
LABEL_46:
    wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(&edpContext);
    return v12;
  }
  v11 = OleGetClipboard(dataObject);
  v12 = v11;
  if ( v11 < 0 )
    wil::details::in1diag3::Return_Hr(retaddr, 0xA8Eu, "com\\ole32\\ole232\\clipbrd\\clipapi.cpp", v11);
  return v12;
}

```

## disassembly

```asm
0x180089a50  push    rbp
0x180089a52  push    rbx
0x180089a53  push    rsi
0x180089a54  push    rdi
0x180089a55  push    r12
0x180089a57  push    r13
0x180089a59  push    r14
0x180089a5b  push    r15
0x180089a5d  mov     rbp, rsp
0x180089a60  sub     rsp, 68h
0x180089a64  mov     rax, [rbp+arg_20]
0x180089a68  xor     edi, edi
0x180089a6a  mov     [dataObject], rdi
0x180089a6d  mov     r15, targetDescription
0x180089a70  mov     [dataEnterpriseId], rdi
0x180089a73  mov     r12, sourceDescription
0x180089a76  mov     [sourceDescription], rdi
0x180089a79  mov     r13, dataEnterpriseId
0x180089a7c  mov     [targetDescription], rdi
0x180089a7f  mov     r14, dataObject
0x180089a82  mov     [rax], rdi
0x180089a85  call    cs:__imp_EdpGetIsManaged
0x180089a8c  nop     dword ptr [rax+rax+00h]
0x180089a91  test    eax, eax
0x180089a93  jnz     short loc_180089AC4
0x180089a95  mov     dataObject, r14; ppDataObj
0x180089a98  call    OleGetClipboard
0x180089a9d  mov     ebx, eax
0x180089a9f  test    eax, eax
0x180089aa1  jns     loc_180089ECD
0x180089aa7  mov     dataObject, [rbp+40h]; callerReturnAddress
0x180089aab  lea     sourceDescription, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x180089ab2  mov     r9d, eax; hr
0x180089ab5  mov     edx, 0A8Eh; lineNumber
0x180089aba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089abf  jmp     loc_180089ECD
0x180089ac4  lea     dataEnterpriseId, [rbp+edpContext]
0x180089ac8  mov     [rbp+edpContext.m_ptr], rdi
0x180089acc  xor     ecx, ecx
0x180089ace  call    cs:__imp_EdpGetContextForWindow
0x180089ad5  nop     dword ptr [rax+rax+00h]
0x180089ada  mov     ebx, eax
0x180089adc  test    eax, eax
0x180089ade  jns     short loc_180089AE7
0x180089ae0  mov     edx, 0A92h
0x180089ae5  jmp     short loc_180089B15
0x180089ae7  mov     rax, [rbp+edpContext.m_ptr]
0x180089aeb  mov     ecx, 1; EvaluationDisabled
0x180089af0  test    [rax], cl
0x180089af2  jnz     short loc_180089B2D
0x180089af4  test    byte ptr [rax], 2
0x180089af7  jz      short loc_180089AFE
0x180089af9  cmp     [rax+4], edi
0x180089afc  ja      short loc_180089B2D
0x180089afe  mov     dataObject, r14; ppDataObj
0x180089b01  call    OleGetClipboard
0x180089b06  mov     ebx, eax
0x180089b08  test    eax, eax
0x180089b0a  jns     loc_180089EC4
0x180089b10  mov     edx, 0A9Ch; lineNumber
0x180089b15  mov     dataObject, [rbp+40h]; callerReturnAddress
0x180089b19  lea     sourceDescription, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x180089b20  mov     r9d, eax; hr
0x180089b23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089b28  jmp     loc_180089EC4
0x180089b2d  call    ?EdpInlSetCurrentThreadPolicyEvaluation@@YAJH@Z; EdpInlSetCurrentThreadPolicyEvaluation(int)
0x180089b32  lea     dataObject, [rbp+localDataObject]; this
0x180089b36  mov     [rbp+localDataObject.ptr_], rdi
0x180089b3a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180089b3f  lea     dataObject, [rbp+localDataObject]; ppDataObj
0x180089b43  call    OleGetClipboard
0x180089b48  mov     ebx, eax
0x180089b4a  test    eax, eax
0x180089b4c  jns     short loc_180089B7B
0x180089b4e  mov     dataObject, [rbp+40h]; callerReturnAddress
0x180089b52  lea     sourceDescription, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x180089b59  mov     r9d, eax; hr
0x180089b5c  mov     edx, 0AA4h; lineNumber
0x180089b61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089b66  lea     dataObject, [rbp+localDataObject]; this
0x180089b6a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180089b6f  xor     ecx, ecx; EvaluationDisabled
0x180089b71  call    ?EdpInlSetCurrentThreadPolicyEvaluation@@YAJH@Z; EdpInlSetCurrentThreadPolicyEvaluation(int)
0x180089b76  jmp     loc_180089EC4
0x180089b7b  mov     dataObject, [rbp+localDataObject.ptr_]; dataObject
0x180089b7f  lea     dataEnterpriseId, [rbp+heapDataEnterpriseId]; ppEnterpriseId
0x180089b83  mov     [rbp+heapDataEnterpriseId.m_ptr], rdi
0x180089b87  call    ?GetDataObjectEnterpriseId@@YAJPEAUIDataObject@@PEAPEAG@Z; GetDataObjectEnterpriseId(IDataObject *,ushort * *)
0x180089b8c  test    eax, eax
0x180089b8e  jns     short loc_180089BF3
0x180089b90  mov     rbx, [rbp+heapDataEnterpriseId.m_ptr]
0x180089b94  test    rbx, rbx
0x180089b97  jz      short loc_180089BB3
0x180089b99  lea     dataObject, [rbp+var_18]; this
0x180089b9d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180089ba2  mov     dataObject, rbx; p
0x180089ba5  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180089baa  lea     dataObject, [rbp+var_18]; this
0x180089bae  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180089bb3  lea     dataObject, [rbp+heapDataEnterpriseId]
0x180089bb7  mov     [rbp+heapDataEnterpriseId.m_ptr], rdi
0x180089bbb  call    cs:__imp_EdpGetEnterpriseIdForClipboard
0x180089bc2  nop     dword ptr [rax+rax+00h]
0x180089bc7  mov     ebx, eax
0x180089bc9  test    eax, eax
0x180089bcb  jns     short loc_180089BF3
0x180089bcd  mov     dataObject, [rbp+40h]; callerReturnAddress
0x180089bd1  lea     sourceDescription, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x180089bd8  mov     r9d, eax; hr
0x180089bdb  mov     edx, 0AAAh; lineNumber
0x180089be0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089be5  lea     dataObject, [rbp+heapDataEnterpriseId]; this
0x180089be9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180089bee  jmp     loc_180089B66
0x180089bf3  lea     dataObject, [rbp+heapSourceDescription]
0x180089bf7  mov     [rbp+heapSourceDescription.m_ptr], rdi
0x180089bfb  call    cs:__imp_EdpGetSourceAppIdForClipboard
0x180089c02  nop     dword ptr [rax+rax+00h]
0x180089c07  mov     ebx, eax
0x180089c09  test    eax, eax
0x180089c0b  jns     short loc_180089C30
0x180089c0d  mov     dataObject, [rbp+40h]; callerReturnAddress
0x180089c11  lea     sourceDescription, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x180089c18  mov     r9d, eax; hr
0x180089c1b  mov     edx, 0AAEh; lineNumber
0x180089c20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089c25  lea     dataObject, [rbp+heapSourceDescription]; this
0x180089c29  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180089c2e  jmp     short loc_180089BE5
0x180089c30  mov     [rbp+heapTargetDescription.m_ptr], rdi
0x180089c34  call    cs:__imp_GetCurrentProcessId
0x180089c3b  nop     dword ptr [rax+rax+00h]
0x180089c40  mov     ecx, eax
0x180089c42  lea     dataEnterpriseId, [rbp+heapTargetDescription]
0x180089c46  call    cs:__imp_EdpGetAppLockerUniqueAppIdentifier
0x180089c4d  nop     dword ptr [rax+rax+00h]
0x180089c52  mov     ebx, eax
0x180089c54  test    eax, eax
0x180089c56  jns     short loc_180089C7B
0x180089c58  mov     dataObject, [rbp+40h]; callerReturnAddress
0x180089c5c  lea     sourceDescription, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x180089c63  mov     r9d, eax; hr
0x180089c66  mov     edx, 0AB1h; lineNumber
0x180089c6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089c70  lea     dataObject, [rbp+heapTargetDescription]; this
0x180089c74  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180089c79  jmp     short loc_180089C25
0x180089c7b  mov     dataObject, [rbp+localDataObject.ptr_]
0x180089c7f  lea     dataEnterpriseId, [rbp+heapDataDescription]
0x180089c83  mov     [rbp+heapDataDescription.m_ptr], rdi
0x180089c87  call    cs:__imp_EdpGetDataInfoFromDataObject
0x180089c8e  nop     dword ptr [rax+rax+00h]
0x180089c93  mov     ebx, eax
0x180089c95  test    eax, eax
0x180089c97  jns     short loc_180089CBC
0x180089c99  mov     dataObject, [rbp+40h]; callerReturnAddress
0x180089c9d  lea     sourceDescription, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x180089ca4  mov     r9d, eax; hr
0x180089ca7  mov     edx, 0AB4h; lineNumber
0x180089cac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089cb1  lea     dataObject, [rbp+heapDataDescription]; this
0x180089cb5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180089cba  jmp     short loc_180089C70
0x180089cbc  mov     dataEnterpriseId, [rbp+heapDataEnterpriseId.m_ptr]; source
0x180089cc0  mov     rbx, rdi
0x180089cc3  mov     [rbp+coTaskDataEnterpriseId.m_ptr], rbx
0x180089cc7  test    dataEnterpriseId, dataEnterpriseId
0x180089cca  jz      short loc_180089D1C
0x180089ccc  lea     dataObject, [rbp+coTaskDataDescription]; result
0x180089cd0  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180089cd5  lea     dataEnterpriseId, [rbp+coTaskDataDescription]; other
0x180089cd9  lea     dataObject, [rbp+coTaskDataEnterpriseId]; this
0x180089cdd  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180089ce2  lea     dataObject, [rbp+coTaskDataDescription]; this
0x180089ce6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180089ceb  mov     rbx, [rbp+coTaskDataEnterpriseId.m_ptr]
0x180089cef  test    rbx, rbx
0x180089cf2  jnz     short loc_180089D1C
0x180089cf4  mov     dataObject, [rbp+40h]; callerReturnAddress
0x180089cf8  lea     sourceDescription, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x180089cff  mov     ebx, 8007000Eh
0x180089d04  mov     edx, 0ABBh; lineNumber
0x180089d09  mov     r9d, ebx; hr
0x180089d0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089d11  lea     dataObject, [rbp+coTaskDataEnterpriseId]; this
0x180089d15  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180089d1a  jmp     short loc_180089CB1
0x180089d1c  mov     dataEnterpriseId, [rbp+heapSourceDescription.m_ptr]; source
0x180089d20  mov     rsi, rdi
0x180089d23  mov     [rbp+coTaskSourceDescription.m_ptr], rdi
0x180089d27  test    dataEnterpriseId, dataEnterpriseId
0x180089d2a  jz      short loc_180089D7C
0x180089d2c  lea     dataObject, [rbp+coTaskDataDescription]; result
0x180089d30  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180089d35  lea     dataEnterpriseId, [rbp+coTaskDataDescription]; other
0x180089d39  lea     dataObject, [rbp+coTaskSourceDescription]; this
0x180089d3d  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180089d42  lea     dataObject, [rbp+coTaskDataDescription]; this
0x180089d46  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180089d4b  mov     rsi, [rbp+coTaskSourceDescription.m_ptr]
0x180089d4f  test    rsi, rsi
0x180089d52  jnz     short loc_180089D7C
0x180089d54  mov     dataObject, [rbp+40h]; callerReturnAddress
0x180089d58  lea     sourceDescription, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x180089d5f  mov     ebx, 8007000Eh
0x180089d64  mov     edx, 0AC1h; lineNumber
0x180089d69  mov     r9d, ebx; hr
0x180089d6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089d71  lea     dataObject, [rbp+coTaskSourceDescription]; this
0x180089d75  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180089d7a  jmp     short loc_180089D11
0x180089d7c  mov     dataEnterpriseId, [rbp+heapTargetDescription.m_ptr]; source
0x180089d80  mov     [rbp+coTaskTargetDescription.m_ptr], rdi
0x180089d84  test    dataEnterpriseId, dataEnterpriseId
0x180089d87  jz      short loc_180089DD9
0x180089d89  lea     dataObject, [rbp+coTaskDataDescription]; result
0x180089d8d  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180089d92  lea     dataEnterpriseId, [rbp+coTaskDataDescription]; other
0x180089d96  lea     dataObject, [rbp+coTaskTargetDescription]; this
0x180089d9a  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180089d9f  lea     dataObject, [rbp+coTaskDataDescription]; this
0x180089da3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180089da8  mov     rdi, [rbp+coTaskTargetDescription.m_ptr]
0x180089dac  test    rdi, rdi
0x180089daf  jnz     short loc_180089DD9
0x180089db1  mov     dataObject, [rbp+40h]; callerReturnAddress
0x180089db5  lea     sourceDescription, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x180089dbc  mov     ebx, 8007000Eh
0x180089dc1  mov     edx, 0AC7h; lineNumber
0x180089dc6  mov     r9d, ebx; hr
0x180089dc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089dce  lea     dataObject, [rbp+coTaskTargetDescription]; this
0x180089dd2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180089dd7  jmp     short loc_180089D71
0x180089dd9  mov     dataEnterpriseId, [rbp+heapDataDescription.m_ptr]; source
0x180089ddd  xor     ecx, ecx
0x180089ddf  mov     [rbp+coTaskDataDescription.m_ptr], dataObject
0x180089de3  test    dataEnterpriseId, dataEnterpriseId
0x180089de6  jz      short loc_180089E38
0x180089de8  lea     dataObject, [rbp+var_18]; result
0x180089dec  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180089df1  lea     dataEnterpriseId, [rbp+var_18]; other
0x180089df5  lea     dataObject, [rbp+coTaskDataDescription]; this
0x180089df9  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180089dfe  lea     dataObject, [rbp+var_18]; this
0x180089e02  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180089e07  mov     dataObject, [rbp+coTaskDataDescription.m_ptr]
0x180089e0b  test    dataObject, dataObject
0x180089e0e  jnz     short loc_180089E38
0x180089e10  mov     dataObject, [rbp+40h]; callerReturnAddress
0x180089e14  lea     sourceDescription, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x180089e1b  mov     ebx, 8007000Eh
0x180089e20  mov     edx, 0ACDh; lineNumber
0x180089e25  mov     r9d, ebx; hr
0x180089e28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089e2d  lea     dataObject, [rbp+coTaskDataDescription]; this
0x180089e31  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180089e36  jmp     short loc_180089DCE
0x180089e38  mov     rax, [rbp+localDataObject.ptr_]
0x180089e3c  and     [rbp+localDataObject.ptr_], 0
0x180089e41  and     [rbp+coTaskDataEnterpriseId.m_ptr], 0
0x180089e46  and     [rbp+coTaskSourceDescription.m_ptr], 0
0x180089e4b  and     [rbp+coTaskTargetDescription.m_ptr], 0
0x180089e50  and     [rbp+coTaskDataDescription.m_ptr], 0
0x180089e55  mov     [r14], rax
0x180089e58  mov     rax, [rbp+arg_20]
0x180089e5c  mov     [r13+0], rbx
0x180089e60  mov     [r12], rsi
0x180089e64  mov     [r15], rdi
0x180089e67  mov     [rax], dataObject
0x180089e6a  lea     dataObject, [rbp+coTaskDataDescription]; this
0x180089e6e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180089e73  lea     dataObject, [rbp+coTaskTargetDescription]; this
0x180089e77  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180089e7c  lea     dataObject, [rbp+coTaskSourceDescription]; this
0x180089e80  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180089e85  lea     dataObject, [rbp+coTaskDataEnterpriseId]; this
0x180089e89  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180089e8e  lea     dataObject, [rbp+heapDataDescription]; this
0x180089e92  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180089e97  lea     dataObject, [rbp+heapTargetDescription]; this
0x180089e9b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180089ea0  lea     dataObject, [rbp+heapSourceDescription]; this
0x180089ea4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180089ea9  lea     dataObject, [rbp+heapDataEnterpriseId]; this
0x180089ead  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180089eb2  lea     dataObject, [rbp+localDataObject]; this
0x180089eb6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180089ebb  xor     ecx, ecx; EvaluationDisabled
0x180089ebd  call    ?EdpInlSetCurrentThreadPolicyEvaluation@@YAJH@Z; EdpInlSetCurrentThreadPolicyEvaluation(int)
0x180089ec2  xor     ebx, ebx
0x180089ec4  lea     dataObject, [rbp+edpContext]; this
0x180089ec8  call    ??1?$unique_storage@U?$resource_policy@PEAUEDP_CONTEXT@@P6AXPEAU1@@Z$1?EdpFreeContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(void)
0x180089ecd  mov     eax, ebx
0x180089ecf  add     rsp, 68h
0x180089ed3  pop     r15
0x180089ed5  pop     r14
0x180089ed7  pop     r13
0x180089ed9  pop     r12
0x180089edb  pop     rdi
  ... truncated ...
```
