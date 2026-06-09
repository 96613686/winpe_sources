# CCbsExecutionObject::PopulateExecutionUpdates(ulong,CCbsPackage *,int,ulong,PerSessionPackageState *,CCbsExecutionPackage *,int,int,CbsState,CbsState,CCbsPointerArray<PackageToAdd *> *)

- ea: `0x1801680f4`
- end: `0x180169d0a`
- name: `?PopulateExecutionUpdates@CCbsExecutionObject@@AEAAJKPEAVCCbsPackage@@HKPEAUPerSessionPackageState@@PEAVCCbsExecutionPackage@@HHW4CbsState@@3PEAV?$CCbsPointerArray@PEAUPackageToAdd@@@@@Z`
- size: `7190`
- prototype: ``
- caller_count: `1`
- callee_count: `60`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18016be2c`

## callees

- `0x18000c70c`
- `0x18000d910`
- `0x180010b60`
- `0x180010cc0`
- `0x1800115a8`
- `0x180012ae4`
- `0x180012fe4`
- `0x1800138b8`
- `0x180015420`
- `0x18001e1a0`
- `0x18001f90c`
- `0x18002293c`
- `0x18002341c`
- `0x180023444`
- `0x180025008`
- `0x180042130`
- `0x1800466f8`
- `0x18004c2f4`
- `0x18004d564`
- `0x1800649d4`
- `0x180065f04`
- `0x180092590`
- `0x180093a70`
- `0x180093c4c`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800a06ec`
- `0x1800a0898`
- `0x1800a5fe0`
- `0x1800ad504`
- `0x1800bd450`
- `0x1800bd544`
- `0x1800c0054`
- `0x1800eb4c0`
- `0x1800eb920`
- `0x180143f5c`
- `0x18015fa6c`
- `0x18015fc38`
- `0x18015ff68`
- `0x1801608c0`
- `0x180160afc`
- `0x1801633f4`
- `0x180166580`
- `0x1801666b8`
- `0x180166930`
- `0x180166ae0`
- `0x180167078`
- `0x1801677b4`

## string_xrefs

- `0x180168433`: `Appl: Force package: {}, update: {}, applicable state: {}, for MFL`
- `0x180169b02`: `Failed to get start state for update: {}`
- `0x18016849d`: `Plan: Sub-Execution, use current state as update start state`
- `0x180168628`: `Plan: Skip superseded on demand update, adjust its target state to Resolved: {}`
- `0x180169c81`: `Failed to get per session update state`
- `0x1801691f1`: `Failed to get applicable state for update.`
- `0x180169bc6`: `Failed to get applicable state for update.`
- `0x180168254`: `Plan: Force package:{}, update: {} into absent state since package state is absent`
- `0x180169250`: `Failed to set selection on update: {} for Package: {}`
- `0x18016833c`: `Appl: Force package: {}, update: {}, selected: {}, RemovePayload: {} by request of Client`
- `0x180168ded`: `Plan: Will attempt to restore Package: {}, Update: {}`
- `0x180168ca4`: `Plan: Skip update: {} that points to package {} since it is semi-isolated and target state is not absent.`
- `0x1801689b4`: `Exec: Planning an absent detached OC capability during a transmog operation, skipping capability planning for: {}`
- `0x18016895a`: `Exec: NetFx3 OC and package already added to the execution, skip`
- `0x1801686df`: `Plan: Merged into existing execution update for Package: {}, Update: {}, targeted: {}, merged: {}`
- `0x180169340`: `Failed to merge execution for package:{}, update:{}`
- `0x1801699ba`: `Failed to add execution component to execution package.`
- `0x180169098`: `Failed to add execution component to parent execution update.`
- `0x180169895`: `Failed to add execution component to parent execution update.`
- `0x1801688e0`: `Plan: Skip update: {} that points to package {} since it is isolated`
- `0x1801694be`: `Failed to resolve detached OC capability on installation of detached OC: {}`
- `0x180168aa0`: `Exec: Planning an absent detached update and it is not applicable, skipping capability planning for: {}`
- `0x18016944b`: `Failed to resolve detached OC capability on uninstallation or evaluation of installed detached OC: {}`

## pseudocode

```c
__int64 __fastcall CCbsExecutionObject::PopulateExecutionUpdates(
        __int64 a1,
        __int64 a2,
        CCbsPackage *a3,
        int a4,
        int a5,
        struct PerSessionPackageState *a6,
        CCbsExecutionPackage *a7,
        int a8,
        int a9,
        int a10,
        unsigned int a11,
        __int64 a12)
{
  __int64 v12; // r14
  struct PerSessionPackageState *v13; // rdx
  CCbsPackage *v14; // r13
  __int64 v15; // rax
  struct CCbsUpdate **v16; // rcx
  const wchar_t *v17; // rsi
  struct CCbsUpdate *v18; // r15
  CCbsSession *v19; // rcx
  int SessionUpdateState; // ebx
  int v21; // edx
  int v22; // edi
  const wchar_t *v23; // rax
  bool v24; // zf
  PackageToAdd *v25; // rax
  struct PerSessionUpdateState *v26; // r12
  const wchar_t *v27; // rdx
  const struct SessionAction *DeferredOCAction; // rax
  __int64 v29; // rdx
  unsigned int Selection; // ebx
  __int64 v31; // r8
  int v32; // edx
  int v33; // r8d
  unsigned int v34; // r10d
  PackageToAdd *v35; // rcx
  CapabilityToChange *v36; // rcx
  __int64 v37; // rax
  int v38; // edx
  const wchar_t *v39; // rax
  const wchar_t *v40; // rax
  int v41; // r12d
  __int64 v42; // rcx
  unsigned int v43; // ebx
  __int64 v44; // rax
  int v45; // edx
  int v46; // r8d
  int v47; // r9d
  const wchar_t *v48; // rax
  const wchar_t *v49; // rax
  __int64 v50; // rcx
  const wchar_t *v51; // rax
  unsigned int v52; // edi
  CCbsExecutionUpdate *v53; // rbx
  __int64 v54; // rax
  int v55; // edx
  int v56; // r8d
  const wchar_t *v57; // rax
  const wchar_t *v58; // rax
  CCbsExecutionUpdate *v59; // rax
  int CurrentState; // edi
  int v61; // edi
  unsigned int *v62; // rcx
  __int64 v63; // rax
  __int64 v64; // r14
  int v65; // ecx
  const wchar_t *v66; // rax
  PackageToAdd *v67; // r13
  struct CCbsIdentity **v68; // rax
  unsigned int v69; // r14d
  wchar_t *v70; // rax
  int v71; // edx
  int v72; // r10d
  const wchar_t *v73; // rax
  const char *v74; // r9
  const wchar_t **v75; // rax
  int v76; // ecx
  int v77; // ecx
  int v78; // ecx
  const wchar_t *v79; // rcx
  wchar_t *FastCbsIdentityString; // rax
  int v81; // edx
  int v82; // ecx
  wchar_t **v83; // rax
  const char *v84; // r9
  CCbsUpdate *v85; // rcx
  wchar_t *v86; // rax
  char v87; // dl
  CCbsUpdate *v88; // rcx
  int v89; // r8d
  int v90; // r9d
  wchar_t *v91; // rax
  CCbsUpdate *v92; // rcx
  int v93; // r9d
  int v94; // r9d
  wchar_t *v95; // rax
  CCbsCapabilityManager *v96; // rdi
  struct CCbsCapability **InitPointer; // rax
  __int64 v98; // r8
  _QWORD *v99; // r14
  __int64 v100; // r9
  bool v101; // cc
  const wchar_t *v102; // r8
  const wchar_t *v103; // rdx
  __int64 v104; // r9
  struct PerSessionUpdateState *v105; // rcx
  CCbsCapability ***v106; // rdi
  CCbsCapability ***v107; // r12
  CCbsCapability **v108; // r14
  wchar_t *v109; // rax
  const wchar_t *v110; // rax
  int v111; // edx
  CCbsPackage *v112; // r8
  __int64 v113; // r9
  struct LogAdapter::Logger *v114; // r10
  __int64 v115; // r13
  __int64 v116; // rdi
  __int64 v117; // r14
  CapabilityToChange *v118; // rax
  const wchar_t *v119; // rax
  CapabilityToChange *v120; // rdi
  const wchar_t *v121; // rdx
  int v122; // eax
  int RoomAt; // r14d
  __int64 v124; // r12
  int v125; // eax
  PackageToAdd *v126; // rdi
  int v127; // eax
  int v128; // eax
  int v129; // edx
  __int64 v130; // rdx
  unsigned int v131; // edx
  const wchar_t *v132; // rdx
  __int64 v133; // r13
  __int64 v134; // r12
  CCbsExecutionComponent *v135; // rdi
  struct ICbsExecutionItem *v136; // rdx
  int v137; // eax
  int v138; // edx
  __int64 v139; // rdx
  struct ICbsExecutionItem *v140; // rdx
  char *v141; // rcx
  char *v142; // rcx
  int v143; // edx
  __int64 v144; // rdx
  const wchar_t *v145; // rax
  int v146; // edx
  int v147; // edx
  const wchar_t *v148; // rax
  int v149; // edx
  int v150; // edx
  __int64 v151; // rdx
  int v152; // edx
  int v153; // edx
  int v154; // edx
  int v155; // edx
  int v156; // edx
  __int64 v157; // rdx
  unsigned int v158; // edx
  __int64 v159; // rdx
  void (*v160)(void); // rax
  int v161; // edx
  void (*v162)(void); // rax
  int v163; // edx
  char *v164; // rcx
  int v165; // edx
  char *v166; // rcx
  char *v167; // rcx
  char *v169; // rcx
  int v170; // edx
  int v171; // edx
  int v172; // edx
  int v173; // edx
  int v174; // edx
  int v175; // edx
  int v176; // edx
  int v177; // [rsp+20h] [rbp-E0h]
  wchar_t **v178; // [rsp+28h] [rbp-D8h]
  bool v179; // [rsp+70h] [rbp-90h] BYREF
  int v180[2]; // [rsp+78h] [rbp-88h] BYREF
  int v181; // [rsp+80h] [rbp-80h] BYREF
  int v182; // [rsp+84h] [rbp-7Ch]
  int v183[2]; // [rsp+88h] [rbp-78h] BYREF
  struct CCbsIdentity *v184; // [rsp+90h] [rbp-70h] BYREF
  int v185; // [rsp+98h] [rbp-68h] BYREF
  struct CCbsCapability *v186; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v187; // [rsp+A8h] [rbp-58h] BYREF
  PackageToAdd *v188; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v189; // [rsp+B8h] [rbp-48h]
  CCbsPackage *v190; // [rsp+C0h] [rbp-40h]
  struct PerSessionUpdateState *v191; // [rsp+C8h] [rbp-38h] BYREF
  CapabilityToChange *v192; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int *v193; // [rsp+D8h] [rbp-28h] BYREF
  int v194[2]; // [rsp+E0h] [rbp-20h] BYREF
  int v195[2]; // [rsp+E8h] [rbp-18h] BYREF
  int v196[2]; // [rsp+F0h] [rbp-10h] BYREF
  struct CCbsUpdate **v197; // [rsp+F8h] [rbp-8h]
  CCbsExecutionPackage *v198; // [rsp+100h] [rbp+0h]
  const wchar_t *v199; // [rsp+108h] [rbp+8h] BYREF
  __int64 v200; // [rsp+110h] [rbp+10h] BYREF
  const wchar_t *v201; // [rsp+118h] [rbp+18h] BYREF
  const wchar_t *v202; // [rsp+120h] [rbp+20h] BYREF
  __int64 v203; // [rsp+128h] [rbp+28h] BYREF
  __int64 v204; // [rsp+130h] [rbp+30h] BYREF
  __int64 v205; // [rsp+138h] [rbp+38h] BYREF
  __int64 v206; // [rsp+140h] [rbp+40h] BYREF
  __int64 v207; // [rsp+148h] [rbp+48h] BYREF
  __int64 v208; // [rsp+150h] [rbp+50h] BYREF
  const wchar_t *v209; // [rsp+158h] [rbp+58h] BYREF
  int v210[2]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v211; // [rsp+168h] [rbp+68h] BYREF
  __int64 v212; // [rsp+170h] [rbp+70h] BYREF
  const wchar_t *v213; // [rsp+178h] [rbp+78h] BYREF
  const wchar_t *v214; // [rsp+180h] [rbp+80h] BYREF
  const wchar_t *v215; // [rsp+188h] [rbp+88h] BYREF
  wchar_t *v216; // [rsp+190h] [rbp+90h] BYREF
  wchar_t *v217; // [rsp+198h] [rbp+98h] BYREF
  wchar_t *v218; // [rsp+1A0h] [rbp+A0h] BYREF
  wchar_t *v219; // [rsp+1A8h] [rbp+A8h] BYREF
  wchar_t *v220; // [rsp+1B0h] [rbp+B0h] BYREF
  const wchar_t *v221; // [rsp+1B8h] [rbp+B8h] BYREF
  wchar_t *v222; // [rsp+1C0h] [rbp+C0h] BYREF
  wchar_t *v223; // [rsp+1C8h] [rbp+C8h] BYREF
  unsigned int v224; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned int UpdateOptions; // [rsp+1D4h] [rbp+D4h] BYREF
  CCbsExecutionComponent *v226; // [rsp+1D8h] [rbp+D8h] BYREF
  unsigned int v227; // [rsp+1E0h] [rbp+E0h] BYREF
  int v228; // [rsp+1E4h] [rbp+E4h] BYREF
  int v229; // [rsp+1E8h] [rbp+E8h] BYREF
  int v230; // [rsp+1ECh] [rbp+ECh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  v12 = a1;
  v13 = a6;
  v14 = a3;
  v198 = a7;
  v224 = a11;
  *(_QWORD *)v194 = a12;
  v15 = *((_QWORD *)a3 + 92);
  v189 = a1;
  v16 = (struct CCbsUpdate **)*((_QWORD *)a3 + 94);
  v229 = a4;
  v190 = a3;
  *(_QWORD *)v180 = a6;
  v197 = v16;
  *(_QWORD *)v183 = &v16[v15];
  if ( v16 == *(struct CCbsUpdate ***)v183 )
    return 0;
  v17 = &qword_1802EB518;
  while ( 1 )
  {
    v18 = *v16;
    v19 = *(CCbsSession **)(v12 + 64);
    v185 = 4096;
    v181 = 4096;
    v227 = -1;
    LODWORD(v226) = 0;
    v179 = 0;
    v191 = 0;
    SessionUpdateState = CCbsSession::GetSessionUpdateState(v19, v18, v13, 1, &v191);
    if ( SessionUpdateState < 0 )
    {
      v230 = SessionUpdateState;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get per session update state");
        *(_QWORD *)v196 = &v230;
        LOBYTE(v176) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v176,
          3,
          (unsigned int)": {}",
          (__int64)v196);
      }
      v144 = 171;
      goto LABEL_336;
    }
    SessionUpdateState = CCbsUpdate::GetCurrentState(v18, *(struct CCbsSession **)(v12 + 64), (enum CbsState *)&v185);
    if ( SessionUpdateState < 0 )
    {
      v230 = SessionUpdateState;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get current state.");
        *(_QWORD *)v196 = &v230;
        LOBYTE(v175) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v175,
          3,
          (unsigned int)": {}",
          (__int64)v196);
      }
      v144 = 174;
      goto LABEL_336;
    }
    if ( !a10 )
    {
      v22 = 0;
      v23 = &qword_1802EB518;
      if ( *((_QWORD *)v18 + 4) )
        v23 = (const wchar_t *)*((_QWORD *)v18 + 4);
      v24 = *((_QWORD *)v14 + 15) == 0;
      v187 = (__int64)v23;
      v25 = (PackageToAdd *)&qword_1802EB518;
      if ( !v24 )
        v25 = (PackageToAdd *)*((_QWORD *)v14 + 15);
      v188 = v25;
      if ( LogAdapter::g_Logger )
      {
        LOBYTE(v21) = 1;
        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
          (_DWORD)LogAdapter::g_Logger,
          v21,
          1,
          (unsigned int)"Plan: Force package:{}, update: {} into absent state since package state is absent",
          (__int64)&v188,
          (__int64)&v187);
      }
      goto LABEL_37;
    }
    v26 = v191;
    SessionUpdateState = CCbsUpdate::GetApplicableSelectableState(
                           v18,
                           *(struct CCbsSession **)(v12 + 64),
                           v191,
                           (enum CbsState *)&v181,
                           &v179);
    if ( SessionUpdateState < 0 )
    {
      v224 = SessionUpdateState;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get applicable state for update.");
        *(_QWORD *)v180 = &v224;
        LOBYTE(v174) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v174,
          3,
          (unsigned int)": {}",
          (__int64)v180);
      }
      v144 = 192;
      goto LABEL_336;
    }
    if ( (unsigned int)CCbsUpdate::IsSelectable(v18) )
    {
      v22 = v181;
      if ( v181 <= 32 )
        goto LABEL_28;
      v27 = &qword_1802EB518;
      if ( *((_QWORD *)v18 + 4) )
        v27 = (const wchar_t *)*((_QWORD *)v18 + 4);
      DeferredOCAction = CCbsSession::GetDeferredOCAction(*(CCbsSession **)(v12 + 64), v27);
      if ( !DeferredOCAction || *(_DWORD *)DeferredOCAction != 3 )
        goto LABEL_28;
      Selection = SessionAction::GetSelection(DeferredOCAction, v29, DeferredOCAction);
      UpdateOptions = SessionAction::GetUpdateOptions(v31);
      v187 = CbsSelectionToString(Selection);
      v35 = (PackageToAdd *)&qword_1802EB518;
      if ( *((_QWORD *)v18 + 4) )
        v35 = (PackageToAdd *)*((_QWORD *)v18 + 4);
      v24 = *((_QWORD *)v14 + 15) == 0;
      v188 = v35;
      v36 = (CapabilityToChange *)&qword_1802EB518;
      if ( !v24 )
        v36 = (CapabilityToChange *)*((_QWORD *)v14 + 15);
      v192 = v36;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t const *,wchar_t const *,unsigned long>(
          (_DWORD)LogAdapter::g_Logger,
          v32,
          v33,
          (unsigned int)"Appl: Force package: {}, update: {}, selected: {}, RemovePayload: {} by request of Client",
          (__int64)&v192,
          (__int64)&v188,
          (__int64)&v187,
          (__int64)&UpdateOptions);
        v34 = UpdateOptions;
      }
      v177 = 0;
      SessionUpdateState = CCbsUpdate::SetInstallState(v18, v34, *(_QWORD *)(v12 + 64), Selection);
      if ( SessionUpdateState < 0 )
      {
        v224 = SessionUpdateState;
        if ( LogAdapter::g_Logger )
        {
          v145 = &qword_1802EB518;
          if ( *((_QWORD *)v14 + 15) )
            v145 = (const wchar_t *)*((_QWORD *)v14 + 15);
          v24 = *((_QWORD *)v18 + 4) == 0;
          *(_QWORD *)v180 = v145;
          if ( !v24 )
            v17 = (const wchar_t *)*((_QWORD *)v18 + 4);
          *(_QWORD *)v183 = v17;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to set selection on update: {} for Package: {}",
            (__int64)v183,
            (__int64)v180);
          v193 = &v224;
          LOBYTE(v146) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v146,
            3,
            (unsigned int)": {}",
            (__int64)&v193);
        }
        v144 = 213;
        goto LABEL_336;
      }
      SessionUpdateState = CCbsUpdate::GetApplicableSelectableState(
                             v18,
                             *(struct CCbsSession **)(v12 + 64),
                             v26,
                             (enum CbsState *)&v181,
                             &v179);
      if ( SessionUpdateState < 0 )
      {
        v224 = SessionUpdateState;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get applicable state for update.");
          *(_QWORD *)v180 = &v224;
          LOBYTE(v143) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v143,
            3,
            (unsigned int)": {}",
            (__int64)v180);
        }
        v144 = 222;
        goto LABEL_336;
      }
    }
    v22 = v181;
LABEL_28:
    if ( v22 != 112 && (a5 & 0x20000) != 0 && *(_BYTE *)(*(_QWORD *)(v12 + 64) + 1744LL) )
    {
      v22 = 112;
      v37 = CbsStateToString(112);
      v24 = *((_QWORD *)v18 + 4) == 0;
      v200 = v37;
      v39 = &qword_1802EB518;
      if ( !v24 )
        v39 = (const wchar_t *)*((_QWORD *)v18 + 4);
      v24 = *((_QWORD *)v14 + 15) == 0;
      v201 = v39;
      v40 = &qword_1802EB518;
      if ( !v24 )
        v40 = (const wchar_t *)*((_QWORD *)v14 + 15);
      v202 = v40;
      if ( LogAdapter::g_Logger )
      {
        LOBYTE(v38) = 1;
        LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(
          (_DWORD)LogAdapter::g_Logger,
          v38,
          1,
          (unsigned int)"Appl: Force package: {}, update: {}, applicable state: {}, for MFL",
          (__int64)&v202,
          (__int64)&v201,
          (__int64)&v200);
      }
    }
LABEL_37:
    SessionUpdateState = CCbsUpdate::GetUserSelectionWithAdjustment(
                           v18,
                           *(struct CCbsSession **)(v12 + 64),
                           1,
                           (enum UpdateSelection *)&v227,
                           (int *)&v226);
    if ( SessionUpdateState < 0 )
    {
      v224 = SessionUpdateState;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get user selection state");
        *(_QWORD *)v180 = &v224;
        LOBYTE(v173) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v173,
          3,
          (unsigned int)": {}",
          (__int64)v180);
      }
      v144 = 245;
      goto LABEL_336;
    }
    v41 = v22;
    UpdateOptions = 4096;
    if ( a10 < v22 )
      v41 = a10;
    v24 = *(_BYTE *)(v12 + 888) == 0;
    v182 = v41;
    if ( v24 )
    {
      SessionUpdateState = CCbsUpdate::GetStartState(v18, *(_QWORD *)(v12 + 64), (unsigned int)v41, &UpdateOptions);
      if ( SessionUpdateState < 0 )
      {
        v224 = SessionUpdateState;
        if ( LogAdapter::g_Logger )
        {
          if ( *((_QWORD *)v18 + 4) )
            v17 = (const wchar_t *)*((_QWORD *)v18 + 4);
          *(_QWORD *)v180 = v17;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to get start state for update: {}",
            (__int64)v180);
          *(_QWORD *)v183 = &v224;
          LOBYTE(v172) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v172,
            3,
            (unsigned int)": {}",
            (__int64)v183);
        }
        v144 = 307;
        goto LABEL_336;
      }
      v42 = UpdateOptions;
    }
    else
    {
      LogAdapter::TraceAtLevel<>(1, "Plan: Sub-Execution, use current state as update start state");
      v42 = (unsigned int)v185;
    }
    v181 = EquivalentStateIfInvalid(v42, (unsigned int)v41);
    v43 = v181;
    if ( v41 == 4096 )
    {
      CurrentState = -2146498560;
      v224 = -2146498560;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "target state cannot be default");
        *(_QWORD *)v180 = &v224;
        LOBYTE(v171) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v171,
          3,
          (unsigned int)": {}",
          (__int64)v180);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x139,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
        (const char *)0x800F0800LL,
        v177);
      return (unsigned int)CurrentState;
    }
    v187 = CbsSelectionToString(v227);
    v203 = CbsStateToString(v224);
    v204 = CbsStateToString((unsigned int)v41);
    v205 = CbsStateToString((unsigned int)v22);
    v206 = CbsStateToString(v43);
    v207 = CbsStateToString(4096);
    v44 = CbsStateToString((unsigned int)v185);
    v24 = *((_QWORD *)v18 + 4) == 0;
    v208 = v44;
    v48 = &qword_1802EB518;
    if ( !v24 )
      v48 = (const wchar_t *)*((_QWORD *)v18 + 4);
    v24 = *((_QWORD *)v14 + 15) == 0;
    v209 = v48;
    v49 = &qword_1802EB518;
    if ( !v24 )
      v49 = (const wchar_t *)*((_QWORD *)v14 + 15);
    *(_QWORD *)v210 = v49;
    if ( LogAdapter::g_Logger )
      LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        v45,
        v46,
        v47,
        (__int64)v210,
        (__int64)&v209,
        (__int64)&v208,
        (__int64)&v207,
        (__int64)&v206,
        (__int64)&v205,
        (__int64)&v204,
        (__int64)&v203,
        (__int64)&v187);
    v50 = *(_QWORD *)(v12 + 24);
    if ( v50 )
    {
      SessionUpdateState = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, bool))(*(_QWORD *)v50 + 40LL))(
                             v50,
                             32,
                             (unsigned int)(a9 != 0) - 2,
                             a9 == 0);
      if ( SessionUpdateState < 0 )
      {
        v224 = SessionUpdateState;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Plan: User cancelled the operation.");
          *(_QWORD *)v180 = &v224;
          LOBYTE(v147) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v147,
            3,
            (unsigned int)": {}",
            (__int64)v180);
        }
        v144 = 336;
        goto LABEL_336;
      }
    }
    if ( v185 == 32 && v41 == 80 )
    {
      v51 = &qword_1802EB518;
      if ( *((_QWORD *)v18 + 4) )
        v51 = (const wchar_t *)*((_QWORD *)v18 + 4);
      v187 = (__int64)v51;
      LogAdapter::TraceAtLevel<wchar_t const *>(
        1,
        "Plan: Skip superseded on demand update, adjust its target state to Resolved: {}",
        &v187);
      v41 = 32;
      v182 = 32;
    }
    if ( a8 )
    {
      UpdateOptions = 4096;
      SessionUpdateState = CCbsExecutionPackage::MergeExecutionUpdate(v198, v18, (unsigned int)v41, &UpdateOptions);
      if ( SessionUpdateState < 0 )
      {
        v224 = SessionUpdateState;
        if ( LogAdapter::g_Logger )
        {
          v148 = &qword_1802EB518;
          if ( *((_QWORD *)v18 + 4) )
            v148 = (const wchar_t *)*((_QWORD *)v18 + 4);
          v24 = *((_QWORD *)v14 + 15) == 0;
          *(_QWORD *)v180 = v148;
          if ( !v24 )
            v17 = (const wchar_t *)*((_QWORD *)v14 + 15);
          *(_QWORD *)v183 = v17;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to merge execution for package:{}, update:{}",
            (__int64)v183,
            (__int64)v180);
          v193 = &v224;
          LOBYTE(v149) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v149,
            3,
            (unsigned int)": {}",
            (__int64)&v193);
        }
        v144 = 360;
LABEL_336:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v144,
          (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
          (const char *)(unsigned int)SessionUpdateState,
          v177);
        return (unsigned int)SessionUpdateState;
      }
      v52 = UpdateOptions;
      v53 = 0;
      if ( v41 != UpdateOptions )
      {
        v211 = CbsStateToString(UpdateOptions);
        v54 = CbsStateToString((unsigned int)v41);
        v24 = *((_QWORD *)v18 + 4) == 0;
        v212 = v54;
        v57 = &qword_1802EB518;
        if ( !v24 )
          v57 = (const wchar_t *)*((_QWORD *)v18 + 4);
        v24 = *((_QWORD *)v14 + 15) == 0;
        v213 = v57;
        v58 = &qword_1802EB518;
        if ( !v24 )
          v58 = (const wchar_t *)*((_QWORD *)v14 + 15);
        v214 = v58;
        if ( LogAdapter::g_Logger )
          LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t const *,wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            v55,
            v56,
            (unsigned int)"Plan: Merged into existing execution update for Package: {}, Update: {}, targeted: {}, merged: {}",
            (__int64)&v214,
            (__int64)&v213,
            (__int64)&v212,
            (__int64)&v211);
      }
      v41 = v52;
      v182 = v52;
    }
    else
    {
      v59 = (CCbsExecutionUpdate *)operator new(0xA0u);
      if ( !v59 || (v53 = CCbsExecutionUpdate::CCbsExecutionUpdate(v59)) == 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x178,
          (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
          (const char *)0x8007000ELL,
          v177);
        return 2147942414LL;
      }
      v177 = (int)v18;
      CCbsExecutionUpdate::Initialize(v53, *(_QWORD *)(v12 + 64), v198, v14);
      CurrentState = CCbsExecutionPackage::AddExecutionUpdate(v198, v53);
      if ( CurrentState < 0 )
      {
        UpdateOptions = CurrentState;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to add execution component to execution package.");
          *(_QWORD *)v195 = &UpdateOptions;
          LOBYTE(v170) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v170,
            3,
            (unsigned int)": {}",
            (__int64)v195);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x184,
          (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
          (const char *)(unsigned int)CurrentState,
          v177);
        goto LABEL_311;
      }
    }
    v61 = v181;
    if ( v229 && v41 > 64 )
    {
      if ( v181 <= 64 )
        v41 = 64;
      v182 = v41;
    }
    *((_DWORD *)v191 + 3) = v41;
    v62 = (unsigned int *)*((_QWORD *)v18 + 28);
    v63 = *((_QWORD *)v18 + 26);
    v187 = (__int64)v62;
    v193 = &v62[2 * v63];
    if ( v62 != v193 )
      break;
LABEL_222:
    if ( v53 )
    {
      v142 = (char *)v53 + *(int *)(*((_QWORD *)v53 + 1) + 4LL) + 8;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v142 + 16LL))(v142);
    }
    v16 = v197 + 1;
    v197 = v16;
    if ( v16 == *(struct CCbsUpdate ***)v183 )
      return 0;
    v13 = *(struct PerSessionPackageState **)v180;
  }
  while ( 1 )
  {
    v64 = *(_QWORD *)v62;
    v65 = *(_DWORD *)(*(_QWORD *)v62 + 24LL);
    if ( v65 == 5 && (a5 & 0x4000) != 0 )
      break;
    v76 = v65 - 1;
    if ( !v76 )
    {
      if ( a8 )
        goto LABEL_220;
      v226 = 0;
      if ( Windows::AutoComPtr<CCbsExecutionComponent>::AllocateWithNew<CCbsExecutionComponent,>(&v226) )
      {
        v135 = v226;
        CCbsExecutionComponent::Initialize(
          v226,
          *(struct CCbsSession **)(v189 + 64),
          v14,
          v18,
          *(struct CCbsComponentDeployment **)(v64 + 40));
        if ( v135 )
          v140 = (CCbsExecutionComponent *)((char *)v135 + *(int *)(*((_QWORD *)v135 + 1) + 4LL) + 8);
        else
          v140 = 0;
        RoomAt = CCbsExecutionUpdate::AddExecutionItem(v53, v140);
        if ( RoomAt < 0 )
        {
          v227 = RoomAt;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              LogAdapter::g_Logger,
              0,
              3,
              "Failed to add execution component to parent execution update.");
            *(_QWORD *)v194 = &v227;
            LOBYTE(v165) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v165,
              3,
              (unsigned int)": {}",
              (__int64)v194);
          }
          v139 = 449;
          goto LABEL_298;
        }
LABEL_218:
        if ( v135 )
        {
          v141 = (char *)v135 + *(int *)(*((_QWORD *)v135 + 1) + 4LL) + 8;
          (*(void (__fastcall **)(char *))(*(_QWORD *)v141 + 16LL))(v141);
        }
        goto LABEL_220;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BB,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
        (const char *)0x8007000ELL,
        v177);
      if ( v226 )
      {
        v169 = (char *)v226 + *(int *)(*((_QWORD *)v226 + 1) + 4LL) + 8;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v169 + 16LL))(v169);
      }
      if ( v53 )
      {
        v160 = *(void (**)(void))(*(_QWORD *)((char *)v53 + *(int *)(*((_QWORD *)v53 + 1) + 4LL) + 8) + 16LL);
        goto LABEL_307;
      }
      return 2147942414LL;
    }
    v77 = v76 - 1;
    if ( !v77 )
    {
      if ( a8 )
        goto LABEL_220;
      v226 = 0;
      if ( Windows::AutoComPtr<CCbsExecutionComponent>::AllocateWithNew<CCbsExecutionComponent,>(&v226) )
      {
        v135 = v226;
        CCbsExecutionComponent::Initialize(
          v226,
          *(struct CCbsSession **)(v189 + 64),
          v14,
          v18,
          *(struct CCbsDriverDeployment **)(v64 + 40));
        if ( v135 )
          v136 = (CCbsExecutionComponent *)((char *)v135 + *(int *)(*((_QWORD *)v135 + 1) + 4LL) + 8);
        else
          v136 = 0;
        v137 = CCbsExecutionUpdate::AddExecutionItem(v53, v136);
        RoomAt = v137;
        if ( v137 < 0 )
        {
          v229 = v137;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              LogAdapter::g_Logger,
              0,
              3,
              "Failed to add execution component to parent execution update.");
            *(_QWORD *)v183 = &v229;
            LOBYTE(v138) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v138,
              3,
              (unsigned int)": {}",
              (__int64)v183);
          }
          v139 = 464;
LABEL_298:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v139,
            (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
            (const char *)(unsigned int)RoomAt,
            v177);
          if ( v135 )
          {
            v166 = (char *)v135 + *(int *)(*((_QWORD *)v135 + 1) + 4LL) + 8;
            (*(void (__fastcall **)(char *))(*(_QWORD *)v166 + 16LL))(v166);
          }
          goto LABEL_300;
        }
        goto LABEL_218;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CA,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
        (const char *)0x8007000ELL,
        v177);
      if ( v226 )
      {
        v164 = (char *)v226 + *(int *)(*((_QWORD *)v226 + 1) + 4LL) + 8;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v164 + 16LL))(v164);
      }
LABEL_278:
      if ( !v53 )
        return 2147942414LL;
      v160 = *(void (**)(void))(*(_QWORD *)((char *)v53 + *(int *)(*((_QWORD *)v53 + 1) + 4LL) + 8) + 16LL);
LABEL_307:
      v160();
      return 2147942414LL;
    }
    v78 = v77 - 1;
    if ( !v78 )
      goto LABEL_82;
    if ( v78 != 2 )
    {
      CurrentState = -2146498560;
      LODWORD(v226) = -2146498560;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Unknown Deployment Type.");
        *(_QWORD *)v180 = &v226;
        LOBYTE(v156) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v156,
          3,
          (unsigned int)": {}",
          (__int64)v180);
      }
      v157 = 825;
LABEL_290:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v157,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
        (const char *)(unsigned int)CurrentState,
        v177);
LABEL_291:
      if ( !v53 )
        return (unsigned int)CurrentState;
LABEL_311:
      v162 = *(void (**)(void))(*(_QWORD *)((char *)v53 + *(int *)(*((_QWORD *)v53 + 1) + 4LL) + 8) + 16LL);
LABEL_312:
      v162();
      return (unsigned int)CurrentState;
    }
    if ( v61 != v41 )
    {
      v79 = &qword_1802EB518;
      if ( *((_QWORD *)v18 + 4) )
        v79 = (const wchar_t *)*((_QWORD *)v18 + 4);
      if ( !(unsigned __int8)StringsAreEqual(v79, L"NetFx3", 1)
        || (*(_DWORD *)(*(_QWORD *)(v189 + 64) + 2208LL) & 0x2000) == 0 )
      {
        v186 = 0;
        if ( (v61 <= 0 || v185 <= 0) && (*(_DWORD *)(*(_QWORD *)(v189 + 64) + 2208LL) & 0x100000) != 0 )
        {
          FastCbsIdentityString = GetFastCbsIdentityString(*((const struct CCbsIdentity **)v14 + 14));
          v82 = (int)LogAdapter::g_Logger;
          v216 = FastCbsIdentityString;
          if ( LogAdapter::g_Logger )
          {
            v83 = &v216;
            v84 = "Exec: Planning an absent detached OC capability during a transmog operation, skipping capability planning for: {}";
            goto LABEL_122;
          }
LABEL_147:
          Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v186);
          goto LABEL_220;
        }
        if ( CCbsUpdate::AllowAbsentIfCapabilityAbsent(v18) && v179 && v61 < 64 )
        {
          v86 = GetFastCbsIdentityString(*((const struct CCbsIdentity **)v14 + 14));
          v82 = (int)LogAdapter::g_Logger;
          v217 = v86;
          if ( !LogAdapter::g_Logger )
            goto LABEL_147;
          v83 = &v217;
          v84 = "Exec: Planning an absent detached OC using default feature state, skipping capability planning for: {}";
LABEL_122:
          LOBYTE(v81) = 1;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(v82, v81, 1, (_DWORD)v84, (__int64)v83);
          goto LABEL_147;
        }
        if ( CCbsUpdate::AllowAbsentIfCapabilityAbsent(v85) && !v87 && v227 == v89 && v61 < v90 )
        {
          v91 = GetFastCbsIdentityString(*((const struct CCbsIdentity **)v14 + 14));
          v82 = (int)LogAdapter::g_Logger;
          v223 = v91;
          if ( !LogAdapter::g_Logger )
            goto LABEL_147;
          v83 = &v223;
          v84 = "Exec: Planning an absent detached OC and user selection is off, skipping capability planning for: {}";
          goto LABEL_122;
        }
        if ( CCbsUpdate::AllowAbsentIfCapabilityAbsent(v88)
          && v61 < v93
          && !(unsigned int)CCbsUpdate::IsSelectable(v92)
          && v41 == v94 )
        {
          v95 = GetFastCbsIdentityString(*((const struct CCbsIdentity **)v14 + 14));
          v82 = (int)LogAdapter::g_Logger;
          v218 = v95;
          if ( !LogAdapter::g_Logger )
            goto LABEL_147;
          v83 = &v218;
          v84 = "Exec: Planning an absent detached update and it is not applicable, skipping capability planning for: {}";
          goto LABEL_122;
        }
        v96 = vpCapabilityManager;
        InitPointer = (struct CCbsCapability **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v186);
        v98 = *(_QWORD *)(v64 + 40);
        v99 = (_QWORD *)v189;
        CurrentState = CCbsCapabilityManager::ResolveCapability(
                         v96,
                         *(struct CCbsSession **)(v189 + 64),
                         *(const struct CCbsIdentity **)(v98 + 24),
                         InitPointer);
        if ( CurrentState < 0 )
        {
          if ( v41 > 64 )
          {
            v224 = CurrentState;
            if ( LogAdapter::g_Logger )
            {
              if ( *((_QWORD *)v18 + 4) )
                v17 = (const wchar_t *)*((_QWORD *)v18 + 4);
              *(_QWORD *)v180 = v17;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to resolve detached OC capability on installation of detached OC: {}",
                (__int64)v180);
              *(_QWORD *)v183 = &v224;
              LOBYTE(v153) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v153,
                3,
                (unsigned int)": {}",
                (__int64)v183);
            }
            v151 = 729;
            goto LABEL_261;
          }
          if ( v181 > 64 )
          {
            v224 = CurrentState;
            if ( LogAdapter::g_Logger )
            {
              if ( *((_QWORD *)v18 + 4) )
                v17 = (const wchar_t *)*((_QWORD *)v18 + 4);
              *(_QWORD *)v180 = v17;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to resolve detached OC capability on uninstallation or evaluation of installed detached OC: {}",
                (__int64)v180);
              *(_QWORD *)v183 = &v224;
              LOBYTE(v152) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v152,
                3,
                (unsigned int)": {}",
                (__int64)v183);
            }
            v151 = 737;
            goto LABEL_261;
          }
          if ( !CCbsUpdate::AllowAbsentIfCapabilityAbsent(v18) )
          {
            v224 = CurrentState;
            if ( LogAdapter::g_Logger )
            {
              if ( *((_QWORD *)v18 + 4) != v100 )
                v17 = (const wchar_t *)*((_QWORD *)v18 + 4);
              *(_QWORD *)v180 = v17;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to resolve detached OC capability and absent default state is not allowed: {}",
                (__int64)v180);
              *(_QWORD *)v183 = &v224;
              LOBYTE(v150) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v150,
                3,
                (unsigned int)": {}",
                (__int64)v183);
            }
            v151 = 751;
LABEL_261:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v151,
              (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
              (const char *)(unsigned int)CurrentState,
              v177);
            Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v186);
            goto LABEL_291;
          }
          LogAdapter::TraceAtLevel<>(
            (unsigned int)(v100 + 1),
            "Staging an OC with a missing FoD, allowing absent as the capability is absent");
          goto LABEL_147;
        }
        v101 = v41 < 64;
        if ( v41 <= 64 )
        {
LABEL_136:
          if ( v101 )
          {
            v41 = 0;
            v182 = 0;
            v219 = GetFastCbsIdentityString(*((const struct CCbsIdentity **)v186 + 17));
            LogAdapter::TraceAtLevel<wchar_t const *>(
              1,
              "Forcing Capability: {} targetState from Resolved to Absent because it is a detached OC",
              &v219);
          }
        }
        else if ( v181 < v41 )
        {
          v102 = &qword_1802EB518;
          v103 = &qword_1802EB518;
          if ( *((_QWORD *)v18 + 4) )
            v102 = (const wchar_t *)*((_QWORD *)v18 + 4);
          v177 = 0;
          if ( *((_QWORD *)v14 + 15) )
            v103 = (const wchar_t *)*((_QWORD *)v14 + 15);
          CurrentState = CCbsSession::AddAction(v99[8], v103, v102, 11);
          if ( CurrentState < 0 )
          {
            v224 = CurrentState;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to add action.");
              *(_QWORD *)v180 = &v224;
              LOBYTE(v154) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v154,
                3,
                (unsigned int)": {}",
                (__int64)v180);
            }
            v151 = 763;
            goto LABEL_261;
          }
          v101 = v41 < 64;
          goto LABEL_136;
        }
        LOBYTE(v104) = CCbsUpdate::AllowAbsentIfCapabilityAbsent(v18);
        CurrentState = CCbsExecutionObject::PlanCapability(v99, v186, (unsigned int)v41, v104);
        if ( CurrentState < 0 )
        {
          v224 = CurrentState;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to plan capability");
            *(_QWORD *)v180 = &v224;
            LOBYTE(v155) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v155,
              3,
              (unsigned int)": {}",
              (__int64)v180);
          }
          v151 = 782;
          goto LABEL_261;
        }
        v105 = v191;
        if ( (*((_BYTE *)v191 + 24) & 1) != 0 )
        {
          v106 = (CCbsCapability ***)v99[71];
          v107 = &v106[v99[69]];
          if ( v106 == v107 )
          {
LABEL_145:
            v41 = v182;
            if ( v181 >= 64 )
            {
              *((_DWORD *)v105 + 3) = v181;
              *((_DWORD *)v105 + 6) &= ~1u;
            }
          }
          else
          {
            while ( 1 )
            {
              v108 = *v106;
              if ( (*(_BYTE *)*v106 & 2) != 0 && CCbsCapability::IsSameCapability(v108[1], v186) )
                break;
              if ( ++v106 == v107 )
              {
                v105 = v191;
                goto LABEL_145;
              }
            }
            v41 = v182;
            if ( *((int *)v108 + 8) >= 64 )
              *((_DWORD *)v191 + 6) &= ~1u;
          }
        }
        goto LABEL_147;
      }
      LogAdapter::TraceAtLevel<>(1, "Exec: NetFx3 OC and package already added to the execution, skip");
    }
LABEL_220:
    v61 = v181;
    v62 = (unsigned int *)(v187 + 8);
    v187 = (__int64)v62;
    if ( v62 == v193 )
    {
      v12 = v189;
      goto LABEL_222;
    }
  }
  v66 = &qword_1802EB518;
  if ( *((_QWORD *)v14 + 15) )
    v66 = (const wchar_t *)*((_QWORD *)v14 + 15);
  v215 = v66;
  LogAdapter::TraceAtLevel<wchar_t const *>(1, "Planning child capability of LCU as a package: {}", &v215);
LABEL_82:
  v67 = *(PackageToAdd **)(v64 + 40);
  v188 = v67;
  v228 = 4096;
  CurrentState = CCbsPackageDeployment::GetCurrentState(
                   v67,
                   *(struct CCbsSession **)(v189 + 64),
                   v18,
                   (enum CbsState *)&v228);
  if ( CurrentState < 0 )
  {
    LODWORD(v226) = CurrentState;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get current package state.");
      *(_QWORD *)v180 = &v226;
      LOBYTE(v163) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v163,
        3,
        (unsigned int)": {}",
        (__int64)v180);
    }
    v157 = 481;
    goto LABEL_290;
  }
  if ( v228 == 4096 )
  {
    CurrentState = -2146498560;
    v224 = -2146498560;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Package state cannot be CbsStateDefault");
      *(_QWORD *)v180 = &v224;
      LOBYTE(v161) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v161,
        3,
        (unsigned int)": {}",
        (__int64)v180);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E3,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
      (const char *)0x800F0800LL,
      v177);
    if ( v53 )
    {
      v162 = *(void (**)(void))(*(_QWORD *)((char *)v53 + *(int *)(*((_QWORD *)v53 + 1) + 4LL) + 8) + 16LL);
      goto LABEL_312;
    }
    return (unsigned int)CurrentState;
  }
  LODWORD(v226) = 0;
  v184 = 0;
  UpdateOptions = 0;
  v68 = (struct CCbsIdentity **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v184);
  CCbsPackageDeployment::GetData(v67, v68, (enum PACKAGE_INTEGRATION_TYPE::PACKAGE_INTEGRATION *)&UpdateOptions);
  v69 = UpdateOptions;
  if ( UpdateOptions != 1 )
  {
    if ( UpdateOptions != 4 || !*((_DWORD *)v190 + 224) || !v41 )
      goto LABEL_160;
    v109 = GetFastCbsIdentityString(v184);
    v24 = *((_QWORD *)v18 + 4) == 0;
    v72 = (int)LogAdapter::g_Logger;
    v222 = v109;
    v110 = &qword_1802EB518;
    if ( !v24 )
      v110 = (const wchar_t *)*((_QWORD *)v18 + 4);
    v199 = v110;
    if ( LogAdapter::g_Logger )
    {
      v178 = &v222;
      v74 = "Plan: Skip update: {} that points to package {} since it is semi-isolated and target state is not absent.";
      v75 = &v199;
LABEL_157:
      LOBYTE(v71) = 1;
      LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
        v72,
        v71,
        1,
        (_DWORD)v74,
        (__int64)v75,
        (__int64)v178);
    }
LABEL_158:
    if ( (a5 & 0x20) != 0 )
    {
      LODWORD(v226) = 1;
      goto LABEL_160;
    }
LABEL_202:
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v184);
    v14 = v190;
    goto LABEL_220;
  }
  if ( *((_DWORD *)v190 + 224) )
  {
    v70 = GetFastCbsIdentityString(v184);
    v24 = *((_QWORD *)v18 + 4) == 0;
    v72 = (int)LogAdapter::g_Logger;
    v220 = v70;
    v73 = &qword_1802EB518;
    if ( !v24 )
      v73 = (const wchar_t *)*((_QWORD *)v18 + 4);
    v221 = v73;
    if ( LogAdapter::g_Logger )
    {
      v178 = &v220;
      v74 = "Plan: Skip update: {} that points to package {} since it is isolated";
      v75 = &v221;
      goto LABEL_157;
    }
    goto LABEL_158;
  }
LABEL_160:
  if ( *(_BYTE *)(*(_QWORD *)(v189 + 64) + 1744LL)
    || !(unsigned int)CCbsUpdate::IsSelectable(v18)
    || (unsigned int)CCbsUpdate::GetDeploymentType() == 5
    || v179
    || CCbsPackage::IsFODorLPPackage(v190)
    || (v228 & 0xFFFFFFDF) != 0
    || v228 >= v41
    || v41 < 64 )
  {
LABEL_187:
    v188 = 0;
    Windows::AutoNewPtr<PackageToAdd>::Allocate<>(&v188);
    v126 = v188;
    if ( !v188 )
    {
      v159 = 591;
LABEL_277:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v159,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
        (const char *)0x8007000ELL,
        v177);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v184);
      goto LABEL_278;
    }
    Windows::AutoComPtr<IServicingCache>::operator=(v188, &v184);
    *((_DWORD *)v126 + 13) |= a5;
    if ( v229 )
      *((_DWORD *)v126 + 13) |= 0x40u;
    *((_DWORD *)v126 + 2) = v41;
    Windows::AutoComPtr<CCbsPackageDeployment>::operator=((char *)v126 + 16, v67);
    v127 = (int)v226;
    *((_DWORD *)v126 + 8) = v69;
    *((_DWORD *)v126 + 9) = v127;
    *((_DWORD *)v126 + 10) = a9;
    if ( v69 == 1 )
    {
      v128 = (*(__int64 (__fastcall **)(struct CCbsIdentity *, __int64))(*(_QWORD *)v184 + 72LL))(
               v184,
               (__int64)v126 + 24);
      RoomAt = v128;
      if ( v128 < 0 )
      {
        v224 = v128;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get identity string");
          *(_QWORD *)v180 = &v224;
          LOBYTE(v129) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v129,
            3,
            (unsigned int)": {}",
            (__int64)v180);
        }
        v130 = 619;
        goto LABEL_195;
      }
    }
    else
    {
      v132 = &qword_1802EB518;
      if ( *((_QWORD *)v190 + 15) )
        v132 = (const wchar_t *)*((_QWORD *)v190 + 15);
      RoomAt = SczAllocFromSz((char *)v126 + 24, v132);
      if ( RoomAt < 0 )
      {
        v130 = 627;
        goto LABEL_195;
      }
    }
    v133 = *(_QWORD *)v194;
    v134 = *(_QWORD *)(*(_QWORD *)v194 + 24LL);
    RoomAt = CCbsArrayBase<SessionAction *,CCbsPointerArray<SessionAction *>>::MakeRoomAt(*(_QWORD *)v194, v134);
    if ( RoomAt >= 0 )
    {
      *(_QWORD *)(*(_QWORD *)(v133 + 40) + 8 * v134) = v126;
      v41 = v182;
      goto LABEL_202;
    }
    v130 = 630;
LABEL_195:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v130,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
      (const char *)(unsigned int)RoomAt,
      v177);
    if ( v126 )
      PackageToAdd::`scalar deleting destructor'(v126, v131);
    goto LABEL_275;
  }
  v115 = v113 + 528;
  v116 = *(_QWORD *)(v113 + 568);
  v117 = v116 + 8LL * *(_QWORD *)(v113 + 552);
  if ( v116 != v117 )
  {
    do
    {
      if ( (**(_BYTE **)v116 & 4) != 0 )
      {
        if ( (unsigned int)CCbsIdentity::IsFastEqual(
                             *(CCbsIdentity **)(*(_QWORD *)v116 + 16LL),
                             *((struct CCbsIdentity **)v112 + 14)) )
          goto LABEL_186;
        v112 = v190;
      }
      v116 += 8;
    }
    while ( v116 != v117 );
    v114 = LogAdapter::g_Logger;
  }
  v118 = (CapabilityToChange *)&qword_1802EB518;
  if ( *((_QWORD *)v18 + 4) )
    v118 = (CapabilityToChange *)*((_QWORD *)v18 + 4);
  v24 = *((_QWORD *)v112 + 15) == 0;
  v192 = v118;
  v119 = &qword_1802EB518;
  if ( !v24 )
    v119 = (const wchar_t *)*((_QWORD *)v112 + 15);
  *(_QWORD *)v195 = v119;
  if ( v114 )
  {
    LOBYTE(v111) = 1;
    LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
      (_DWORD)v114,
      v111,
      1,
      (unsigned int)"Plan: Will attempt to restore Package: {}, Update: {}",
      (__int64)v195,
      (__int64)&v192);
  }
  v192 = 0;
  Windows::AutoNewPtr<CapabilityToChange>::Allocate<>(&v192);
  v120 = v192;
  if ( !v192 )
  {
    v159 = 571;
    goto LABEL_277;
  }
  *(_DWORD *)v192 |= 4u;
  Windows::AutoComPtr<CCbsPublicSession>::TakeReference((char *)v120 + 16, *((_QWORD *)v190 + 14));
  v121 = &qword_1802EB518;
  if ( *((_QWORD *)v18 + 4) )
    v121 = (const wchar_t *)*((_QWORD *)v18 + 4);
  v122 = SczAllocFromSz((char *)v120 + 24, v121);
  RoomAt = v122;
  if ( v122 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x241,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
      (const char *)(unsigned int)v122,
      v177);
    goto LABEL_274;
  }
  *((_DWORD *)v120 + 9) = v181;
  *((_DWORD *)v120 + 8) = v41;
  *((_BYTE *)v120 + 168) = 1;
  v124 = *(_QWORD *)(v115 + 24);
  v125 = CCbsArrayBase<SessionAction *,CCbsPointerArray<SessionAction *>>::MakeRoomAt(v115, v124);
  RoomAt = v125;
  if ( v125 >= 0 )
  {
    *(_QWORD *)(*(_QWORD *)(v115 + 40) + 8 * v124) = v120;
    v41 = v182;
LABEL_186:
    v67 = v188;
    v69 = UpdateOptions;
    goto LABEL_187;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x247,
    (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
    (const char *)(unsigned int)v125,
    v177);
  if ( v120 )
LABEL_274:
    CapabilityToChange::`scalar deleting destructor'(v120, v158);
LABEL_275:
  Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v184);
LABEL_300:
  if ( v53 )
  {
    v167 = (char *)v53 + *(int *)(*((_QWORD *)v53 + 1) + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v167 + 16LL))(v167);
  }
  return (unsigned int)RoomAt;
}

```

## disassembly

```asm
0x1801680f4  mov     [rsp-8+arg_8], rbx
0x1801680f9  push    rbp
0x1801680fa  push    rsi
0x1801680fb  push    rdi
0x1801680fc  push    r12
0x1801680fe  push    r13
0x180168100  push    r14
0x180168102  push    r15
0x180168104  lea     rbp, [rsp-100h]
0x18016810c  sub     rsp, 200h
0x180168113  mov     rax, cs:__security_cookie
0x18016811a  xor     rax, rsp
0x18016811d  mov     [rbp+130h+var_40], rax
0x180168124  mov     rax, [rbp+130h+arg_30]
0x18016812b  mov     r14, rcx
0x18016812e  mov     rdx, [rbp+130h+arg_28]
0x180168135  mov     r13, r8
0x180168138  mov     [rbp+130h+var_130], rax
0x18016813c  mov     eax, [rbp+130h+arg_50]
0x180168142  mov     [rbp+130h+var_60], eax
0x180168148  mov     rax, [rbp+130h+arg_58]
0x18016814f  mov     qword ptr [rbp+130h+var_150], rax
0x180168153  mov     rax, [r8+2E0h]
0x18016815a  mov     [rbp+130h+var_178], rcx
0x18016815e  mov     rcx, [r8+2F0h]
0x180168165  mov     [rbp+130h+var_48], r9d
0x18016816c  mov     [rbp+130h+var_170], r8
0x180168170  mov     qword ptr [rsp+230h+var_1B8], rdx
0x180168175  lea     rax, [rcx+rax*8]
0x180168179  mov     [rbp+130h+var_138], rcx
0x18016817d  mov     qword ptr [rbp+130h+var_1A8], rax
0x180168181  cmp     rcx, rax
0x180168184  jz      loc_180169CDD
0x18016818a  lea     rsi, qword_1802EB518
0x180168191  mov     r15, [rcx]
0x180168194  lea     rax, [rbp+130h+var_168]
0x180168198  mov     rcx, [r14+40h]; this
0x18016819c  mov     r8, rdx; struct PerSessionPackageState *
0x18016819f  mov     rdx, r15; struct CCbsUpdate *
0x1801681a2  mov     [rbp+130h+var_198], 1000h
0x1801681a9  mov     r9d, 1; int
0x1801681af  mov     [rbp+130h+var_1B0], 1000h
0x1801681b6  mov     [rbp+130h+var_50], 0FFFFFFFFh
0x1801681c0  mov     dword ptr [rbp+130h+var_58], 0
0x1801681ca  mov     [rsp+230h+var_1C0], 0
0x1801681cf  mov     [rbp+130h+var_168], 0
0x1801681d7  mov     [rsp+230h+var_210], rax; struct PerSessionUpdateState **
0x1801681dc  call    ?GetSessionUpdateState@CCbsSession@@QEAAJPEAVCCbsUpdate@@PEAUPerSessionPackageState@@HPEAPEAUPerSessionUpdateState@@@Z; CCbsSession::GetSessionUpdateState(CCbsUpdate *,PerSessionPackageState *,int,PerSessionUpdateState * *)
0x1801681e1  mov     ebx, eax
0x1801681e3  test    eax, eax
0x1801681e5  js      loc_180169C6A
0x1801681eb  mov     rdx, [r14+40h]; struct CCbsSession *
0x1801681ef  lea     r8, [rbp+130h+var_198]; enum CbsState *
0x1801681f3  mov     rcx, r15; this
0x1801681f6  call    ?GetCurrentState@CCbsUpdate@@QEAAJPEAVCCbsSession@@PEAW4CbsState@@@Z; CCbsUpdate::GetCurrentState(CCbsSession *,CbsState *)
0x1801681fb  mov     ebx, eax
0x1801681fd  test    eax, eax
0x1801681ff  js      loc_180169C0F
0x180168205  cmp     [rbp+130h+arg_48], 0
0x18016820c  jnz     short loc_18016826A
0x18016820e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180168215  xor     edi, edi
0x180168217  cmp     [r15+20h], rdi
0x18016821b  mov     rax, rsi
0x18016821e  cmovnz  rax, [r15+20h]
0x180168223  cmp     [r13+78h], rdi
0x180168227  mov     [rbp+130h+var_188], rax
0x18016822b  mov     rax, rsi
0x18016822e  cmovnz  rax, [r13+78h]
0x180168233  mov     [rbp+130h+var_180], rax
0x180168237  test    rcx, rcx
0x18016823a  jz      loc_180168448
0x180168240  lea     rax, [rbp+130h+var_188]
0x180168244  mov     [rsp+230h+var_208], rax
0x180168249  lea     r8d, [rdi+1]
0x18016824d  lea     rax, [rbp+130h+var_180]
0x180168251  mov     dl, r8b
0x180168254  lea     r9, aPlanForcePacka; "Plan: Force package:{}, update: {} into"...
0x18016825b  mov     [rsp+230h+var_210], rax
0x180168260  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x180168265  jmp     loc_180168448
0x18016826a  mov     r12, [rbp+130h+var_168]
0x18016826e  lea     rax, [rsp+230h+var_1C0]
0x180168273  mov     rdx, [r14+40h]; struct CCbsSession *
0x180168277  lea     r9, [rbp+130h+var_1B0]; enum CbsState *
0x18016827b  mov     r8, r12; struct PerSessionUpdateState *
0x18016827e  mov     [rsp+230h+var_210], rax; bool *
0x180168283  mov     rcx, r15; this
0x180168286  call    ?GetApplicableSelectableState@CCbsUpdate@@QEAAJPEAVCCbsSession@@PEAUPerSessionUpdateState@@PEAW4CbsState@@PEA_N@Z; CCbsUpdate::GetApplicableSelectableState(CCbsSession *,PerSessionUpdateState *,CbsState *,bool *)
0x18016828b  mov     ebx, eax
0x18016828d  test    eax, eax
0x18016828f  js      loc_180169BAF
0x180168295  mov     rcx, r15; this
0x180168298  call    ?IsSelectable@CCbsUpdate@@QEBAHXZ; CCbsUpdate::IsSelectable(void)
0x18016829d  test    eax, eax
0x18016829f  jz      loc_1801683B1
0x1801682a5  mov     edi, [rbp+130h+var_1B0]
0x1801682a8  cmp     edi, 20h ; ' '
0x1801682ab  jle     loc_1801683B4
0x1801682b1  cmp     qword ptr [r15+20h], 0
0x1801682b6  mov     rdx, rsi
0x1801682b9  mov     rcx, [r14+40h]; this
0x1801682bd  cmovnz  rdx, [r15+20h]; wchar_t *
0x1801682c2  call    ?GetDeferredOCAction@CCbsSession@@QEBAQEBUSessionAction@@QEB_W@Z; CCbsSession::GetDeferredOCAction(wchar_t const * const)
0x1801682c7  mov     r8, rax
0x1801682ca  test    rax, rax
0x1801682cd  jz      loc_1801683B4
0x1801682d3  cmp     dword ptr [rax], 3
0x1801682d6  jnz     loc_1801683B4
0x1801682dc  mov     rcx, rax
0x1801682df  call    ?GetSelection@SessionAction@@QEBA?AW4UpdateSelection@@XZ; SessionAction::GetSelection(void)
0x1801682e4  mov     rcx, r8
0x1801682e7  mov     ebx, eax
0x1801682e9  call    ?GetUpdateOptions@SessionAction@@QEBA?AW4_CbsUpdateOption@@XZ; SessionAction::GetUpdateOptions(void)
0x1801682ee  mov     ecx, ebx
0x1801682f0  mov     [rbp+130h+var_5C], eax
0x1801682f6  mov     r10d, eax
0x1801682f9  call    ?CbsSelectionToString@@YAPEB_WW4UpdateSelection@@@Z; CbsSelectionToString(UpdateSelection)
0x1801682fe  xor     edi, edi
0x180168300  mov     [rbp+130h+var_188], rax
0x180168304  cmp     [r15+20h], rdi
0x180168308  mov     rcx, rsi
0x18016830b  cmovnz  rcx, [r15+20h]
0x180168310  cmp     [r13+78h], rdi
0x180168314  mov     [rbp+130h+var_180], rcx
0x180168318  mov     rcx, rsi
0x18016831b  cmovnz  rcx, [r13+78h]
0x180168320  mov     [rbp+130h+var_160], rcx
0x180168324  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18016832b  test    rcx, rcx
0x18016832e  jz      short loc_18016836A
0x180168330  lea     rax, [rbp+130h+var_5C]
0x180168337  mov     [rsp+230h+var_1F8], rax
0x18016833c  lea     r9, aApplForcePacka; "Appl: Force package: {}, update: {}, se"...
0x180168343  lea     rax, [rbp+130h+var_188]
0x180168347  mov     [rsp+230h+var_200], rax
0x18016834c  lea     rax, [rbp+130h+var_180]
0x180168350  mov     [rsp+230h+var_208], rax
0x180168355  lea     rax, [rbp+130h+var_160]
0x180168359  mov     [rsp+230h+var_210], rax
0x18016835e  call    ??$LogNumObjects@PEB_WPEB_WPEB_WK@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W33AEBK@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t const *,wchar_t const *,ulong>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t const * const &,wchar_t const * const &,ulong const &)
0x180168363  mov     r10d, [rbp+130h+var_5C]
0x18016836a  mov     r8, [r14+40h]
0x18016836e  mov     r9d, ebx
0x180168371  mov     edx, r10d
0x180168374  mov     dword ptr [rsp+230h+var_210], edi
0x180168378  mov     rcx, r15
0x18016837b  call    ?SetInstallState@CCbsUpdate@@QEAAJKPEAVCCbsSession@@W4UpdateSelection@@H@Z; CCbsUpdate::SetInstallState(ulong,CCbsSession *,UpdateSelection,int)
0x180168380  mov     ebx, eax
0x180168382  test    eax, eax
0x180168384  js      loc_18016923A
0x18016838a  mov     rdx, [r14+40h]; struct CCbsSession *
0x18016838e  lea     rax, [rsp+230h+var_1C0]
0x180168393  lea     r9, [rbp+130h+var_1B0]; enum CbsState *
0x180168397  mov     [rsp+230h+var_210], rax; bool *
0x18016839c  mov     r8, r12; struct PerSessionUpdateState *
0x18016839f  mov     rcx, r15; this
0x1801683a2  call    ?GetApplicableSelectableState@CCbsUpdate@@QEAAJPEAVCCbsSession@@PEAUPerSessionUpdateState@@PEAW4CbsState@@PEA_N@Z; CCbsUpdate::GetApplicableSelectableState(CCbsSession *,PerSessionUpdateState *,CbsState *,bool *)
0x1801683a7  mov     ebx, eax
0x1801683a9  test    eax, eax
0x1801683ab  js      loc_1801691DA
0x1801683b1  mov     edi, [rbp+130h+var_1B0]
0x1801683b4  mov     r12d, 70h ; 'p'
0x1801683ba  cmp     edi, r12d
0x1801683bd  jz      loc_180168448
0x1801683c3  test    [rbp+130h+arg_20], 20000h
0x1801683cd  jz      short loc_180168448
0x1801683cf  mov     rax, [r14+40h]
0x1801683d3  cmp     byte ptr [rax+6D0h], 0
0x1801683da  jz      short loc_180168448
0x1801683dc  mov     ecx, r12d
0x1801683df  mov     edi, r12d
0x1801683e2  call    ?CbsStateToString@@YAPEB_WW4CbsState@@@Z; CbsStateToString(CbsState)
0x1801683e7  cmp     qword ptr [r15+20h], 0
0x1801683ec  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801683f3  mov     [rbp+130h+var_120], rax
0x1801683f7  mov     rax, rsi
0x1801683fa  cmovnz  rax, [r15+20h]
0x1801683ff  cmp     qword ptr [r13+78h], 0
0x180168404  mov     [rbp+130h+var_118], rax
0x180168408  mov     rax, rsi
0x18016840b  cmovnz  rax, [r13+78h]
0x180168410  mov     [rbp+130h+var_110], rax
0x180168414  test    rcx, rcx
0x180168417  jz      short loc_180168448
0x180168419  lea     rax, [rbp+130h+var_120]
0x18016841d  mov     [rsp+230h+var_200], rax
0x180168422  lea     r8d, [r12-6Fh]
0x180168427  lea     rax, [rbp+130h+var_118]
0x18016842b  mov     dl, r8b
0x18016842e  mov     [rsp+230h+var_208], rax
0x180168433  lea     r9, aApplForcePacka_0; "Appl: Force package: {}, update: {}, ap"...
0x18016843a  lea     rax, [rbp+130h+var_110]
0x18016843e  mov     [rsp+230h+var_210], rax
0x180168443  call    ??$LogNumObjects@PEB_WVAutoScz@@PEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBVAutoScz@@AEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,AutoScz const &,wchar_t * const &)
0x180168448  mov     rdx, [r14+40h]; struct CCbsSession *
0x18016844c  lea     rax, [rbp+130h+var_58]
0x180168453  lea     r9, [rbp+130h+var_50]; enum UpdateSelection *
0x18016845a  mov     [rsp+230h+var_210], rax; int *
0x18016845f  mov     r8b, 1; bool
0x180168462  mov     rcx, r15; this
0x180168465  call    ?GetUserSelectionWithAdjustment@CCbsUpdate@@QEAAJPEAVCCbsSession@@_NPEAW4UpdateSelection@@PEAH@Z; CCbsUpdate::GetUserSelectionWithAdjustment(CCbsSession *,bool,UpdateSelection *,int *)
0x18016846a  mov     ebx, eax
0x18016846c  test    eax, eax
0x18016846e  js      loc_180169B4E
0x180168474  cmp     [rbp+130h+arg_48], edi
0x18016847a  mov     r12d, edi
0x18016847d  mov     [rbp+130h+var_5C], 1000h
0x180168487  cmovl   r12d, [rbp+130h+arg_48]
0x18016848f  cmp     byte ptr [r14+378h], 0
0x180168497  mov     [rbp+130h+var_1AC], r12d
0x18016849b  jz      short loc_1801684B3
0x18016849d  lea     rdx, aPlanSubExecuti_0; "Plan: Sub-Execution, use current state "...
0x1801684a4  mov     ecx, 1
0x1801684a9  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1801684ae  mov     ecx, [rbp+130h+var_198]
0x1801684b1  jmp     short loc_1801684D9
0x1801684b3  mov     rdx, [r14+40h]
0x1801684b7  lea     r9, [rbp+130h+var_5C]
0x1801684be  mov     r8d, r12d
0x1801684c1  mov     rcx, r15
0x1801684c4  call    ?GetStartState@CCbsUpdate@@QEAAJPEAVCCbsSession@@W4CbsState@@PEAW43@@Z; CCbsUpdate::GetStartState(CCbsSession *,CbsState,CbsState *)
0x1801684c9  mov     ebx, eax
0x1801684cb  test    eax, eax
0x1801684cd  js      loc_180169AD7
0x1801684d3  mov     ecx, [rbp+130h+var_5C]
0x1801684d9  mov     edx, r12d
0x1801684dc  call    ?EquivalentStateIfInvalid@@YA?AW4CbsState@@W41@0@Z; EquivalentStateIfInvalid(CbsState,CbsState)
0x1801684e1  mov     [rbp+130h+var_1B0], eax
0x1801684e4  mov     ebx, eax
0x1801684e6  cmp     r12d, 1000h
0x1801684ed  jz      loc_180169A5A
0x1801684f3  mov     ecx, [rbp+130h+var_50]
0x1801684f9  call    ?CbsSelectionToString@@YAPEB_WW4UpdateSelection@@@Z; CbsSelectionToString(UpdateSelection)
0x1801684fe  mov     ecx, [rbp+130h+var_60]
0x180168504  mov     [rbp+130h+var_188], rax
0x180168508  call    ?CbsStateToString@@YAPEB_WW4CbsState@@@Z; CbsStateToString(CbsState)
0x18016850d  mov     ecx, r12d
0x180168510  mov     [rbp+130h+var_108], rax
0x180168514  call    ?CbsStateToString@@YAPEB_WW4CbsState@@@Z; CbsStateToString(CbsState)
0x180168519  mov     ecx, edi
0x18016851b  mov     [rbp+130h+var_100], rax
0x18016851f  call    ?CbsStateToString@@YAPEB_WW4CbsState@@@Z; CbsStateToString(CbsState)
0x180168524  mov     ecx, ebx
0x180168526  mov     [rbp+130h+var_F8], rax
0x18016852a  call    ?CbsStateToString@@YAPEB_WW4CbsState@@@Z; CbsStateToString(CbsState)
0x18016852f  mov     ecx, 1000h
0x180168534  mov     [rbp+130h+var_F0], rax
0x180168538  call    ?CbsStateToString@@YAPEB_WW4CbsState@@@Z; CbsStateToString(CbsState)
0x18016853d  mov     ecx, [rbp+130h+var_198]
0x180168540  mov     [rbp+130h+var_E8], rax
0x180168544  call    ?CbsStateToString@@YAPEB_WW4CbsState@@@Z; CbsStateToString(CbsState)
0x180168549  cmp     qword ptr [r15+20h], 0
0x18016854e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180168555  mov     [rbp+130h+var_E0], rax
0x180168559  mov     rax, rsi
0x18016855c  cmovnz  rax, [r15+20h]
0x180168561  cmp     qword ptr [r13+78h], 0
0x180168566  mov     [rbp+130h+var_D8], rax
0x18016856a  mov     rax, rsi
0x18016856d  cmovnz  rax, [r13+78h]
0x180168572  mov     qword ptr [rbp+130h+var_D0], rax
0x180168576  test    rcx, rcx
0x180168579  jz      short loc_1801685D1
0x18016857b  lea     rax, [rbp+130h+var_188]
0x18016857f  mov     [rsp+230h+var_1D0], rax
0x180168584  lea     rax, [rbp+130h+var_108]
0x180168588  mov     [rsp+230h+var_1D8], rax
0x18016858d  lea     rax, [rbp+130h+var_100]
0x180168591  mov     [rsp+230h+var_1E0], rax
0x180168596  lea     rax, [rbp+130h+var_F8]
0x18016859a  mov     [rsp+230h+var_1E8], rax
0x18016859f  lea     rax, [rbp+130h+var_F0]
0x1801685a3  mov     [rsp+230h+var_1F0], rax
0x1801685a8  lea     rax, [rbp+130h+var_E8]
0x1801685ac  mov     [rsp+230h+var_1F8], rax
0x1801685b1  lea     rax, [rbp+130h+var_E0]
0x1801685b5  mov     [rsp+230h+var_200], rax
0x1801685ba  lea     rax, [rbp+130h+var_D8]
0x1801685be  mov     [rsp+230h+var_208], rax
0x1801685c3  lea     rax, [rbp+130h+var_D0]
0x1801685c7  mov     [rsp+230h+var_210], rax; int
0x1801685cc  call    ??$LogNumObjects@PEB_WPEB_WPEB_WPEB_WPEB_WPEB_WPEB_WPEB_WPEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W33333333@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t const * const &,wchar_t const * const &,wchar_t const * const &,wchar_t const * const &,wchar_t const * const &,wchar_t const * const &,wchar_t const * const &,wchar_t const * const &)
0x1801685d1  mov     rcx, [r14+18h]
0x1801685d5  test    rcx, rcx
0x1801685d8  jz      short loc_180168610
0x1801685da  mov     eax, [rbp+130h+arg_40]
0x1801685e0  xor     r9d, r9d
0x1801685e3  mov     r10, [rcx]
0x1801685e6  test    eax, eax
0x1801685e8  mov     edx, 20h ; ' '
0x1801685ed  setz    r9b
0x1801685f1  neg     eax
0x1801685f3  mov     rax, [r10+28h]
0x1801685f7  sbb     r8d, r8d
0x1801685fa  neg     r8d
0x1801685fd  add     r8d, 0FFFFFFFEh
0x180168601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180168606  mov     ebx, eax
0x180168608  test    eax, eax
  ... truncated ...
```
