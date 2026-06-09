# FwMoneisCreateAppContainer

- ea: `0x18002f7d4`
- end: `0x1800308ce`
- name: `FwMoneisCreateAppContainer`
- size: `4346`
- prototype: `__int64 __fastcall(void *, int, SID *, SID *, __int64, unsigned __int16 *, __int64, struct _SID_AND_ATTRIBUTES *, unsigned int)`
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800308e0`
- `0x1800b5890`

## callees

- `0x1800093b0`
- `0x180009460`
- `0x18000a0c0`
- `0x18000af3c`
- `0x180017110`
- `0x180023dd8`
- `0x180025afc`
- `0x180029b48`
- `0x18002b87c`
- `0x18002f7d4`
- `0x180033b28`
- `0x18003b4a0`
- `0x18003ca2c`
- `0x1800535a8`
- `0x180059270`
- `0x180062008`
- `0x1800620b8`
- `0x18006f520`
- `0x18006ffc8`
- `0x18008fc50`
- `0x1800acb2c`
- `0x1800b51d0`
- `0x1800b5e34`
- `0x1800bb620`
- `0x1800bde80`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002f8ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800307ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002f8ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800307ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb67`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800307c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800307d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800307c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800307d7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002fb04`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002fb5d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002fb04`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002fb5d`
- `fwbase!FwHResultToWindowsError` at `0x18002fbb1`
- `fwbase!FwHResultToWindowsError` at `0x18002fc5f`
- `fwbase!FwHResultToWindowsError` at `0x18003066a`
- `fwbase!FwHResultToWindowsError` at `0x18003069d`
- `fwbase!FwHResultToWindowsError` at `0x18002fbb1`
- `fwbase!FwHResultToWindowsError` at `0x18002fc5f`
- `fwbase!FwHResultToWindowsError` at `0x18003066a`
- `fwbase!FwHResultToWindowsError` at `0x18003069d`
- `fwbase!FwStringBuild` at `0x18002fba9`
- `fwbase!FwStringBuild` at `0x18002fba9`
- `fwbase!FwCriticalSectionEnter` at `0x180030814`
- `fwbase!FwCriticalSectionEnter` at `0x180030814`
- `fwbase!FwCriticalSectionLeave` at `0x18003086f`
- `fwbase!FwCriticalSectionLeave` at `0x18003086f`
- `fwbase!FwFree` at `0x1800307b9`
- `fwbase!FwFree` at `0x1800307b9`
- `FWPolicyIOMgr!FwAddRule` at `0x18002fc57`
- `FWPolicyIOMgr!FwAddRule` at `0x18002fc57`

## string_xrefs

- `0x1800306de`: `FwMoneisCreateAppContainer`
- `0x1800306ee`: `FwMoneisCreateAppContainer`

## pseudocode

```c
__int64 __fastcall FwMoneisCreateAppContainer(
        void *a1,
        int a2,
        SID *a3,
        SID *a4,
        __int64 a5,
        unsigned __int16 *a6,
        __int64 a7,
        struct _SID_AND_ATTRIBUTES *a8,
        unsigned int a9)
{
  struct _SID *v9; // rdi
  SID_AND_ATTRIBUTES *v10; // r14
  struct _SID *v11; // r12
  ULONGLONG TickCount64; // rax
  __int64 v14; // r8
  unsigned __int64 v15; // rcx
  ULONGLONG v16; // r13
  unsigned int v17; // ebx
  unsigned int IsChildAppContainer; // eax
  volatile unsigned int v19; // r9d
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r9
  int v23; // r15d
  DWORD LastError; // eax
  __int64 v25; // rcx
  int v26; // esi
  __int64 v27; // rdx
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int updated; // eax
  appIsolation::InboxAppContainerManager *v31; // rdi
  int v32; // r12d
  __int64 v33; // rdx
  void *v34; // rdi
  int v35; // eax
  __int64 v36; // rcx
  __int64 v37; // rdx
  int v38; // r15d
  int v39; // eax
  __int64 v40; // rcx
  __int64 v41; // rdx
  int v42; // esi
  int v43; // r14d
  void *v44; // rdi
  int v45; // eax
  bool v46; // zf
  int v47; // eax
  __int64 v48; // rcx
  __int64 v49; // rdx
  __int64 v50; // rdi
  unsigned int v51; // eax
  __int64 v52; // rcx
  __int64 v53; // rdx
  unsigned int v54; // eax
  unsigned int v55; // eax
  ULONGLONG v56; // rdi
  __int64 v57; // rcx
  int v58; // r14d
  unsigned __int64 v59; // rdx
  unsigned int v60; // ecx
  __int64 v61; // rcx
  int v63; // [rsp+30h] [rbp-D0h] BYREF
  SID *v64; // [rsp+38h] [rbp-C8h]
  SID *v65; // [rsp+40h] [rbp-C0h]
  ULONGLONG v66; // [rsp+48h] [rbp-B8h]
  int v67; // [rsp+50h] [rbp-B0h] BYREF
  int v68; // [rsp+54h] [rbp-ACh]
  _QWORD v69[4]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v70; // [rsp+78h] [rbp-88h]
  struct _SID_AND_ATTRIBUTES *v71; // [rsp+80h] [rbp-80h]
  void *v72; // [rsp+88h] [rbp-78h] BYREF
  void *v73; // [rsp+90h] [rbp-70h] BYREF
  void *v74; // [rsp+98h] [rbp-68h]
  _INET_FIREWALL_AC_CHANGE v75; // [rsp+A0h] [rbp-60h] BYREF
  LPWSTR StringSid; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v77; // [rsp+D8h] [rbp-28h] BYREF
  LPWSTR v78; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v79; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v80[8]; // [rsp+F0h] [rbp-10h] BYREF
  __int16 v81; // [rsp+F8h] [rbp-8h]
  unsigned __int16 *v82; // [rsp+108h] [rbp+8h]
  __int64 v83; // [rsp+110h] [rbp+10h]
  int v84; // [rsp+118h] [rbp+18h]
  int v85; // [rsp+11Ch] [rbp+1Ch]
  __int16 v86; // [rsp+120h] [rbp+20h]
  __int64 v87; // [rsp+1A0h] [rbp+A0h]
  int v88; // [rsp+1F8h] [rbp+F8h]
  int v89; // [rsp+210h] [rbp+110h]
  __int16 v90; // [rsp+214h] [rbp+114h]
  unsigned __int16 *v91; // [rsp+228h] [rbp+128h]
  int v92; // [rsp+230h] [rbp+130h]
  int *v93; // [rsp+238h] [rbp+138h]
  __int64 AppContainerSidAcl; // [rsp+260h] [rbp+160h]
  LPWSTR v95; // [rsp+268h] [rbp+168h]
  LPWSTR v96; // [rsp+270h] [rbp+170h]
  int v97; // [rsp+278h] [rbp+178h]
  __int16 v98; // [rsp+298h] [rbp+198h]
  __int64 v99; // [rsp+2E0h] [rbp+1E0h]
  __int64 v100; // [rsp+2F0h] [rbp+1F0h] BYREF
  __int16 v101; // [rsp+2F8h] [rbp+1F8h]
  __int64 v102; // [rsp+300h] [rbp+200h]
  struct _SID *v103; // [rsp+308h] [rbp+208h]
  struct _SID *v104; // [rsp+310h] [rbp+210h]
  __int64 v105; // [rsp+318h] [rbp+218h]
  unsigned __int16 *v106; // [rsp+320h] [rbp+220h]
  __int64 v107; // [rsp+328h] [rbp+228h]
  unsigned int v108; // [rsp+330h] [rbp+230h]
  struct _SID_AND_ATTRIBUTES *v109; // [rsp+338h] [rbp+238h]
  int v110; // [rsp+370h] [rbp+270h] BYREF
  __int64 v111; // [rsp+378h] [rbp+278h] BYREF
  int v112[4]; // [rsp+380h] [rbp+280h] BYREF
  _BYTE v113[336]; // [rsp+390h] [rbp+290h] BYREF

  v9 = a4;
  v10 = a8;
  v11 = a3;
  v77 = a5;
  v70 = a6;
  v64 = a4;
  v65 = a3;
  v68 = a2;
  v74 = a1;
  v71 = a8;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 51, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids);
  v67 = 0;
  v63 = 0;
  v73 = 0;
  v72 = 0;
  *(_OWORD *)v112 = 0;
  StringSid = 0;
  v78 = 0;
  v79 = 0;
  memset_0(&v100, 0, 0x78u);
  *(&v75.binaries.count + 1) = 0;
  memset_0(v80, 0, 0x1F8u);
  v110 = 132608;
  v111 = 161;
  memset_0(v113, 0, 0x142u);
  TickCount64 = GetTickCount64();
  v15 = -1;
  v16 = TickCount64;
  v66 = TickCount64;
  v69[0] = v113;
  v69[1] = &v111;
  v69[2] = &v77;
  v69[3] = v80;
  do
    ++v15;
  while ( *(_WORD *)(v77 + 2 * v15) );
  if ( v15 <= 0x40 )
  {
    if ( !v15 )
      goto LABEL_9;
    IsChildAppContainer = FwMoneisValidateCapabilitySids(a8, a9);
    v17 = IsChildAppContainer;
    if ( IsChildAppContainer )
    {
      v20 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || ((unsigned __int8)v19 & *(_BYTE *)(WPP_GLOBAL_Control + 28LL)) == 0 )
      {
        goto LABEL_29;
      }
      v21 = 53;
      goto LABEL_51;
    }
    DelaySignaled = v19;
    IsChildAppContainer = FwMoneisIsChildAppContainer(v9, &v67);
    v17 = IsChildAppContainer;
    if ( IsChildAppContainer )
    {
      v20 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_29;
      v21 = 54;
      goto LABEL_51;
    }
    IsChildAppContainer = FwMoneisValidateAppContainerOperation(v74, a2, v67, v11, v9, &v63);
    v17 = IsChildAppContainer;
    if ( IsChildAppContainer )
    {
      v20 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_29;
      v21 = 55;
      goto LABEL_51;
    }
    if ( !v63 )
    {
      v17 = 0;
      v20 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_29;
      v21 = 56;
      v22 = 0;
      goto LABEL_28;
    }
    appIsolation::SidManagement::ComputeAppContainerSidsPresence(
      (appIsolation::SidManagement *)gSidManager,
      v112,
      a8,
      a9);
    IsChildAppContainer = FwMoneisOpenStores(a2, &v73, &v72);
    v17 = IsChildAppContainer;
    if ( IsChildAppContainer )
    {
      v20 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_29;
      v21 = 57;
      goto LABEL_51;
    }
    v23 = 0;
    if ( !ConvertSidToStringSidW(v11, &StringSid) )
    {
      LastError = GetLastError();
      v17 = LastError;
      v25 = WPP_GLOBAL_Control;
      LOBYTE(v26) = 1;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v27 = 58;
LABEL_38:
        WPP_SF_d(*(_QWORD *)(v25 + 16), v27, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids, LastError);
        goto LABEL_193;
      }
      goto LABEL_193;
    }
    if ( !ConvertSidToStringSidW(v9, &v78) )
    {
      LastError = GetLastError();
      v17 = LastError;
      v25 = WPP_GLOBAL_Control;
      LOBYTE(v26) = 1;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v27 = 59;
        goto LABEL_38;
      }
LABEL_193:
      if ( !v17 || !v23 )
      {
LABEL_198:
        v16 = v66;
        goto LABEL_199;
      }
LABEL_195:
      v55 = FwMoneisDeleteAppContainer(v74, v68, v11, v9, v70);
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && ((unsigned __int8)v26 & *(_BYTE *)(WPP_GLOBAL_Control + 28LL)) != 0 )
      {
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 84, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids, v55);
      }
      goto LABEL_198;
    }
    v28 = FwStringBuild(&v79, v78, StringSid, 0);
    IsChildAppContainer = FwHResultToWindowsError(v28);
    v17 = IsChildAppContainer;
    if ( IsChildAppContainer )
    {
      v20 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_29;
      v21 = 60;
      goto LABEL_51;
    }
    v100 = 0;
    v101 = 545;
    v102 = v79;
    v105 = v77;
    v106 = v70;
    v103 = v9;
    v104 = v11;
    v107 = a7;
    v108 = a9;
    v109 = a8;
    v29 = FwAddRule(*((_QWORD *)gFwIsolationManager + 12), 3, &v100);
    IsChildAppContainer = FwHResultToWindowsError(v29);
    v17 = IsChildAppContainer;
    if ( IsChildAppContainer )
    {
      v20 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_29;
      v21 = 61;
LABEL_51:
      v22 = IsChildAppContainer;
LABEL_28:
      WPP_SF_d(*(_QWORD *)(v20 + 16), v21, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids, v22);
LABEL_29:
      v16 = v66;
      goto LABEL_199;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl'::`2'::impl) )
    {
      updated = FwMoneisUpdatePackageIdConditions(v9);
      v17 = updated;
      if ( updated )
      {
        LOBYTE(v26) = 1;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 62, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids, updated);
        goto LABEL_195;
      }
    }
    v31 = gInboxAppContainerManager;
    v23 = 1;
    v63 = 1;
    v32 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl'::`2'::impl) )
      LOBYTE(v32) = *((_DWORD *)v31 + 15) == 0;
    else
      LOBYTE(v32) = *((_DWORD *)v31 + 15) == 0;
    if ( v67 )
      goto LABEL_176;
    memset_0(v80, 0, 0x1F8u);
    v90 = 1;
    v81 = 545;
    v82 = v70;
    v91 = v70;
    v96 = StringSid;
    v83 = a7;
    v86 = 256;
    LOBYTE(v33) = 1;
    LOBYTE(v26) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppContainerPFN>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_AppContainerPFN>::GetImpl'::`2'::impl,
      v33);
    if ( v77 )
      v99 = v77;
    else
      v95 = v78;
    v34 = v73;
    v98 |= 8u;
    v89 = 2;
    v84 = 0x7FFFFFFF;
    v85 = 1;
    v35 = lambda_e5e55c76e432676809aa605172d104a8_::operator()(v69, L"-In-Block", v73, StringSid);
    if ( v35 < 0 )
    {
      v36 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_192;
      v37 = 63;
      goto LABEL_68;
    }
    v85 = 2;
    v35 = lambda_e5e55c76e432676809aa605172d104a8_::operator()(v69, L"-Out-Block", v34, StringSid);
    if ( v35 < 0 )
    {
      v36 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_192;
      v37 = 64;
      goto LABEL_68;
    }
    v89 = 3;
    if ( v112[3] == 1 )
    {
      AppContainerSidAcl = FwMoneisGetAppContainerSidAcl(3);
      v97 = 1;
      v85 = 1;
      v35 = lambda_e5e55c76e432676809aa605172d104a8_::operator()(v69, L"-In-Allow-Proximity", v34, StringSid);
      if ( v35 < 0 )
      {
        v36 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_192;
        v37 = 65;
        goto LABEL_68;
      }
      v85 = 2;
      v35 = lambda_e5e55c76e432676809aa605172d104a8_::operator()(v69, L"-Out-Allow-Proximity", v34, StringSid);
      if ( v35 < 0 )
      {
        v36 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_192;
        v37 = 66;
        goto LABEL_68;
      }
      v97 = 16;
      v88 = 2;
      v85 = 1;
      v35 = lambda_e5e55c76e432676809aa605172d104a8_::operator()(v69, L"-In-Allow-Proximity-Wireless", v34, StringSid);
      if ( v35 < 0 )
      {
        v36 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_192;
        v37 = 67;
        goto LABEL_68;
      }
      v85 = 2;
      v35 = lambda_e5e55c76e432676809aa605172d104a8_::operator()(v69, L"-Out-Allow-Proximity-Wireless", v34, StringSid);
      if ( v35 < 0 )
      {
        v36 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_192;
        v37 = 68;
LABEL_68:
        WPP_SF_d(*(_QWORD *)(v36 + 16), v37, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids, (unsigned int)v35);
LABEL_192:
        v9 = v64;
        v11 = v65;
        goto LABEL_193;
      }
      v97 = 0;
      v88 = 0;
    }
    v38 = v112[2];
    if ( v112[2] == 1 )
    {
      AppContainerSidAcl = FwMoneisGetAppContainerSidAcl(2);
      v84 = 7;
      v87 = 0x2000000020LL;
      v85 = 1;
      v39 = lambda_e5e55c76e432676809aa605172d104a8_::operator()(v69, L"-In-Allow-Intranet", v34, StringSid);
      if ( v39 < 0 )
      {
        v40 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v41 = 69;
        goto LABEL_96;
      }
      v85 = 2;
      v39 = lambda_e5e55c76e432676809aa605172d104a8_::operator()(v69, L"-Out-Allow-Intranet", v34, StringSid);
      if ( v39 < 0 )
      {
        v40 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v41 = 70;
        goto LABEL_96;
      }
      v85 = 1;
      v90 |= 2u;
      v84 = 6;
      v87 = 0x10000000100LL;
      v39 = lambda_e5e55c76e432676809aa605172d104a8_::operator()(
              v69,
              L"-In-Allow-Intranet-Authenticate",
              v34,
              StringSid);
      if ( v39 < 0 )
      {
        v40 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v41 = 71;
        goto LABEL_96;
      }
      v85 = 2;
      v39 = lambda_e5e55c76e432676809aa605172d104a8_::operator()(
              v69,
              L"-Out-Allow-Intranet-Authenticate",
              v34,
              StringSid);
      if ( v39 < 0 )
      {
        v40 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v41 = 72;
        goto LABEL_96;
      }
      v90 &= ~2u;
    }
    v42 = v112[0];
    v43 = v112[1];
    if ( v112[0] == 1 )
    {
      AppContainerSidAcl = FwMoneisGetAppContainerSidAcl(0);
      v84 = 7;
      v87 = 0x4000000040LL;
      v85 = 1;
      v39 = lambda_e5e55c76e432676809aa605172d104a8_::operator()(v69, L"-In-Allow-Internet", v34, StringSid);
      if ( v39 < 0 )
      {
        v40 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          LOBYTE(v26) = 1;
          if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_97;
          v41 = 73;
LABEL_96:
          WPP_SF_d(*(_QWORD *)(v40 + 16), v41, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids, (unsigned int)v39);
LABEL_97:
          v23 = 1;
          goto LABEL_192;
        }
LABEL_191:
        v23 = v63;
        LOBYTE(v26) = v63;
        goto LABEL_192;
      }
      v85 = 2;
      v39 = lambda_e5e55c76e432676809aa605172d104a8_::operator()(v69, L"-Out-Allow-Internet", v34, StringSid);
      if ( v39 < 0 )
      {
        v40 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          LOBYTE(v26) = 1;
          if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_97;
          v41 = 74;
          goto LABEL_96;
        }
        goto LABEL_191;
      }
    }
    else if ( !v112[0] && v112[1] == 1 )
    {
      AppContainerSidAcl = FwMoneisGetAppContainerSidAcl(1);
      v84 = 7;
      v87 = 0x4000000040LL;
      v85 = 2;
      v39 = lambda_e5e55c76e432676809aa605172d104a8_::operator()(v69, L"-Out-Allow-InternetClient", v34, StringSid);
      if ( v39 < 0 )
      {
        v40 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          LOBYTE(v26) = 1;
          if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_97;
          v41 = 75;
          goto LABEL_96;
        }
        goto LABEL_191;
      }
    }
    if ( v68 != 1 )
    {
LABEL_175:
      v23 = v63;
      v10 = v71;
LABEL_176:
      v26 = v23;
      goto LABEL_177;
    }
    v44 = v72;
    v93 = &v110;
    v84 = 0;
    v87 = 0;
    AppContainerSidAcl = 0;
    v92 = 1;
    LOBYTE(v110) = 10;
    if ( v38 != 1 && v42 != 1 && v43 != 1 )
    {
LABEL_146:
      if ( v112[3] == 1 )
      {
        v97 = 1;
        v45 = 7;
        v84 = 7;
        v85 = 1;
        if ( v42 == 1 )
        {
          v84 = 3;
          if ( v38 != 1 )
            goto LABEL_153;
          v45 = 0;
          v84 = 0;
        }
        if ( !v42 )
          v90 |= 8u;
        if ( !v45 )
        {
LABEL_157:
          v97 = 16;
          v88 = 2;
          v84 = 4;
          v39 = lambda_e5e55c76e432676809aa605172d104a8_::operator()(v69, L"-In-Allow-WifiDirect", v44, StringSid);
          if ( v39 < 0 )
          {
            v40 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              LOBYTE(v26) = 1;
              if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
                goto LABEL_97;
              v41 = 79;
              goto LABEL_96;
            }
            goto LABEL_191;
          }
          v88 = 0;
          v90 &= ~8u;
          v46 = v42 == 1;
          v97 = 1;
          v26 = 1;
          v84 = 7;
          v85 = 2;
          if ( !v46 && v43 != 1 || (v84 = 3, v38 != 1) )
          {
            v47 = lambda_e5e55c76e432676809aa605172d104a8_::operator()(v69, L"-Out-Allow-EdgeTraversal", v44, StringSid);
            if ( v47 < 0 )
            {
              v48 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
              {
                goto LABEL_169;
              }
              v49 = 80;
LABEL_168:
              WPP_SF_d(*(_QWORD *)(v48 + 16), v49, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids, (unsigned int)v47);
LABEL_169:
              v23 = v63;
              goto LABEL_192;
            }
          }
          v97 = 16;
          v88 = 2;
          v84 = 4;
          v47 = lambda_e5e55c76e432676809aa605172d104a8_::operator()(v69, L"-Out-Allow-WifiDirect", v44, StringSid);
          if ( v47 < 0 )
          {
            v48 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            {
              goto LABEL_169;
            }
            v49 = 81;
            goto LABEL_168;
          }
          v10 = v71;
          v23 = v63;
          v97 = 0;
          v88 = 0;
LABEL_177:
          if ( v32 )
          {
            v50 = (unsigned int)FwLock();
            v51 = FwHResultToWindowsError(v50);
            v17 = v51;
            if ( v51 )
            {
              v52 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && ((unsigned __int8)v26 & *(_BYTE *)(WPP_GLOBAL_Control + 28LL)) != 0 )
              {
                v53 = 82;
LABEL_186:
                WPP_SF_d(*(_QWORD *)(v52 + 16), v53, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids, v51);
                goto LABEL_187;
              }
              goto LABEL_187;
            }
            v54 = FwUpdateFlushDelayedEnforced();
            v51 = FwHResultToWindowsError(v54);
            v17 = v51;
            if ( v51 )
            {
              v52 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && ((unsigned __int8)v26 & *(_BYTE *)(WPP_GLOBAL_Control + 28LL)) != 0 )
              {
                v53 = 83;
                goto LABEL_186;
              }
LABEL_187:
              if ( (int)v50 >= 0 )
                FwUnlockInternal(0, "FwMoneisCreateAppContainer");
              goto LABEL_192;
            }
            FwUnlockInternal(0, "FwMoneisCreateAppContainer");
          }
          v11 = v65;
          v9 = v64;
          v75.userSid = v65;
          v75.appContainerSid = v64;
          v75.displayName = v70;
          v75.changeType = v26;
          v75.createType = v26;
          v75.capabilities.count = a9;
          v75.capabilities.capabilities = v10;
          appIsolation::IsolationEvents::FwMoneisSendNotification(Block, v67, &v75);
          goto LABEL_193;
        }
LABEL_153:
        v39 = lambda_e5e55c76e432676809aa605172d104a8_::operator()(v69, L"-In-Allow-EdgeTraversal", v44, StringSid);
        if ( v39 < 0 )
        {
          v40 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            LOBYTE(v26) = 1;
            if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
              goto LABEL_97;
            v41 = 78;
            goto LABEL_96;
          }
          goto LABEL_191;
        }
        goto LABEL_157;
      }
      goto LABEL_175;
    }
    v85 = 2;
    v84 = 3;
    if ( v42 == 1 || v43 == 1 )
      v84 = 7;
    v39 = lambda_e5e55c76e432676809aa605172d104a8_::operator()(v69, L"-Out-Allow-AllCapabilities", v72, StringSid);
    if ( v39 < 0 )
    {
      v40 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        LOBYTE(v26) = 1;
        if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v41 = 76;
        goto LABEL_96;
      }
      goto LABEL_191;
    }
    v85 = 1;
    if ( v42 )
    {
      v90 |= 8u;
      if ( v42 == 1 )
        goto LABEL_141;
    }
    else
    {
      v84 &= ~4u;
    }
    if ( v38 != 1 )
    {
LABEL_145:
      v90 &= ~8u;
      goto LABEL_146;
    }
LABEL_141:
    v39 = lambda_e5e55c76e432676809aa605172d104a8_::operator()(v69, L"-In-Allow-ServerCapability", v44, StringSid);
    if ( v39 < 0 )
    {
      v40 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        LOBYTE(v26) = 1;
        if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v41 = 77;
        goto LABEL_96;
      }
      goto LABEL_191;
    }
    goto LABEL_145;
  }
  MicrosoftTelemetryAssertTriggeredNoArgs(v15, v77, v14, 1);
LABEL_9:
  v17 = 87;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 52, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids, 87);
LABEL_199:
  if ( v79 )
    FwFree(v79);
  if ( v78 )
    LocalFree(v78);
  if ( StringSid )
    LocalFree(StringSid);
  FwMoneisCloseStores(&v73, &v72);
  v56 = GetTickCount64();
  FwAggregateTelemetryEventWriteApiTimeout(v57, v56 - v16);
  if ( v56 - v16 > 0xBB8 )
  {
    v58 = 0;
    FwCriticalSectionEnter(&g_fwEventCriticalSection);
    v59 = g_fwEventLoggingStartTime;
    if ( g_fwEventLoggingStartTime && v56 - g_fwEventLoggingStartTime <= 0x3E8 )
    {
      v60 = g_fwEventCount;
    }
    else
    {
      v59 = v56;
      v60 = 0;
      g_fwEventLoggingStartTime = v56;
      g_fwEventCount = 0;
    }
    if ( v56 - v59 >= 28 * v60 )
    {
      v58 = 1;
      g_fwEventCount = v60 + 1;
    }
    FwCriticalSectionLeave(&g_fwEventCriticalSection);
    if ( v58 )
      FwTelemetryEventWriteApiTimeout(v61, v56 - v16);
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 85, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids);
  return v17;
}

```

## disassembly

```asm
0x18002f7d4  push    rbp
0x18002f7d6  push    rbx
0x18002f7d7  push    rsi
0x18002f7d8  push    rdi
0x18002f7d9  push    r12
0x18002f7db  push    r13
0x18002f7dd  push    r14
0x18002f7df  push    r15
0x18002f7e1  lea     rbp, [rsp-3F8h]
0x18002f7e9  sub     rsp, 4F8h
0x18002f7f0  mov     rax, cs:__security_cookie
0x18002f7f7  xor     rax, rsp
0x18002f7fa  mov     [rbp+430h+var_50], rax
0x18002f801  mov     rax, [rbp+430h+arg_20]
0x18002f808  mov     rdi, r9
0x18002f80b  mov     r14, [rbp+430h+arg_38]
0x18002f812  mov     r12, r8
0x18002f815  mov     rsi, [rbp+430h+arg_30]
0x18002f81c  mov     r15d, edx
0x18002f81f  mov     [rbp+430h+var_458], rax
0x18002f823  mov     rax, [rbp+430h+arg_28]
0x18002f82a  mov     [rsp+530h+var_4B8], rax
0x18002f82f  mov     [rsp+530h+var_4F8], r9
0x18002f834  mov     [rsp+530h+var_4F0], r8
0x18002f839  mov     [rsp+530h+var_4DC], edx
0x18002f83d  mov     [rbp+430h+var_498], rcx
0x18002f841  mov     [rbp+430h+var_4B0], r14
0x18002f845  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f84c  lea     rax, WPP_GLOBAL_Control
0x18002f853  cmp     rcx, rax
0x18002f856  jz      short loc_18002F873
0x18002f858  test    byte ptr [rcx+1Ch], 8
0x18002f85c  jz      short loc_18002F873
0x18002f85e  mov     rcx, [rcx+10h]
0x18002f862  lea     r8, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids
0x18002f869  mov     edx, 33h ; '3'
0x18002f86e  call    WPP_SF_
0x18002f873  xor     ebx, ebx
0x18002f875  lea     rcx, [rbp+430h+var_240]; void *
0x18002f87c  xorps   xmm0, xmm0
0x18002f87f  mov     [rsp+530h+var_4E0], ebx
0x18002f883  xor     edx, edx; Val
0x18002f885  mov     [rsp+530h+var_500], ebx
0x18002f889  mov     [rbp+430h+var_4A0], rbx
0x18002f88d  lea     r8d, [rbx+78h]; Size
0x18002f891  mov     [rbp+430h+var_4A8], rbx
0x18002f895  movups  xmmword ptr [rbp+430h+var_1B0], xmm0
0x18002f89c  mov     [rbp+430h+StringSid], rbx
0x18002f8a0  mov     [rbp+430h+var_450], rbx
0x18002f8a4  mov     [rbp+430h+var_448], rbx
0x18002f8a8  call    memset_0
0x18002f8ad  xor     edx, edx; Val
0x18002f8af  mov     dword ptr [rbp+430h+var_490.20h+4], ebx
0x18002f8b2  mov     r8d, 1F8h; Size
0x18002f8b8  lea     rcx, [rbp+430h+var_440]; void *
0x18002f8bc  call    memset_0
0x18002f8c1  xor     edx, edx; Val
0x18002f8c3  mov     [rbp+430h+var_1C0], 20600h
0x18002f8cd  mov     r8d, 142h; Size
0x18002f8d3  mov     [rbp+430h+var_1B8], 0A1h
0x18002f8de  lea     rcx, [rbp+430h+var_1A0]; void *
0x18002f8e5  call    memset_0
0x18002f8ea  call    cs:__imp_GetTickCount64
0x18002f8f0  mov     rdx, [rbp+430h+var_458]
0x18002f8f4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002f8f8  mov     r13, rax
0x18002f8fb  mov     [rsp+530h+var_4E8], rax
0x18002f900  lea     rax, [rbp+430h+var_1A0]
0x18002f907  mov     [rsp+530h+var_4D8], rax
0x18002f90c  lea     rax, [rbp+430h+var_1B8]
0x18002f913  mov     [rsp+530h+var_4D0], rax
0x18002f918  lea     rax, [rbp+430h+var_458]
0x18002f91c  mov     [rsp+530h+var_4C8], rax
0x18002f921  lea     rax, [rbp+430h+var_440]
0x18002f925  mov     [rsp+530h+var_4C0], rax
0x18002f92a  inc     rcx
0x18002f92d  cmp     [rdx+rcx*2], bx
0x18002f931  jnz     short loc_18002F92A
0x18002f933  mov     r9d, 1
0x18002f939  cmp     rcx, 40h ; '@'
0x18002f93d  jbe     short loc_18002F94C
0x18002f93f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002f944  mov     r9d, 1
0x18002f94a  jmp     short loc_18002F951
0x18002f94c  test    rcx, rcx
0x18002f94f  jnz     short loc_18002F992
0x18002f951  mov     ebx, 57h ; 'W'
0x18002f956  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f95d  lea     r14, WPP_GLOBAL_Control
0x18002f964  cmp     rcx, r14
0x18002f967  jz      loc_1800307A9
0x18002f96d  test    [rcx+1Ch], r9b
0x18002f971  jz      loc_1800307A9
0x18002f977  mov     rcx, [rcx+10h]
0x18002f97b  lea     edx, [rbx-23h]
0x18002f97e  mov     r9d, ebx
0x18002f981  lea     r8, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids
0x18002f988  call    WPP_SF_d
0x18002f98d  jmp     loc_1800307A9
0x18002f992  mov     r13d, [rbp+430h+arg_40]
0x18002f999  mov     rcx, r14; struct _SID_AND_ATTRIBUTES *
0x18002f99c  mov     edx, r13d; unsigned int
0x18002f99f  call    ?FwMoneisValidateCapabilitySids@@YAKPEAU_SID_AND_ATTRIBUTES@@K@Z; FwMoneisValidateCapabilitySids(_SID_AND_ATTRIBUTES *,ulong)
0x18002f9a4  mov     ebx, eax
0x18002f9a6  test    eax, eax
0x18002f9a8  jz      short loc_18002F9D5
0x18002f9aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f9b1  lea     r15, WPP_GLOBAL_Control
0x18002f9b8  cmp     rcx, r15
0x18002f9bb  jz      loc_18002FA9E
0x18002f9c1  test    [rcx+1Ch], r9b
0x18002f9c5  jz      loc_18002FA9E
0x18002f9cb  mov     edx, 35h ; '5'
0x18002f9d0  jmp     loc_18002FC91
0x18002f9d5  lea     rdx, [rsp+530h+var_4E0]; int *
0x18002f9da  mov     cs:?DelaySignaled@@3KC, r9d; ulong volatile DelaySignaled
0x18002f9e1  mov     rcx, rdi; struct _SID *
0x18002f9e4  call    ?FwMoneisIsChildAppContainer@@YAKPEAU_SID@@PEAH@Z; FwMoneisIsChildAppContainer(_SID *,int *)
0x18002f9e9  mov     ebx, eax
0x18002f9eb  test    eax, eax
0x18002f9ed  jz      short loc_18002FA1A
0x18002f9ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f9f6  lea     r15, WPP_GLOBAL_Control
0x18002f9fd  cmp     rcx, r15
0x18002fa00  jz      loc_18002FA9E
0x18002fa06  test    byte ptr [rcx+1Ch], 1
0x18002fa0a  jz      loc_18002FA9E
0x18002fa10  mov     edx, 36h ; '6'
0x18002fa15  jmp     loc_18002FC91
0x18002fa1a  mov     r8d, [rsp+530h+var_4E0]; int
0x18002fa1f  lea     rax, [rsp+530h+var_500]
0x18002fa24  mov     rcx, [rbp+430h+var_498]; void *
0x18002fa28  mov     r9, r12; struct _SID *
0x18002fa2b  mov     [rsp+530h+var_508], rax; int *
0x18002fa30  mov     edx, r15d; int
0x18002fa33  mov     [rsp+530h+var_510], rdi; struct _SID *
0x18002fa38  call    ?FwMoneisValidateAppContainerOperation@@YAKPEAXHHPEAU_SID@@1PEAH@Z; FwMoneisValidateAppContainerOperation(void *,int,int,_SID *,_SID *,int *)
0x18002fa3d  mov     ebx, eax
0x18002fa3f  test    eax, eax
0x18002fa41  jz      short loc_18002FA66
0x18002fa43  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fa4a  lea     r15, WPP_GLOBAL_Control
0x18002fa51  cmp     rcx, r15
0x18002fa54  jz      short loc_18002FA9E
0x18002fa56  test    byte ptr [rcx+1Ch], 1
0x18002fa5a  jz      short loc_18002FA9E
0x18002fa5c  mov     edx, 37h ; '7'
0x18002fa61  jmp     loc_18002FC91
0x18002fa66  cmp     [rsp+530h+var_500], 0
0x18002fa6b  jnz     short loc_18002FAA8
0x18002fa6d  xor     ebx, ebx
0x18002fa6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fa76  lea     r15, WPP_GLOBAL_Control
0x18002fa7d  cmp     rcx, r15
0x18002fa80  jz      short loc_18002FA9E
0x18002fa82  test    byte ptr [rcx+1Ch], 1
0x18002fa86  jz      short loc_18002FA9E
0x18002fa88  lea     edx, [rbx+38h]
0x18002fa8b  xor     r9d, r9d
0x18002fa8e  mov     rcx, [rcx+10h]
0x18002fa92  lea     r8, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids
0x18002fa99  call    WPP_SF_d
0x18002fa9e  mov     r13, [rsp+530h+var_4E8]
0x18002faa3  jmp     loc_1800307B0
0x18002faa8  mov     rcx, cs:?gSidManager@@3V?$unique_ptr@VSidManagement@appIsolation@@U?$default_delete@VSidManagement@appIsolation@@@wistd@@@wistd@@A; this
0x18002faaf  lea     rdx, [rbp+430h+var_1B0]; int *
0x18002fab6  mov     r9d, r13d; unsigned int
0x18002fab9  mov     r8, r14; struct _SID_AND_ATTRIBUTES *
0x18002fabc  call    ?ComputeAppContainerSidsPresence@SidManagement@appIsolation@@QEAAXPEAHPEAU_SID_AND_ATTRIBUTES@@K@Z; appIsolation::SidManagement::ComputeAppContainerSidsPresence(int *,_SID_AND_ATTRIBUTES *,ulong)
0x18002fac1  lea     r8, [rbp+430h+var_4A8]; void **
0x18002fac5  mov     ecx, r15d; int
0x18002fac8  lea     rdx, [rbp+430h+var_4A0]; void **
0x18002facc  call    ?FwMoneisOpenStores@@YAKHPEAPEAX0@Z; FwMoneisOpenStores(int,void * *,void * *)
0x18002fad1  mov     ebx, eax
0x18002fad3  test    eax, eax
0x18002fad5  jz      short loc_18002FAFA
0x18002fad7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fade  lea     r15, WPP_GLOBAL_Control
0x18002fae5  cmp     rcx, r15
0x18002fae8  jz      short loc_18002FA9E
0x18002faea  test    byte ptr [rcx+1Ch], 1
0x18002faee  jz      short loc_18002FA9E
0x18002faf0  mov     edx, 39h ; '9'
0x18002faf5  jmp     loc_18002FC91
0x18002fafa  lea     rdx, [rbp+430h+StringSid]; StringSid
0x18002fafe  mov     rcx, r12; Sid
0x18002fb01  xor     r15d, r15d
0x18002fb04  call    cs:__imp_ConvertSidToStringSidW
0x18002fb0a  test    eax, eax
0x18002fb0c  jnz     short loc_18002FB56
0x18002fb0e  call    cs:__imp_GetLastError
0x18002fb14  mov     ebx, eax
0x18002fb16  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb1d  lea     r14, WPP_GLOBAL_Control
0x18002fb24  lea     esi, [r15+1]
0x18002fb28  cmp     rcx, r14
0x18002fb2b  jz      loc_180030754
0x18002fb31  test    [rcx+1Ch], sil
0x18002fb35  jz      loc_180030754
0x18002fb3b  lea     edx, [rsi+39h]
0x18002fb3e  mov     rcx, [rcx+10h]
0x18002fb42  lea     r8, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids
0x18002fb49  mov     r9d, eax
0x18002fb4c  call    WPP_SF_d
0x18002fb51  jmp     loc_180030754
0x18002fb56  lea     rdx, [rbp+430h+var_450]; StringSid
0x18002fb5a  mov     rcx, rdi; Sid
0x18002fb5d  call    cs:__imp_ConvertSidToStringSidW
0x18002fb63  test    eax, eax
0x18002fb65  jnz     short loc_18002FB9A
0x18002fb67  call    cs:__imp_GetLastError
0x18002fb6d  mov     ebx, eax
0x18002fb6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb76  lea     r14, WPP_GLOBAL_Control
0x18002fb7d  mov     esi, 1
0x18002fb82  cmp     rcx, r14
0x18002fb85  jz      loc_180030754
0x18002fb8b  test    [rcx+1Ch], sil
0x18002fb8f  jz      loc_180030754
0x18002fb95  lea     edx, [rsi+3Ah]
0x18002fb98  jmp     short loc_18002FB3E
0x18002fb9a  mov     r8, [rbp+430h+StringSid]
0x18002fb9e  lea     rcx, [rbp+430h+var_448]
0x18002fba2  mov     rdx, [rbp+430h+var_450]
0x18002fba6  xor     r9d, r9d
0x18002fba9  call    cs:__imp_FwStringBuild
0x18002fbaf  mov     ecx, eax
0x18002fbb1  call    cs:__imp_FwHResultToWindowsError
0x18002fbb7  mov     ebx, eax
0x18002fbb9  test    eax, eax
0x18002fbbb  jz      short loc_18002FBE8
0x18002fbbd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fbc4  lea     r15, WPP_GLOBAL_Control
0x18002fbcb  cmp     rcx, r15
0x18002fbce  jz      loc_18002FA9E
0x18002fbd4  test    byte ptr [rcx+1Ch], 1
0x18002fbd8  jz      loc_18002FA9E
0x18002fbde  mov     edx, 3Ch ; '<'
0x18002fbe3  jmp     loc_18002FC91
0x18002fbe8  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x18002fbef  lea     r8, [rbp+430h+var_240]
0x18002fbf6  mov     eax, 221h
0x18002fbfb  mov     [rbp+430h+var_240], r15
0x18002fc02  mov     [rbp+430h+var_238], ax
0x18002fc09  mov     edx, 3
0x18002fc0e  mov     rax, [rbp+430h+var_448]
0x18002fc12  mov     [rbp+430h+var_230], rax
0x18002fc19  mov     rax, [rbp+430h+var_458]
0x18002fc1d  mov     [rbp+430h+var_218], rax
0x18002fc24  mov     rax, [rsp+530h+var_4B8]
0x18002fc29  mov     [rbp+430h+var_210], rax
0x18002fc30  mov     [rbp+430h+var_228], rdi
0x18002fc37  mov     [rbp+430h+var_220], r12
0x18002fc3e  mov     [rbp+430h+var_208], rsi
0x18002fc45  mov     [rbp+430h+var_200], r13d
0x18002fc4c  mov     [rbp+430h+var_1F8], r14
0x18002fc53  mov     rcx, [rcx+60h]
0x18002fc57  call    cs:__imp_FwAddRule
0x18002fc5d  mov     ecx, eax
0x18002fc5f  call    cs:__imp_FwHResultToWindowsError
0x18002fc65  mov     ebx, eax
0x18002fc67  test    eax, eax
0x18002fc69  jz      short loc_18002FC99
0x18002fc6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fc72  lea     r15, WPP_GLOBAL_Control
0x18002fc79  cmp     rcx, r15
0x18002fc7c  jz      loc_18002FA9E
0x18002fc82  test    byte ptr [rcx+1Ch], 1
0x18002fc86  jz      loc_18002FA9E
0x18002fc8c  mov     edx, 3Dh ; '='
0x18002fc91  mov     r9d, eax
0x18002fc94  jmp     loc_18002FA8E
0x18002fc99  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_042024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024> `wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl(void)'::`2'::impl
0x18002fca0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(void)
0x18002fca5  test    al, al
0x18002fca7  jz      short loc_18002FCF8
0x18002fca9  mov     rcx, rdi; pSid2
0x18002fcac  call    ?FwMoneisUpdatePackageIdConditions@@YAKPEAU_SID@@@Z; FwMoneisUpdatePackageIdConditions(_SID *)
0x18002fcb1  mov     ebx, eax
0x18002fcb3  test    eax, eax
0x18002fcb5  jz      short loc_18002FCF8
0x18002fcb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fcbe  lea     r14, WPP_GLOBAL_Control
0x18002fcc5  mov     esi, 1
0x18002fcca  cmp     rcx, r14
0x18002fccd  jz      loc_18003075D
0x18002fcd3  test    [rcx+1Ch], sil
0x18002fcd7  jz      loc_18003075D
0x18002fcdd  mov     rcx, [rcx+10h]
0x18002fce1  lea     edx, [rsi+3Dh]
0x18002fce4  mov     r9d, eax
0x18002fce7  lea     r8, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids
0x18002fcee  call    WPP_SF_d
0x18002fcf3  jmp     loc_18003075D
0x18002fcf8  mov     rdi, cs:?gInboxAppContainerManager@@3V?$unique_ptr@VInboxAppContainerManager@appIsolation@@U?$default_delete@VInboxAppContainerManager@appIsolation@@@wistd@@@wistd@@A; wistd::unique_ptr<appIsolation::InboxAppContainerManager,wistd::default_delete<appIsolation::InboxAppContainerManager>> gInboxAppContainerManager
0x18002fcff  mov     r15d, 1
0x18002fd05  mov     [rsp+530h+var_500], r15d
0x18002fd0a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall> `wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl(void)'::`2'::impl
0x18002fd11  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(void)
0x18002fd16  xor     r12d, r12d
  ... truncated ...
```
