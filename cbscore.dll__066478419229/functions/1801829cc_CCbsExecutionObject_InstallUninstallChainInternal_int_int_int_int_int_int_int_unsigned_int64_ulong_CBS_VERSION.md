# CCbsExecutionObject::InstallUninstallChainInternal(int,int &,int &,int &,int &,int &,int &,unsigned __int64 &,ulong &,_CBS_VERSION &,_CBS_VERSION &,CCbsOSVersionPublisher &,CCbsExecutionSpecialTransformers &,DoqExecuteImmediate &,CCbsInterfaceArray<CCbsExecutionUpdate *> &)

- ea: `0x1801829cc`
- end: `0x18018487e`
- name: `?InstallUninstallChainInternal@CCbsExecutionObject@@AEAAJHAEAH00000AEA_KAEAKAEAT_CBS_VERSION@@3AEAVCCbsOSVersionPublisher@@AEAVCCbsExecutionSpecialTransformers@@AEAVDoqExecuteImmediate@@AEAV?$CCbsInterfaceArray@PEAVCCbsExecutionUpdate@@@@@Z`
- size: `7858`
- prototype: `__int64 __usercall@<rax>(CCbsExecutionObject *this@<rcx>, __int64, __int64, __int64, __int64, __int64, __int64, union _CBS_VERSION *, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `69`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180182458`

## callees

- `0x180010cc0`
- `0x180012fe4`
- `0x180013250`
- `0x180016d40`
- `0x180028e24`
- `0x180042448`
- `0x180048c24`
- `0x18005620c`
- `0x18005b180`
- `0x180064934`
- `0x180065920`
- `0x180065f88`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800a8058`
- `0x1800a8438`
- `0x1800a8678`
- `0x1800ad504`
- `0x1800ad8cc`
- `0x1800ae508`
- `0x1800b980c`
- `0x1800c82d8`
- `0x1800cf6f8`
- `0x1800d28bc`
- `0x1800e1850`
- `0x1800eb920`
- `0x1800ef360`
- `0x1800f60c4`
- `0x1800f618c`
- `0x1800f8500`
- `0x1800ff474`
- `0x1800ffd84`
- `0x180126a14`
- `0x18012a934`
- `0x18012ad40`
- `0x18012e0f8`
- `0x180145828`
- `0x180146ac0`
- `0x180146cb8`
- `0x1801474b0`
- `0x180148378`
- `0x180148cac`
- `0x180149be8`
- `0x18014b730`
- `0x18014cbf4`
- `0x18014d46c`
- `0x18014d6e8`
- `0x18014db70`

## string_xrefs

- `0x1801830db`: `Failed to process component watch list.`
- `0x18018309b`: `Plan: Start to process component watchlist`
- `0x1801832ed`: `Exec: package or update requires restart, delay the execution to shutdown.`
- `0x180183266`: `Exec: package or update requires restart but ignoring because it is being removed by deep clean, which means it was superseded`
- `0x18018320d`: `Failed to set cim payload source for CIM based update.`
- `0x180182cde`: `Failed to check whether package was already earlier pended.`
- `0x180182c2a`: `onecore\base\cbs\core\cbsexecutionobjectinstall.cpp`
- `0x180182e64`: `onecore\base\cbs\core\cbsexecutionobjectinstall.cpp`
- `0x180182f4e`: `onecore\base\cbs\core\cbsexecutionobjectinstall.cpp`
- `0x180183448`: `onecore\base\cbs\core\cbsexecutionobjectinstall.cpp`
- `0x180183651`: `onecore\base\cbs\core\cbsexecutionobjectinstall.cpp`
- `0x1801840b3`: `onecore\base\cbs\core\cbsexecutionobjectinstall.cpp`
- `0x180182f06`: `Failed to create CSI transaction for executing.`
- `0x180182e1c`: `Failed creating committer for Desktop update`
- `0x180182dab`: `Failed creating committer for CIM based update`
- `0x180182d2e`: `Exec: Task package already smart pended by earlier sessions, force package smart pend`
- `0x180183989`: `Doqe: Driver operations completed successfully.`
- `0x1801839a3`: `Doqe: Driver operations completed successfully.`
- `0x18018382b`: `Failed executing special install transformers`
- `0x180183a79`: `Failed executing special install transformers`
- `0x180183b83`: `Unable to configure poqexec pend location.`
- `0x1801843ae`: `Unable to configure poqexec pend location.`
- `0x180184413`: `Unable to configure poqexec pend location.`
- `0x180183ad5`: `Exec: Skipping transaction commit since nothing was changed.`
- `0x1801839bf`: `Doqe: interactive driver operations completed but required a reboot.`
- `0x1801839b3`: `Doqe: interactive driver operations completed.`
- `0x180183523`: `Analysis indicated that installation cannot succeed without pending.`
- `0x180183405`: `CBS already has pended content.`
- `0x180183305`: `Exec: The Package or one of its Updates required and client specified DelayExecutionIfPendRequired, Execution will be delayed to system shutdown time.`
- `0x180184235`: `Exec: The Package or one of its Updates required and client specified DelayExecutionIfPendRequired, Execution will be delayed to system shutdown time.`
- `0x1801846f4`: `Exec: Transaction failed, and an advanced installer required a reboot.`
- `0x1801847bd`: `Exec: Cancelled pending transactions after rollback.`
- `0x180184745`: `Exec: An error occurred while committing the transaction and the transaction rollback requires a reboot.`
- `0x180184729`: `Exec: Scheduled TrustedInstaller for auto-start because rollback was pended.`
- `0x180183d1c`: `Unable to finalize driver installs`
- `0x180183caf`: `Doqe: primitives did not complete, so rolling back interactive driver operations.`
- `0x180183e46`: `Exec: Failed to commit CSI transaction to execute changes.`
- `0x180183d7c`: `Exec: An error occurred while committing the transaction, the transaction has been rolled back.`
- `0x180184264`: `Exec: Failed to commit CSI transaction due to file in use or Component reboot required, package changes need to be pended.`
- `0x18018424b`: `Exec: Failed to commit CSI transaction due to file in use or Component reboot required and client specified DelayExecutionIfPendRequired, Execution will be delayed to system shutdown time.`
- `0x18018423e`: `Exec: The Package or one of its Updates required a reboot so transaction commit was skipped, Package's changes need to be pended.`
- `0x1801844ce`: `Exec: Pended transaction, changes will be applied during shutdown/startup processing.`
- `0x180184423`: `Exec: Restoring driver operations because of a CSI commit failure.`
- `0x180183f43`: `Unable to get offline boot directory`
- `0x180183f09`: `Exec: Although the offline commit completed immediately, CBS has to consider it pended due to a previous operation.`
- `0x180183eec`: `Exec: Offline commit completes with no pending online operations.`
- `0x180184800`: `Exec: An error occurred while committing the transaction, the transaction could not be rolled back.`
- `0x18018401d`: `Exec: Pended transaction, changes will be applied during startup processing. Scheduled TrustedInstaller for auto-start.`
- `0x180183fc3`: `Exec: Removed package list file from {}`
- `0x180183f9f`: `Unable to remove package list file: {}`
- `0x180183f64`: `Unable to allocate package list path`
- `0x18018413c`: `Exec: Advanced installer executed successfully but still required a reboot.`
- `0x18018451b`: `Exec: Skipping shutdown processing as it is using CIM based update flow.`
- `0x18018416f`: `Exec: Scheduled TrustedInstaller for auto-start because we pended the transaction.`
- `0x1801844fa`: `Exec: Scheduled TrustedInstaller for auto-start because we pended the transaction.`
- `0x1801845d3`: `Exec: Scavenge on completion requested by session.`
- `0x180184071`: `If a transaction was already pending, then we must have pended the transaction again.`
- `0x1801841cd`: `Exec: Scheduled TrustedInstaller for auto-start because interactive drivers required a reboot.`

## pseudocode

```c
__int64 __fastcall CCbsExecutionObject::InstallUninstallChainInternal(
        CCbsExecutionObject *this,
        __int64 a2,
        BOOL *a3,
        int *a4,
        int *a5,
        __int64 a6,
        _DWORD *a7,
        _DWORD *a8,
        __int64 *a9,
        WCHAR *a10,
        union _CBS_VERSION *a11,
        union _CBS_VERSION *a12,
        wchar_t *a13,
        CCbsExecutionSpecialTransformers *a14,
        struct HDRIVERUPDATECONTEXT__ **a15,
        __int64 a16)
{
  union _CBS_VERSION *v16; // r12
  __int64 v18; // rbx
  BOOL *v19; // r15
  unsigned int v20; // r8d
  CCbsSession **v21; // r14
  CCbsSession *v22; // rax
  int v23; // eax
  int v24; // edi
  int v25; // edx
  __int64 v26; // rdx
  int v27; // edx
  __int64 v28; // r8
  unsigned int ProgressCost; // eax
  __int64 v30; // r11
  int v31; // eax
  int v32; // edx
  CCbsSession *v33; // rcx
  int IsTaskPackageAlreadySmartPended; // eax
  int v35; // edx
  CCbsSession *v37; // rcx
  int v38; // eax
  int v39; // eax
  unsigned int v40; // ebx
  int v41; // edx
  __int64 v42; // rdx
  int v43; // eax
  int v44; // edx
  int v45; // eax
  int v46; // edx
  __int64 v47; // rdx
  int v48; // eax
  int v49; // edx
  int v50; // edx
  int v51; // eax
  int v52; // edx
  int v53; // eax
  int v54; // edx
  __int64 v55; // rax
  _QWORD *v56; // r15
  _QWORD *v57; // r12
  int v58; // ecx
  int v59; // eax
  int v60; // edx
  int v61; // edx
  int v62; // edi
  __int64 v63; // rax
  int v64; // edi
  int ShouldTheExecutionSmartPended; // eax
  const wchar_t *v66; // rdx
  const wchar_t *v67; // rdx
  int IsOffline; // eax
  unsigned __int8 v69; // r15
  int v70; // edx
  unsigned int v71; // edi
  int v72; // eax
  unsigned int v73; // r15d
  int v74; // edx
  __int64 v75; // rdx
  union _CBS_VERSION *v76; // rcx
  int v77; // eax
  int v78; // edx
  int v79; // edx
  CCbsExecutionSpecialTransformers *v80; // r15
  int TransformersFromAnalysis; // eax
  int v82; // edx
  int v83; // eax
  int v84; // edx
  int v85; // eax
  int v86; // edx
  int v87; // eax
  int v88; // edx
  int v89; // r12d
  int v90; // eax
  int v91; // edx
  LPCWSTR v92; // rdx
  struct HDRIVERUPDATECONTEXT__ **v93; // rcx
  struct CCbsSession *v94; // rcx
  const char *v95; // r8
  const char *v96; // rdx
  int v97; // eax
  int v98; // edx
  int v99; // eax
  int v100; // edx
  unsigned int v101; // r15d
  int v102; // eax
  int v103; // edx
  struct CCbsSession *v104; // rcx
  unsigned int v105; // edi
  unsigned int v106; // eax
  CCbsSession *v107; // rcx
  int v108; // eax
  int v109; // edx
  struct CCbsSession *v110; // rcx
  unsigned int v111; // r8d
  unsigned int v112; // eax
  unsigned int v113; // eax
  unsigned int v114; // eax
  int v115; // r8d
  unsigned int v116; // ecx
  unsigned int v117; // eax
  unsigned int v118; // r8d
  CCbsSession *v119; // rcx
  int v120; // r8d
  __int64 v121; // rcx
  int v122; // r8d
  BOOL *v123; // r15
  int v124; // eax
  int OfflineWindowsDirectory; // eax
  const char *v126; // r8
  const WCHAR *v127; // rdi
  int v128; // eax
  int v129; // edx
  BOOL v130; // eax
  unsigned int v131; // eax
  char v132; // r12
  int v133; // edx
  unsigned int v134; // eax
  const char *v135; // r8
  int v136; // eax
  int v137; // edi
  const char *v138; // rdx
  int v139; // eax
  int v140; // edx
  __int64 *v141; // r15
  int v142; // eax
  int v143; // edx
  unsigned int v144; // eax
  CCbsSession *v145; // rcx
  unsigned int v146; // eax
  unsigned int v147; // eax
  __int64 v148; // rcx
  int v149; // eax
  int v150; // edx
  bool v151; // zf
  unsigned int v152; // eax
  int v153; // eax
  int v154; // edx
  char v155; // di
  const char *v156; // rdx
  const char *v157; // rdx
  unsigned int v158; // eax
  const char *v159; // rdx
  unsigned int v160; // eax
  __int64 v161; // rcx
  unsigned int v162; // eax
  unsigned int v163; // eax
  int v164; // [rsp+20h] [rbp-E0h]
  unsigned int *v165; // [rsp+20h] [rbp-E0h]
  struct ICSITransaction *v166; // [rsp+50h] [rbp-B0h] BYREF
  char v167; // [rsp+58h] [rbp-A8h]
  __int64 v168; // [rsp+60h] [rbp-A0h] BYREF
  bool v169; // [rsp+68h] [rbp-98h]
  int v170[4]; // [rsp+70h] [rbp-90h] BYREF
  int v171[2]; // [rsp+80h] [rbp-80h] BYREF
  BOOL *v172; // [rsp+88h] [rbp-78h]
  wchar_t *v173; // [rsp+90h] [rbp-70h] BYREF
  __int64 v174; // [rsp+98h] [rbp-68h]
  LPCWSTR lpExistingFileName; // [rsp+A0h] [rbp-60h] BYREF
  int *v176; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v177; // [rsp+B0h] [rbp-50h] BYREF
  union _CBS_VERSION *v178; // [rsp+B8h] [rbp-48h]
  __int64 *v179; // [rsp+C0h] [rbp-40h]
  struct HDRIVERUPDATECONTEXT__ **v180; // [rsp+C8h] [rbp-38h]
  int *v181; // [rsp+D0h] [rbp-30h] BYREF
  CCbsExecutionSpecialTransformers *v182; // [rsp+D8h] [rbp-28h]
  union _CBS_VERSION *v183; // [rsp+E0h] [rbp-20h]
  _DWORD *v184; // [rsp+E8h] [rbp-18h]
  _DWORD *v185; // [rsp+F0h] [rbp-10h]
  int *v186; // [rsp+F8h] [rbp-8h] BYREF
  int v187[2]; // [rsp+100h] [rbp+0h] BYREF
  int v188; // [rsp+108h] [rbp+8h] BYREF
  struct IUnknown *v189; // [rsp+110h] [rbp+10h] BYREF
  int v190; // [rsp+118h] [rbp+18h] BYREF
  unsigned int v191; // [rsp+11Ch] [rbp+1Ch] BYREF
  _BYTE v192[40]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v16 = a11;
  v182 = a14;
  v18 = 0;
  v19 = a3;
  v178 = a12;
  v181 = a5;
  *(_QWORD *)v171 = a6;
  v185 = a7;
  v184 = a8;
  v179 = a9;
  v173 = a13;
  v180 = a15;
  v174 = a16;
  v176 = a4;
  v172 = a3;
  v183 = a11;
  lpExistingFileName = a10;
  v177 = 0;
  LogAdapter::TraceAtLevel<>(1, "Perf: Execute chain started.");
  *(_OWORD *)v170 = CbsInstallUninstallStartEvent;
  CbsGenericEventReport(v170, L"Perf: Execute chain started.");
  v21 = (CCbsSession **)((char *)this + 64);
  v166 = 0;
  v168 = 0;
  v191 = 0;
  v190 = 0;
  v189 = 0;
  if ( *((_DWORD *)this + 10) || (v22 = *v21, v167 = 1, (*((_DWORD *)v22 + 173) & 0x4000) != 0) )
    v167 = 0;
  Windows::Rtl::StopWatch::StopWatch((Windows::Rtl::StopWatch *)v192, (CCbsSession *)((char *)*v21 + 304), v20);
  if ( !*((_DWORD *)this + 14) && !(unsigned int)CCbsSession::IsOffline(*v21) )
    *(_DWORD *)a10 = 7;
  v23 = CCbsExecutionObject::SetPendingStateforDelayedExecutedPackages(this, 15);
  v24 = v23;
  if ( v23 < 0 )
  {
    v188 = v23;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed setting pending state.");
      v186 = &v188;
      LOBYTE(v25) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v25,
        3,
        (unsigned int)": {}",
        (__int64)&v186);
    }
    v26 = 76;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectinstall.cpp",
      (const char *)(unsigned int)v24,
      v164);
LABEL_30:
    Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v192);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v189);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v168);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v166);
    return (unsigned int)v24;
  }
  SetRebootReason(*v21);
  if ( *((_QWORD *)this + 3) )
  {
    ProgressCost = CCbsExecutionObject::GetProgressCost(this);
    v31 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v30 + 32LL))(v30, 50, ProgressCost);
    v24 = v31;
    if ( v31 < 0 )
    {
      v190 = v31;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Exec: Client cancelled");
        *(_QWORD *)v187 = &v190;
        LOBYTE(v32) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v32,
          3,
          (unsigned int)": {}",
          (__int64)v187);
      }
      v26 = 91;
      goto LABEL_16;
    }
  }
  if ( *((_DWORD *)this + 24) )
    SetRebootReason(*v21);
  if ( (*((_BYTE *)*v21 + 688) & 0x40) != 0 )
  {
    *(_QWORD *)v170 = *((_QWORD *)*v21 + 80);
    if ( LogAdapter::g_Logger )
    {
      LOBYTE(v27) = 1;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        v27,
        1,
        (unsigned int)"Exec: Client forces reboot on session: {}",
        (__int64)v170);
    }
    v33 = *v21;
    v190 = 1;
    SetRebootReason(v33);
  }
  if ( !*((_DWORD *)this + 126) )
  {
    v188 = 0;
    IsTaskPackageAlreadySmartPended = CCbsExecutionObject::IsTaskPackageAlreadySmartPended(this, &v188);
    v24 = IsTaskPackageAlreadySmartPended;
    if ( IsTaskPackageAlreadySmartPended < 0 )
    {
      v188 = IsTaskPackageAlreadySmartPended;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to check whether package was already earlier pended.");
        *(_QWORD *)v170 = &v188;
        LOBYTE(v35) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v35,
          3,
          (unsigned int)": {}",
          (__int64)v170);
      }
      v26 = 125;
      goto LABEL_16;
    }
    if ( v188 )
    {
      LogAdapter::TraceAtLevel<>(
        1,
        "Exec: Task package already smart pended by earlier sessions, force package smart pend");
      *((_DWORD *)this + 13) = 1;
      v24 = 0;
      *v19 = 1;
      goto LABEL_30;
    }
  }
  v37 = *v21;
  v38 = *((_DWORD *)*v21 + 173);
  if ( (v38 & 0x80000) != 0 )
  {
    v39 = CCbsSession::CreateServicingCommitter(v37, 2, v28, &v177);
    v40 = v39;
    if ( v39 < 0 )
    {
      v188 = v39;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed creating committer for CIM based update");
        *(_QWORD *)v170 = &v188;
        LOBYTE(v41) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v41,
          3,
          (unsigned int)": {}",
          (__int64)v170);
      }
      v42 = 146;
LABEL_42:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v42,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectinstall.cpp",
        (const char *)v40,
        v164);
      Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v192);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v189);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v168);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v166);
      if ( v177 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v177 + 16LL))(v177);
      return v40;
    }
  }
  else
  {
    if ( (v38 & 0x400) == 0 )
      goto LABEL_46;
    v43 = CCbsSession::CreateServicingCommitter(v37, 3, v28, &v177);
    v40 = v43;
    if ( v43 < 0 )
    {
      v188 = v43;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed creating committer for Desktop update");
        *(_QWORD *)v170 = &v188;
        LOBYTE(v44) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v44,
          3,
          (unsigned int)": {}",
          (__int64)v170);
      }
      v42 = 155;
      goto LABEL_42;
    }
  }
  v18 = v177;
LABEL_46:
  Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v166);
  v165 = (unsigned int *)*((_QWORD *)this + 9);
  v45 = WcpCreateTransaction(&v168, *((_QWORD *)this + 11), 4, *v21);
  v24 = v45;
  if ( v45 < 0 )
  {
    v188 = v45;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to create CSI transaction for executing.");
      *(_QWORD *)v170 = &v188;
      LOBYTE(v46) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v46,
        3,
        (unsigned int)": {}",
        (__int64)v170);
    }
    v47 = 172;
LABEL_50:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v47,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectinstall.cpp",
      (const char *)(unsigned int)v24,
      (int)v165);
    goto LABEL_51;
  }
  v48 = DoqInitialize(*v21);
  v24 = v48;
  if ( v48 < 0 )
  {
    v188 = v48;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed initializing driver operation queue");
      *(_QWORD *)v170 = &v188;
      LOBYTE(v49) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v49,
        3,
        (unsigned int)": {}",
        (__int64)v170);
    }
    v47 = 175;
    goto LABEL_50;
  }
  *(_QWORD *)v170 = DoqCountDriverOperations(0, 0);
  v51 = CCbsExecutionObject::PrepareExecution((_DWORD)this, v50, (_DWORD)v166, v174, (__int64)&v190, v18);
  v24 = v51;
  if ( v51 < 0 )
  {
    v188 = v51;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to prepare execution");
      *(_QWORD *)v170 = &v188;
      LOBYTE(v52) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v52,
        3,
        (unsigned int)": {}",
        (__int64)v170);
    }
    v47 = 186;
    goto LABEL_50;
  }
  if ( !*((_DWORD *)*v21 + 363) )
  {
    LogAdapter::TraceAtLevel<>(1, "Plan: Start to process component watchlist");
    v53 = CCbsExecutionObject::ProcessComponentWatchList(this, v18);
    v24 = v53;
    if ( v53 < 0 )
    {
      v188 = v53;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to process component watch list.");
        *(_QWORD *)v170 = &v188;
        LOBYTE(v54) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v54,
          3,
          (unsigned int)": {}",
          (__int64)v170);
      }
      v47 = 201;
      goto LABEL_50;
    }
  }
  if ( (*((_DWORD *)*v21 + 173) & 0x80000) != 0 )
  {
    v55 = *((_QWORD *)*v21 + 307);
    if ( v55 )
    {
      v56 = *(_QWORD **)(v55 + 88);
      v57 = &v56[*(_QWORD *)(v55 + 72)];
      while ( 1 )
      {
        if ( v56 == v57 )
        {
          v19 = v172;
          v16 = v183;
          goto LABEL_73;
        }
        v24 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v18 + 72LL))(v18, *v56);
        if ( v24 < 0 )
          break;
        ++v56;
      }
      v188 = v24;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to set cim payload source for CIM based update.");
        *(_QWORD *)v170 = &v188;
        LOBYTE(v61) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v61,
          3,
          (unsigned int)": {}",
          (__int64)v170);
      }
      v47 = 209;
      goto LABEL_50;
    }
  }
LABEL_73:
  v58 = *((_DWORD *)*v21 + 173);
  if ( (v58 & 0x400) != 0 || (v58 & 0x80000) != 0 )
  {
    v59 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 80LL))(v18);
    v24 = v59;
    if ( v59 < 0 )
    {
      v188 = v59;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "finalizing changes using turbostack failed");
        *(_QWORD *)v170 = &v188;
        LOBYTE(v60) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v60,
          3,
          (unsigned int)": {}",
          (__int64)v170);
      }
      v47 = 216;
      goto LABEL_50;
    }
  }
  v62 = v190;
  if ( *((_DWORD *)this + 14) && (v190 & 1) != 0 )
  {
    LogAdapter::TraceAtLevel<>(
      1,
      "Exec: package or update requires restart but ignoring because it is being removed by deep clean, which means it was superseded");
    v62 &= ~1u;
    v190 = v62;
  }
  v63 = DoqCountDriverOperations(0, 0);
  *v179 = v63;
  if ( !*((_DWORD *)this + 14) && (v63 || (v62 & 1) != 0) )
    SetRebootReason(*v21);
  v64 = v62 & 1;
  v188 = v64;
  if ( v64 )
  {
    if ( !*((_DWORD *)this + 14) )
    {
      ShouldTheExecutionSmartPended = CCbsExecutionObject::ShouldTheExecutionSmartPended(this, 0);
      *((_DWORD *)this + 13) = ShouldTheExecutionSmartPended;
      if ( ShouldTheExecutionSmartPended || *((_BYTE *)*v21 + 2272) )
      {
        LogAdapter::TraceAtLevel<>(1, "Exec: package or update requires restart, delay the execution to shutdown.");
        *v19 = 1;
        RequireShutdownProcessing(1);
        LogAdapter::TraceAtLevel<>(
          1,
          "Exec: The Package or one of its Updates required and client specified DelayExecutionIfPendRequired, Execution "
          "will be delayed to system shutdown time.");
        SetServicingInProgress(*v21);
        PackageStoreCleanupCachedApplicabilityEvaluationPackage(*v21, v66);
LABEL_94:
        Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v192);
        Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v189);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v168);
        Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v166);
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        return 0;
      }
    }
  }
  if ( *(_QWORD *)(v174 + 24) )
  {
    PackageStoreWriteTimeStamp(*v21, L"LastModified_UTC");
    PackageStoreCleanupCachedApplicabilityEvaluationPackage(*v21, v67);
    PackageStoreMaintenanceActionSet(*v21, 2u, 0);
    PackageStoreMaintenanceActionSet(*v21, 0xFFFFu, 0);
  }
  v169 = (unsigned int)CCbsSession::IsOffline(*v21) || !*((_DWORD *)this + 24) && !v64;
  IsOffline = CCbsSession::IsOffline(*v21);
  v69 = v167;
  if ( IsOffline && v167 && *((_DWORD *)this + 24) )
  {
    v188 = -2146498554;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "CBS already has pended content.");
      *(_QWORD *)v170 = &v188;
      LOBYTE(v70) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v70,
        3,
        (unsigned int)": {}",
        (__int64)v170);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14B,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectinstall.cpp",
      (const char *)0x800F0806LL,
      (int)v165);
    Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v192);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v189);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v168);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v166);
    if ( !v18 )
      return 2148468742LL;
    goto LABEL_349;
  }
  if ( !(unsigned int)CCbsSession::IsOffline(*v21) )
    goto LABEL_151;
  if ( *((_QWORD *)this + 76) )
  {
    v76 = v178;
    *(_QWORD *)v16 = *((_QWORD *)this + 75);
    *(_QWORD *)v76 = *((_QWORD *)this + 76);
    v77 = CCbsOSVersionPublisher::SetOsVersions((CCbsOSVersionPublisher *)v173, v16, v76, 0);
    v24 = v77;
    if ( v77 < 0 )
    {
      v188 = v77;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed setting new OS versions");
        *(_QWORD *)v170 = &v188;
        LOBYTE(v78) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v78,
          3,
          (unsigned int)": {}",
          (__int64)v170);
      }
      v47 = 356;
      goto LABEL_50;
    }
  }
  else
  {
    CCbsOSVersionPublisher::GetOsVersions((CCbsOSVersionPublisher *)v173, v16, v178);
  }
  if ( !*((_DWORD *)this + 14) || v69 )
  {
    if ( v189 )
    {
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x18018487DLL);
    }
    v71 = 16 * v69;
    v72 = TransactionAnalyze(v166, v71, &GUID_7a8b78de_d107_46ca_812b_8e3f1c163270, &v189);
    v73 = v72;
    if ( v71 )
    {
      if ( v72 < 0 )
      {
        v188 = v72;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Analysis indicated that installation cannot succeed without pending.");
          *(_QWORD *)v170 = &v188;
          LOBYTE(v74) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v74,
            3,
            (unsigned int)": {}",
            (__int64)v170);
        }
        v75 = 383;
LABEL_130:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v75,
          (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectinstall.cpp",
          (const char *)v73,
          (int)v165);
        Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v192);
        Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v189);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v168);
        Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v166);
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        return v73;
      }
    }
    else if ( v72 < 0 )
    {
      v188 = v72;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get analysis of transaction.");
        *(_QWORD *)v170 = &v188;
        LOBYTE(v79) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v79,
          3,
          (unsigned int)": {}",
          (__int64)v170);
      }
      v75 = 387;
      goto LABEL_130;
    }
    v80 = v182;
    if ( !*((_DWORD *)this + 14) )
    {
      TransformersFromAnalysis = CCbsExecutionSpecialTransformers::GetTransformersFromAnalysis(
                                   v182,
                                   (struct ICSITransactionAnalysis *)v189);
      v24 = TransformersFromAnalysis;
      if ( TransformersFromAnalysis < 0 )
      {
        v188 = TransformersFromAnalysis;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed getting special transformers");
          *(_QWORD *)v170 = &v188;
          LOBYTE(v82) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v82,
            3,
            (unsigned int)": {}",
            (__int64)v170);
        }
        v47 = 394;
        goto LABEL_50;
      }
      v83 = CCbsExecutionSpecialTransformers::Save(v80, v16, v178);
      v24 = v83;
      if ( v83 < 0 )
      {
        v188 = v83;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed saving special transformers");
          *(_QWORD *)v170 = &v188;
          LOBYTE(v84) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v84,
            3,
            (unsigned int)": {}",
            (__int64)v170);
        }
        v47 = 398;
        goto LABEL_50;
      }
    }
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v189);
    if ( (unsigned int)CCbsExecutionSpecialTransformers::IsInstall(v80) )
    {
      v85 = CCbsOSVersionPublisher::SetOsVersions((CCbsOSVersionPublisher *)v173, 0, 0, v178);
      v24 = v85;
      if ( v85 < 0 )
      {
        v188 = v85;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed setting pnp target OS override");
          *(_QWORD *)v170 = &v188;
          LOBYTE(v86) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v86,
            3,
            (unsigned int)": {}",
            (__int64)v170);
        }
        v47 = 421;
        goto LABEL_50;
      }
      v87 = CCbsExecutionSpecialTransformers::ExecutePhase(v80, 0, v176);
      v24 = v87;
      if ( v87 < 0 )
      {
        v188 = v87;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed executing special install transformers");
          v176 = &v188;
          LOBYTE(v88) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v88,
            3,
            (unsigned int)": {}",
            (__int64)&v176);
        }
        v47 = 430;
        goto LABEL_50;
      }
    }
  }
  else
  {
LABEL_151:
    v80 = v182;
  }
  v89 = 0;
  if ( *v179 && v169 )
  {
    if ( !(unsigned int)CCbsSession::IsOffline(*v21) )
      SetExecuteState(0x10000u);
    v90 = DoqSave(*v21);
    v24 = v90;
    if ( v90 < 0 )
    {
      v188 = v90;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed saving driver operation queue");
        v176 = &v188;
        LOBYTE(v91) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v91,
          3,
          (unsigned int)": {}",
          (__int64)&v176);
      }
      v47 = 448;
      goto LABEL_50;
    }
    if ( (*((_DWORD *)*v21 + 173) & 0x4000) != 0 && (unsigned int)CCbsSession::IsOffline(*v21) )
    {
      SetExecuteState(0);
    }
    else
    {
      v92 = lpExistingFileName;
      v93 = v180;
      *v184 = 1;
      v165 = 0;
      v24 = DoqExecuteImmediate::Execute(v93, *(unsigned int *)v92, *v21, 0);
      if ( v24 < 0 )
      {
        if ( (unsigned int)CCbsSession::IsOffline(*v21) )
          TryToMarkImageAsNotServiceable(v94);
        v95 = "Doqe: Failed while processing driver operations queue interactively.";
        goto LABEL_167;
      }
      LogAdapter::TraceAtLevel<>(1, "Doqe: Driver operations completed successfully.");
      if ( (unsigned int)CCbsSession::IsOffline(*v21) )
      {
        v96 = "Doqe: Driver operations completed successfully.";
      }
      else
      {
        v89 = dword_1803B40DC;
        v96 = "Doqe: interactive driver operations completed.";
        if ( dword_1803B40DC )
          v96 = "Doqe: interactive driver operations completed but required a reboot.";
      }
      LogAdapter::TraceAtLevel<>(1, v96);
    }
  }
  if ( *((_QWORD *)v80 + 3) && !(unsigned int)CCbsExecutionSpecialTransformers::IsInstall(v80) )
  {
    v97 = CCbsOSVersionPublisher::SetOsVersions((CCbsOSVersionPublisher *)v173, 0, 0, v178);
    v24 = v97;
    if ( v97 < 0 )
    {
      v188 = v97;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed setting pnp target OS override");
        v176 = &v188;
        LOBYTE(v98) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v98,
          3,
          (unsigned int)": {}",
          (__int64)&v176);
      }
      v47 = 513;
      goto LABEL_50;
    }
    v99 = CCbsExecutionSpecialTransformers::ExecutePhase(v80, 1u, v181);
    v24 = v99;
    if ( v99 < 0 )
    {
      v188 = v99;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed executing special install transformers");
        v181 = &v188;
        LOBYTE(v100) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v100,
          3,
          (unsigned int)": {}",
          (__int64)&v181);
      }
      v47 = 522;
      goto LABEL_50;
    }
  }
  v101 = 0;
  if ( v169 )
  {
    if ( !*(_QWORD *)(v174 + 24) )
    {
      LogAdapter::TraceAtLevel<>(1, "Exec: Skipping transaction commit since nothing was changed.");
LABEL_186:
      v102 = CCbsSession::SaveCurrentBuildNumbers(*v21);
      v24 = v102;
      if ( v102 < 0 )
      {
        v188 = v102;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed setting current build numbers");
          *(_QWORD *)v171 = &v188;
          LOBYTE(v103) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v103,
            3,
            (unsigned int)": {}",
            (__int64)v171);
        }
        v47 = 731;
        goto LABEL_50;
      }
      if ( (int)CCbsSession::InvalidateWinnersPreload(*v21) < 0 )
        LogAdapter::TraceAtLevel<>(1, "Unable to invalidate for winners preload.");
      if ( (int)CCbsSession::InvalidateBaselinesPreload(*v21) < 0 )
        LogAdapter::TraceAtLevel<>(1, "Unable to invalidate for baselines preload.");
      goto LABEL_239;
    }
    if ( (unsigned int)CCbsSession::IsOffline(*v21) )
    {
      if ( v167 )
      {
        v105 = 1120;
      }
      else
      {
        v105 = 96;
        if ( (*((_DWORD *)v104 + 173) & 0x4000) != 0 )
          v105 = 97;
      }
      v106 = ConfigurePoqexecPendLocation(0, v104);
      LogAdapter::TraceAtLevelIfFailed<long,>(1, v106, "Unable to configure poqexec pend location.");
    }
    else
    {
      v105 = 102;
    }
    v107 = *v21;
    if ( (*((_DWORD *)*v21 + 173) & 0x80000) != 0 )
    {
      CCbsSession::CimSetupCleanup(v107);
      v108 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 88LL))(v18);
      v24 = v108;
      if ( v108 < 0 )
      {
        v188 = v108;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed finalizing pending changes");
          v181 = &v188;
          LOBYTE(v109) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v109,
            3,
            (unsigned int)": {}",
            (__int64)&v181);
        }
        v47 = 583;
        goto LABEL_50;
      }
      v191 = 1;
      goto LABEL_186;
    }
    v24 = TransactionCommit(v107, v166, v105, 1, &v191);
    v101 = v191 & 0xFFFF0000;
    v191 = (unsigned __int16)v191;
    if ( v24 >= 0 && *(_QWORD *)v178 && ((unsigned __int16)v191 == 1 || (unsigned __int16)v191 == 13) )
      **(_DWORD **)v171 = 1;
    if ( !(unsigned int)CCbsSession::IsOffline(*v21) && *v179 )
    {
      if ( v24 < 0 || v111 != 5 && v111 > 2 && v111 < 8 )
      {
        LogAdapter::TraceAtLevel<>(
          1,
          "Doqe: primitives did not complete, so rolling back interactive driver operations.");
        v165 = 0;
        v112 = DoqExecuteImmediate::Execute(v180, *(unsigned int *)lpExistingFileName, *v21, 1);
        LogAdapter::TraceAtLevelHr<long,>(3, v112, "Doqe: Failed undoing interactive driver operations.");
        *v184 = 0;
        v110 = *v21;
      }
      if ( (*(_BYTE *)lpExistingFileName & 2) != 0 )
      {
        v113 = DoqExecuteImmediate::Finalize((DoqExecuteImmediate *)v180, v110);
        LogAdapter::TraceAtLevelIfFailed<long,>(1, v113, "Unable to finalize driver installs");
        v110 = *v21;
      }
      if ( !v89 )
        v89 = dword_1803B40DC;
      v114 = DoqClear(v110, 0);
      LogAdapter::TraceAtLevelIfFailed<long,>(1, v114, "Unable to clear the live driver operations key");
    }
    if ( (unsigned int)CCbsSession::IsOffline(*v21) )
    {
      if ( v24 < 0 )
        goto LABEL_227;
      if ( v115 == 6 )
        goto LABEL_223;
      if ( v115 == 8 || v115 == 14 )
LABEL_227:
        TryToMarkImageAsNotServiceable(*v21);
      v116 = (*((_DWORD *)*v21 + 173) & 0x4000) == 0 ? 3 : 0;
    }
    else
    {
      v117 = ClearCurrentBuildNumbers(*v21);
      LogAdapter::TraceAtLevelIfFailed<long,>(3, v117, "Unable to clear current build numbers");
      v116 = -1;
    }
    SetExecuteState(v116);
    if ( v24 >= 0 )
      goto LABEL_186;
    if ( !(unsigned int)CCbsSession::IsOffline(*v21) && v24 == -2146885628 )
    {
      LogAdapter::TraceAtLevelIfFailed<long,>(1, 2148081668LL, "Mismatched catalog, mark store as corrupt.");
      CCbsSession::MarkPackageStoreCorrupt(*v21);
    }
    v95 = "Exec: Failed to commit CSI transaction to execute changes.";
LABEL_167:
    LogAdapter::TraceAtLevelHr<long,>(3, (unsigned int)v24, v95);
    goto LABEL_51;
  }
LABEL_239:
  v118 = v191;
  if ( v191 - 6 <= 2 )
  {
    if ( (v101 & 0x10000) != 0 )
    {
      v159 = "Exec: Transaction failed, and an advanced installer required a reboot.";
    }
    else
    {
      if ( !v89 )
        goto LABEL_356;
      v159 = "Exec: Transaction failed, and interactive drivers required a reboot.";
    }
    LogAdapter::TraceAtLevel<>(1, v159);
    RequireShutdownProcessing(1);
    v118 = v191;
LABEL_356:
    if ( v118 == 7 )
    {
      v160 = SetTrustedInstallerAutoStart(*v21);
      LogAdapter::TraceAtLevelHr<long,>(
        1,
        v160,
        "Exec: Scheduled TrustedInstaller for auto-start because rollback was pended.");
      RequireShutdownProcessing(1);
      v24 = -2147021879;
      LogAdapter::TraceAtLevelHr<long,>(
        3,
        2147945417LL,
        "Exec: An error occurred while committing the transaction and the transaction rollback requires a reboot.");
      Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v192);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v189);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v168);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v166);
      if ( !v18 )
        return (unsigned int)v24;
      goto LABEL_52;
    }
    v161 = *((_QWORD *)this + 11);
    LODWORD(v165) = 0;
    v188 = 0;
    v162 = PackageStoreCancelPendingTransaction(v161, v168, 0, &v188, v165, 0);
    LogAdapter::TraceAtLevelHr<long,>(1, v162, "Exec: Cancelled pending transactions after rollback.");
    DeletePoqexecFromCcpConfig(*v21);
    v163 = ConfigurePoqexecPendLocation(1, *v21);
    LogAdapter::TraceAtLevelIfFailed<long,>(1, v163, "Unable to set flag to pend PoqExec in SetupExecute.");
    if ( v191 != 6 )
    {
      LogAdapter::TraceAtLevelHr<long,>(
        3,
        2148469026LL,
        "Exec: An error occurred while committing the transaction, the transaction could not be rolled back.");
      Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v192);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v189);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v168);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v166);
      if ( v18 )
LABEL_361:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      return 2148469026LL;
    }
LABEL_223:
    LogAdapter::TraceAtLevelHr<long,>(
      3,
      2148469026LL,
      "Exec: An error occurred while committing the transaction, the transaction has been rolled back.");
    Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v192);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v189);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v168);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v166);
    if ( v18 )
      goto LABEL_361;
    return 2148469026LL;
  }
  if ( (unsigned int)CCbsSession::IsOffline(*v21) )
  {
    if ( CCbsSession::IsOfflineUnitTestMode(v119) && (*(_BYTE *)(v121 + 688) & 0x40) != 0
      || (*(_DWORD *)(v121 + 692) & 0x4000) != 0 )
    {
      v123 = v172;
      *v172 = 1;
      goto LABEL_264;
    }
    if ( v122 != 1 )
    {
      v130 = *((_DWORD *)this + 24) || *(_QWORD *)(v174 + 24);
      v123 = v172;
      *v172 = v130;
LABEL_264:
      if ( !*((_QWORD *)*v21 + 182) )
      {
        v131 = SetTrustedInstallerAutoStart(*v21);
        LogAdapter::TraceAtLevelHr<long,>(
          1,
          v131,
          "Exec: Pended transaction, changes will be applied during startup processing. Scheduled TrustedInstaller for auto-start.");
      }
      goto LABEL_266;
    }
    LogAdapter::TraceAtLevel<>(1, "Exec: Offline commit completes with no pending online operations.");
    *v185 = 1;
    if ( *((_DWORD *)this + 24) )
      LogAdapter::TraceAtLevel<>(
        1,
        "Exec: Although the offline commit completed immediately, CBS has to consider it pended due to a previous operation.");
    v124 = *((_DWORD *)this + 24);
    v123 = v172;
    v173 = 0;
    lpExistingFileName = 0;
    *v172 = v124;
    OfflineWindowsDirectory = CCbsSession::GetOfflineWindowsDirectory(*v21, &v173);
    if ( OfflineWindowsDirectory >= 0 )
    {
      OfflineWindowsDirectory = SczAllocConcat2Sz(&lpExistingFileName, v173, L"Servicing\\cbs_pbr_package_list.txt");
      if ( OfflineWindowsDirectory >= 0 )
      {
        v127 = lpExistingFileName;
        if ( (unsigned int)DoesFileExist(lpExistingFileName, 0) )
        {
          v128 = CbsSetAttrAndDeleteFile(v127);
          *(_QWORD *)v171 = v127;
          if ( v128 >= 0 )
          {
            if ( LogAdapter::g_Logger )
            {
              LOBYTE(v129) = 1;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                v129,
                1,
                (unsigned int)"Exec: Removed package list file from {}",
                (__int64)v171);
            }
          }
          else
          {
            LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
              1,
              (unsigned int)v128,
              "Unable to remove package list file: {}",
              v171);
          }
        }
        goto LABEL_258;
      }
      v126 = "Unable to allocate package list path";
    }
    else
    {
      v126 = "Unable to get offline boot directory";
    }
    LogAdapter::TraceAtLevelIfFailed<long,>(1, (unsigned int)OfflineWindowsDirectory, v126);
LABEL_258:
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v173);
    goto LABEL_264;
  }
  if ( !*((_DWORD *)this + 24) && !v188 && (unsigned int)(v120 - 3) > 1 )
  {
    *v185 = 1;
    if ( (v101 & 0x10000) != 0 )
    {
      LogAdapter::TraceAtLevel<>(1, "Exec: Advanced installer executed successfully but still required a reboot.");
      v123 = v172;
      *v172 = 1;
      if ( !*((_DWORD *)*v21 + 317) )
        *((_DWORD *)*v21 + 317) = 9;
      v134 = SetTrustedInstallerAutoStart(*v21);
      v135 = "Exec: Scheduled TrustedInstaller for auto-start because we pended the transaction.";
    }
    else
    {
      if ( !v89 )
      {
        v123 = v172;
        goto LABEL_288;
      }
      LogAdapter::TraceAtLevel<>(1, "Exec: Interactive drivers executed successfully but still required a reboot.");
      v123 = v172;
      *v172 = 1;
      if ( !*((_DWORD *)*v21 + 317) )
        *((_DWORD *)*v21 + 317) = 11;
      SetRebootReason(*v21);
      v134 = SetTrustedInstallerAutoStart(*v21);
      v135 = "Exec: Scheduled TrustedInstaller for auto-start because interactive drivers required a reboot.";
    }
    LogAdapter::TraceAtLevelHr<long,>(1, v134, v135);
    RequireShutdownProcessing(1);
LABEL_288:
    if ( *v123 )
      SetServicingInProgress(*v21);
    v132 = v190;
    if ( (v190 & 2) != 0 && !*((_DWORD *)this + 14) )
      *((_DWORD *)this + 124) = 1;
    goto LABEL_267;
  }
  v136 = CCbsExecutionObject::ShouldTheExecutionSmartPended(this, 0);
  v137 = v136;
  if ( v188 )
  {
    if ( v136 )
    {
      RequireShutdownProcessing(1);
      v138 = "Exec: The Package or one of its Updates required and client specified DelayExecutionIfPendRequired, Executi"
             "on will be delayed to system shutdown time.";
    }
    else
    {
      v138 = "Exec: The Package or one of its Updates required a reboot so transaction commit was skipped, Package's chan"
             "ges need to be pended.";
    }
  }
  else
  {
    if ( v136 )
    {
      LogAdapter::TraceAtLevel<>(
        1,
        "Exec: Failed to commit CSI transaction due to file in use or Component reboot required and client specified Dela"
        "yExecutionIfPendRequired, Execution will be delayed to system shutdown time.");
      RequireShutdownProcessing(1);
      goto LABEL_301;
    }
    v138 = "Exec: Failed to commit CSI transaction due to file in use or Component reboot required, package changes need to be pended.";
  }
  LogAdapter::TraceAtLevel<>(1, v138);
LABEL_301:
  if ( !*((_DWORD *)this + 10) )
  {
    LogAdapter::TraceAtLevel<>(1, "Exec: Client did not specify to pend if necessary, no changes have been applied.");
    Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v192);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v189);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v168);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v166);
    if ( !v18 )
      return 2148468742LL;
LABEL_349:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    return 2148468742LL;
  }
  if ( !v137 )
  {
    v139 = DoqSave(*v21);
    v24 = v139;
    if ( v139 < 0 )
    {
      v188 = v139;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed saving driver operation queue");
        *(_QWORD *)v171 = &v188;
        LOBYTE(v140) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v140,
          3,
          (unsigned int)": {}",
          (__int64)v171);
      }
      v47 = 1014;
      goto LABEL_50;
    }
    if ( !*(_QWORD *)(v174 + 24) )
    {
      LogAdapter::TraceAtLevel<>(1, "Exec: Skipping transaction pend since nothing was changed.");
      v141 = v179;
      goto LABEL_309;
    }
    SetExecuteState(0x14u);
    v141 = v179;
    v144 = ConfigurePoqexecPendLocation(*v179 == 0, *v21);
    LogAdapter::TraceAtLevelIfFailed<long,>(1, v144, "Unable to configure poqexec pend location.");
    v145 = *v21;
    if ( (*((_DWORD *)*v21 + 173) & 0x80000) != 0 )
    {
      CCbsSession::CimSetupCleanup(v145);
      goto LABEL_309;
    }
    v24 = TransactionCommit(v145, v166, 0x2Fu, 1, &v191);
    if ( v24 >= 0 )
    {
LABEL_309:
      if ( (*((_DWORD *)*v21 + 173) & 0x80000) != 0 )
      {
        v142 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 88LL))(v18);
        v24 = v142;
        if ( v142 < 0 )
        {
          v188 = v142;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed finalizing pending changes");
            *(_QWORD *)v171 = &v188;
            LOBYTE(v143) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v143,
              3,
              (unsigned int)": {}",
              (__int64)v171);
          }
          v47 = 1084;
          goto LABEL_50;
        }
      }
      v149 = CCbsSession::SaveCurrentBuildNumbers(*v21);
      v24 = v149;
      if ( v149 < 0 )
      {
        v188 = v149;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed setting current build numbers");
          *(_QWORD *)v171 = &v188;
          LOBYTE(v150) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v150,
            3,
            (unsigned int)": {}",
            (__int64)v171);
        }
        v47 = 1087;
        goto LABEL_50;
      }
      v151 = *v141 == 0;
      v123 = v172;
      *((_DWORD *)this + 26) = v151;
      *v123 = 1;
      LogAdapter::TraceAtLevel<>(
        1,
        "Exec: Pended transaction, changes will be applied during shutdown/startup processing.");
      v152 = SetTrustedInstallerAutoStart(*v21);
      LogAdapter::TraceAtLevelHr<long,>(
        1,
        v152,
        "Exec: Scheduled TrustedInstaller for auto-start because we pended the transaction.");
      if ( (*((_DWORD *)*v21 + 173) & 0x80000) != 0 )
        LogAdapter::TraceAtLevel<>(1, "Exec: Skipping shutdown processing as it is using CIM based update flow.");
      else
        RequireShutdownProcessing(1);
      goto LABEL_328;
    }
    if ( !*(_QWORD *)v170 )
    {
      v146 = ConfigurePoqexecPendLocation(1, *v21);
      LogAdapter::TraceAtLevelIfFailed<long,>(1, v146, "Unable to configure poqexec pend location.");
    }
    LogAdapter::TraceAtLevel<>(1, "Exec: Restoring driver operations because of a CSI commit failure.");
    v147 = DoqUndoSave(*v21);
    LogAdapter::TraceAtLevelIfFailed<long,>(1, v147, "Exec: Failed restoring driver operations queue");
    SetExecuteState(0xFFFFFFFF);
    LogAdapter::TraceAtLevelHr<long,unsigned long>(
      v148,
      (unsigned int)v24,
      "Exec: Failed to pend CSI transaction because transactions cannot be merged: {}.",
      &v191);
LABEL_51:
    Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v192);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v189);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v168);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v166);
    if ( !v18 )
      return (unsigned int)v24;
LABEL_52:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    return (unsigned int)v24;
  }
  v123 = v172;
  *((_DWORD *)this + 13) = 1;
  *v123 = 1;
LABEL_328:
  SetServicingInProgress(*v21);
LABEL_266:
  v132 = v190;
LABEL_267:
  if ( !*((_DWORD *)this + 24) )
    goto LABEL_367;
  if ( *v123 )
    goto LABEL_334;
  if ( !*(_QWORD *)(v174 + 24) )
  {
LABEL_367:
    if ( !*v123 )
    {
      v153 = DoqExecuteImmediate::NotifyVersionChange(v180, *v21);
      v24 = v153;
      if ( v153 < 0 )
      {
        v188 = v153;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to notify PNP of possible OS version change.");
          *(_QWORD *)v171 = &v188;
          LOBYTE(v154) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v154,
            3,
            (unsigned int)": {}",
            (__int64)v171);
        }
        v47 = 1178;
        goto LABEL_50;
      }
    }
LABEL_334:
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v166);
    if ( *((_DWORD *)*v21 + 367) )
    {
      v155 = 1;
      v156 = "Exec: Scavenge on completion requested by session.";
    }
    else if ( (unsigned int)CCbsSession::IsOffline(*v21) && (v132 & 4) != 0 && !*((_DWORD *)this + 14) )
    {
      v155 = 1;
      v156 = "Exec: Scavenge for offline operation requiring cleanup requested.";
    }
    else
    {
      v155 = 0;
      v156 = "Exec: Scavenge not requested.";
    }
    LogAdapter::TraceAtLevel<>(1, v156);
    if ( !v155 )
      goto LABEL_94;
    if ( (*((_DWORD *)*v21 + 173) & 0x20000) != 0 )
    {
      v157 = "Exec: Scavenge not allowed by session request.";
    }
    else
    {
      if ( !*v123 )
      {
        DoqExecuteImmediate::Close((DoqExecuteImmediate *)v180);
        v158 = PackageStoreCsiScavenge(*v21, 0, 0, 0, 0, 0, 0, 0, 0);
        LogAdapter::TraceAtLevelIfFailed<long,>(2, v158, "Scavenge: Unable to scavenge offline store immediately");
        goto LABEL_94;
      }
      v157 = "Exec: Scavenge not allowed due to pended transaction.";
    }
    LogAdapter::TraceAtLevel<>(1, v157);
    goto LABEL_94;
  }
  v188 = -2146498560;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      LogAdapter::g_Logger,
      0,
      3,
      "If a transaction was already pending, then we must have pended the transaction again.");
    *(_QWORD *)v171 = &v188;
    LOBYTE(v133) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v133,
      3,
      (unsigned int)": {}",
      (__int64)v171);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x496,
    (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectinstall.cpp",
    (const char *)0x800F0800LL,
    (int)v165);
  Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v192);
  Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v189);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v168);
  Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v166);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  return 2148468736LL;
}

```

## disassembly

```asm
0x1801829cc  mov     [rsp-8+arg_8], rbx
0x1801829d1  push    rbp
0x1801829d2  push    rsi
0x1801829d3  push    rdi
0x1801829d4  push    r12
0x1801829d6  push    r13
0x1801829d8  push    r14
0x1801829da  push    r15
0x1801829dc  lea     rbp, [rsp-50h]
0x1801829e1  sub     rsp, 150h
0x1801829e8  mov     rax, cs:__security_cookie
0x1801829ef  xor     rax, rsp
0x1801829f2  mov     [rbp+80h+var_38], rax
0x1801829f6  mov     rax, [rbp+80h+arg_68]
0x1801829fd  lea     rdx, aPerfExecuteCha; "Perf: Execute chain started."
0x180182a04  mov     r12, [rbp+80h+arg_50]
0x180182a0b  xor     esi, esi
0x180182a0d  mov     rdi, [rbp+80h+arg_48]
0x180182a14  mov     r13, rcx
0x180182a17  mov     [rbp+80h+var_A8], rax
0x180182a1b  mov     ebx, esi
0x180182a1d  mov     rax, [rbp+80h+arg_58]
0x180182a24  mov     r15, r8
0x180182a27  mov     [rbp+80h+var_C8], rax
0x180182a2b  lea     ecx, [rsi+1]
0x180182a2e  mov     rax, [rbp+80h+arg_20]
0x180182a35  mov     [rbp+80h+var_B0], rax
0x180182a39  mov     rax, [rbp+80h+arg_28]
0x180182a40  mov     qword ptr [rbp+80h+var_100], rax
0x180182a44  mov     rax, [rbp+80h+arg_30]
0x180182a4b  mov     [rbp+80h+var_90], rax
0x180182a4f  mov     rax, [rbp+80h+arg_38]
0x180182a56  mov     [rbp+80h+var_98], rax
0x180182a5a  mov     rax, [rbp+80h+arg_40]
0x180182a61  mov     [rbp+80h+var_C0], rax
0x180182a65  mov     rax, [rbp+80h+arg_60]
0x180182a6c  mov     [rbp+80h+var_F0], rax
0x180182a70  mov     rax, [rbp+80h+arg_70]
0x180182a77  mov     [rbp+80h+var_B8], rax
0x180182a7b  mov     rax, [rbp+80h+arg_78]
0x180182a82  mov     [rbp+80h+var_E8], rax
0x180182a86  mov     [rbp+80h+var_D8], r9
0x180182a8a  mov     [rbp+80h+var_F8], r8
0x180182a8e  mov     [rbp+80h+var_A0], r12
0x180182a92  mov     [rbp+80h+lpExistingFileName], rdi
0x180182a96  mov     [rbp+80h+var_D0], rbx
0x180182a9a  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x180182a9f  movups  xmm0, cs:CbsInstallUninstallStartEvent
0x180182aa6  lea     rdx, aPerfExecuteCha_0; "Perf: Execute chain started."
0x180182aad  lea     rcx, [rsp+180h+var_110]
0x180182ab2  movdqu  xmmword ptr [rsp+180h+var_110], xmm0
0x180182ab8  call    CbsGenericEventReport
0x180182abd  lea     r14, [r13+40h]
0x180182ac1  mov     [rsp+180h+var_130], rsi
0x180182ac6  mov     [rsp+180h+var_120], rsi
0x180182acb  mov     [rbp+80h+var_64], esi
0x180182ace  mov     [rbp+80h+var_68], esi
0x180182ad1  mov     [rbp+80h+var_70], rsi
0x180182ad5  cmp     [r13+28h], esi
0x180182ad9  jnz     short loc_180182AEF
0x180182adb  mov     rax, [r14]
0x180182ade  mov     [rsp+180h+var_128], 1
0x180182ae3  test    dword ptr [rax+2B4h], 4000h
0x180182aed  jz      short loc_180182AF4
0x180182aef  mov     [rsp+180h+var_128], sil
0x180182af4  mov     rdx, [r14]
0x180182af7  lea     rcx, [rbp+80h+var_60]; this
0x180182afb  add     rdx, 130h; struct Windows::Rtl::StopWatch *
0x180182b02  call    ??0StopWatch@Rtl@Windows@@QEAA@PEAV012@K@Z; Windows::Rtl::StopWatch::StopWatch(Windows::Rtl::StopWatch *,ulong)
0x180182b07  cmp     [r13+38h], esi
0x180182b0b  jnz     short loc_180182B1F
0x180182b0d  mov     rcx, [r14]; this
0x180182b10  call    ?IsOffline@CCbsSession@@QEBAHXZ; CCbsSession::IsOffline(void)
0x180182b15  test    eax, eax
0x180182b17  jnz     short loc_180182B1F
0x180182b19  mov     dword ptr [rdi], 7
0x180182b1f  xor     r8d, r8d
0x180182b22  mov     rcx, r13
0x180182b25  lea     edx, [r8+0Fh]
0x180182b29  call    ?SetPendingStateforDelayedExecutedPackages@CCbsExecutionObject@@AEAAJW4CbsStoreObjectType@@H@Z; CCbsExecutionObject::SetPendingStateforDelayedExecutedPackages(CbsStoreObjectType,int)
0x180182b2e  mov     edi, eax
0x180182b30  test    eax, eax
0x180182b32  jns     short loc_180182B8C
0x180182b34  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182b3b  mov     [rbp+80h+var_78], eax
0x180182b3e  test    rcx, rcx
0x180182b41  jz      short loc_180182B82
0x180182b43  mov     esi, 3
0x180182b48  lea     r9, aFailedSettingP_3; "Failed setting pending state."
0x180182b4f  mov     r8d, esi
0x180182b52  xor     edx, edx
0x180182b54  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180182b59  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182b60  lea     rax, [rbp+80h+var_78]
0x180182b64  mov     [rbp+80h+var_88], rax
0x180182b68  lea     r9, asc_1802EE7AC; ": {}"
0x180182b6f  lea     rax, [rbp+80h+var_88]
0x180182b73  mov     r8d, esi
0x180182b76  mov     dl, 1
0x180182b78  mov     [rsp+180h+var_160], rax
0x180182b7d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180182b82  mov     edx, 4Ch ; 'L'
0x180182b87  jmp     loc_180182C23
0x180182b8c  mov     rcx, [r14]; this
0x180182b8f  xor     edx, edx
0x180182b91  call    SetRebootReason
0x180182b96  mov     r11, [r13+18h]
0x180182b9a  test    r11, r11
0x180182b9d  jz      loc_180182C3E
0x180182ba3  mov     rcx, r13; this
0x180182ba6  call    ?GetProgressCost@CCbsExecutionObject@@AEAAKXZ; CCbsExecutionObject::GetProgressCost(void)
0x180182bab  mov     rdx, [r11]
0x180182bae  mov     r9d, 1
0x180182bb4  mov     r8d, eax
0x180182bb7  mov     rcx, r11
0x180182bba  mov     r10, [rdx+20h]
0x180182bbe  lea     edx, [r9+31h]
0x180182bc2  mov     rax, r10
0x180182bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180182bca  mov     edi, eax
0x180182bcc  test    eax, eax
0x180182bce  jns     short loc_180182C3E
0x180182bd0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182bd7  mov     [rbp+80h+var_68], eax
0x180182bda  test    rcx, rcx
0x180182bdd  jz      short loc_180182C1E
0x180182bdf  mov     esi, 3
0x180182be4  lea     r9, aExecClientCanc; "Exec: Client cancelled"
0x180182beb  mov     r8d, esi
0x180182bee  xor     edx, edx
0x180182bf0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180182bf5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182bfc  lea     rax, [rbp+80h+var_68]
0x180182c00  mov     qword ptr [rbp+80h+var_80], rax
0x180182c04  lea     r9, asc_1802EE7AC; ": {}"
0x180182c0b  lea     rax, [rbp+80h+var_80]
0x180182c0f  mov     r8d, esi
0x180182c12  mov     dl, 1
0x180182c14  mov     [rsp+180h+var_160], rax; int
0x180182c19  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180182c1e  mov     edx, 5Bh ; '['; void *
0x180182c23  mov     rcx, [rbp+88h]; this
0x180182c2a  lea     r8, aOnecoreBaseCbs_38; "onecore\\base\\cbs\\core\\cbsexecutiono"...
0x180182c31  mov     r9d, edi; char *
0x180182c34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180182c39  jmp     loc_180182D45
0x180182c3e  cmp     [r13+60h], esi
0x180182c42  jz      short loc_180182C51
0x180182c44  mov     rcx, [r14]; this
0x180182c47  mov     edx, 9
0x180182c4c  call    SetRebootReason
0x180182c51  mov     rax, [r14]
0x180182c54  test    byte ptr [rax+2B0h], 40h
0x180182c5b  jz      short loc_180182CA8
0x180182c5d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182c64  mov     rax, [rax+280h]
0x180182c6b  mov     qword ptr [rsp+180h+var_110], rax
0x180182c70  test    rcx, rcx
0x180182c73  jz      short loc_180182C94
0x180182c75  mov     r8d, 1
0x180182c7b  lea     rax, [rsp+180h+var_110]
0x180182c80  mov     dl, r8b
0x180182c83  mov     [rsp+180h+var_160], rax
0x180182c88  lea     r9, aExecClientForc; "Exec: Client forces reboot on session: "...
0x180182c8f  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180182c94  mov     rcx, [r14]; this
0x180182c97  mov     edx, 5
0x180182c9c  mov     [rbp+80h+var_68], 1
0x180182ca3  call    SetRebootReason
0x180182ca8  cmp     [r13+1F8h], esi
0x180182caf  jnz     loc_180182D72
0x180182cb5  lea     rdx, [rbp+80h+var_78]; int *
0x180182cb9  mov     [rbp+80h+var_78], esi
0x180182cbc  mov     rcx, r13; this
0x180182cbf  call    ?IsTaskPackageAlreadySmartPended@CCbsExecutionObject@@QEAAJPEAH@Z; CCbsExecutionObject::IsTaskPackageAlreadySmartPended(int *)
0x180182cc4  mov     edi, eax
0x180182cc6  test    eax, eax
0x180182cc8  jns     short loc_180182D24
0x180182cca  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182cd1  mov     [rbp+80h+var_78], eax
0x180182cd4  test    rcx, rcx
0x180182cd7  jz      short loc_180182D1A
0x180182cd9  mov     esi, 3
0x180182cde  lea     r9, aFailedToCheckW_10; "Failed to check whether package was alr"...
0x180182ce5  mov     r8d, esi
0x180182ce8  xor     edx, edx
0x180182cea  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180182cef  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182cf6  lea     rax, [rbp+80h+var_78]
0x180182cfa  mov     qword ptr [rsp+180h+var_110], rax
0x180182cff  lea     r9, asc_1802EE7AC; ": {}"
0x180182d06  lea     rax, [rsp+180h+var_110]
0x180182d0b  mov     r8d, esi
0x180182d0e  mov     dl, 1
0x180182d10  mov     [rsp+180h+var_160], rax
0x180182d15  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180182d1a  mov     edx, 7Dh ; '}'
0x180182d1f  jmp     loc_180182C23
0x180182d24  cmp     [rbp+80h+var_78], esi
0x180182d27  jz      short loc_180182D72
0x180182d29  mov     ebx, 1
0x180182d2e  lea     rdx, aExecTaskPackag; "Exec: Task package already smart pended"...
0x180182d35  mov     ecx, ebx
0x180182d37  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x180182d3c  mov     [r13+34h], ebx
0x180182d40  mov     edi, esi
0x180182d42  mov     [r15], ebx
0x180182d45  lea     rcx, [rbp+80h+var_60]; this
0x180182d49  call    ??1StopWatch@Rtl@Windows@@QEAA@XZ; Windows::Rtl::StopWatch::~StopWatch(void)
0x180182d4e  lea     rcx, [rbp+80h+var_70]
0x180182d52  call    ?Close@?$AutoComPtr@UIEnumCSI_PENDING_TRANSACTION@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(void)
0x180182d57  lea     rcx, [rsp+180h+var_120]
0x180182d5c  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x180182d61  lea     rcx, [rsp+180h+var_130]
0x180182d66  call    ?Close@?$AutoComPtr@UIEnumCSI_PENDING_TRANSACTION@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(void)
0x180182d6b  mov     eax, edi
0x180182d6d  jmp     loc_18018484B
0x180182d72  mov     rcx, [r14]
0x180182d75  mov     esi, 3
0x180182d7a  mov     eax, [rcx+2B4h]
0x180182d80  bt      eax, 13h
0x180182d84  jnb     short loc_180182DEE
0x180182d86  lea     r9, [rbp+80h+var_D0]
0x180182d8a  lea     edx, [rsi-1]
0x180182d8d  call    ?CreateServicingCommitter@CCbsSession@@QEAAJW4InitializeScenario@IServicingCommitter@@PEAUICSIStore@@PEAV?$AutoComPtr@VIServicingCommitter@@@Windows@@@Z; CCbsSession::CreateServicingCommitter(IServicingCommitter::InitializeScenario,ICSIStore *,Windows::AutoComPtr<IServicingCommitter> *)
0x180182d92  mov     ebx, eax
0x180182d94  test    eax, eax
0x180182d96  jns     loc_180182EB5
0x180182d9c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182da3  mov     [rbp+80h+var_78], eax
0x180182da6  test    rcx, rcx
0x180182da9  jz      short loc_180182DE7
0x180182dab  lea     r9, aFailedCreating_6; "Failed creating committer for CIM based"...
0x180182db2  mov     r8d, esi
0x180182db5  xor     edx, edx
0x180182db7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180182dbc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182dc3  lea     rax, [rbp+80h+var_78]
0x180182dc7  mov     qword ptr [rsp+180h+var_110], rax
0x180182dcc  lea     r9, asc_1802EE7AC; ": {}"
0x180182dd3  lea     rax, [rsp+180h+var_110]
0x180182dd8  mov     r8d, esi
0x180182ddb  mov     dl, 1
0x180182ddd  mov     [rsp+180h+var_160], rax
0x180182de2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180182de7  mov     edx, 92h
0x180182dec  jmp     short loc_180182E5D
0x180182dee  bt      eax, 0Ah
0x180182df2  jnb     loc_180182EB9
0x180182df8  lea     r9, [rbp+80h+var_D0]
0x180182dfc  mov     edx, esi
0x180182dfe  call    ?CreateServicingCommitter@CCbsSession@@QEAAJW4InitializeScenario@IServicingCommitter@@PEAUICSIStore@@PEAV?$AutoComPtr@VIServicingCommitter@@@Windows@@@Z; CCbsSession::CreateServicingCommitter(IServicingCommitter::InitializeScenario,ICSIStore *,Windows::AutoComPtr<IServicingCommitter> *)
0x180182e03  mov     ebx, eax
0x180182e05  test    eax, eax
0x180182e07  jns     loc_180182EB5
0x180182e0d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182e14  mov     [rbp+80h+var_78], eax
0x180182e17  test    rcx, rcx
0x180182e1a  jz      short loc_180182E58
0x180182e1c  lea     r9, aFailedCreating_2; "Failed creating committer for Desktop u"...
0x180182e23  mov     r8d, esi
0x180182e26  xor     edx, edx
0x180182e28  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180182e2d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182e34  lea     rax, [rbp+80h+var_78]
0x180182e38  mov     qword ptr [rsp+180h+var_110], rax
0x180182e3d  lea     r9, asc_1802EE7AC; ": {}"
0x180182e44  lea     rax, [rsp+180h+var_110]
0x180182e49  mov     r8d, esi
0x180182e4c  mov     dl, 1
0x180182e4e  mov     [rsp+180h+var_160], rax; int
0x180182e53  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180182e58  mov     edx, 9Bh; void *
0x180182e5d  mov     rcx, [rbp+88h]; this
0x180182e64  lea     r8, aOnecoreBaseCbs_38; "onecore\\base\\cbs\\core\\cbsexecutiono"...
0x180182e6b  mov     r9d, ebx; char *
0x180182e6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180182e73  lea     rcx, [rbp+80h+var_60]; this
0x180182e77  call    ??1StopWatch@Rtl@Windows@@QEAA@XZ; Windows::Rtl::StopWatch::~StopWatch(void)
0x180182e7c  lea     rcx, [rbp+80h+var_70]
0x180182e80  call    ?Close@?$AutoComPtr@UIEnumCSI_PENDING_TRANSACTION@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(void)
0x180182e85  lea     rcx, [rsp+180h+var_120]
0x180182e8a  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x180182e8f  lea     rcx, [rsp+180h+var_130]
0x180182e94  call    ?Close@?$AutoComPtr@UIEnumCSI_PENDING_TRANSACTION@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(void)
0x180182e99  mov     rcx, [rbp+80h+var_D0]
0x180182e9d  test    rcx, rcx
0x180182ea0  jz      short loc_180182EAE
0x180182ea2  mov     rax, [rcx]
0x180182ea5  mov     rax, [rax+10h]
0x180182ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180182eae  mov     eax, ebx
0x180182eb0  jmp     loc_18018484B
0x180182eb5  mov     rbx, [rbp+80h+var_D0]
0x180182eb9  lea     rcx, [rsp+180h+var_130]
0x180182ebe  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x180182ec3  mov     r9, [r14]
0x180182ec6  lea     rcx, [rsp+180h+var_120]
0x180182ecb  mov     rdx, [r13+58h]
0x180182ecf  mov     r8d, 4
  ... truncated ...
```
