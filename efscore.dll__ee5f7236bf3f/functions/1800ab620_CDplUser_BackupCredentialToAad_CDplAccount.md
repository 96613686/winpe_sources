# CDplUser::BackupCredentialToAad(CDplAccount *)

- ea: `0x1800ab620`
- end: `0x1800ac1de`
- name: `?BackupCredentialToAad@CDplUser@@AEAAJPEAVCDplAccount@@@Z`
- size: `3006`
- prototype: `__int64 __fastcall(CDplUser *__hidden this, struct CDplAccount *)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800bd950`

## callees

- `0x180001a7c`
- `0x180001d84`
- `0x180002628`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x18006fb14`
- `0x1800841d0`
- `0x1800857a8`
- `0x180088808`
- `0x1800961b0`
- `0x1800964ac`
- `0x18009652c`
- `0x18009a5a8`
- `0x1800a8660`
- `0x1800ab00c`
- `0x1800ab620`
- `0x1800b4668`
- `0x1800bd7a8`
- `0x1800bd810`
- `0x1800bd9d8`
- `0x1800cf880`
- `0x1800cfe1c`
- `0x1800d0534`
- `0x1800d5af8`
- `0x1800dca3c`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aba02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800abf4a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aba02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800abf4a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aba10`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800abf58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aba10`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800abf58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab8de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab8de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aba77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aba77`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800abad2`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800abad2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800abd87`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800abd87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800aba58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800aba58`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800aba68`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800aba68`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800ab8d0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800ab8d0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800ab77c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800abec5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800abfb2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800ab77c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800abec5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800abfb2`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800ac141`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800ac141`
- `WINHTTP!WinHttpCloseHandle` at `0x1800aba1f`
- `WINHTTP!WinHttpCloseHandle` at `0x1800aba2e`
- `WINHTTP!WinHttpCloseHandle` at `0x1800aba3c`
- `WINHTTP!WinHttpCloseHandle` at `0x1800abf6e`
- `WINHTTP!WinHttpCloseHandle` at `0x1800abf81`
- `WINHTTP!WinHttpCloseHandle` at `0x1800abf93`
- `WINHTTP!WinHttpCloseHandle` at `0x1800aba1f`
- `WINHTTP!WinHttpCloseHandle` at `0x1800aba2e`
- `WINHTTP!WinHttpCloseHandle` at `0x1800aba3c`
- `WINHTTP!WinHttpCloseHandle` at `0x1800abf6e`
- `WINHTTP!WinHttpCloseHandle` at `0x1800abf81`
- `WINHTTP!WinHttpCloseHandle` at `0x1800abf93`

## string_xrefs

- `0x1800abb3e`: `RequestComplete`

## pseudocode

```c
__int64 __fastcall CDplUser::BackupCredentialToAad(CDplUser *this, struct CDplAccount *a2)
{
  signed int IsAutoRecoverySupported; // ebx
  unsigned __int16 *v5; // rsi
  void *v6; // r13
  void *v7; // r15
  unsigned __int16 *v8; // r12
  __int64 v9; // rcx
  bool IsZero; // al
  GUID *p_ActivityId; // r9
  unsigned __int64 v12; // rcx
  __int64 v13; // rax
  int v14; // ecx
  int v15; // ecx
  signed int LastError; // eax
  __int64 *v17; // rdx
  int v18; // r8d
  HANDLE v19; // rax
  int v20; // r9d
  int v22; // ecx
  int v23; // ecx
  CDplServiceImpl *v24; // rcx
  int v25; // r9d
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  HANDLE ProcessHeap; // rax
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  const unsigned __int16 *v35; // rdx
  LSTATUS v36; // eax
  char lpData; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v38; // [rsp+50h] [rbp-B0h] BYREF
  int v39; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 Data; // [rsp+60h] [rbp-A0h] BYREF
  int v41; // [rsp+68h] [rbp-98h] BYREF
  int v42; // [rsp+6Ch] [rbp-94h]
  BOOL v43; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v44; // [rsp+74h] [rbp-8Ch] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v46; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v47; // [rsp+84h] [rbp-7Ch] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v49; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v50; // [rsp+98h] [rbp-68h] BYREF
  LPVOID lpMem; // [rsp+A0h] [rbp-60h] BYREF
  HINTERNET v52; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int8 *v53; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int8 *v54; // [rsp+B8h] [rbp-48h] BYREF
  HINTERNET hInternet; // [rsp+C0h] [rbp-40h] BYREF
  HINTERNET v56; // [rsp+C8h] [rbp-38h] BYREF
  HANDLE hToken; // [rsp+D0h] [rbp-30h] BYREF
  void *v58; // [rsp+D8h] [rbp-28h] BYREF
  int v59; // [rsp+E0h] [rbp-20h] BYREF
  char v60; // [rsp+E4h] [rbp-1Ch]
  _BYTE v61[16]; // [rsp+E8h] [rbp-18h] BYREF
  GUID ActivityId; // [rsp+F8h] [rbp-8h] BYREF

  IsAutoRecoverySupported = 0;
  v58 = 0;
  hToken = 0;
  v43 = 0;
  v41 = 0;
  v53 = 0;
  v47 = 0;
  v5 = 0;
  v54 = 0;
  v6 = 0;
  v46 = 0;
  v7 = 0;
  v50 = 0;
  v8 = 0;
  v44 = 0;
  v38 = 0;
  lpMem = 0;
  hInternet = 0;
  v56 = 0;
  v52 = 0;
  hKey = 0;
  SystemTimeAsFileTime = 0;
  Data = 0;
  v49 = 0;
  v42 = 0;
  v39 = 0;
  v59 = 0;
  v60 = 0;
  fnEfsLogTrace1Strings((_DWORD)this, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 40, 123);
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hEfsCoreTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v59);
  if ( (unsigned int)dword_180114250 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180114250, 0x400000000000LL) )
  {
    if ( !v60 || (IsZero = _tlgGuidIsZero(&ActivityId), p_ActivityId = &ActivityId, IsZero) )
      p_ActivityId = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180114250,
      word_18010393A,
      v61,
      p_ActivityId);
  }
  if ( !a2 )
  {
    IsAutoRecoverySupported = -2147024809;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 40, 131);
    goto LABEL_30;
  }
  if ( *((_DWORD *)a2 + 51) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v9);
    IsAutoRecoverySupported = -2147418113;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147418113, 40, 137);
    goto LABEL_30;
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v12 = *((_QWORD *)a2 + 1);
  Data = (unsigned __int64)SystemTimeAsFileTime;
  if ( *((_QWORD *)this + 3) < v12 )
  {
    v13 = *((_QWORD *)a2 + 27);
    if ( !v13 || v13 + 36000000000LL <= Data )
    {
      if ( *((_DWORD *)a2 + 50) )
      {
        *((_QWORD *)this + 3) = v12;
        goto LABEL_30;
      }
      fnEfsLogTrace1Strings(v12, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 179);
      IsAutoRecoverySupported = CDplServiceImpl::RevertToSelf(*((CDplServiceImpl **)this + 6), &v58);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  IsAutoRecoverySupported,
                  40,
                  179) >= 0 )
      {
        fnEfsLogTrace1Strings(v14, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 185);
        IsAutoRecoverySupported = EdpCredSvcQuerySessionUserTokenBySid(*((const unsigned __int16 **)this + 13), &hToken);
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    IsAutoRecoverySupported,
                    40,
                    185) >= 0 )
        {
          if ( !hToken )
          {
            IsAutoRecoverySupported = -2147023888;
            fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147023888, 40, 191);
            goto LABEL_30;
          }
          v43 = ImpersonateLoggedOnUser(hToken);
          if ( !v43 )
          {
            LastError = GetLastError();
            IsAutoRecoverySupported = LastError;
            if ( LastError > 0 )
              IsAutoRecoverySupported = (unsigned __int16)LastError | 0x80070000;
            fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, IsAutoRecoverySupported, 40, 197);
            goto LABEL_30;
          }
          fnEfsLogTrace1Strings(v15, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 206);
          IsAutoRecoverySupported = CDplUser::IsAutoRecoverySupported(this, *((const unsigned __int16 **)a2 + 8), &v41);
          if ( (int)fnEfsLogTrace1String1Dword(
                      g_hPublisher,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                      (unsigned int)&sourceString,
                      IsAutoRecoverySupported,
                      40,
                      206) < 0 )
            goto LABEL_30;
          if ( !v41 )
          {
            lpData = -42;
LABEL_27:
            v17 = EFS_TRACE_STATUS;
            IsAutoRecoverySupported = 1;
            v18 = 1;
LABEL_28:
            fnEfsLogTrace1(g_hPublisher, (_DWORD)v17, v18, 40, lpData);
LABEL_29:
            v5 = v38;
            goto LABEL_30;
          }
          if ( *((_QWORD *)a2 + 10) )
          {
            lpData = -28;
            goto LABEL_27;
          }
          v42 = CDplUser::UserSvcLock(this);
          fnEfsLogTrace1Strings(v22, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 243);
          IsAutoRecoverySupported = CDplAccount::Serialize(a2, &v53, &v47, &v54, &v46, 1, 0);
          if ( (int)fnEfsLogTrace1String1Dword(
                      g_hPublisher,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                      (unsigned int)&sourceString,
                      IsAutoRecoverySupported,
                      40,
                      243) < 0 )
            goto LABEL_29;
          v42 = CDplUser::UserSvcUnlock(this, v42);
          if ( v54 )
          {
            if ( v46 )
            {
              fnEfsLogTrace1Strings(v23, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 254);
              IsAutoRecoverySupported = CDplServiceImpl::Base64Encode(v24, v53, v47, v25, &v50, &v44);
              if ( (int)fnEfsLogTrace1String1Dword(
                          g_hPublisher,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                          (unsigned int)&sourceString,
                          IsAutoRecoverySupported,
                          40,
                          254) < 0 )
                goto LABEL_29;
              fnEfsLogTrace1Strings(v26, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 1);
              IsAutoRecoverySupported = CDplService::UtcTimestampToLocalTimeString(*((_QWORD *)a2 + 1), &v38);
              if ( (int)fnEfsLogTrace1String1Dword(
                          g_hPublisher,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                          (unsigned int)&sourceString,
                          IsAutoRecoverySupported,
                          40,
                          1) < 0 )
                goto LABEL_29;
              v27 = 0;
              while ( 1 )
              {
                v39 = v27 + 1;
                Sleep(250 * v27);
                fnEfsLogTrace1Strings(v28, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 24);
                IsAutoRecoverySupported = WIPCreateRequestForAAD(
                                            3,
                                            (char *)a2 + 24,
                                            v38,
                                            v50,
                                            &lpMem,
                                            &hInternet,
                                            &v56,
                                            &v52);
                if ( (int)fnEfsLogTrace1String1Dword(
                            g_hPublisher,
                            (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                            (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                            (unsigned int)&sourceString,
                            IsAutoRecoverySupported,
                            40,
                            24) < 0
                  || IsAutoRecoverySupported == 1 )
                {
                  v6 = lpMem;
                  v7 = v52;
                  goto LABEL_29;
                }
                fnEfsLogTrace1Strings(v29, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 41);
                v6 = lpMem;
                v7 = v52;
                IsAutoRecoverySupported = WIPSendHttpRequest(3, v52, lpMem);
                if ( (int)fnEfsLogTrace1String1Dword(
                            g_hPublisher,
                            (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                            (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                            (unsigned int)&sourceString,
                            IsAutoRecoverySupported,
                            40,
                            41) < 0 )
                  goto LABEL_29;
                IsAutoRecoverySupported = WIPGetAndParseResponse(3, v7, 0);
                if ( IsAutoRecoverySupported >= 0 )
                  break;
                GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
                Data = (unsigned __int64)SystemTimeAsFileTime;
                *((struct _FILETIME *)a2 + 27) = SystemTimeAsFileTime;
                fnEfsLogTrace1Strings(v30, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 116);
                if ( (int)fnEfsLogTrace1String1Dword(
                            g_hPublisher,
                            (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                            (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                            (unsigned int)&sourceString,
                            IsAutoRecoverySupported,
                            40,
                            116) >= 0 )
                {
                  if ( v6 )
                  {
                    ProcessHeap = GetProcessHeap();
                    HeapFree(ProcessHeap, 0, v6);
                    v6 = 0;
                    lpMem = 0;
                  }
                  if ( hInternet )
                  {
                    WinHttpCloseHandle(hInternet);
                    hInternet = 0;
                  }
                  if ( v56 )
                  {
                    WinHttpCloseHandle(v56);
                    v56 = 0;
                  }
                  if ( v7 )
                  {
                    WinHttpCloseHandle(v7);
                    v7 = 0;
                    v52 = 0;
                  }
                  v27 = v39;
                  if ( v39 < 3 )
                    continue;
                }
                goto LABEL_29;
              }
              GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
              Data = (unsigned __int64)SystemTimeAsFileTime;
              fnEfsLogTrace1Strings(v32, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 63);
              IsAutoRecoverySupported = CDplService::UtcTimestampToLocalTimeString(Data, &v49);
              if ( (int)fnEfsLogTrace1String1Dword(
                          g_hPublisher,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                          (unsigned int)&sourceString,
                          IsAutoRecoverySupported,
                          40,
                          63) < 0
                || (fnEfsLogTrace1Strings(v33, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 71),
                    IsAutoRecoverySupported = EdpCredSvcOpenUserCredStore(
                                                *((const unsigned __int16 **)this + 13),
                                                0xF003Fu,
                                                &hKey),
                    (int)fnEfsLogTrace1String1Dword(
                           g_hPublisher,
                           (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                           (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                           (unsigned int)&sourceString,
                           IsAutoRecoverySupported,
                           40,
                           71) < 0) )
              {
                v8 = v49;
                goto LABEL_29;
              }
              fnEfsLogTrace1Strings(v34, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 76);
              v8 = v49;
              IsAutoRecoverySupported = CDplService::RegSetStringValue(hKey, v35, L"AadLastBackupSucceededTime", v49);
              if ( (int)fnEfsLogTrace1String1Dword(
                          g_hPublisher,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                          (unsigned int)&sourceString,
                          IsAutoRecoverySupported,
                          40,
                          76) < 0 )
                goto LABEL_29;
              if ( v8 )
                DplibMemFree(v8);
              v8 = 0;
              v36 = RegSetKeyValueW(hKey, 0, L"AadBackupSucceededOnce", 0xBu, &Data, 8u);
              if ( !v36 )
              {
                *((_QWORD *)this + 3) = Data;
                *((_QWORD *)a2 + 27) = 0;
                goto LABEL_29;
              }
              if ( v36 > 0 )
                IsAutoRecoverySupported = (unsigned __int16)v36 | 0x80070000;
              else
                IsAutoRecoverySupported = v36;
              lpData = 89;
              v18 = IsAutoRecoverySupported;
              goto LABEL_93;
            }
            lpData = -8;
          }
          else
          {
            lpData = -9;
          }
          IsAutoRecoverySupported = -2147418113;
          v18 = -2147418113;
LABEL_93:
          v17 = EFS_TRACE_ERROR;
          goto LABEL_28;
        }
      }
    }
  }
LABEL_30:
  CDplUser::UserSvcUnlock(this, v42);
  if ( v53 )
    DplibMemFree(v53);
  v53 = 0;
  if ( v54 )
    DplibMemFree(v54);
  v54 = 0;
  if ( v50 )
    DplibMemFree(v50);
  if ( v5 )
    DplibMemFree(v5);
  if ( v6 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v6);
  }
  if ( hInternet )
    WinHttpCloseHandle(hInternet);
  if ( v56 )
    WinHttpCloseHandle(v56);
  if ( v7 )
    WinHttpCloseHandle(v7);
  if ( v8 )
    DplibMemFree(v8);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v43 )
    RevertToSelf();
  if ( hToken )
  {
    CloseHandle(hToken);
    hToken = 0;
  }
  CDplServiceImpl::RestoreImpersonation(*((CDplServiceImpl **)this + 6), &v58);
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    IsAutoRecoverySupported,
    40,
    188);
  if ( v60 )
    EventActivityIdControl(4u, &ActivityId);
  v59 = 2;
  if ( (unsigned int)dword_180114250 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180114250, 0x400000000000LL) )
  {
    v50 = (unsigned __int16 *)*((_QWORD *)this + 3);
    v49 = (unsigned __int16 *)"RequestComplete";
    v43 = IsAutoRecoverySupported;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180114250,
      (unsigned int)&unk_180103770,
      (unsigned int)v61,
      v20,
      (__int64)&v49,
      (__int64)&v39,
      (__int64)&v41,
      (__int64)&v50,
      (__int64)&v44,
      (__int64)&v43);
  }
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hEfsCoreTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hEfsCoreTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v59);
  return (unsigned int)IsAutoRecoverySupported;
}

```

## disassembly

```asm
0x1800ab620  mov     [rsp-8+arg_10], rbx
0x1800ab625  push    rbp
0x1800ab626  push    rsi
0x1800ab627  push    rdi
0x1800ab628  push    r12
0x1800ab62a  push    r13
0x1800ab62c  push    r14
0x1800ab62e  push    r15
0x1800ab630  lea     rbp, [rsp-10h]
0x1800ab635  sub     rsp, 110h
0x1800ab63c  mov     rax, cs:__security_cookie
0x1800ab643  xor     rax, rsp
0x1800ab646  mov     [rbp+40h+var_38], rax
0x1800ab64a  xor     ebx, ebx
0x1800ab64c  mov     dword ptr [rsp+140h+lpData], 2F7Bh
0x1800ab654  mov     rdi, rdx
0x1800ab657  mov     [rbp+40h+var_68], rbx
0x1800ab65b  lea     r8, sourceString
0x1800ab662  mov     [rbp+40h+hToken], rbx
0x1800ab666  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800ab66d  mov     [rsp+140h+var_D0], ebx
0x1800ab671  lea     r9d, [rbx+28h]
0x1800ab675  mov     [rsp+140h+var_D8], ebx
0x1800ab679  mov     r14, rcx
0x1800ab67c  mov     [rbp+40h+var_90], rbx
0x1800ab680  mov     [rbp+40h+var_BC], ebx
0x1800ab683  mov     esi, ebx
0x1800ab685  mov     [rbp+40h+var_88], rbx
0x1800ab689  mov     r13d, ebx
0x1800ab68c  mov     [rbp+40h+var_C0], ebx
0x1800ab68f  mov     r15d, ebx
0x1800ab692  mov     [rbp+40h+var_A8], rbx
0x1800ab696  mov     r12d, ebx
0x1800ab699  mov     [rsp+140h+var_CC], ebx
0x1800ab69d  mov     [rsp+140h+var_F0], rbx
0x1800ab6a2  mov     [rbp+40h+lpMem], rbx
0x1800ab6a6  mov     [rbp+40h+hInternet], rbx
0x1800ab6aa  mov     [rbp+40h+var_78], rbx
0x1800ab6ae  mov     [rbp+40h+var_98], rbx
0x1800ab6b2  mov     [rbp+40h+hKey], rbx
0x1800ab6b6  mov     qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x1800ab6bb  mov     [rsp+140h+Data], rbx
0x1800ab6c0  mov     [rbp+40h+var_B0], rbx
0x1800ab6c4  mov     [rsp+140h+var_D4], ebx
0x1800ab6c8  mov     [rsp+140h+var_E8], ebx
0x1800ab6cc  mov     [rbp+40h+var_60], ebx
0x1800ab6cf  mov     [rbp+40h+var_5C], bl
0x1800ab6d2  call    fnEfsLogTrace1Strings
0x1800ab6d7  lea     rcx, [rbp+40h+var_60]
0x1800ab6db  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hEfsCoreTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hEfsCoreTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x1800ab6e0  mov     eax, cs:dword_180114250
0x1800ab6e6  cmp     eax, 5
0x1800ab6e9  jbe     short loc_1800AB735
0x1800ab6eb  mov     rdx, 400000000000h
0x1800ab6f5  lea     rcx, dword_180114250
0x1800ab6fc  call    _tlgKeywordOn
0x1800ab701  test    al, al
0x1800ab703  jz      short loc_1800AB735
0x1800ab705  cmp     [rbp+40h+var_5C], bl
0x1800ab708  jz      short loc_1800AB71B
0x1800ab70a  lea     rcx, [rbp+40h+ActivityId]; struct _GUID *
0x1800ab70e  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800ab713  lea     r9, [rbp+40h+ActivityId]
0x1800ab717  test    al, al
0x1800ab719  jz      short loc_1800AB71E
0x1800ab71b  mov     r9, rbx
0x1800ab71e  lea     r8, [rbp+40h+var_58]
0x1800ab722  lea     rdx, word_18010393A
0x1800ab729  lea     rcx, dword_180114250
0x1800ab730  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800ab735  test    rdi, rdi
0x1800ab738  jnz     short loc_1800AB76B
0x1800ab73a  mov     ebx, 80070057h
0x1800ab73f  mov     dword ptr [rsp+140h+lpData], 2F83h
0x1800ab747  mov     r8d, 80070057h
0x1800ab74d  mov     rcx, cs:g_hPublisher
0x1800ab754  lea     rdx, EFS_TRACE_ERROR
0x1800ab75b  mov     r9d, 28h ; '('
0x1800ab761  call    fnEfsLogTrace1
0x1800ab766  jmp     loc_1800AB9A8
0x1800ab76b  cmp     [rdi+0CCh], ebx
0x1800ab771  jnz     loc_1800AC1C1
0x1800ab777  lea     rcx, [rsp+140h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800ab77c  call    cs:__imp_GetSystemTimeAsFileTime
0x1800ab782  mov     eax, [rsp+140h+SystemTimeAsFileTime.dwHighDateTime]
0x1800ab786  mov     rcx, [rdi+8]
0x1800ab78a  mov     dword ptr [rsp+140h+Data+4], eax
0x1800ab78e  mov     eax, [rsp+140h+SystemTimeAsFileTime.dwLowDateTime]
0x1800ab792  mov     dword ptr [rsp+140h+Data], eax
0x1800ab796  cmp     [r14+18h], rcx
0x1800ab79a  jnb     loc_1800AB9A8
0x1800ab7a0  mov     rax, [rdi+0D8h]
0x1800ab7a7  test    rax, rax
0x1800ab7aa  jz      short loc_1800AB7C4
0x1800ab7ac  mov     rdx, 861C46800h
0x1800ab7b6  add     rax, rdx
0x1800ab7b9  cmp     rax, [rsp+140h+Data]
0x1800ab7be  ja      loc_1800AB9A8
0x1800ab7c4  cmp     [rdi+0C8h], ebx
0x1800ab7ca  jz      short loc_1800AB7D5
0x1800ab7cc  mov     [r14+18h], rcx
0x1800ab7d0  jmp     loc_1800AB9A8
0x1800ab7d5  mov     r9d, 28h ; '('
0x1800ab7db  mov     dword ptr [rsp+140h+lpData], 2FB3h
0x1800ab7e3  lea     r8, sourceString
0x1800ab7ea  lea     rdx, EFS_TRACE_START_EVENT
0x1800ab7f1  call    fnEfsLogTrace1Strings
0x1800ab7f6  mov     rcx, [r14+30h]; this
0x1800ab7fa  lea     rdx, [rbp+40h+var_68]; void **
0x1800ab7fe  call    ?RevertToSelf@CDplServiceImpl@@AEAAJPEAPEAX@Z; CDplServiceImpl::RevertToSelf(void * *)
0x1800ab803  mov     rcx, cs:g_hPublisher
0x1800ab80a  lea     r9, sourceString
0x1800ab811  mov     dword ptr [rsp+140h+var_110], 2FB3h
0x1800ab819  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800ab820  mov     [rsp+140h+cbData], 28h ; '('
0x1800ab828  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800ab82f  mov     dword ptr [rsp+140h+lpData], eax
0x1800ab833  mov     ebx, eax
0x1800ab835  call    fnEfsLogTrace1String1Dword
0x1800ab83a  test    eax, eax
0x1800ab83c  js      loc_1800AB9A8
0x1800ab842  mov     r9d, 28h ; '('
0x1800ab848  mov     dword ptr [rsp+140h+lpData], 2FB9h
0x1800ab850  lea     r8, sourceString
0x1800ab857  lea     rdx, EFS_TRACE_START_EVENT
0x1800ab85e  call    fnEfsLogTrace1Strings
0x1800ab863  mov     rcx, [r14+68h]; unsigned __int16 *
0x1800ab867  lea     rdx, [rbp+40h+hToken]; void **
0x1800ab86b  call    ?EdpCredSvcQuerySessionUserTokenBySid@@YAJPEBGPEAPEAX@Z; EdpCredSvcQuerySessionUserTokenBySid(ushort const *,void * *)
0x1800ab870  mov     rcx, cs:g_hPublisher
0x1800ab877  lea     r9, sourceString
0x1800ab87e  mov     dword ptr [rsp+140h+var_110], 2FB9h
0x1800ab886  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800ab88d  mov     [rsp+140h+cbData], 28h ; '('
0x1800ab895  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800ab89c  mov     dword ptr [rsp+140h+lpData], eax
0x1800ab8a0  mov     ebx, eax
0x1800ab8a2  call    fnEfsLogTrace1String1Dword
0x1800ab8a7  test    eax, eax
0x1800ab8a9  js      loc_1800AB9A8
0x1800ab8af  mov     rcx, [rbp+40h+hToken]; hToken
0x1800ab8b3  test    rcx, rcx
0x1800ab8b6  jnz     short loc_1800AB8D0
0x1800ab8b8  mov     ebx, 800703F0h
0x1800ab8bd  mov     dword ptr [rsp+140h+lpData], 2FBFh
0x1800ab8c5  mov     r8d, 800703F0h
0x1800ab8cb  jmp     loc_1800AB74D
0x1800ab8d0  call    cs:__imp_ImpersonateLoggedOnUser
0x1800ab8d6  mov     [rsp+140h+var_D0], eax
0x1800ab8da  test    eax, eax
0x1800ab8dc  jnz     short loc_1800AB903
0x1800ab8de  call    cs:__imp_GetLastError
0x1800ab8e4  mov     ebx, eax
0x1800ab8e6  test    eax, eax
0x1800ab8e8  jle     short loc_1800AB8F3
0x1800ab8ea  movzx   ebx, ax
0x1800ab8ed  or      ebx, 80070000h
0x1800ab8f3  mov     dword ptr [rsp+140h+lpData], 2FC5h
0x1800ab8fb  mov     r8d, ebx
0x1800ab8fe  jmp     loc_1800AB74D
0x1800ab903  mov     r9d, 28h ; '('
0x1800ab909  mov     dword ptr [rsp+140h+lpData], 2FCEh
0x1800ab911  lea     r8, sourceString
0x1800ab918  lea     rdx, EFS_TRACE_START_EVENT
0x1800ab91f  call    fnEfsLogTrace1Strings
0x1800ab924  mov     rdx, [rdi+40h]; unsigned __int16 *
0x1800ab928  lea     r8, [rsp+140h+var_D8]; int *
0x1800ab92d  mov     rcx, r14; this
0x1800ab930  call    ?IsAutoRecoverySupported@CDplUser@@AEAAJPEBGPEAH@Z; CDplUser::IsAutoRecoverySupported(ushort const *,int *)
0x1800ab935  mov     rcx, cs:g_hPublisher
0x1800ab93c  lea     r9, sourceString
0x1800ab943  mov     dword ptr [rsp+140h+var_110], 2FCEh
0x1800ab94b  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800ab952  mov     [rsp+140h+cbData], 28h ; '('
0x1800ab95a  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800ab961  mov     dword ptr [rsp+140h+lpData], eax
0x1800ab965  mov     ebx, eax
0x1800ab967  call    fnEfsLogTrace1String1Dword
0x1800ab96c  test    eax, eax
0x1800ab96e  js      short loc_1800AB9A8
0x1800ab970  cmp     [rsp+140h+var_D8], esi
0x1800ab974  jnz     loc_1800ABBBE
0x1800ab97a  mov     dword ptr [rsp+140h+lpData], 2FD6h
0x1800ab982  mov     esi, 1
0x1800ab987  lea     rdx, EFS_TRACE_STATUS
0x1800ab98e  mov     ebx, esi
0x1800ab990  mov     r8d, esi
0x1800ab993  lea     r9d, [rsi+27h]
0x1800ab997  mov     rcx, cs:g_hPublisher
0x1800ab99e  call    fnEfsLogTrace1
0x1800ab9a3  mov     rsi, [rsp+140h+var_F0]
0x1800ab9a8  mov     edx, [rsp+140h+var_D4]; int
0x1800ab9ac  mov     rcx, r14; this
0x1800ab9af  call    ?UserSvcUnlock@CDplUser@@AEAAHH@Z; CDplUser::UserSvcUnlock(int)
0x1800ab9b4  mov     rcx, [rbp+40h+var_90]; void *
0x1800ab9b8  test    rcx, rcx
0x1800ab9bb  jz      short loc_1800AB9C2
0x1800ab9bd  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x1800ab9c2  mov     rcx, [rbp+40h+var_88]; void *
0x1800ab9c6  mov     [rbp+40h+var_90], 0
0x1800ab9ce  test    rcx, rcx
0x1800ab9d1  jz      short loc_1800AB9D8
0x1800ab9d3  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x1800ab9d8  mov     rcx, [rbp+40h+var_A8]; void *
0x1800ab9dc  mov     [rbp+40h+var_88], 0
0x1800ab9e4  test    rcx, rcx
0x1800ab9e7  jz      short loc_1800AB9EE
0x1800ab9e9  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x1800ab9ee  test    rsi, rsi
0x1800ab9f1  jz      short loc_1800AB9FB
0x1800ab9f3  mov     rcx, rsi; void *
0x1800ab9f6  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x1800ab9fb  xor     esi, esi
0x1800ab9fd  test    r13, r13
0x1800aba00  jz      short loc_1800ABA16
0x1800aba02  call    cs:__imp_GetProcessHeap
0x1800aba08  mov     r8, r13; lpMem
0x1800aba0b  xor     edx, edx; dwFlags
0x1800aba0d  mov     rcx, rax; hHeap
0x1800aba10  call    cs:__imp_HeapFree
0x1800aba16  mov     rcx, [rbp+40h+hInternet]; hInternet
0x1800aba1a  test    rcx, rcx
0x1800aba1d  jz      short loc_1800ABA25
0x1800aba1f  call    cs:__imp_WinHttpCloseHandle
0x1800aba25  mov     rcx, [rbp+40h+var_78]; hInternet
0x1800aba29  test    rcx, rcx
0x1800aba2c  jz      short loc_1800ABA34
0x1800aba2e  call    cs:__imp_WinHttpCloseHandle
0x1800aba34  test    r15, r15
0x1800aba37  jz      short loc_1800ABA42
0x1800aba39  mov     rcx, r15; hInternet
0x1800aba3c  call    cs:__imp_WinHttpCloseHandle
0x1800aba42  test    r12, r12
0x1800aba45  jz      short loc_1800ABA4F
0x1800aba47  mov     rcx, r12; void *
0x1800aba4a  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x1800aba4f  mov     rcx, [rbp+40h+hKey]; hKey
0x1800aba53  test    rcx, rcx
0x1800aba56  jz      short loc_1800ABA62
0x1800aba58  call    cs:__imp_RegCloseKey
0x1800aba5e  mov     [rbp+40h+hKey], rsi
0x1800aba62  cmp     [rsp+140h+var_D0], esi
0x1800aba66  jz      short loc_1800ABA6E
0x1800aba68  call    cs:__imp_RevertToSelf
0x1800aba6e  mov     rcx, [rbp+40h+hToken]; hObject
0x1800aba72  test    rcx, rcx
0x1800aba75  jz      short loc_1800ABA81
0x1800aba77  call    cs:__imp_CloseHandle
0x1800aba7d  mov     [rbp+40h+hToken], rsi
0x1800aba81  mov     rcx, [r14+30h]; this
0x1800aba85  lea     rdx, [rbp+40h+var_68]; void **
0x1800aba89  call    ?RestoreImpersonation@CDplServiceImpl@@AEAAXPEAPEAX@Z; CDplServiceImpl::RestoreImpersonation(void * *)
0x1800aba8e  mov     rcx, cs:g_hPublisher
0x1800aba95  lea     r9, sourceString
0x1800aba9c  mov     dword ptr [rsp+140h+var_110], 30BCh
0x1800abaa4  lea     r8, EFS_TRACE_LEAVE_HR_EVENT_ERROR
0x1800abaab  mov     [rsp+140h+cbData], 28h ; '('
0x1800abab3  lea     rdx, EFS_TRACE_LEAVE_HR_EVENT
0x1800ababa  mov     dword ptr [rsp+140h+lpData], ebx
0x1800ababe  call    fnEfsLogTrace1String1Dword
0x1800abac3  cmp     [rbp+40h+var_5C], sil
0x1800abac7  jz      short loc_1800ABAD8
0x1800abac9  lea     rdx, [rbp+40h+ActivityId]; ActivityId
0x1800abacd  mov     ecx, 4; ControlCode
0x1800abad2  call    cs:__imp_EventActivityIdControl
0x1800abad8  mov     eax, cs:dword_180114250
0x1800abade  mov     [rbp+40h+var_60], 2
0x1800abae5  cmp     eax, 5
0x1800abae8  jbe     loc_1800ABB8C
0x1800abaee  mov     rdx, 400000000000h
0x1800abaf8  lea     rcx, dword_180114250
0x1800abaff  call    _tlgKeywordOn
0x1800abb04  test    al, al
0x1800abb06  jz      loc_1800ABB8C
0x1800abb0c  mov     eax, [rsp+140h+var_CC]
0x1800abb10  lea     r8, [rbp+40h+var_58]
0x1800abb14  mov     [rsp+140h+var_CC], eax
0x1800abb18  lea     rdx, unk_180103770
0x1800abb1f  mov     rax, [r14+18h]
0x1800abb23  lea     rcx, dword_180114250
0x1800abb2a  mov     [rbp+40h+var_A8], rax
0x1800abb2e  mov     eax, [rsp+140h+var_D8]
0x1800abb32  mov     [rsp+140h+var_D8], eax
0x1800abb36  mov     eax, [rsp+140h+var_E8]
0x1800abb3a  mov     [rsp+140h+var_E8], eax
0x1800abb3e  lea     rax, aRequestcomplet; "RequestComplete"
0x1800abb45  mov     [rbp+40h+var_B0], rax
0x1800abb49  lea     rax, [rsp+140h+var_D0]
0x1800abb4e  mov     [rsp+140h+var_F8], rax
0x1800abb53  lea     rax, [rsp+140h+var_CC]
0x1800abb58  mov     [rsp+140h+var_100], rax
0x1800abb5d  lea     rax, [rbp+40h+var_A8]
0x1800abb61  mov     [rsp+140h+var_108], rax
0x1800abb66  lea     rax, [rsp+140h+var_D8]
0x1800abb6b  mov     [rsp+140h+var_110], rax
0x1800abb70  lea     rax, [rsp+140h+var_E8]
0x1800abb75  mov     qword ptr [rsp+140h+cbData], rax
0x1800abb7a  lea     rax, [rbp+40h+var_B0]
0x1800abb7e  mov     [rsp+140h+lpData], rax
0x1800abb83  mov     [rsp+140h+var_D0], ebx
  ... truncated ...
```
