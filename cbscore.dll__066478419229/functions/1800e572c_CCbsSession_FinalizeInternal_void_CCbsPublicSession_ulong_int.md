# CCbsSession::FinalizeInternal(void *,CCbsPublicSession *,ulong,int *)

- ea: `0x1800e572c`
- end: `0x1800e74f7`
- name: `?FinalizeInternal@CCbsSession@@AEAAJPEAXPEAVCCbsPublicSession@@KPEAH@Z`
- size: `7627`
- prototype: `__int64 __usercall@<rax>(CCbsSession *__hidden this@<rcx>, void *@<rdx>, struct CCbsPublicSession *@<r8>, unsigned int@<r9d>, int *)`
- caller_count: `1`
- callee_count: `65`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801d99f8`

## callees

- `0x18000f090`
- `0x180010b60`
- `0x180010cc0`
- `0x180012fe4`
- `0x180013018`
- `0x1800132a4`
- `0x1800138b8`
- `0x180013c54`
- `0x1800194bc`
- `0x180023e74`
- `0x18002573c`
- `0x1800289f0`
- `0x180028e24`
- `0x18002a78c`
- `0x18002ac84`
- `0x18002f9a8`
- `0x180048fc0`
- `0x1800532d4`
- `0x18005e64c`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800a8678`
- `0x1800ad504`
- `0x1800aea00`
- `0x1800b693c`
- `0x1800b7698`
- `0x1800b8e68`
- `0x1800b980c`
- `0x1800bce9c`
- `0x1800be2e0`
- `0x1800be684`
- `0x1800c03f0`
- `0x1800c12b4`
- `0x1800d5720`
- `0x1800d9578`
- `0x1800e572c`
- `0x1800e7500`
- `0x1800e9f30`
- `0x1800eb920`
- `0x1800f19ec`
- `0x1800f5dcc`
- `0x1800fdf60`
- `0x180150750`
- `0x1801507a8`
- `0x1801507f4`
- `0x180150840`
- `0x180150888`
- `0x18016e1f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e5ade`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e5ade`

## string_xrefs

- `0x1800e6b40`: `PostRebootInstallSandbox`
- `0x1800e7366`: `Failed to create private session store.`
- `0x1800e74e1`: `Session complete notification failed.`
- `0x1800e6abe`: `Failed to decompress OC content.`
- `0x1800e5ad7`: `UpdateAgentLCU`
- `0x1800e60d7`: `Executing pending online actions cannot be done in the same call as package installs.`
- `0x1800e5f4d`: `Failed preparing for servicing during pre-shutdown`
- `0x1800e5f99`: `Failed preparing for servicing during pre-shutdown`
- `0x1800e5888`: `No write operations are allowed on a container`
- `0x1800e5917`: `No write operations are allowed on a read only session`
- `0x1800e59fd`: `Cannot finalize a session that has both UseLocalSourceOnly and UseWindowsUpdate set.`
- `0x1800e5a68`: `Cannot finalize a session that has both CbsSessionOptionNoPend and CbsSessionOptionDelayExecutionIfPendRequired set.`
- `0x1800e58e7`: `Read only operations session, exit.`
- `0x1800e6d11`: `Client specifies manual store corruption detect or repair.`
- `0x1800e6cbf`: `Session: {} failed to perform store corruption detect and repair operation.`
- `0x1800e6dd1`: `Session: {} failed to perform store corruption detect and repair operation.`
- `0x1800e6a21`: `Call to decompress the OC content along with setting the store flag to not compress it again.`
- `0x1800e6bff`: `Client specifies auto store corruption detect or repair.`
- `0x1800e6b63`: `Failed to set the sandbox property for post reboot installation.`
- `0x1800e6fbf`: `B2B: OSUninstall: Adding package to reservicing: {}`
- `0x1800e71d3`: `B2B: OSUninstall: Adding package to reservicing: {}`
- `0x1800e704a`: `B2B: OSUninstall: Failed to collect packages from package store`

## pseudocode

```c
__int64 __fastcall CCbsSession::FinalizeInternal(
        CCbsSession *this,
        void *a2,
        struct CCbsPublicSession *a3,
        int a4,
        int *a5)
{
  unsigned int v5; // r12d
  const char *v8; // rdx
  int v9; // eax
  int v10; // edi
  int v11; // edx
  __int64 v12; // rdx
  void *v13; // r14
  int v14; // r13d
  int v15; // edx
  int v16; // edx
  int v17; // eax
  int v18; // edx
  int v19; // eax
  int v20; // edx
  int v21; // edx
  __int64 v22; // rcx
  int v23; // eax
  unsigned int v24; // ecx
  int v25; // eax
  bool v26; // zf
  int v27; // ebx
  int v28; // edx
  int v29; // eax
  int v30; // edx
  int v31; // edx
  int IsAdministrator; // eax
  int v33; // edx
  unsigned int active; // ebx
  int v35; // eax
  int v36; // eax
  int v37; // edx
  int v38; // eax
  int v39; // edx
  int v40; // eax
  int v41; // edx
  int v42; // edx
  int v43; // eax
  int v44; // edx
  int v45; // ecx
  int v46; // edx
  int v47; // eax
  int v48; // edx
  int v49; // eax
  int v50; // edx
  unsigned int v51; // ebx
  int v52; // edx
  int v53; // eax
  int v54; // eax
  unsigned int v55; // r14d
  int v56; // edx
  __int64 v57; // rdx
  int v58; // eax
  int v59; // edx
  int v60; // eax
  int v61; // edx
  int v62; // eax
  int v63; // edx
  int v64; // eax
  int v65; // edx
  int v66; // eax
  int v67; // edx
  int v68; // eax
  int v69; // edx
  int v70; // eax
  int v71; // edx
  int v72; // eax
  int v73; // edx
  int v74; // eax
  int v75; // edx
  int v76; // eax
  int v77; // edx
  int v78; // eax
  int v79; // edx
  int v80; // eax
  int v81; // edx
  int v82; // eax
  int v83; // edx
  int v84; // eax
  unsigned int v85; // esi
  int v86; // edx
  int v88; // eax
  int v89; // edx
  int v90; // eax
  int v91; // edx
  int v92; // eax
  int v93; // edx
  int v94; // eax
  int v95; // edx
  int v96; // r9d
  __int64 v97; // r8
  unsigned int v98; // ecx
  struct CCbsIdentity **InitPointer; // rax
  struct CCbsPackage **v100; // rax
  struct ICbsUIHandler *v101; // r9
  int v102; // eax
  int v103; // edx
  __int64 v104; // rdx
  int v105; // edx
  int v106; // eax
  int v107; // edx
  struct ICbsIdentity **v108; // r12
  struct ICbsIdentity **v109; // rax
  struct ICbsIdentity *v110; // r13
  struct CCbsPackage **v111; // rax
  struct ICbsUIHandler *v112; // r9
  int v113; // edx
  unsigned int v114; // r14d
  int v115; // eax
  int v116; // edx
  int v117; // eax
  __int64 v118; // rcx
  void *v119; // r12
  int SessionSandbox; // eax
  int v121; // edx
  __int64 *v122; // rcx
  __int64 *v123; // r9
  __int64 v124; // rax
  __int64 *v125; // rdx
  __int64 *v126; // r8
  __int64 v127; // rax
  int v128; // r8d
  int v129; // eax
  int v130; // edx
  unsigned int v131; // eax
  struct ICbsIdentity *v132; // [rsp+20h] [rbp-E0h]
  int v133[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v134[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct CCbsPublicSession *v135; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v136; // [rsp+68h] [rbp-98h] BYREF
  int v137[2]; // [rsp+70h] [rbp-90h] BYREF
  void *v138; // [rsp+78h] [rbp-88h]
  int v139[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v140[24]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v141; // [rsp+A0h] [rbp-60h] BYREF
  int v142; // [rsp+A8h] [rbp-58h]
  __int128 v143; // [rsp+B0h] [rbp-50h]
  __int64 v144; // [rsp+C0h] [rbp-40h]
  bool v145[8]; // [rsp+C8h] [rbp-38h] BYREF
  CCbsSession *v146; // [rsp+D0h] [rbp-30h]
  int v147; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v148; // [rsp+E0h] [rbp-20h] BYREF
  struct CCbsIdentity *v149; // [rsp+E8h] [rbp-18h] BYREF
  CCbsPackage *v150; // [rsp+F0h] [rbp-10h] BYREF
  int v151; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v152[24]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v153; // [rsp+118h] [rbp+18h]
  struct ICbsIdentity **v154; // [rsp+128h] [rbp+28h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v5 = 0;
  v138 = a2;
  v135 = a3;
  *a5 = 0;
  CritSecLocker::CritSecLocker((CritSecLocker *)v140, (CCbsSession *)((char *)this + 584), 1);
  v145[0] = 1;
  v146 = this;
  if ( !a4 && !*((_DWORD *)this + 173) && !*((_DWORD *)this + 403) && *((_DWORD *)this + 369) )
  {
    v8 = "Lazy store initialization and no action to do, exit.";
LABEL_21:
    LogAdapter::TraceAtLevel<>(1, v8);
LABEL_22:
    v10 = v5;
    goto LABEL_213;
  }
  v9 = CCbsSession::CheckInitialized(this);
  v10 = v9;
  if ( v9 < 0 )
  {
    LODWORD(v148) = v9;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Cannot finalize a session that has not been initialized.");
      v135 = (struct CCbsPublicSession *)&v148;
      LOBYTE(v11) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v11,
        3,
        (unsigned int)": {}",
        (__int64)&v135);
    }
    v12 = 195;
    goto LABEL_10;
  }
  v13 = (void *)*((_QWORD *)this + 141);
  v14 = CCbsSession::InspectSessionTask(this);
  if ( !v14 && *((_DWORD *)this + 172) && CCbsSession::IsImageReadOnly(this) )
  {
    v10 = -2146498493;
    LODWORD(v148) = -2146498493;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        (unsigned int)(v14 + 3),
        "No write operations are allowed on a container");
      v135 = (struct CCbsPublicSession *)&v148;
      LOBYTE(v15) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v15,
        v14 + 3,
        (unsigned int)": {}",
        (__int64)&v135);
    }
    v12 = 212;
    goto LABEL_10;
  }
  *((_DWORD *)this + 172) |= a4;
  if ( *((_BYTE *)this + 1040) )
  {
    if ( !v14 && !*((_DWORD *)this + 172) )
    {
      v8 = "Read only operations session, exit.";
      goto LABEL_21;
    }
    v10 = -2146498493;
    LODWORD(v148) = -2146498493;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "No write operations are allowed on a read only session");
      v135 = (struct CCbsPublicSession *)&v148;
      LOBYTE(v16) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v16,
        3,
        (unsigned int)": {}",
        (__int64)&v135);
    }
    v12 = 226;
    goto LABEL_10;
  }
  v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 306) + 88LL))(*((_QWORD *)this + 306), 0);
  v10 = v17;
  if ( v17 < 0 )
  {
    LODWORD(v150) = v17;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to validate store version");
      v135 = (struct CCbsPublicSession *)&v150;
      LOBYTE(v18) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v18,
        3,
        (unsigned int)": {}",
        (__int64)&v135);
    }
    v12 = 235;
    goto LABEL_10;
  }
  v19 = *((_DWORD *)this + 172);
  if ( (v19 & 0x20000) != 0 && (v19 & 0x40000) != 0 )
  {
    v10 = -2147024809;
    LODWORD(v148) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Cannot finalize a session that has both UseLocalSourceOnly and UseWindowsUpdate set.");
      v135 = (struct CCbsPublicSession *)&v148;
      LOBYTE(v20) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v20,
        3,
        (unsigned int)": {}",
        (__int64)&v135);
    }
    v12 = 243;
    goto LABEL_10;
  }
  if ( (v19 & 0x10000) != 0 && (v19 & 0x2000000) != 0 )
  {
    v10 = -2147024809;
    LODWORD(v148) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Cannot finalize a session that has both CbsSessionOptionNoPend and CbsSessionOptionDelayExecutionIfPendRequired set.");
      v135 = (struct CCbsPublicSession *)&v148;
      LOBYTE(v21) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v21,
        3,
        (unsigned int)": {}",
        (__int64)&v135);
    }
    v12 = 248;
    goto LABEL_10;
  }
  if ( (*((_BYTE *)this + 2208) & 0x10) != 0
    && ((unsigned int)CCbsSession::IsClientWindowsUpdate(this)
     || (v22 = *((_QWORD *)this + 81)) != 0 && !(unsigned int)_o__wcsicmp(v22, L"UpdateAgentLCU")) )
  {
    if ( *((_BYTE *)this + 2320) )
    {
      LODWORD(v148) = 0;
      v23 = (*(__int64 (__fastcall **)(struct IServicingWOSCSettings *, const wchar_t *, __int64 *))(*(_QWORD *)vOneSettings + 48LL))(
              vOneSettings,
              L"ENABLEPRIORITY",
              &v148);
      if ( !IsExpectedOneSettingsError_HRESULT(v23) )
        LogAdapter::TraceAtLevelIfFailed<long,>(1, v24, "Unable to get the OneSettings value for ENABLEPRIORITY.");
      switch ( (_DWORD)v148 )
      {
        case 1:
          LogAdapter::TraceAtLevel<>(1, "Setting Normal priority based on onesettings");
          *((_DWORD *)this + 173) &= 0xCFFFFFFF;
          break;
        case 2:
          LogAdapter::TraceAtLevel<>(1, "Setting UserAway priority based on onesettings");
          *((_DWORD *)this + 173) &= ~0x10000000u;
          *((_DWORD *)this + 173) |= 0x20000000u;
          break;
        case 3:
          LogAdapter::TraceAtLevel<>(1, "Setting UserPresent priority based on onesettings");
          *((_DWORD *)this + 173) &= ~0x20000000u;
          *((_DWORD *)this + 173) |= 0x10000000u;
          break;
      }
    }
  }
  v25 = *((_DWORD *)this + 173);
  if ( (v25 & 0x10000000) != 0 )
  {
    CCbsSession::SetUserPresentPriority(this);
  }
  else if ( (v25 & 0x20000000) != 0 )
  {
    CCbsSession::SetUserAwayPriority(this);
  }
  else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Update_EcoQos>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Update_EcoQos>::GetImpl'::`2'::impl)
         && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Update_EcoQos>::__private_GetVariant(`wil::Feature<__WilFeatureTraits_Feature_Update_EcoQos>::GetImpl'::`2'::impl) == 1 )
  {
    CCbsSession::SetNormalPriorityEcoQos(this);
  }
  v26 = (*((_DWORD *)this + 172) & 0x200) == 0;
  v147 = *((_DWORD *)this + 172) & 0x200;
  LOBYTE(v5) = !v26;
  v27 = a4 & 0x80000;
  v151 = v5;
  v26 = *((_DWORD *)this + 190) == 0;
  *((_DWORD *)this + 316) = v27 != 0;
  if ( !v26 && !v27 )
  {
    v10 = -2146498494;
    LODWORD(v149) = -2146498494;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Cannot finalize a session that has been finalized.");
      v135 = (struct CCbsPublicSession *)&v149;
      LOBYTE(v28) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v28,
        3,
        (unsigned int)": {}",
        (__int64)&v135);
    }
    v12 = 309;
    goto LABEL_10;
  }
  *((_DWORD *)this + 270) = 1;
  v29 = CCbsSession::FinalizeOCs(this);
  v10 = v29;
  if ( v29 < 0 )
  {
    LODWORD(v149) = v29;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to finalize OCs");
      v136 = (__int64 *)&v149;
      LOBYTE(v31) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v31,
        3,
        (unsigned int)": {}",
        (__int64)&v136);
    }
    v12 = 319;
    goto LABEL_10;
  }
  v26 = *((_DWORD *)this + 403) == 0;
  *((_DWORD *)this + 190) = 1;
  if ( !v26 )
  {
    IsAdministrator = EnsureCallerIsAdministrator(v13);
    v10 = IsAdministrator;
    if ( IsAdministrator < 0 )
    {
      LODWORD(v149) = IsAdministrator;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to ensure caller is an administrator.");
        v136 = (__int64 *)&v149;
        LOBYTE(v33) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v33,
          3,
          (unsigned int)": {}",
          (__int64)&v136);
      }
      v12 = 331;
      goto LABEL_10;
    }
    if ( *((_DWORD *)this + 403) == 1 )
    {
      v36 = CCbsSession::ExportRepository(this, a5);
    }
    else if ( *((_DWORD *)this + 403) == 3 )
    {
      v36 = CCbsSession::PerformPrepareServicingOperation(this, v5, v135);
    }
    else
    {
      if ( *((_DWORD *)this + 403) != 4 )
      {
        if ( *((_DWORD *)this + 403) == 10 )
        {
          active = CCbsSessionManager::RegisterActiveSession((CCbsSessionManager *)qword_1803B11E8, this, 0);
          v35 = CCbsSession::OfflineFinalizeInstallation(this);
        }
        else
        {
          if ( *((_DWORD *)this + 403) != 11 )
            goto LABEL_90;
          active = CCbsSessionManager::RegisterActiveSession((CCbsSessionManager *)qword_1803B11E8, this, 0);
          v35 = CCbsSession::OfflineRollbackInstallation(this);
        }
        v10 = v35;
        CCbsSessionManager::UnregisterActiveSession((CCbsSessionManager *)qword_1803B11E8, active);
LABEL_86:
        if ( v10 < 0 )
        {
          LODWORD(v148) = v10;
          if ( LogAdapter::g_Logger )
          {
            LODWORD(v150) = *((_DWORD *)this + 403);
            LogAdapter::Logger::LogNumObjects<unsigned long>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed to perform client operation: {}",
              (__int64)&v150);
            v136 = &v148;
            LOBYTE(v37) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v37,
              3,
              (unsigned int)": {}",
              (__int64)&v136);
          }
          v12 = 362;
          goto LABEL_10;
        }
LABEL_90:
        v10 = 0;
        goto LABEL_213;
      }
      v36 = CCbsSession::PerformLateAcquisitionOperation(this, v138, v5, v135, a5);
    }
    v10 = v36;
    goto LABEL_86;
  }
  v5 = 0;
  v10 = 0;
  if ( (*((_DWORD *)this + 172) & 0x200000) != 0 )
  {
    v38 = EnsureCallerIsAdministrator(v13);
    v10 = v38;
    if ( v38 < 0 )
    {
      LODWORD(v149) = v38;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to ensure caller is an administrator.");
        v136 = (__int64 *)&v149;
        LOBYTE(v39) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v39,
          3,
          (unsigned int)": {}",
          (__int64)&v136);
      }
      v12 = 372;
      goto LABEL_10;
    }
    v40 = AnticipatePreshutdownNeeded();
    v10 = v40;
    if ( v40 < 0 )
    {
      if ( v14 )
      {
        LODWORD(v148) = v40;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed preparing for servicing during pre-shutdown");
          *(_QWORD *)v134 = &v148;
          LOBYTE(v42) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v42,
            3,
            (unsigned int)": {}",
            (__int64)v134);
        }
        v12 = 379;
      }
      else
      {
        LODWORD(v150) = v40;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed preparing for servicing during pre-shutdown");
          *(_QWORD *)v139 = &v150;
          LOBYTE(v41) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v41,
            3,
            (unsigned int)": {}",
            (__int64)v139);
        }
        v12 = 377;
      }
      goto LABEL_10;
    }
  }
  if ( (*((_BYTE *)this + 692) & 1) != 0 )
  {
    *(_QWORD *)v133 = *((_QWORD *)this + 81);
    if ( LogAdapter::g_Logger )
    {
      LOBYTE(v30) = 1;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        v30,
        1,
        (unsigned int)"ExecPA: Client: {} requested postponing of online actions until explicitly requested",
        (__int64)v133);
    }
    v43 = PackageStoreSetProperty(this, L"PostponeOnlineActions", 1u);
    v5 = v43;
    if ( v43 < 0 )
    {
      v151 = v43;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "ExecPA: Failed postponing online actions");
        *(_QWORD *)v133 = &v151;
        LOBYTE(v44) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v44,
          3,
          (unsigned int)": {}",
          (__int64)v133);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x186,
        (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationexecution.cpp",
        (const char *)v5,
        (int)v132);
      goto LABEL_22;
    }
    v5 = 0;
  }
  v45 = *((_DWORD *)this + 173);
  if ( (v45 & 2) != 0 )
  {
    if ( v14 )
    {
      v10 = -2146498554;
      v147 = -2146498554;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Executing pending online actions cannot be done in the same call as package installs.");
        *(_QWORD *)v133 = &v147;
        LOBYTE(v46) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v46,
          3,
          (unsigned int)": {}",
          (__int64)v133);
      }
      v12 = 397;
    }
    else
    {
      v135 = (struct CCbsPublicSession *)*((_QWORD *)this + 81);
      if ( LogAdapter::g_Logger )
      {
        LOBYTE(v30) = 1;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          v30,
          1,
          (unsigned int)"ExecPA: Executing postponed online actions per request by client: {}",
          (__int64)&v135);
      }
      v47 = EnsureCallerIsAdministrator(v13);
      v10 = v47;
      if ( v47 >= 0 )
      {
        v49 = PackageStoreSetProperty(this, L"PostponeOnlineActions", 2u);
        v10 = v49;
        if ( v49 >= 0 )
        {
          v51 = CCbsSessionManager::RegisterActiveSession((CCbsSessionManager *)qword_1803B11E8, this, 0);
          CritSecLocker::Unlock((CritSecLocker *)v140);
          v10 = CbsCoreStartupProcessingEx(1);
          CCbsSessionManager::UnregisterActiveSession((CCbsSessionManager *)qword_1803B11E8, v51);
          if ( v10 == -2147021886 )
          {
            LogAdapter::TraceAtLevel<>(1, "ExecPA: Online actions required a reboot");
            *a5 = 1;
          }
          else if ( v10 < 0 )
          {
            v147 = v10;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "ExecPA: Failed executing online actions");
              *(_QWORD *)v133 = &v147;
              LOBYTE(v52) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v52,
                3,
                (unsigned int)": {}",
                (__int64)v133);
            }
            v12 = 427;
            goto LABEL_10;
          }
          *((_DWORD *)this + 192) = 208;
          goto LABEL_22;
        }
        v147 = v49;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "ExecPA: Failed clearing postpone flag for online actions");
          *(_QWORD *)v133 = &v147;
          LOBYTE(v50) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v50,
            3,
            (unsigned int)": {}",
            (__int64)v133);
        }
        v12 = 406;
      }
      else
      {
        v147 = v47;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to ensure caller is an administrator.");
          *(_QWORD *)v133 = &v147;
          LOBYTE(v48) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v48,
            3,
            (unsigned int)": {}",
            (__int64)v133);
        }
        v12 = 402;
      }
    }
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationexecution.cpp",
      (const char *)(unsigned int)v10,
      (int)v132);
    goto LABEL_213;
  }
  if ( v14 )
  {
    v96 = 7044;
    if ( *((_QWORD *)this + 122) )
    {
      v97 = **((_QWORD **)this + 124);
      if ( *(_QWORD *)(v97 + 24) )
      {
        v98 = *(_DWORD *)(*(_QWORD *)(**(_QWORD **)(v97 + 40) + 24LL) + 632LL);
        if ( v98 <= 0xC && _bittest(&v96, v98) && (unsigned int)CCbsSession::IsClientWindowsUpdate(this) )
          *((_DWORD *)this + 172) |= 0x100u;
      }
    }
    if ( (*((_BYTE *)this + 692) & 4) != 0 )
    {
      v149 = 0;
      InitPointer = (struct CCbsIdentity **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v149);
      if ( CCbsSession::IsAnLCUInstalled(this, InitPointer) && v149 )
      {
        v148 = 0;
        v100 = (struct CCbsPackage **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v148);
        v102 = CCbsSession::ResolvePackage(this, 0, *((void **)this + 141), v101, v149, 1, v100, 0);
        v55 = v102;
        if ( v102 < 0 )
        {
          v147 = v102;
          if ( LogAdapter::g_Logger )
          {
            *(_QWORD *)v133 = GetFastCbsIdentityString(v149);
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed to resolve the LCU package: {}",
              (__int64)v133);
            *(_QWORD *)v134 = &v147;
            LOBYTE(v103) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v103,
              3,
              (unsigned int)": {}",
              (__int64)v134);
          }
          v104 = 638;
          goto LABEL_243;
        }
        *(_QWORD *)v133 = GetFastCbsIdentityString(v149);
        if ( LogAdapter::g_Logger )
        {
          LOBYTE(v105) = 1;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            v105,
            1,
            (unsigned int)"B2B: OSUninstall: Adding package to reservicing: {}",
            (__int64)v133);
        }
        *(_QWORD *)v133 = v148;
        v55 = CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::Add((char *)this + 2144, v133);
        if ( (v55 & 0x80000000) != 0 )
        {
          v104 = 641;
LABEL_243:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v104,
            (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationexecution.cpp",
            (const char *)v55,
            (int)v132);
          Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v148);
LABEL_244:
          Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v149);
          goto LABEL_141;
        }
        *((_DWORD *)this + 173) |= 0x40000000u;
        Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v148);
      }
      CCbsInterfaceArray<ICbsSessionObserverListener *>::CCbsInterfaceArray<ICbsSessionObserverListener *>(v152);
      v106 = PackageStoreCollectPackages(this, 496, v152);
      v55 = v106;
      if ( v106 < 0 )
      {
        v147 = v106;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "B2B: OSUninstall: Failed to collect packages from package store");
          *(_QWORD *)v133 = &v147;
          LOBYTE(v107) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v107,
            3,
            (unsigned int)": {}",
            (__int64)v133);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x293,
          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationexecution.cpp",
          (const char *)v55,
          (int)v132);
LABEL_254:
        CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>::~CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>(v152);
        goto LABEL_244;
      }
      v108 = v154;
      v109 = &v154[v153];
      *(_QWORD *)v137 = v109;
      while ( v108 != v109 )
      {
        v110 = *v108;
        v150 = 0;
        v111 = (struct CCbsPackage **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v150);
        v10 = CCbsSession::ResolvePackage(this, 0, 0, v112, v110, 1, v111, 0);
        *(_QWORD *)v133 = GetFastCbsIdentityString(v110);
        if ( v10 >= 0 )
        {
          v114 = *((_DWORD *)v150 + 158);
          if ( CCbsPackage::IsLCUPackage(v150) && *((_DWORD *)v150 + 176) != 112
            || !*((_DWORD *)v150 + 225)
            && *((_DWORD *)v150 + 159) != 2
            && v114 <= 0xC
            && (v115 = 7044, _bittest(&v115, v114)) )
          {
            *(_QWORD *)v139 = GetFastCbsIdentityString(v110);
            if ( LogAdapter::g_Logger )
            {
              LOBYTE(v116) = 1;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                v116,
                1,
                (unsigned int)"B2B: OSUninstall: Adding package to reservicing: {}",
                (__int64)v139);
            }
            v136 = (__int64 *)v150;
            v117 = CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::Add((char *)this + 2144, &v136);
            v55 = v117;
            if ( v117 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x2BE,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationexecution.cpp",
                (const char *)(unsigned int)v117,
                (int)v132);
              Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v150);
              goto LABEL_254;
            }
            *((_DWORD *)this + 173) |= 0x40000000u;
          }
        }
        else
        {
          LogAdapter::TraceAtLevelHr<long,wchar_t const *>(1, (unsigned int)v10, "Unable to resolve package: {}", v133);
          *(_QWORD *)v134 = GetFastCbsIdentityString(v110);
          if ( LogAdapter::g_Logger )
          {
            LOBYTE(v113) = 1;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              v113,
              1,
              (unsigned int)"Unable to resolve package: {}, moving on",
              (__int64)v134);
          }
          v10 = 0;
        }
        Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v150);
        v109 = *(struct ICbsIdentity ***)v137;
        ++v108;
      }
      CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>::~CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>(v152);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v149);
    }
    if ( (*((_DWORD *)this + 172) & 0x100) != 0 )
      *((_DWORD *)this + 264) = 1;
    if ( !(unsigned int)CCbsSession::IsOffline(this) )
    {
      v141 = 0;
      v142 = 0;
      v144 = 0;
      v132 = (struct ICbsIdentity *)&v141;
      v143 = 0;
      if ( (int)CCbsSession::GetStoreObject(v118, 0, 1) >= 0 )
      {
        CCbsStoreObject::SetValue((CCbsStoreObject *)&v141, L"DoqTime", 0);
        CCbsStoreObject::SetValue((CCbsStoreObject *)&v141, L"DoqCount", 0);
        CCbsStoreObject::SetValue((CCbsStoreObject *)&v141, L"PoqTime", 0);
        CCbsStoreObject::SetValue((CCbsStoreObject *)&v141, L"PoqCount", 0);
        CCbsStoreObject::SetValue((CCbsStoreObject *)&v141, L"RptTime", 0);
        CCbsStoreObject::SetValue((CCbsStoreObject *)&v141, L"RptCount", 0);
      }
      CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v141);
    }
    v119 = v138;
    SessionSandbox = CCbsSession::CreateSessionSandbox(this, v138, 0, 0);
    v55 = SessionSandbox;
    if ( SessionSandbox < 0 )
    {
      v147 = SessionSandbox;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to create private session store.");
        *(_QWORD *)v137 = &v147;
        LOBYTE(v121) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v121,
          3,
          (unsigned int)": {}",
          (__int64)v137);
      }
      v57 = 740;
      goto LABEL_140;
    }
    CritSecLocker::Unlock((CritSecLocker *)v140);
    if ( *((_DWORD *)this + 316) )
    {
      CCbsSession::SetRetryFlag(this);
      v122 = (__int64 *)*((_QWORD *)this + 102);
      v123 = &v122[*((_QWORD *)this + 100)];
      while ( v122 != v123 )
      {
        v124 = *v122;
        *(_DWORD *)(v124 + 56) = 4096;
        v125 = *(__int64 **)(v124 + 104);
        v126 = &v125[*(_QWORD *)(v124 + 88)];
        while ( v125 != v126 )
        {
          v127 = *v125++;
          *(_DWORD *)(v127 + 12) = 4096;
        }
        ++v122;
      }
    }
    v128 = *((_DWORD *)this + 316);
    v145[0] = v147 == 0;
    v129 = CCbsSession::PerformSessionTasksOperation(this, v119, v128, 0, v151, 0, v135, a5, 0);
    v55 = v129;
    if ( v129 < 0 )
    {
      v147 = v129;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to perform operation. ");
        *(_QWORD *)v137 = &v147;
        LOBYTE(v130) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v130,
          3,
          (unsigned int)": {}",
          (__int64)v137);
      }
      v57 = 778;
      goto LABEL_140;
    }
    if ( *((_DWORD *)this + 316) && !*a5 )
    {
      v131 = CCbsSession::ChangeState(this, 208, (unsigned int)v10);
      LogAdapter::TraceAtLevelIfFailed<long,>(1, v131, "Session complete notification failed.");
    }
    goto LABEL_208;
  }
  v53 = *((_DWORD *)this + 172);
  if ( (v53 & 0x400) != 0 )
  {
    LogAdapter::TraceAtLevel<>(1, "No call is made on InitiateChanges, Scavenge only.");
    v54 = EnsureCallerIsAdministrator(v13);
    v55 = v54;
    if ( v54 < 0 )
    {
      v147 = v54;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to ensure caller is an administrator.");
        *(_QWORD *)v133 = &v147;
        LOBYTE(v56) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v56,
          3,
          (unsigned int)": {}",
          (__int64)v133);
      }
      v57 = 443;
LABEL_140:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v57,
        (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationexecution.cpp",
        (const char *)v55,
        (int)v132);
LABEL_141:
      v10 = v55;
      goto LABEL_213;
    }
    CritSecLocker::Unlock((CritSecLocker *)v140);
    LODWORD(v132) = 0;
    v58 = CCbsSession::PerformMaintenanceTaskOperation(this, 0, vhIdleProcessingPaused, 0);
    v55 = v58;
    if ( v58 < 0 )
    {
      v147 = v58;
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)v133 = *((_QWORD *)this + 80);
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Session: {} failed to perform synchronous scavenge operation",
          (__int64)v133);
        *(_QWORD *)v134 = &v147;
        LOBYTE(v59) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v59,
          3,
          (unsigned int)": {}",
          (__int64)v134);
      }
      v57 = 460;
      goto LABEL_140;
    }
    goto LABEL_206;
  }
  if ( (v53 & 0x400000) != 0 )
  {
    LogAdapter::TraceAtLevel<>(1, "No call is made on InitiateChanges, Synchronous Cleanup only.");
    v60 = EnsureCallerIsAdministrator(v13);
    v55 = v60;
    if ( v60 < 0 )
    {
      v147 = v60;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to ensure caller is an administrator.");
        *(_QWORD *)v133 = &v147;
        LOBYTE(v61) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v61,
          3,
          (unsigned int)": {}",
          (__int64)v133);
      }
      v57 = 476;
      goto LABEL_140;
    }
    CritSecLocker::Unlock((CritSecLocker *)v140);
    if ( (*((_DWORD *)this + 173) & 0x800000) != 0 )
      LogAdapter::TraceAtLevel<>(1, "Testing mode, simulating automatic cleanup");
    LODWORD(v132) = 0;
    v62 = CCbsSession::PerformMaintenanceTaskOperation(this, 0, vhIdleProcessingPaused, 0);
    v55 = v62;
    if ( v62 < 0 )
    {
      v147 = v62;
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)v133 = *((_QWORD *)this + 80);
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Session: {} failed to perform Synchronous Cleanup operation",
          (__int64)v133);
        *(_QWORD *)v134 = &v147;
        LOBYTE(v63) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v63,
          3,
          (unsigned int)": {}",
          (__int64)v134);
      }
      v57 = 498;
      goto LABEL_140;
    }
    goto LABEL_206;
  }
  if ( (v53 & 0x100000) != 0 )
  {
    LogAdapter::TraceAtLevel<>(1, "Client specifies reporting stack internal information");
    v64 = EnsureCallerIsAdministrator(v13);
    v55 = v64;
    if ( v64 < 0 )
    {
      v147 = v64;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to ensure caller is an administrator.");
        *(_QWORD *)v133 = &v147;
        LOBYTE(v65) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v65,
          3,
          (unsigned int)": {}",
          (__int64)v133);
      }
      v57 = 509;
      goto LABEL_140;
    }
    CritSecLocker::Unlock((CritSecLocker *)v140);
    v66 = CCbsSession::PerformInternalReportingOperation(this, v135, a5);
    v55 = v66;
    if ( v66 < 0 )
    {
      v147 = v66;
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)v133 = *((_QWORD *)this + 80);
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Session: {} failed to perform internal reporting operation",
          (__int64)v133);
        *(_QWORD *)v134 = &v147;
        LOBYTE(v67) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v67,
          3,
          (unsigned int)": {}",
          (__int64)v134);
      }
      v57 = 519;
      goto LABEL_140;
    }
LABEL_206:
    *((_DWORD *)this + 192) = 208;
    goto LABEL_208;
  }
  if ( v53 >= 0 )
  {
    if ( (v53 & 0x800) != 0 )
    {
      LogAdapter::TraceAtLevel<>(1, "Client specified cancelling all pended transactions.");
      v72 = EnsureCallerIsAdministrator(v13);
      v55 = v72;
      if ( v72 < 0 )
      {
        v147 = v72;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to ensure caller is an administrator.");
          *(_QWORD *)v133 = &v147;
          LOBYTE(v73) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v73,
            3,
            (unsigned int)": {}",
            (__int64)v133);
        }
        v57 = 542;
        goto LABEL_140;
      }
      CritSecLocker::Unlock((CritSecLocker *)v140);
      v74 = CCbsSession::PerformCancelTransactionsInternal(this, a5, 0);
      v55 = v74;
      if ( v74 < 0 )
      {
        v147 = v74;
        if ( LogAdapter::g_Logger )
        {
          *(_QWORD *)v133 = *((_QWORD *)this + 80);
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Session: {} failed to perform cancelling all pending transactions.",
            (__int64)v133);
          *(_QWORD *)v134 = &v147;
          LOBYTE(v75) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v75,
            3,
            (unsigned int)": {}",
            (__int64)v134);
        }
        v57 = 552;
        goto LABEL_140;
      }
    }
    else if ( (v45 & 0x800) != 0 || (v45 & 0x1000) != 0 )
    {
      LogAdapter::TraceAtLevel<>(1, "Client specifies manual store corruption detect or repair.");
      v92 = EnsureCallerIsAdministrator(v13);
      v55 = v92;
      if ( v92 < 0 )
      {
        v147 = v92;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to ensure caller is an administrator.");
          *(_QWORD *)v133 = &v147;
          LOBYTE(v93) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v93,
            3,
            (unsigned int)": {}",
            (__int64)v133);
        }
        v57 = 559;
        goto LABEL_140;
      }
      CritSecLocker::Unlock((CritSecLocker *)v140);
      v94 = CCbsSession::PerformStoreCorruptionDetectAndRepairOperation(this, v138, 1, a5);
      v55 = v94;
      if ( v94 < 0 )
      {
        v147 = v94;
        if ( LogAdapter::g_Logger )
        {
          *(_QWORD *)v133 = *((_QWORD *)this + 80);
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Session: {} failed to perform store corruption detect and repair operation.",
            (__int64)v133);
          *(_QWORD *)v134 = &v147;
          LOBYTE(v95) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v95,
            3,
            (unsigned int)": {}",
            (__int64)v134);
        }
        v57 = 569;
        goto LABEL_140;
      }
    }
    else
    {
      if ( (v53 & 0xC000) == 0 )
      {
        if ( (v53 & 0x8000000) != 0 )
        {
          LogAdapter::TraceAtLevel<>(1, "No call is made on InitiateChanges, Synchronous analysis only.");
          v76 = EnsureCallerIsAdministrator(v13);
          v55 = v76;
          if ( v76 < 0 )
          {
            v147 = v76;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "Failed to ensure caller is an administrator.");
              *(_QWORD *)v133 = &v147;
              LOBYTE(v77) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v77,
                3,
                (unsigned int)": {}",
                (__int64)v133);
            }
            v57 = 591;
            goto LABEL_140;
          }
          CritSecLocker::Unlock((CritSecLocker *)v140);
          v78 = CCbsSession::PerformStoreAnalysisOperation(this, a5);
          v55 = v78;
          if ( v78 < 0 )
          {
            v147 = v78;
            if ( LogAdapter::g_Logger )
            {
              *(_QWORD *)v133 = *((_QWORD *)this + 80);
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Session: {} failed to perform store analysis operation",
                (__int64)v133);
              *(_QWORD *)v134 = &v147;
              LOBYTE(v79) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v79,
                3,
                (unsigned int)": {}",
                (__int64)v134);
            }
            v57 = 597;
            goto LABEL_140;
          }
        }
        else
        {
          if ( (v45 & 0x40) == 0 )
          {
            *a5 = CCbsSession::IsRebootRequired(this);
            *((_DWORD *)this + 192) = 208;
            goto LABEL_208;
          }
          LogAdapter::TraceAtLevel<>(
            1,
            "Call to decompress the OC content along with setting the store flag to not compress it again.");
          v80 = EnsureCallerIsAdministrator(v13);
          v55 = v80;
          if ( v80 < 0 )
          {
            v147 = v80;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "Failed to ensure caller is an administrator.");
              *(_QWORD *)v133 = &v147;
              LOBYTE(v81) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v81,
                3,
                (unsigned int)": {}",
                (__int64)v133);
            }
            v57 = 607;
            goto LABEL_140;
          }
          CritSecLocker::Unlock((CritSecLocker *)v140);
          v82 = CCbsSession::DecompressOCContent(this);
          v55 = v82;
          if ( v82 < 0 )
          {
            v147 = v82;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to decompress OC content.");
              *(_QWORD *)v133 = &v147;
              LOBYTE(v83) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v83,
                3,
                (unsigned int)": {}",
                (__int64)v133);
            }
            v57 = 611;
            goto LABEL_140;
          }
        }
        goto LABEL_206;
      }
      LogAdapter::TraceAtLevel<>(1, "Client specifies auto store corruption detect or repair.");
      v88 = EnsureCallerIsAdministrator(v13);
      v55 = v88;
      if ( v88 < 0 )
      {
        v147 = v88;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to ensure caller is an administrator.");
          *(_QWORD *)v133 = &v147;
          LOBYTE(v89) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v89,
            3,
            (unsigned int)": {}",
            (__int64)v133);
        }
        v57 = 575;
        goto LABEL_140;
      }
      CritSecLocker::Unlock((CritSecLocker *)v140);
      v90 = CCbsSession::PerformStoreCorruptionDetectAndRepairOperation(this, v138, 0, a5);
      v55 = v90;
      if ( v90 < 0 )
      {
        v147 = v90;
        if ( LogAdapter::g_Logger )
        {
          *(_QWORD *)v133 = *((_QWORD *)this + 80);
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Session: {} failed to perform store corruption detect and repair operation.",
            (__int64)v133);
          *(_QWORD *)v134 = &v147;
          LOBYTE(v91) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v91,
            3,
            (unsigned int)": {}",
            (__int64)v134);
        }
        v57 = 585;
        goto LABEL_140;
      }
    }
  }
  else
  {
    LogAdapter::TraceAtLevel<>(1, "Client specified cancelling only smart pended transactions.");
    v68 = EnsureCallerIsAdministrator(v13);
    v55 = v68;
    if ( v68 < 0 )
    {
      v147 = v68;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to ensure caller is an administrator.");
        *(_QWORD *)v133 = &v147;
        LOBYTE(v69) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v69,
          3,
          (unsigned int)": {}",
          (__int64)v133);
      }
      v57 = 529;
      goto LABEL_140;
    }
    v70 = CCbsSession::PerformCancelTransactionsInternal(this, a5, 1);
    v55 = v70;
    if ( v70 < 0 )
    {
      v147 = v70;
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)v133 = *((_QWORD *)this + 80);
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Session: {} failed to perform cancelling all pending transactions.",
          (__int64)v133);
        *(_QWORD *)v134 = &v147;
        LOBYTE(v71) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v71,
          3,
          (unsigned int)": {}",
          (__int64)v134);
      }
      v57 = 533;
      goto LABEL_140;
    }
    *a5 |= PackageStoreIsPendingRequired(this, 0, 0);
  }
LABEL_208:
  if ( *((_BYTE *)this + 2273) )
  {
    v84 = PackageStoreSetStringProperty(0, L"PostRebootInstallSandbox", *((const wchar_t **)this + 285));
    v85 = v84;
    if ( v84 < 0 )
    {
      v147 = v84;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to set the sandbox property for post reboot installation.");
        *(_QWORD *)v137 = &v147;
        LOBYTE(v86) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v86,
          3,
          (unsigned int)": {}",
          (__int64)v137);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x31A,
        (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationexecution.cpp",
        (const char *)v85,
        (int)v132);
      v10 = v85;
    }
  }
LABEL_213:
  Windows::Detail::OnBlockExitImpl__CCbsSession::FinalizeInternal_::_2_::_lambda_1___::_OnBlockExitImpl__CCbsSession::FinalizeInternal_::_2_::_lambda_1___(v145);
  CritSecLocker::~CritSecLocker((CritSecLocker *)v140);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800e572c  mov     [rsp-8+arg_18], rbx
0x1800e5731  push    rbp
0x1800e5732  push    rsi
0x1800e5733  push    rdi
0x1800e5734  push    r12
0x1800e5736  push    r13
0x1800e5738  push    r14
0x1800e573a  push    r15
0x1800e573c  lea     rbp, [rsp-50h]
0x1800e5741  sub     rsp, 150h
0x1800e5748  mov     rax, cs:__security_cookie
0x1800e574f  xor     rax, rsp
0x1800e5752  mov     [rbp+80h+var_40], rax
0x1800e5756  mov     r15, [rbp+80h+arg_20]
0x1800e575d  xor     r12d, r12d
0x1800e5760  mov     [rsp+180h+var_108], rdx
0x1800e5765  mov     rsi, rcx
0x1800e5768  mov     [rsp+180h+var_120], r8
0x1800e576d  lea     rdx, [rcx+248h]; struct AutoCritSec *
0x1800e5774  lea     rcx, [rbp+80h+var_F8]; this
0x1800e5778  mov     ebx, r9d
0x1800e577b  lea     r14d, [r12+1]
0x1800e5780  mov     [r15], r12d
0x1800e5783  mov     r8b, r14b; bool
0x1800e5786  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x1800e578b  mov     [rbp+80h+var_B8], r14b
0x1800e578f  mov     [rbp+80h+var_B0], rsi
0x1800e5793  test    ebx, ebx
0x1800e5795  jnz     short loc_1800E57C1
0x1800e5797  cmp     [rsi+2B4h], r12d
0x1800e579e  jnz     short loc_1800E57C1
0x1800e57a0  cmp     [rsi+64Ch], r12d
0x1800e57a7  jnz     short loc_1800E57C1
0x1800e57a9  cmp     [rsi+5C4h], r12d
0x1800e57b0  jz      short loc_1800E57C1
0x1800e57b2  lea     rdx, aLazyStoreIniti; "Lazy store initialization and no action"...
0x1800e57b9  mov     ecx, r14d
0x1800e57bc  jmp     loc_1800E58F1
0x1800e57c1  mov     rcx, rsi; this
0x1800e57c4  call    ?CheckInitialized@CCbsSession@@QEAAJXZ; CCbsSession::CheckInitialized(void)
0x1800e57c9  mov     edi, eax
0x1800e57cb  test    eax, eax
0x1800e57cd  jns     short loc_1800E5840
0x1800e57cf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e57d6  mov     dword ptr [rbp+80h+var_A0], eax
0x1800e57d9  test    rcx, rcx
0x1800e57dc  jz      short loc_1800E5820
0x1800e57de  mov     ebx, 3
0x1800e57e3  lea     r9, aCannotFinalize_1; "Cannot finalize a session that has not "...
0x1800e57ea  mov     r8d, ebx
0x1800e57ed  xor     edx, edx
0x1800e57ef  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e57f4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e57fb  lea     rax, [rbp+80h+var_A0]
0x1800e57ff  mov     [rsp+180h+var_120], rax
0x1800e5804  lea     r9, asc_1802EE7AC; ": {}"
0x1800e580b  lea     rax, [rsp+180h+var_120]
0x1800e5810  mov     r8d, ebx
0x1800e5813  mov     dl, r14b
0x1800e5816  mov     [rsp+180h+var_160], rax; int
0x1800e581b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e5820  mov     edx, 0C3h; void *
0x1800e5825  mov     rcx, [rbp+88h]; this
0x1800e582c  lea     r8, aOnecoreBaseCbs_110; "onecore\\base\\cbs\\core\\cbssessionope"...
0x1800e5833  mov     r9d, edi; char *
0x1800e5836  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e583b  jmp     loc_1800E6BBD
0x1800e5840  mov     r14, [rsi+468h]
0x1800e5847  mov     rcx, rsi; this
0x1800e584a  call    ?InspectSessionTask@CCbsSession@@AEAAHXZ; CCbsSession::InspectSessionTask(void)
0x1800e584f  mov     r13d, eax
0x1800e5852  test    eax, eax
0x1800e5854  jnz     short loc_1800E58C9
0x1800e5856  cmp     [rsi+2B0h], r12d
0x1800e585d  jz      short loc_1800E58C9
0x1800e585f  mov     rcx, rsi; this
0x1800e5862  call    ?IsImageReadOnly@CCbsSession@@QEAA_NXZ; CCbsSession::IsImageReadOnly(void)
0x1800e5867  test    al, al
0x1800e5869  jz      short loc_1800E58C9
0x1800e586b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e5872  mov     edi, 800F0843h
0x1800e5877  mov     dword ptr [rbp+80h+var_A0], edi
0x1800e587a  test    rcx, rcx
0x1800e587d  jz      short loc_1800E58BF
0x1800e587f  lea     ebx, [r13+3]
0x1800e5883  xor     edx, edx
0x1800e5885  mov     r8d, ebx
0x1800e5888  lea     r9, aNoWriteOperati_0; "No write operations are allowed on a co"...
0x1800e588f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e5894  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e589b  lea     rax, [rbp+80h+var_A0]
0x1800e589f  mov     [rsp+180h+var_120], rax
0x1800e58a4  lea     r9, asc_1802EE7AC; ": {}"
0x1800e58ab  lea     rax, [rsp+180h+var_120]
0x1800e58b0  mov     r8d, ebx
0x1800e58b3  mov     dl, 1
0x1800e58b5  mov     [rsp+180h+var_160], rax
0x1800e58ba  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e58bf  mov     edx, 0D4h
0x1800e58c4  jmp     loc_1800E5825
0x1800e58c9  or      [rsi+2B0h], ebx
0x1800e58cf  mov     eax, [rsi+2B0h]
0x1800e58d5  cmp     [rsi+410h], r12b
0x1800e58dc  jz      short loc_1800E595D
0x1800e58de  test    r13d, r13d
0x1800e58e1  jnz     short loc_1800E58FE
0x1800e58e3  test    eax, eax
0x1800e58e5  jnz     short loc_1800E58FE
0x1800e58e7  lea     rdx, aReadOnlyOperat; "Read only operations session, exit."
0x1800e58ee  lea     ecx, [rax+1]
0x1800e58f1  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1800e58f6  mov     edi, r12d
0x1800e58f9  jmp     loc_1800E6BBD
0x1800e58fe  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e5905  mov     edi, 800F0843h
0x1800e590a  mov     dword ptr [rbp+80h+var_A0], edi
0x1800e590d  test    rcx, rcx
0x1800e5910  jz      short loc_1800E5953
0x1800e5912  mov     ebx, 3
0x1800e5917  lea     r9, aNoWriteOperati; "No write operations are allowed on a re"...
0x1800e591e  mov     r8d, ebx
0x1800e5921  xor     edx, edx
0x1800e5923  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e5928  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e592f  lea     rax, [rbp+80h+var_A0]
0x1800e5933  mov     [rsp+180h+var_120], rax
0x1800e5938  lea     r9, asc_1802EE7AC; ": {}"
0x1800e593f  lea     rax, [rsp+180h+var_120]
0x1800e5944  mov     r8d, ebx
0x1800e5947  mov     dl, 1
0x1800e5949  mov     [rsp+180h+var_160], rax
0x1800e594e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e5953  mov     edx, 0E2h
0x1800e5958  jmp     loc_1800E5825
0x1800e595d  mov     rcx, [rsi+990h]
0x1800e5964  xor     edx, edx
0x1800e5966  mov     rax, [rcx]
0x1800e5969  mov     rax, [rax+58h]
0x1800e596d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5972  mov     edi, eax
0x1800e5974  test    eax, eax
0x1800e5976  jns     short loc_1800E59D2
0x1800e5978  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e597f  mov     dword ptr [rbp+80h+var_90], eax
0x1800e5982  test    rcx, rcx
0x1800e5985  jz      short loc_1800E59C8
0x1800e5987  mov     ebx, 3
0x1800e598c  lea     r9, aFailedToValida_3; "Failed to validate store version"
0x1800e5993  mov     r8d, ebx
0x1800e5996  xor     edx, edx
0x1800e5998  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e599d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e59a4  lea     rax, [rbp+80h+var_90]
0x1800e59a8  mov     [rsp+180h+var_120], rax
0x1800e59ad  lea     r9, asc_1802EE7AC; ": {}"
0x1800e59b4  lea     rax, [rsp+180h+var_120]
0x1800e59b9  mov     r8d, ebx
0x1800e59bc  mov     dl, 1
0x1800e59be  mov     [rsp+180h+var_160], rax
0x1800e59c3  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e59c8  mov     edx, 0EBh
0x1800e59cd  jmp     loc_1800E5825
0x1800e59d2  mov     eax, [rsi+2B0h]
0x1800e59d8  bt      eax, 11h
0x1800e59dc  jnb     short loc_1800E5A43
0x1800e59de  bt      eax, 12h
0x1800e59e2  jnb     short loc_1800E5A43
0x1800e59e4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e59eb  mov     edi, 80070057h
0x1800e59f0  mov     dword ptr [rbp+80h+var_A0], edi
0x1800e59f3  test    rcx, rcx
0x1800e59f6  jz      short loc_1800E5A39
0x1800e59f8  mov     ebx, 3
0x1800e59fd  lea     r9, aCannotFinalize_2; "Cannot finalize a session that has both"...
0x1800e5a04  mov     r8d, ebx
0x1800e5a07  xor     edx, edx
0x1800e5a09  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e5a0e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e5a15  lea     rax, [rbp+80h+var_A0]
0x1800e5a19  mov     [rsp+180h+var_120], rax
0x1800e5a1e  lea     r9, asc_1802EE7AC; ": {}"
0x1800e5a25  lea     rax, [rsp+180h+var_120]
0x1800e5a2a  mov     r8d, ebx
0x1800e5a2d  mov     dl, 1
0x1800e5a2f  mov     [rsp+180h+var_160], rax
0x1800e5a34  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e5a39  mov     edx, 0F3h
0x1800e5a3e  jmp     loc_1800E5825
0x1800e5a43  bt      eax, 10h
0x1800e5a47  jnb     short loc_1800E5AAE
0x1800e5a49  bt      eax, 19h
0x1800e5a4d  jnb     short loc_1800E5AAE
0x1800e5a4f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e5a56  mov     edi, 80070057h
0x1800e5a5b  mov     dword ptr [rbp+80h+var_A0], edi
0x1800e5a5e  test    rcx, rcx
0x1800e5a61  jz      short loc_1800E5AA4
0x1800e5a63  mov     ebx, 3
0x1800e5a68  lea     r9, aCannotFinalize_0; "Cannot finalize a session that has both"...
0x1800e5a6f  mov     r8d, ebx
0x1800e5a72  xor     edx, edx
0x1800e5a74  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e5a79  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e5a80  lea     rax, [rbp+80h+var_A0]
0x1800e5a84  mov     [rsp+180h+var_120], rax
0x1800e5a89  lea     r9, asc_1802EE7AC; ": {}"
0x1800e5a90  lea     rax, [rsp+180h+var_120]
0x1800e5a95  mov     r8d, ebx
0x1800e5a98  mov     dl, 1
0x1800e5a9a  mov     [rsp+180h+var_160], rax
0x1800e5a9f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e5aa4  mov     edx, 0F8h
0x1800e5aa9  jmp     loc_1800E5825
0x1800e5aae  test    byte ptr [rsi+8A0h], 10h
0x1800e5ab5  jz      loc_1800E5BAB
0x1800e5abb  mov     rcx, rsi; this
0x1800e5abe  call    ?IsClientWindowsUpdate@CCbsSession@@QEBAHXZ; CCbsSession::IsClientWindowsUpdate(void)
0x1800e5ac3  test    eax, eax
0x1800e5ac5  jnz     short loc_1800E5AF2
0x1800e5ac7  mov     rcx, [rsi+288h]
0x1800e5ace  test    rcx, rcx
0x1800e5ad1  jz      loc_1800E5BAB
0x1800e5ad7  lea     rdx, aUpdateagentlcu; "UpdateAgentLCU"
0x1800e5ade  call    cs:__imp__o__wcsicmp
0x1800e5ae5  nop     dword ptr [rax+rax+00h]
0x1800e5aea  test    eax, eax
0x1800e5aec  jnz     loc_1800E5BAB
0x1800e5af2  cmp     [rsi+910h], r12b
0x1800e5af9  jz      loc_1800E5BAB
0x1800e5aff  mov     rcx, cs:?vOneSettings@@3PEAVIServicingWOSCSettings@@EA; IServicingWOSCSettings * vOneSettings
0x1800e5b06  lea     r8, [rbp+80h+var_A0]
0x1800e5b0a  lea     rdx, aEnablepriority; "ENABLEPRIORITY"
0x1800e5b11  mov     dword ptr [rbp+80h+var_A0], r12d
0x1800e5b15  mov     rax, [rcx]
0x1800e5b18  mov     rax, [rax+30h]
0x1800e5b1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5b21  mov     ecx, eax; int
0x1800e5b23  call    ?IsExpectedOneSettingsError_HRESULT@@YA_NJ@Z; IsExpectedOneSettingsError_HRESULT(long)
0x1800e5b28  mov     edi, 1
0x1800e5b2d  test    al, al
0x1800e5b2f  jnz     short loc_1800E5B41
0x1800e5b31  mov     edx, ecx
0x1800e5b33  lea     r8, aUnableToGetThe_5; "Unable to get the OneSettings value for"...
0x1800e5b3a  mov     ecx, edi
0x1800e5b3c  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1800e5b41  mov     ecx, dword ptr [rbp+80h+var_A0]
0x1800e5b44  sub     ecx, 1
0x1800e5b47  jz      short loc_1800E5B93
0x1800e5b49  sub     ecx, 1
0x1800e5b4c  jz      short loc_1800E5B73
0x1800e5b4e  cmp     ecx, 1
0x1800e5b51  jnz     short loc_1800E5BAB
0x1800e5b53  lea     rdx, aSettingUserpre; "Setting UserPresent priority based on o"...
0x1800e5b5a  mov     ecx, edi
0x1800e5b5c  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1800e5b61  btr     dword ptr [rsi+2B4h], 1Dh
0x1800e5b69  bts     dword ptr [rsi+2B4h], 1Ch
0x1800e5b71  jmp     short loc_1800E5BAB
0x1800e5b73  lea     rdx, aSettingUserawa; "Setting UserAway priority based on ones"...
0x1800e5b7a  mov     ecx, edi
0x1800e5b7c  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1800e5b81  btr     dword ptr [rsi+2B4h], 1Ch
0x1800e5b89  bts     dword ptr [rsi+2B4h], 1Dh
0x1800e5b91  jmp     short loc_1800E5BAB
0x1800e5b93  lea     rdx, aSettingNormalP; "Setting Normal priority based on oneset"...
0x1800e5b9a  mov     ecx, edi
0x1800e5b9c  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1800e5ba1  and     dword ptr [rsi+2B4h], 0CFFFFFFFh
0x1800e5bab  mov     eax, [rsi+2B4h]
0x1800e5bb1  bt      eax, 1Ch
0x1800e5bb5  jnb     short loc_1800E5BC1
0x1800e5bb7  mov     rcx, rsi; this
0x1800e5bba  call    ?SetUserPresentPriority@CCbsSession@@QEAAXXZ; CCbsSession::SetUserPresentPriority(void)
0x1800e5bbf  jmp     short loc_1800E5BF9
0x1800e5bc1  bt      eax, 1Dh
0x1800e5bc5  jnb     short loc_1800E5BD1
0x1800e5bc7  mov     rcx, rsi; this
0x1800e5bca  call    ?SetUserAwayPriority@CCbsSession@@QEAAXXZ; CCbsSession::SetUserAwayPriority(void)
0x1800e5bcf  jmp     short loc_1800E5BF9
0x1800e5bd1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Update_EcoQos@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Update_EcoQos@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Update_EcoQos> `wil::Feature<__WilFeatureTraits_Feature_Update_EcoQos>::GetImpl(void)'::`2'::impl
0x1800e5bd8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Update_EcoQos@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Update_EcoQos>::__private_IsEnabled(void)
0x1800e5bdd  test    al, al
0x1800e5bdf  jz      short loc_1800E5BF9
0x1800e5be1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Update_EcoQos@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Update_EcoQos@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Update_EcoQos> `wil::Feature<__WilFeatureTraits_Feature_Update_EcoQos>::GetImpl(void)'::`2'::impl
0x1800e5be8  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_Update_EcoQos@@@details@wil@@QEAA?AW4Variant_Update_EcoQos@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Update_EcoQos>::__private_GetVariant(wil::VariantReportingKind,bool)
0x1800e5bed  cmp     al, 1
0x1800e5bef  jnz     short loc_1800E5BF9
0x1800e5bf1  mov     rcx, rsi; this
0x1800e5bf4  call    ?SetNormalPriorityEcoQos@CCbsSession@@QEAAXXZ; CCbsSession::SetNormalPriorityEcoQos(void)
0x1800e5bf9  mov     eax, [rsi+2B0h]
0x1800e5bff  and     eax, 200h
0x1800e5c04  mov     [rbp+80h+var_A8], eax
0x1800e5c07  mov     eax, 0
0x1800e5c0c  setnz   r12b
0x1800e5c10  and     ebx, 80000h
0x1800e5c16  mov     [rbp+80h+var_88], r12d
0x1800e5c1a  setnz   al
0x1800e5c1d  cmp     dword ptr [rsi+2F8h], 0
0x1800e5c24  mov     [rsi+4F0h], eax
0x1800e5c2a  jz      short loc_1800E5C8F
  ... truncated ...
```
