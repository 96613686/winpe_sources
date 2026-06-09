# UserHitBlackscreenKey(_GUID,ulong)

- ea: `0x18007c448`
- end: `0x18007cd1c`
- name: `?UserHitBlackscreenKey@@YAJU_GUID@@K@Z`
- size: `2260`
- prototype: `__int64 __fastcall(IID *rclsid, unsigned int, int, int)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18007bca0`

## callees

- `0x180001408`
- `0x180001b80`
- `0x180002e88`
- `0x180008f64`
- `0x180014ff0`
- `0x18001aa50`
- `0x180025070`
- `0x180045788`
- `0x180045da4`
- `0x180046298`
- `0x1800462b8`
- `0x18004b460`
- `0x18004bf44`
- `0x180052fcc`
- `0x18007bc24`
- `0x18007bde8`
- `0x18007bf70`
- `0x18007bf9c`
- `0x18007c1c4`
- `0x18007c2e4`
- `0x18007c3c0`
- `0x18007c410`
- `0x18007c448`
- `0x18007cdfc`
- `0x18007ce68`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007c710`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007c75f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007c710`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007c75f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ca53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ca53`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18007c50f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18007ca70`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18007c50f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18007ca70`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCreate` at `0x18007c668`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCreate` at `0x18007c668`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCloseHandle` at `0x18007c63e`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCloseHandle` at `0x18007c63e`

## string_xrefs

- `0x18007c68f`: `Failed to create report`

## pseudocode

```c
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

  if ( (unsigned int)dword_1800DA020 > 5 )
  {
    v31 = a2;
    v40 = (struct ISessionManagerInternal *)rclsid;
    v32 = "Got blackscreen hotkey";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      (_DWORD)rclsid,
      (unsigned int)byte_1800C799D,
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
    LODWORD(v9) = dword_1800DA020;
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_77;
    v32 = "UserHitBlackscreenKey";
    v10 = "Failed to convert guid to string";
    v11 = byte_1800C7913;
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
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_77;
    v32 = "UserHitBlackscreenKey";
    v10 = "Failed to set event name";
    v11 = (char *)&unk_1800C7958;
    goto LABEL_6;
  }
  InstanceOfSessionManagerInternal = StringCchCopyW(
                                       pReportInformation.wzDescription,
                                       0x200u,
                                       L"The user has invoked the Black Screen Diagnostics Tool to generate this report ab"
                                        "out LSM and Termsrv");
  if ( InstanceOfSessionManagerInternal < 0 )
  {
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_77;
    v32 = "UserHitBlackscreenKey";
    v10 = "Failed to set event description";
    v11 = (char *)&word_1800C78CE;
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
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_77;
    v32 = "UserHitBlackscreenKey";
    v10 = "Failed to create report";
    v11 = (char *)&dword_1800C7844;
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
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_77;
    v32 = "UserHitBlackscreenKey";
    v10 = "Failed to get LSM dump";
    v11 = byte_1800C7889;
    goto LABEL_6;
  }
  if ( ServicePid )
  {
    InstanceOfSessionManagerInternal = AddBlackscreenDump(ServicePid, hReportHandle, 1);
    if ( InstanceOfSessionManagerInternal < 0 )
    {
      if ( (unsigned int)dword_1800DA020 <= 3 )
        goto LABEL_77;
      v32 = "UserHitBlackscreenKey";
      v10 = "Failed to get termsrv dump";
      v11 = (char *)&dword_1800C77D4;
      goto LABEL_6;
    }
  }
  else if ( (unsigned int)dword_1800DA020 > 3 )
  {
    v32 = "Not including termsrv dump because we couldn't determine the PID";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (_DWORD)v9,
      (unsigned int)byte_1800C7819,
      v7,
      v8,
      (__int64)&v32);
  }
  InstanceOfSessionManagerInternal = ISessionManagerInternal::GetInstanceOfSessionManagerInternal(&v40);
  if ( InstanceOfSessionManagerInternal < 0 )
  {
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_77;
    v32 = "UserHitBlackscreenKey";
    v10 = "Failed to get session manager";
    v11 = (char *)word_1800C774A;
    goto LABEL_6;
  }
  InstanceOfSessionManagerInternal = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *, __int64 *))(*(_QWORD *)v40 + 24LL))(
                                       v40,
                                       &v44);
  if ( InstanceOfSessionManagerInternal < 0 )
  {
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_77;
    v32 = "UserHitBlackscreenKey";
    v10 = "Failed to get session list";
    v11 = &byte_1800C778F;
    goto LABEL_6;
  }
  InstanceOfSessionManagerInternal = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 32LL))(v44, &v42);
  if ( InstanceOfSessionManagerInternal < 0 )
  {
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_77;
    v32 = "UserHitBlackscreenKey";
    v10 = "Failed to get session enum";
    v11 = byte_1800C7705;
    goto LABEL_6;
  }
  InstanceOfSessionManagerInternal = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v42 + 80LL))(v42, &v39);
  if ( InstanceOfSessionManagerInternal < 0 )
  {
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_77;
    v32 = "UserHitBlackscreenKey";
    v10 = "Failed to get any sessions";
    v11 = (char *)&unk_1800C76C0;
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
      else if ( (unsigned int)dword_1800DA020 > 3 )
      {
        v37 = "UserHitBlackscreenKey";
        LODWORD(v32) = InstanceOfSessionManagerInternal;
        v41 = "Failed to convert blackscreen guid to string";
        v45[0] = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)v9,
          (unsigned int)&byte_1800C75E7,
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
  if ( (unsigned int)dword_1800DA020 > 3 )
  {
    v45[0] = "UserHitBlackscreenKey";
    LODWORD(v32) = InstanceOfSessionManagerInternal;
    v41 = "Failed to get WUDFHostPid dump";
    v37 = "Warning HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (_DWORD)v9,
      (unsigned int)byte_1800C767B,
      v7,
      v8,
      (__int64)&v37,
      (__int64)&v41,
      (__int64)&v32,
      (__int64)v45);
  }
LABEL_77:
  if ( (unsigned int)dword_1800DA020 > 5 )
  {
    LODWORD(v32) = InstanceOfSessionManagerInternal;
    LODWORD(v33) = a2;
    v37 = (const char *)rclsid;
    v41 = "Finished blackscreen hotkey";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v9,
      (unsigned int)&dword_1800C762C,
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
0x18007c448  mov     [rsp-8+arg_10], rbx
0x18007c44d  push    rbp
0x18007c44e  push    rsi
0x18007c44f  push    rdi
0x18007c450  push    r12
0x18007c452  push    r13
0x18007c454  push    r14
0x18007c456  push    r15
0x18007c458  lea     rbp, [rsp-8C0h]
0x18007c460  sub     rsp, 9C0h
0x18007c467  mov     rax, cs:__security_cookie
0x18007c46e  xor     rax, rsp
0x18007c471  mov     [rbp+8F0h+var_40], rax
0x18007c478  mov     r15d, edx
0x18007c47b  mov     r12, rcx
0x18007c47e  mov     eax, cs:dword_1800DA020
0x18007c484  cmp     eax, 5
0x18007c487  jbe     short loc_18007C4C6
0x18007c489  mov     [rsp+9F0h+var_9B0], edx
0x18007c48d  mov     [rbp+8F0h+var_968], rcx
0x18007c491  lea     rax, aGotBlackscreen; "Got blackscreen hotkey"
0x18007c498  mov     [rsp+9F0h+var_9A8], rax
0x18007c49d  lea     rax, [rsp+9F0h+var_9B0]
0x18007c4a2  mov     [rsp+9F0h+var_9C0], rax
0x18007c4a7  lea     rax, [rbp+8F0h+var_968]
0x18007c4ab  mov     [rsp+9F0h+var_9C8], rax
0x18007c4b0  lea     rax, [rsp+9F0h+var_9A8]
0x18007c4b5  mov     [rsp+9F0h+var_9D0], rax
0x18007c4ba  lea     rdx, byte_1800C799D
0x18007c4c1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18007c4c6  xor     r13d, r13d
0x18007c4c9  mov     [rbp+8F0h+var_970], r13
0x18007c4cd  mov     [rbp+8F0h+var_950], r13
0x18007c4d1  mov     [rbp+8F0h+var_968], r13
0x18007c4d5  mov     [rbp+8F0h+var_948], r13
0x18007c4d9  mov     [rbp+8F0h+var_958], r13
0x18007c4dd  mov     edi, 8A0h
0x18007c4e2  mov     r8d, edi; Size
0x18007c4e5  xor     edx, edx; Val
0x18007c4e7  lea     rcx, [rbp+8F0h+pReportInformation]; void *
0x18007c4eb  call    memset_0
0x18007c4f0  lea     rcx, [rbp+8F0h+var_70]
0x18007c4f7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18007c4fc  nop
0x18007c4fd  mov     [rsp+9F0h+hReportHandle], r13
0x18007c502  mov     [rsp+9F0h+lpsz], r13
0x18007c507  lea     rdx, [rsp+9F0h+lpsz]; lplpsz
0x18007c50c  mov     rcx, r12; rclsid
0x18007c50f  call    cs:__imp_StringFromCLSID
0x18007c515  mov     ebx, eax
0x18007c517  test    eax, eax
0x18007c519  jns     short loc_18007C58B
0x18007c51b  mov     ecx, cs:dword_1800DA020
0x18007c521  cmp     ecx, 3
0x18007c524  jbe     loc_18007CC44
0x18007c52a  lea     rax, aUserhitblacksc; "UserHitBlackscreenKey"
0x18007c531  mov     [rsp+9F0h+var_9A8], rax
0x18007c536  lea     rax, aFailedToConver; "Failed to convert guid to string"
0x18007c53d  lea     rdx, byte_1800C7913
0x18007c544  mov     [rsp+9F0h+var_9A0], rax
0x18007c549  lea     rax, aWarningHresult; "Warning HResult failed"
0x18007c550  mov     qword ptr [rsp+9F0h+dwProcessId], rax
0x18007c555  lea     rax, [rsp+9F0h+var_9A8]
0x18007c55a  mov     [rsp+9F0h+var_9B8], rax
0x18007c55f  lea     rax, [rsp+9F0h+var_9B0]
0x18007c564  mov     [rsp+9F0h+var_9C0], rax
0x18007c569  lea     rax, [rsp+9F0h+var_9A0]
0x18007c56e  mov     [rsp+9F0h+var_9C8], rax
0x18007c573  lea     rax, [rsp+9F0h+dwProcessId]
0x18007c578  mov     [rsp+9F0h+var_9B0], ebx
0x18007c57c  mov     [rsp+9F0h+var_9D0], rax
0x18007c581  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18007c586  jmp     loc_18007CC44
0x18007c58b  mov     [rbp+8F0h+pReportInformation.hProcess], r13
0x18007c58f  mov     [rbp+8F0h+pReportInformation.dwSize], edi
0x18007c592  lea     r8, aBlackScreenUse; "Black Screen - User Reported"
0x18007c599  mov     edx, 80h; unsigned __int64
0x18007c59e  lea     rcx, [rbp+8F0h+pReportInformation.wzFriendlyEventName]; unsigned __int16 *
0x18007c5a2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007c5a7  mov     ebx, eax
0x18007c5a9  test    eax, eax
0x18007c5ab  jns     short loc_18007C5DB
0x18007c5ad  mov     eax, cs:dword_1800DA020
0x18007c5b3  cmp     eax, 3
0x18007c5b6  jbe     loc_18007CC44
0x18007c5bc  lea     rax, aUserhitblacksc; "UserHitBlackscreenKey"
0x18007c5c3  mov     [rsp+9F0h+var_9A8], rax
0x18007c5c8  lea     rax, aFailedToSetEve; "Failed to set event name"
0x18007c5cf  lea     rdx, unk_1800C7958
0x18007c5d6  jmp     loc_18007C544
0x18007c5db  lea     r8, aTheUserHasInvo; "The user has invoked the Black Screen D"...
0x18007c5e2  mov     edx, 200h; unsigned __int64
0x18007c5e7  lea     rcx, [rbp+8F0h+pReportInformation.wzDescription]; unsigned __int16 *
0x18007c5ee  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007c5f3  mov     ebx, eax
0x18007c5f5  test    eax, eax
0x18007c5f7  jns     short loc_18007C627
0x18007c5f9  mov     eax, cs:dword_1800DA020
0x18007c5ff  cmp     eax, 3
0x18007c602  jbe     loc_18007CC44
0x18007c608  lea     rax, aUserhitblacksc; "UserHitBlackscreenKey"
0x18007c60f  mov     [rsp+9F0h+var_9A8], rax
0x18007c614  lea     rax, aFailedToSetEve_0; "Failed to set event description"
0x18007c61b  lea     rdx, word_1800C78CE
0x18007c622  jmp     loc_18007C544
0x18007c627  mov     rbx, [rsp+9F0h+hReportHandle]
0x18007c62c  test    rbx, rbx
0x18007c62f  jz      short loc_18007C64E
0x18007c631  lea     rcx, [rsp+9F0h+var_9A8]; this
0x18007c636  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18007c63b  mov     rcx, rbx; hReportHandle
0x18007c63e  call    cs:__imp_WerReportCloseHandle
0x18007c644  lea     rcx, [rsp+9F0h+var_9A8]; this
0x18007c649  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18007c64e  mov     [rsp+9F0h+hReportHandle], r13
0x18007c653  lea     r9, [rsp+9F0h+hReportHandle]; phReportHandle
0x18007c658  lea     r8, [rbp+8F0h+pReportInformation]; pReportInformation
0x18007c65c  mov     edx, 1; repType
0x18007c661  lea     rcx, pwzEventType; "WindowsBlackScreenDiagnosticsV1"
0x18007c668  call    cs:__imp_WerReportCreate
0x18007c66e  mov     ebx, eax
0x18007c670  test    eax, eax
0x18007c672  jns     short loc_18007C6A2
0x18007c674  mov     eax, cs:dword_1800DA020
0x18007c67a  cmp     eax, 3
0x18007c67d  jbe     loc_18007CC44
0x18007c683  lea     rax, aUserhitblacksc; "UserHitBlackscreenKey"
0x18007c68a  mov     [rsp+9F0h+var_9A8], rax
0x18007c68f  lea     rax, aFailedToCreate; "Failed to create report"
0x18007c696  lea     rdx, dword_1800C7844
0x18007c69d  jmp     loc_18007C544
0x18007c6a2  call    ?GetServicePid@@YAKPEBG@Z; GetServicePid(ushort const *)
0x18007c6a7  mov     edi, eax
0x18007c6a9  mov     edx, r15d
0x18007c6ac  lea     rcx, [rbp+8F0h+var_90]
0x18007c6b3  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@K@Z; std::to_wstring(ulong)
0x18007c6b8  cmp     qword ptr [rax+18h], 7
0x18007c6bd  jbe     short loc_18007C6C2
0x18007c6bf  mov     rax, [rax]
0x18007c6c2  mov     rdx, rax; unsigned __int16 *
0x18007c6c5  lea     rcx, aSourcesessioni; "SourceSessionId"
0x18007c6cc  call    ?AddCustomMetadata@@YAXPEBG0@Z; AddCustomMetadata(ushort const *,ushort const *)
0x18007c6d1  lea     rcx, [rbp+8F0h+var_90]
0x18007c6d8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007c6dd  mov     edx, edi
0x18007c6df  lea     rcx, [rbp+8F0h+var_90]
0x18007c6e6  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@J@Z; std::to_wstring(long)
0x18007c6eb  cmp     qword ptr [rax+18h], 7
0x18007c6f0  jbe     short loc_18007C6F5
0x18007c6f2  mov     rax, [rax]
0x18007c6f5  mov     rdx, rax; unsigned __int16 *
0x18007c6f8  lea     rcx, aTermsrvpid; "TermsrvPID"
0x18007c6ff  call    ?AddCustomMetadata@@YAXPEBG0@Z; AddCustomMetadata(ushort const *,ushort const *)
0x18007c704  lea     rcx, [rbp+8F0h+var_90]
0x18007c70b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007c710  call    cs:__imp_GetCurrentProcessId
0x18007c716  mov     edx, eax
0x18007c718  lea     rcx, [rbp+8F0h+var_90]
0x18007c71f  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@K@Z; std::to_wstring(ulong)
0x18007c724  cmp     qword ptr [rax+18h], 7
0x18007c729  jbe     short loc_18007C72E
0x18007c72b  mov     rax, [rax]
0x18007c72e  mov     rdx, rax; unsigned __int16 *
0x18007c731  lea     rcx, aLsmpid; "LsmPID"
0x18007c738  call    ?AddCustomMetadata@@YAXPEBG0@Z; AddCustomMetadata(ushort const *,ushort const *)
0x18007c73d  lea     rcx, [rbp+8F0h+var_90]
0x18007c744  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007c749  mov     rdx, [rsp+9F0h+lpsz]; unsigned __int16 *
0x18007c74e  lea     rcx, aBlackscreenins; "BlackScreenInstanceGuid"
0x18007c755  call    ?AddCustomMetadata@@YAXPEBG0@Z; AddCustomMetadata(ushort const *,ushort const *)
0x18007c75a  mov     rbx, [rsp+9F0h+hReportHandle]
0x18007c75f  call    cs:__imp_GetCurrentProcessId
0x18007c765  xor     r8d, r8d; bool
0x18007c768  mov     rdx, rbx; hReportHandle
0x18007c76b  mov     ecx, eax; dwProcessId
0x18007c76d  call    ?AddBlackscreenDump@@YAJKPEAX_N@Z; AddBlackscreenDump(ulong,void *,bool)
0x18007c772  mov     ebx, eax
0x18007c774  test    eax, eax
0x18007c776  jns     short loc_18007C7A6
0x18007c778  mov     eax, cs:dword_1800DA020
0x18007c77e  cmp     eax, 3
0x18007c781  jbe     loc_18007CC44
0x18007c787  lea     rax, aUserhitblacksc; "UserHitBlackscreenKey"
0x18007c78e  mov     [rsp+9F0h+var_9A8], rax
0x18007c793  lea     rax, aFailedToGetLsm; "Failed to get LSM dump"
0x18007c79a  lea     rdx, byte_1800C7889
0x18007c7a1  jmp     loc_18007C544
0x18007c7a6  test    edi, edi
0x18007c7a8  jz      short loc_18007C7ED
0x18007c7aa  mov     r8b, 1; bool
0x18007c7ad  mov     rdx, [rsp+9F0h+hReportHandle]; hReportHandle
0x18007c7b2  mov     ecx, edi; dwProcessId
0x18007c7b4  call    ?AddBlackscreenDump@@YAJKPEAX_N@Z; AddBlackscreenDump(ulong,void *,bool)
0x18007c7b9  mov     ebx, eax
0x18007c7bb  test    eax, eax
0x18007c7bd  jns     short loc_18007C81A
0x18007c7bf  mov     eax, cs:dword_1800DA020
0x18007c7c5  cmp     eax, 3
0x18007c7c8  jbe     loc_18007CC44
0x18007c7ce  lea     rax, aUserhitblacksc; "UserHitBlackscreenKey"
0x18007c7d5  mov     [rsp+9F0h+var_9A8], rax
0x18007c7da  lea     rax, aFailedToGetTer_1; "Failed to get termsrv dump"
0x18007c7e1  lea     rdx, dword_1800C77D4
0x18007c7e8  jmp     loc_18007C544
0x18007c7ed  mov     eax, cs:dword_1800DA020
0x18007c7f3  cmp     eax, 3
0x18007c7f6  jbe     short loc_18007C81A
0x18007c7f8  lea     rax, aNotIncludingTe; "Not including termsrv dump because we c"...
0x18007c7ff  mov     [rsp+9F0h+var_9A8], rax
0x18007c804  lea     rax, [rsp+9F0h+var_9A8]
0x18007c809  mov     [rsp+9F0h+var_9D0], rax
0x18007c80e  lea     rdx, byte_1800C7819
0x18007c815  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18007c81a  lea     rcx, [rbp+8F0h+var_968]; struct ISessionManagerInternal **
0x18007c81e  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x18007c823  mov     ebx, eax
0x18007c825  test    eax, eax
0x18007c827  jns     short loc_18007C857
0x18007c829  mov     eax, cs:dword_1800DA020
0x18007c82f  cmp     eax, 3
0x18007c832  jbe     loc_18007CC44
0x18007c838  lea     rax, aUserhitblacksc; "UserHitBlackscreenKey"
0x18007c83f  mov     [rsp+9F0h+var_9A8], rax
0x18007c844  lea     rax, aFailedToGetSes_0; "Failed to get session manager"
0x18007c84b  lea     rdx, word_1800C774A
0x18007c852  jmp     loc_18007C544
0x18007c857  mov     rcx, [rbp+8F0h+var_968]
0x18007c85b  mov     rax, [rcx]
0x18007c85e  lea     rdx, [rbp+8F0h+var_948]
0x18007c862  mov     rax, [rax+18h]
0x18007c866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c86b  mov     ebx, eax
0x18007c86d  test    eax, eax
0x18007c86f  jns     short loc_18007C89F
0x18007c871  mov     eax, cs:dword_1800DA020
0x18007c877  cmp     eax, 3
0x18007c87a  jbe     loc_18007CC44
0x18007c880  lea     rax, aUserhitblacksc; "UserHitBlackscreenKey"
0x18007c887  mov     [rsp+9F0h+var_9A8], rax
0x18007c88c  lea     rax, aFailedToGetSes; "Failed to get session list"
0x18007c893  lea     rdx, byte_1800C778F
0x18007c89a  jmp     loc_18007C544
0x18007c89f  mov     rcx, [rbp+8F0h+var_948]
0x18007c8a3  mov     rax, [rcx]
0x18007c8a6  lea     rdx, [rbp+8F0h+var_958]
0x18007c8aa  mov     rax, [rax+20h]
0x18007c8ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c8b3  mov     ebx, eax
0x18007c8b5  test    eax, eax
0x18007c8b7  jns     short loc_18007C8E7
0x18007c8b9  mov     eax, cs:dword_1800DA020
0x18007c8bf  cmp     eax, 3
0x18007c8c2  jbe     loc_18007CC44
0x18007c8c8  lea     rax, aUserhitblacksc; "UserHitBlackscreenKey"
0x18007c8cf  mov     [rsp+9F0h+var_9A8], rax
0x18007c8d4  lea     rax, aFailedToGetSes_3; "Failed to get session enum"
0x18007c8db  lea     rdx, byte_1800C7705
0x18007c8e2  jmp     loc_18007C544
0x18007c8e7  mov     rcx, [rbp+8F0h+var_958]
0x18007c8eb  mov     rax, [rcx]
0x18007c8ee  lea     rdx, [rbp+8F0h+var_970]
0x18007c8f2  mov     rax, [rax+50h]
0x18007c8f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c8fb  mov     ebx, eax
0x18007c8fd  test    eax, eax
0x18007c8ff  jns     short loc_18007C92F
0x18007c901  mov     eax, cs:dword_1800DA020
0x18007c907  cmp     eax, 3
0x18007c90a  jbe     loc_18007CC44
0x18007c910  lea     rax, aUserhitblacksc; "UserHitBlackscreenKey"
0x18007c917  mov     [rsp+9F0h+var_9A8], rax
0x18007c91c  lea     rax, aFailedToGetAny; "Failed to get any sessions"
0x18007c923  lea     rdx, unk_1800C76C0
0x18007c92a  jmp     loc_18007C544
0x18007c92f  mov     edi, r13d
0x18007c932  mov     esi, r13d
0x18007c935  mov     r14d, r13d
0x18007c938  mov     rcx, [rbp+8F0h+var_970]
0x18007c93c  mov     rax, [rcx]
0x18007c93f  lea     rdx, [rbp+8F0h+var_950]
0x18007c943  mov     rax, [rax+68h]
0x18007c947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c94c  test    eax, eax
0x18007c94e  js      loc_18007CA1E
0x18007c954  mov     dword ptr [rsp+9F0h+var_9A0], r13d
0x18007c959  mov     [rsp+9F0h+var_988], r13d
0x18007c95e  xorps   xmm0, xmm0
0x18007c961  movups  [rbp+8F0h+var_90], xmm0
0x18007c968  xorps   xmm1, xmm1
0x18007c96b  movups  [rbp+8F0h+var_50], xmm1
0x18007c972  mov     rcx, [rbp+8F0h+var_950]
0x18007c976  mov     rax, [rcx]
0x18007c979  lea     rdx, [rbp+8F0h+var_50]
0x18007c980  mov     [rsp+9F0h+var_9D0], rdx
0x18007c985  lea     r9, [rsp+9F0h+var_988]
0x18007c98a  lea     r8, [rsp+9F0h+var_9A0]
0x18007c98f  lea     rdx, [rbp+8F0h+var_90]
0x18007c996  mov     rax, [rax+88h]
0x18007c99d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c9a2  cmp     [rsp+9F0h+var_988], 1
  ... truncated ...
```
