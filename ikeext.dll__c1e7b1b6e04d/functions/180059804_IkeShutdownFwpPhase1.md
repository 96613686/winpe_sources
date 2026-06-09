# IkeShutdownFwpPhase1

- ea: `0x180059804`
- end: `0x18005b280`
- name: `IkeShutdownFwpPhase1`
- size: `6780`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180058100`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x180059804`
- `0x18005bc40`
- `0x18005bce4`

## import_xrefs

- `fwpuclnt!IPsecKeyModuleDelete0` at `0x180059928`
- `fwpuclnt!IPsecKeyModuleDelete0` at `0x180059ae4`
- `fwpuclnt!IPsecKeyModuleDelete0` at `0x180059ca0`
- `fwpuclnt!IPsecKeyModuleDelete0` at `0x180059928`
- `fwpuclnt!IPsecKeyModuleDelete0` at `0x180059ae4`
- `fwpuclnt!IPsecKeyModuleDelete0` at `0x180059ca0`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005a54c`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005a708`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005a8c4`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005aa80`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005ac3c`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005adf8`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005afb4`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005b170`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005a54c`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005a708`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005a8c4`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005aa80`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005ac3c`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005adf8`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005afb4`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005b170`
- `fwpuclnt!FwpmFilterUnsubscribeChanges0` at `0x180059e5c`
- `fwpuclnt!FwpmFilterUnsubscribeChanges0` at `0x18005a018`
- `fwpuclnt!FwpmFilterUnsubscribeChanges0` at `0x18005a1d4`
- `fwpuclnt!FwpmFilterUnsubscribeChanges0` at `0x18005a390`
- `fwpuclnt!FwpmFilterUnsubscribeChanges0` at `0x180059e5c`
- `fwpuclnt!FwpmFilterUnsubscribeChanges0` at `0x18005a018`
- `fwpuclnt!FwpmFilterUnsubscribeChanges0` at `0x18005a1d4`
- `fwpuclnt!FwpmFilterUnsubscribeChanges0` at `0x18005a390`

## pseudocode

```c
__int64 IkeShutdownFwpPhase1()
{
  __int64 v0; // rcx
  LPCRITICAL_SECTION v1; // rax
  __int64 v2; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v4; // rcx
  int TlsMmLuid; // eax
  __int64 v6; // rcx
  const WCHAR *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  int v10; // esi
  __int64 v11; // rdi
  __int64 v12; // rbx
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  const WCHAR *v16; // rax
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rdi
  __int64 v20; // rbx
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  const WCHAR *v24; // rax
  __int64 v25; // r8
  __int64 v26; // r9
  int v27; // esi
  __int64 v28; // rdi
  __int64 v29; // rbx
  __int64 v30; // rcx
  int v31; // eax
  __int64 v32; // rcx
  const WCHAR *v33; // rax
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 v36; // rdi
  __int64 v37; // rbx
  __int64 v38; // rcx
  int v39; // eax
  __int64 v40; // rcx
  const WCHAR *v41; // rax
  __int64 v42; // r8
  __int64 v43; // r9
  int v44; // esi
  __int64 v45; // rdi
  __int64 v46; // rbx
  __int64 v47; // rcx
  int v48; // eax
  __int64 v49; // rcx
  const WCHAR *v50; // rax
  __int64 v51; // r8
  __int64 v52; // r9
  __int64 v53; // rdi
  __int64 v54; // rbx
  __int64 v55; // rcx
  int v56; // eax
  __int64 v57; // rcx
  const WCHAR *v58; // rax
  __int64 v59; // r8
  __int64 v60; // r9
  DWORD v61; // esi
  __int64 v62; // rdi
  __int64 v63; // rbx
  __int64 v64; // rcx
  int v65; // eax
  __int64 v66; // rcx
  const WCHAR *v67; // rax
  __int64 v68; // r8
  __int64 v69; // r9
  __int64 v70; // rdi
  __int64 v71; // rbx
  __int64 v72; // rcx
  int v73; // eax
  __int64 v74; // rcx
  const WCHAR *v75; // rax
  __int64 v76; // r8
  __int64 v77; // r9
  DWORD v78; // esi
  __int64 v79; // rdi
  __int64 v80; // rbx
  __int64 v81; // rcx
  int v82; // eax
  __int64 v83; // rcx
  const WCHAR *v84; // rax
  __int64 v85; // r8
  __int64 v86; // r9
  __int64 v87; // rdi
  __int64 v88; // rbx
  __int64 v89; // rcx
  int v90; // eax
  __int64 v91; // rcx
  const WCHAR *v92; // rax
  __int64 v93; // r8
  __int64 v94; // r9
  DWORD v95; // esi
  __int64 v96; // rdi
  __int64 v97; // rbx
  __int64 v98; // rcx
  int v99; // eax
  __int64 v100; // rcx
  const WCHAR *v101; // rax
  __int64 v102; // r8
  __int64 v103; // r9
  __int64 v104; // rdi
  __int64 v105; // rbx
  __int64 v106; // rcx
  int v107; // eax
  __int64 v108; // rcx
  const WCHAR *v109; // rax
  __int64 v110; // r8
  __int64 v111; // r9
  DWORD v112; // esi
  __int64 v113; // rdi
  __int64 v114; // rbx
  __int64 v115; // rcx
  int v116; // eax
  __int64 v117; // rcx
  const WCHAR *v118; // rax
  __int64 v119; // r8
  __int64 v120; // r9
  __int64 v121; // rdi
  __int64 v122; // rbx
  __int64 v123; // rcx
  int v124; // eax
  __int64 v125; // rcx
  const WCHAR *v126; // rax
  __int64 v127; // r8
  __int64 v128; // r9
  DWORD v129; // esi
  __int64 v130; // rdi
  __int64 v131; // rbx
  __int64 v132; // rcx
  int v133; // eax
  __int64 v134; // rcx
  const WCHAR *v135; // rax
  __int64 v136; // r8
  __int64 v137; // r9
  __int64 v138; // rdi
  __int64 v139; // rbx
  __int64 v140; // rcx
  int v141; // eax
  __int64 v142; // rcx
  const WCHAR *v143; // rax
  __int64 v144; // r8
  __int64 v145; // r9
  DWORD v146; // esi
  __int64 v147; // rdi
  __int64 v148; // rbx
  __int64 v149; // rcx
  int v150; // eax
  __int64 v151; // rcx
  const WCHAR *v152; // rax
  __int64 v153; // r8
  __int64 v154; // r9
  __int64 v155; // rdi
  __int64 v156; // rbx
  __int64 v157; // rcx
  int v158; // eax
  __int64 v159; // rcx
  const WCHAR *v160; // rax
  __int64 v161; // r8
  __int64 v162; // r9
  DWORD v163; // esi
  __int64 v164; // rdi
  __int64 v165; // rbx
  __int64 v166; // rcx
  int v167; // eax
  __int64 v168; // rcx
  const WCHAR *v169; // rax
  __int64 v170; // r8
  __int64 v171; // r9
  __int64 v172; // rdi
  __int64 v173; // rbx
  __int64 v174; // rcx
  int v175; // eax
  __int64 v176; // rcx
  const WCHAR *v177; // rax
  __int64 v178; // r8
  __int64 v179; // r9
  DWORD v180; // esi
  __int64 v181; // rdi
  __int64 v182; // rbx
  __int64 v183; // rcx
  int v184; // eax
  __int64 v185; // rcx
  const WCHAR *v186; // rax
  __int64 v187; // r8
  __int64 v188; // r9
  __int64 v189; // rdi
  __int64 v190; // rbx
  __int64 v191; // rcx
  int v192; // eax
  __int64 v193; // rcx
  const WCHAR *v194; // rax
  __int64 v195; // r8
  __int64 v196; // r9
  DWORD v197; // esi
  __int64 v198; // rdi
  __int64 v199; // rbx
  __int64 v200; // rcx
  int v201; // eax
  __int64 v202; // rcx
  const WCHAR *v203; // rax
  __int64 v204; // r8
  __int64 v205; // r9
  __int64 v206; // rdi
  __int64 v207; // rbx
  __int64 v208; // rcx
  int v209; // eax
  __int64 v210; // rcx
  const WCHAR *v211; // rax
  __int64 v212; // r8
  __int64 v213; // r9
  DWORD v214; // esi
  __int64 v215; // rdi
  __int64 v216; // rbx
  __int64 v217; // rcx
  int v218; // eax
  __int64 v219; // rcx
  const WCHAR *v220; // rax
  __int64 v221; // r8
  __int64 v222; // r9
  __int64 v223; // rdi
  __int64 v224; // rbx
  __int64 v225; // rcx
  int v226; // eax
  __int64 v227; // rcx
  const WCHAR *v228; // rax
  __int64 v229; // r8
  __int64 v230; // r9
  DWORD v231; // esi
  __int64 v232; // rdi
  __int64 v233; // rbx
  __int64 v234; // rcx
  int v235; // eax
  __int64 v236; // rcx
  const WCHAR *v237; // rax
  __int64 v238; // r8
  __int64 v239; // r9
  __int64 v240; // rdi
  __int64 v241; // rbx
  __int64 v242; // rcx
  int v243; // eax
  __int64 v244; // rcx
  const WCHAR *v245; // rax
  __int64 v246; // r8
  __int64 v247; // r9
  __int64 v248; // rcx
  DWORD v249; // esi
  __int64 v250; // rdi
  __int64 v251; // rbx
  __int64 v252; // rcx
  int v253; // eax
  __int64 v254; // rcx
  const WCHAR *v255; // rax
  __int64 v256; // r8
  __int64 v257; // r9
  __int64 v259; // [rsp+28h] [rbp-71h]
  __int64 v260; // [rsp+30h] [rbp-69h] BYREF
  __int64 v261; // [rsp+38h] [rbp-61h] BYREF
  _BYTE v262[32]; // [rsp+40h] [rbp-59h] BYREF
  __int64 *v263; // [rsp+60h] [rbp-39h]
  __int64 v264; // [rsp+68h] [rbp-31h]
  _BYTE v265[16]; // [rsp+70h] [rbp-29h] BYREF
  const char *v266; // [rsp+80h] [rbp-19h]
  __int64 v267; // [rsp+88h] [rbp-11h]
  __int64 *v268; // [rsp+90h] [rbp-9h]
  __int64 v269; // [rsp+98h] [rbp-1h]

  TraceLogHelper("IkeShutdownFwpPhase1", 1);
  v1 = gIkeExtGlobals;
  if ( gIkeExtGlobals[68].LockSemaphore )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v2 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      TlsPeerAddr = IkeGetTlsPeerAddr(v0);
      TlsMmLuid = IkeGetTlsMmLuid(v4);
      WPP_SF_iS(v2, 46, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, TlsMmLuid, TlsPeerAddr);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v261 = IkeGetTlsMmLuid(v0);
      v263 = &v261;
      v264 = 8;
      v7 = (const WCHAR *)IkeGetTlsPeerAddr(v6);
      tlgCreate1Sz_wchar_t((__int64)v265, v7);
      v267 = 32;
      v266 = "Deregistering IKE keying module";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_18014ED4F,
        v8,
        v9,
        5,
        (__int64)v262);
    }
    v10 = IPsecKeyModuleDelete0(gIkeExtGlobals[68].OwningThread, gIkeExtGlobals[68].LockSemaphore);
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v11 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v12 = IkeGetTlsPeerAddr(v0);
        v14 = IkeGetTlsMmLuid(v13);
        LODWORD(v259) = v10;
        WPP_SF_iSL(v11, 47, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v14, v12, v259);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v260 = IkeGetTlsMmLuid(v0);
        v263 = &v260;
        v264 = 8;
        v16 = (const WCHAR *)IkeGetTlsPeerAddr(v15);
        tlgCreate1Sz_wchar_t((__int64)v265, v16);
        v267 = 39;
        v268 = &v261;
        v266 = "Deregistering IKE keying module failed";
        LODWORD(v261) = v10;
        v269 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (__int64)&dword_180173278,
          (unsigned __int8 *)word_18014ED02,
          v17,
          v18,
          6,
          (__int64)v262);
      }
    }
    gIkeExtGlobals[68].LockSemaphore = 0;
    v1 = gIkeExtGlobals;
  }
  if ( v1[68].SpinCount )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v19 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v20 = IkeGetTlsPeerAddr(v0);
      v22 = IkeGetTlsMmLuid(v21);
      WPP_SF_iS(v19, 48, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v22, v20);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v260 = IkeGetTlsMmLuid(v0);
      v263 = &v260;
      v264 = 8;
      v24 = (const WCHAR *)IkeGetTlsPeerAddr(v23);
      tlgCreate1Sz_wchar_t((__int64)v265, v24);
      v267 = 36;
      v266 = "Deregistering Authip keying modulee";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_18014ECBF,
        v25,
        v26,
        5,
        (__int64)v262);
    }
    v27 = IPsecKeyModuleDelete0(gIkeExtGlobals[68].OwningThread, gIkeExtGlobals[68].SpinCount);
    if ( v27 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v28 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v29 = IkeGetTlsPeerAddr(v0);
        v31 = IkeGetTlsMmLuid(v30);
        LODWORD(v259) = v27;
        WPP_SF_iSL(v28, 49, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v31, v29, v259);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v260 = IkeGetTlsMmLuid(v0);
        v263 = &v260;
        v264 = 8;
        v33 = (const WCHAR *)IkeGetTlsPeerAddr(v32);
        tlgCreate1Sz_wchar_t((__int64)v265, v33);
        v267 = 42;
        v268 = &v261;
        v266 = "Deregistering Authip keying module failed";
        LODWORD(v261) = v27;
        v269 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (__int64)&dword_180173278,
          (unsigned __int8 *)word_18014EC72,
          v34,
          v35,
          6,
          (__int64)v262);
      }
    }
    gIkeExtGlobals[68].SpinCount = 0;
    v1 = gIkeExtGlobals;
  }
  if ( v1[69].DebugInfo )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v36 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v37 = IkeGetTlsPeerAddr(v0);
      v39 = IkeGetTlsMmLuid(v38);
      WPP_SF_iS(v36, 50, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v39, v37);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v260 = IkeGetTlsMmLuid(v0);
      v263 = &v260;
      v264 = 8;
      v41 = (const WCHAR *)IkeGetTlsPeerAddr(v40);
      tlgCreate1Sz_wchar_t((__int64)v265, v41);
      v267 = 34;
      v266 = "Deregistering IKEv2 keying module";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_18014EC2F,
        v42,
        v43,
        5,
        (__int64)v262);
    }
    v44 = IPsecKeyModuleDelete0(gIkeExtGlobals[68].OwningThread, gIkeExtGlobals[69].DebugInfo);
    if ( v44 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v45 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v46 = IkeGetTlsPeerAddr(v0);
        v48 = IkeGetTlsMmLuid(v47);
        LODWORD(v259) = v44;
        WPP_SF_iSL(v45, 51, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v48, v46, v259);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v260 = IkeGetTlsMmLuid(v0);
        v263 = &v260;
        v264 = 8;
        v50 = (const WCHAR *)IkeGetTlsPeerAddr(v49);
        tlgCreate1Sz_wchar_t((__int64)v265, v50);
        v267 = 41;
        v268 = &v261;
        v266 = "Deregistering IKEv2 keying module failed";
        LODWORD(v261) = v44;
        v269 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (__int64)&dword_180173278,
          (unsigned __int8 *)word_18014EBE2,
          v51,
          v52,
          6,
          (__int64)v262);
      }
    }
    gIkeExtGlobals[69].DebugInfo = 0;
    v1 = gIkeExtGlobals;
  }
  if ( *(_QWORD *)&v1[69].LockCount )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v53 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v54 = IkeGetTlsPeerAddr(v0);
      v56 = IkeGetTlsMmLuid(v55);
      WPP_SF_iS(v53, 52, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v56, v54);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v260 = IkeGetTlsMmLuid(v0);
      v263 = &v260;
      v264 = 8;
      v58 = (const WCHAR *)IkeGetTlsPeerAddr(v57);
      tlgCreate1Sz_wchar_t((__int64)v265, v58);
      v267 = 47;
      v266 = "Unsubscribing MM V4 filter change notification";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_18014EB9F,
        v59,
        v60,
        5,
        (__int64)v262);
    }
    v61 = FwpmFilterUnsubscribeChanges0(gIkeExtGlobals[68].OwningThread, *(HANDLE *)&gIkeExtGlobals[69].LockCount);
    if ( v61 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v62 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v63 = IkeGetTlsPeerAddr(v0);
        v65 = IkeGetTlsMmLuid(v64);
        LODWORD(v259) = v61;
        WPP_SF_iSL(v62, 53, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v65, v63, v259);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v260 = IkeGetTlsMmLuid(v0);
        v263 = &v260;
        v264 = 8;
        v67 = (const WCHAR *)IkeGetTlsPeerAddr(v66);
        tlgCreate1Sz_wchar_t((__int64)v265, v67);
        v267 = 54;
        v268 = &v261;
        v266 = "Unsubscribing MM V4 filter change notification failed";
        LODWORD(v261) = v61;
        v269 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (__int64)&dword_180173278,
          (unsigned __int8 *)word_18014EB52,
          v68,
          v69,
          6,
          (__int64)v262);
      }
    }
    *(_QWORD *)&gIkeExtGlobals[69].LockCount = 0;
    v1 = gIkeExtGlobals;
  }
  if ( v1[69].LockSemaphore )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v70 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v71 = IkeGetTlsPeerAddr(v0);
      v73 = IkeGetTlsMmLuid(v72);
      WPP_SF_iS(v70, 54, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v73, v71);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v260 = IkeGetTlsMmLuid(v0);
      v263 = &v260;
      v264 = 8;
      v75 = (const WCHAR *)IkeGetTlsPeerAddr(v74);
      tlgCreate1Sz_wchar_t((__int64)v265, v75);
      v267 = 47;
      v266 = "Unsubscribing MM V6 filter change notification";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_18014EB0F,
        v76,
        v77,
        5,
        (__int64)v262);
    }
    v78 = FwpmFilterUnsubscribeChanges0(gIkeExtGlobals[68].OwningThread, gIkeExtGlobals[69].LockSemaphore);
    if ( v78 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v79 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v80 = IkeGetTlsPeerAddr(v0);
        v82 = IkeGetTlsMmLuid(v81);
        LODWORD(v259) = v78;
        WPP_SF_iSL(v79, 55, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v82, v80, v259);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v260 = IkeGetTlsMmLuid(v0);
        v263 = &v260;
        v264 = 8;
        v84 = (const WCHAR *)IkeGetTlsPeerAddr(v83);
        tlgCreate1Sz_wchar_t((__int64)v265, v84);
        v267 = 54;
        v268 = &v261;
        v266 = "Unsubscribing MM V6 filter change notification failed";
        LODWORD(v261) = v78;
        v269 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (__int64)&dword_180173278,
          (unsigned __int8 *)word_18014EAC2,
          v85,
          v86,
          6,
          (__int64)v262);
      }
    }
    gIkeExtGlobals[69].LockSemaphore = 0;
    v1 = gIkeExtGlobals;
  }
  if ( v1[69].OwningThread )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v87 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v88 = IkeGetTlsPeerAddr(v0);
      v90 = IkeGetTlsMmLuid(v89);
      WPP_SF_iS(v87, 56, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v90, v88);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v260 = IkeGetTlsMmLuid(v0);
      v263 = &v260;
      v264 = 8;
      v92 = (const WCHAR *)IkeGetTlsPeerAddr(v91);
      tlgCreate1Sz_wchar_t((__int64)v265, v92);
      v267 = 47;
      v266 = "Unsubscribing QM V4 filter change notification";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_18014EA7F,
        v93,
        v94,
        5,
        (__int64)v262);
    }
    v95 = FwpmFilterUnsubscribeChanges0(gIkeExtGlobals[68].OwningThread, gIkeExtGlobals[69].OwningThread);
    if ( v95 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v96 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v97 = IkeGetTlsPeerAddr(v0);
        v99 = IkeGetTlsMmLuid(v98);
        LODWORD(v259) = v95;
        WPP_SF_iSL(v96, 57, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v99, v97, v259);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v260 = IkeGetTlsMmLuid(v0);
        v263 = &v260;
        v264 = 8;
        v101 = (const WCHAR *)IkeGetTlsPeerAddr(v100);
        tlgCreate1Sz_wchar_t((__int64)v265, v101);
        v267 = 54;
        v268 = &v261;
        v266 = "Unsubscribing QM V4 filter change notification failed";
        LODWORD(v261) = v95;
        v269 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (__int64)&dword_180173278,
          (unsigned __int8 *)word_18014EA32,
          v102,
          v103,
          6,
          (__int64)v262);
      }
    }
    gIkeExtGlobals[69].OwningThread = 0;
    v1 = gIkeExtGlobals;
  }
  if ( v1[69].SpinCount )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v104 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v105 = IkeGetTlsPeerAddr(v0);
      v107 = IkeGetTlsMmLuid(v106);
      WPP_SF_iS(v104, 58, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v107, v105);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v260 = IkeGetTlsMmLuid(v0);
      v263 = &v260;
      v264 = 8;
      v109 = (const WCHAR *)IkeGetTlsPeerAddr(v108);
      tlgCreate1Sz_wchar_t((__int64)v265, v109);
      v267 = 47;
      v266 = "Unsubscribing QM V6 filter change notification";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_18014E9EF,
        v110,
        v111,
        5,
        (__int64)v262);
    }
    v112 = FwpmFilterUnsubscribeChanges0(gIkeExtGlobals[68].OwningThread, (HANDLE)gIkeExtGlobals[69].SpinCount);
    if ( v112 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v113 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v114 = IkeGetTlsPeerAddr(v0);
        v116 = IkeGetTlsMmLuid(v115);
        LODWORD(v259) = v112;
        WPP_SF_iSL(v113, 59, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v116, v114, v259);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v260 = IkeGetTlsMmLuid(v0);
        v263 = &v260;
        v264 = 8;
        v118 = (const WCHAR *)IkeGetTlsPeerAddr(v117);
        tlgCreate1Sz_wchar_t((__int64)v265, v118);
        v267 = 54;
        v268 = &v261;
        v266 = "Unsubscribing QM V6 filter change notification failed";
        LODWORD(v261) = v112;
        v269 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (__int64)&dword_180173278,
          (unsigned __int8 *)word_18014E9A2,
          v119,
          v120,
          6,
          (__int64)v262);
      }
    }
    gIkeExtGlobals[69].SpinCount = 0;
    v1 = gIkeExtGlobals;
  }
  if ( v1[70].DebugInfo )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v121 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v122 = IkeGetTlsPeerAddr(v0);
      v124 = IkeGetTlsMmLuid(v123);
      WPP_SF_iS(v121, 60, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v124, v122);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v260 = IkeGetTlsMmLuid(v0);
      v263 = &v260;
      v264 = 8;
      v126 = (const WCHAR *)IkeGetTlsPeerAddr(v125);
      tlgCreate1Sz_wchar_t((__int64)v265, v126);
      v267 = 48;
      v266 = "Unsubscribing IKE MM policy change notification";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_18014E95F,
        v127,
        v128,
        5,
        (__int64)v262);
    }
    v129 = FwpmProviderContextUnsubscribeChanges0(gIkeExtGlobals[68].OwningThread, gIkeExtGlobals[70].DebugInfo);
    if ( v129 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v130 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v131 = IkeGetTlsPeerAddr(v0);
        v133 = IkeGetTlsMmLuid(v132);
        LODWORD(v259) = v129;
        WPP_SF_iSL(v130, 61, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v133, v131, v259);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v260 = IkeGetTlsMmLuid(v0);
        v263 = &v260;
        v264 = 8;
        v135 = (const WCHAR *)IkeGetTlsPeerAddr(v134);
        tlgCreate1Sz_wchar_t((__int64)v265, v135);
        v267 = 55;
        v268 = &v261;
        v266 = "Unsubscribing IKE MM policy change notification failed";
        LODWORD(v261) = v129;
        v269 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (__int64)&dword_180173278,
          (unsigned __int8 *)word_18014E912,
          v136,
          v137,
          6,
          (__int64)v262);
      }
    }
    gIkeExtGlobals[70].DebugInfo = 0;
    v1 = gIkeExtGlobals;
  }
  if ( v1[70].LockSemaphore )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v138 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v139 = IkeGetTlsPeerAddr(v0);
      v141 = IkeGetTlsMmLuid(v140);
      WPP_SF_iS(v138, 62, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v141, v139);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v260 = IkeGetTlsMmLuid(v0);
      v263 = &v260;
      v264 = 8;
      v143 = (const WCHAR *)IkeGetTlsPeerAddr(v142);
      tlgCreate1Sz_wchar_t((__int64)v265, v143);
      v267 = 51;
      v266 = "Unsubscribing Authip MM policy change notification";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_18014E8CF,
        v144,
        v145,
        5,
        (__int64)v262);
    }
    v146 = FwpmProviderContextUnsubscribeChanges0(gIkeExtGlobals[68].OwningThread, gIkeExtGlobals[70].LockSemaphore);
    if ( v146 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v147 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v148 = IkeGetTlsPeerAddr(v0);
        v150 = IkeGetTlsMmLuid(v149);
        LODWORD(v259) = v146;
        WPP_SF_iSL(v147, 63, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v150, v148, v259);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v260 = IkeGetTlsMmLuid(v0);
        v263 = &v260;
        v264 = 8;
        v152 = (const WCHAR *)IkeGetTlsPeerAddr(v151);
        tlgCreate1Sz_wchar_t((__int64)v265, v152);
        v267 = 58;
        v268 = &v261;
        v266 = "Unsubscribing Authip MM policy change notification failed";
        LODWORD(v261) = v146;
        v269 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (__int64)&dword_180173278,
          (unsigned __int8 *)word_18014E882,
          v153,
          v154,
          6,
          (__int64)v262);
      }
    }
    gIkeExtGlobals[70].LockSemaphore = 0;
    v1 = gIkeExtGlobals;
  }
  if ( v1[70].SpinCount )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v155 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v156 = IkeGetTlsPeerAddr(v0);
      v158 = IkeGetTlsMmLuid(v157);
      WPP_SF_iS(v155, 64, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v158, v156);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v260 = IkeGetTlsMmLuid(v0);
      v263 = &v260;
      v264 = 8;
      v160 = (const WCHAR *)IkeGetTlsPeerAddr(v159);
      tlgCreate1Sz_wchar_t((__int64)v265, v160);
      v267 = 50;
      v266 = "Unsubscribing IKEv2 MM policy change notification";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_18014E83F,
        v161,
        v162,
        5,
        (__int64)v262);
    }
    v163 = FwpmProviderContextUnsubscribeChanges0(gIkeExtGlobals[68].OwningThread, (HANDLE)gIkeExtGlobals[70].SpinCount);
    if ( v163 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v164 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v165 = IkeGetTlsPeerAddr(v0);
        v167 = IkeGetTlsMmLuid(v166);
        LODWORD(v259) = v163;
        WPP_SF_iSL(v164, 65, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v167, v165, v259);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v260 = IkeGetTlsMmLuid(v0);
        v263 = &v260;
        v264 = 8;
        v169 = (const WCHAR *)IkeGetTlsPeerAddr(v168);
        tlgCreate1Sz_wchar_t((__int64)v265, v169);
        v267 = 57;
        v268 = &v261;
        v266 = "Unsubscribing IKEv2 MM policy change notification failed";
        LODWORD(v261) = v163;
        v269 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (__int64)&dword_180173278,
          (unsigned __int8 *)word_18014E7F2,
          v170,
          v171,
          6,
          (__int64)v262);
      }
    }
    gIkeExtGlobals[70].SpinCount = 0;
    v1 = gIkeExtGlobals;
  }
  if ( *(_QWORD *)&v1[70].LockCount )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v172 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v173 = IkeGetTlsPeerAddr(v0);
      v175 = IkeGetTlsMmLuid(v174);
      WPP_SF_iS(v172, 66, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v175, v173);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v260 = IkeGetTlsMmLuid(v0);
      v263 = &v260;
      v264 = 8;
      v177 = (const WCHAR *)IkeGetTlsPeerAddr(v176);
      tlgCreate1Sz_wchar_t((__int64)v265, v177);
      v267 = 54;
      v266 = "Unsubscribing IKE QM Trans policy change notification";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_18014E7AF,
        v178,
        v179,
        5,
        (__int64)v262);
    }
    v180 = FwpmProviderContextUnsubscribeChanges0(
             gIkeExtGlobals[68].OwningThread,
             *(HANDLE *)&gIkeExtGlobals[70].LockCount);
    if ( v180 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v181 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v182 = IkeGetTlsPeerAddr(v0);
        v184 = IkeGetTlsMmLuid(v183);
        LODWORD(v259) = v180;
        WPP_SF_iSL(v181, 67, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v184, v182, v259);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v260 = IkeGetTlsMmLuid(v0);
        v263 = &v260;
        v264 = 8;
        v186 = (const WCHAR *)IkeGetTlsPeerAddr(v185);
        tlgCreate1Sz_wchar_t((__int64)v265, v186);
        v267 = 61;
        v268 = &v261;
        v266 = "Unsubscribing IKE QM Trans policy change notification failed";
        LODWORD(v261) = v180;
        v269 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (__int64)&dword_180173278,
          (unsigned __int8 *)word_18014E762,
          v187,
          v188,
          6,
          (__int64)v262);
      }
    }
    *(_QWORD *)&gIkeExtGlobals[70].LockCount = 0;
    v1 = gIkeExtGlobals;
  }
  if ( v1[70].OwningThread )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v189 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v190 = IkeGetTlsPeerAddr(v0);
      v192 = IkeGetTlsMmLuid(v191);
      WPP_SF_iS(v189, 68, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v192, v190);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v260 = IkeGetTlsMmLuid(v0);
      v263 = &v260;
      v264 = 8;
      v194 = (const WCHAR *)IkeGetTlsPeerAddr(v193);
      tlgCreate1Sz_wchar_t((__int64)v265, v194);
      v267 = 55;
      v266 = "Unsubscribing IKE QM Tunnel policy change notification";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_18014E71F,
        v195,
        v196,
        5,
        (__int64)v262);
    }
    v197 = FwpmProviderContextUnsubscribeChanges0(gIkeExtGlobals[68].OwningThread, gIkeExtGlobals[70].OwningThread);
    if ( v197 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v198 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v199 = IkeGetTlsPeerAddr(v0);
        v201 = IkeGetTlsMmLuid(v200);
        LODWORD(v259) = v197;
        WPP_SF_iSL(v198, 69, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v201, v199, v259);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v260 = IkeGetTlsMmLuid(v0);
        v263 = &v260;
        v264 = 8;
        v203 = (const WCHAR *)IkeGetTlsPeerAddr(v202);
        tlgCreate1Sz_wchar_t((__int64)v265, v203);
        v267 = 62;
        v268 = &v261;
        v266 = "Unsubscribing IKE QM Tunnel policy change notification failed";
        LODWORD(v261) = v197;
        v269 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (__int64)&dword_180173278,
          (unsigned __int8 *)word_18014E6D2,
          v204,
          v205,
          6,
          (__int64)v262);
      }
    }
    gIkeExtGlobals[70].OwningThread = 0;
    v1 = gIkeExtGlobals;
  }
  if ( v1[71].DebugInfo )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v206 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v207 = IkeGetTlsPeerAddr(v0);
      v209 = IkeGetTlsMmLuid(v208);
      WPP_SF_iS(v206, 70, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v209, v207);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v260 = IkeGetTlsMmLuid(v0);
      v263 = &v260;
      v264 = 8;
      v211 = (const WCHAR *)IkeGetTlsPeerAddr(v210);
      tlgCreate1Sz_wchar_t((__int64)v265, v211);
      v267 = 57;
      v266 = "Unsubscribing Authip QM Trans policy change notification";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_18014E68F,
        v212,
        v213,
        5,
        (__int64)v262);
    }
    v214 = FwpmProviderContextUnsubscribeChanges0(gIkeExtGlobals[68].OwningThread, gIkeExtGlobals[71].DebugInfo);
    if ( v214 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v215 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v216 = IkeGetTlsPeerAddr(v0);
        v218 = IkeGetTlsMmLuid(v217);
        LODWORD(v259) = v214;
        WPP_SF_iSL(v215, 71, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v218, v216, v259);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v260 = IkeGetTlsMmLuid(v0);
        v263 = &v260;
        v264 = 8;
        v220 = (const WCHAR *)IkeGetTlsPeerAddr(v219);
        tlgCreate1Sz_wchar_t((__int64)v265, v220);
        v267 = 64;
        v268 = &v261;
        v266 = "Unsubscribing Authip QM Trans policy change notification failed";
        LODWORD(v261) = v214;
        v269 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (__int64)&dword_180173278,
          (unsigned __int8 *)word_18014E642,
          v221,
          v222,
          6,
          (__int64)v262);
      }
    }
    gIkeExtGlobals[71].DebugInfo = 0;
    v1 = gIkeExtGlobals;
  }
  if ( *(_QWORD *)&v1[71].LockCount )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v223 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v224 = IkeGetTlsPeerAddr(v0);
      v226 = IkeGetTlsMmLuid(v225);
      WPP_SF_iS(v223, 72, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v226, v224);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v260 = IkeGetTlsMmLuid(v0);
      v263 = &v260;
      v264 = 8;
      v228 = (const WCHAR *)IkeGetTlsPeerAddr(v227);
      tlgCreate1Sz_wchar_t((__int64)v265, v228);
      v267 = 58;
      v266 = "Unsubscribing Authip QM Tunnel policy change notification";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_18014E5FF,
        v229,
        v230,
        5,
        (__int64)v262);
    }
    v231 = FwpmProviderContextUnsubscribeChanges0(
             gIkeExtGlobals[68].OwningThread,
             *(HANDLE *)&gIkeExtGlobals[71].LockCount);
    if ( v231 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v232 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v233 = IkeGetTlsPeerAddr(v0);
        v235 = IkeGetTlsMmLuid(v234);
        LODWORD(v259) = v231;
        WPP_SF_iSL(v232, 73, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v235, v233, v259);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v260 = IkeGetTlsMmLuid(v0);
        v263 = &v260;
        v264 = 8;
        v237 = (const WCHAR *)IkeGetTlsPeerAddr(v236);
        tlgCreate1Sz_wchar_t((__int64)v265, v237);
        v267 = 65;
        v268 = &v261;
        v266 = "Unsubscribing Authip QM Tunnel policy change notification failed";
        LODWORD(v261) = v231;
        v269 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (__int64)&dword_180173278,
          (unsigned __int8 *)word_18014E5B2,
          v238,
          v239,
          6,
          (__int64)v262);
      }
    }
    *(_QWORD *)&gIkeExtGlobals[71].LockCount = 0;
    v1 = gIkeExtGlobals;
  }
  if ( v1[71].OwningThread )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v240 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v241 = IkeGetTlsPeerAddr(v0);
      v243 = IkeGetTlsMmLuid(v242);
      WPP_SF_iS(v240, 74, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v243, v241);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v260 = IkeGetTlsMmLuid(v0);
      v263 = &v260;
      v264 = 8;
      v245 = (const WCHAR *)IkeGetTlsPeerAddr(v244);
      tlgCreate1Sz_wchar_t((__int64)v265, v245);
      v267 = 57;
      v266 = "Unsubscribing IKEv2 QM Tunnel policy change notification";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_18014E56F,
        v246,
        v247,
        5,
        (__int64)v262);
    }
    v249 = FwpmProviderContextUnsubscribeChanges0(gIkeExtGlobals[68].OwningThread, gIkeExtGlobals[71].OwningThread);
    if ( v249 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v250 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v251 = IkeGetTlsPeerAddr(v248);
        v253 = IkeGetTlsMmLuid(v252);
        LODWORD(v259) = v249;
        WPP_SF_iSL(v250, 75, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v253, v251, v259);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v260 = IkeGetTlsMmLuid(v248);
        v263 = &v260;
        v264 = 8;
        v255 = (const WCHAR *)IkeGetTlsPeerAddr(v254);
        tlgCreate1Sz_wchar_t((__int64)v265, v255);
        v267 = 64;
        v268 = &v261;
        v266 = "Unsubscribing IKEv2 QM Tunnel policy change notification failed";
        LODWORD(v261) = v249;
        v269 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (__int64)&dword_180173278,
          (unsigned __int8 *)word_18014E522,
          v256,
          v257,
          6,
          (__int64)v262);
      }
    }
    gIkeExtGlobals[71].OwningThread = 0;
  }
  return TraceLogHelper("IkeShutdownFwpPhase1", 0);
}

```

## disassembly

```asm
0x180059804  push    rbp
0x180059806  push    rbx
0x180059807  push    rsi
0x180059808  push    rdi
0x180059809  push    r12
0x18005980b  push    r13
0x18005980d  push    r14
0x18005980f  push    r15
0x180059811  lea     rbp, [rsp-1Fh]
0x180059816  sub     rsp, 0B8h
0x18005981d  mov     rax, cs:__security_cookie
0x180059824  xor     rax, rsp
0x180059827  mov     [rbp+57h+var_50], rax
0x18005982b  mov     edx, 1
0x180059830  lea     rcx, aIkeshutdownfwp_0; "IkeShutdownFwpPhase1"
0x180059837  call    TraceLogHelper
0x18005983c  mov     rax, cs:gIkeExtGlobals
0x180059843  lea     r12, WPP_GLOBAL_Control
0x18005984a  xor     r14d, r14d
0x18005984d  mov     r15d, 4
0x180059853  mov     r13b, 10h
0x180059856  cmp     [rax+0AB8h], r14
0x18005985d  jz      loc_180059A11
0x180059863  mov     rdi, cs:WPP_GLOBAL_Control
0x18005986a  cmp     rdi, r12
0x18005986d  jz      short loc_1800598A7
0x18005986f  cmp     [rdi+19h], r15b
0x180059873  jb      short loc_1800598A7
0x180059875  test    [rdi+1Ch], r13b
0x180059879  jz      short loc_1800598A7
0x18005987b  mov     rdi, [rdi+10h]
0x18005987f  call    IkeGetTlsPeerAddr
0x180059884  mov     rbx, rax
0x180059887  call    IkeGetTlsMmLuid
0x18005988c  mov     r9, rax
0x18005988f  mov     [rsp+0F0h+var_D0], rbx
0x180059894  lea     edx, [r15+2Ah]
0x180059898  mov     rcx, rdi
0x18005989b  lea     r8, WPP_c3da8f174801358a223b58501d21a257_Traceguids
0x1800598a2  call    WPP_SF_iS
0x1800598a7  mov     eax, cs:dword_180173278
0x1800598ad  cmp     eax, r15d
0x1800598b0  jbe     short loc_180059913
0x1800598b2  call    IkeGetTlsMmLuid
0x1800598b7  mov     [rbp+57h+var_B8], rax
0x1800598bb  lea     rax, [rbp+57h+var_B8]
0x1800598bf  mov     [rbp+57h+var_90], rax
0x1800598c3  mov     [rbp+57h+var_88], 8
0x1800598cb  call    IkeGetTlsPeerAddr
0x1800598d0  mov     rdx, rax
0x1800598d3  lea     rcx, [rbp+57h+var_80]
0x1800598d7  call    _tlgCreate1Sz_wchar_t
0x1800598dc  lea     rcx, aDeregisteringI_0; "Deregistering IKE keying module"
0x1800598e3  mov     [rbp+57h+var_68], 20h ; ' '
0x1800598eb  lea     rax, [rbp+57h+var_B0]
0x1800598ef  mov     [rbp+57h+var_70], rcx
0x1800598f3  mov     [rsp+0F0h+var_C8], rax
0x1800598f8  lea     rcx, dword_180173278
0x1800598ff  lea     rdx, byte_18014ED4F
0x180059906  mov     dword ptr [rsp+0F0h+var_D0], 5
0x18005990e  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180059913  mov     rcx, cs:gIkeExtGlobals
0x18005991a  mov     rdx, [rcx+0AB8h]
0x180059921  mov     rcx, [rcx+0AB0h]
0x180059928  call    cs:__imp_IPsecKeyModuleDelete0
0x18005992e  mov     esi, eax
0x180059930  test    eax, eax
0x180059932  jz      loc_1800599FC
0x180059938  mov     rdi, cs:WPP_GLOBAL_Control
0x18005993f  cmp     rdi, r12
0x180059942  jz      short loc_180059981
0x180059944  cmp     [rdi+19h], r15b
0x180059948  jb      short loc_180059981
0x18005994a  test    [rdi+1Ch], r13b
0x18005994e  jz      short loc_180059981
0x180059950  mov     rdi, [rdi+10h]
0x180059954  call    IkeGetTlsPeerAddr
0x180059959  mov     rbx, rax
0x18005995c  call    IkeGetTlsMmLuid
0x180059961  mov     r9, rax
0x180059964  mov     dword ptr [rsp+0F0h+var_C8], esi
0x180059968  mov     edx, 2Fh ; '/'
0x18005996d  mov     [rsp+0F0h+var_D0], rbx
0x180059972  lea     r8, WPP_c3da8f174801358a223b58501d21a257_Traceguids
0x180059979  mov     rcx, rdi
0x18005997c  call    WPP_SF_iSL
0x180059981  mov     eax, cs:dword_180173278
0x180059987  cmp     eax, r15d
0x18005998a  jbe     short loc_1800599FC
0x18005998c  call    IkeGetTlsMmLuid
0x180059991  mov     [rbp+57h+var_C0], rax
0x180059995  lea     rax, [rbp+57h+var_C0]
0x180059999  mov     [rbp+57h+var_90], rax
0x18005999d  mov     [rbp+57h+var_88], 8
0x1800599a5  call    IkeGetTlsPeerAddr
0x1800599aa  mov     rdx, rax
0x1800599ad  lea     rcx, [rbp+57h+var_80]
0x1800599b1  call    _tlgCreate1Sz_wchar_t
0x1800599b6  lea     rax, [rbp+57h+var_B8]
0x1800599ba  mov     [rbp+57h+var_68], 27h ; '''
0x1800599c2  mov     [rbp+57h+var_60], rax
0x1800599c6  lea     rcx, aDeregisteringI_2; "Deregistering IKE keying module failed"
0x1800599cd  lea     rax, [rbp+57h+var_B0]
0x1800599d1  mov     [rbp+57h+var_70], rcx
0x1800599d5  mov     [rsp+0F0h+var_C8], rax
0x1800599da  lea     rdx, word_18014ED02
0x1800599e1  lea     rcx, dword_180173278
0x1800599e8  mov     dword ptr [rsp+0F0h+var_D0], 6
0x1800599f0  mov     dword ptr [rbp+57h+var_B8], esi
0x1800599f3  mov     [rbp+57h+var_58], r15
0x1800599f7  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1800599fc  mov     rax, cs:gIkeExtGlobals
0x180059a03  mov     [rax+0AB8h], r14
0x180059a0a  mov     rax, cs:gIkeExtGlobals
0x180059a11  cmp     [rax+0AC0h], r14
0x180059a18  jz      loc_180059BCD
0x180059a1e  mov     rdi, cs:WPP_GLOBAL_Control
0x180059a25  cmp     rdi, r12
0x180059a28  jz      short loc_180059A63
0x180059a2a  cmp     [rdi+19h], r15b
0x180059a2e  jb      short loc_180059A63
0x180059a30  test    [rdi+1Ch], r13b
0x180059a34  jz      short loc_180059A63
0x180059a36  mov     rdi, [rdi+10h]
0x180059a3a  call    IkeGetTlsPeerAddr
0x180059a3f  mov     rbx, rax
0x180059a42  call    IkeGetTlsMmLuid
0x180059a47  mov     r9, rax
0x180059a4a  mov     [rsp+0F0h+var_D0], rbx
0x180059a4f  mov     edx, 30h ; '0'
0x180059a54  lea     r8, WPP_c3da8f174801358a223b58501d21a257_Traceguids
0x180059a5b  mov     rcx, rdi
0x180059a5e  call    WPP_SF_iS
0x180059a63  mov     eax, cs:dword_180173278
0x180059a69  cmp     eax, r15d
0x180059a6c  jbe     short loc_180059ACF
0x180059a6e  call    IkeGetTlsMmLuid
0x180059a73  mov     [rbp+57h+var_C0], rax
0x180059a77  lea     rax, [rbp+57h+var_C0]
0x180059a7b  mov     [rbp+57h+var_90], rax
0x180059a7f  mov     [rbp+57h+var_88], 8
0x180059a87  call    IkeGetTlsPeerAddr
0x180059a8c  mov     rdx, rax
0x180059a8f  lea     rcx, [rbp+57h+var_80]
0x180059a93  call    _tlgCreate1Sz_wchar_t
0x180059a98  lea     rcx, aDeregisteringA; "Deregistering Authip keying modulee"
0x180059a9f  mov     [rbp+57h+var_68], 24h ; '$'
0x180059aa7  lea     rax, [rbp+57h+var_B0]
0x180059aab  mov     [rbp+57h+var_70], rcx
0x180059aaf  mov     [rsp+0F0h+var_C8], rax
0x180059ab4  lea     rcx, dword_180173278
0x180059abb  lea     rdx, byte_18014ECBF
0x180059ac2  mov     dword ptr [rsp+0F0h+var_D0], 5
0x180059aca  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180059acf  mov     rcx, cs:gIkeExtGlobals
0x180059ad6  mov     rdx, [rcx+0AC0h]
0x180059add  mov     rcx, [rcx+0AB0h]
0x180059ae4  call    cs:__imp_IPsecKeyModuleDelete0
0x180059aea  mov     esi, eax
0x180059aec  test    eax, eax
0x180059aee  jz      loc_180059BB8
0x180059af4  mov     rdi, cs:WPP_GLOBAL_Control
0x180059afb  cmp     rdi, r12
0x180059afe  jz      short loc_180059B3D
0x180059b00  cmp     [rdi+19h], r15b
0x180059b04  jb      short loc_180059B3D
0x180059b06  test    [rdi+1Ch], r13b
0x180059b0a  jz      short loc_180059B3D
0x180059b0c  mov     rdi, [rdi+10h]
0x180059b10  call    IkeGetTlsPeerAddr
0x180059b15  mov     rbx, rax
0x180059b18  call    IkeGetTlsMmLuid
0x180059b1d  mov     r9, rax
0x180059b20  mov     dword ptr [rsp+0F0h+var_C8], esi
0x180059b24  mov     edx, 31h ; '1'
0x180059b29  mov     [rsp+0F0h+var_D0], rbx
0x180059b2e  lea     r8, WPP_c3da8f174801358a223b58501d21a257_Traceguids
0x180059b35  mov     rcx, rdi
0x180059b38  call    WPP_SF_iSL
0x180059b3d  mov     eax, cs:dword_180173278
0x180059b43  cmp     eax, r15d
0x180059b46  jbe     short loc_180059BB8
0x180059b48  call    IkeGetTlsMmLuid
0x180059b4d  mov     [rbp+57h+var_C0], rax
0x180059b51  lea     rax, [rbp+57h+var_C0]
0x180059b55  mov     [rbp+57h+var_90], rax
0x180059b59  mov     [rbp+57h+var_88], 8
0x180059b61  call    IkeGetTlsPeerAddr
0x180059b66  mov     rdx, rax
0x180059b69  lea     rcx, [rbp+57h+var_80]
0x180059b6d  call    _tlgCreate1Sz_wchar_t
0x180059b72  lea     rax, [rbp+57h+var_B8]
0x180059b76  mov     [rbp+57h+var_68], 2Ah ; '*'
0x180059b7e  mov     [rbp+57h+var_60], rax
0x180059b82  lea     rcx, aDeregisteringA_0; "Deregistering Authip keying module fail"...
0x180059b89  lea     rax, [rbp+57h+var_B0]
0x180059b8d  mov     [rbp+57h+var_70], rcx
0x180059b91  mov     [rsp+0F0h+var_C8], rax
0x180059b96  lea     rdx, word_18014EC72
0x180059b9d  lea     rcx, dword_180173278
0x180059ba4  mov     dword ptr [rsp+0F0h+var_D0], 6
0x180059bac  mov     dword ptr [rbp+57h+var_B8], esi
0x180059baf  mov     [rbp+57h+var_58], r15
0x180059bb3  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180059bb8  mov     rax, cs:gIkeExtGlobals
0x180059bbf  mov     [rax+0AC0h], r14
0x180059bc6  mov     rax, cs:gIkeExtGlobals
0x180059bcd  cmp     [rax+0AC8h], r14
0x180059bd4  jz      loc_180059D89
0x180059bda  mov     rdi, cs:WPP_GLOBAL_Control
0x180059be1  cmp     rdi, r12
0x180059be4  jz      short loc_180059C1F
0x180059be6  cmp     [rdi+19h], r15b
0x180059bea  jb      short loc_180059C1F
0x180059bec  test    [rdi+1Ch], r13b
0x180059bf0  jz      short loc_180059C1F
0x180059bf2  mov     rdi, [rdi+10h]
0x180059bf6  call    IkeGetTlsPeerAddr
0x180059bfb  mov     rbx, rax
0x180059bfe  call    IkeGetTlsMmLuid
0x180059c03  mov     r9, rax
0x180059c06  mov     [rsp+0F0h+var_D0], rbx
0x180059c0b  mov     edx, 32h ; '2'
0x180059c10  lea     r8, WPP_c3da8f174801358a223b58501d21a257_Traceguids
0x180059c17  mov     rcx, rdi
0x180059c1a  call    WPP_SF_iS
0x180059c1f  mov     eax, cs:dword_180173278
0x180059c25  cmp     eax, r15d
0x180059c28  jbe     short loc_180059C8B
0x180059c2a  call    IkeGetTlsMmLuid
0x180059c2f  mov     [rbp+57h+var_C0], rax
0x180059c33  lea     rax, [rbp+57h+var_C0]
0x180059c37  mov     [rbp+57h+var_90], rax
0x180059c3b  mov     [rbp+57h+var_88], 8
0x180059c43  call    IkeGetTlsPeerAddr
0x180059c48  mov     rdx, rax
0x180059c4b  lea     rcx, [rbp+57h+var_80]
0x180059c4f  call    _tlgCreate1Sz_wchar_t
0x180059c54  lea     rcx, aDeregisteringI_1; "Deregistering IKEv2 keying module"
0x180059c5b  mov     [rbp+57h+var_68], 22h ; '"'
0x180059c63  lea     rax, [rbp+57h+var_B0]
0x180059c67  mov     [rbp+57h+var_70], rcx
0x180059c6b  mov     [rsp+0F0h+var_C8], rax
0x180059c70  lea     rcx, dword_180173278
0x180059c77  lea     rdx, byte_18014EC2F
0x180059c7e  mov     dword ptr [rsp+0F0h+var_D0], 5
0x180059c86  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180059c8b  mov     rcx, cs:gIkeExtGlobals
0x180059c92  mov     rdx, [rcx+0AC8h]
0x180059c99  mov     rcx, [rcx+0AB0h]
0x180059ca0  call    cs:__imp_IPsecKeyModuleDelete0
0x180059ca6  mov     esi, eax
0x180059ca8  test    eax, eax
0x180059caa  jz      loc_180059D74
0x180059cb0  mov     rdi, cs:WPP_GLOBAL_Control
0x180059cb7  cmp     rdi, r12
0x180059cba  jz      short loc_180059CF9
0x180059cbc  cmp     [rdi+19h], r15b
0x180059cc0  jb      short loc_180059CF9
0x180059cc2  test    [rdi+1Ch], r13b
0x180059cc6  jz      short loc_180059CF9
0x180059cc8  mov     rdi, [rdi+10h]
0x180059ccc  call    IkeGetTlsPeerAddr
0x180059cd1  mov     rbx, rax
0x180059cd4  call    IkeGetTlsMmLuid
0x180059cd9  mov     r9, rax
0x180059cdc  mov     dword ptr [rsp+0F0h+var_C8], esi
0x180059ce0  mov     edx, 33h ; '3'
0x180059ce5  mov     [rsp+0F0h+var_D0], rbx
0x180059cea  lea     r8, WPP_c3da8f174801358a223b58501d21a257_Traceguids
0x180059cf1  mov     rcx, rdi
0x180059cf4  call    WPP_SF_iSL
0x180059cf9  mov     eax, cs:dword_180173278
0x180059cff  cmp     eax, r15d
0x180059d02  jbe     short loc_180059D74
0x180059d04  call    IkeGetTlsMmLuid
0x180059d09  mov     [rbp+57h+var_C0], rax
0x180059d0d  lea     rax, [rbp+57h+var_C0]
0x180059d11  mov     [rbp+57h+var_90], rax
0x180059d15  mov     [rbp+57h+var_88], 8
0x180059d1d  call    IkeGetTlsPeerAddr
0x180059d22  mov     rdx, rax
0x180059d25  lea     rcx, [rbp+57h+var_80]
0x180059d29  call    _tlgCreate1Sz_wchar_t
0x180059d2e  lea     rax, [rbp+57h+var_B8]
0x180059d32  mov     [rbp+57h+var_68], 29h ; ')'
0x180059d3a  mov     [rbp+57h+var_60], rax
0x180059d3e  lea     rcx, aDeregisteringI; "Deregistering IKEv2 keying module faile"...
0x180059d45  lea     rax, [rbp+57h+var_B0]
0x180059d49  mov     [rbp+57h+var_70], rcx
0x180059d4d  mov     [rsp+0F0h+var_C8], rax
0x180059d52  lea     rdx, word_18014EBE2
0x180059d59  lea     rcx, dword_180173278
0x180059d60  mov     dword ptr [rsp+0F0h+var_D0], 6
0x180059d68  mov     dword ptr [rbp+57h+var_B8], esi
0x180059d6b  mov     [rbp+57h+var_58], r15
0x180059d6f  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180059d74  mov     rax, cs:gIkeExtGlobals
0x180059d7b  mov     [rax+0AC8h], r14
0x180059d82  mov     rax, cs:gIkeExtGlobals
  ... truncated ...
```
