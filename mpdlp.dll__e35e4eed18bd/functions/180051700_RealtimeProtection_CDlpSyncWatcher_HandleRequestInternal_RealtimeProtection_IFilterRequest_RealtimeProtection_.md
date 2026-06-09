# RealtimeProtection::CDlpSyncWatcher::HandleRequestInternal(RealtimeProtection::IFilterRequest *,RealtimeProtection::IFilterReply *)

- ea: `0x180051700`
- end: `0x18005218e`
- name: `?HandleRequestInternal@CDlpSyncWatcher@RealtimeProtection@@AEAAJPEAUIFilterRequest@2@PEAUIFilterReply@2@@Z`
- size: `2702`
- prototype: `__int64 __fastcall(RealtimeProtection::CDlpSyncWatcher *__hidden this, struct RealtimeProtection::IFilterRequest *, struct RealtimeProtection::IFilterReply *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18015e8d0`

## callees

- `0x180046d10`
- `0x180051700`
- `0x180052190`
- `0x180052b30`
- `0x180053080`
- `0x180053870`
- `0x18005c2a0`
- `0x1800809d0`
- `0x1800a8f30`
- `0x180101af8`
- `0x180105e54`
- `0x180105f50`
- `0x18010cb40`
- `0x18010d47c`
- `0x18015d2cc`
- `0x18015d758`
- `0x18023a290`

## import_xrefs

- `MpClient!MpClientUtilExportFunctions` at `0x180051a26`
- `MpClient!MpClientUtilExportFunctions` at `0x180051a26`
- `KERNEL32!GetCurrentThread` at `0x18005182e`
- `KERNEL32!GetCurrentThread` at `0x180051a88`
- `KERNEL32!GetCurrentThread` at `0x180051ac8`
- `KERNEL32!GetCurrentThread` at `0x180051bcb`
- `KERNEL32!GetCurrentThread` at `0x180051c7e`
- `KERNEL32!GetCurrentThread` at `0x18005182e`
- `KERNEL32!GetCurrentThread` at `0x180051a88`
- `KERNEL32!GetCurrentThread` at `0x180051ac8`
- `KERNEL32!GetCurrentThread` at `0x180051bcb`
- `KERNEL32!GetCurrentThread` at `0x180051c7e`

## string_xrefs

- `0x180051a32`: `MpRtp_SkipThreadPriorityRestore`
- `0x180051dba`: `GetThreadInformation`
- `0x180051ec8`: `GetThreadInformation`
- `0x18005204b`: `GetThreadInformation`
- `0x180052103`: `GetThreadInformation`
- `0x180051ddb`: `SetThreadInformation`
- `0x180051eeb`: `SetThreadInformation`
- `0x180052071`: `SetThreadInformation`
- `0x180052128`: `SetThreadInformation`
- `0x180052037`: `[DLP] RevertPrioritySkippedDueToMiscConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RealtimeProtection::CDlpSyncWatcher::HandleRequestInternal(
        RealtimeProtection::CDlpSyncWatcher *this,
        struct RealtimeProtection::IFilterRequest *a2,
        struct RealtimeProtection::IFilterReply *a3)
{
  struct RealtimeProtection::IFilterRequest *v4; // rsi
  int LastFailure; // ebx
  char *v6; // rax
  char *v7; // r14
  __int16 v8; // r12
  __int64 v9; // r9
  struct _MP_SCAN_FILE_REQUEST *v10; // rdx
  const char *v11; // r8
  int *v12; // r9
  const char *v13; // r8
  bool v14; // r9
  unsigned int (__fastcall *v15)(HANDLE, __int64, unsigned int *, __int64); // rbx
  HANDLE v16; // rax
  int LoadedKernel32ProcAddress; // eax
  __int64 v18; // rcx
  __int64 v19; // r8
  int v20; // r15d
  char *v21; // rbx
  int v22; // r9d
  __int64 v23; // r10
  int v24; // r11d
  __int64 v25; // rsi
  int v26; // r14d
  char *v27; // r15
  int v28; // r12d
  int v29; // r13d
  __int64 v30; // rax
  char *v31; // r8
  int v32; // eax
  int v33; // esi
  __int64 v34; // rax
  const char *v35; // r8
  bool v36; // r9
  __int64 (__fastcall *v37)(HANDLE, __int64, unsigned int *, __int64); // rbx
  HANDLE v38; // rax
  int v39; // eax
  int v40; // r14d
  HANDLE v41; // rax
  int v42; // ebx
  __int128 v43; // xmm2
  __int64 v44; // xmm0_8
  int v45; // eax
  HANDLE CurrentThread; // rbx
  const char *v48; // r8
  bool v49; // r9
  __int64 (__fastcall *v50)(HANDLE, __int64, unsigned int *, __int64); // rbx
  HANDLE v51; // rax
  int v52; // eax
  __int64 v53; // rcx
  char ThreadPriority; // al
  int v55; // edx
  int v56; // ecx
  int v57; // eax
  int v58; // eax
  char v59; // al
  int v60; // edx
  int v61; // ecx
  unsigned int v62; // eax
  char v63; // al
  int v64; // edx
  int v65; // ecx
  int v66; // eax
  int v67; // eax
  int *v68; // [rsp+20h] [rbp-F0h]
  __int16 v69; // [rsp+90h] [rbp-80h]
  unsigned int v70; // [rsp+94h] [rbp-7Ch]
  int v71; // [rsp+9Ch] [rbp-74h]
  __int128 v72; // [rsp+A0h] [rbp-70h] BYREF
  unsigned int v73; // [rsp+B0h] [rbp-60h] BYREF
  int v74; // [rsp+B8h] [rbp-58h] BYREF
  unsigned int v75; // [rsp+C0h] [rbp-50h] BYREF
  char *v76; // [rsp+C8h] [rbp-48h] BYREF
  _OWORD v77[3]; // [rsp+D0h] [rbp-40h] BYREF
  _BYTE v78[12]; // [rsp+100h] [rbp-10h] BYREF
  int v79; // [rsp+110h] [rbp+0h] BYREF
  const wchar_t *v80; // [rsp+120h] [rbp+10h]
  __int64 v81; // [rsp+128h] [rbp+18h]
  unsigned int *v82; // [rsp+130h] [rbp+20h]
  __int64 v83; // [rsp+138h] [rbp+28h]
  unsigned int *v84; // [rsp+140h] [rbp+30h]
  __int64 v85; // [rsp+148h] [rbp+38h]
  _QWORD *v86; // [rsp+150h] [rbp+40h]
  __int64 v87; // [rsp+158h] [rbp+48h]

  v4 = a2;
  memset((char *)v77 + 4, 0, 40);
  LastFailure = 0;
  if ( a2 )
  {
    if ( *(void ***)a2 != &RealtimeProtection::CFileFilterRequest::`vftable'{for `RealtimeProtection::IFilterRequest'} )
      _castguard_check_failure_fastfail(*(_QWORD *)a2);
  }
  else
  {
    v4 = 0;
  }
  v6 = (char *)*((_QWORD *)v4 + 7);
  v7 = (char *)v4 + 72;
  if ( v6 )
  {
    v8 = *((_WORD *)v6 + 9);
    v9 = *((unsigned int *)v6 + 7);
  }
  else
  {
    v8 = *((_WORD *)v4 + 45);
    v9 = *((unsigned int *)v4 + 25);
    v6 = (char *)v4 + 72;
  }
  v69 = v8;
  if ( (int)v9 >= 8 || *((int *)v6 + 6) < 2 )
  {
    if ( *((_DWORD *)v6 + 6) )
    {
      if ( *((_DWORD *)v6 + 6) == 1 && (int)v9 < 5 )
        v9 = 5;
    }
    else if ( (int)v9 < 4 )
    {
      v9 = 4;
    }
  }
  else
  {
    v9 = 8;
  }
  v73 = v9;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_658ae26af5033c3314d8787140215a40_Traceguids, v9);
  v71 = 0;
  if ( !(unsigned int)MpIsWindows8OrGreater() )
  {
    v70 = 0;
    goto LABEL_14;
  }
  if ( qword_1803135B0
    || (LOBYTE(v11) = 1,
        LastFailure = CommonUtil::UtilRawGetLoadedKernel32ProcAddress(
                        (CommonUtil *)&qword_1803135B0,
                        (__int64 (**)(void))"GetThreadInformation",
                        v11,
                        (bool)v12),
        LastFailure >= 0) )
  {
    if ( qword_1803135A8
      || (LOBYTE(v11) = 1,
          LastFailure = CommonUtil::UtilRawGetLoadedKernel32ProcAddress(
                          (CommonUtil *)&qword_1803135A8,
                          (__int64 (**)(void))"SetThreadInformation",
                          v11,
                          (bool)v12),
          LastFailure >= 0) )
    {
      CurrentThread = GetCurrentThread();
      v75 = 0;
      if ( !(unsigned int)qword_1803135B0(CurrentThread, 1, &v75, 4) )
      {
        LastFailure = HrGetLastFailure();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            WPP_658ae26af5033c3314d8787140215a40_Traceguids,
            (unsigned int)LastFailure);
        v70 = 0;
        goto LABEL_58;
      }
      v70 = v75;
      if ( v75 == v73 )
      {
        v70 = 0;
      }
      else
      {
        if ( !(unsigned int)qword_1803135A8(CurrentThread, 1, &v73, 4) )
        {
          LastFailure = HrGetLastFailure();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              WPP_658ae26af5033c3314d8787140215a40_Traceguids,
              (unsigned int)LastFailure);
          goto LABEL_58;
        }
        v71 = 1;
      }
      LastFailure = 0;
LABEL_58:
      v69 = v8;
      goto LABEL_14;
    }
  }
  v70 = 0;
LABEL_14:
  if ( LastFailure < 0 )
  {
    if ( (Microsoft_Antimalware_RTPEnableBits & 1) != 0 )
    {
      ThreadPriority = UtilGetThreadPriority();
      McTemplateU0zqqq_EventWriteTransfer(
        v56,
        v55,
        (unsigned int)L"[DLP] AdjustedPriorityError",
        v70,
        LastFailure,
        ThreadPriority);
    }
  }
  else if ( (Microsoft_Antimalware_RTPEnableBits & 1) != 0 )
  {
    if ( (unsigned int)MpIsWindows8OrGreater() )
    {
      if ( qword_1803135B0
        || (LOBYTE(v13) = 1,
            LoadedKernel32ProcAddress = CommonUtil::UtilRawGetLoadedKernel32ProcAddress(
                                          (CommonUtil *)&qword_1803135B0,
                                          (__int64 (**)(void))"GetThreadInformation",
                                          v13,
                                          v14),
            LoadedKernel32ProcAddress >= 0) )
      {
        if ( qword_1803135A8
          || (LOBYTE(v13) = 1,
              LoadedKernel32ProcAddress = CommonUtil::UtilRawGetLoadedKernel32ProcAddress(
                                            (CommonUtil *)&qword_1803135A8,
                                            (__int64 (**)(void))"SetThreadInformation",
                                            v13,
                                            v14),
              LoadedKernel32ProcAddress >= 0) )
        {
          v73 = 0;
          v15 = (unsigned int (__fastcall *)(HANDLE, __int64, unsigned int *, __int64))qword_1803135B0;
          v16 = GetCurrentThread();
          v69 = v8;
          if ( v15(v16, 1, &v73, 4) )
            LoadedKernel32ProcAddress = v73;
          else
            LoadedKernel32ProcAddress = 0;
        }
      }
    }
    else
    {
      LoadedKernel32ProcAddress = 0;
    }
    LODWORD(v76) = LoadedKernel32ProcAddress;
    v75 = (*(__int64 (__fastcall **)(struct RealtimeProtection::IFilterRequest *))(*(_QWORD *)v4 + 72LL))(v4);
    v73 = v70;
    v80 = L"[DLP] AdjustedPriorityOK";
    v81 = 50;
    v82 = &v73;
    v83 = 4;
    v84 = &v75;
    v85 = 4;
    v86 = &v76;
    v87 = 4;
    v68 = &v79;
    McGenEventWrite_EventWriteTransfer(v18, RTPPriorityEvent, v19, 5);
  }
  v74 = -1073741823;
  v20 = -2147467259;
  LODWORD(v77[0]) = 2884005;
  if ( v8 != 4 )
  {
    if ( v8 == 5 )
    {
      if ( *((_QWORD *)v4 + 7) )
        v7 = (char *)*((_QWORD *)v4 + 7);
      v58 = RealtimeProtection::DlpFilterSyncMessageHandler::HandleDlpOperationCheckRequest(
              (RealtimeProtection::DlpFilterSyncMessageHandler *)(v7 + 16),
              (struct _MP_SCAN_FILE_REQUEST *const)&v77[1],
              (enum MpDlpResultAccessDecision *)((char *)&v77[1] + 4),
              (enum MpDlpResultAccessReason *)&v74,
              v68);
    }
    else if ( v8 == 6 )
    {
      if ( *((_QWORD *)v4 + 7) )
        v7 = (char *)*((_QWORD *)v4 + 7);
      v58 = RealtimeProtection::DlpFilterSyncMessageHandler::HandleDlpAtomicFileAccessAndOperationCheckRequest(
              (RealtimeProtection::DlpFilterSyncMessageHandler *)(v7 + 16),
              (struct _MP_SCAN_FILE_REQUEST *const)&v77[1],
              (enum MpDlpResultAccessDecision *)((char *)&v77[1] + 4),
              (enum MpDlpResultAccessReason *)&v74,
              v68);
    }
    else
    {
      if ( v69 != 7 )
        goto LABEL_30;
      if ( *((_QWORD *)v4 + 7) )
        v7 = (char *)*((_QWORD *)v4 + 7);
      v58 = RealtimeProtection::DlpFilterSyncMessageHandler::HandleDlpServiceMessageRequest(
              (RealtimeProtection::DlpFilterSyncMessageHandler *)(v7 + 16),
              (struct _MP_DLP_SERVICE_REQUEST_MESSAGE_HEADER *const)&v77[1],
              (struct _MP_DLP_SERVICE_REPLY_MESSAGE *)&v74,
              v12);
    }
    v20 = v58;
    goto LABEL_30;
  }
  if ( *((_QWORD *)v4 + 7) )
    v7 = (char *)*((_QWORD *)v4 + 7);
  v21 = v7 + 16;
  v74 = 0;
  v20 = RealtimeProtection::DlpFilterSyncMessageHandler::ValidateDlpFileAccessCheckRequest(
          (RealtimeProtection::DlpFilterSyncMessageHandler *)(v7 + 16),
          v10);
  if ( v20 < 0 )
  {
    v74 = -1073741811;
    goto LABEL_30;
  }
  *(_QWORD *)&v78[4] = 0;
  *(_DWORD *)&v78[8] = *((_DWORD *)v7 + 28);
  *(_QWORD *)v78 = *((_QWORD *)v7 + 6);
  v22 = *((_DWORD *)v7 + 41);
  v23 = (__int64)&v7[*((_QWORD *)v7 + 13) + 16];
  v24 = *((_DWORD *)v7 + 44);
  v25 = (__int64)&v7[*((_QWORD *)v7 + 12) + 16];
  v26 = *((_DWORD *)v7 + 43);
  v27 = &v21[*((_QWORD *)v21 + 8)];
  v28 = *((_DWORD *)v21 + 36);
  v29 = *((_DWORD *)v21 + 32);
  v30 = *((_QWORD *)v21 + 15);
  v76 = &v21[*((_QWORD *)v21 + 5)];
  if ( *((_DWORD *)v21 + 35) )
    v31 = &v21[*((_QWORD *)v21 + 7)];
  else
    v31 = 0;
  v72 = *(_OWORD *)(v21 + 104);
  v32 = Dlp::Engine::Interop::CheckAccessForFile(
          *((unsigned int *)v21 + 6),
          &v21[*((_QWORD *)v21 + 6)],
          v31,
          v76,
          v78,
          *((_DWORD *)v21 + 25),
          &v72,
          v30,
          v29,
          v28,
          v27,
          v26,
          v25,
          v24,
          v23,
          v22,
          &v77[1],
          (char *)&v77[1] + 4);
  v20 = v32;
  if ( v32 >= 0 )
  {
    v20 = 0;
LABEL_30:
    v33 = -2147024809;
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      56,
      &WPP_ddb2fdf8fd7c3cc2f50b1c32e633aabe_Traceguids,
      (unsigned int)v32);
  v33 = -2147024809;
  if ( v20 == -2147483634 )
  {
    v74 = -1073741816;
  }
  else if ( v20 == -2147024809 )
  {
    v74 = -1073741811;
  }
  else
  {
    v57 = -1073741823;
    if ( v20 == -2147024882 )
      v57 = -1073741670;
    v74 = v57;
  }
LABEL_31:
  v73 = 0;
  v34 = MpClientUtilExportFunctions();
  if ( (*(int (__fastcall **)(const wchar_t *, _QWORD, unsigned int *))(v34 + 160))(
         L"MpRtp_SkipThreadPriorityRestore",
         0,
         &v73) < 0
    || !v73 )
  {
    if ( (unsigned int)MpIsWindows8OrGreater() )
    {
      if ( qword_1803135B0
        || (LOBYTE(v35) = 1,
            v40 = CommonUtil::UtilRawGetLoadedKernel32ProcAddress(
                    (CommonUtil *)&qword_1803135B0,
                    (__int64 (**)(void))"GetThreadInformation",
                    v35,
                    v36),
            v40 >= 0) )
      {
        if ( qword_1803135A8
          || (LOBYTE(v35) = 1,
              v40 = CommonUtil::UtilRawGetLoadedKernel32ProcAddress(
                      (CommonUtil *)&qword_1803135A8,
                      (__int64 (**)(void))"SetThreadInformation",
                      v35,
                      v36),
              v40 >= 0) )
        {
          v73 = 0;
          v37 = (__int64 (__fastcall *)(HANDLE, __int64, unsigned int *, __int64))qword_1803135B0;
          v38 = GetCurrentThread();
          v39 = v37(v38, 1, &v73, 4);
          v40 = v73;
          if ( !v39 )
            v40 = 0;
        }
      }
    }
    else
    {
      v40 = 0;
    }
    if ( v71 )
    {
      if ( !qword_1803135A8 )
        goto LABEL_42;
      v41 = GetCurrentThread();
      LODWORD(v76) = v70;
      if ( !(unsigned int)qword_1803135A8(v41, 1, &v76, 4) )
      {
        v62 = HrGetLastFailure();
        v33 = v62;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_658ae26af5033c3314d8787140215a40_Traceguids, v62);
        goto LABEL_42;
      }
    }
    v33 = 0;
LABEL_42:
    if ( v33 < 0 )
    {
      if ( (Microsoft_Antimalware_RTPEnableBits & 1) != 0 )
      {
        v63 = UtilGetThreadPriority();
        McTemplateU0zqqq_EventWriteTransfer(v65, v64, (unsigned int)L"[DLP] RevertPriorityError", v40, v33, v63);
      }
    }
    else if ( (Microsoft_Antimalware_RTPEnableBits & 1) != 0 )
    {
      if ( (unsigned int)MpIsWindows8OrGreater() )
      {
        if ( qword_1803135B0
          || (LOBYTE(v48) = 1,
              v66 = CommonUtil::UtilRawGetLoadedKernel32ProcAddress(
                      (CommonUtil *)&qword_1803135B0,
                      (__int64 (**)(void))"GetThreadInformation",
                      v48,
                      v49),
              v53 = (unsigned int)v66,
              v66 >= 0) )
        {
          if ( qword_1803135A8
            || (LOBYTE(v48) = 1,
                v67 = CommonUtil::UtilRawGetLoadedKernel32ProcAddress(
                        (CommonUtil *)&qword_1803135A8,
                        (__int64 (**)(void))"SetThreadInformation",
                        v48,
                        v49),
                v53 = (unsigned int)v67,
                v67 >= 0) )
          {
            v73 = 0;
            v50 = (__int64 (__fastcall *)(HANDLE, __int64, unsigned int *, __int64))qword_1803135B0;
            v51 = GetCurrentThread();
            v52 = v50(v51, 1, &v73, 4);
            v53 = v73;
            if ( !v52 )
              v53 = 0;
          }
        }
      }
      else
      {
        v53 = 0;
      }
      v75 = v53;
      v73 = v70;
      LODWORD(v76) = v40;
      v80 = L"[DLP] RevertPriorityOK";
      v81 = 46;
      v82 = (unsigned int *)&v76;
      v83 = 4;
      v84 = &v73;
      v85 = 4;
      v86 = &v75;
      v87 = 4;
      McGenEventWrite_EventWriteTransfer(v53, RTPPriorityEvent, v48, 5);
    }
    goto LABEL_44;
  }
  if ( (Microsoft_Antimalware_RTPEnableBits & 1) != 0 )
  {
    v59 = UtilGetThreadPriority();
    McTemplateU0zqqq_EventWriteTransfer(
      v61,
      v60,
      (unsigned int)L"[DLP] RevertPrioritySkippedDueToMiscConfig",
      0,
      0,
      v59);
  }
LABEL_44:
  v42 = v74;
  if ( (v20 < 0 || v74 < 0)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      WPP_742f2f96c3793b6ec1a2630691659419_Traceguids,
      (unsigned int)v20,
      v74);
  }
  if ( a3 )
  {
    if ( *(void ***)a3 != &RealtimeProtection::CFileFilterReply::`vftable'{for `RealtimeProtection::IFilterReply'} )
      _castguard_check_failure_fastfail(*(_QWORD *)a3);
  }
  else
  {
    a3 = 0;
  }
  *(_DWORD *)(*(__int64 (__fastcall **)(struct RealtimeProtection::IFilterReply *))(*(_QWORD *)a3 + 32LL))(a3) = v42;
  *((_DWORD *)a3 + 38) = 60;
  v43 = v77[1];
  v44 = *(_QWORD *)&v77[2];
  v45 = DWORD2(v77[2]);
  *(_OWORD *)((char *)a3 + 40) = v77[0];
  *(_OWORD *)((char *)a3 + 56) = v43;
  *((_QWORD *)a3 + 9) = v44;
  *((_DWORD *)a3 + 20) = v45;
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180051700  mov     [rsp-8+arg_0], rbx
0x180051705  push    rbp
0x180051706  push    rsi
0x180051707  push    rdi
0x180051708  push    r12
0x18005170a  push    r13
0x18005170c  push    r14
0x18005170e  push    r15
0x180051710  lea     rbp, [rsp-60h]
0x180051715  sub     rsp, 170h
0x18005171c  mov     rax, cs:__security_cookie
0x180051723  xor     rax, rsp
0x180051726  mov     [rbp+90h+var_40], rax
0x18005172a  mov     rdi, r8
0x18005172d  mov     rsi, rdx
0x180051730  xorps   xmm0, xmm0
0x180051733  movdqu  [rbp+90h+var_D0+4], xmm0
0x180051738  xorps   xmm1, xmm1
0x18005173b  movdqu  [rbp+90h+var_BC], xmm1
0x180051740  xor     ebx, ebx
0x180051742  mov     [rbp+90h+var_AC], rbx
0x180051746  test    rdx, rdx
0x180051749  jz      loc_180051DAF
0x18005174f  lea     rcx, ??_7CFileFilterRequest@RealtimeProtection@@6BIFilterRequest@1@@; const RealtimeProtection::CFileFilterRequest::`vftable'{for `RealtimeProtection::IFilterRequest'}
0x180051756  mov     rax, [rdx]
0x180051759  cmp     rax, rcx
0x18005175c  jnz     loc_180051D8C
0x180051762  mov     rax, [rsi+38h]
0x180051766  lea     r14, [rsi+48h]
0x18005176a  test    rax, rax
0x18005176d  jnz     loc_180051D51
0x180051773  movzx   r12d, word ptr [r14+12h]
0x180051778  mov     r9d, [r14+1Ch]
0x18005177c  mov     rax, r14
0x18005177f  mov     [rbp+90h+var_110], r12w
0x180051784  movzx   r15d, r12w
0x180051788  movzx   r13d, r12w
0x18005178c  mov     ecx, 5
0x180051791  cmp     r9d, 8
0x180051795  jge     loc_180051D36
0x18005179b  cmp     dword ptr [rax+18h], 2
0x18005179f  jl      loc_180051D36
0x1800517a5  mov     r9d, 8
0x1800517ab  mov     [rbp+90h+var_F0], r9d
0x1800517af  lea     rax, WPP_GLOBAL_Control
0x1800517b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800517bd  cmp     rcx, rax
0x1800517c0  jz      short loc_1800517CC
0x1800517c2  test    byte ptr [rcx+1Ch], 4
0x1800517c6  jnz     loc_180051D1C
0x1800517cc  mov     [rbp+90h+var_108], rbx
0x1800517d0  call    MpIsWindows8OrGreater
0x1800517d5  test    eax, eax
0x1800517d7  jnz     loc_180051BAF
0x1800517dd  mov     eax, ebx
0x1800517df  mov     [rbp+90h+var_10C], ebx
0x1800517e2  test    ebx, ebx
0x1800517e4  js      loc_180051E96
0x1800517ea  test    cs:Microsoft_Antimalware_RTPEnableBits, 1
0x1800517f1  jz      loc_180051BA8
0x1800517f7  call    MpIsWindows8OrGreater
0x1800517fc  test    eax, eax
0x1800517fe  jz      loc_180051D67
0x180051804  cmp     cs:qword_1803135B0, 0
0x18005180c  jz      loc_180051EC5
0x180051812  cmp     cs:qword_1803135A8, 0
0x18005181a  jz      loc_180051EE8
0x180051820  mov     [rbp+90h+var_F0], 0
0x180051827  mov     rbx, cs:qword_1803135B0
0x18005182e  call    cs:__imp_GetCurrentThread
0x180051834  mov     rcx, rax
0x180051837  mov     r9d, 4
0x18005183d  lea     r8, [rbp+90h+var_F0]
0x180051841  mov     edx, 1
0x180051846  mov     rax, rbx
0x180051849  call    cs:__guard_dispatch_icall_fptr
0x18005184f  mov     [rbp+90h+var_110], r15w
0x180051854  test    eax, eax
0x180051856  jz      loc_180051D99
0x18005185c  mov     eax, [rbp+90h+var_F0]
0x18005185f  xor     ebx, ebx
0x180051861  mov     dword ptr [rbp+90h+var_D8], eax
0x180051864  mov     rax, [rsi]
0x180051867  mov     rcx, rsi
0x18005186a  mov     rax, [rax+48h]
0x18005186e  call    cs:__guard_dispatch_icall_fptr
0x180051874  mov     [rbp+90h+var_E0], eax
0x180051877  mov     eax, [rbp+90h+var_10C]
0x18005187a  mov     [rbp+90h+var_F0], eax
0x18005187d  lea     rax, aDlpAdjustedpri_0; "[DLP] AdjustedPriorityOK"
0x180051884  mov     [rbp+90h+var_80], rax
0x180051888  mov     [rbp+90h+var_78], 32h ; '2'
0x180051890  lea     rax, [rbp+90h+var_F0]
0x180051894  mov     [rbp+90h+var_70], rax
0x180051898  mov     [rbp+90h+var_68], 4
0x1800518a0  lea     rax, [rbp+90h+var_E0]
0x1800518a4  mov     [rbp+90h+var_60], rax
0x1800518a8  mov     [rbp+90h+var_58], 4
0x1800518b0  lea     rax, [rbp+90h+var_D8]
0x1800518b4  mov     [rbp+90h+var_50], rax
0x1800518b8  mov     [rbp+90h+var_48], 4
0x1800518c0  lea     rax, [rbp+90h+var_90]
0x1800518c4  mov     [rsp+1A0h+var_180], rax; int *
0x1800518c9  mov     r9d, 5
0x1800518cf  lea     rdx, RTPPriorityEvent
0x1800518d6  call    McGenEventWrite_EventWriteTransfer
0x1800518db  mov     [rbp+90h+var_E8], 0C0000001h
0x1800518e2  mov     r15d, 80004005h
0x1800518e8  mov     dword ptr [rbp+90h+var_D0], 2C01A5h
0x1800518ef  cmp     r13w, 4
0x1800518f4  jnz     loc_180051F99
0x1800518fa  mov     rax, [rsi+38h]
0x1800518fe  test    rax, rax
0x180051901  cmovnz  r14, rax
0x180051905  lea     rbx, [r14+10h]
0x180051909  mov     [rbp+90h+var_E8], 0
0x180051910  mov     rcx, rbx; this
0x180051913  call    ?ValidateDlpFileAccessCheckRequest@DlpFilterSyncMessageHandler@RealtimeProtection@@YAJQEAU_MP_SCAN_FILE_REQUEST@@@Z; RealtimeProtection::DlpFilterSyncMessageHandler::ValidateDlpFileAccessCheckRequest(_MP_SCAN_FILE_REQUEST * const)
0x180051918  mov     r15d, eax
0x18005191b  test    eax, eax
0x18005191d  js      loc_180051F0B
0x180051923  xor     eax, eax
0x180051925  mov     [rbp+90h+var_9C], rax
0x180051929  mov     eax, [rbx+60h]
0x18005192c  mov     dword ptr [rbp+90h+var_9C+4], eax
0x18005192f  mov     rax, [rbx+20h]
0x180051933  mov     [rbp-10h], rax
0x180051937  mov     r9d, [rbx+94h]
0x18005193e  mov     r10, [rbx+58h]
0x180051942  add     r10, rbx
0x180051945  mov     r11d, [rbx+0A0h]
0x18005194c  mov     rsi, [rbx+50h]
0x180051950  add     rsi, rbx
0x180051953  mov     r14d, [rbx+9Ch]
0x18005195a  mov     r15, [rbx+40h]
0x18005195e  add     r15, rbx
0x180051961  mov     r12d, [rbx+90h]
0x180051968  mov     r13d, [rbx+80h]
0x18005196f  mov     rax, [rbx+78h]
0x180051973  mov     rcx, [rbx+28h]
0x180051977  add     rcx, rbx
0x18005197a  mov     [rbp+90h+var_D8], rcx
0x18005197e  cmp     dword ptr [rbx+8Ch], 0
0x180051985  jnz     loc_180051F19
0x18005198b  xor     r8d, r8d
0x18005198e  movups  xmm0, xmmword ptr [rbx+68h]
0x180051992  movaps  [rbp+90h+var_100], xmm0
0x180051996  mov     rdx, [rbx+30h]
0x18005199a  add     rdx, rbx
0x18005199d  lea     rcx, [rbp+90h+var_BC]
0x1800519a1  mov     [rsp+1A0h+var_118], rcx
0x1800519a9  lea     rcx, [rbp+90h+var_C0]
0x1800519ad  mov     [rsp+1A0h+var_120], rcx
0x1800519b5  mov     [rsp+1A0h+var_128], r9d
0x1800519ba  mov     [rsp+1A0h+var_130], r10
0x1800519bf  mov     [rsp+1A0h+var_138], r11d
0x1800519c4  mov     [rsp+1A0h+var_140], rsi
0x1800519c9  mov     [rsp+1A0h+var_148], r14d
0x1800519ce  mov     [rsp+1A0h+var_150], r15
0x1800519d3  mov     [rsp+1A0h+var_158], r12d
0x1800519d8  mov     [rsp+1A0h+var_160], r13d
0x1800519dd  mov     [rsp+1A0h+var_168], rax
0x1800519e2  lea     rax, [rbp+90h+var_100]
0x1800519e6  mov     [rsp+1A0h+var_170], rax
0x1800519eb  mov     eax, [rbx+64h]
0x1800519ee  mov     [rsp+1A0h+var_178], eax
0x1800519f2  lea     rax, [rbp+90h+var_A0]
0x1800519f6  mov     [rsp+1A0h+var_180], rax
0x1800519fb  mov     r9, [rbp+90h+var_D8]
0x1800519ff  mov     ecx, [rbx+18h]
0x180051a02  call    ?CheckAccessForFile@Interop@Engine@Dlp@@YAJW4DlpFileAccessCheckType@@PEB_W11AEBUPPID@@W4_MP_KNOWN_PROCESS_TYPE@@U_GUID@@T_LARGE_INTEGER@@KKPEAEK6K6KPEAW4MpDlpResultAccessDecision@@PEAW4MpDlpResultAccessReason@@@Z; Dlp::Engine::Interop::CheckAccessForFile(DlpFileAccessCheckType,wchar_t const *,wchar_t const *,wchar_t const *,PPID const &,_MP_KNOWN_PROCESS_TYPE,_GUID,_LARGE_INTEGER,ulong,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,MpDlpResultAccessDecision *,MpDlpResultAccessReason *)
0x180051a07  mov     r15d, eax
0x180051a0a  test    eax, eax
0x180051a0c  js      loc_180051F25
0x180051a12  xor     ebx, ebx
0x180051a14  mov     r15d, ebx
0x180051a17  lea     r12, WPP_GLOBAL_Control
0x180051a1e  mov     esi, 80070057h
0x180051a23  mov     [rbp+90h+var_F0], ebx
0x180051a26  call    cs:__imp_MpClientUtilExportFunctions
0x180051a2c  lea     r8, [rbp+90h+var_F0]
0x180051a30  xor     edx, edx
0x180051a32  lea     rcx, aMprtpSkipthrea; "MpRtp_SkipThreadPriorityRestore"
0x180051a39  mov     rax, [rax+0A0h]
0x180051a40  call    cs:__guard_dispatch_icall_fptr
0x180051a46  nop
0x180051a47  test    eax, eax
0x180051a49  js      short loc_180051A55
0x180051a4b  cmp     [rbp+90h+var_F0], 0
0x180051a4f  jnz     loc_18005201A
0x180051a55  call    MpIsWindows8OrGreater
0x180051a5a  test    eax, eax
0x180051a5c  jz      loc_180051D5F
0x180051a62  cmp     cs:qword_1803135B0, 0
0x180051a6a  jz      loc_180052048
0x180051a70  cmp     cs:qword_1803135A8, 0
0x180051a78  jz      loc_18005206E
0x180051a7e  mov     [rbp+90h+var_F0], ebx
0x180051a81  mov     rbx, cs:qword_1803135B0
0x180051a88  call    cs:__imp_GetCurrentThread
0x180051a8e  mov     rcx, rax
0x180051a91  mov     r9d, 4
0x180051a97  lea     r8, [rbp+90h+var_F0]
0x180051a9b  mov     edx, 1
0x180051aa0  mov     rax, rbx
0x180051aa3  call    cs:__guard_dispatch_icall_fptr
0x180051aa9  mov     r14d, [rbp+90h+var_F0]
0x180051aad  test    eax, eax
0x180051aaf  mov     ebx, 0
0x180051ab4  cmovz   r14d, ebx
0x180051ab8  cmp     dword ptr [rbp+90h+var_108+4], 0
0x180051abc  jz      short loc_180051AFB
0x180051abe  cmp     cs:qword_1803135A8, 0
0x180051ac6  jz      short loc_180051AFD
0x180051ac8  call    cs:__imp_GetCurrentThread
0x180051ace  mov     ecx, [rbp+90h+var_10C]
0x180051ad1  mov     dword ptr [rbp+90h+var_D8], ecx
0x180051ad4  mov     r9d, 4
0x180051ada  lea     r8, [rbp+90h+var_D8]
0x180051ade  mov     edx, 1
0x180051ae3  mov     rcx, rax
0x180051ae6  mov     rax, cs:qword_1803135A8
0x180051aed  call    cs:__guard_dispatch_icall_fptr
0x180051af3  test    eax, eax
0x180051af5  jz      loc_180052094
0x180051afb  mov     esi, ebx
0x180051afd  test    esi, esi
0x180051aff  js      loc_1800520D2
0x180051b05  test    cs:Microsoft_Antimalware_RTPEnableBits, 1
0x180051b0c  jnz     loc_180051C4B
0x180051b12  mov     ebx, [rbp+90h+var_E8]
0x180051b15  test    r15d, r15d
0x180051b18  js      loc_18005214A
0x180051b1e  test    ebx, ebx
0x180051b20  js      loc_18005214A
0x180051b26  test    rdi, rdi
0x180051b29  jz      loc_180052185
0x180051b2f  lea     rcx, ??_7CFileFilterReply@RealtimeProtection@@6BIFilterReply@1@@; const RealtimeProtection::CFileFilterReply::`vftable'{for `RealtimeProtection::IFilterReply'}
0x180051b36  mov     rax, [rdi]
0x180051b39  cmp     rax, rcx
0x180051b3c  jnz     loc_180051DA2
0x180051b42  mov     rax, [rdi]
0x180051b45  mov     rcx, rdi
0x180051b48  mov     rax, [rax+20h]
0x180051b4c  call    cs:__guard_dispatch_icall_fptr
0x180051b52  mov     [rax], ebx
0x180051b54  mov     dword ptr [rdi+98h], 3Ch ; '<'
0x180051b5e  movups  xmm1, [rbp+90h+var_D0]
0x180051b62  movups  xmm2, xmmword ptr [rbp-30h]
0x180051b66  movsd   xmm0, qword ptr [rbp+90h+var_BC+0Ch]
0x180051b6b  mov     eax, dword ptr [rbp+90h+var_AC+4]
0x180051b6e  movups  xmmword ptr [rdi+28h], xmm1
0x180051b72  movups  xmmword ptr [rdi+38h], xmm2
0x180051b76  movsd   qword ptr [rdi+48h], xmm0
0x180051b7b  mov     [rdi+50h], eax
0x180051b7e  mov     eax, r15d
0x180051b81  mov     rcx, [rbp+90h+var_40]
0x180051b85  xor     rcx, rsp; StackCookie
0x180051b88  call    __security_check_cookie
0x180051b8d  mov     rbx, [rsp+1A0h+arg_0]
0x180051b95  add     rsp, 170h
0x180051b9c  pop     r15
0x180051b9e  pop     r14
0x180051ba0  pop     r13
0x180051ba2  pop     r12
0x180051ba4  pop     rdi
0x180051ba5  pop     rsi
0x180051ba6  pop     rbp
0x180051ba7  retn
0x180051ba8  xor     ebx, ebx
0x180051baa  jmp     loc_1800518DB
0x180051baf  cmp     cs:qword_1803135B0, 0
0x180051bb7  jz      loc_180051DB7
0x180051bbd  cmp     cs:qword_1803135A8, 0
0x180051bc5  jz      loc_180051DD8
0x180051bcb  call    cs:__imp_GetCurrentThread
0x180051bd1  mov     rbx, rax
0x180051bd4  mov     [rbp+90h+var_E0], 0
0x180051bdb  mov     r9d, 4
0x180051be1  lea     r8, [rbp+90h+var_E0]
0x180051be5  mov     edx, 1
0x180051bea  mov     rcx, rax
0x180051bed  mov     rax, cs:qword_1803135B0
0x180051bf4  call    cs:__guard_dispatch_icall_fptr
0x180051bfa  test    eax, eax
0x180051bfc  jz      loc_180051E03
0x180051c02  mov     eax, [rbp+90h+var_E0]
0x180051c05  mov     [rbp+90h+var_10C], eax
0x180051c08  cmp     eax, [rbp+90h+var_F0]
0x180051c0b  jz      loc_180051E46
0x180051c11  mov     r9d, 4
0x180051c17  lea     r8, [rbp+90h+var_F0]
0x180051c1b  mov     edx, 1
0x180051c20  mov     rcx, rbx
0x180051c23  mov     rax, cs:qword_1803135A8
0x180051c2a  call    cs:__guard_dispatch_icall_fptr
0x180051c30  test    eax, eax
0x180051c32  jz      loc_180051E51
0x180051c38  mov     dword ptr [rbp+90h+var_108+4], 1
0x180051c3f  xor     ebx, ebx
  ... truncated ...
```
