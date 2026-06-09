# CleanupStartupProcessing

- ea: `0x1800faf90`
- end: `0x1800fb632`
- name: `CleanupStartupProcessing`
- size: `1698`
- prototype: ``
- caller_count: `1`
- callee_count: `51`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800fdf60`

## callees

- `0x180012fe4`
- `0x1800138b8`
- `0x18004a920`
- `0x180058b98`
- `0x180059680`
- `0x1800a02ec`
- `0x1800a8010`
- `0x1800a85a4`
- `0x1800a8678`
- `0x1800ad504`
- `0x1800ae508`
- `0x1800d59e8`
- `0x1800e1e58`
- `0x1800eb920`
- `0x1800f1eb4`
- `0x1800f3190`
- `0x1800f7ba4`
- `0x1800fa80c`
- `0x1800faf90`
- `0x1800fb80c`
- `0x1800fdd04`
- `0x1800fe8e0`
- `0x1800ff474`
- `0x1800ff7f0`
- `0x1800ff94c`
- `0x1800ffd84`
- `0x180108ad4`
- `0x18010e8a0`
- `0x18010f05c`
- `0x180122e10`
- `0x180122ff4`
- `0x180124384`
- `0x180126a14`
- `0x18012d584`
- `0x180146ac0`
- `0x180146c94`
- `0x180148d60`
- `0x18014c97c`
- `0x18014ca54`
- `0x18014ca7c`
- `0x1801bd258`
- `0x1801bd4f4`
- `0x1801e0638`
- `0x1801e0e54`
- `0x1801e5618`
- `0x1801e58ec`
- `0x1801e6db4`
- `0x1801e80f4`
- `0x1801e8c08`
- `0x1801e8e80`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800fb589`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800fb589`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800fb31f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800fb31f`

## string_xrefs

- `0x1800fafd4`: `Unable to close driver update context`
- `0x1800fb272`: `Startup: start scavenging at service startup`
- `0x1800fb2b6`: `Startup: Scavenging returned complete: {}`
- `0x1800fb3fb`: `TiAttemptedInitialization`
- `0x1800fb442`: `TiAttemptedInitialization`
- `0x1800fb47f`: `TiAttemptedInitialization`
- `0x1800fb45c`: `Failed to set TiAttemptedInitialization to 1 in CBS`
- `0x1800fb4bc`: `Failed to delete CbsArmAfterReboot`
- `0x1800fb494`: `Failed to set TiAttemptedInitialization`
- `0x1800fb4e2`: `Startup: Processing complete.`
- `0x1800fb5bf`: `Unable to write LastTrustedInstallerBoot value.`
- `0x1800fb5a4`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing\Interface`
- `0x1800fb599`: `LastTrustedInstallerBoot`

## pseudocode

```c
void __fastcall CleanupStartupProcessing(unsigned int *a1)
{
  struct HDRIVERUPDATECONTEXT__ *v2; // rcx
  unsigned int v3; // eax
  __int64 v4; // r8
  __int64 v5; // rcx
  unsigned int *v6; // rdx
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // ecx
  _DWORD *v10; // rdi
  unsigned int v11; // eax
  _DWORD *v12; // r14
  CCbsSessionManager *v13; // rcx
  unsigned int v14; // eax
  unsigned int v15; // eax
  struct CCbsSession *v16; // rcx
  unsigned int v17; // eax
  __int64 v18; // rcx
  unsigned int v19; // eax
  unsigned int v20; // eax
  const char *v21; // r8
  __int64 v22; // rdx
  int DWORDValue; // eax
  unsigned int v24; // eax
  const wchar_t *v25; // rdx
  unsigned int v26; // eax
  unsigned int KnownGood; // eax
  unsigned int v28; // eax
  unsigned int v29[2]; // [rsp+30h] [rbp-69h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-61h] BYREF
  _BYTE v31[96]; // [rsp+40h] [rbp-59h] BYREF

  v2 = (struct HDRIVERUPDATECONTEXT__ *)*((_QWORD *)a1 + 18);
  if ( v2 )
  {
    v3 = DoqCloseContext(v2);
    LogAdapter::TraceAtLevelIfFailed<long,>(1, v3, "Unable to close driver update context");
  }
  if ( a1[31] )
  {
    CCbsOSVersionPublisher::CCbsOSVersionPublisher((CCbsOSVersionPublisher *)&SystemTimeAsFileTime, 0);
    CCbsExecutionSpecialTransformers::CCbsExecutionSpecialTransformers((CCbsExecutionSpecialTransformers *)v31, 0);
    CCbsOSVersionPublisher::CleanupVersions((CCbsOSVersionPublisher *)&SystemTimeAsFileTime);
    CCbsExecutionSpecialTransformers::Clear((CCbsExecutionSpecialTransformers *)v31);
    if ( HIDWORD(qword_1803B11E8[8].SpinCount) )
    {
      LogAdapter::TraceAtLevel<>(
        1,
        "Startup: Previous pended transaction was cancelled, mark all packages with the error");
      v4 = 0;
      v5 = 2148468805LL;
      v6 = 0;
    }
    else
    {
      v29[0] = 0;
      GetRollbackFailState(v29);
      v4 = v29[0];
      v6 = a1 + 8;
      v5 = *a1;
    }
    v7 = PackageStoreProcessPendingPackages(v5, v6, v4);
    LogAdapter::TraceAtLevelIfFailed<long,>(
      2,
      v7,
      "Startup: Unable to process all pending packages, ignoring failure and continuing.");
    PackageStoreSetOriginalFailureStatus(0, 0);
    DoqClear(0, 0);
    v8 = ClearCurrentBuildNumbers(0);
    LogAdapter::TraceAtLevelIfFailed<long,>(3, v8, "Unable to clear current build numbers");
    if ( a1[24] )
    {
      if ( a1[32] )
      {
        a1[38] = 4;
        v9 = 4;
      }
      else if ( (a1[38] & 0x3FFF) == 0x14 )
      {
        v9 = 1048626;
        a1[38] = 1048626;
      }
      else
      {
        a1[38] = 50;
        v9 = 50;
      }
    }
    else
    {
      a1[38] = -1;
      v9 = -1;
    }
    SetExecuteState(v9);
    CCbsExecutionSpecialTransformers::~CCbsExecutionSpecialTransformers((CCbsExecutionSpecialTransformers *)v31);
    Windows::AutoComPtr<CCbsDriverDeployment>::Close(&SystemTimeAsFileTime);
  }
  DoqUninitialize();
  v10 = a1 + 24;
  v11 = CCbsSessionManager::NotifyStartupFinish(qword_1803B11E8, *a1, a1[24], a1 + 8);
  LogAdapter::TraceAtLevelIfFailed<long,>(3, v11, "Startup: Failed to notify session manager on startup finish.");
  if ( a1[24] && vpfnRequireRebootCallback )
    vpfnRequireRebootCallback();
  v12 = a1 + 30;
  if ( a1[30] || (unsigned int)PackageStoreIsPendingInstallRequired() )
  {
    if ( *v10 )
    {
      LogAdapter::TraceAtLevel<>(
        1,
        "Startup: Retry delayed by pending reboot; making sure we remain auto-start and don't clean up the package store.");
      *a1 = -2147021886;
      goto LABEL_26;
    }
    v29[0] = 0;
    LogAdapter::TraceAtLevel<>(1, "Startup: Retrying failed packages.");
    v13 = (CCbsSessionManager *)qword_1803B11E8;
    if ( *(_QWORD *)&qword_1803B11E8[4].LockCount )
    {
      SetProgressMessage(4, a1[38]);
      v13 = (CCbsSessionManager *)qword_1803B11E8;
    }
    v14 = CCbsSessionManager::RetryPendingVictims(v13, (int *)v29);
    LogAdapter::TraceAtLevelIfFailed<long,>(2, v14, "Startup: Failed retrying pending victims");
    if ( v29[0] )
    {
      *v10 = 1;
LABEL_26:
      *v12 = 0;
    }
  }
  v15 = ResumePendingSessions(a1 + 24, a1 + 30, a1[38]);
  if ( v15 == 985139 || v15 == 985091 )
    *a1 = v15;
  if ( !*v10 )
    goto LABEL_84;
  if ( *v12 )
  {
    a1[38] = 50;
    SetExecuteState(0x32u);
    *v12 = 0;
  }
  if ( !*v10 )
  {
LABEL_84:
    if ( *a1 != 985139 && *a1 != 985091 && (unsigned int)PackageStoreIsScavengeRequired(v16) )
    {
      if ( a1[49] )
      {
        LogAdapter::TraceAtLevel<>(
          1,
          "Startup: skipping synchronous scavenge at startup due to: client initiated startup processing");
        PackageStoreMarkScavengeCompleted(0);
      }
      else
      {
        v29[0] = 0;
        LogAdapter::TraceAtLevel<>(1, "Startup: start scavenging at service startup");
        a1[38] = 100;
        SetExecuteState(0x64u);
        SetProgressMessage(0xFFFFFFFFLL, a1[38]);
        v17 = CbsCoreServiceIdleProcessing(0, (int *)v29);
        LogAdapter::TraceAtLevelHr<long,int>(v18, v17, "Startup: Scavenging returned complete: {}", v29);
        a1[38] = -1;
        SetExecuteState(0xFFFFFFFF);
      }
    }
  }
  if ( (vdwCbsCoreMode & 2) != 0 )
  {
    if ( *v10 )
    {
      CStopwatch::Stop((CStopwatch *)&vStopwatchStartupProcessing);
      if ( qword_1803AF520 < 10000 )
      {
        v29[0] = 10000 - qword_1803AF520;
        LogAdapter::TraceAtLevel<unsigned long>(1, "Waiting for {} milliseconds for UI before restarting", v29);
        Sleep(10000 - qword_1803AF520);
      }
    }
  }
  CleanupProgress();
  CCbsProgress::Finalize((CCbsProgress *)(a1 + 62));
  CReboundProgress::Finalize((CReboundProgress *)(a1 + 108));
  if ( *v10 && (*a1 & 0x80000000) == 0 )
  {
    *a1 = -2147021886;
    LogAdapter::TraceAtLevel<>(1, "Startup: Success, restart required to continue processing.");
  }
  if ( a1[49] )
  {
    if ( a1[48] == 2 && !*v10 )
    {
      LogAdapter::TraceAtLevel<>(1, "Clearing PostponeOnlineActions");
      PackageStoreDeleteProperty(0, L"PostponeOnlineActions");
    }
  }
  else
  {
    if ( *v10 && (*a1 & 0x80000000) != 0 && *a1 != -2147021879 && *a1 != -2147021886 )
    {
      *a1 = -2147021886;
      LogAdapter::TraceAtLevel<>(1, "Startup: Failed, restart required to try again.");
    }
    if ( a1[34] )
      *a1 = -2147467260;
  }
  v29[0] = 0;
  if ( *a1 == -2147021886 )
  {
    if ( (unsigned int)(CbsRegQueryDWORDValue(
                          HKEY_LOCAL_MACHINE,
                          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ReserveManager",
                          0,
                          L"TiAttemptedInitialization",
                          v29)
                      + 2147024894) > 1 )
      goto LABEL_68;
    v19 = CbsRegSetDWORDValue(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ReserveManager",
            0,
            L"CbsArmAfterReboot",
            1u);
    LogAdapter::TraceAtLevelIfFailed<long,>(3, v19, "Failed to set CbsArmAfterReboot to 1");
    v20 = CbsRegSetDWORDValue(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ReserveManager",
            0,
            L"TiAttemptedInitialization",
            1u);
    v21 = "Failed to set TiAttemptedInitialization to 1 in CBS";
    goto LABEL_61;
  }
  DWORDValue = CbsRegQueryDWORDValue(
                 HKEY_LOCAL_MACHINE,
                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ReserveManager",
                 0,
                 L"CbsArmAfterReboot",
                 v29);
  v22 = (unsigned int)DWORDValue;
  if ( DWORDValue < 0 )
  {
    if ( (unsigned int)(DWORDValue + 2147024894) <= 1 )
      goto LABEL_68;
    goto LABEL_66;
  }
  if ( v29[0] != 1 )
  {
LABEL_66:
    v21 = "Failed to query CbsArmAfterReboot. Assuming it is not set.";
    goto LABEL_67;
  }
  v24 = CbsRegDeleteValue(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ReserveManager",
          0,
          L"TiAttemptedInitialization");
  LogAdapter::TraceAtLevelIfFailed<long,>(3, v24, "Failed to set TiAttemptedInitialization");
  v20 = CbsRegDeleteValue(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ReserveManager",
          0,
          L"CbsArmAfterReboot");
  v21 = "Failed to delete CbsArmAfterReboot";
LABEL_61:
  v22 = v20;
LABEL_67:
  LogAdapter::TraceAtLevelIfFailed<long,>(3, v22, v21);
LABEL_68:
  LogAdapter::TraceAtLevelHr<long,>(1, *a1, "Startup: Processing complete.");
  PackageStoreWriteTimeStamp(0, L"LastModified_UTC");
  PackageStoreCleanupCachedApplicabilityEvaluationPackage(0, v25);
  if ( *v10 )
    SetRebootInProgressFlag();
  if ( (unsigned __int64)(*((_QWORD *)a1 + 23) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v26 = AllowSystemSleepMode();
    LogAdapter::TraceAtLevelIfFailed<long,>(1, v26, "Unable to unblock system sleep");
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      a1 + 46,
      0);
  }
  if ( *v12 || a1[49] )
  {
    KnownGood = EnableLastKnownGood(0);
    LogAdapter::TraceAtLevelIfFailed<long,>(1, KnownGood, "Startup: Failed enabling LKG");
  }
  if ( !*v10 )
  {
    SetServicingInProgress(0);
    SetReboundState(0);
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    *(struct _FILETIME *)v29 = SystemTimeAsFileTime;
    v28 = CbsRegSetQWORDValue(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\Interface",
            0,
            L"LastTrustedInstallerBoot",
            (const unsigned __int64 *const)v29);
    LogAdapter::TraceAtLevelIfFailed<long,>(1, v28, "Unable to write LastTrustedInstallerBoot value.");
    CCbsSessionManager::Reset((CCbsSessionManager *)qword_1803B11E8, 0);
  }
  if ( *((_QWORD *)a1 + 13) )
  {
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&vStartupCache);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(a1 + 26);
    CloseOnlineStore();
  }
  if ( a1[43] || *v10 )
    FlushHivesAndSystemVolume();
}

```

## disassembly

```asm
0x1800faf90  push    rbp
0x1800faf92  push    rbx
0x1800faf93  push    rsi
0x1800faf94  push    rdi
0x1800faf95  push    r12
0x1800faf97  push    r13
0x1800faf99  push    r14
0x1800faf9b  push    r15
0x1800faf9d  lea     rbp, [rsp-1Fh]
0x1800fafa2  sub     rsp, 0B8h
0x1800fafa9  mov     rax, cs:__security_cookie
0x1800fafb0  xor     rax, rsp
0x1800fafb3  mov     [rbp+57h+var_50], rax
0x1800fafb7  mov     rbx, rcx
0x1800fafba  xor     r12d, r12d
0x1800fafbd  mov     rcx, [rcx+90h]; struct HDRIVERUPDATECONTEXT__ *
0x1800fafc4  mov     r13d, 1
0x1800fafca  test    rcx, rcx
0x1800fafcd  jz      short loc_1800FAFE5
0x1800fafcf  call    ?DoqCloseContext@@YAJPEAUHDRIVERUPDATECONTEXT__@@@Z; DoqCloseContext(HDRIVERUPDATECONTEXT__ *)
0x1800fafd4  lea     r8, aUnableToCloseD; "Unable to close driver update context"
0x1800fafdb  mov     edx, eax
0x1800fafdd  mov     ecx, r13d
0x1800fafe0  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1800fafe5  mov     edi, 4
0x1800fafea  or      r14d, 0FFFFFFFFh
0x1800fafee  lea     esi, [rdi+2Eh]
0x1800faff1  lea     r15d, [rdi-1]
0x1800faff5  cmp     [rbx+7Ch], r12d
0x1800faff9  jz      loc_1800FB10E
0x1800fafff  xor     edx, edx; struct CCbsSession *
0x1800fb001  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; this
0x1800fb005  call    ??0CCbsOSVersionPublisher@@QEAA@PEAVCCbsSession@@@Z; CCbsOSVersionPublisher::CCbsOSVersionPublisher(CCbsSession *)
0x1800fb00a  xor     edx, edx; struct CCbsSession *
0x1800fb00c  lea     rcx, [rbp+57h+var_B0]; this
0x1800fb010  call    ??0CCbsExecutionSpecialTransformers@@QEAA@PEAVCCbsSession@@@Z; CCbsExecutionSpecialTransformers::CCbsExecutionSpecialTransformers(CCbsSession *)
0x1800fb015  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; this
0x1800fb019  call    ?CleanupVersions@CCbsOSVersionPublisher@@QEAAJXZ; CCbsOSVersionPublisher::CleanupVersions(void)
0x1800fb01e  lea     rcx, [rbp+57h+var_B0]; this
0x1800fb022  call    ?Clear@CCbsExecutionSpecialTransformers@@QEAAJXZ; CCbsExecutionSpecialTransformers::Clear(void)
0x1800fb027  mov     rax, cs:qword_1803B11E8
0x1800fb02e  cmp     [rax+164h], r12d
0x1800fb035  jz      short loc_1800FB052
0x1800fb037  lea     rdx, aStartupPreviou; "Startup: Previous pended transaction wa"...
0x1800fb03e  mov     ecx, r13d
0x1800fb041  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1800fb046  xor     r8d, r8d
0x1800fb049  mov     ecx, 800F0845h
0x1800fb04e  xor     edx, edx
0x1800fb050  jmp     short loc_1800FB069
0x1800fb052  lea     rcx, [rbp+57h+var_C0]
0x1800fb056  mov     [rbp+57h+var_C0], r12d
0x1800fb05a  call    GetRollbackFailState
0x1800fb05f  mov     r8d, [rbp+57h+var_C0]
0x1800fb063  lea     rdx, [rbx+20h]
0x1800fb067  mov     ecx, [rbx]
0x1800fb069  call    ?PackageStoreProcessPendingPackages@@YAJJPEAV?$CCbsPointerArray@PEAUPendingPackageError@@@@W4CbsRollbackFailState@@@Z; PackageStoreProcessPendingPackages(long,CCbsPointerArray<PendingPackageError *> *,CbsRollbackFailState)
0x1800fb06e  lea     r8, aStartupUnableT_2; "Startup: Unable to process all pending "...
0x1800fb075  mov     edx, eax
0x1800fb077  mov     ecx, 2
0x1800fb07c  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1800fb081  xor     edx, edx; unsigned int
0x1800fb083  xor     ecx, ecx; int
0x1800fb085  call    ?PackageStoreSetOriginalFailureStatus@@YAXJK@Z; PackageStoreSetOriginalFailureStatus(long,ulong)
0x1800fb08a  xor     edx, edx
0x1800fb08c  xor     ecx, ecx
0x1800fb08e  call    ?DoqClear@@YAJPEAVCCbsSession@@W4_DOQ_KEY_TYPE@@@Z; DoqClear(CCbsSession *,_DOQ_KEY_TYPE)
0x1800fb093  xor     ecx, ecx; struct CCbsSession *
0x1800fb095  call    ?ClearCurrentBuildNumbers@@YAJPEAVCCbsSession@@@Z; ClearCurrentBuildNumbers(CCbsSession *)
0x1800fb09a  lea     r8, aUnableToClearC; "Unable to clear current build numbers"
0x1800fb0a1  mov     edx, eax
0x1800fb0a3  mov     ecx, r15d
0x1800fb0a6  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1800fb0ab  cmp     [rbx+60h], r12d
0x1800fb0af  jz      short loc_1800FB0EB
0x1800fb0b1  cmp     [rbx+80h], r12d
0x1800fb0b8  jz      short loc_1800FB0C4
0x1800fb0ba  mov     [rbx+98h], edi
0x1800fb0c0  mov     ecx, edi
0x1800fb0c2  jmp     short loc_1800FB0F5
0x1800fb0c4  mov     eax, [rbx+98h]
0x1800fb0ca  and     eax, 3FFFh
0x1800fb0cf  cmp     eax, 14h
0x1800fb0d2  jnz     short loc_1800FB0E1
0x1800fb0d4  mov     ecx, 100032h
0x1800fb0d9  mov     [rbx+98h], ecx
0x1800fb0df  jmp     short loc_1800FB0F5
0x1800fb0e1  mov     [rbx+98h], esi
0x1800fb0e7  mov     ecx, esi
0x1800fb0e9  jmp     short loc_1800FB0F5
0x1800fb0eb  mov     [rbx+98h], r14d
0x1800fb0f2  mov     ecx, r14d; unsigned int
0x1800fb0f5  xor     edx, edx
0x1800fb0f7  call    SetExecuteState
0x1800fb0fc  lea     rcx, [rbp+57h+var_B0]; this
0x1800fb100  call    ??1CCbsExecutionSpecialTransformers@@QEAA@XZ; CCbsExecutionSpecialTransformers::~CCbsExecutionSpecialTransformers(void)
0x1800fb105  lea     rcx, [rbp+57h+SystemTimeAsFileTime]
0x1800fb109  call    ?Close@?$AutoComPtr@VCCbsDriverDeployment@@@Windows@@QEAAXXZ; Windows::AutoComPtr<CCbsDriverDeployment>::Close(void)
0x1800fb10e  call    ?DoqUninitialize@@YAJXZ; DoqUninitialize(void)
0x1800fb113  mov     edx, [rbx]
0x1800fb115  lea     rdi, [rbx+60h]
0x1800fb119  mov     r8d, [rdi]
0x1800fb11c  lea     r9, [rbx+20h]
0x1800fb120  mov     rcx, cs:qword_1803B11E8
0x1800fb127  call    ?NotifyStartupFinish@CCbsSessionManager@@QEAAJJHPEAV?$CCbsPointerArray@PEAUPendingPackageError@@@@@Z; CCbsSessionManager::NotifyStartupFinish(long,int,CCbsPointerArray<PendingPackageError *> *)
0x1800fb12c  lea     r8, aStartupFailedT_6; "Startup: Failed to notify session manag"...
0x1800fb133  mov     edx, eax
0x1800fb135  mov     ecx, r15d
0x1800fb138  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1800fb13d  cmp     [rdi], r12d
0x1800fb140  jz      short loc_1800FB153
0x1800fb142  mov     rax, cs:?vpfnRequireRebootCallback@@3P6AXXZEA; void (*vpfnRequireRebootCallback)(void)
0x1800fb149  test    rax, rax
0x1800fb14c  jz      short loc_1800FB153
0x1800fb14e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb153  lea     r14, [rbx+78h]
0x1800fb157  mov     r15d, 80070BC2h
0x1800fb15d  cmp     [r14], r12d
0x1800fb160  jnz     short loc_1800FB16B
0x1800fb162  call    ?PackageStoreIsPendingInstallRequired@@YAHXZ; PackageStoreIsPendingInstallRequired(void)
0x1800fb167  test    eax, eax
0x1800fb169  jz      short loc_1800FB1E5
0x1800fb16b  mov     ecx, r13d
0x1800fb16e  cmp     [rdi], r12d
0x1800fb171  jnz     short loc_1800FB1D3
0x1800fb173  lea     rdx, aStartupRetryin_0; "Startup: Retrying failed packages."
0x1800fb17a  mov     [rbp+57h+var_C0], r12d
0x1800fb17e  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1800fb183  mov     rcx, cs:qword_1803B11E8
0x1800fb18a  cmp     [rcx+0A8h], r12
0x1800fb191  jbe     short loc_1800FB1AC
0x1800fb193  mov     edx, [rbx+98h]
0x1800fb199  xor     r8d, r8d
0x1800fb19c  lea     ecx, [r8+4]
0x1800fb1a0  call    ?SetProgressMessage@@YAXW4CbsProgressMessageStage@@KK@Z; SetProgressMessage(CbsProgressMessageStage,ulong,ulong)
0x1800fb1a5  mov     rcx, cs:qword_1803B11E8; this
0x1800fb1ac  lea     rdx, [rbp+57h+var_C0]; int *
0x1800fb1b0  call    ?RetryPendingVictims@CCbsSessionManager@@QEAAJPEAH@Z; CCbsSessionManager::RetryPendingVictims(int *)
0x1800fb1b5  lea     r8, aStartupFailedR; "Startup: Failed retrying pending victim"...
0x1800fb1bc  mov     edx, eax
0x1800fb1be  mov     ecx, 2
0x1800fb1c3  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1800fb1c8  cmp     [rbp+57h+var_C0], r12d
0x1800fb1cc  jz      short loc_1800FB1E5
0x1800fb1ce  mov     [rdi], r13d
0x1800fb1d1  jmp     short loc_1800FB1E2
0x1800fb1d3  lea     rdx, aStartupRetryDe; "Startup: Retry delayed by pending reboo"...
0x1800fb1da  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1800fb1df  mov     [rbx], r15d
0x1800fb1e2  mov     [r14], r12d
0x1800fb1e5  mov     r8d, [rbx+98h]
0x1800fb1ec  mov     rdx, r14
0x1800fb1ef  mov     rcx, rdi
0x1800fb1f2  call    ResumePendingSessions
0x1800fb1f7  cmp     eax, 0F0833h
0x1800fb1fc  jz      short loc_1800FB205
0x1800fb1fe  cmp     eax, 0F0803h
0x1800fb203  jnz     short loc_1800FB207
0x1800fb205  mov     [rbx], eax
0x1800fb207  cmp     [rdi], r12d
0x1800fb20a  jz      short loc_1800FB22C
0x1800fb20c  cmp     [r14], r12d
0x1800fb20f  jz      short loc_1800FB223
0x1800fb211  xor     edx, edx
0x1800fb213  mov     [rbx+98h], esi
0x1800fb219  mov     ecx, esi; unsigned int
0x1800fb21b  call    SetExecuteState
0x1800fb220  mov     [r14], r12d
0x1800fb223  cmp     [rdi], r12d
0x1800fb226  jnz     loc_1800FB2D2
0x1800fb22c  cmp     dword ptr [rbx], 0F0833h
0x1800fb232  jz      loc_1800FB2D2
0x1800fb238  cmp     dword ptr [rbx], 0F0803h
0x1800fb23e  jz      loc_1800FB2D2
0x1800fb244  call    ?PackageStoreIsScavengeRequired@@YAHPEAVCCbsSession@@@Z; PackageStoreIsScavengeRequired(CCbsSession *)
0x1800fb249  test    eax, eax
0x1800fb24b  jz      loc_1800FB2D2
0x1800fb251  mov     ecx, r13d
0x1800fb254  cmp     [rbx+0C4h], r12d
0x1800fb25b  jz      short loc_1800FB272
0x1800fb25d  lea     rdx, aStartupSkippin; "Startup: skipping synchronous scavenge "...
0x1800fb264  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1800fb269  xor     ecx, ecx; struct CCbsSession *
0x1800fb26b  call    ?PackageStoreMarkScavengeCompleted@@YAJPEAVCCbsSession@@@Z; PackageStoreMarkScavengeCompleted(CCbsSession *)
0x1800fb270  jmp     short loc_1800FB2D2
0x1800fb272  lea     rdx, aStartupStartSc; "Startup: start scavenging at service st"...
0x1800fb279  mov     [rbp+57h+var_C0], r12d
0x1800fb27d  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1800fb282  mov     ecx, 64h ; 'd'; unsigned int
0x1800fb287  xor     edx, edx
0x1800fb289  mov     [rbx+98h], ecx
0x1800fb28f  call    SetExecuteState
0x1800fb294  mov     edx, [rbx+98h]
0x1800fb29a  xor     r8d, r8d
0x1800fb29d  or      ecx, 0FFFFFFFFh
0x1800fb2a0  call    ?SetProgressMessage@@YAXW4CbsProgressMessageStage@@KK@Z; SetProgressMessage(CbsProgressMessageStage,ulong,ulong)
0x1800fb2a5  lea     rdx, [rbp+57h+var_C0]; int *
0x1800fb2a9  xor     ecx, ecx; int
0x1800fb2ab  call    ?CbsCoreServiceIdleProcessing@@YAJHPEAH@Z; CbsCoreServiceIdleProcessing(int,int *)
0x1800fb2b0  lea     r9, [rbp+57h+var_C0]
0x1800fb2b4  mov     edx, eax
0x1800fb2b6  lea     r8, aStartupScaveng_0; "Startup: Scavenging returned complete: "...
0x1800fb2bd  call    ??$TraceAtLevelHr@JH@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBH@Z; LogAdapter::TraceAtLevelHr<long,int>(LogAdapter::LogLevel,long,char const * const,int const &)
0x1800fb2c2  or      ecx, 0FFFFFFFFh; unsigned int
0x1800fb2c5  xor     edx, edx
0x1800fb2c7  mov     [rbx+98h], ecx
0x1800fb2cd  call    SetExecuteState
0x1800fb2d2  test    byte ptr cs:?vdwCbsCoreMode@@3KA, 2; ulong vdwCbsCoreMode
0x1800fb2d9  jz      short loc_1800FB32B
0x1800fb2db  cmp     [rdi], r12d
0x1800fb2de  jz      short loc_1800FB32B
0x1800fb2e0  lea     rcx, ?vStopwatchStartupProcessing@@3VCStopwatch@@A; this
0x1800fb2e7  call    ?Stop@CStopwatch@@QEAAXXZ; CStopwatch::Stop(void)
0x1800fb2ec  mov     rcx, cs:qword_1803AF520
0x1800fb2f3  mov     esi, 2710h
0x1800fb2f8  cmp     rcx, rsi
0x1800fb2fb  jge     short loc_1800FB32B
0x1800fb2fd  mov     eax, esi
0x1800fb2ff  lea     r8, [rbp+57h+var_C0]
0x1800fb303  sub     eax, ecx
0x1800fb305  lea     rdx, aWaitingForMill; "Waiting for {} milliseconds for UI befo"...
0x1800fb30c  mov     ecx, r13d
0x1800fb30f  mov     [rbp+57h+var_C0], eax
0x1800fb312  call    ??$TraceAtLevel@K@LogAdapter@@YAXW4LogLevel@0@QEBDAEBK@Z; LogAdapter::TraceAtLevel<ulong>(LogAdapter::LogLevel,char const * const,ulong const &)
0x1800fb317  sub     esi, dword ptr cs:qword_1803AF520
0x1800fb31d  mov     ecx, esi; dwMilliseconds
0x1800fb31f  call    cs:__imp_Sleep
0x1800fb326  nop     dword ptr [rax+rax+00h]
0x1800fb32b  call    ?CleanupProgress@@YAXXZ; CleanupProgress(void)
0x1800fb330  lea     rcx, [rbx+0F8h]; this
0x1800fb337  call    ?Finalize@CCbsProgress@@QEAAJXZ; CCbsProgress::Finalize(void)
0x1800fb33c  lea     rcx, [rbx+1B0h]; this
0x1800fb343  call    ?Finalize@CReboundProgress@@QEAAJXZ; CReboundProgress::Finalize(void)
0x1800fb348  cmp     [rdi], r12d
0x1800fb34b  jz      short loc_1800FB364
0x1800fb34d  cmp     [rbx], r12d
0x1800fb350  jl      short loc_1800FB364
0x1800fb352  lea     rdx, aStartupSuccess; "Startup: Success, restart required to c"...
0x1800fb359  mov     [rbx], r15d
0x1800fb35c  mov     ecx, r13d
0x1800fb35f  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1800fb364  cmp     [rbx+0C4h], r12d
0x1800fb36b  jnz     short loc_1800FB3A7
0x1800fb36d  cmp     [rdi], r12d
0x1800fb370  jz      short loc_1800FB396
0x1800fb372  cmp     [rbx], r12d
0x1800fb375  jge     short loc_1800FB396
0x1800fb377  cmp     dword ptr [rbx], 80070BC9h
0x1800fb37d  jz      short loc_1800FB396
0x1800fb37f  cmp     [rbx], r15d
0x1800fb382  jz      short loc_1800FB396
0x1800fb384  lea     rdx, aStartupFailedR_0; "Startup: Failed, restart required to tr"...
0x1800fb38b  mov     [rbx], r15d
0x1800fb38e  mov     ecx, r13d
0x1800fb391  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1800fb396  cmp     [rbx+88h], r12d
0x1800fb39d  jz      short loc_1800FB3D2
0x1800fb39f  mov     dword ptr [rbx], 80004004h
0x1800fb3a5  jmp     short loc_1800FB3D2
0x1800fb3a7  cmp     dword ptr [rbx+0C0h], 2
0x1800fb3ae  jnz     short loc_1800FB3D2
0x1800fb3b0  cmp     [rdi], r12d
0x1800fb3b3  jnz     short loc_1800FB3D2
0x1800fb3b5  lea     rdx, aClearingPostpo; "Clearing PostponeOnlineActions"
0x1800fb3bc  mov     ecx, r13d
0x1800fb3bf  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1800fb3c4  lea     rdx, aPostponeonline; "PostponeOnlineActions"
0x1800fb3cb  xor     ecx, ecx; struct CCbsSession *
0x1800fb3cd  call    ?PackageStoreDeleteProperty@@YAJPEAVCCbsSession@@PEB_W@Z; PackageStoreDeleteProperty(CCbsSession *,wchar_t const *)
0x1800fb3d2  xor     r8d, r8d; unsigned int
0x1800fb3d5  mov     [rbp+57h+var_C0], r12d
0x1800fb3d9  cmp     [rbx], r15d
0x1800fb3dc  lea     rax, [rbp+57h+var_C0]
0x1800fb3e0  mov     r15, 0FFFFFFFF80000002h
0x1800fb3e7  mov     [rsp+0F0h+var_D0], rax; unsigned int *
0x1800fb3ec  lea     rsi, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800fb3f3  mov     rcx, r15; HKEY
0x1800fb3f6  mov     rdx, rsi; wchar_t *
0x1800fb3f9  jnz     short loc_1800FB467
0x1800fb3fb  lea     r9, aTiattemptedini; "TiAttemptedInitialization"
0x1800fb402  call    ?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z; CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)
0x1800fb407  add     eax, 7FF8FFFEh
0x1800fb40c  cmp     eax, r13d
0x1800fb40f  ja      loc_1800FB4E0
0x1800fb415  lea     r9, aCbsarmafterreb; "CbsArmAfterReboot"
0x1800fb41c  mov     dword ptr [rsp+0F0h+var_D0], r13d; unsigned int
0x1800fb421  xor     r8d, r8d; unsigned int
0x1800fb424  mov     rdx, rsi; wchar_t *
0x1800fb427  mov     rcx, r15; hKey
0x1800fb42a  call    ?CbsRegSetDWORDValue@@YAJPEAUHKEY__@@PEB_WK1K@Z; CbsRegSetDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong)
0x1800fb42f  lea     r8, aFailedToSetCbs; "Failed to set CbsArmAfterReboot to 1"
0x1800fb436  mov     edx, eax
0x1800fb438  mov     ecx, 3
0x1800fb43d  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1800fb442  lea     r9, aTiattemptedini; "TiAttemptedInitialization"
0x1800fb449  mov     dword ptr [rsp+0F0h+var_D0], r13d; unsigned int
0x1800fb44e  xor     r8d, r8d; unsigned int
0x1800fb451  mov     rdx, rsi; wchar_t *
0x1800fb454  mov     rcx, r15; hKey
0x1800fb457  call    ?CbsRegSetDWORDValue@@YAJPEAUHKEY__@@PEB_WK1K@Z; CbsRegSetDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong)
  ... truncated ...
```
