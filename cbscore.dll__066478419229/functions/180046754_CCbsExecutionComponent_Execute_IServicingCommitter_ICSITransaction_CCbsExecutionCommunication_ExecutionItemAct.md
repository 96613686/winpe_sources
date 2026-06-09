# CCbsExecutionComponent::Execute(IServicingCommitter *,ICSITransaction *,CCbsExecutionCommunication *,ExecutionItemAction)

- ea: `0x180046754`
- end: `0x180048110`
- name: `?Execute@CCbsExecutionComponent@@UEAAJPEAVIServicingCommitter@@PEAUICSITransaction@@PEAVCCbsExecutionCommunication@@W4ExecutionItemAction@@@Z`
- size: `6588`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180167760`

## callees

- `0x180010cc0`
- `0x180010f54`
- `0x1800110d0`
- `0x180012fe4`
- `0x180028e24`
- `0x180046754`
- `0x180048118`
- `0x18004854c`
- `0x18006822c`
- `0x180093a70`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800a4b58`
- `0x1800a8678`
- `0x1800bc75c`
- `0x1800eb920`
- `0x18012b54c`
- `0x1801461a4`
- `0x1801c3524`
- `0x1802d5010`

## string_xrefs

- `0x18004691e`: `onecore\base\cbs\core\cbsexecutioncomponent.cpp`
- `0x180047fd2`: `onecore\base\cbs\core\cbsexecutioncomponent.cpp`
- `0x180046859`: `Item action for Component Executions should never be ExecutionItemActionDefault because it doesn't do anything`
- `0x1800478f4`: `Failed adding unproject component operation`
- `0x180047c11`: `Failed adding unproject component operation`
- `0x1800475c8`: `Exec: Unprojecting/Unmarking Package: {}, Update: {}, UninstallDeployment/UnstageDeployment: {}`
- `0x180047018`: `Failed to begin deployment uninstallation for Update: {}`
- `0x180047656`: `Failed to begin deployment uninstallation for Update: {}`
- `0x180047a21`: `Failed to begin deployment uninstallation for Update: {}`
- `0x1800470c5`: `ComponentAnalyzerUninstallDeployment: Failed on update: {}`
- `0x1800473e7`: `ComponentAnalyzerUninstallDeployment: Failed on update: {}`
- `0x18004785b`: `ComponentAnalyzerUninstallDeployment: Failed on update: {}`
- `0x180047b78`: `ComponentAnalyzerUninstallDeployment: Failed on update: {}`
- `0x18004752d`: `Failed adding uninstall component operation`
- `0x180047cac`: `Exec: Installing Package: {}, Update: {}, InstallDeployment: {}`
- `0x180046e61`: `Exec: Unmarking Package: {}, Update: {}, UnstageDeployment: {}`
- `0x180047290`: `Failed to unpin deployment after uninstall for Update '{}'`
- `0x180046a80`: `Failed to unpin deployment for Update '{}'`
- `0x180046c52`: `Failed to unpin deployment for Update '{}'`
- `0x180046cff`: `Failed to MarkDeploymentUntaged while staging Update: {}`
- `0x180046ed9`: `Failed to MarkDeploymentUntaged while staging Update: {}`
- `0x1800471e3`: `Failed to MarkDeploymentUntaged while staging Update: {}`
- `0x180047704`: `Failed to MarkDeploymentUntaged while staging Update: {}`
- `0x1800468db`: `Could not acquire an ICSITransaction2 from ICSITransaction, mismatched wcp.dll and cbscore.dll?`
- `0x180046be2`: `Exec: Unstaging Package: {}, Update: {}, UnstageDeployment/UnpinDeployment: {}`
- `0x180046f8a`: `Exec: Unprojecting Package: {}, Update: {}, UninstallDeployment: {}`
- `0x18004798f`: `Exec: Unprojecting Package: {}, Update: {}, UninstallDeployment: {}`
- `0x18004733a`: `Failed to install manifest for Update: {}`
- `0x1800477ae`: `Failed to install manifest for Update: {}`
- `0x180047acb`: `Failed to install manifest for Update: {}`
- `0x180047ed0`: `Failed to install manifest for Update: {}`
- `0x180046b31`: `ComponentAnalyzerUnPinDeployment: Failed on update: {}`
- `0x180046db0`: `ComponentAnalyzerUnPinDeployment: Failed on update: {}`
- `0x180047494`: `ComponentAnalyzerUnPinDeployment: Failed on update: {}`
- `0x180046a1c`: `Exec: Unpinning Package: {}, Update: {}, UnpinDeployment: {}`
- `0x18004716f`: `Exec: Unpinning Package: {}, Update: {}, UnpinDeployment: {}`
- `0x180047e26`: `Failed to begin deployment installation for Update: {}`
- `0x180047f82`: `ComponentAnalyzerInstallDeployment: Failed on update: {}`
- `0x180047d15`: `Failed to get stored catalog path for package: {}`
- `0x180047df7`: `Unable to verify manifest against catalog, mark store as corrupt.`
- `0x18004806b`: `Failed adding install component operation`

## pseudocode

```c
__int64 __fastcall CCbsExecutionComponent::Execute(
        __int64 a1,
        __int64 a2,
        __int64 (__fastcall ***a3)(_QWORD, GUID *, __int64),
        __int64 a4,
        int a5)
{
  unsigned int v8; // ebx
  int v9; // edx
  __int64 v10; // rdx
  int v11; // edx
  __int64 (__fastcall *v12)(_QWORD, GUID *, __int64); // rbx
  __int64 InitPointer; // rax
  int v14; // eax
  int v15; // edx
  struct IDefinitionIdentity **v16; // rax
  int v17; // edx
  const wchar_t *v18; // rsi
  __int64 v19; // rax
  wchar_t *v20; // rcx
  __int64 v21; // rax
  const wchar_t *v22; // rcx
  int v23; // eax
  __int64 v24; // rax
  int v25; // edx
  int v26; // eax
  __int64 v27; // rax
  int v28; // edx
  int v29; // edx
  const wchar_t *v30; // rsi
  __int64 v31; // rax
  const wchar_t *v32; // rcx
  __int64 v33; // rax
  wchar_t *v34; // rcx
  int v35; // eax
  __int64 v36; // rax
  int v37; // edx
  int v38; // eax
  __int64 v39; // rax
  int v40; // edx
  int v41; // eax
  __int64 v42; // rax
  int v43; // edx
  int v44; // edx
  const wchar_t *v45; // rsi
  __int64 v46; // rax
  const wchar_t *v47; // rcx
  __int64 v48; // rax
  wchar_t *v49; // rcx
  int v50; // eax
  __int64 v51; // rax
  int v52; // edx
  int v53; // edx
  const wchar_t *v54; // rsi
  __int64 v55; // rax
  const wchar_t *v56; // rcx
  __int64 v57; // rax
  wchar_t *v58; // rcx
  int v59; // ecx
  int v60; // eax
  __int64 v61; // rax
  int v62; // edx
  int v63; // eax
  __int64 v64; // rax
  int v65; // edx
  int v66; // edx
  const wchar_t *v67; // rcx
  __int64 v68; // rax
  __int64 v69; // rax
  wchar_t *v70; // rcx
  int v71; // eax
  __int64 v72; // rax
  int v73; // edx
  int v74; // eax
  __int64 v75; // rax
  int v76; // edx
  __int64 v77; // rdx
  const wchar_t *v78; // r9
  const wchar_t *v79; // r8
  __int64 v80; // rax
  int v81; // eax
  __int64 v82; // rax
  int v83; // edx
  int v84; // eax
  __int64 v85; // rax
  int v86; // edx
  int v87; // eax
  __int64 v88; // rax
  int v89; // edx
  int v90; // eax
  int v91; // edx
  int v92; // edx
  const wchar_t *v93; // rsi
  __int64 v94; // rax
  const wchar_t *v95; // rcx
  __int64 v96; // rax
  wchar_t *v97; // rcx
  int v98; // ecx
  int v99; // eax
  __int64 v100; // rax
  int v101; // edx
  int v102; // eax
  __int64 v103; // rax
  int v104; // edx
  __int64 v105; // rcx
  const wchar_t *v106; // r9
  const wchar_t *v107; // r8
  __int64 v108; // rax
  int v109; // eax
  __int64 v110; // rax
  int v111; // edx
  int v112; // eax
  __int64 v113; // rax
  int v114; // edx
  int v115; // eax
  int v116; // edx
  int v117; // edx
  const wchar_t *v118; // rsi
  __int64 v119; // rax
  const wchar_t *v120; // rcx
  __int64 v121; // rax
  wchar_t *v122; // rcx
  int v123; // ecx
  int v124; // eax
  __int64 v125; // rax
  int v126; // edx
  __int64 v127; // rcx
  const wchar_t *v128; // r9
  const wchar_t *v129; // r8
  __int64 v130; // rax
  int v131; // eax
  __int64 v132; // rax
  int v133; // edx
  int v134; // eax
  __int64 v135; // rax
  int v136; // edx
  int v137; // eax
  int v138; // edx
  int v139; // edx
  const wchar_t *v140; // rsi
  __int64 v141; // rax
  const wchar_t *v142; // rcx
  __int64 v143; // rax
  const wchar_t *v144; // rcx
  struct CCbsSession *v145; // rdx
  int v146; // eax
  int StoredCatalogPath; // eax
  __int64 v148; // rdx
  int v149; // edx
  CCbsSession *v150; // rcx
  int v151; // eax
  __int64 v152; // rax
  int v153; // edx
  __int64 v154; // rcx
  const wchar_t *v155; // r9
  const wchar_t *v156; // r8
  __int64 v157; // rax
  int v158; // eax
  __int64 v159; // rax
  int v160; // edx
  int v161; // eax
  __int64 v162; // rdx
  int v163; // edx
  int v164; // eax
  int v165; // edx
  int v167; // [rsp+20h] [rbp-81h]
  int v168; // [rsp+20h] [rbp-81h]
  char v169[8]; // [rsp+60h] [rbp-41h] BYREF
  int v170[2]; // [rsp+68h] [rbp-39h] BYREF
  int v171[2]; // [rsp+70h] [rbp-31h] BYREF
  struct IDefinitionIdentity *v172; // [rsp+78h] [rbp-29h] BYREF
  wchar_t **v173; // [rsp+80h] [rbp-21h] BYREF
  _QWORD v174[2]; // [rsp+88h] [rbp-19h] BYREF
  char v175; // [rsp+98h] [rbp-9h]
  wchar_t *v176; // [rsp+A0h] [rbp-1h] BYREF
  __int64 v177; // [rsp+A8h] [rbp+7h] BYREF
  int v178; // [rsp+B0h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]

  v174[1] = &vComponentAnalyzerLock;
  v172 = 0;
  v174[0] = &PackageTrackerLocker::`vftable';
  v177 = 0;
  v178 = 0;
  v176 = 0;
  v175 = 0;
  MonitoredCritSecLocker::Lock((MonitoredCritSecLocker *)v174);
  v169[0] = 1;
  if ( vpfnTiLockProcess )
    vpfnTiLockProcess(0);
  if ( !a3 )
  {
    v8 = -2147024809;
    LODWORD(v176) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No transaction specified");
      *(_QWORD *)v171 = &v176;
      LOBYTE(v9) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v9,
        3,
        (unsigned int)": {}",
        (__int64)v171);
    }
    v10 = 263;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutioncomponent.cpp",
      (const char *)v8,
      v167);
    AutoCsiStoreLock::~AutoCsiStoreLock((AutoCsiStoreLock *)v169);
    MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v174);
    if ( v177 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v177 + 16LL))(v177);
      v177 = 0;
    }
LABEL_271:
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v172);
    return v8;
  }
  if ( !a5 )
  {
    v8 = -2147024809;
    LODWORD(v176) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Item action for Component Executions should never be ExecutionItemActionDefault because it doesn't do anything");
      *(_QWORD *)v171 = &v176;
      LOBYTE(v11) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v11,
        3,
        (unsigned int)": {}",
        (__int64)v171);
    }
    v10 = 265;
    goto LABEL_15;
  }
  v12 = **a3;
  InitPointer = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v177);
  v14 = v12(a3, &GUID_0e695bd1_628c_40a1_88cf_925083986d16, InitPointer);
  v8 = v14;
  if ( v14 < 0 )
  {
    LODWORD(v176) = v14;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Could not acquire an ICSITransaction2 from ICSITransaction, mismatched wcp.dll and cbscore.dll?");
      *(_QWORD *)v171 = &v176;
      LOBYTE(v15) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v15,
        3,
        (unsigned int)": {}",
        (__int64)v171);
    }
    v10 = 269;
    goto LABEL_15;
  }
  v16 = (struct IDefinitionIdentity **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v172);
  CCbsExecutionComponent::GetIdentity((CCbsExecutionComponent *)(a1 - 72), v16);
  if ( a5 != 3 )
  {
    switch ( a5 )
    {
      case 4:
        *(_QWORD *)v170 = GetFastIdentityString(v172);
        v118 = &qword_1802EB518;
        v119 = *(_QWORD *)(a1 - 40);
        v120 = &qword_1802EB518;
        if ( *(_QWORD *)(v119 + 32) )
          v120 = *(const wchar_t **)(v119 + 32);
        v121 = *(_QWORD *)(a1 - 48);
        *(_QWORD *)v171 = v120;
        v122 = (wchar_t *)&qword_1802EB518;
        if ( *(_QWORD *)(v121 + 120) )
          v122 = *(wchar_t **)(v121 + 120);
        v176 = v122;
        if ( LogAdapter::g_Logger )
        {
          LOBYTE(v117) = 1;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            v117,
            1,
            (unsigned int)"Exec: Unprojecting Package: {}, Update: {}, UninstallDeployment: {}",
            (__int64)&v176,
            (__int64)v171,
            (__int64)v170);
        }
        v123 = *(_DWORD *)(*(_QWORD *)(a1 - 32) + 692LL);
        if ( (v123 & 0x80000) != 0 || (v123 & 0x400) != 0 )
        {
          v127 = *(_QWORD *)(a1 - 48);
          v128 = &qword_1802EB518;
          v129 = &qword_1802EB518;
          v130 = *(_QWORD *)(a1 - 40);
          if ( *(_QWORD *)(v130 + 32) )
            v128 = *(const wchar_t **)(v130 + 32);
          if ( *(_QWORD *)(v127 + 120) )
            v129 = *(const wchar_t **)(v127 + 120);
          v131 = (*(__int64 (__fastcall **)(__int64, struct IDefinitionIdentity *, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 64LL))(
                   a2,
                   v172,
                   v129,
                   v128);
          v8 = v131;
          if ( v131 < 0 )
          {
            LODWORD(v176) = v131;
            if ( LogAdapter::g_Logger )
            {
              v132 = *(_QWORD *)(a1 - 40);
              if ( *(_QWORD *)(v132 + 32) )
                v118 = *(const wchar_t **)(v132 + 32);
              *(_QWORD *)v170 = v118;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to install manifest for Update: {}",
                (__int64)v170);
              *(_QWORD *)v171 = &v176;
              LOBYTE(v133) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v133,
                3,
                (unsigned int)": {}",
                (__int64)v171);
            }
            v10 = 322;
            goto LABEL_15;
          }
        }
        else
        {
          v167 = 0;
          v124 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), _QWORD, struct IDefinitionIdentity *, _QWORD))(*a3)[5])(
                   a3,
                   0,
                   v172,
                   0);
          v8 = v124;
          if ( v124 < 0 )
          {
            LODWORD(v176) = v124;
            if ( LogAdapter::g_Logger )
            {
              v125 = *(_QWORD *)(a1 - 40);
              if ( *(_QWORD *)(v125 + 32) )
                v118 = *(const wchar_t **)(v125 + 32);
              *(_QWORD *)v170 = v118;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to begin deployment uninstallation for Update: {}",
                (__int64)v170);
              *(_QWORD *)v171 = &v176;
              LOBYTE(v126) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v126,
                3,
                (unsigned int)": {}",
                (__int64)v171);
            }
            v10 = 328;
            goto LABEL_15;
          }
        }
        v134 = ComponentAnalyzerChangeDeployment(
                 *(struct CCbsSession **)(a1 - 32),
                 *(_QWORD *)(a1 - 40) + 376LL,
                 4,
                 *(_QWORD *)(a1 - 16) != 0);
        v8 = v134;
        if ( v134 < 0 )
        {
          LODWORD(v176) = v134;
          if ( LogAdapter::g_Logger )
          {
            v135 = *(_QWORD *)(a1 - 40);
            if ( *(_QWORD *)(v135 + 32) )
              v118 = *(const wchar_t **)(v135 + 32);
            *(_QWORD *)v170 = v118;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"ComponentAnalyzerUninstallDeployment: Failed on update: {}",
              (__int64)v170);
            *(_QWORD *)v171 = &v176;
            LOBYTE(v136) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v136,
              3,
              (unsigned int)": {}",
              (__int64)v171);
          }
          v10 = 334;
          goto LABEL_15;
        }
        if ( *(_QWORD *)(a1 - 16) )
        {
          v167 = 1;
          v137 = DoqAddDriverOperation(*(_QWORD *)(a1 - 32), *(_QWORD *)(a1 - 48), *(_QWORD *)(a1 - 40));
          v8 = v137;
          if ( v137 < 0 )
          {
            LODWORD(v176) = v137;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "Failed adding unproject component operation");
              *(_QWORD *)v170 = &v176;
              LOBYTE(v138) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v138,
                3,
                (unsigned int)": {}",
                (__int64)v170);
            }
            v10 = 340;
            goto LABEL_15;
          }
        }
        break;
      case 5:
        *(_QWORD *)v170 = GetFastIdentityString(v172);
        v93 = &qword_1802EB518;
        v94 = *(_QWORD *)(a1 - 40);
        v95 = &qword_1802EB518;
        if ( *(_QWORD *)(v94 + 32) )
          v95 = *(const wchar_t **)(v94 + 32);
        v96 = *(_QWORD *)(a1 - 48);
        *(_QWORD *)v171 = v95;
        v97 = (wchar_t *)&qword_1802EB518;
        if ( *(_QWORD *)(v96 + 120) )
          v97 = *(wchar_t **)(v96 + 120);
        v176 = v97;
        if ( LogAdapter::g_Logger )
        {
          LOBYTE(v92) = 1;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            v92,
            1,
            (unsigned int)"Exec: Unprojecting/Unmarking Package: {}, Update: {}, UninstallDeployment/UnstageDeployment: {}",
            (__int64)&v176,
            (__int64)v171,
            (__int64)v170);
        }
        v98 = *(_DWORD *)(*(_QWORD *)(a1 - 32) + 692LL);
        if ( (v98 & 0x80000) != 0 || (v98 & 0x400) != 0 )
        {
          v105 = *(_QWORD *)(a1 - 48);
          v106 = &qword_1802EB518;
          v107 = &qword_1802EB518;
          v108 = *(_QWORD *)(a1 - 40);
          if ( *(_QWORD *)(v108 + 32) )
            v106 = *(const wchar_t **)(v108 + 32);
          if ( *(_QWORD *)(v105 + 120) )
            v107 = *(const wchar_t **)(v105 + 120);
          v109 = (*(__int64 (__fastcall **)(__int64, struct IDefinitionIdentity *, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 64LL))(
                   a2,
                   v172,
                   v107,
                   v106);
          v8 = v109;
          if ( v109 < 0 )
          {
            LODWORD(v176) = v109;
            if ( LogAdapter::g_Logger )
            {
              v110 = *(_QWORD *)(a1 - 40);
              if ( *(_QWORD *)(v110 + 32) )
                v93 = *(const wchar_t **)(v110 + 32);
              *(_QWORD *)v170 = v93;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to install manifest for Update: {}",
                (__int64)v170);
              *(_QWORD *)v171 = &v176;
              LOBYTE(v111) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v111,
                3,
                (unsigned int)": {}",
                (__int64)v171);
            }
            v10 = 352;
            goto LABEL_15;
          }
        }
        else
        {
          v167 = 0;
          v99 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), _QWORD, struct IDefinitionIdentity *, _QWORD))(*a3)[5])(
                  a3,
                  0,
                  v172,
                  0);
          v8 = v99;
          if ( v99 < 0 )
          {
            LODWORD(v176) = v99;
            if ( LogAdapter::g_Logger )
            {
              v100 = *(_QWORD *)(a1 - 40);
              if ( *(_QWORD *)(v100 + 32) )
                v93 = *(const wchar_t **)(v100 + 32);
              *(_QWORD *)v170 = v93;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to begin deployment uninstallation for Update: {}",
                (__int64)v170);
              *(_QWORD *)v171 = &v176;
              LOBYTE(v101) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v101,
                3,
                (unsigned int)": {}",
                (__int64)v171);
            }
            v10 = 358;
            goto LABEL_15;
          }
          v167 = 0;
          v102 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IDefinitionIdentity *, _QWORD))(*(_QWORD *)v177
                                                                                                  + 72LL))(
                   v177,
                   0,
                   v172,
                   0);
          v8 = v102;
          if ( v102 < 0 )
          {
            LODWORD(v176) = v102;
            if ( LogAdapter::g_Logger )
            {
              v103 = *(_QWORD *)(a1 - 40);
              if ( *(_QWORD *)(v103 + 32) )
                v93 = *(const wchar_t **)(v103 + 32);
              *(_QWORD *)v170 = v93;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to MarkDeploymentUntaged while staging Update: {}",
                (__int64)v170);
              *(_QWORD *)v171 = &v176;
              LOBYTE(v104) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v104,
                3,
                (unsigned int)": {}",
                (__int64)v171);
            }
            v10 = 362;
            goto LABEL_15;
          }
        }
        v112 = ComponentAnalyzerChangeDeployment(
                 *(struct CCbsSession **)(a1 - 32),
                 *(_QWORD *)(a1 - 40) + 376LL,
                 4,
                 *(_QWORD *)(a1 - 16) != 0);
        v8 = v112;
        if ( v112 < 0 )
        {
          LODWORD(v176) = v112;
          if ( LogAdapter::g_Logger )
          {
            v113 = *(_QWORD *)(a1 - 40);
            if ( *(_QWORD *)(v113 + 32) )
              v93 = *(const wchar_t **)(v113 + 32);
            *(_QWORD *)v170 = v93;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"ComponentAnalyzerUninstallDeployment: Failed on update: {}",
              (__int64)v170);
            *(_QWORD *)v171 = &v176;
            LOBYTE(v114) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v114,
              3,
              (unsigned int)": {}",
              (__int64)v171);
          }
          v10 = 368;
          goto LABEL_15;
        }
        if ( *(_QWORD *)(a1 - 16) )
        {
          v167 = 1;
          v115 = DoqAddDriverOperation(*(_QWORD *)(a1 - 32), *(_QWORD *)(a1 - 48), *(_QWORD *)(a1 - 40));
          v8 = v115;
          if ( v115 < 0 )
          {
            LODWORD(v176) = v115;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "Failed adding unproject component operation");
              *(_QWORD *)v170 = &v176;
              LOBYTE(v116) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v116,
                3,
                (unsigned int)": {}",
                (__int64)v170);
            }
            v10 = 374;
            goto LABEL_15;
          }
        }
        break;
      case 6:
        *(_QWORD *)v170 = GetFastIdentityString(v172);
        v54 = &qword_1802EB518;
        v55 = *(_QWORD *)(a1 - 40);
        v56 = &qword_1802EB518;
        if ( *(_QWORD *)(v55 + 32) )
          v56 = *(const wchar_t **)(v55 + 32);
        v57 = *(_QWORD *)(a1 - 48);
        *(_QWORD *)v171 = v56;
        v58 = (wchar_t *)&qword_1802EB518;
        if ( *(_QWORD *)(v57 + 120) )
          v58 = *(wchar_t **)(v57 + 120);
        v176 = v58;
        if ( LogAdapter::g_Logger )
        {
          LOBYTE(v53) = 1;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            v53,
            1,
            (unsigned int)"Exec: Unprojecting Package: {}, Update: {}, UninstallDeployment: {}",
            (__int64)&v176,
            (__int64)v171,
            (__int64)v170);
        }
        v59 = *(_DWORD *)(*(_QWORD *)(a1 - 32) + 692LL);
        if ( (v59 & 0x80000) != 0 || (v59 & 0x400) != 0 )
        {
          v77 = *(_QWORD *)(a1 - 48);
          v78 = &qword_1802EB518;
          v79 = &qword_1802EB518;
          v80 = *(_QWORD *)(a1 - 40);
          if ( *(_QWORD *)(v80 + 32) )
            v78 = *(const wchar_t **)(v80 + 32);
          if ( *(_QWORD *)(v77 + 120) )
            v79 = *(const wchar_t **)(v77 + 120);
          v81 = (*(__int64 (__fastcall **)(__int64, struct IDefinitionIdentity *, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 64LL))(
                  a2,
                  v172,
                  v79,
                  v78);
          v8 = v81;
          if ( v81 < 0 )
          {
            LODWORD(v176) = v81;
            if ( LogAdapter::g_Logger )
            {
              v82 = *(_QWORD *)(a1 - 40);
              if ( *(_QWORD *)(v82 + 32) )
                v54 = *(const wchar_t **)(v82 + 32);
              *(_QWORD *)v170 = v54;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to install manifest for Update: {}",
                (__int64)v170);
              *(_QWORD *)v171 = &v176;
              LOBYTE(v83) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v83,
                3,
                (unsigned int)": {}",
                (__int64)v171);
            }
            v10 = 395;
            goto LABEL_15;
          }
          v84 = ComponentAnalyzerChangeDeployment(
                  *(struct CCbsSession **)(a1 - 32),
                  *(_QWORD *)(a1 - 40) + 376LL,
                  4,
                  *(_QWORD *)(a1 - 16) != 0);
          v8 = v84;
          if ( v84 < 0 )
          {
            LODWORD(v176) = v84;
            if ( LogAdapter::g_Logger )
            {
              v85 = *(_QWORD *)(a1 - 40);
              if ( *(_QWORD *)(v85 + 32) )
                v54 = *(const wchar_t **)(v85 + 32);
              *(_QWORD *)v170 = v54;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"ComponentAnalyzerUninstallDeployment: Failed on update: {}",
                (__int64)v170);
              *(_QWORD *)v171 = &v176;
              LOBYTE(v86) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v86,
                3,
                (unsigned int)": {}",
                (__int64)v171);
            }
            v10 = 400;
            goto LABEL_15;
          }
        }
        else
        {
          v167 = 0;
          v60 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), _QWORD, struct IDefinitionIdentity *, _QWORD))(*a3)[5])(
                  a3,
                  0,
                  v172,
                  0);
          v8 = v60;
          if ( v60 < 0 )
          {
            LODWORD(v176) = v60;
            if ( LogAdapter::g_Logger )
            {
              v61 = *(_QWORD *)(a1 - 40);
              if ( *(_QWORD *)(v61 + 32) )
                v54 = *(const wchar_t **)(v61 + 32);
              *(_QWORD *)v170 = v54;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to begin deployment uninstallation for Update: {}",
                (__int64)v170);
              *(_QWORD *)v171 = &v176;
              LOBYTE(v62) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v62,
                3,
                (unsigned int)": {}",
                (__int64)v171);
            }
            v10 = 406;
            goto LABEL_15;
          }
          v63 = ComponentAnalyzerChangeDeployment(
                  *(struct CCbsSession **)(a1 - 32),
                  *(_QWORD *)(a1 - 40) + 376LL,
                  4,
                  *(_QWORD *)(a1 - 16) != 0);
          v8 = v63;
          if ( v63 < 0 )
          {
            LODWORD(v176) = v63;
            if ( LogAdapter::g_Logger )
            {
              v64 = *(_QWORD *)(a1 - 40);
              if ( *(_QWORD *)(v64 + 32) )
                v54 = *(const wchar_t **)(v64 + 32);
              *(_QWORD *)v170 = v54;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"ComponentAnalyzerUninstallDeployment: Failed on update: {}",
                (__int64)v170);
              *(_QWORD *)v171 = &v176;
              LOBYTE(v65) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v65,
                3,
                (unsigned int)": {}",
                (__int64)v171);
            }
            v10 = 411;
            goto LABEL_15;
          }
          *(_QWORD *)v170 = GetFastIdentityString(v172);
          v67 = &qword_1802EB518;
          v68 = *(_QWORD *)(a1 - 40);
          if ( *(_QWORD *)(v68 + 32) )
            v67 = *(const wchar_t **)(v68 + 32);
          v69 = *(_QWORD *)(a1 - 48);
          *(_QWORD *)v171 = v67;
          v70 = (wchar_t *)&qword_1802EB518;
          if ( *(_QWORD *)(v69 + 120) )
            v70 = *(wchar_t **)(v69 + 120);
          v176 = v70;
          if ( LogAdapter::g_Logger )
          {
            LOBYTE(v66) = 1;
            LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(
              (_DWORD)LogAdapter::g_Logger,
              v66,
              1,
              (unsigned int)"Exec: Unpinning Package: {}, Update: {}, UnpinDeployment: {}",
              (__int64)&v176,
              (__int64)v171,
              (__int64)v170);
          }
          v167 = 0;
          v71 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IDefinitionIdentity *, _QWORD))(*(_QWORD *)v177 + 72LL))(
                  v177,
                  0,
                  v172,
                  0);
          v8 = v71;
          if ( v71 < 0 )
          {
            LODWORD(v176) = v71;
            if ( LogAdapter::g_Logger )
            {
              v72 = *(_QWORD *)(a1 - 40);
              if ( *(_QWORD *)(v72 + 32) )
                v54 = *(const wchar_t **)(v72 + 32);
              *(_QWORD *)v170 = v54;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to MarkDeploymentUntaged while staging Update: {}",
                (__int64)v170);
              *(_QWORD *)v171 = &v176;
              LOBYTE(v73) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v73,
                3,
                (unsigned int)": {}",
                (__int64)v171);
            }
            v10 = 418;
            goto LABEL_15;
          }
          v167 = 0;
          v74 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), _QWORD, struct IDefinitionIdentity *, _QWORD))(*a3)[6])(
                  a3,
                  0,
                  v172,
                  0);
          v8 = v74;
          if ( v74 < 0 )
          {
            LODWORD(v176) = v74;
            if ( LogAdapter::g_Logger )
            {
              v75 = *(_QWORD *)(a1 - 40);
              if ( *(_QWORD *)(v75 + 32) )
                v54 = *(const wchar_t **)(v75 + 32);
              *(_QWORD *)v170 = v54;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to unpin deployment after uninstall for Update '{}'",
                (__int64)v170);
              *(_QWORD *)v171 = &v176;
              LOBYTE(v76) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v76,
                3,
                (unsigned int)": {}",
                (__int64)v171);
            }
            v10 = 422;
            goto LABEL_15;
          }
        }
        v87 = ComponentAnalyzerChangeDeployment(
                *(struct CCbsSession **)(a1 - 32),
                *(_QWORD *)(a1 - 40) + 376LL,
                2,
                *(_QWORD *)(a1 - 16) != 0);
        v8 = v87;
        if ( v87 < 0 )
        {
          LODWORD(v176) = v87;
          if ( LogAdapter::g_Logger )
          {
            v88 = *(_QWORD *)(a1 - 40);
            if ( *(_QWORD *)(v88 + 32) )
              v54 = *(const wchar_t **)(v88 + 32);
            *(_QWORD *)v170 = v54;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"ComponentAnalyzerUnPinDeployment: Failed on update: {}",
              (__int64)v170);
            *(_QWORD *)v171 = &v176;
            LOBYTE(v89) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v89,
              3,
              (unsigned int)": {}",
              (__int64)v171);
          }
          v10 = 428;
          goto LABEL_15;
        }
        if ( *(_QWORD *)(a1 - 16) )
        {
          v167 = 1;
          v90 = DoqAddDriverOperation(*(_QWORD *)(a1 - 32), *(_QWORD *)(a1 - 48), *(_QWORD *)(a1 - 40));
          v8 = v90;
          if ( v90 < 0 )
          {
            LODWORD(v176) = v90;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "Failed adding uninstall component operation");
              *(_QWORD *)v170 = &v176;
              LOBYTE(v91) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v91,
                3,
                (unsigned int)": {}",
                (__int64)v170);
            }
            v10 = 434;
            goto LABEL_15;
          }
        }
        break;
      case 7:
        *(_QWORD *)v170 = GetFastIdentityString(v172);
        v45 = &qword_1802EB518;
        v46 = *(_QWORD *)(a1 - 40);
        v47 = &qword_1802EB518;
        if ( *(_QWORD *)(v46 + 32) )
          v47 = *(const wchar_t **)(v46 + 32);
        v48 = *(_QWORD *)(a1 - 48);
        *(_QWORD *)v171 = v47;
        v49 = (wchar_t *)&qword_1802EB518;
        if ( *(_QWORD *)(v48 + 120) )
          v49 = *(wchar_t **)(v48 + 120);
        v176 = v49;
        if ( LogAdapter::g_Logger )
        {
          LOBYTE(v44) = 1;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            v44,
            1,
            (unsigned int)"Exec: Unmarking Package: {}, Update: {}, UnstageDeployment: {}",
            (__int64)&v176,
            (__int64)v171,
            (__int64)v170);
        }
        v167 = 0;
        v50 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IDefinitionIdentity *, _QWORD))(*(_QWORD *)v177 + 72LL))(
                v177,
                0,
                v172,
                0);
        v8 = v50;
        if ( v50 < 0 )
        {
          LODWORD(v176) = v50;
          if ( LogAdapter::g_Logger )
          {
            v51 = *(_QWORD *)(a1 - 40);
            if ( *(_QWORD *)(v51 + 32) )
              v45 = *(const wchar_t **)(v51 + 32);
            *(_QWORD *)v170 = v45;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed to MarkDeploymentUntaged while staging Update: {}",
              (__int64)v170);
            *(_QWORD *)v171 = &v176;
            LOBYTE(v52) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v52,
              3,
              (unsigned int)": {}",
              (__int64)v171);
          }
          v10 = 384;
          goto LABEL_15;
        }
        break;
      case 8:
        *(_QWORD *)v170 = GetFastIdentityString(v172);
        v30 = &qword_1802EB518;
        v31 = *(_QWORD *)(a1 - 40);
        v32 = &qword_1802EB518;
        if ( *(_QWORD *)(v31 + 32) )
          v32 = *(const wchar_t **)(v31 + 32);
        v33 = *(_QWORD *)(a1 - 48);
        *(_QWORD *)v171 = v32;
        v34 = (wchar_t *)&qword_1802EB518;
        if ( *(_QWORD *)(v33 + 120) )
          v34 = *(wchar_t **)(v33 + 120);
        v176 = v34;
        if ( LogAdapter::g_Logger )
        {
          LOBYTE(v29) = 1;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            v29,
            1,
            (unsigned int)"Exec: Unstaging Package: {}, Update: {}, UnstageDeployment/UnpinDeployment: {}",
            (__int64)&v176,
            (__int64)v171,
            (__int64)v170);
        }
        v167 = 0;
        v35 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), _QWORD, struct IDefinitionIdentity *, _QWORD))(*a3)[6])(
                a3,
                0,
                v172,
                0);
        v8 = v35;
        if ( v35 < 0 )
        {
          LODWORD(v176) = v35;
          if ( LogAdapter::g_Logger )
          {
            v36 = *(_QWORD *)(a1 - 40);
            if ( *(_QWORD *)(v36 + 32) )
              v30 = *(const wchar_t **)(v36 + 32);
            *(_QWORD *)v170 = v30;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed to unpin deployment for Update '{}'",
              (__int64)v170);
            *(_QWORD *)v171 = &v176;
            LOBYTE(v37) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v37,
              3,
              (unsigned int)": {}",
              (__int64)v171);
          }
          v10 = 288;
          goto LABEL_15;
        }
        v167 = 0;
        v38 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IDefinitionIdentity *, _QWORD))(*(_QWORD *)v177 + 72LL))(
                v177,
                0,
                v172,
                0);
        v8 = v38;
        if ( v38 < 0 )
        {
          LODWORD(v176) = v38;
          if ( LogAdapter::g_Logger )
          {
            v39 = *(_QWORD *)(a1 - 40);
            if ( *(_QWORD *)(v39 + 32) )
              v30 = *(const wchar_t **)(v39 + 32);
            *(_QWORD *)v170 = v30;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed to MarkDeploymentUntaged while staging Update: {}",
              (__int64)v170);
            *(_QWORD *)v171 = &v176;
            LOBYTE(v40) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v40,
              3,
              (unsigned int)": {}",
              (__int64)v171);
          }
          v10 = 292;
          goto LABEL_15;
        }
        v41 = ComponentAnalyzerChangeDeployment(
                *(struct CCbsSession **)(a1 - 32),
                *(_QWORD *)(a1 - 40) + 376LL,
                2,
                *(_QWORD *)(a1 - 16) != 0);
        v8 = v41;
        if ( v41 < 0 )
        {
          LODWORD(v176) = v41;
          if ( LogAdapter::g_Logger )
          {
            v42 = *(_QWORD *)(a1 - 40);
            if ( *(_QWORD *)(v42 + 32) )
              v30 = *(const wchar_t **)(v42 + 32);
            *(_QWORD *)v170 = v30;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"ComponentAnalyzerUnPinDeployment: Failed on update: {}",
              (__int64)v170);
            *(_QWORD *)v171 = &v176;
            LOBYTE(v43) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v43,
              3,
              (unsigned int)": {}",
              (__int64)v171);
          }
          v10 = 297;
          goto LABEL_15;
        }
        break;
      case 9:
        *(_QWORD *)v171 = GetFastIdentityString(v172);
        v18 = &qword_1802EB518;
        v19 = *(_QWORD *)(a1 - 40);
        v20 = (wchar_t *)&qword_1802EB518;
        if ( *(_QWORD *)(v19 + 32) )
          v20 = *(wchar_t **)(v19 + 32);
        v21 = *(_QWORD *)(a1 - 48);
        v176 = v20;
        v22 = &qword_1802EB518;
        if ( *(_QWORD *)(v21 + 120) )
          v22 = *(const wchar_t **)(v21 + 120);
        *(_QWORD *)v170 = v22;
        if ( LogAdapter::g_Logger )
        {
          LOBYTE(v17) = 1;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            v17,
            1,
            (unsigned int)"Exec: Unpinning Package: {}, Update: {}, UnpinDeployment: {}",
            (__int64)v170,
            (__int64)&v176,
            (__int64)v171);
        }
        v167 = 0;
        v23 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), _QWORD, struct IDefinitionIdentity *, _QWORD))(*a3)[6])(
                a3,
                0,
                v172,
                0);
        v8 = v23;
        if ( v23 < 0 )
        {
          LODWORD(v176) = v23;
          if ( LogAdapter::g_Logger )
          {
            v24 = *(_QWORD *)(a1 - 40);
            if ( *(_QWORD *)(v24 + 32) )
              v18 = *(const wchar_t **)(v24 + 32);
            *(_QWORD *)v170 = v18;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed to unpin deployment for Update '{}'",
              (__int64)v170);
            *(_QWORD *)v171 = &v176;
            LOBYTE(v25) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v25,
              3,
              (unsigned int)": {}",
              (__int64)v171);
          }
          v10 = 306;
          goto LABEL_15;
        }
        v26 = ComponentAnalyzerChangeDeployment(
                *(struct CCbsSession **)(a1 - 32),
                *(_QWORD *)(a1 - 40) + 376LL,
                2,
                *(_QWORD *)(a1 - 16) != 0);
        v8 = v26;
        if ( v26 < 0 )
        {
          LODWORD(v176) = v26;
          if ( LogAdapter::g_Logger )
          {
            v27 = *(_QWORD *)(a1 - 40);
            if ( *(_QWORD *)(v27 + 32) )
              v18 = *(const wchar_t **)(v27 + 32);
            *(_QWORD *)v170 = v18;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"ComponentAnalyzerUnPinDeployment: Failed on update: {}",
              (__int64)v170);
            *(_QWORD *)v171 = &v176;
            LOBYTE(v28) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v28,
              3,
              (unsigned int)": {}",
              (__int64)v171);
          }
          v10 = 311;
          goto LABEL_15;
        }
        break;
    }
LABEL_268:
    AutoCsiStoreLock::~AutoCsiStoreLock((AutoCsiStoreLock *)v169);
    MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v174);
    if ( v177 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v177 + 16LL))(v177);
      v177 = 0;
    }
    v8 = 0;
    goto LABEL_271;
  }
  *(_QWORD *)v170 = GetFastIdentityString(v172);
  v140 = &qword_1802EB518;
  v141 = *(_QWORD *)(a1 - 40);
  v142 = &qword_1802EB518;
  if ( *(_QWORD *)(v141 + 32) )
    v142 = *(const wchar_t **)(v141 + 32);
  v143 = *(_QWORD *)(a1 - 48);
  *(_QWORD *)v171 = v142;
  v144 = &qword_1802EB518;
  if ( *(_QWORD *)(v143 + 120) )
    v144 = *(const wchar_t **)(v143 + 120);
  v173 = (wchar_t **)v144;
  if ( LogAdapter::g_Logger )
  {
    LOBYTE(v139) = 1;
    LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(
      (_DWORD)LogAdapter::g_Logger,
      v139,
      1,
      (unsigned int)"Exec: Installing Package: {}, Update: {}, InstallDeployment: {}",
      (__int64)&v173,
      (__int64)v171,
      (__int64)v170);
  }
  v145 = *(struct CCbsSession **)(a1 - 32);
  v146 = *((_DWORD *)v145 + 173);
  if ( (v146 & 0x80000) != 0 || (v146 & 0x400) != 0 )
  {
    v154 = *(_QWORD *)(a1 - 48);
    v155 = &qword_1802EB518;
    v156 = &qword_1802EB518;
    v157 = *(_QWORD *)(a1 - 40);
    if ( *(_QWORD *)(v157 + 32) )
      v155 = *(const wchar_t **)(v157 + 32);
    if ( *(_QWORD *)(v154 + 120) )
      v156 = *(const wchar_t **)(v154 + 120);
    v158 = (*(__int64 (__fastcall **)(__int64, struct IDefinitionIdentity *, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 56LL))(
             a2,
             v172,
             v156,
             v155);
    v8 = v158;
    if ( v158 < 0 )
    {
      LODWORD(v176) = v158;
      if ( LogAdapter::g_Logger )
      {
        v159 = *(_QWORD *)(a1 - 40);
        if ( *(_QWORD *)(v159 + 32) )
          v140 = *(const wchar_t **)(v159 + 32);
        v173 = (wchar_t **)v140;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to install manifest for Update: {}",
          (__int64)&v173);
        *(_QWORD *)v170 = &v176;
        LOBYTE(v160) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v160,
          3,
          (unsigned int)": {}",
          (__int64)v170);
      }
      v10 = 449;
      goto LABEL_15;
    }
  }
  else
  {
    StoredCatalogPath = CCbsPackage::GetStoredCatalogPath(*(CCbsPackage **)(*(_QWORD *)(a1 - 40) + 24LL), v145, &v176);
    v8 = StoredCatalogPath;
    if ( StoredCatalogPath < 0 )
    {
      LODWORD(v176) = StoredCatalogPath;
      if ( LogAdapter::g_Logger )
      {
        v148 = *(_QWORD *)(*(_QWORD *)(a1 - 40) + 24LL);
        if ( *(_QWORD *)(v148 + 120) )
          v140 = *(const wchar_t **)(v148 + 120);
        v173 = (wchar_t **)v140;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to get stored catalog path for package: {}",
          (__int64)&v173);
        *(_QWORD *)v170 = &v176;
        LOBYTE(v149) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v149,
          3,
          (unsigned int)": {}",
          (__int64)v170);
      }
      v10 = 455;
      goto LABEL_15;
    }
    v167 = 0;
    v8 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), _QWORD, struct IDefinitionIdentity *, _QWORD))(*a3)[3])(
           a3,
           0,
           v172,
           0);
    if ( (v8 & 0x80000000) != 0 )
    {
      if ( !(unsigned int)CCbsSession::IsOffline(*(CCbsSession **)(a1 - 32)) )
      {
        v151 = VerifyCatalogAndManifest(v150, v176);
        if ( v151 < 0 )
        {
          LogAdapter::TraceAtLevelIfFailed<long,>(
            1,
            (unsigned int)v151,
            "Unable to verify manifest against catalog, mark store as corrupt.");
          CCbsSession::MarkPackageStoreCorrupt(*(CCbsSession **)(a1 - 32));
        }
      }
      LODWORD(v176) = v8;
      if ( LogAdapter::g_Logger )
      {
        v152 = *(_QWORD *)(a1 - 40);
        if ( *(_QWORD *)(v152 + 32) )
          v140 = *(const wchar_t **)(v152 + 32);
        v173 = (wchar_t **)v140;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to begin deployment installation for Update: {}",
          (__int64)&v173);
        *(_QWORD *)v170 = &v176;
        LOBYTE(v153) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v153,
          3,
          (unsigned int)": {}",
          (__int64)v170);
      }
      v10 = 486;
      goto LABEL_15;
    }
  }
  v161 = ComponentAnalyzerChangeDeployment(
           *(struct CCbsSession **)(a1 - 32),
           *(_QWORD *)(a1 - 40) + 376LL,
           3,
           *(_QWORD *)(a1 - 16) != 0);
  v8 = v161;
  if ( v161 >= 0 )
  {
    if ( *(_QWORD *)(a1 - 16) )
    {
      v167 = 0;
      v164 = DoqAddDriverOperation(*(_QWORD *)(a1 - 32), *(_QWORD *)(a1 - 48), *(_QWORD *)(a1 - 40));
      v8 = v164;
      if ( v164 < 0 )
      {
        LODWORD(v176) = v164;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed adding install component operation");
          v173 = &v176;
          LOBYTE(v165) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v165,
            3,
            (unsigned int)": {}",
            (__int64)&v173);
        }
        v10 = 499;
        goto LABEL_15;
      }
    }
    goto LABEL_268;
  }
  LODWORD(v176) = v161;
  if ( LogAdapter::g_Logger )
  {
    v162 = *(_QWORD *)(a1 - 40);
    if ( *(_QWORD *)(v162 + 32) )
      v140 = *(const wchar_t **)(v162 + 32);
    v173 = (wchar_t **)v140;
    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
      (_DWORD)LogAdapter::g_Logger,
      0,
      3,
      (unsigned int)"ComponentAnalyzerInstallDeployment: Failed on update: {}",
      (__int64)&v173);
    *(_QWORD *)v170 = &v176;
    LOBYTE(v163) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v163,
      3,
      (unsigned int)": {}",
      (__int64)v170);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1ED,
    (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutioncomponent.cpp",
    (const char *)v8,
    v168);
  if ( vpfnTiUnlockProcess )
    vpfnTiUnlockProcess();
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v174);
  if ( v177 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v177 + 16LL))(v177);
    v177 = 0;
  }
  if ( v172 )
    (*(void (__fastcall **)(struct IDefinitionIdentity *))(*(_QWORD *)v172 + 16LL))(v172);
  return v8;
}

```

## disassembly

```asm
0x180046754  mov     [rsp-8+arg_18], rbx
0x180046759  push    rbp
0x18004675a  push    rsi
0x18004675b  push    rdi
0x18004675c  push    r12
0x18004675e  push    r13
0x180046760  push    r14
0x180046762  push    r15
0x180046764  lea     rbp, [rsp-1Fh]
0x180046769  sub     rsp, 0C0h
0x180046770  mov     rax, cs:__security_cookie
0x180046777  xor     rax, rsp
0x18004677a  mov     [rbp+4Fh+var_38], rax
0x18004677e  xor     r13d, r13d
0x180046781  lea     rax, ?vComponentAnalyzerLock@@3UMonitoredCritSec@@A; MonitoredCritSec vComponentAnalyzerLock
0x180046788  mov     [rbp+4Fh+var_60], rax
0x18004678c  mov     rdi, rcx
0x18004678f  lea     rax, ??_7PackageTrackerLocker@@6B@; const PackageTrackerLocker::`vftable'
0x180046796  mov     [rbp+4Fh+var_78], r13
0x18004679a  lea     rcx, [rbp+4Fh+var_68]; this
0x18004679e  mov     [rbp+4Fh+var_68], rax
0x1800467a2  mov     r15, r8
0x1800467a5  mov     [rbp+4Fh+var_48], r13
0x1800467a9  mov     r12, rdx
0x1800467ac  mov     [rbp+4Fh+var_40], r13d
0x1800467b0  mov     [rbp+4Fh+var_50], r13
0x1800467b4  mov     [rbp+4Fh+var_58], r13b
0x1800467b8  call    ?Lock@MonitoredCritSecLocker@@UEAAXXZ; MonitoredCritSecLocker::Lock(void)
0x1800467bd  mov     rax, cs:?vpfnTiLockProcess@@3P6AHH@ZEA; int (*vpfnTiLockProcess)(int)
0x1800467c4  mov     [rbp+4Fh+var_90], 1
0x1800467c8  test    rax, rax
0x1800467cb  jz      short loc_1800467D4
0x1800467cd  xor     ecx, ecx
0x1800467cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800467d4  test    r15, r15
0x1800467d7  jnz     short loc_180046835
0x1800467d9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800467e0  mov     ebx, 80070057h
0x1800467e5  mov     dword ptr [rbp+4Fh+var_50], ebx
0x1800467e8  test    rcx, rcx
0x1800467eb  jz      short loc_18004682B
0x1800467ed  lea     r14d, [r15+3]
0x1800467f1  xor     edx, edx
0x1800467f3  mov     r8d, r14d
0x1800467f6  lea     r9, aNoTransactionS_0; "No transaction specified"
0x1800467fd  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180046802  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180046809  lea     rax, [rbp+4Fh+var_50]
0x18004680d  mov     qword ptr [rbp+4Fh+var_80], rax
0x180046811  lea     r9, asc_1802EE7AC; ": {}"
0x180046818  lea     rax, [rbp+4Fh+var_80]
0x18004681c  mov     r8d, r14d
0x18004681f  mov     dl, 1
0x180046821  mov     qword ptr [rsp+0F0h+var_D0], rax
0x180046826  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004682b  mov     edx, 107h
0x180046830  jmp     loc_18004691A
0x180046835  mov     esi, [rbp+4Fh+arg_20]
0x180046838  test    esi, esi
0x18004683a  jnz     short loc_180046898
0x18004683c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180046843  mov     ebx, 80070057h
0x180046848  mov     dword ptr [rbp+4Fh+var_50], ebx
0x18004684b  test    rcx, rcx
0x18004684e  jz      short loc_18004688E
0x180046850  lea     r14d, [rsi+3]
0x180046854  xor     edx, edx
0x180046856  mov     r8d, r14d
0x180046859  lea     r9, aItemActionForC; "Item action for Component Executions sh"...
0x180046860  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180046865  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004686c  lea     rax, [rbp+4Fh+var_50]
0x180046870  mov     qword ptr [rbp+4Fh+var_80], rax
0x180046874  lea     r9, asc_1802EE7AC; ": {}"
0x18004687b  lea     rax, [rbp+4Fh+var_80]
0x18004687f  mov     r8d, r14d
0x180046882  mov     dl, 1
0x180046884  mov     qword ptr [rsp+0F0h+var_D0], rax
0x180046889  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004688e  mov     edx, 109h
0x180046893  jmp     loc_18004691A
0x180046898  mov     rax, [r15]
0x18004689b  lea     rcx, [rbp+4Fh+var_48]
0x18004689f  mov     rbx, [rax]
0x1800468a2  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1800468a7  mov     r8, rax
0x1800468aa  lea     rdx, _GUID_0e695bd1_628c_40a1_88cf_925083986d16
0x1800468b1  mov     rax, rbx
0x1800468b4  mov     rcx, r15
0x1800468b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800468bc  mov     ebx, eax
0x1800468be  test    eax, eax
0x1800468c0  jns     loc_180046961
0x1800468c6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800468cd  mov     dword ptr [rbp+4Fh+var_50], eax
0x1800468d0  test    rcx, rcx
0x1800468d3  jz      short loc_180046915
0x1800468d5  mov     r14d, 3
0x1800468db  lea     r9, aCouldNotAcquir; "Could not acquire an ICSITransaction2 f"...
0x1800468e2  mov     r8d, r14d
0x1800468e5  xor     edx, edx
0x1800468e7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800468ec  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800468f3  lea     rax, [rbp+4Fh+var_50]
0x1800468f7  mov     qword ptr [rbp+4Fh+var_80], rax
0x1800468fb  lea     r9, asc_1802EE7AC; ": {}"
0x180046902  lea     rax, [rbp+4Fh+var_80]
0x180046906  mov     r8d, r14d
0x180046909  mov     dl, 1
0x18004690b  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x180046910  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180046915  mov     edx, 10Dh; void *
0x18004691a  mov     rcx, [rbp+57h]; this
0x18004691e  lea     r8, aOnecoreBaseCbs_139; "onecore\\base\\cbs\\core\\cbsexecutionc"...
0x180046925  mov     r9d, ebx; char *
0x180046928  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004692d  lea     rcx, [rbp+4Fh+var_90]; this
0x180046931  call    ??1AutoCsiStoreLock@@QEAA@XZ; AutoCsiStoreLock::~AutoCsiStoreLock(void)
0x180046936  lea     rcx, [rbp+4Fh+var_68]; this
0x18004693a  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x18004693f  mov     rcx, [rbp+4Fh+var_48]
0x180046943  test    rcx, rcx
0x180046946  jz      loc_1800480DD
0x18004694c  mov     rax, [rcx]
0x18004694f  mov     rax, [rax+10h]
0x180046953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046958  mov     [rbp+4Fh+var_48], r13
0x18004695c  jmp     loc_1800480DD
0x180046961  lea     rcx, [rbp+4Fh+var_78]
0x180046965  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x18004696a  lea     rcx, [rdi-48h]; this
0x18004696e  mov     rdx, rax; struct IDefinitionIdentity **
0x180046971  call    ?GetIdentity@CCbsExecutionComponent@@QEAAXPEAPEAUIDefinitionIdentity@@@Z; CCbsExecutionComponent::GetIdentity(IDefinitionIdentity * *)
0x180046976  mov     r14d, 3
0x18004697c  sub     esi, r14d
0x18004697f  jz      loc_180047C55
0x180046985  sub     esi, 1
0x180046988  jz      loc_180047938
0x18004698e  sub     esi, 1
0x180046991  jz      loc_180047571
0x180046997  sub     esi, 1
0x18004699a  jz      loc_180046F33
0x1800469a0  sub     esi, 1
0x1800469a3  jz      loc_180046E0A
0x1800469a9  sub     esi, 1
0x1800469ac  jz      loc_180046B8B
0x1800469b2  cmp     esi, 1
0x1800469b5  jnz     loc_1800480AF
0x1800469bb  mov     rcx, [rbp+4Fh+var_78]; struct IDefinitionIdentity *
0x1800469bf  call    ?GetFastIdentityString@@YAPEA_WPEAUIDefinitionIdentity@@@Z; GetFastIdentityString(IDefinitionIdentity *)
0x1800469c4  mov     qword ptr [rbp+4Fh+var_80], rax
0x1800469c8  lea     rsi, qword_1802EB518
0x1800469cf  mov     rax, [rdi-28h]
0x1800469d3  mov     rcx, rsi
0x1800469d6  cmp     [rax+20h], r13
0x1800469da  cmovnz  rcx, [rax+20h]
0x1800469df  mov     rax, [rdi-30h]
0x1800469e3  mov     [rbp+4Fh+var_50], rcx
0x1800469e7  mov     rcx, rsi
0x1800469ea  cmp     [rax+78h], r13
0x1800469ee  cmovnz  rcx, [rax+78h]
0x1800469f3  mov     qword ptr [rbp+4Fh+var_88], rcx
0x1800469f7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800469fe  test    rcx, rcx
0x180046a01  jz      short loc_180046A31
0x180046a03  lea     rax, [rbp+4Fh+var_80]
0x180046a07  mov     [rsp+0F0h+var_C0], rax
0x180046a0c  lea     r8d, [r14-2]
0x180046a10  lea     rax, [rbp+4Fh+var_50]
0x180046a14  mov     dl, r8b
0x180046a17  mov     [rsp+0F0h+var_C8], rax
0x180046a1c  lea     r9, aExecUnpinningP; "Exec: Unpinning Package: {}, Update: {}"...
0x180046a23  lea     rax, [rbp+4Fh+var_88]
0x180046a27  mov     qword ptr [rsp+0F0h+var_D0], rax
0x180046a2c  call    ??$LogNumObjects@PEB_WVAutoScz@@PEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBVAutoScz@@AEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,AutoScz const &,wchar_t * const &)
0x180046a31  mov     rcx, [rdi-28h]
0x180046a35  lea     rdx, [rbp+4Fh+var_40]
0x180046a39  mov     rax, [r15]
0x180046a3c  xor     r9d, r9d
0x180046a3f  mov     r8, [rbp+4Fh+var_78]
0x180046a43  mov     [rsp+0F0h+var_C0], rdx
0x180046a48  xor     edx, edx
0x180046a4a  mov     rcx, [rcx+1C8h]
0x180046a51  mov     rax, [rax+30h]
0x180046a55  mov     [rsp+0F0h+var_C8], rcx
0x180046a5a  mov     rcx, r15
0x180046a5d  mov     qword ptr [rsp+0F0h+var_D0], r13
0x180046a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a67  mov     ebx, eax
0x180046a69  test    eax, eax
0x180046a6b  jns     short loc_180046ADA
0x180046a6d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180046a74  mov     dword ptr [rbp+4Fh+var_50], eax
0x180046a77  test    rcx, rcx
0x180046a7a  jz      short loc_180046AD0
0x180046a7c  mov     rax, [rdi-28h]
0x180046a80  lea     r9, aFailedToUnpinD; "Failed to unpin deployment for Update '"...
0x180046a87  mov     r8d, r14d
0x180046a8a  cmp     [rax+20h], r13
0x180046a8e  cmovnz  rsi, [rax+20h]
0x180046a93  lea     rax, [rbp+4Fh+var_88]
0x180046a97  xor     edx, edx
0x180046a99  mov     qword ptr [rsp+0F0h+var_D0], rax
0x180046a9e  mov     qword ptr [rbp+4Fh+var_88], rsi
0x180046aa2  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180046aa7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180046aae  lea     rax, [rbp+4Fh+var_50]
0x180046ab2  mov     qword ptr [rbp+4Fh+var_80], rax
0x180046ab6  lea     r9, asc_1802EE7AC; ": {}"
0x180046abd  lea     rax, [rbp+4Fh+var_80]
0x180046ac1  mov     r8d, r14d
0x180046ac4  mov     dl, 1
0x180046ac6  mov     qword ptr [rsp+0F0h+var_D0], rax
0x180046acb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180046ad0  mov     edx, 132h
0x180046ad5  jmp     loc_18004691A
0x180046ada  mov     rdx, [rdi-28h]
0x180046ade  mov     eax, r13d
0x180046ae1  cmp     [rdi-10h], r13
0x180046ae5  mov     r9, [rbp+4Fh+var_78]
0x180046ae9  setnz   al
0x180046aec  lea     rcx, [rdx+178h]
0x180046af3  mov     dword ptr [rsp+0F0h+var_C0], eax
0x180046af7  mov     rdx, [rdx+1C8h]
0x180046afe  mov     dword ptr [rsp+0F0h+var_C8], 2
0x180046b06  mov     qword ptr [rsp+0F0h+var_D0], rcx
0x180046b0b  mov     rcx, [rdi-20h]
0x180046b0f  call    ComponentAnalyzerChangeDeployment
0x180046b14  mov     ebx, eax
0x180046b16  test    eax, eax
0x180046b18  jns     loc_1800480AF
0x180046b1e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180046b25  mov     dword ptr [rbp+4Fh+var_50], eax
0x180046b28  test    rcx, rcx
0x180046b2b  jz      short loc_180046B81
0x180046b2d  mov     rax, [rdi-28h]
0x180046b31  lea     r9, aComponentanaly; "ComponentAnalyzerUnPinDeployment: Faile"...
0x180046b38  mov     r8d, r14d
0x180046b3b  cmp     [rax+20h], r13
0x180046b3f  cmovnz  rsi, [rax+20h]
0x180046b44  lea     rax, [rbp+4Fh+var_88]
0x180046b48  xor     edx, edx
0x180046b4a  mov     qword ptr [rsp+0F0h+var_D0], rax
0x180046b4f  mov     qword ptr [rbp+4Fh+var_88], rsi
0x180046b53  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180046b58  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180046b5f  lea     rax, [rbp+4Fh+var_50]
0x180046b63  mov     qword ptr [rbp+4Fh+var_80], rax
0x180046b67  lea     r9, asc_1802EE7AC; ": {}"
0x180046b6e  lea     rax, [rbp+4Fh+var_80]
0x180046b72  mov     r8d, r14d
0x180046b75  mov     dl, 1
0x180046b77  mov     qword ptr [rsp+0F0h+var_D0], rax
0x180046b7c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180046b81  mov     edx, 137h
0x180046b86  jmp     loc_18004691A
0x180046b8b  mov     rcx, [rbp+4Fh+var_78]; struct IDefinitionIdentity *
0x180046b8f  call    ?GetFastIdentityString@@YAPEA_WPEAUIDefinitionIdentity@@@Z; GetFastIdentityString(IDefinitionIdentity *)
0x180046b94  mov     qword ptr [rbp+4Fh+var_88], rax
0x180046b98  lea     rsi, qword_1802EB518
0x180046b9f  mov     rax, [rdi-28h]
0x180046ba3  mov     rcx, rsi
0x180046ba6  cmp     [rax+20h], r13
0x180046baa  cmovnz  rcx, [rax+20h]
0x180046baf  mov     rax, [rdi-30h]
0x180046bb3  mov     qword ptr [rbp+4Fh+var_80], rcx
0x180046bb7  mov     rcx, rsi
0x180046bba  cmp     [rax+78h], r13
0x180046bbe  cmovnz  rcx, [rax+78h]
0x180046bc3  mov     [rbp+4Fh+var_50], rcx
0x180046bc7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180046bce  test    rcx, rcx
0x180046bd1  jz      short loc_180046C03
0x180046bd3  lea     rax, [rbp+4Fh+var_88]
0x180046bd7  mov     r8d, 1
0x180046bdd  mov     [rsp+0F0h+var_C0], rax
0x180046be2  lea     r9, aExecUnstagingP; "Exec: Unstaging Package: {}, Update: {}"...
0x180046be9  lea     rax, [rbp+4Fh+var_80]
0x180046bed  mov     dl, r8b
0x180046bf0  mov     [rsp+0F0h+var_C8], rax
0x180046bf5  lea     rax, [rbp+4Fh+var_50]
0x180046bf9  mov     qword ptr [rsp+0F0h+var_D0], rax
0x180046bfe  call    ??$LogNumObjects@PEB_WVAutoScz@@PEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBVAutoScz@@AEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,AutoScz const &,wchar_t * const &)
0x180046c03  mov     rcx, [rdi-28h]
0x180046c07  lea     rdx, [rbp+4Fh+var_40]
0x180046c0b  mov     rax, [r15]
0x180046c0e  xor     r9d, r9d
0x180046c11  mov     r8, [rbp+4Fh+var_78]
0x180046c15  mov     [rsp+0F0h+var_C0], rdx
0x180046c1a  xor     edx, edx
0x180046c1c  mov     rcx, [rcx+1C8h]
0x180046c23  mov     rax, [rax+30h]
0x180046c27  mov     [rsp+0F0h+var_C8], rcx
0x180046c2c  mov     rcx, r15
0x180046c2f  mov     qword ptr [rsp+0F0h+var_D0], r13
0x180046c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c39  mov     ebx, eax
0x180046c3b  test    eax, eax
0x180046c3d  jns     short loc_180046CAC
0x180046c3f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
  ... truncated ...
```
