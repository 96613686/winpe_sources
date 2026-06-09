# UserHitBlackscreenKey(_GUID,ulong)

- ea: `0x180080d9c`
- end: `0x18008169b`
- name: `?UserHitBlackscreenKey@@YAJU_GUID@@K@Z`
- size: `2303`
- prototype: `__int64 __fastcall(IID *rclsid, unsigned int)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180080550`

## callees

- `0x180001408`
- `0x180001b90`
- `0x180002ea4`
- `0x180009580`
- `0x18000c684`
- `0x18000f320`
- `0x18002701c`
- `0x180048788`
- `0x180048bb0`
- `0x180049204`
- `0x180049228`
- `0x18004e850`
- `0x18004f354`
- `0x180056758`
- `0x1800804c4`
- `0x1800806ac`
- `0x18008084c`
- `0x180080880`
- `0x180080ad8`
- `0x180080c1c`
- `0x180080d00`
- `0x180080d5c`
- `0x180080d9c`
- `0x180081788`
- `0x1800817f4`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180081076`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800810cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180081076`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800810cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800813c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800813c5`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180080e63`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800813e8`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180080e63`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800813e8`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCreate` at `0x180080fc8`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCreate` at `0x180080fc8`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCloseHandle` at `0x180080f98`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCloseHandle` at `0x180080f98`

## string_xrefs

- `0x180080ff5`: `Failed to create report`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall UserHitBlackscreenKey(IID *rclsid, unsigned int a2, int a3, int a4)
{
  HRESULT InstanceOfSessionManagerInternal; // ebx
  int v7; // r8d
  int v8; // r9d
  const unsigned __int16 *v9; // rcx
  const char *v10; // rax
  char *v11; // rdx
  HREPORT v12; // rbx
  DWORD ServicePid; // edi
  __int64 v14; // rax
  __int64 v15; // rax
  DWORD CurrentProcessId; // eax
  __int64 v17; // rax
  HREPORT v18; // rbx
  DWORD v19; // eax
  int v20; // edi
  int v21; // esi
  int v22; // r14d
  int v23; // ebx
  int v24; // eax
  LPOLESTR v25; // rbx
  const unsigned __int16 *v26; // r8
  const unsigned __int16 *v27; // r8
  const unsigned __int16 *v28; // r8
  const unsigned __int16 *v29; // r8
  HRESULT v31; // [rsp+40h] [rbp-C0h] BYREF
  const char *v32; // [rsp+48h] [rbp-B8h] BYREF
  const char *v33; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwProcessId[2]; // [rsp+58h] [rbp-A8h] BYREF
  HREPORT hReportHandle; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+68h] [rbp-98h] BYREF
  const char *v37; // [rsp+70h] [rbp-90h] BYREF
  LPOLESTR lpsz; // [rsp+78h] [rbp-88h] BYREF
  __int64 v39; // [rsp+80h] [rbp-80h] BYREF
  struct ISessionManagerInternal *v40; // [rsp+88h] [rbp-78h] BYREF
  const char *v41; // [rsp+90h] [rbp-70h] BYREF
  __int64 v42; // [rsp+98h] [rbp-68h] BYREF
  __int64 v43; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v44; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v45[2]; // [rsp+B0h] [rbp-50h] BYREF
  _WER_REPORT_INFORMATION pReportInformation; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v47[2]; // [rsp+960h] [rbp+860h] BYREF
  unsigned __int16 *v48[4]; // [rsp+980h] [rbp+880h] BYREF
  __int128 v49; // [rsp+9A0h] [rbp+8A0h] BYREF

  if ( (unsigned int)dword_1800DF020 > 5 )
  {
    v31 = a2;
    v40 = (struct ISessionManagerInternal *)rclsid;
    v32 = "Got blackscreen hotkey";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      (_DWORD)rclsid,
      (unsigned int)byte_1800CCB25,
      a3,
      a4,
      (__int64)&v32,
      (__int64)&v40,
      (__int64)&v31);
  }
  v39 = 0;
  v43 = 0;
  v40 = 0;
  v44 = 0;
  v42 = 0;
  memset_0(&pReportInformation, 0, sizeof(pReportInformation));
  std::wstring::wstring(v48);
  hReportHandle = 0;
  lpsz = 0;
  InstanceOfSessionManagerInternal = StringFromCLSID(rclsid, &lpsz);
  if ( InstanceOfSessionManagerInternal < 0 )
  {
    LODWORD(v9) = dword_1800DF020;
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_77;
    v32 = "UserHitBlackscreenKey";
    v10 = "Failed to convert guid to string";
    v11 = (char *)&unk_1800CCAE0;
LABEL_6:
    v33 = v10;
    *(_QWORD *)dwProcessId = "Warning HResult failed";
    v31 = InstanceOfSessionManagerInternal;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (_DWORD)v9,
      (_DWORD)v11,
      v7,
      v8,
      (__int64)dwProcessId,
      (__int64)&v33,
      (__int64)&v31,
      (__int64)&v32);
    goto LABEL_77;
  }
  pReportInformation.hProcess = 0;
  pReportInformation.dwSize = 2208;
  InstanceOfSessionManagerInternal = StringCchCopyW(
                                       pReportInformation.wzFriendlyEventName,
                                       0x80u,
                                       L"Black Screen - User Reported");
  if ( InstanceOfSessionManagerInternal < 0 )
  {
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_77;
    v32 = "UserHitBlackscreenKey";
    v10 = "Failed to set event name";
    v11 = byte_1800CCA9B;
    goto LABEL_6;
  }
  InstanceOfSessionManagerInternal = StringCchCopyW(
                                       pReportInformation.wzDescription,
                                       0x200u,
                                       L"The user has invoked the Black Screen Diagnostics Tool to generate this report ab"
                                        "out LSM and Termsrv");
  if ( InstanceOfSessionManagerInternal < 0 )
  {
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_77;
    v32 = "UserHitBlackscreenKey";
    v10 = "Failed to set event description";
    v11 = (char *)&word_1800CCA56;
    goto LABEL_6;
  }
  v12 = hReportHandle;
  if ( hReportHandle )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v32);
    WerReportCloseHandle(v12);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v32);
  }
  hReportHandle = 0;
  InstanceOfSessionManagerInternal = WerReportCreate(
                                       L"WindowsBlackScreenDiagnosticsV1",
                                       WerReportCritical,
                                       &pReportInformation,
                                       &hReportHandle);
  if ( InstanceOfSessionManagerInternal < 0 )
  {
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_77;
    v32 = "UserHitBlackscreenKey";
    v10 = "Failed to create report";
    v11 = byte_1800CCA11;
    goto LABEL_6;
  }
  ServicePid = GetServicePid(v9);
  v14 = std::to_wstring(v47, a2);
  if ( *(_QWORD *)(v14 + 24) > 7u )
    v14 = *(_QWORD *)v14;
  AddCustomMetadata(L"SourceSessionId", (const unsigned __int16 *)v14);
  std::wstring::_Tidy_deallocate(v47);
  v15 = std::to_wstring(v47, ServicePid);
  if ( *(_QWORD *)(v15 + 24) > 7u )
    v15 = *(_QWORD *)v15;
  AddCustomMetadata(L"TermsrvPID", (const unsigned __int16 *)v15);
  std::wstring::_Tidy_deallocate(v47);
  CurrentProcessId = GetCurrentProcessId();
  v17 = std::to_wstring(v47, CurrentProcessId);
  if ( *(_QWORD *)(v17 + 24) > 7u )
    v17 = *(_QWORD *)v17;
  AddCustomMetadata(L"LsmPID", (const unsigned __int16 *)v17);
  std::wstring::_Tidy_deallocate(v47);
  AddCustomMetadata(L"BlackScreenInstanceGuid", lpsz);
  v18 = hReportHandle;
  v19 = GetCurrentProcessId();
  InstanceOfSessionManagerInternal = AddBlackscreenDump(v19, v18, 0);
  if ( InstanceOfSessionManagerInternal < 0 )
  {
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_77;
    v32 = "UserHitBlackscreenKey";
    v10 = "Failed to get LSM dump";
    v11 = (char *)&dword_1800CC9CC;
    goto LABEL_6;
  }
  if ( ServicePid )
  {
    InstanceOfSessionManagerInternal = AddBlackscreenDump(ServicePid, hReportHandle, 1);
    if ( InstanceOfSessionManagerInternal < 0 )
    {
      if ( (unsigned int)dword_1800DF020 <= 3 )
        goto LABEL_77;
      v32 = "UserHitBlackscreenKey";
      v10 = "Failed to get termsrv dump";
      v11 = &byte_1800CC987;
      goto LABEL_6;
    }
  }
  else if ( (unsigned int)dword_1800DF020 > 3 )
  {
    v32 = "Not including termsrv dump because we couldn't determine the PID";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (_DWORD)v9,
      (unsigned int)&dword_1800CC95C,
      v7,
      v8,
      (__int64)&v32);
  }
  InstanceOfSessionManagerInternal = ISessionManagerInternal::GetInstanceOfSessionManagerInternal(&v40);
  if ( InstanceOfSessionManagerInternal < 0 )
  {
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_77;
    v32 = "UserHitBlackscreenKey";
    v10 = "Failed to get session manager";
    v11 = &byte_1800CC917;
    goto LABEL_6;
  }
  InstanceOfSessionManagerInternal = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *, __int64 *))(*(_QWORD *)v40 + 24LL))(
                                       v40,
                                       &v44);
  if ( InstanceOfSessionManagerInternal < 0 )
  {
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_77;
    v32 = "UserHitBlackscreenKey";
    v10 = "Failed to get session list";
    v11 = (char *)word_1800CC8D2;
    goto LABEL_6;
  }
  InstanceOfSessionManagerInternal = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 32LL))(v44, &v42);
  if ( InstanceOfSessionManagerInternal < 0 )
  {
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_77;
    v32 = "UserHitBlackscreenKey";
    v10 = "Failed to get session enum";
    v11 = byte_1800CC88D;
    goto LABEL_6;
  }
  InstanceOfSessionManagerInternal = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v42 + 80LL))(v42, &v39);
  if ( InstanceOfSessionManagerInternal < 0 )
  {
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_77;
    v32 = "UserHitBlackscreenKey";
    v10 = "Failed to get any sessions";
    v11 = (char *)&unk_1800CC848;
    goto LABEL_6;
  }
  v20 = 0;
  v21 = 0;
  v22 = 0;
  while ( 1 )
  {
    if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 104LL))(v39, &v43) >= 0 )
    {
      LODWORD(v33) = 0;
      v36 = 0;
      v47[0] = 0;
      v49 = 0;
      (*(void (__fastcall **)(__int64, _OWORD *, const char **, int *, __int128 *))(*(_QWORD *)v43 + 136LL))(
        v43,
        v47,
        &v33,
        &v36,
        &v49);
      if ( v36 == 1 )
      {
        ++v21;
      }
      else if ( v36 == 9 )
      {
        ++v22;
      }
      dwProcessId[0] = 0;
      v23 = (*(__int64 (__fastcall **)(__int64, DWORD *))(*(_QWORD *)v43 + 224LL))(v43, dwProcessId);
      v31 = 0;
      v24 = (*(__int64 (__fastcall **)(__int64, HRESULT *))(*(_QWORD *)v39 + 80LL))(v39, &v31);
      if ( v23 >= 0 && v24 >= 0 )
      {
        if ( dwProcessId[0] )
        {
          if ( v31 == a2 )
          {
            InstanceOfSessionManagerInternal = AddBlackscreenDump(dwProcessId[0], hReportHandle, 1);
            if ( InstanceOfSessionManagerInternal < 0 )
              break;
          }
        }
      }
    }
    ++v20;
    if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v42 + 80LL))(v42, &v39) < 0 )
    {
      v25 = lpsz;
      if ( lpsz )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v37);
        CoTaskMemFree(v25);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v37);
      }
      lpsz = 0;
      InstanceOfSessionManagerInternal = StringFromCLSID(rclsid, &lpsz);
      if ( InstanceOfSessionManagerInternal >= 0 )
      {
        SetReportParameter(hReportHandle, 0, L"RDP");
        if ( v20 < 10 )
        {
          v26 = L"Low";
        }
        else if ( v20 > 50 )
        {
          v26 = L"High";
        }
        else
        {
          v26 = L"Medium";
        }
        SetReportParameter(hReportHandle, 1u, v26);
        v27 = L"FALSE";
        if ( v21 )
          v27 = L"TRUE";
        SetReportParameter(hReportHandle, 2u, v27);
        v28 = L"FALSE";
        if ( v22 )
          v28 = L"TRUE";
        SetReportParameter(hReportHandle, 3u, v28);
        GetCurrentProcessVersionInfo(v48);
        v29 = (const unsigned __int16 *)v48;
        if ( v48[3] > (unsigned __int16 *)7 )
          v29 = v48[0];
        SetReportParameter(hReportHandle, 4u, v29);
        QueueReportForSubmission(hReportHandle);
        RemoveCustomMetadata(L"BlackScreenInstanceGuid");
        RemoveCustomMetadata(L"SourceSessionId");
        RemoveCustomMetadata(L"TermsrvPID");
        RemoveCustomMetadata(L"LsmPID");
        RemoveCustomMetadata(L"BlackScreenInstanceGuid");
      }
      else if ( (unsigned int)dword_1800DF020 > 3 )
      {
        v37 = "UserHitBlackscreenKey";
        LODWORD(v32) = InstanceOfSessionManagerInternal;
        v41 = "Failed to convert blackscreen guid to string";
        v45[0] = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)v9,
          (unsigned int)&word_1800CC7BE,
          v7,
          v8,
          (__int64)v45,
          (__int64)&v41,
          (__int64)&v32,
          (__int64)&v37);
      }
      goto LABEL_77;
    }
  }
  if ( (unsigned int)dword_1800DF020 > 3 )
  {
    v45[0] = "UserHitBlackscreenKey";
    LODWORD(v32) = InstanceOfSessionManagerInternal;
    v41 = "Failed to get WUDFHostPid dump";
    v37 = "Warning HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (_DWORD)v9,
      (unsigned int)byte_1800CC803,
      v7,
      v8,
      (__int64)&v37,
      (__int64)&v41,
      (__int64)&v32,
      (__int64)v45);
  }
LABEL_77:
  if ( (unsigned int)dword_1800DF020 > 5 )
  {
    LODWORD(v32) = InstanceOfSessionManagerInternal;
    LODWORD(v33) = a2;
    v37 = (const char *)rclsid;
    v41 = "Finished blackscreen hotkey";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v9,
      (unsigned int)&byte_1800CC76F,
      v7,
      v8,
      (__int64)&v41,
      (__int64)&v37,
      (__int64)&v33,
      (__int64)&v32);
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hReportHandle);
  std::wstring::_Tidy_deallocate(v48);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v42);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v44);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v40);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v43);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v39);
  return (unsigned int)InstanceOfSessionManagerInternal;
}

```

## disassembly

```asm
0x180080d9c  mov     [rsp-8+arg_10], rbx
0x180080da1  push    rbp
0x180080da2  push    rsi
0x180080da3  push    rdi
0x180080da4  push    r12
0x180080da6  push    r13
0x180080da8  push    r14
0x180080daa  push    r15
0x180080dac  lea     rbp, [rsp-8C0h]
0x180080db4  sub     rsp, 9C0h
0x180080dbb  mov     rax, cs:__security_cookie
0x180080dc2  xor     rax, rsp
0x180080dc5  mov     [rbp+8F0h+var_40], rax
0x180080dcc  mov     r15d, edx
0x180080dcf  mov     r12, rcx
0x180080dd2  mov     eax, cs:dword_1800DF020
0x180080dd8  cmp     eax, 5
0x180080ddb  jbe     short loc_180080E1A
0x180080ddd  mov     [rsp+9F0h+var_9B0], edx
0x180080de1  mov     [rbp+8F0h+var_968], rcx
0x180080de5  lea     rax, aGotBlackscreen; "Got blackscreen hotkey"
0x180080dec  mov     [rsp+9F0h+var_9A8], rax
0x180080df1  lea     rax, [rsp+9F0h+var_9B0]
0x180080df6  mov     [rsp+9F0h+var_9C0], rax
0x180080dfb  lea     rax, [rbp+8F0h+var_968]
0x180080dff  mov     [rsp+9F0h+var_9C8], rax
0x180080e04  lea     rax, [rsp+9F0h+var_9A8]
0x180080e09  mov     [rsp+9F0h+var_9D0], rax
0x180080e0e  lea     rdx, byte_1800CCB25
0x180080e15  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x180080e1a  xor     r13d, r13d
0x180080e1d  mov     [rbp+8F0h+var_970], r13
0x180080e21  mov     [rbp+8F0h+var_950], r13
0x180080e25  mov     [rbp+8F0h+var_968], r13
0x180080e29  mov     [rbp+8F0h+var_948], r13
0x180080e2d  mov     [rbp+8F0h+var_958], r13
0x180080e31  mov     edi, 8A0h
0x180080e36  mov     r8d, edi; Size
0x180080e39  xor     edx, edx; Val
0x180080e3b  lea     rcx, [rbp+8F0h+pReportInformation]; void *
0x180080e3f  call    memset_0
0x180080e44  lea     rcx, [rbp+8F0h+var_70]
0x180080e4b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180080e50  nop
0x180080e51  mov     [rsp+9F0h+hReportHandle], r13
0x180080e56  mov     [rsp+9F0h+lpsz], r13
0x180080e5b  lea     rdx, [rsp+9F0h+lpsz]; lplpsz
0x180080e60  mov     rcx, r12; rclsid
0x180080e63  call    cs:__imp_StringFromCLSID
0x180080e6a  nop     dword ptr [rax+rax+00h]
0x180080e6f  mov     ebx, eax
0x180080e71  test    eax, eax
0x180080e73  jns     short loc_180080EE5
0x180080e75  mov     ecx, cs:dword_1800DF020
0x180080e7b  cmp     ecx, 3
0x180080e7e  jbe     loc_1800815C2
0x180080e84  lea     rax, aUserhitblacksc; "UserHitBlackscreenKey"
0x180080e8b  mov     [rsp+9F0h+var_9A8], rax
0x180080e90  lea     rax, aFailedToConver; "Failed to convert guid to string"
0x180080e97  lea     rdx, unk_1800CCAE0
0x180080e9e  mov     [rsp+9F0h+var_9A0], rax
0x180080ea3  lea     rax, aWarningHresult; "Warning HResult failed"
0x180080eaa  mov     qword ptr [rsp+9F0h+dwProcessId], rax
0x180080eaf  lea     rax, [rsp+9F0h+var_9A8]
0x180080eb4  mov     [rsp+9F0h+var_9B8], rax
0x180080eb9  lea     rax, [rsp+9F0h+var_9B0]
0x180080ebe  mov     [rsp+9F0h+var_9C0], rax
0x180080ec3  lea     rax, [rsp+9F0h+var_9A0]
0x180080ec8  mov     [rsp+9F0h+var_9C8], rax
0x180080ecd  lea     rax, [rsp+9F0h+dwProcessId]
0x180080ed2  mov     [rsp+9F0h+var_9B0], ebx
0x180080ed6  mov     [rsp+9F0h+var_9D0], rax
0x180080edb  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180080ee0  jmp     loc_1800815C2
0x180080ee5  mov     [rbp+8F0h+pReportInformation.hProcess], r13
0x180080ee9  mov     [rbp+8F0h+pReportInformation.dwSize], edi
0x180080eec  lea     r8, aBlackScreenUse; "Black Screen - User Reported"
0x180080ef3  mov     edx, 80h; unsigned __int64
0x180080ef8  lea     rcx, [rbp+8F0h+pReportInformation.wzFriendlyEventName]; unsigned __int16 *
0x180080efc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180080f01  mov     ebx, eax
0x180080f03  test    eax, eax
0x180080f05  jns     short loc_180080F35
0x180080f07  mov     eax, cs:dword_1800DF020
0x180080f0d  cmp     eax, 3
0x180080f10  jbe     loc_1800815C2
0x180080f16  lea     rax, aUserhitblacksc; "UserHitBlackscreenKey"
0x180080f1d  mov     [rsp+9F0h+var_9A8], rax
0x180080f22  lea     rax, aFailedToSetEve; "Failed to set event name"
0x180080f29  lea     rdx, byte_1800CCA9B
0x180080f30  jmp     loc_180080E9E
0x180080f35  lea     r8, aTheUserHasInvo; "The user has invoked the Black Screen D"...
0x180080f3c  mov     edx, 200h; unsigned __int64
0x180080f41  lea     rcx, [rbp+8F0h+pReportInformation.wzDescription]; unsigned __int16 *
0x180080f48  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180080f4d  mov     ebx, eax
0x180080f4f  test    eax, eax
0x180080f51  jns     short loc_180080F81
0x180080f53  mov     eax, cs:dword_1800DF020
0x180080f59  cmp     eax, 3
0x180080f5c  jbe     loc_1800815C2
0x180080f62  lea     rax, aUserhitblacksc; "UserHitBlackscreenKey"
0x180080f69  mov     [rsp+9F0h+var_9A8], rax
0x180080f6e  lea     rax, aFailedToSetEve_0; "Failed to set event description"
0x180080f75  lea     rdx, word_1800CCA56
0x180080f7c  jmp     loc_180080E9E
0x180080f81  mov     rbx, [rsp+9F0h+hReportHandle]
0x180080f86  test    rbx, rbx
0x180080f89  jz      short loc_180080FAE
0x180080f8b  lea     rcx, [rsp+9F0h+var_9A8]; this
0x180080f90  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180080f95  mov     rcx, rbx; hReportHandle
0x180080f98  call    cs:__imp_WerReportCloseHandle
0x180080f9f  nop     dword ptr [rax+rax+00h]
0x180080fa4  lea     rcx, [rsp+9F0h+var_9A8]; this
0x180080fa9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180080fae  mov     [rsp+9F0h+hReportHandle], r13
0x180080fb3  lea     r9, [rsp+9F0h+hReportHandle]; phReportHandle
0x180080fb8  lea     r8, [rbp+8F0h+pReportInformation]; pReportInformation
0x180080fbc  mov     edx, 1; repType
0x180080fc1  lea     rcx, pwzEventType; "WindowsBlackScreenDiagnosticsV1"
0x180080fc8  call    cs:__imp_WerReportCreate
0x180080fcf  nop     dword ptr [rax+rax+00h]
0x180080fd4  mov     ebx, eax
0x180080fd6  test    eax, eax
0x180080fd8  jns     short loc_180081008
0x180080fda  mov     eax, cs:dword_1800DF020
0x180080fe0  cmp     eax, 3
0x180080fe3  jbe     loc_1800815C2
0x180080fe9  lea     rax, aUserhitblacksc; "UserHitBlackscreenKey"
0x180080ff0  mov     [rsp+9F0h+var_9A8], rax
0x180080ff5  lea     rax, aFailedToCreate; "Failed to create report"
0x180080ffc  lea     rdx, byte_1800CCA11
0x180081003  jmp     loc_180080E9E
0x180081008  call    ?GetServicePid@@YAKPEBG@Z; GetServicePid(ushort const *)
0x18008100d  mov     edi, eax
0x18008100f  mov     edx, r15d
0x180081012  lea     rcx, [rbp+8F0h+var_90]
0x180081019  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@K@Z; std::to_wstring(ulong)
0x18008101e  cmp     qword ptr [rax+18h], 7
0x180081023  jbe     short loc_180081028
0x180081025  mov     rax, [rax]
0x180081028  mov     rdx, rax; unsigned __int16 *
0x18008102b  lea     rcx, aSourcesessioni; "SourceSessionId"
0x180081032  call    ?AddCustomMetadata@@YAXPEBG0@Z; AddCustomMetadata(ushort const *,ushort const *)
0x180081037  lea     rcx, [rbp+8F0h+var_90]
0x18008103e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180081043  mov     edx, edi
0x180081045  lea     rcx, [rbp+8F0h+var_90]
0x18008104c  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@J@Z; std::to_wstring(long)
0x180081051  cmp     qword ptr [rax+18h], 7
0x180081056  jbe     short loc_18008105B
0x180081058  mov     rax, [rax]
0x18008105b  mov     rdx, rax; unsigned __int16 *
0x18008105e  lea     rcx, aTermsrvpid; "TermsrvPID"
0x180081065  call    ?AddCustomMetadata@@YAXPEBG0@Z; AddCustomMetadata(ushort const *,ushort const *)
0x18008106a  lea     rcx, [rbp+8F0h+var_90]
0x180081071  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180081076  call    cs:__imp_GetCurrentProcessId
0x18008107d  nop     dword ptr [rax+rax+00h]
0x180081082  mov     edx, eax
0x180081084  lea     rcx, [rbp+8F0h+var_90]
0x18008108b  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@K@Z; std::to_wstring(ulong)
0x180081090  cmp     qword ptr [rax+18h], 7
0x180081095  jbe     short loc_18008109A
0x180081097  mov     rax, [rax]
0x18008109a  mov     rdx, rax; unsigned __int16 *
0x18008109d  lea     rcx, aLsmpid; "LsmPID"
0x1800810a4  call    ?AddCustomMetadata@@YAXPEBG0@Z; AddCustomMetadata(ushort const *,ushort const *)
0x1800810a9  lea     rcx, [rbp+8F0h+var_90]
0x1800810b0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800810b5  mov     rdx, [rsp+9F0h+lpsz]; unsigned __int16 *
0x1800810ba  lea     rcx, aBlackscreenins; "BlackScreenInstanceGuid"
0x1800810c1  call    ?AddCustomMetadata@@YAXPEBG0@Z; AddCustomMetadata(ushort const *,ushort const *)
0x1800810c6  mov     rbx, [rsp+9F0h+hReportHandle]
0x1800810cb  call    cs:__imp_GetCurrentProcessId
0x1800810d2  nop     dword ptr [rax+rax+00h]
0x1800810d7  xor     r8d, r8d; bool
0x1800810da  mov     rdx, rbx; hReportHandle
0x1800810dd  mov     ecx, eax; dwProcessId
0x1800810df  call    ?AddBlackscreenDump@@YAJKPEAX_N@Z; AddBlackscreenDump(ulong,void *,bool)
0x1800810e4  mov     ebx, eax
0x1800810e6  test    eax, eax
0x1800810e8  jns     short loc_180081118
0x1800810ea  mov     eax, cs:dword_1800DF020
0x1800810f0  cmp     eax, 3
0x1800810f3  jbe     loc_1800815C2
0x1800810f9  lea     rax, aUserhitblacksc; "UserHitBlackscreenKey"
0x180081100  mov     [rsp+9F0h+var_9A8], rax
0x180081105  lea     rax, aFailedToGetLsm; "Failed to get LSM dump"
0x18008110c  lea     rdx, dword_1800CC9CC
0x180081113  jmp     loc_180080E9E
0x180081118  test    edi, edi
0x18008111a  jz      short loc_18008115F
0x18008111c  mov     r8b, 1; bool
0x18008111f  mov     rdx, [rsp+9F0h+hReportHandle]; hReportHandle
0x180081124  mov     ecx, edi; dwProcessId
0x180081126  call    ?AddBlackscreenDump@@YAJKPEAX_N@Z; AddBlackscreenDump(ulong,void *,bool)
0x18008112b  mov     ebx, eax
0x18008112d  test    eax, eax
0x18008112f  jns     short loc_18008118C
0x180081131  mov     eax, cs:dword_1800DF020
0x180081137  cmp     eax, 3
0x18008113a  jbe     loc_1800815C2
0x180081140  lea     rax, aUserhitblacksc; "UserHitBlackscreenKey"
0x180081147  mov     [rsp+9F0h+var_9A8], rax
0x18008114c  lea     rax, aFailedToGetTer_1; "Failed to get termsrv dump"
0x180081153  lea     rdx, byte_1800CC987
0x18008115a  jmp     loc_180080E9E
0x18008115f  mov     eax, cs:dword_1800DF020
0x180081165  cmp     eax, 3
0x180081168  jbe     short loc_18008118C
0x18008116a  lea     rax, aNotIncludingTe; "Not including termsrv dump because we c"...
0x180081171  mov     [rsp+9F0h+var_9A8], rax
0x180081176  lea     rax, [rsp+9F0h+var_9A8]
0x18008117b  mov     [rsp+9F0h+var_9D0], rax
0x180081180  lea     rdx, dword_1800CC95C
0x180081187  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18008118c  lea     rcx, [rbp+8F0h+var_968]; struct ISessionManagerInternal **
0x180081190  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x180081195  mov     ebx, eax
0x180081197  test    eax, eax
0x180081199  jns     short loc_1800811C9
0x18008119b  mov     eax, cs:dword_1800DF020
0x1800811a1  cmp     eax, 3
0x1800811a4  jbe     loc_1800815C2
0x1800811aa  lea     rax, aUserhitblacksc; "UserHitBlackscreenKey"
0x1800811b1  mov     [rsp+9F0h+var_9A8], rax
0x1800811b6  lea     rax, aFailedToGetSes_0; "Failed to get session manager"
0x1800811bd  lea     rdx, byte_1800CC917
0x1800811c4  jmp     loc_180080E9E
0x1800811c9  mov     rcx, [rbp+8F0h+var_968]
0x1800811cd  mov     rax, [rcx]
0x1800811d0  lea     rdx, [rbp+8F0h+var_948]
0x1800811d4  mov     rax, [rax+18h]
0x1800811d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800811dd  mov     ebx, eax
0x1800811df  test    eax, eax
0x1800811e1  jns     short loc_180081211
0x1800811e3  mov     eax, cs:dword_1800DF020
0x1800811e9  cmp     eax, 3
0x1800811ec  jbe     loc_1800815C2
0x1800811f2  lea     rax, aUserhitblacksc; "UserHitBlackscreenKey"
0x1800811f9  mov     [rsp+9F0h+var_9A8], rax
0x1800811fe  lea     rax, aFailedToGetSes; "Failed to get session list"
0x180081205  lea     rdx, word_1800CC8D2
0x18008120c  jmp     loc_180080E9E
0x180081211  mov     rcx, [rbp+8F0h+var_948]
0x180081215  mov     rax, [rcx]
0x180081218  lea     rdx, [rbp+8F0h+var_958]
0x18008121c  mov     rax, [rax+20h]
0x180081220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081225  mov     ebx, eax
0x180081227  test    eax, eax
0x180081229  jns     short loc_180081259
0x18008122b  mov     eax, cs:dword_1800DF020
0x180081231  cmp     eax, 3
0x180081234  jbe     loc_1800815C2
0x18008123a  lea     rax, aUserhitblacksc; "UserHitBlackscreenKey"
0x180081241  mov     [rsp+9F0h+var_9A8], rax
0x180081246  lea     rax, aFailedToGetSes_3; "Failed to get session enum"
0x18008124d  lea     rdx, byte_1800CC88D
0x180081254  jmp     loc_180080E9E
0x180081259  mov     rcx, [rbp+8F0h+var_958]
0x18008125d  mov     rax, [rcx]
0x180081260  lea     rdx, [rbp+8F0h+var_970]
0x180081264  mov     rax, [rax+50h]
0x180081268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008126d  mov     ebx, eax
0x18008126f  test    eax, eax
0x180081271  jns     short loc_1800812A1
0x180081273  mov     eax, cs:dword_1800DF020
0x180081279  cmp     eax, 3
0x18008127c  jbe     loc_1800815C2
0x180081282  lea     rax, aUserhitblacksc; "UserHitBlackscreenKey"
0x180081289  mov     [rsp+9F0h+var_9A8], rax
0x18008128e  lea     rax, aFailedToGetAny; "Failed to get any sessions"
0x180081295  lea     rdx, unk_1800CC848
0x18008129c  jmp     loc_180080E9E
0x1800812a1  mov     edi, r13d
0x1800812a4  mov     esi, r13d
0x1800812a7  mov     r14d, r13d
0x1800812aa  mov     rcx, [rbp+8F0h+var_970]
0x1800812ae  mov     rax, [rcx]
0x1800812b1  lea     rdx, [rbp+8F0h+var_950]
0x1800812b5  mov     rax, [rax+68h]
0x1800812b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800812be  test    eax, eax
0x1800812c0  js      loc_180081390
0x1800812c6  mov     dword ptr [rsp+9F0h+var_9A0], r13d
0x1800812cb  mov     [rsp+9F0h+var_988], r13d
0x1800812d0  xorps   xmm0, xmm0
0x1800812d3  movups  [rbp+8F0h+var_90], xmm0
0x1800812da  xorps   xmm1, xmm1
0x1800812dd  movups  [rbp+8F0h+var_50], xmm1
0x1800812e4  mov     rcx, [rbp+8F0h+var_950]
0x1800812e8  mov     rax, [rcx]
0x1800812eb  lea     rdx, [rbp+8F0h+var_50]
0x1800812f2  mov     [rsp+9F0h+var_9D0], rdx
0x1800812f7  lea     r9, [rsp+9F0h+var_988]
  ... truncated ...
```
