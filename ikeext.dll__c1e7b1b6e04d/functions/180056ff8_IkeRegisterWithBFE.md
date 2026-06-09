# IkeRegisterWithBFE

- ea: `0x180056ff8`
- end: `0x1800580ca`
- name: `IkeRegisterWithBFE`
- size: `4306`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

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
  __int64 v0; // rcx
  __int64 v1; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v3; // rcx
  int TlsMmLuid; // eax
  __int64 v5; // rcx
  const WCHAR *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  DWORD v9; // eax
  __int64 v10; // rcx
  const char *v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rsi
  __int64 v14; // rdi
  __int64 v15; // rbx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  const WCHAR *v19; // rax
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rdi
  __int64 v23; // rbx
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // rcx
  const WCHAR *v27; // rax
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // rdi
  __int64 v31; // rbx
  __int64 v32; // rcx
  int v33; // eax
  __int64 v34; // rcx
  const WCHAR *v35; // rax
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 v38; // rdi
  __int64 v39; // rbx
  __int64 v40; // rcx
  int v41; // eax
  __int64 v42; // rcx
  const WCHAR *v43; // rax
  __int64 v44; // r8
  __int64 v45; // r9
  __int64 v46; // rdi
  __int64 v47; // rbx
  __int64 v48; // rcx
  int v49; // eax
  __int64 v50; // rcx
  const WCHAR *v51; // rax
  __int64 v52; // r8
  __int64 v53; // r9
  __int64 v54; // rdi
  __int64 v55; // rbx
  __int64 v56; // rcx
  int v57; // eax
  __int64 v58; // rcx
  const WCHAR *v59; // rax
  __int64 v60; // r8
  __int64 v61; // r9
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
  __int64 v78; // rdi
  __int64 v79; // rbx
  __int64 v80; // rcx
  int v81; // eax
  __int64 v82; // rcx
  const WCHAR *v83; // rax
  __int64 v84; // r8
  __int64 v85; // r9
  __int64 v86; // rdi
  __int64 v87; // rbx
  __int64 v88; // rcx
  int v89; // eax
  __int64 v90; // rcx
  const WCHAR *v91; // rax
  __int64 v92; // r8
  __int64 v93; // r9
  __int64 v94; // rdi
  __int64 v95; // rbx
  __int64 v96; // rcx
  int v97; // eax
  __int64 v98; // rcx
  const WCHAR *v99; // rax
  __int64 v100; // r8
  __int64 v101; // r9
  __int64 v102; // rdi
  __int64 v103; // rbx
  __int64 v104; // rcx
  int v105; // eax
  __int64 v106; // rcx
  const WCHAR *v107; // rax
  __int64 v108; // r8
  __int64 v109; // r9
  __int64 v110; // rdi
  __int64 v111; // rbx
  __int64 v112; // rcx
  int v113; // eax
  __int64 v114; // rcx
  const WCHAR *v115; // rax
  __int64 v116; // r8
  __int64 v117; // r9
  __int64 v118; // rdi
  __int64 v119; // rbx
  __int64 v120; // rcx
  int v121; // eax
  __int64 v122; // rcx
  const WCHAR *v123; // rax
  __int64 v124; // r8
  __int64 v125; // r9
  __int64 v126; // rdi
  __int64 v127; // rbx
  __int64 v128; // rcx
  int v129; // eax
  __int64 v130; // rcx
  const WCHAR *v131; // rax
  __int64 v132; // r8
  FWPM_PROVIDER_CONTEXT_SUBSCRIPTION0 v134; // [rsp+30h] [rbp-D0h] BYREF
  GUID v135; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v136; // [rsp+60h] [rbp-A0h]
  __int64 (__fastcall *v137)(int, int, int, int, __int64, int, int, __int64); // [rsp+70h] [rbp-90h]
  __int64 (__fastcall *v138)(); // [rsp+78h] [rbp-88h]
  __int64 (__fastcall *v139)(); // [rsp+80h] [rbp-80h]
  __int64 (*v140)(); // [rsp+88h] [rbp-78h]
  FWPM_FILTER_SUBSCRIPTION0 subscription; // [rsp+90h] [rbp-70h] BYREF
  __int64 v142; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v143; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v144[8]; // [rsp+D0h] [rbp-30h] BYREF
  GUID v145; // [rsp+D8h] [rbp-28h]
  int v146; // [rsp+E8h] [rbp-18h]
  int v147; // [rsp+108h] [rbp+8h]
  _BYTE v148[32]; // [rsp+120h] [rbp+20h] BYREF
  __int64 *v149; // [rsp+140h] [rbp+40h]
  __int64 v150; // [rsp+148h] [rbp+48h]
  _BYTE v151[16]; // [rsp+150h] [rbp+50h] BYREF
  const char *v152; // [rsp+160h] [rbp+60h]
  __int64 v153; // [rsp+168h] [rbp+68h]

  memset_0(&v135, 0, 0x40u);
  memset_0(v144, 0, 0x48u);
  memset(&subscription, 0, sizeof(subscription));
  v143 = 0;
  memset(&v134, 0, sizeof(v134));
  TraceLogHelper("IkeRegisterWithBFE", 1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v1 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    TlsPeerAddr = IkeGetTlsPeerAddr(v0);
    TlsMmLuid = IkeGetTlsMmLuid(v3);
    WPP_SF_iS(v1, 30, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, TlsMmLuid, TlsPeerAddr);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v142 = IkeGetTlsMmLuid(v0);
    v149 = &v142;
    v150 = 8;
    v6 = (const WCHAR *)IkeGetTlsPeerAddr(v5);
    tlgCreate1Sz_wchar_t((__int64)v151, v6);
    v153 = 42;
    v152 = "Subscribing as diagnostics event provider";
    tlgWriteTransfer_EtwEventWriteTransfer(
      (__int64)&dword_180173278,
      (unsigned __int8 *)byte_18014F161,
      v7,
      v8,
      5,
      (__int64)v148);
  }
  v9 = FwpmEventProviderCreate0(0, &gIkeExtGlobals[71].LockSemaphore);
  if ( v9 )
  {
    v11 = "FwpmEventProviderCreate0";
LABEL_118:
    v13 = WfpReportSysErrorAsWinError(v10, v11, v9, 1);
    return IkeReturnError(v13, "IkeRegisterWithBFE");
  }
  v13 = WfpUnifiedTraceStart();
  if ( !v13 )
  {
    v146 = 0;
    v147 = -1;
    v145 = FWPM_LAYER_IKEEXT_V4;
    subscription.flags = 2;
    subscription.enumTemplate = (FWPM_FILTER_ENUM_TEMPLATE0 *)v144;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v14 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v15 = IkeGetTlsPeerAddr(v12);
      v17 = IkeGetTlsMmLuid(v16);
      WPP_SF_iS(v14, 31, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v17, v15);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v142 = IkeGetTlsMmLuid(v12);
      v149 = &v142;
      v150 = 8;
      v19 = (const WCHAR *)IkeGetTlsPeerAddr(v18);
      tlgCreate1Sz_wchar_t((__int64)v151, v19);
      v153 = 43;
      v152 = "Subscribing for MM V4 filter notifications";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)&unk_18014F120,
        v20,
        v21,
        5,
        (__int64)v148);
    }
    v9 = FwpmFilterSubscribeChanges0(
           gIkeExtGlobals[68].OwningThread,
           &subscription,
           IkeProcessMMFilterChange,
           0,
           (HANDLE *)&gIkeExtGlobals[69].LockCount);
    if ( v9 )
      goto LABEL_17;
    v145 = FWPM_LAYER_IKEEXT_V6;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v22 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v23 = IkeGetTlsPeerAddr(v10);
      v25 = IkeGetTlsMmLuid(v24);
      WPP_SF_iS(v22, 32, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v25, v23);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v142 = IkeGetTlsMmLuid(v10);
      v149 = &v142;
      v150 = 8;
      v27 = (const WCHAR *)IkeGetTlsPeerAddr(v26);
      tlgCreate1Sz_wchar_t((__int64)v151, v27);
      v153 = 43;
      v152 = "Subscribing for MM V6 filter notifications";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_18014F0DF,
        v28,
        v29,
        5,
        (__int64)v148);
    }
    v9 = FwpmFilterSubscribeChanges0(
           gIkeExtGlobals[68].OwningThread,
           &subscription,
           IkeProcessMMFilterChange,
           0,
           &gIkeExtGlobals[69].LockSemaphore);
    if ( v9 )
      goto LABEL_17;
    v145 = FWPM_LAYER_IPSEC_V4;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v30 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v31 = IkeGetTlsPeerAddr(v10);
      v33 = IkeGetTlsMmLuid(v32);
      WPP_SF_iS(v30, 33, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v33, v31);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v142 = IkeGetTlsMmLuid(v10);
      v149 = &v142;
      v150 = 8;
      v35 = (const WCHAR *)IkeGetTlsPeerAddr(v34);
      tlgCreate1Sz_wchar_t((__int64)v151, v35);
      v153 = 43;
      v152 = "Subscribing for QM V4 filter notifications";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)&word_18014F09E,
        v36,
        v37,
        5,
        (__int64)v148);
    }
    v9 = FwpmFilterSubscribeChanges0(
           gIkeExtGlobals[68].OwningThread,
           &subscription,
           IkeProcessQMFilterChange,
           0,
           &gIkeExtGlobals[69].OwningThread);
    if ( v9 )
      goto LABEL_17;
    v145 = FWPM_LAYER_IPSEC_V6;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v38 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v39 = IkeGetTlsPeerAddr(v10);
      v41 = IkeGetTlsMmLuid(v40);
      WPP_SF_iS(v38, 34, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v41, v39);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v142 = IkeGetTlsMmLuid(v10);
      v149 = &v142;
      v150 = 8;
      v43 = (const WCHAR *)IkeGetTlsPeerAddr(v42);
      tlgCreate1Sz_wchar_t((__int64)v151, v43);
      v153 = 43;
      v152 = "Subscribing for QM V6 filter notifications";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_18014F05D,
        v44,
        v45,
        5,
        (__int64)v148);
    }
    v9 = FwpmFilterSubscribeChanges0(
           gIkeExtGlobals[68].OwningThread,
           &subscription,
           IkeProcessQMFilterChange,
           0,
           (HANDLE *)&gIkeExtGlobals[69].SpinCount);
    if ( v9 )
    {
LABEL_17:
      v11 = "FwpmFilterSubscribeChanges0";
      goto LABEL_118;
    }
    DWORD2(v143) = 5;
    v134.enumTemplate = (FWPM_PROVIDER_CONTEXT_ENUM_TEMPLATE0 *)&v143;
    v134.flags = 2;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v46 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v47 = IkeGetTlsPeerAddr(v10);
      v49 = IkeGetTlsMmLuid(v48);
      WPP_SF_iS(v46, 35, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v49, v47);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v142 = IkeGetTlsMmLuid(v10);
      v149 = &v142;
      v150 = 8;
      v51 = (const WCHAR *)IkeGetTlsPeerAddr(v50);
      tlgCreate1Sz_wchar_t((__int64)v151, v51);
      v153 = 44;
      v152 = "Subscribing for IKE MM policy notifications";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)&dword_18014F01C,
        v52,
        v53,
        5,
        (__int64)v148);
    }
    v9 = FwpmProviderContextSubscribeChanges0(
           gIkeExtGlobals[68].OwningThread,
           &v134,
           IkeProcessMMPolicyChange,
           0,
           (HANDLE *)&gIkeExtGlobals[70].DebugInfo);
    if ( v9 )
      goto LABEL_46;
    DWORD2(v143) = 6;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v54 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v55 = IkeGetTlsPeerAddr(v10);
      v57 = IkeGetTlsMmLuid(v56);
      WPP_SF_iS(v54, 36, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v57, v55);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v142 = IkeGetTlsMmLuid(v10);
      v149 = &v142;
      v150 = 8;
      v59 = (const WCHAR *)IkeGetTlsPeerAddr(v58);
      tlgCreate1Sz_wchar_t((__int64)v151, v59);
      v153 = 47;
      v152 = "Subscribing for Authip MM policy notifications";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_18014EFDB,
        v60,
        v61,
        5,
        (__int64)v148);
    }
    v9 = FwpmProviderContextSubscribeChanges0(
           gIkeExtGlobals[68].OwningThread,
           &v134,
           IkeProcessMMPolicyChange,
           0,
           &gIkeExtGlobals[70].LockSemaphore);
    if ( v9 )
      goto LABEL_46;
    DWORD2(v143) = 10;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v62 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v63 = IkeGetTlsPeerAddr(v10);
      v65 = IkeGetTlsMmLuid(v64);
      WPP_SF_iS(v62, 37, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v65, v63);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v142 = IkeGetTlsMmLuid(v10);
      v149 = &v142;
      v150 = 8;
      v67 = (const WCHAR *)IkeGetTlsPeerAddr(v66);
      tlgCreate1Sz_wchar_t((__int64)v151, v67);
      v153 = 46;
      v152 = "Subscribing for IKEv2 MM policy notifications";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)word_18014EF9A,
        v68,
        v69,
        5,
        (__int64)v148);
    }
    v9 = FwpmProviderContextSubscribeChanges0(
           gIkeExtGlobals[68].OwningThread,
           &v134,
           IkeProcessMMPolicyChange,
           0,
           (HANDLE *)&gIkeExtGlobals[70].SpinCount);
    if ( v9 )
      goto LABEL_46;
    DWORD2(v143) = 1;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v70 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v71 = IkeGetTlsPeerAddr(v10);
      v73 = IkeGetTlsMmLuid(v72);
      WPP_SF_iS(v70, 38, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v73, v71);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v142 = IkeGetTlsMmLuid(v10);
      v149 = &v142;
      v150 = 8;
      v75 = (const WCHAR *)IkeGetTlsPeerAddr(v74);
      tlgCreate1Sz_wchar_t((__int64)v151, v75);
      v153 = 54;
      v152 = "Subscribing for IKE QM transport policy notifications";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_18014EF59,
        v76,
        v77,
        5,
        (__int64)v148);
    }
    v9 = FwpmProviderContextSubscribeChanges0(
           gIkeExtGlobals[68].OwningThread,
           &v134,
           IkeProcessQMPolicyChange,
           0,
           (HANDLE *)&gIkeExtGlobals[70].LockCount);
    if ( v9 )
      goto LABEL_46;
    DWORD2(v143) = 2;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v78 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v79 = IkeGetTlsPeerAddr(v10);
      v81 = IkeGetTlsMmLuid(v80);
      WPP_SF_iS(v78, 39, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v81, v79);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v142 = IkeGetTlsMmLuid(v10);
      v149 = &v142;
      v150 = 8;
      v83 = (const WCHAR *)IkeGetTlsPeerAddr(v82);
      tlgCreate1Sz_wchar_t((__int64)v151, v83);
      v153 = 51;
      v152 = "Subscribing for IKE QM tunnel policy notifications";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)&unk_18014EF18,
        v84,
        v85,
        5,
        (__int64)v148);
    }
    v9 = FwpmProviderContextSubscribeChanges0(
           gIkeExtGlobals[68].OwningThread,
           &v134,
           IkeProcessQMPolicyChange,
           0,
           &gIkeExtGlobals[70].OwningThread);
    if ( v9 )
      goto LABEL_46;
    DWORD2(v143) = 3;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v86 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v87 = IkeGetTlsPeerAddr(v10);
      v89 = IkeGetTlsMmLuid(v88);
      WPP_SF_iS(v86, 40, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v89, v87);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v142 = IkeGetTlsMmLuid(v10);
      v149 = &v142;
      v150 = 8;
      v91 = (const WCHAR *)IkeGetTlsPeerAddr(v90);
      tlgCreate1Sz_wchar_t((__int64)v151, v91);
      v153 = 57;
      v152 = "Subscribing for Authip QM transport policy notifications";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_18014EED7,
        v92,
        v93,
        5,
        (__int64)v148);
    }
    v9 = FwpmProviderContextSubscribeChanges0(
           gIkeExtGlobals[68].OwningThread,
           &v134,
           IkeProcessQMPolicyChange,
           0,
           (HANDLE *)&gIkeExtGlobals[71].DebugInfo);
    if ( v9 )
      goto LABEL_46;
    DWORD2(v143) = 4;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v94 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v95 = IkeGetTlsPeerAddr(v10);
      v97 = IkeGetTlsMmLuid(v96);
      WPP_SF_iS(v94, 41, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v97, v95);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v142 = IkeGetTlsMmLuid(v10);
      v149 = &v142;
      v150 = 8;
      v99 = (const WCHAR *)IkeGetTlsPeerAddr(v98);
      tlgCreate1Sz_wchar_t((__int64)v151, v99);
      v153 = 54;
      v152 = "Subscribing for Authip QM tunnel policy notifications";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)&word_18014EE96,
        v100,
        v101,
        5,
        (__int64)v148);
    }
    v9 = FwpmProviderContextSubscribeChanges0(
           gIkeExtGlobals[68].OwningThread,
           &v134,
           IkeProcessQMPolicyChange,
           0,
           (HANDLE *)&gIkeExtGlobals[71].LockCount);
    if ( v9 )
      goto LABEL_46;
    DWORD2(v143) = 9;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v102 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v103 = IkeGetTlsPeerAddr(v10);
      v105 = IkeGetTlsMmLuid(v104);
      WPP_SF_iS(v102, 42, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v105, v103);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v142 = IkeGetTlsMmLuid(v10);
      v149 = &v142;
      v150 = 8;
      v107 = (const WCHAR *)IkeGetTlsPeerAddr(v106);
      tlgCreate1Sz_wchar_t((__int64)v151, v107);
      v153 = 53;
      v152 = "Subscribing for IKEv2 QM tunnel policy notifications";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_18014EE55,
        v108,
        v109,
        5,
        (__int64)v148);
    }
    v9 = FwpmProviderContextSubscribeChanges0(
           gIkeExtGlobals[68].OwningThread,
           &v134,
           IkeProcessQMPolicyChange,
           0,
           &gIkeExtGlobals[71].OwningThread);
    if ( v9 )
    {
LABEL_46:
      v11 = "FwpmProviderContextSubscribeChanges0";
      goto LABEL_118;
    }
    v136 = ikev1DisplayName;
    v137 = IkeProcessAcquireOak;
    v138 = IkeProcessExpire;
    v139 = IkeProcessClearTextResponseOak;
    v140 = _scrt_stub_for_is_c_termination_complete;
    v135 = FWPM_KEYING_MODULE_IKE;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v110 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v111 = IkeGetTlsPeerAddr(v10);
      v113 = IkeGetTlsMmLuid(v112);
      WPP_SF_iS(v110, 43, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v113, v111);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v142 = IkeGetTlsMmLuid(v10);
      v149 = &v142;
      v150 = 8;
      v115 = (const WCHAR *)IkeGetTlsPeerAddr(v114);
      tlgCreate1Sz_wchar_t((__int64)v151, v115);
      v153 = 30;
      v152 = "Registering IKE keying module";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)&dword_18014EE14,
        v116,
        v117,
        5,
        (__int64)v148);
    }
    v9 = IPsecKeyModuleAdd0(gIkeExtGlobals[68].OwningThread, &v135, &gIkeExtGlobals[68].LockSemaphore);
    if ( v9 )
      goto LABEL_117;
    v136 = authipDisplayName;
    v137 = IkeProcessAcquireAuthip;
    v139 = IkeProcessClearTextResponseAuthip;
    v140 = _scrt_stub_for_is_c_termination_complete;
    v135 = FWPM_KEYING_MODULE_AUTHIP;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v118 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v119 = IkeGetTlsPeerAddr(v10);
      v121 = IkeGetTlsMmLuid(v120);
      WPP_SF_iS(v118, 44, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v121, v119);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v142 = IkeGetTlsMmLuid(v10);
      v149 = &v142;
      v150 = 8;
      v123 = (const WCHAR *)IkeGetTlsPeerAddr(v122);
      tlgCreate1Sz_wchar_t((__int64)v151, v123);
      v153 = 33;
      v152 = "Registering Authip keying module";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_18014EDD3,
        v124,
        v125,
        5,
        (__int64)v148);
    }
    v9 = IPsecKeyModuleAdd0(gIkeExtGlobals[68].OwningThread, &v135, &gIkeExtGlobals[68].SpinCount);
    if ( v9 )
      goto LABEL_117;
    v136 = ikev2DisplayName;
    v137 = IkeProcessAcquireIkeV2;
    v139 = guard_check_icall_nop;
    v140 = IkeIfrEventEnumCallbackIkeV2;
    v135 = FWPM_KEYING_MODULE_IKEV2;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v126 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v127 = IkeGetTlsPeerAddr(v10);
      v129 = IkeGetTlsMmLuid(v128);
      WPP_SF_iS(v126, 45, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v129, v127);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v142 = IkeGetTlsMmLuid(v10);
      v149 = &v142;
      v150 = 8;
      v131 = (const WCHAR *)IkeGetTlsPeerAddr(v130);
      tlgCreate1Sz_wchar_t((__int64)v151, v131);
      v153 = 32;
      v152 = "Registering IKEv2 keying module";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)word_18014ED92,
        v132,
        (__int64)"Registering IKEv2 keying module",
        5,
        (__int64)v148);
    }
    v9 = IPsecKeyModuleAdd0(gIkeExtGlobals[68].OwningThread, &v135, &gIkeExtGlobals[69]);
    if ( v9 )
    {
LABEL_117:
      v11 = "IPsecKeyModuleAdd0";
      goto LABEL_118;
    }
  }
  return IkeReturnError(v13, "IkeRegisterWithBFE");
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
