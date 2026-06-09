# IkeRegisterWithBFE

- ea: `0x180056ff8`
- end: `0x1800580ca`
- name: `IkeRegisterWithBFE`
- size: `4306`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180054bf4`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800061ec`
- `0x180008388`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x1800510ee`
- `0x180053afc`
- `0x180056ff8`
- `0x18005bc40`

## import_xrefs

- `fwpuclnt!FwpmFilterSubscribeChanges0` at `0x18005726f`
- `fwpuclnt!FwpmFilterSubscribeChanges0` at `0x180057371`
- `fwpuclnt!FwpmFilterSubscribeChanges0` at `0x18005746b`
- `fwpuclnt!FwpmFilterSubscribeChanges0` at `0x180057565`
- `fwpuclnt!FwpmFilterSubscribeChanges0` at `0x18005726f`
- `fwpuclnt!FwpmFilterSubscribeChanges0` at `0x180057371`
- `fwpuclnt!FwpmFilterSubscribeChanges0` at `0x18005746b`
- `fwpuclnt!FwpmFilterSubscribeChanges0` at `0x180057565`
- `fwpuclnt!FwpmProviderContextSubscribeChanges0` at `0x18005766c`
- `fwpuclnt!FwpmProviderContextSubscribeChanges0` at `0x18005776a`
- `fwpuclnt!FwpmProviderContextSubscribeChanges0` at `0x180057860`
- `fwpuclnt!FwpmProviderContextSubscribeChanges0` at `0x180057953`
- `fwpuclnt!FwpmProviderContextSubscribeChanges0` at `0x180057a49`
- `fwpuclnt!FwpmProviderContextSubscribeChanges0` at `0x180057b3f`
- `fwpuclnt!FwpmProviderContextSubscribeChanges0` at `0x180057c32`
- `fwpuclnt!FwpmProviderContextSubscribeChanges0` at `0x180057d28`
- `fwpuclnt!FwpmProviderContextSubscribeChanges0` at `0x18005766c`
- `fwpuclnt!FwpmProviderContextSubscribeChanges0` at `0x18005776a`
- `fwpuclnt!FwpmProviderContextSubscribeChanges0` at `0x180057860`
- `fwpuclnt!FwpmProviderContextSubscribeChanges0` at `0x180057953`
- `fwpuclnt!FwpmProviderContextSubscribeChanges0` at `0x180057a49`
- `fwpuclnt!FwpmProviderContextSubscribeChanges0` at `0x180057b3f`
- `fwpuclnt!FwpmProviderContextSubscribeChanges0` at `0x180057c32`
- `fwpuclnt!FwpmProviderContextSubscribeChanges0` at `0x180057d28`
- `fwpuclnt!IPsecKeyModuleAdd0` at `0x180057e4f`
- `fwpuclnt!IPsecKeyModuleAdd0` at `0x180057f6a`
- `fwpuclnt!IPsecKeyModuleAdd0` at `0x18005807e`
- `fwpuclnt!IPsecKeyModuleAdd0` at `0x180057e4f`
- `fwpuclnt!IPsecKeyModuleAdd0` at `0x180057f6a`
- `fwpuclnt!IPsecKeyModuleAdd0` at `0x18005807e`
- `fwpuclnt!FwpmEventProviderCreate0` at `0x180057144`
- `fwpuclnt!FwpmEventProviderCreate0` at `0x180057144`

## string_xrefs

- `0x18005714e`: `FwpmEventProviderCreate0`

## pseudocode

```c
__int64 IkeRegisterWithBFE()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // r8
  __int64 v3; // r9
  __int64 v4; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  int TlsMmLuid; // eax
  __int64 v11; // rcx
  __int64 v12; // rax
  int v13; // r8d
  int v14; // r9d
  DWORD v15; // eax
  __int64 v16; // rcx
  const char *v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rsi
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rdi
  __int64 v24; // rbx
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rax
  int v32; // r8d
  int v33; // r9d
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // rdi
  __int64 v38; // rbx
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // r8
  __int64 v42; // r9
  int v43; // eax
  __int64 v44; // rcx
  __int64 v45; // rax
  int v46; // r8d
  int v47; // r9d
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // r9
  __int64 v51; // rdi
  __int64 v52; // rbx
  __int64 v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // r8
  __int64 v56; // r9
  int v57; // eax
  __int64 v58; // rcx
  __int64 v59; // rax
  int v60; // r8d
  int v61; // r9d
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // r9
  __int64 v65; // rdi
  __int64 v66; // rbx
  __int64 v67; // rdx
  __int64 v68; // rcx
  __int64 v69; // r8
  __int64 v70; // r9
  int v71; // eax
  __int64 v72; // rcx
  __int64 v73; // rax
  int v74; // r8d
  int v75; // r9d
  __int64 v76; // rdx
  __int64 v77; // r8
  __int64 v78; // r9
  __int64 v79; // rdi
  __int64 v80; // rbx
  __int64 v81; // rdx
  __int64 v82; // rcx
  __int64 v83; // r8
  __int64 v84; // r9
  int v85; // eax
  __int64 v86; // rcx
  __int64 v87; // rax
  int v88; // r8d
  int v89; // r9d
  __int64 v90; // rdx
  __int64 v91; // r8
  __int64 v92; // r9
  __int64 v93; // rdi
  __int64 v94; // rbx
  __int64 v95; // rdx
  __int64 v96; // rcx
  __int64 v97; // r8
  __int64 v98; // r9
  int v99; // eax
  __int64 v100; // rcx
  __int64 v101; // rax
  int v102; // r8d
  int v103; // r9d
  __int64 v104; // rdx
  __int64 v105; // r8
  __int64 v106; // r9
  __int64 v107; // rdi
  __int64 v108; // rbx
  __int64 v109; // rdx
  __int64 v110; // rcx
  __int64 v111; // r8
  __int64 v112; // r9
  int v113; // eax
  __int64 v114; // rcx
  __int64 v115; // rax
  int v116; // r8d
  int v117; // r9d
  __int64 v118; // rdx
  __int64 v119; // r8
  __int64 v120; // r9
  __int64 v121; // rdi
  __int64 v122; // rbx
  __int64 v123; // rdx
  __int64 v124; // rcx
  __int64 v125; // r8
  __int64 v126; // r9
  int v127; // eax
  __int64 v128; // rcx
  __int64 v129; // rax
  int v130; // r8d
  int v131; // r9d
  __int64 v132; // rdx
  __int64 v133; // r8
  __int64 v134; // r9
  __int64 v135; // rdi
  __int64 v136; // rbx
  __int64 v137; // rdx
  __int64 v138; // rcx
  __int64 v139; // r8
  __int64 v140; // r9
  int v141; // eax
  __int64 v142; // rcx
  __int64 v143; // rax
  int v144; // r8d
  int v145; // r9d
  __int64 v146; // rdx
  __int64 v147; // r8
  __int64 v148; // r9
  __int64 v149; // rdi
  __int64 v150; // rbx
  __int64 v151; // rdx
  __int64 v152; // rcx
  __int64 v153; // r8
  __int64 v154; // r9
  int v155; // eax
  __int64 v156; // rcx
  __int64 v157; // rax
  int v158; // r8d
  int v159; // r9d
  __int64 v160; // rdx
  __int64 v161; // r8
  __int64 v162; // r9
  __int64 v163; // rdi
  __int64 v164; // rbx
  __int64 v165; // rdx
  __int64 v166; // rcx
  __int64 v167; // r8
  __int64 v168; // r9
  int v169; // eax
  __int64 v170; // rcx
  __int64 v171; // rax
  int v172; // r8d
  int v173; // r9d
  __int64 v174; // rdx
  __int64 v175; // r8
  __int64 v176; // r9
  __int64 v177; // rdi
  __int64 v178; // rbx
  __int64 v179; // rdx
  __int64 v180; // rcx
  __int64 v181; // r8
  __int64 v182; // r9
  int v183; // eax
  __int64 v184; // rcx
  __int64 v185; // rax
  int v186; // r8d
  int v187; // r9d
  __int64 v188; // rdx
  __int64 v189; // r8
  __int64 v190; // r9
  __int64 v191; // rdi
  __int64 v192; // rbx
  __int64 v193; // rdx
  __int64 v194; // rcx
  __int64 v195; // r8
  __int64 v196; // r9
  int v197; // eax
  __int64 v198; // rcx
  __int64 v199; // rax
  int v200; // r8d
  int v201; // r9d
  __int64 v202; // rdx
  __int64 v203; // r8
  __int64 v204; // r9
  __int64 v205; // rdi
  __int64 v206; // rbx
  __int64 v207; // rdx
  __int64 v208; // rcx
  __int64 v209; // r8
  __int64 v210; // r9
  int v211; // eax
  __int64 v212; // rcx
  __int64 v213; // rax
  int v214; // r8d
  int v215; // r9d
  __int64 v216; // rdx
  __int64 v217; // r8
  __int64 v218; // r9
  __int64 v219; // rdi
  __int64 v220; // rbx
  __int64 v221; // rdx
  __int64 v222; // rcx
  __int64 v223; // r8
  __int64 v224; // r9
  int v225; // eax
  __int64 v226; // rcx
  __int64 v227; // rax
  int v228; // r8d
  FWPM_PROVIDER_CONTEXT_SUBSCRIPTION0 v230; // [rsp+30h] [rbp-D0h] BYREF
  GUID v231; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v232; // [rsp+60h] [rbp-A0h]
  __int64 (__fastcall *v233)(int, int, int, int, __int64, int, int, __int64); // [rsp+70h] [rbp-90h]
  __int64 (__fastcall *v234)(); // [rsp+78h] [rbp-88h]
  __int64 (__fastcall *v235)(); // [rsp+80h] [rbp-80h]
  __int64 (__fastcall *v236)(); // [rsp+88h] [rbp-78h]
  FWPM_FILTER_SUBSCRIPTION0 subscription; // [rsp+90h] [rbp-70h] BYREF
  __int64 v238; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v239; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v240[8]; // [rsp+D0h] [rbp-30h] BYREF
  GUID v241; // [rsp+D8h] [rbp-28h]
  int v242; // [rsp+E8h] [rbp-18h]
  int v243; // [rsp+108h] [rbp+8h]
  _BYTE v244[32]; // [rsp+120h] [rbp+20h] BYREF
  __int64 *v245; // [rsp+140h] [rbp+40h]
  __int64 v246; // [rsp+148h] [rbp+48h]
  _BYTE v247[16]; // [rsp+150h] [rbp+50h] BYREF
  const char *v248; // [rsp+160h] [rbp+60h]
  __int64 v249; // [rsp+168h] [rbp+68h]

  memset_0(&v231, 0, 0x40u);
  memset_0(v240, 0, 0x48u);
  memset(&subscription, 0, sizeof(subscription));
  v239 = 0;
  memset(&v230, 0, sizeof(v230));
  TraceLogHelper("IkeRegisterWithBFE", 1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v4 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    TlsPeerAddr = IkeGetTlsPeerAddr(v1);
    TlsMmLuid = IkeGetTlsMmLuid(v7, v6, v8, v9);
    WPP_SF_iS(v4, 30, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, TlsMmLuid, TlsPeerAddr);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v238 = IkeGetTlsMmLuid(v1, v0, v2, v3);
    v245 = &v238;
    v246 = 8;
    v12 = IkeGetTlsPeerAddr(v11);
    tlgCreate1Sz_wchar_t(v247, v12);
    v249 = 42;
    v248 = "Subscribing as diagnostics event provider";
    tlgWriteTransfer_EtwEventWriteTransfer(
      (unsigned int)&dword_180173278,
      (unsigned int)byte_18014F161,
      v13,
      v14,
      5,
      (__int64)v244);
  }
  v15 = FwpmEventProviderCreate0(0, &gIkeExtGlobals[71].LockSemaphore);
  if ( v15 )
  {
    v17 = "FwpmEventProviderCreate0";
LABEL_118:
    v20 = WfpReportSysErrorAsWinError(v16, v17, v15, 1);
    return IkeReturnError(v20, "IkeRegisterWithBFE");
  }
  v20 = WfpUnifiedTraceStart();
  if ( !v20 )
  {
    v242 = 0;
    v243 = -1;
    v241 = FWPM_LAYER_IKEEXT_V4;
    subscription.flags = 2;
    subscription.enumTemplate = (FWPM_FILTER_ENUM_TEMPLATE0 *)v240;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v23 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v24 = IkeGetTlsPeerAddr(v19);
      v29 = IkeGetTlsMmLuid(v26, v25, v27, v28);
      WPP_SF_iS(v23, 31, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v29, v24);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v238 = IkeGetTlsMmLuid(v19, v18, v21, v22);
      v245 = &v238;
      v246 = 8;
      v31 = IkeGetTlsPeerAddr(v30);
      tlgCreate1Sz_wchar_t(v247, v31);
      v249 = 43;
      v248 = "Subscribing for MM V4 filter notifications";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&unk_18014F120,
        v32,
        v33,
        5,
        (__int64)v244);
    }
    v15 = FwpmFilterSubscribeChanges0(
            gIkeExtGlobals[68].OwningThread,
            &subscription,
            IkeProcessMMFilterChange,
            0,
            (HANDLE *)&gIkeExtGlobals[69].LockCount);
    if ( v15 )
      goto LABEL_17;
    v241 = FWPM_LAYER_IKEEXT_V6;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v37 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v38 = IkeGetTlsPeerAddr(v16);
      v43 = IkeGetTlsMmLuid(v40, v39, v41, v42);
      WPP_SF_iS(v37, 32, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v43, v38);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v238 = IkeGetTlsMmLuid(v16, v34, v35, v36);
      v245 = &v238;
      v246 = 8;
      v45 = IkeGetTlsPeerAddr(v44);
      tlgCreate1Sz_wchar_t(v247, v45);
      v249 = 43;
      v248 = "Subscribing for MM V6 filter notifications";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&byte_18014F0DF,
        v46,
        v47,
        5,
        (__int64)v244);
    }
    v15 = FwpmFilterSubscribeChanges0(
            gIkeExtGlobals[68].OwningThread,
            &subscription,
            IkeProcessMMFilterChange,
            0,
            &gIkeExtGlobals[69].LockSemaphore);
    if ( v15 )
      goto LABEL_17;
    v241 = FWPM_LAYER_IPSEC_V4;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v51 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v52 = IkeGetTlsPeerAddr(v16);
      v57 = IkeGetTlsMmLuid(v54, v53, v55, v56);
      WPP_SF_iS(v51, 33, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v57, v52);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v238 = IkeGetTlsMmLuid(v16, v48, v49, v50);
      v245 = &v238;
      v246 = 8;
      v59 = IkeGetTlsPeerAddr(v58);
      tlgCreate1Sz_wchar_t(v247, v59);
      v249 = 43;
      v248 = "Subscribing for QM V4 filter notifications";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&word_18014F09E,
        v60,
        v61,
        5,
        (__int64)v244);
    }
    v15 = FwpmFilterSubscribeChanges0(
            gIkeExtGlobals[68].OwningThread,
            &subscription,
            IkeProcessQMFilterChange,
            0,
            &gIkeExtGlobals[69].OwningThread);
    if ( v15 )
      goto LABEL_17;
    v241 = FWPM_LAYER_IPSEC_V6;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v65 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v66 = IkeGetTlsPeerAddr(v16);
      v71 = IkeGetTlsMmLuid(v68, v67, v69, v70);
      WPP_SF_iS(v65, 34, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v71, v66);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v238 = IkeGetTlsMmLuid(v16, v62, v63, v64);
      v245 = &v238;
      v246 = 8;
      v73 = IkeGetTlsPeerAddr(v72);
      tlgCreate1Sz_wchar_t(v247, v73);
      v249 = 43;
      v248 = "Subscribing for QM V6 filter notifications";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)byte_18014F05D,
        v74,
        v75,
        5,
        (__int64)v244);
    }
    v15 = FwpmFilterSubscribeChanges0(
            gIkeExtGlobals[68].OwningThread,
            &subscription,
            IkeProcessQMFilterChange,
            0,
            (HANDLE *)&gIkeExtGlobals[69].SpinCount);
    if ( v15 )
    {
LABEL_17:
      v17 = "FwpmFilterSubscribeChanges0";
      goto LABEL_118;
    }
    DWORD2(v239) = 5;
    v230.enumTemplate = (FWPM_PROVIDER_CONTEXT_ENUM_TEMPLATE0 *)&v239;
    v230.flags = 2;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v79 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v80 = IkeGetTlsPeerAddr(v16);
      v85 = IkeGetTlsMmLuid(v82, v81, v83, v84);
      WPP_SF_iS(v79, 35, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v85, v80);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v238 = IkeGetTlsMmLuid(v16, v76, v77, v78);
      v245 = &v238;
      v246 = 8;
      v87 = IkeGetTlsPeerAddr(v86);
      tlgCreate1Sz_wchar_t(v247, v87);
      v249 = 44;
      v248 = "Subscribing for IKE MM policy notifications";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&dword_18014F01C,
        v88,
        v89,
        5,
        (__int64)v244);
    }
    v15 = FwpmProviderContextSubscribeChanges0(
            gIkeExtGlobals[68].OwningThread,
            &v230,
            IkeProcessMMPolicyChange,
            0,
            (HANDLE *)&gIkeExtGlobals[70].DebugInfo);
    if ( v15 )
      goto LABEL_46;
    DWORD2(v239) = 6;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v93 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v94 = IkeGetTlsPeerAddr(v16);
      v99 = IkeGetTlsMmLuid(v96, v95, v97, v98);
      WPP_SF_iS(v93, 36, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v99, v94);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v238 = IkeGetTlsMmLuid(v16, v90, v91, v92);
      v245 = &v238;
      v246 = 8;
      v101 = IkeGetTlsPeerAddr(v100);
      tlgCreate1Sz_wchar_t(v247, v101);
      v249 = 47;
      v248 = "Subscribing for Authip MM policy notifications";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)byte_18014EFDB,
        v102,
        v103,
        5,
        (__int64)v244);
    }
    v15 = FwpmProviderContextSubscribeChanges0(
            gIkeExtGlobals[68].OwningThread,
            &v230,
            IkeProcessMMPolicyChange,
            0,
            &gIkeExtGlobals[70].LockSemaphore);
    if ( v15 )
      goto LABEL_46;
    DWORD2(v239) = 10;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v107 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v108 = IkeGetTlsPeerAddr(v16);
      v113 = IkeGetTlsMmLuid(v110, v109, v111, v112);
      WPP_SF_iS(v107, 37, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v113, v108);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v238 = IkeGetTlsMmLuid(v16, v104, v105, v106);
      v245 = &v238;
      v246 = 8;
      v115 = IkeGetTlsPeerAddr(v114);
      tlgCreate1Sz_wchar_t(v247, v115);
      v249 = 46;
      v248 = "Subscribing for IKEv2 MM policy notifications";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)word_18014EF9A,
        v116,
        v117,
        5,
        (__int64)v244);
    }
    v15 = FwpmProviderContextSubscribeChanges0(
            gIkeExtGlobals[68].OwningThread,
            &v230,
            IkeProcessMMPolicyChange,
            0,
            (HANDLE *)&gIkeExtGlobals[70].SpinCount);
    if ( v15 )
      goto LABEL_46;
    DWORD2(v239) = 1;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v121 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v122 = IkeGetTlsPeerAddr(v16);
      v127 = IkeGetTlsMmLuid(v124, v123, v125, v126);
      WPP_SF_iS(v121, 38, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v127, v122);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v238 = IkeGetTlsMmLuid(v16, v118, v119, v120);
      v245 = &v238;
      v246 = 8;
      v129 = IkeGetTlsPeerAddr(v128);
      tlgCreate1Sz_wchar_t(v247, v129);
      v249 = 54;
      v248 = "Subscribing for IKE QM transport policy notifications";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)byte_18014EF59,
        v130,
        v131,
        5,
        (__int64)v244);
    }
    v15 = FwpmProviderContextSubscribeChanges0(
            gIkeExtGlobals[68].OwningThread,
            &v230,
            IkeProcessQMPolicyChange,
            0,
            (HANDLE *)&gIkeExtGlobals[70].LockCount);
    if ( v15 )
      goto LABEL_46;
    DWORD2(v239) = 2;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v135 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v136 = IkeGetTlsPeerAddr(v16);
      v141 = IkeGetTlsMmLuid(v138, v137, v139, v140);
      WPP_SF_iS(v135, 39, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v141, v136);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v238 = IkeGetTlsMmLuid(v16, v132, v133, v134);
      v245 = &v238;
      v246 = 8;
      v143 = IkeGetTlsPeerAddr(v142);
      tlgCreate1Sz_wchar_t(v247, v143);
      v249 = 51;
      v248 = "Subscribing for IKE QM tunnel policy notifications";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&unk_18014EF18,
        v144,
        v145,
        5,
        (__int64)v244);
    }
    v15 = FwpmProviderContextSubscribeChanges0(
            gIkeExtGlobals[68].OwningThread,
            &v230,
            IkeProcessQMPolicyChange,
            0,
            &gIkeExtGlobals[70].OwningThread);
    if ( v15 )
      goto LABEL_46;
    DWORD2(v239) = 3;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v149 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v150 = IkeGetTlsPeerAddr(v16);
      v155 = IkeGetTlsMmLuid(v152, v151, v153, v154);
      WPP_SF_iS(v149, 40, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v155, v150);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v238 = IkeGetTlsMmLuid(v16, v146, v147, v148);
      v245 = &v238;
      v246 = 8;
      v157 = IkeGetTlsPeerAddr(v156);
      tlgCreate1Sz_wchar_t(v247, v157);
      v249 = 57;
      v248 = "Subscribing for Authip QM transport policy notifications";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&byte_18014EED7,
        v158,
        v159,
        5,
        (__int64)v244);
    }
    v15 = FwpmProviderContextSubscribeChanges0(
            gIkeExtGlobals[68].OwningThread,
            &v230,
            IkeProcessQMPolicyChange,
            0,
            (HANDLE *)&gIkeExtGlobals[71].DebugInfo);
    if ( v15 )
      goto LABEL_46;
    DWORD2(v239) = 4;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v163 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v164 = IkeGetTlsPeerAddr(v16);
      v169 = IkeGetTlsMmLuid(v166, v165, v167, v168);
      WPP_SF_iS(v163, 41, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v169, v164);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v238 = IkeGetTlsMmLuid(v16, v160, v161, v162);
      v245 = &v238;
      v246 = 8;
      v171 = IkeGetTlsPeerAddr(v170);
      tlgCreate1Sz_wchar_t(v247, v171);
      v249 = 54;
      v248 = "Subscribing for Authip QM tunnel policy notifications";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&word_18014EE96,
        v172,
        v173,
        5,
        (__int64)v244);
    }
    v15 = FwpmProviderContextSubscribeChanges0(
            gIkeExtGlobals[68].OwningThread,
            &v230,
            IkeProcessQMPolicyChange,
            0,
            (HANDLE *)&gIkeExtGlobals[71].LockCount);
    if ( v15 )
      goto LABEL_46;
    DWORD2(v239) = 9;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v177 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v178 = IkeGetTlsPeerAddr(v16);
      v183 = IkeGetTlsMmLuid(v180, v179, v181, v182);
      WPP_SF_iS(v177, 42, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v183, v178);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v238 = IkeGetTlsMmLuid(v16, v174, v175, v176);
      v245 = &v238;
      v246 = 8;
      v185 = IkeGetTlsPeerAddr(v184);
      tlgCreate1Sz_wchar_t(v247, v185);
      v249 = 53;
      v248 = "Subscribing for IKEv2 QM tunnel policy notifications";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)byte_18014EE55,
        v186,
        v187,
        5,
        (__int64)v244);
    }
    v15 = FwpmProviderContextSubscribeChanges0(
            gIkeExtGlobals[68].OwningThread,
            &v230,
            IkeProcessQMPolicyChange,
            0,
            &gIkeExtGlobals[71].OwningThread);
    if ( v15 )
    {
LABEL_46:
      v17 = "FwpmProviderContextSubscribeChanges0";
      goto LABEL_118;
    }
    v232 = ikev1DisplayName;
    v233 = IkeProcessAcquireOak;
    v234 = IkeProcessExpire;
    v235 = IkeProcessClearTextResponseOak;
    v236 = (__int64 (__fastcall *)())WARBIRD_DELAY_LOAD::SetBkMode;
    v231 = FWPM_KEYING_MODULE_IKE;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v191 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v192 = IkeGetTlsPeerAddr(v16);
      v197 = IkeGetTlsMmLuid(v194, v193, v195, v196);
      WPP_SF_iS(v191, 43, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v197, v192);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v238 = IkeGetTlsMmLuid(v16, v188, v189, v190);
      v245 = &v238;
      v246 = 8;
      v199 = IkeGetTlsPeerAddr(v198);
      tlgCreate1Sz_wchar_t(v247, v199);
      v249 = 30;
      v248 = "Registering IKE keying module";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&dword_18014EE14,
        v200,
        v201,
        5,
        (__int64)v244);
    }
    v15 = IPsecKeyModuleAdd0(gIkeExtGlobals[68].OwningThread, &v231, &gIkeExtGlobals[68].LockSemaphore);
    if ( v15 )
      goto LABEL_117;
    v232 = authipDisplayName;
    v233 = IkeProcessAcquireAuthip;
    v235 = IkeProcessClearTextResponseAuthip;
    v236 = (__int64 (__fastcall *)())WARBIRD_DELAY_LOAD::SetBkMode;
    v231 = FWPM_KEYING_MODULE_AUTHIP;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v205 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v206 = IkeGetTlsPeerAddr(v16);
      v211 = IkeGetTlsMmLuid(v208, v207, v209, v210);
      WPP_SF_iS(v205, 44, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v211, v206);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v238 = IkeGetTlsMmLuid(v16, v202, v203, v204);
      v245 = &v238;
      v246 = 8;
      v213 = IkeGetTlsPeerAddr(v212);
      tlgCreate1Sz_wchar_t(v247, v213);
      v249 = 33;
      v248 = "Registering Authip keying module";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)byte_18014EDD3,
        v214,
        v215,
        5,
        (__int64)v244);
    }
    v15 = IPsecKeyModuleAdd0(gIkeExtGlobals[68].OwningThread, &v231, &gIkeExtGlobals[68].SpinCount);
    if ( v15 )
      goto LABEL_117;
    v232 = ikev2DisplayName;
    v233 = IkeProcessAcquireIkeV2;
    v235 = guard_check_icall_nop;
    v236 = IkeIfrEventEnumCallbackIkeV2;
    v231 = FWPM_KEYING_MODULE_IKEV2;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v219 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v220 = IkeGetTlsPeerAddr(v16);
      v225 = IkeGetTlsMmLuid(v222, v221, v223, v224);
      WPP_SF_iS(v219, 45, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v225, v220);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v238 = IkeGetTlsMmLuid(v16, v216, v217, v218);
      v245 = &v238;
      v246 = 8;
      v227 = IkeGetTlsPeerAddr(v226);
      tlgCreate1Sz_wchar_t(v247, v227);
      v249 = 32;
      v248 = "Registering IKEv2 keying module";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)word_18014ED92,
        v228,
        (unsigned int)"Registering IKEv2 keying module",
        5,
        (__int64)v244);
    }
    v15 = IPsecKeyModuleAdd0(gIkeExtGlobals[68].OwningThread, &v231, &gIkeExtGlobals[69]);
    if ( v15 )
    {
LABEL_117:
      v17 = "IPsecKeyModuleAdd0";
      goto LABEL_118;
    }
  }
  return IkeReturnError(v20, "IkeRegisterWithBFE");
}

```

## disassembly

```asm
0x180056ff8  push    rbp
0x180056ffa  push    rbx
0x180056ffb  push    rsi
0x180056ffc  push    rdi
0x180056ffd  push    r12
0x180056fff  push    r14
0x180057001  push    r15
0x180057003  lea     rbp, [rsp-80h]
0x180057008  sub     rsp, 180h
0x18005700f  mov     rax, cs:__security_cookie
0x180057016  xor     rax, rsp
0x180057019  mov     [rbp+0B0h+var_40], rax
0x18005701d  xor     edx, edx; Val
0x18005701f  lea     rcx, [rsp+1B0h+var_160]; void *
0x180057024  lea     r8d, [rdx+40h]; Size
0x180057028  call    memset_0
0x18005702d  xor     edx, edx; Val
0x18005702f  lea     rcx, [rbp+0B0h+var_E0]; void *
0x180057033  lea     r8d, [rdx+48h]; Size
0x180057037  call    memset_0
0x18005703c  xorps   xmm0, xmm0
0x18005703f  lea     rcx, aIkeregisterwit; "IkeRegisterWithBFE"
0x180057046  xorps   xmm1, xmm1
0x180057049  mov     r12d, 1
0x18005704f  mov     edx, r12d
0x180057052  movups  xmmword ptr [rbp+0B0h+subscription.enumTemplate], xmm0
0x180057056  movups  xmmword ptr [rbp+0B0h+subscription.sessionKey.Data2], xmm0
0x18005705a  movups  [rbp+0B0h+var_F8], xmm0
0x18005705e  movups  xmmword ptr [rsp+1B0h+var_180.enumTemplate], xmm1
0x180057063  movups  xmmword ptr [rsp+1B0h+var_180.sessionKey.Data2], xmm1
0x180057068  call    TraceLogHelper
0x18005706d  mov     rdi, cs:WPP_GLOBAL_Control
0x180057074  lea     rbx, WPP_GLOBAL_Control
0x18005707b  lea     r14d, [r12+3]
0x180057080  cmp     rdi, rbx
0x180057083  jz      short loc_1800570C5
0x180057085  cmp     [rdi+19h], r14b
0x180057089  jb      short loc_1800570C5
0x18005708b  test    byte ptr [rdi+1Ch], 10h
0x18005708f  jz      short loc_1800570C5
0x180057091  mov     rdi, [rdi+10h]
0x180057095  call    IkeGetTlsPeerAddr
0x18005709a  mov     rbx, rax
0x18005709d  call    IkeGetTlsMmLuid
0x1800570a2  mov     r9, rax
0x1800570a5  mov     [rsp+1B0h+changeHandle], rbx
0x1800570aa  lea     edx, [r12+1Dh]
0x1800570af  mov     rcx, rdi
0x1800570b2  lea     r8, WPP_c3da8f174801358a223b58501d21a257_Traceguids
0x1800570b9  call    WPP_SF_iS
0x1800570be  lea     rbx, WPP_GLOBAL_Control
0x1800570c5  mov     eax, cs:dword_180173278
0x1800570cb  xor     r15d, r15d
0x1800570ce  cmp     eax, r14d
0x1800570d1  jbe     short loc_180057134
0x1800570d3  call    IkeGetTlsMmLuid
0x1800570d8  mov     [rbp+0B0h+var_100], rax
0x1800570dc  lea     rax, [rbp+0B0h+var_100]
0x1800570e0  mov     [rbp+0B0h+var_70], rax
0x1800570e4  mov     [rbp+0B0h+var_68], 8
0x1800570ec  call    IkeGetTlsPeerAddr
0x1800570f1  mov     rdx, rax
0x1800570f4  lea     rcx, [rbp+0B0h+var_60]
0x1800570f8  call    _tlgCreate1Sz_wchar_t
0x1800570fd  lea     rcx, aSubscribingAsD; "Subscribing as diagnostics event provid"...
0x180057104  mov     [rbp+0B0h+var_48], 2Ah ; '*'
0x18005710c  lea     rax, [rbp+0B0h+var_90]
0x180057110  mov     [rbp+0B0h+var_50], rcx
0x180057114  mov     [rsp+1B0h+var_188], rax
0x180057119  lea     rcx, dword_180173278
0x180057120  lea     rdx, byte_18014F161
0x180057127  mov     dword ptr [rsp+1B0h+changeHandle], 5
0x18005712f  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180057134  mov     rdx, cs:gIkeExtGlobals
0x18005713b  xor     ecx, ecx
0x18005713d  add     rdx, 0B30h
0x180057144  call    cs:__imp_FwpmEventProviderCreate0
0x18005714a  test    eax, eax
0x18005714c  jz      short loc_18005715A
0x18005714e  lea     rdx, aFwpmeventprovi; "FwpmEventProviderCreate0"
0x180057155  jmp     loc_18005808F
0x18005715a  call    WfpUnifiedTraceStart
0x18005715f  mov     rsi, rax
0x180057162  test    rax, rax
0x180057165  jnz     loc_18005809D
0x18005716b  movups  xmm0, xmmword ptr cs:FWPM_LAYER_IKEEXT_V4.Data1
0x180057172  lea     rax, [rbp+0B0h+var_E0]
0x180057176  mov     [rbp+0B0h+var_C8], r15d
0x18005717a  mov     [rbp+0B0h+var_A8], 0FFFFFFFFh
0x180057181  movdqu  [rbp+0B0h+var_D8], xmm0
0x180057186  mov     [rbp+0B0h+subscription.flags], 2
0x18005718d  mov     [rbp+0B0h+subscription.enumTemplate], rax
0x180057191  mov     rdi, cs:WPP_GLOBAL_Control
0x180057198  cmp     rdi, rbx
0x18005719b  jz      short loc_1800571DB
0x18005719d  cmp     [rdi+19h], r14b
0x1800571a1  jb      short loc_1800571DB
0x1800571a3  test    byte ptr [rdi+1Ch], 10h
0x1800571a7  jz      short loc_1800571DB
0x1800571a9  mov     rdi, [rdi+10h]
0x1800571ad  call    IkeGetTlsPeerAddr
0x1800571b2  mov     rbx, rax
0x1800571b5  call    IkeGetTlsMmLuid
0x1800571ba  mov     r9, rax
0x1800571bd  mov     [rsp+1B0h+changeHandle], rbx
0x1800571c2  lea     edx, [rsi+1Fh]
0x1800571c5  mov     rcx, rdi
0x1800571c8  lea     r8, WPP_c3da8f174801358a223b58501d21a257_Traceguids
0x1800571cf  call    WPP_SF_iS
0x1800571d4  lea     rbx, WPP_GLOBAL_Control
0x1800571db  mov     eax, cs:dword_180173278
0x1800571e1  cmp     eax, r14d
0x1800571e4  jbe     short loc_180057247
0x1800571e6  call    IkeGetTlsMmLuid
0x1800571eb  mov     [rbp+0B0h+var_100], rax
0x1800571ef  lea     rax, [rbp+0B0h+var_100]
0x1800571f3  mov     [rbp+0B0h+var_70], rax
0x1800571f7  mov     [rbp+0B0h+var_68], 8
0x1800571ff  call    IkeGetTlsPeerAddr
0x180057204  mov     rdx, rax
0x180057207  lea     rcx, [rbp+0B0h+var_60]
0x18005720b  call    _tlgCreate1Sz_wchar_t
0x180057210  lea     rcx, aSubscribingFor_9; "Subscribing for MM V4 filter notificati"...
0x180057217  mov     [rbp+0B0h+var_48], 2Bh ; '+'
0x18005721f  lea     rax, [rbp+0B0h+var_90]
0x180057223  mov     [rbp+0B0h+var_50], rcx
0x180057227  mov     [rsp+1B0h+var_188], rax
0x18005722c  lea     rcx, dword_180173278
0x180057233  lea     rdx, unk_18014F120
0x18005723a  mov     dword ptr [rsp+1B0h+changeHandle], 5
0x180057242  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180057247  mov     rcx, cs:gIkeExtGlobals
0x18005724e  lea     r8, IkeProcessMMFilterChange; callback
0x180057255  xor     r9d, r9d; context
0x180057258  lea     rdx, [rbp+0B0h+subscription]; subscription
0x18005725c  lea     rax, [rcx+0AD0h]
0x180057263  mov     rcx, [rcx+0AB0h]; engineHandle
0x18005726a  mov     [rsp+1B0h+changeHandle], rax; changeHandle
0x18005726f  call    cs:__imp_FwpmFilterSubscribeChanges0
0x180057275  test    eax, eax
0x180057277  jz      short loc_180057285
0x180057279  lea     rdx, aFwpmfiltersubs; "FwpmFilterSubscribeChanges0"
0x180057280  jmp     loc_18005808F
0x180057285  movups  xmm0, xmmword ptr cs:FWPM_LAYER_IKEEXT_V6.Data1
0x18005728c  movdqu  [rbp+0B0h+var_D8], xmm0
0x180057291  mov     rdi, cs:WPP_GLOBAL_Control
0x180057298  cmp     rdi, rbx
0x18005729b  jz      short loc_1800572DD
0x18005729d  cmp     [rdi+19h], r14b
0x1800572a1  jb      short loc_1800572DD
0x1800572a3  test    byte ptr [rdi+1Ch], 10h
0x1800572a7  jz      short loc_1800572DD
0x1800572a9  mov     rdi, [rdi+10h]
0x1800572ad  call    IkeGetTlsPeerAddr
0x1800572b2  mov     rbx, rax
0x1800572b5  call    IkeGetTlsMmLuid
0x1800572ba  mov     r9, rax
0x1800572bd  mov     [rsp+1B0h+changeHandle], rbx
0x1800572c2  mov     edx, 20h ; ' '
0x1800572c7  lea     r8, WPP_c3da8f174801358a223b58501d21a257_Traceguids
0x1800572ce  mov     rcx, rdi
0x1800572d1  call    WPP_SF_iS
0x1800572d6  lea     rbx, WPP_GLOBAL_Control
0x1800572dd  mov     eax, cs:dword_180173278
0x1800572e3  cmp     eax, r14d
0x1800572e6  jbe     short loc_180057349
0x1800572e8  call    IkeGetTlsMmLuid
0x1800572ed  mov     [rbp+0B0h+var_100], rax
0x1800572f1  lea     rax, [rbp+0B0h+var_100]
0x1800572f5  mov     [rbp+0B0h+var_70], rax
0x1800572f9  mov     [rbp+0B0h+var_68], 8
0x180057301  call    IkeGetTlsPeerAddr
0x180057306  mov     rdx, rax
0x180057309  lea     rcx, [rbp+0B0h+var_60]
0x18005730d  call    _tlgCreate1Sz_wchar_t
0x180057312  lea     rcx, aSubscribingFor_0; "Subscribing for MM V6 filter notificati"...
0x180057319  mov     [rbp+0B0h+var_48], 2Bh ; '+'
0x180057321  lea     rax, [rbp+0B0h+var_90]
0x180057325  mov     [rbp+0B0h+var_50], rcx
0x180057329  mov     [rsp+1B0h+var_188], rax
0x18005732e  lea     rcx, dword_180173278
0x180057335  lea     rdx, byte_18014F0DF
0x18005733c  mov     dword ptr [rsp+1B0h+changeHandle], 5
0x180057344  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180057349  mov     rcx, cs:gIkeExtGlobals
0x180057350  lea     r8, IkeProcessMMFilterChange; callback
0x180057357  xor     r9d, r9d; context
0x18005735a  lea     rdx, [rbp+0B0h+subscription]; subscription
0x18005735e  lea     rax, [rcx+0AE0h]
0x180057365  mov     rcx, [rcx+0AB0h]; engineHandle
0x18005736c  mov     [rsp+1B0h+changeHandle], rax; changeHandle
0x180057371  call    cs:__imp_FwpmFilterSubscribeChanges0
0x180057377  test    eax, eax
0x180057379  jnz     loc_180057279
0x18005737f  movups  xmm0, xmmword ptr cs:FWPM_LAYER_IPSEC_V4.Data1
0x180057386  movdqu  [rbp+0B0h+var_D8], xmm0
0x18005738b  mov     rdi, cs:WPP_GLOBAL_Control
0x180057392  cmp     rdi, rbx
0x180057395  jz      short loc_1800573D7
0x180057397  cmp     [rdi+19h], r14b
0x18005739b  jb      short loc_1800573D7
0x18005739d  test    byte ptr [rdi+1Ch], 10h
0x1800573a1  jz      short loc_1800573D7
0x1800573a3  mov     rdi, [rdi+10h]
0x1800573a7  call    IkeGetTlsPeerAddr
0x1800573ac  mov     rbx, rax
0x1800573af  call    IkeGetTlsMmLuid
0x1800573b4  mov     r9, rax
0x1800573b7  mov     [rsp+1B0h+changeHandle], rbx
0x1800573bc  mov     edx, 21h ; '!'
0x1800573c1  lea     r8, WPP_c3da8f174801358a223b58501d21a257_Traceguids
0x1800573c8  mov     rcx, rdi
0x1800573cb  call    WPP_SF_iS
0x1800573d0  lea     rbx, WPP_GLOBAL_Control
0x1800573d7  mov     eax, cs:dword_180173278
0x1800573dd  cmp     eax, r14d
0x1800573e0  jbe     short loc_180057443
0x1800573e2  call    IkeGetTlsMmLuid
0x1800573e7  mov     [rbp+0B0h+var_100], rax
0x1800573eb  lea     rax, [rbp+0B0h+var_100]
0x1800573ef  mov     [rbp+0B0h+var_70], rax
0x1800573f3  mov     [rbp+0B0h+var_68], 8
0x1800573fb  call    IkeGetTlsPeerAddr
0x180057400  mov     rdx, rax
0x180057403  lea     rcx, [rbp+0B0h+var_60]
0x180057407  call    _tlgCreate1Sz_wchar_t
0x18005740c  lea     rcx, aSubscribingFor_5; "Subscribing for QM V4 filter notificati"...
0x180057413  mov     [rbp+0B0h+var_48], 2Bh ; '+'
0x18005741b  lea     rax, [rbp+0B0h+var_90]
0x18005741f  mov     [rbp+0B0h+var_50], rcx
0x180057423  mov     [rsp+1B0h+var_188], rax
0x180057428  lea     rcx, dword_180173278
0x18005742f  lea     rdx, word_18014F09E
0x180057436  mov     dword ptr [rsp+1B0h+changeHandle], 5
0x18005743e  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180057443  mov     rcx, cs:gIkeExtGlobals
0x18005744a  lea     r8, IkeProcessQMFilterChange; callback
0x180057451  xor     r9d, r9d; context
0x180057454  lea     rdx, [rbp+0B0h+subscription]; subscription
0x180057458  lea     rax, [rcx+0AD8h]
0x18005745f  mov     rcx, [rcx+0AB0h]; engineHandle
0x180057466  mov     [rsp+1B0h+changeHandle], rax; changeHandle
0x18005746b  call    cs:__imp_FwpmFilterSubscribeChanges0
0x180057471  test    eax, eax
0x180057473  jnz     loc_180057279
0x180057479  movups  xmm0, xmmword ptr cs:FWPM_LAYER_IPSEC_V6.Data1
0x180057480  movdqu  [rbp+0B0h+var_D8], xmm0
0x180057485  mov     rdi, cs:WPP_GLOBAL_Control
0x18005748c  cmp     rdi, rbx
0x18005748f  jz      short loc_1800574D1
0x180057491  cmp     [rdi+19h], r14b
0x180057495  jb      short loc_1800574D1
0x180057497  test    byte ptr [rdi+1Ch], 10h
0x18005749b  jz      short loc_1800574D1
0x18005749d  mov     rdi, [rdi+10h]
0x1800574a1  call    IkeGetTlsPeerAddr
0x1800574a6  mov     rbx, rax
0x1800574a9  call    IkeGetTlsMmLuid
0x1800574ae  mov     r9, rax
0x1800574b1  mov     [rsp+1B0h+changeHandle], rbx
0x1800574b6  mov     edx, 22h ; '"'
0x1800574bb  lea     r8, WPP_c3da8f174801358a223b58501d21a257_Traceguids
0x1800574c2  mov     rcx, rdi
0x1800574c5  call    WPP_SF_iS
0x1800574ca  lea     rbx, WPP_GLOBAL_Control
0x1800574d1  mov     eax, cs:dword_180173278
0x1800574d7  cmp     eax, r14d
0x1800574da  jbe     short loc_18005753D
0x1800574dc  call    IkeGetTlsMmLuid
0x1800574e1  mov     [rbp+0B0h+var_100], rax
0x1800574e5  lea     rax, [rbp+0B0h+var_100]
0x1800574e9  mov     [rbp+0B0h+var_70], rax
0x1800574ed  mov     [rbp+0B0h+var_68], 8
0x1800574f5  call    IkeGetTlsPeerAddr
0x1800574fa  mov     rdx, rax
0x1800574fd  lea     rcx, [rbp+0B0h+var_60]
0x180057501  call    _tlgCreate1Sz_wchar_t
0x180057506  lea     rcx, aSubscribingFor_4; "Subscribing for QM V6 filter notificati"...
0x18005750d  mov     [rbp+0B0h+var_48], 2Bh ; '+'
0x180057515  lea     rax, [rbp+0B0h+var_90]
0x180057519  mov     [rbp+0B0h+var_50], rcx
0x18005751d  mov     [rsp+1B0h+var_188], rax
0x180057522  lea     rcx, dword_180173278
0x180057529  lea     rdx, byte_18014F05D
0x180057530  mov     dword ptr [rsp+1B0h+changeHandle], 5
0x180057538  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18005753d  mov     rcx, cs:gIkeExtGlobals
0x180057544  lea     r8, IkeProcessQMFilterChange; callback
0x18005754b  xor     r9d, r9d; context
0x18005754e  lea     rdx, [rbp+0B0h+subscription]; subscription
0x180057552  lea     rax, [rcx+0AE8h]
0x180057559  mov     rcx, [rcx+0AB0h]; engineHandle
0x180057560  mov     [rsp+1B0h+changeHandle], rax; changeHandle
0x180057565  call    cs:__imp_FwpmFilterSubscribeChanges0
0x18005756b  test    eax, eax
0x18005756d  jnz     loc_180057279
0x180057573  lea     rax, [rbp+0B0h+var_F8]
0x180057577  mov     dword ptr [rbp+0B0h+var_F8+8], 5
0x18005757e  mov     [rsp+1B0h+var_180.enumTemplate], rax
0x180057583  mov     [rsp+1B0h+var_180.flags], 2
  ... truncated ...
```
