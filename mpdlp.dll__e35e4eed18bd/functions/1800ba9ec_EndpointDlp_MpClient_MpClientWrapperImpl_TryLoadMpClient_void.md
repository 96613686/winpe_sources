# EndpointDlp::MpClient::MpClientWrapperImpl::TryLoadMpClient(void)

- ea: `0x1800ba9ec`
- end: `0x1800bb059`
- name: `?TryLoadMpClient@MpClientWrapperImpl@MpClient@EndpointDlp@@AEAA_NXZ`
- size: `1645`
- prototype: `bool __fastcall(EndpointDlp::MpClient::MpClientWrapperImpl *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800ba96c`
- `0x18016e038`
- `0x18016e0c4`

## callees

- `0x180029590`
- `0x1800ba9ec`
- `0x1800bb05c`
- `0x1800cbf98`
- `0x18010cb40`
- `0x18016dd18`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x1800baa4f`
- `KERNEL32!LoadLibraryW` at `0x1800baa4f`
- `KERNEL32!GetProcAddress` at `0x1800baa87`
- `KERNEL32!GetProcAddress` at `0x1800baabb`
- `KERNEL32!GetProcAddress` at `0x1800baaef`
- `KERNEL32!GetProcAddress` at `0x1800bab23`
- `KERNEL32!GetProcAddress` at `0x1800bab57`
- `KERNEL32!GetProcAddress` at `0x1800bab8b`
- `KERNEL32!GetProcAddress` at `0x1800babbf`
- `KERNEL32!GetProcAddress` at `0x1800babf3`
- `KERNEL32!GetProcAddress` at `0x1800bac27`
- `KERNEL32!GetProcAddress` at `0x1800bac5b`
- `KERNEL32!GetProcAddress` at `0x1800bac8f`
- `KERNEL32!GetProcAddress` at `0x1800bacc3`
- `KERNEL32!GetProcAddress` at `0x1800bacf7`
- `KERNEL32!GetProcAddress` at `0x1800bad2b`
- `KERNEL32!GetProcAddress` at `0x1800bad5f`
- `KERNEL32!GetProcAddress` at `0x1800bad96`
- `KERNEL32!GetProcAddress` at `0x1800badcd`
- `KERNEL32!GetProcAddress` at `0x1800bae04`
- `KERNEL32!GetProcAddress` at `0x1800bae3b`
- `KERNEL32!GetProcAddress` at `0x1800bae72`
- `KERNEL32!GetProcAddress` at `0x1800baea9`
- `KERNEL32!GetProcAddress` at `0x1800baee0`
- `KERNEL32!GetProcAddress` at `0x1800baf17`
- `KERNEL32!GetProcAddress` at `0x1800baf4e`
- `KERNEL32!GetProcAddress` at `0x1800baf82`
- `KERNEL32!GetProcAddress` at `0x1800bafb9`
- `KERNEL32!GetProcAddress` at `0x1800baa87`
- `KERNEL32!GetProcAddress` at `0x1800baabb`
- `KERNEL32!GetProcAddress` at `0x1800baaef`
- `KERNEL32!GetProcAddress` at `0x1800bab23`
- `KERNEL32!GetProcAddress` at `0x1800bab57`
- `KERNEL32!GetProcAddress` at `0x1800bab8b`
- `KERNEL32!GetProcAddress` at `0x1800babbf`
- `KERNEL32!GetProcAddress` at `0x1800babf3`
- `KERNEL32!GetProcAddress` at `0x1800bac27`
- `KERNEL32!GetProcAddress` at `0x1800bac5b`
- `KERNEL32!GetProcAddress` at `0x1800bac8f`
- `KERNEL32!GetProcAddress` at `0x1800bacc3`
- `KERNEL32!GetProcAddress` at `0x1800bacf7`
- `KERNEL32!GetProcAddress` at `0x1800bad2b`
- `KERNEL32!GetProcAddress` at `0x1800bad5f`
- `KERNEL32!GetProcAddress` at `0x1800bad96`
- `KERNEL32!GetProcAddress` at `0x1800badcd`
- `KERNEL32!GetProcAddress` at `0x1800bae04`
- `KERNEL32!GetProcAddress` at `0x1800bae3b`
- `KERNEL32!GetProcAddress` at `0x1800bae72`
- `KERNEL32!GetProcAddress` at `0x1800baea9`
- `KERNEL32!GetProcAddress` at `0x1800baee0`
- `KERNEL32!GetProcAddress` at `0x1800baf17`
- `KERNEL32!GetProcAddress` at `0x1800baf4e`
- `KERNEL32!GetProcAddress` at `0x1800baf82`
- `KERNEL32!GetProcAddress` at `0x1800bafb9`

## string_xrefs

- `0x1800baa7d`: `MpManagerOpen`
- `0x1800bab4d`: `MpDlpDispatchAccessEvent`
- `0x1800baae5`: `MpDlpCheckAccessForBuffer`
- `0x1800badfa`: `MpDlpNotifyPostOpenDocumentFile`
- `0x1800badc3`: `MpDlpNotifyPreOpenDocumentFile`

## pseudocode

```c
bool __fastcall EndpointDlp::MpClient::MpClientWrapperImpl::TryLoadMpClient(
        EndpointDlp::MpClient::MpClientWrapperImpl *this)
{
  bool result; // al
  const WCHAR *v3; // rcx
  HMODULE LibraryW; // rax
  HMODULE v5; // rbx
  FARPROC ProcAddress; // rax
  FARPROC v7; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax
  FARPROC v12; // rax
  FARPROC v13; // rax
  FARPROC v14; // rax
  FARPROC v15; // rax
  FARPROC v16; // rax
  FARPROC v17; // rax
  FARPROC v18; // rax
  FARPROC v19; // rax
  FARPROC v20; // rax
  FARPROC v21; // rax
  FARPROC v22; // rax
  FARPROC v23; // rax
  FARPROC v24; // rax
  FARPROC v25; // rax
  FARPROC v26; // rax
  FARPROC v27; // rax
  FARPROC v28; // rax
  FARPROC v29; // rax
  FARPROC v30; // rax
  FARPROC v31; // rax
  struct EndpointDlp::TraceLoggingProvider *v32; // rax
  int v33; // r8d
  int v34; // r9d
  _DWORD *v35; // rcx
  struct EndpointDlp::TraceLoggingProvider *v36; // rax
  _DWORD *v37; // rbx
  struct EndpointDlp::TraceLoggingProvider *v38; // rax
  int v39; // r8d
  int v40; // r9d
  _DWORD *v41; // rcx
  HMODULE v42; // [rsp+40h] [rbp-68h] BYREF
  const wchar_t *v43; // [rsp+48h] [rbp-60h] BYREF
  const wchar_t *v44; // [rsp+50h] [rbp-58h] BYREF
  const wil::ResultException *v45; // [rsp+58h] [rbp-50h] BYREF
  const std::exception *v46; // [rsp+60h] [rbp-48h] BYREF
  LPCWSTR lpLibFileName[4]; // [rsp+68h] [rbp-40h] BYREF
  char v48; // [rsp+88h] [rbp-20h]

  try
  {
    if ( *(_QWORD *)this )
      return 1;
    EndpointDlp::MpClient::_anonymous_namespace_::GetMpClientPath(lpLibFileName);
    v3 = (const WCHAR *)lpLibFileName;
    if ( v48 )
    {
      if ( lpLibFileName[3] > (LPCWSTR)7 )
        v3 = lpLibFileName[0];
      LibraryW = LoadLibraryW(v3);
      v5 = LibraryW;
      v42 = LibraryW;
      if ( LibraryW )
      {
        ProcAddress = GetProcAddress(LibraryW, "MpManagerOpen");
        *((_QWORD *)this + 1) = ProcAddress;
        if ( ProcAddress )
        {
          v7 = GetProcAddress(v5, "MpHandleClose");
          *((_QWORD *)this + 2) = v7;
          if ( v7 )
          {
            v8 = GetProcAddress(v5, "MpDlpCheckAccessForBuffer");
            *((_QWORD *)this + 3) = v8;
            if ( v8 )
            {
              v9 = GetProcAddress(v5, "MpFreeMemory");
              *((_QWORD *)this + 4) = v9;
              if ( v9 )
              {
                v10 = GetProcAddress(v5, "MpDlpDispatchAccessEvent");
                *((_QWORD *)this + 5) = v10;
                if ( v10 )
                {
                  v11 = GetProcAddress(v5, "MpDlpScanLLM");
                  *((_QWORD *)this + 6) = v11;
                  if ( v11 )
                  {
                    v12 = GetProcAddress(v5, "MpGetFCValue");
                    *((_QWORD *)this + 8) = v12;
                    if ( v12 )
                    {
                      v13 = GetProcAddress(v5, "MpNotificationRegister");
                      *((_QWORD *)this + 9) = v13;
                      if ( v13 )
                      {
                        v14 = GetProcAddress(v5, "MpDlpGetEvidenceFileUrl");
                        *((_QWORD *)this + 10) = v14;
                        if ( v14 )
                        {
                          v15 = GetProcAddress(v5, "MpDlpDelegateEnforcement");
                          *((_QWORD *)this + 11) = v15;
                          if ( v15 )
                          {
                            v16 = GetProcAddress(v5, "MpGetDevMode");
                            *((_QWORD *)this + 12) = v16;
                            if ( v16 )
                            {
                              v17 = GetProcAddress(v5, "MpDlpInitializeEnforcementMode");
                              *((_QWORD *)this + 13) = v17;
                              if ( v17 )
                              {
                                v18 = GetProcAddress(v5, "MpDlpNotifyPreSaveAsDocument");
                                *((_QWORD *)this + 14) = v18;
                                if ( v18 )
                                {
                                  v19 = GetProcAddress(v5, "MpDlpNotifyPostSaveAsDocument");
                                  *((_QWORD *)this + 15) = v19;
                                  if ( v19 )
                                  {
                                    v20 = GetProcAddress(v5, "MpDlpNotifyPrePrint");
                                    *((_QWORD *)this + 16) = v20;
                                    if ( v20 )
                                    {
                                      v21 = GetProcAddress(v5, "MpDlpNotifyPostStartPrint");
                                      *((_QWORD *)this + 17) = v21;
                                      if ( v21 )
                                      {
                                        v22 = GetProcAddress(v5, "MpDlpNotifyPreOpenDocumentFile");
                                        *((_QWORD *)this + 18) = v22;
                                        if ( v22 )
                                        {
                                          v23 = GetProcAddress(v5, "MpDlpNotifyPostOpenDocumentFile");
                                          *((_QWORD *)this + 19) = v23;
                                          if ( v23 )
                                          {
                                            v24 = GetProcAddress(v5, "MpDlpNotifyCloseDocumentFile");
                                            *((_QWORD *)this + 20) = v24;
                                            if ( v24 )
                                            {
                                              v25 = GetProcAddress(v5, "MpDlpGetPrinterInformation");
                                              *((_QWORD *)this + 21) = v25;
                                              if ( v25 )
                                              {
                                                v26 = GetProcAddress(v5, "MpDlpGetUsbInformation");
                                                *((_QWORD *)this + 22) = v26;
                                                if ( v26 )
                                                {
                                                  v27 = GetProcAddress(v5, "MpDlpGetDeviceInformation");
                                                  *((_QWORD *)this + 23) = v27;
                                                  if ( v27 )
                                                  {
                                                    v28 = GetProcAddress(v5, "MpDlpGenerateRmsLabelingEvent");
                                                    *((_QWORD *)this + 24) = v28;
                                                    if ( v28 )
                                                    {
                                                      v29 = GetProcAddress(v5, "MpDlpFindSubstitute");
                                                      *((_QWORD *)this + 7) = v29;
                                                      if ( v29 )
                                                      {
                                                        v30 = GetProcAddress(v5, "MpDlpTrustContainerLabelRequest");
                                                        *((_QWORD *)this + 25) = v30;
                                                        if ( v30 )
                                                        {
                                                          v31 = GetProcAddress(v5, "MpDlpRecallQueryInfo");
                                                          *((_QWORD *)this + 26) = v31;
                                                          if ( v31 )
                                                          {
                                                            v43 = *(const wchar_t **)this;
                                                            *(_QWORD *)this = 0;
                                                            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(
                                                              this,
                                                              &v42);
                                                            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(
                                                              &v42,
                                                              &v43);
                                                            CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(&v43);
                                                            CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(&v42);
                                                            std::optional<std::wstring>::~optional<std::wstring>(lpLibFileName);
                                                            return 1;
                                                          }
                                                        }
                                                      }
                                                    }
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
      CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(&v42);
      std::optional<std::wstring>::~optional<std::wstring>(lpLibFileName);
      result = 0;
    }
    else
    {
      std::optional<std::wstring>::~optional<std::wstring>(lpLibFileName);
      result = 0;
    }
  }
  catch ( const wil::ResultException *v45 )
  {
    v32 = EndpointDlp::TraceLoggingProvider::Instance();
    v35 = *(_DWORD **)v32;
    if ( **(_DWORD **)v32 > 2u )
    {
      v43 = L"Failed to load mpclient.dll";
      LODWORD(v42) = *((_DWORD *)v45 + 8);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        (_DWORD)v35,
        (unsigned int)byte_1802BD81B,
        v33,
        v34,
        (__int64)&v42,
        (__int64)&v43);
    }
    return 0;
  }
  catch ( const std::exception *v46 )
  {
    v36 = EndpointDlp::TraceLoggingProvider::Instance();
    v37 = *(_DWORD **)v36;
    if ( **(_DWORD **)v36 > 2u )
    {
      v43 = (const wchar_t *)(*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v46 + 8LL))(v46);
      v44 = L"Failed to load mpclient.dll, std threw an exception";
      LODWORD(v42) = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
        (int)v37,
        (int)&byte_1802BD84B,
        (__int64)&v42,
        (__int64)&v44,
        (__int64)&v43);
    }
    return 0;
  }
  catch ( ... )
  {
    v38 = EndpointDlp::TraceLoggingProvider::Instance();
    v41 = *(_DWORD **)v38;
    if ( **(_DWORD **)v38 > 2u )
    {
      v44 = L"Failed to load mpclient.dll, unknown exception was thrown";
      LODWORD(v42) = -2147418113;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        (_DWORD)v41,
        (unsigned int)byte_1802BD889,
        v39,
        v40,
        (__int64)&v42,
        (__int64)&v44);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800ba9ec  mov     [rsp+arg_8], rbx
0x1800ba9f1  push    rdi
0x1800ba9f2  sub     rsp, 0A0h
0x1800ba9f9  mov     rax, cs:__security_cookie
0x1800baa00  xor     rax, rsp
0x1800baa03  mov     [rsp+0A8h+var_18], rax
0x1800baa0b  mov     rdi, rcx
0x1800baa0e  cmp     qword ptr [rcx], 0
0x1800baa12  jz      short loc_1800BAA1B
0x1800baa14  mov     al, 1
0x1800baa16  jmp     loc_1800BB038
0x1800baa1b  lea     rcx, [rsp+0A8h+lpLibFileName]
0x1800baa20  call    EndpointDlp__MpClient___anonymous_namespace___GetMpClientPath
0x1800baa25  lea     rcx, [rsp+0A8h+lpLibFileName]
0x1800baa2a  cmp     [rsp+0A8h+var_20], 0
0x1800baa32  jnz     short loc_1800BAA40
0x1800baa34  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1800baa39  xor     al, al
0x1800baa3b  jmp     loc_1800BB038
0x1800baa40  cmp     [rsp+0A8h+var_28], 7
0x1800baa49  cmova   rcx, [rsp+0A8h+lpLibFileName]; lpLibFileName
0x1800baa4f  call    cs:__imp_LoadLibraryW
0x1800baa55  mov     rbx, rax
0x1800baa58  mov     [rsp+0A8h+var_68], rax
0x1800baa5d  test    rax, rax
0x1800baa60  jnz     short loc_1800BAA7D
0x1800baa62  lea     rcx, [rsp+0A8h+var_68]
0x1800baa67  call    ??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)
0x1800baa6c  lea     rcx, [rsp+0A8h+lpLibFileName]
0x1800baa71  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1800baa76  xor     al, al
0x1800baa78  jmp     loc_1800BB038
0x1800baa7d  lea     rdx, aMpmanageropen; "MpManagerOpen"
0x1800baa84  mov     rcx, rbx; hModule
0x1800baa87  call    cs:__imp_GetProcAddress
0x1800baa8d  mov     [rdi+8], rax
0x1800baa91  test    rax, rax
0x1800baa94  jnz     short loc_1800BAAB1
0x1800baa96  lea     rcx, [rsp+0A8h+var_68]
0x1800baa9b  call    ??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)
0x1800baaa0  lea     rcx, [rsp+0A8h+lpLibFileName]
0x1800baaa5  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1800baaaa  xor     al, al
0x1800baaac  jmp     loc_1800BB038
0x1800baab1  lea     rdx, aMphandleclose; "MpHandleClose"
0x1800baab8  mov     rcx, rbx; hModule
0x1800baabb  call    cs:__imp_GetProcAddress
0x1800baac1  mov     [rdi+10h], rax
0x1800baac5  test    rax, rax
0x1800baac8  jnz     short loc_1800BAAE5
0x1800baaca  lea     rcx, [rsp+0A8h+var_68]
0x1800baacf  call    ??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)
0x1800baad4  lea     rcx, [rsp+0A8h+lpLibFileName]
0x1800baad9  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1800baade  xor     al, al
0x1800baae0  jmp     loc_1800BB038
0x1800baae5  lea     rdx, aMpdlpcheckacce; "MpDlpCheckAccessForBuffer"
0x1800baaec  mov     rcx, rbx; hModule
0x1800baaef  call    cs:__imp_GetProcAddress
0x1800baaf5  mov     [rdi+18h], rax
0x1800baaf9  test    rax, rax
0x1800baafc  jnz     short loc_1800BAB19
0x1800baafe  lea     rcx, [rsp+0A8h+var_68]
0x1800bab03  call    ??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)
0x1800bab08  lea     rcx, [rsp+0A8h+lpLibFileName]
0x1800bab0d  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1800bab12  xor     al, al
0x1800bab14  jmp     loc_1800BB038
0x1800bab19  lea     rdx, aMpfreememory; "MpFreeMemory"
0x1800bab20  mov     rcx, rbx; hModule
0x1800bab23  call    cs:__imp_GetProcAddress
0x1800bab29  mov     [rdi+20h], rax
0x1800bab2d  test    rax, rax
0x1800bab30  jnz     short loc_1800BAB4D
0x1800bab32  lea     rcx, [rsp+0A8h+var_68]
0x1800bab37  call    ??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)
0x1800bab3c  lea     rcx, [rsp+0A8h+lpLibFileName]
0x1800bab41  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1800bab46  xor     al, al
0x1800bab48  jmp     loc_1800BB038
0x1800bab4d  lea     rdx, aMpdlpdispatcha; "MpDlpDispatchAccessEvent"
0x1800bab54  mov     rcx, rbx; hModule
0x1800bab57  call    cs:__imp_GetProcAddress
0x1800bab5d  mov     [rdi+28h], rax
0x1800bab61  test    rax, rax
0x1800bab64  jnz     short loc_1800BAB81
0x1800bab66  lea     rcx, [rsp+0A8h+var_68]
0x1800bab6b  call    ??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)
0x1800bab70  lea     rcx, [rsp+0A8h+lpLibFileName]
0x1800bab75  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1800bab7a  xor     al, al
0x1800bab7c  jmp     loc_1800BB038
0x1800bab81  lea     rdx, aMpdlpscanllm; "MpDlpScanLLM"
0x1800bab88  mov     rcx, rbx; hModule
0x1800bab8b  call    cs:__imp_GetProcAddress
0x1800bab91  mov     [rdi+30h], rax
0x1800bab95  test    rax, rax
0x1800bab98  jnz     short loc_1800BABB5
0x1800bab9a  lea     rcx, [rsp+0A8h+var_68]
0x1800bab9f  call    ??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)
0x1800baba4  lea     rcx, [rsp+0A8h+lpLibFileName]
0x1800baba9  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1800babae  xor     al, al
0x1800babb0  jmp     loc_1800BB038
0x1800babb5  lea     rdx, aMpgetfcvalue; "MpGetFCValue"
0x1800babbc  mov     rcx, rbx; hModule
0x1800babbf  call    cs:__imp_GetProcAddress
0x1800babc5  mov     [rdi+40h], rax
0x1800babc9  test    rax, rax
0x1800babcc  jnz     short loc_1800BABE9
0x1800babce  lea     rcx, [rsp+0A8h+var_68]
0x1800babd3  call    ??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)
0x1800babd8  lea     rcx, [rsp+0A8h+lpLibFileName]
0x1800babdd  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1800babe2  xor     al, al
0x1800babe4  jmp     loc_1800BB038
0x1800babe9  lea     rdx, aMpnotification; "MpNotificationRegister"
0x1800babf0  mov     rcx, rbx; hModule
0x1800babf3  call    cs:__imp_GetProcAddress
0x1800babf9  mov     [rdi+48h], rax
0x1800babfd  test    rax, rax
0x1800bac00  jnz     short loc_1800BAC1D
0x1800bac02  lea     rcx, [rsp+0A8h+var_68]
0x1800bac07  call    ??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)
0x1800bac0c  lea     rcx, [rsp+0A8h+lpLibFileName]
0x1800bac11  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1800bac16  xor     al, al
0x1800bac18  jmp     loc_1800BB038
0x1800bac1d  lea     rdx, aMpdlpgeteviden; "MpDlpGetEvidenceFileUrl"
0x1800bac24  mov     rcx, rbx; hModule
0x1800bac27  call    cs:__imp_GetProcAddress
0x1800bac2d  mov     [rdi+50h], rax
0x1800bac31  test    rax, rax
0x1800bac34  jnz     short loc_1800BAC51
0x1800bac36  lea     rcx, [rsp+0A8h+var_68]
0x1800bac3b  call    ??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)
0x1800bac40  lea     rcx, [rsp+0A8h+lpLibFileName]
0x1800bac45  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1800bac4a  xor     al, al
0x1800bac4c  jmp     loc_1800BB038
0x1800bac51  lea     rdx, aMpdlpdelegatee; "MpDlpDelegateEnforcement"
0x1800bac58  mov     rcx, rbx; hModule
0x1800bac5b  call    cs:__imp_GetProcAddress
0x1800bac61  mov     [rdi+58h], rax
0x1800bac65  test    rax, rax
0x1800bac68  jnz     short loc_1800BAC85
0x1800bac6a  lea     rcx, [rsp+0A8h+var_68]
0x1800bac6f  call    ??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)
0x1800bac74  lea     rcx, [rsp+0A8h+lpLibFileName]
0x1800bac79  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1800bac7e  xor     al, al
0x1800bac80  jmp     loc_1800BB038
0x1800bac85  lea     rdx, aMpgetdevmode; "MpGetDevMode"
0x1800bac8c  mov     rcx, rbx; hModule
0x1800bac8f  call    cs:__imp_GetProcAddress
0x1800bac95  mov     [rdi+60h], rax
0x1800bac99  test    rax, rax
0x1800bac9c  jnz     short loc_1800BACB9
0x1800bac9e  lea     rcx, [rsp+0A8h+var_68]
0x1800baca3  call    ??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)
0x1800baca8  lea     rcx, [rsp+0A8h+lpLibFileName]
0x1800bacad  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1800bacb2  xor     al, al
0x1800bacb4  jmp     loc_1800BB038
0x1800bacb9  lea     rdx, aMpdlpinitializ; "MpDlpInitializeEnforcementMode"
0x1800bacc0  mov     rcx, rbx; hModule
0x1800bacc3  call    cs:__imp_GetProcAddress
0x1800bacc9  mov     [rdi+68h], rax
0x1800baccd  test    rax, rax
0x1800bacd0  jnz     short loc_1800BACED
0x1800bacd2  lea     rcx, [rsp+0A8h+var_68]
0x1800bacd7  call    ??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)
0x1800bacdc  lea     rcx, [rsp+0A8h+lpLibFileName]
0x1800bace1  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1800bace6  xor     al, al
0x1800bace8  jmp     loc_1800BB038
0x1800baced  lea     rdx, aMpdlpnotifypre; "MpDlpNotifyPreSaveAsDocument"
0x1800bacf4  mov     rcx, rbx; hModule
0x1800bacf7  call    cs:__imp_GetProcAddress
0x1800bacfd  mov     [rdi+70h], rax
0x1800bad01  test    rax, rax
0x1800bad04  jnz     short loc_1800BAD21
0x1800bad06  lea     rcx, [rsp+0A8h+var_68]
0x1800bad0b  call    ??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)
0x1800bad10  lea     rcx, [rsp+0A8h+lpLibFileName]
0x1800bad15  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1800bad1a  xor     al, al
0x1800bad1c  jmp     loc_1800BB038
0x1800bad21  lea     rdx, aMpdlpnotifypos_0; "MpDlpNotifyPostSaveAsDocument"
0x1800bad28  mov     rcx, rbx; hModule
0x1800bad2b  call    cs:__imp_GetProcAddress
0x1800bad31  mov     [rdi+78h], rax
0x1800bad35  test    rax, rax
0x1800bad38  jnz     short loc_1800BAD55
0x1800bad3a  lea     rcx, [rsp+0A8h+var_68]
0x1800bad3f  call    ??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)
0x1800bad44  lea     rcx, [rsp+0A8h+lpLibFileName]
0x1800bad49  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1800bad4e  xor     al, al
0x1800bad50  jmp     loc_1800BB038
0x1800bad55  lea     rdx, aMpdlpnotifypre_0; "MpDlpNotifyPrePrint"
0x1800bad5c  mov     rcx, rbx; hModule
0x1800bad5f  call    cs:__imp_GetProcAddress
0x1800bad65  mov     [rdi+80h], rax
0x1800bad6c  test    rax, rax
0x1800bad6f  jnz     short loc_1800BAD8C
0x1800bad71  lea     rcx, [rsp+0A8h+var_68]
0x1800bad76  call    ??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)
0x1800bad7b  lea     rcx, [rsp+0A8h+lpLibFileName]
0x1800bad80  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1800bad85  xor     al, al
0x1800bad87  jmp     loc_1800BB038
0x1800bad8c  lea     rdx, aMpdlpnotifypos_1; "MpDlpNotifyPostStartPrint"
0x1800bad93  mov     rcx, rbx; hModule
0x1800bad96  call    cs:__imp_GetProcAddress
0x1800bad9c  mov     [rdi+88h], rax
0x1800bada3  test    rax, rax
0x1800bada6  jnz     short loc_1800BADC3
0x1800bada8  lea     rcx, [rsp+0A8h+var_68]
0x1800badad  call    ??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)
0x1800badb2  lea     rcx, [rsp+0A8h+lpLibFileName]
0x1800badb7  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1800badbc  xor     al, al
0x1800badbe  jmp     loc_1800BB038
0x1800badc3  lea     rdx, aMpdlpnotifypre_1; "MpDlpNotifyPreOpenDocumentFile"
0x1800badca  mov     rcx, rbx; hModule
0x1800badcd  call    cs:__imp_GetProcAddress
0x1800badd3  mov     [rdi+90h], rax
0x1800badda  test    rax, rax
0x1800baddd  jnz     short loc_1800BADFA
0x1800baddf  lea     rcx, [rsp+0A8h+var_68]
0x1800bade4  call    ??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)
0x1800bade9  lea     rcx, [rsp+0A8h+lpLibFileName]
0x1800badee  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1800badf3  xor     al, al
0x1800badf5  jmp     loc_1800BB038
0x1800badfa  lea     rdx, aMpdlpnotifypos; "MpDlpNotifyPostOpenDocumentFile"
0x1800bae01  mov     rcx, rbx; hModule
0x1800bae04  call    cs:__imp_GetProcAddress
0x1800bae0a  mov     [rdi+98h], rax
0x1800bae11  test    rax, rax
0x1800bae14  jnz     short loc_1800BAE31
0x1800bae16  lea     rcx, [rsp+0A8h+var_68]
0x1800bae1b  call    ??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)
0x1800bae20  lea     rcx, [rsp+0A8h+lpLibFileName]
0x1800bae25  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1800bae2a  xor     al, al
0x1800bae2c  jmp     loc_1800BB038
0x1800bae31  lea     rdx, aMpdlpnotifyclo; "MpDlpNotifyCloseDocumentFile"
0x1800bae38  mov     rcx, rbx; hModule
0x1800bae3b  call    cs:__imp_GetProcAddress
0x1800bae41  mov     [rdi+0A0h], rax
0x1800bae48  test    rax, rax
0x1800bae4b  jnz     short loc_1800BAE68
0x1800bae4d  lea     rcx, [rsp+0A8h+var_68]
0x1800bae52  call    ??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)
0x1800bae57  lea     rcx, [rsp+0A8h+lpLibFileName]
0x1800bae5c  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1800bae61  xor     al, al
0x1800bae63  jmp     loc_1800BB038
0x1800bae68  lea     rdx, aMpdlpgetprinte; "MpDlpGetPrinterInformation"
0x1800bae6f  mov     rcx, rbx; hModule
0x1800bae72  call    cs:__imp_GetProcAddress
0x1800bae78  mov     [rdi+0A8h], rax
0x1800bae7f  test    rax, rax
0x1800bae82  jnz     short loc_1800BAE9F
0x1800bae84  lea     rcx, [rsp+0A8h+var_68]
0x1800bae89  call    ??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)
0x1800bae8e  lea     rcx, [rsp+0A8h+lpLibFileName]
0x1800bae93  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1800bae98  xor     al, al
0x1800bae9a  jmp     loc_1800BB038
0x1800bae9f  lea     rdx, aMpdlpgetusbinf; "MpDlpGetUsbInformation"
0x1800baea6  mov     rcx, rbx; hModule
0x1800baea9  call    cs:__imp_GetProcAddress
0x1800baeaf  mov     [rdi+0B0h], rax
0x1800baeb6  test    rax, rax
0x1800baeb9  jnz     short loc_1800BAED6
0x1800baebb  lea     rcx, [rsp+0A8h+var_68]
0x1800baec0  call    ??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)
0x1800baec5  lea     rcx, [rsp+0A8h+lpLibFileName]
0x1800baeca  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1800baecf  xor     al, al
0x1800baed1  jmp     loc_1800BB038
0x1800baed6  lea     rdx, aMpdlpgetdevice; "MpDlpGetDeviceInformation"
0x1800baedd  mov     rcx, rbx; hModule
0x1800baee0  call    cs:__imp_GetProcAddress
0x1800baee6  mov     [rdi+0B8h], rax
0x1800baeed  test    rax, rax
0x1800baef0  jnz     short loc_1800BAF0D
0x1800baef2  lea     rcx, [rsp+0A8h+var_68]
0x1800baef7  call    ??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)
0x1800baefc  lea     rcx, [rsp+0A8h+lpLibFileName]
0x1800baf01  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1800baf06  xor     al, al
0x1800baf08  jmp     loc_1800BB038
0x1800baf0d  lea     rdx, aMpdlpgenerater; "MpDlpGenerateRmsLabelingEvent"
0x1800baf14  mov     rcx, rbx; hModule
0x1800baf17  call    cs:__imp_GetProcAddress
0x1800baf1d  mov     [rdi+0C0h], rax
  ... truncated ...
```
