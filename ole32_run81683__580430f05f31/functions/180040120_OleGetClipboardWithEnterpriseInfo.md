# OleGetClipboardWithEnterpriseInfo

- ea: `0x180040120`
- end: `0x1800405b1`
- name: `OleGetClipboardWithEnterpriseInfo`
- size: `1169`
- prototype: `HRESULT __fastcall(IDataObject **dataObject, wchar_t **dataEnterpriseId, wchar_t **sourceDescription, wchar_t **targetDescription, wchar_t **dataDescription)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000a0e8`
- `0x18000b3a0`
- `0x1800185ec`
- `0x180040120`
- `0x1800405b8`
- `0x1800405d4`
- `0x180040640`
- `0x180040660`
- `0x180040698`
- `0x180055f30`
- `0x1800560c4`
- `0x18005639c`
- `0x18008d380`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800402ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800402ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040395`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004042c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040487`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800404e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040513`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040521`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040533`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040395`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004042c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040487`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800404e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040513`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040521`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040533`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetEnterpriseIdForClipboard` at `0x18004027f`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetEnterpriseIdForClipboard` at `0x18004027f`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForWindow` at `0x180040198`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForWindow` at `0x180040198`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x180040155`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x180040155`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetDataInfoFromDataObject` at `0x180040333`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetDataInfoFromDataObject` at `0x180040333`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetAppLockerUniqueAppIdentifier` at `0x1800402f8`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetAppLockerUniqueAppIdentifier` at `0x1800402f8`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetSourceAppIdForClipboard` at `0x1800402b9`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetSourceAppIdForClipboard` at `0x1800402b9`

## string_xrefs

- `0x180040175`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x1800401dd`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x180040216`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x18004028f`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x1800402c9`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x180040308`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x180040343`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x1800403a8`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x18004043f`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x18004049a`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x1800404f4`: `com\ole32\ole232\clipbrd\clipapi.cpp`

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
  wchar_t *v6; // rsi
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
  wchar_t *v24; // rdi
  wchar_t *v25; // rax
  wchar_t **v26; // rcx
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&wil::details::FreeProcessHeap,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > heapDataDescription; // [rsp+20h] [rbp-28h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (__cdecl*)(EDP_CONTEXT *),&EdpFreeContext,wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t> > > edpContext; // [rsp+28h] [rbp-20h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > coTaskTargetDescription; // [rsp+30h] [rbp-18h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > coTaskDataEnterpriseId; // [rsp+38h] [rbp-10h] BYREF
  void *retaddr; // [rsp+88h] [rbp+40h]
  Microsoft::WRL::ComPtr<IDataObject> localDataObject; // [rsp+90h] [rbp+48h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&wil::details::FreeProcessHeap,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > heapDataEnterpriseId; // [rsp+98h] [rbp+50h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&wil::details::FreeProcessHeap,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > heapSourceDescription; // [rsp+A0h] [rbp+58h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&wil::details::FreeProcessHeap,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > heapTargetDescription; // [rsp+A8h] [rbp+60h] BYREF

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
      goto LABEL_56;
    }
    if ( (edpContext.m_ptr->contextStates & 1) == 0
      && ((edpContext.m_ptr->contextStates & 2) == 0 || !edpContext.m_ptr->allowedEnterpriseIdCount) )
    {
      ContextForWindow = OleGetClipboard(dataObject);
      v12 = ContextForWindow;
      if ( ContextForWindow < 0 )
      {
        v14 = 2716;
        goto LABEL_11;
      }
LABEL_56:
      wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(&edpContext);
      return v12;
    }
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
        wil::last_error_context::last_error_context((wil::last_error_context *)&coTaskDataEnterpriseId);
        wil::details::FreeProcessHeap(m_ptr);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&coTaskDataEnterpriseId);
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
              if ( !heapDataEnterpriseId.m_ptr )
                goto LABEL_35;
              wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                &coTaskTargetDescription,
                heapDataEnterpriseId.m_ptr,
                v22);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                &coTaskDataEnterpriseId,
                &coTaskTargetDescription);
              if ( coTaskTargetDescription.m_ptr )
                CoTaskMemFree(coTaskTargetDescription.m_ptr);
              v23 = coTaskDataEnterpriseId.m_ptr;
              if ( coTaskDataEnterpriseId.m_ptr )
              {
LABEL_35:
                v24 = 0;
                coTaskTargetDescription.m_ptr = 0;
                if ( !heapSourceDescription.m_ptr )
                  goto LABEL_40;
                wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                  &coTaskDataEnterpriseId,
                  heapSourceDescription.m_ptr,
                  v22);
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                  &coTaskTargetDescription,
                  &coTaskDataEnterpriseId);
                if ( coTaskDataEnterpriseId.m_ptr )
                  CoTaskMemFree(coTaskDataEnterpriseId.m_ptr);
                v24 = coTaskTargetDescription.m_ptr;
                if ( coTaskTargetDescription.m_ptr )
                {
LABEL_40:
                  coTaskTargetDescription.m_ptr = 0;
                  if ( !heapTargetDescription.m_ptr )
                    goto LABEL_45;
                  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                    &coTaskDataEnterpriseId,
                    heapTargetDescription.m_ptr,
                    v22);
                  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                    &coTaskTargetDescription,
                    &coTaskDataEnterpriseId);
                  if ( coTaskDataEnterpriseId.m_ptr )
                    CoTaskMemFree(coTaskDataEnterpriseId.m_ptr);
                  v6 = coTaskTargetDescription.m_ptr;
                  if ( coTaskTargetDescription.m_ptr )
                  {
LABEL_45:
                    v25 = 0;
                    coTaskTargetDescription.m_ptr = 0;
                    if ( !heapDataDescription.m_ptr )
                      goto LABEL_55;
                    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                      &coTaskDataEnterpriseId,
                      heapDataDescription.m_ptr,
                      v22);
                    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                      &coTaskTargetDescription,
                      &coTaskDataEnterpriseId);
                    if ( coTaskDataEnterpriseId.m_ptr )
                      CoTaskMemFree(coTaskDataEnterpriseId.m_ptr);
                    v25 = coTaskTargetDescription.m_ptr;
                    if ( coTaskTargetDescription.m_ptr )
                    {
LABEL_55:
                      *dataObject = localDataObject.ptr_;
                      v26 = dataDescription;
                      *dataEnterpriseId = v23;
                      *sourceDescription = v24;
                      *targetDescription = v6;
                      *v26 = v25;
                      localDataObject.ptr_ = 0;
                      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&heapDataDescription);
                      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&heapTargetDescription);
                      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&heapSourceDescription);
                      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&heapDataEnterpriseId);
                      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&localDataObject);
                      EdpInlSetCurrentThreadPolicyEvaluation(0);
                      v12 = 0;
                      goto LABEL_56;
                    }
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      0xACDu,
                      "com\\ole32\\ole232\\clipbrd\\clipapi.cpp",
                      -2147024882);
                    if ( v6 )
                      CoTaskMemFree(v6);
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      0xAC7u,
                      "com\\ole32\\ole232\\clipbrd\\clipapi.cpp",
                      -2147024882);
                  }
                  if ( v24 )
                    CoTaskMemFree(v24);
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    0xAC1u,
                    "com\\ole32\\ole232\\clipbrd\\clipapi.cpp",
                    -2147024882);
                }
                if ( v23 )
                  CoTaskMemFree(v23);
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  0xABBu,
                  "com\\ole32\\ole232\\clipbrd\\clipapi.cpp",
                  -2147024882);
              }
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&heapDataDescription);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&heapTargetDescription);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&heapSourceDescription);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&heapDataEnterpriseId);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&localDataObject);
              EdpInlSetCurrentThreadPolicyEvaluation(0);
              v12 = -2147024882;
              goto LABEL_56;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              0xAB4u,
              "com\\ole32\\ole232\\clipbrd\\clipapi.cpp",
              DataInfoFromDataObject);
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
    goto LABEL_56;
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
0x180040120  push    rbp
0x180040122  push    rbx
0x180040123  push    rsi
0x180040124  push    rdi
0x180040125  push    r12
0x180040127  push    r13
0x180040129  push    r14
0x18004012b  push    r15
0x18004012d  mov     rbp, rsp
0x180040130  sub     rsp, 48h
0x180040134  mov     rax, [rbp+arg_20]
0x180040138  xor     esi, esi
0x18004013a  mov     [dataObject], rsi
0x18004013d  mov     r15, targetDescription
0x180040140  mov     [dataEnterpriseId], rsi
0x180040143  mov     r12, sourceDescription
0x180040146  mov     [sourceDescription], rsi
0x180040149  mov     r13, dataEnterpriseId
0x18004014c  mov     [targetDescription], rsi
0x18004014f  mov     r14, dataObject
0x180040152  mov     [rax], rsi
0x180040155  call    cs:__imp_EdpGetIsManaged
0x18004015b  test    eax, eax
0x18004015d  jnz     short loc_18004018E
0x18004015f  mov     dataObject, r14; ppDataObj
0x180040162  call    OleGetClipboard
0x180040167  mov     ebx, eax
0x180040169  test    eax, eax
0x18004016b  jns     loc_18004059E
0x180040171  mov     dataObject, [rbp+40h]; callerReturnAddress
0x180040175  lea     sourceDescription, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x18004017c  mov     r9d, eax; hr
0x18004017f  mov     edx, 0A8Eh; lineNumber
0x180040184  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040189  jmp     loc_18004059E
0x18004018e  lea     dataEnterpriseId, [rbp+edpContext]
0x180040192  mov     [rbp+edpContext.m_ptr], rsi
0x180040196  xor     ecx, ecx
0x180040198  call    cs:__imp_EdpGetContextForWindow
0x18004019e  mov     ebx, eax
0x1800401a0  test    eax, eax
0x1800401a2  jns     short loc_1800401AB
0x1800401a4  mov     edx, 0A92h
0x1800401a9  jmp     short loc_1800401D9
0x1800401ab  mov     rax, [rbp+edpContext.m_ptr]
0x1800401af  mov     ecx, 1; EvaluationDisabled
0x1800401b4  test    [rax], cl
0x1800401b6  jnz     short loc_1800401F1
0x1800401b8  test    byte ptr [rax], 2
0x1800401bb  jz      short loc_1800401C2
0x1800401bd  cmp     [rax+4], esi
0x1800401c0  ja      short loc_1800401F1
0x1800401c2  mov     dataObject, r14; ppDataObj
0x1800401c5  call    OleGetClipboard
0x1800401ca  mov     ebx, eax
0x1800401cc  test    eax, eax
0x1800401ce  jns     loc_180040595
0x1800401d4  mov     edx, 0A9Ch; lineNumber
0x1800401d9  mov     dataObject, [rbp+40h]; callerReturnAddress
0x1800401dd  lea     sourceDescription, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x1800401e4  mov     r9d, eax; hr
0x1800401e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800401ec  jmp     loc_180040595
0x1800401f1  call    ?EdpInlSetCurrentThreadPolicyEvaluation@@YAJH@Z; EdpInlSetCurrentThreadPolicyEvaluation(int)
0x1800401f6  lea     dataObject, [rbp+localDataObject]; this
0x1800401fa  mov     [rbp+localDataObject.ptr_], rsi
0x1800401fe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180040203  lea     dataObject, [rbp+localDataObject]; ppDataObj
0x180040207  call    OleGetClipboard
0x18004020c  mov     ebx, eax
0x18004020e  test    eax, eax
0x180040210  jns     short loc_18004023F
0x180040212  mov     dataObject, [rbp+40h]; callerReturnAddress
0x180040216  lea     sourceDescription, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x18004021d  mov     r9d, eax; hr
0x180040220  mov     edx, 0AA4h; lineNumber
0x180040225  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004022a  lea     dataObject, [rbp+localDataObject]; this
0x18004022e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180040233  xor     ecx, ecx; EvaluationDisabled
0x180040235  call    ?EdpInlSetCurrentThreadPolicyEvaluation@@YAJH@Z; EdpInlSetCurrentThreadPolicyEvaluation(int)
0x18004023a  jmp     loc_180040595
0x18004023f  mov     dataObject, [rbp+localDataObject.ptr_]; dataObject
0x180040243  lea     dataEnterpriseId, [rbp+heapDataEnterpriseId]; ppEnterpriseId
0x180040247  mov     [rbp+heapDataEnterpriseId.m_ptr], rsi
0x18004024b  call    ?GetDataObjectEnterpriseId@@YAJPEAUIDataObject@@PEAPEAG@Z; GetDataObjectEnterpriseId(IDataObject *,ushort * *)
0x180040250  test    eax, eax
0x180040252  jns     short loc_1800402B1
0x180040254  mov     rbx, [rbp+heapDataEnterpriseId.m_ptr]
0x180040258  test    rbx, rbx
0x18004025b  jz      short loc_180040277
0x18004025d  lea     dataObject, [rbp+coTaskDataEnterpriseId]; this
0x180040261  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180040266  mov     dataObject, rbx; ptr
0x180040269  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18004026e  lea     dataObject, [rbp+coTaskDataEnterpriseId]; this
0x180040272  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180040277  lea     dataObject, [rbp+heapDataEnterpriseId]
0x18004027b  mov     [rbp+heapDataEnterpriseId.m_ptr], rsi
0x18004027f  call    cs:__imp_EdpGetEnterpriseIdForClipboard
0x180040285  mov     ebx, eax
0x180040287  test    eax, eax
0x180040289  jns     short loc_1800402B1
0x18004028b  mov     dataObject, [rbp+40h]; callerReturnAddress
0x18004028f  lea     sourceDescription, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x180040296  mov     r9d, eax; hr
0x180040299  mov     edx, 0AAAh; lineNumber
0x18004029e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800402a3  lea     dataObject, [rbp+heapDataEnterpriseId]; this
0x1800402a7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800402ac  jmp     loc_18004022A
0x1800402b1  lea     dataObject, [rbp+heapSourceDescription]
0x1800402b5  mov     [rbp+heapSourceDescription.m_ptr], rsi
0x1800402b9  call    cs:__imp_EdpGetSourceAppIdForClipboard
0x1800402bf  mov     ebx, eax
0x1800402c1  test    eax, eax
0x1800402c3  jns     short loc_1800402E8
0x1800402c5  mov     dataObject, [rbp+40h]; callerReturnAddress
0x1800402c9  lea     sourceDescription, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x1800402d0  mov     r9d, eax; hr
0x1800402d3  mov     edx, 0AAEh; lineNumber
0x1800402d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800402dd  lea     dataObject, [rbp+heapSourceDescription]; this
0x1800402e1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800402e6  jmp     short loc_1800402A3
0x1800402e8  mov     [rbp+heapTargetDescription.m_ptr], rsi
0x1800402ec  call    cs:__imp_GetCurrentProcessId
0x1800402f2  mov     ecx, eax
0x1800402f4  lea     dataEnterpriseId, [rbp+heapTargetDescription]
0x1800402f8  call    cs:__imp_EdpGetAppLockerUniqueAppIdentifier
0x1800402fe  mov     ebx, eax
0x180040300  test    eax, eax
0x180040302  jns     short loc_180040327
0x180040304  mov     dataObject, [rbp+40h]; callerReturnAddress
0x180040308  lea     sourceDescription, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x18004030f  mov     r9d, eax; hr
0x180040312  mov     edx, 0AB1h; lineNumber
0x180040317  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004031c  lea     dataObject, [rbp+heapTargetDescription]; this
0x180040320  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180040325  jmp     short loc_1800402DD
0x180040327  mov     dataObject, [rbp+localDataObject.ptr_]
0x18004032b  lea     dataEnterpriseId, [rbp+heapDataDescription]
0x18004032f  mov     [rbp+heapDataDescription.m_ptr], rsi
0x180040333  call    cs:__imp_EdpGetDataInfoFromDataObject
0x180040339  mov     ebx, eax
0x18004033b  test    eax, eax
0x18004033d  jns     short loc_180040362
0x18004033f  mov     dataObject, [rbp+40h]; callerReturnAddress
0x180040343  lea     sourceDescription, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x18004034a  mov     r9d, eax; hr
0x18004034d  mov     edx, 0AB4h; lineNumber
0x180040352  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040357  lea     dataObject, [rbp+heapDataDescription]; this
0x18004035b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180040360  jmp     short loc_18004031C
0x180040362  mov     dataEnterpriseId, [rbp+heapDataEnterpriseId.m_ptr]; source
0x180040366  mov     rbx, rsi
0x180040369  mov     [rbp+coTaskDataEnterpriseId.m_ptr], rbx
0x18004036d  test    dataEnterpriseId, dataEnterpriseId
0x180040370  jz      loc_1800403FD
0x180040376  lea     dataObject, [rbp+coTaskTargetDescription]; result
0x18004037a  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18004037f  lea     dataEnterpriseId, [rbp+coTaskTargetDescription]; other
0x180040383  lea     dataObject, [rbp+coTaskDataEnterpriseId]; this
0x180040387  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18004038c  mov     dataObject, [rbp+coTaskTargetDescription.m_ptr]; pv
0x180040390  test    dataObject, dataObject
0x180040393  jz      short loc_18004039B
0x180040395  call    cs:__imp_CoTaskMemFree
0x18004039b  mov     rbx, [rbp+coTaskDataEnterpriseId.m_ptr]
0x18004039f  test    rbx, rbx
0x1800403a2  jnz     short loc_1800403FD
0x1800403a4  mov     dataObject, [rbp+40h]; callerReturnAddress
0x1800403a8  lea     sourceDescription, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x1800403af  mov     r9d, 8007000Eh; hr
0x1800403b5  mov     edx, 0ABBh; lineNumber
0x1800403ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800403bf  lea     dataObject, [rbp+heapDataDescription]; this
0x1800403c3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800403c8  lea     dataObject, [rbp+heapTargetDescription]; this
0x1800403cc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800403d1  lea     dataObject, [rbp+heapSourceDescription]; this
0x1800403d5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800403da  lea     dataObject, [rbp+heapDataEnterpriseId]; this
0x1800403de  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800403e3  lea     dataObject, [rbp+localDataObject]; this
0x1800403e7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800403ec  xor     ecx, ecx; EvaluationDisabled
0x1800403ee  call    ?EdpInlSetCurrentThreadPolicyEvaluation@@YAJH@Z; EdpInlSetCurrentThreadPolicyEvaluation(int)
0x1800403f3  mov     ebx, 8007000Eh
0x1800403f8  jmp     loc_180040595
0x1800403fd  mov     dataEnterpriseId, [rbp+heapSourceDescription.m_ptr]; source
0x180040401  mov     rdi, rsi
0x180040404  mov     [rbp+coTaskTargetDescription.m_ptr], rsi
0x180040408  test    dataEnterpriseId, dataEnterpriseId
0x18004040b  jz      short loc_18004045B
0x18004040d  lea     dataObject, [rbp+coTaskDataEnterpriseId]; result
0x180040411  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180040416  lea     dataEnterpriseId, [rbp+coTaskDataEnterpriseId]; other
0x18004041a  lea     dataObject, [rbp+coTaskTargetDescription]; this
0x18004041e  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180040423  mov     dataObject, [rbp+coTaskDataEnterpriseId.m_ptr]; pv
0x180040427  test    dataObject, dataObject
0x18004042a  jz      short loc_180040432
0x18004042c  call    cs:__imp_CoTaskMemFree
0x180040432  mov     rdi, [rbp+coTaskTargetDescription.m_ptr]
0x180040436  test    rdi, rdi
0x180040439  jnz     short loc_18004045B
0x18004043b  mov     dataObject, [rbp+40h]; callerReturnAddress
0x18004043f  lea     sourceDescription, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x180040446  mov     r9d, 8007000Eh; hr
0x18004044c  mov     edx, 0AC1h; lineNumber
0x180040451  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040456  jmp     loc_180040527
0x18004045b  mov     dataEnterpriseId, [rbp+heapTargetDescription.m_ptr]; source
0x18004045f  mov     [rbp+coTaskTargetDescription.m_ptr], rsi
0x180040463  test    dataEnterpriseId, dataEnterpriseId
0x180040466  jz      short loc_1800404B3
0x180040468  lea     dataObject, [rbp+coTaskDataEnterpriseId]; result
0x18004046c  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180040471  lea     dataEnterpriseId, [rbp+coTaskDataEnterpriseId]; other
0x180040475  lea     dataObject, [rbp+coTaskTargetDescription]; this
0x180040479  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18004047e  mov     dataObject, [rbp+coTaskDataEnterpriseId.m_ptr]; pv
0x180040482  test    dataObject, dataObject
0x180040485  jz      short loc_18004048D
0x180040487  call    cs:__imp_CoTaskMemFree
0x18004048d  mov     rsi, [rbp+coTaskTargetDescription.m_ptr]
0x180040491  test    rsi, rsi
0x180040494  jnz     short loc_1800404B3
0x180040496  mov     dataObject, [rbp+40h]; callerReturnAddress
0x18004049a  lea     sourceDescription, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x1800404a1  mov     r9d, 8007000Eh; hr
0x1800404a7  mov     edx, 0AC7h; lineNumber
0x1800404ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800404b1  jmp     short loc_180040519
0x1800404b3  mov     dataEnterpriseId, [rbp+heapDataDescription.m_ptr]; source
0x1800404b7  xor     eax, eax
0x1800404b9  mov     [rbp+coTaskTargetDescription.m_ptr], rax
0x1800404bd  test    dataEnterpriseId, dataEnterpriseId
0x1800404c0  jz      short loc_18004053E
0x1800404c2  lea     dataObject, [rbp+coTaskDataEnterpriseId]; result
0x1800404c6  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800404cb  lea     dataEnterpriseId, [rbp+coTaskDataEnterpriseId]; other
0x1800404cf  lea     dataObject, [rbp+coTaskTargetDescription]; this
0x1800404d3  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800404d8  mov     dataObject, [rbp+coTaskDataEnterpriseId.m_ptr]; pv
0x1800404dc  test    dataObject, dataObject
0x1800404df  jz      short loc_1800404E7
0x1800404e1  call    cs:__imp_CoTaskMemFree
0x1800404e7  mov     rax, [rbp+coTaskTargetDescription.m_ptr]
0x1800404eb  test    rax, rax
0x1800404ee  jnz     short loc_18004053E
0x1800404f0  mov     dataObject, [rbp+40h]; callerReturnAddress
0x1800404f4  lea     sourceDescription, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x1800404fb  mov     r9d, 8007000Eh; hr
0x180040501  mov     edx, 0ACDh; lineNumber
0x180040506  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004050b  test    rsi, rsi
0x18004050e  jz      short loc_180040519
0x180040510  mov     dataObject, rsi; pv
0x180040513  call    cs:__imp_CoTaskMemFree
0x180040519  test    rdi, rdi
0x18004051c  jz      short loc_180040527
0x18004051e  mov     dataObject, rdi; pv
0x180040521  call    cs:__imp_CoTaskMemFree
0x180040527  test    rbx, rbx
0x18004052a  jz      loc_1800403BF
0x180040530  mov     dataObject, rbx; pv
0x180040533  call    cs:__imp_CoTaskMemFree
0x180040539  jmp     loc_1800403BF
0x18004053e  mov     dataObject, [rbp+localDataObject.ptr_]
0x180040542  mov     [r14], dataObject
0x180040545  mov     dataObject, [rbp+arg_20]
0x180040549  mov     [r13+0], rbx
0x18004054d  mov     [r12], rdi
0x180040551  mov     [r15], rsi
0x180040554  mov     [dataObject], rax
0x180040557  lea     dataObject, [rbp+heapDataDescription]; this
0x18004055b  mov     [rbp+localDataObject.ptr_], 0
0x180040563  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180040568  lea     dataObject, [rbp+heapTargetDescription]; this
0x18004056c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180040571  lea     dataObject, [rbp+heapSourceDescription]; this
0x180040575  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004057a  lea     dataObject, [rbp+heapDataEnterpriseId]; this
0x18004057e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180040583  lea     dataObject, [rbp+localDataObject]; this
0x180040587  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004058c  xor     ecx, ecx; EvaluationDisabled
0x18004058e  call    ?EdpInlSetCurrentThreadPolicyEvaluation@@YAJH@Z; EdpInlSetCurrentThreadPolicyEvaluation(int)
0x180040593  xor     ebx, ebx
0x180040595  lea     dataObject, [rbp+edpContext]; this
0x180040599  call    ??1?$unique_storage@U?$resource_policy@PEAUEDP_CONTEXT@@P6AXPEAU1@@Z$1?EdpFreeContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(void)
0x18004059e  mov     eax, ebx
0x1800405a0  add     rsp, 48h
0x1800405a4  pop     r15
0x1800405a6  pop     r14
0x1800405a8  pop     r13
  ... truncated ...
```
