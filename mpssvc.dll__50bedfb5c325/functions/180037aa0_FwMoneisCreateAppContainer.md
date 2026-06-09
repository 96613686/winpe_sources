# FwMoneisCreateAppContainer

- ea: `0x180037aa0`
- end: `0x180038c13`
- name: `FwMoneisCreateAppContainer`
- size: `4467`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800379f0`
- `0x1800bc0b0`

## callees

- `0x1800089bc`
- `0x180008a80`
- `0x1800097b0`
- `0x18000a710`
- `0x1800192e0`
- `0x18002809c`
- `0x18002d340`
- `0x18002ee68`
- `0x180037aa0`
- `0x180038c1c`
- `0x18003cfe0`
- `0x1800511b4`
- `0x18005240c`
- `0x180057928`
- `0x180057bd0`
- `0x18005db50`
- `0x18006649c`
- `0x1800729c0`
- `0x180073488`
- `0x180094610`
- `0x1800b30d8`
- `0x1800bb910`
- `0x1800bcadc`
- `0x1800c2860`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180037bb6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180038b18`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180037bb6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180038b18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037ddf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037e44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037ddf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037e44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038aea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038aff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038aea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038aff`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180037dcf`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180037e34`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180037dcf`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180037e34`
- `fwbase!FwHResultToWindowsError` at `0x180037e9a`
- `fwbase!FwHResultToWindowsError` at `0x180037f54`
- `fwbase!FwHResultToWindowsError` at `0x180038961`
- `fwbase!FwHResultToWindowsError` at `0x18003899d`
- `fwbase!FwHResultToWindowsError` at `0x180037e9a`
- `fwbase!FwHResultToWindowsError` at `0x180037f54`
- `fwbase!FwHResultToWindowsError` at `0x180038961`
- `fwbase!FwHResultToWindowsError` at `0x18003899d`
- `fwbase!FwStringBuild` at `0x180037e8c`
- `fwbase!FwStringBuild` at `0x180037e8c`
- `fwbase!FwCriticalSectionEnter` at `0x180038b4c`
- `fwbase!FwCriticalSectionEnter` at `0x180038b4c`
- `fwbase!FwCriticalSectionLeave` at `0x180038bad`
- `fwbase!FwCriticalSectionLeave` at `0x180038bad`
- `fwbase!FwFree` at `0x180038ad5`
- `fwbase!FwFree` at `0x180038ad5`
- `FWPolicyIOMgr!FwAddRule` at `0x180037f46`
- `FWPolicyIOMgr!FwAddRule` at `0x180037f46`

## string_xrefs

- `0x1800389e7`: `FwMoneisCreateAppContainer`
- `0x180038a03`: `FwMoneisCreateAppContainer`

## pseudocode

```c
__int64 __fastcall FwMoneisCreateAppContainer(
        void *a1,
        int a2,
        SID *a3,
        struct _SID *a4,
        __int64 a5,
        unsigned __int16 *a6,
        __int64 a7,
        struct _SID_AND_ATTRIBUTES *a8,
        unsigned int a9)
{
  struct _SID *v9; // r14
  SID_AND_ATTRIBUTES *v10; // rsi
  struct _SID *v11; // r12
  ULONGLONG TickCount64; // rax
  unsigned __int64 v14; // rcx
  ULONGLONG v15; // r13
  unsigned int v16; // ebx
  unsigned int IsChildAppContainer; // eax
  volatile unsigned int v18; // r9d
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  int v22; // r15d
  DWORD LastError; // eax
  __int64 v24; // rcx
  char v25; // si
  __int64 v26; // rdx
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int updated; // eax
  int v30; // r12d
  __int64 v31; // rdx
  void *v32; // rdi
  int v33; // eax
  __int64 v34; // rcx
  __int64 v35; // rdx
  int v36; // r15d
  int v37; // eax
  __int64 v38; // rcx
  __int64 v39; // rdx
  int v40; // esi
  int v41; // r14d
  void *v42; // rdi
  int v43; // eax
  bool v44; // zf
  int v45; // eax
  __int64 v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // rdi
  unsigned int v49; // eax
  __int64 v50; // rcx
  __int64 v51; // rdx
  unsigned int v52; // eax
  unsigned int v53; // eax
  ULONGLONG v54; // rdi
  __int64 v55; // rcx
  int v56; // r14d
  unsigned __int64 v57; // rdx
  unsigned int v58; // ecx
  __int64 v59; // rcx
  int v61; // [rsp+30h] [rbp-D0h] BYREF
  SID *v62; // [rsp+38h] [rbp-C8h]
  ULONGLONG v63; // [rsp+40h] [rbp-C0h]
  int v64; // [rsp+48h] [rbp-B8h] BYREF
  int v65; // [rsp+4Ch] [rbp-B4h]
  _QWORD v66[4]; // [rsp+50h] [rbp-B0h] BYREF
  struct _SID *v67; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v68; // [rsp+78h] [rbp-88h]
  struct _SID_AND_ATTRIBUTES *v69; // [rsp+80h] [rbp-80h]
  void *v70; // [rsp+88h] [rbp-78h] BYREF
  void *v71; // [rsp+90h] [rbp-70h] BYREF
  void *v72; // [rsp+98h] [rbp-68h]
  struct _INET_FIREWALL_AC_CHANGE v73; // [rsp+A0h] [rbp-60h] BYREF
  LPWSTR StringSid; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v75; // [rsp+D8h] [rbp-28h] BYREF
  LPWSTR v76; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v77; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v78[8]; // [rsp+F0h] [rbp-10h] BYREF
  __int16 v79; // [rsp+F8h] [rbp-8h]
  unsigned __int16 *v80; // [rsp+108h] [rbp+8h]
  __int64 v81; // [rsp+110h] [rbp+10h]
  int v82; // [rsp+118h] [rbp+18h]
  int v83; // [rsp+11Ch] [rbp+1Ch]
  __int16 v84; // [rsp+120h] [rbp+20h]
  __int64 v85; // [rsp+1A0h] [rbp+A0h]
  int v86; // [rsp+1F8h] [rbp+F8h]
  int v87; // [rsp+210h] [rbp+110h]
  __int16 v88; // [rsp+214h] [rbp+114h]
  unsigned __int16 *v89; // [rsp+228h] [rbp+128h]
  int v90; // [rsp+230h] [rbp+130h]
  int *v91; // [rsp+238h] [rbp+138h]
  __int64 v92; // [rsp+260h] [rbp+160h]
  LPWSTR v93; // [rsp+268h] [rbp+168h]
  LPWSTR v94; // [rsp+270h] [rbp+170h]
  int v95; // [rsp+278h] [rbp+178h]
  __int16 v96; // [rsp+298h] [rbp+198h]
  __int64 v97; // [rsp+2E0h] [rbp+1E0h]
  __int64 v98; // [rsp+2F0h] [rbp+1F0h] BYREF
  __int16 v99; // [rsp+2F8h] [rbp+1F8h]
  __int64 v100; // [rsp+300h] [rbp+200h]
  struct _SID *v101; // [rsp+308h] [rbp+208h]
  struct _SID *v102; // [rsp+310h] [rbp+210h]
  __int64 v103; // [rsp+318h] [rbp+218h]
  unsigned __int16 *v104; // [rsp+320h] [rbp+220h]
  __int64 v105; // [rsp+328h] [rbp+228h]
  unsigned int v106; // [rsp+330h] [rbp+230h]
  struct _SID_AND_ATTRIBUTES *v107; // [rsp+338h] [rbp+238h]
  int v108; // [rsp+370h] [rbp+270h] BYREF
  __int64 v109; // [rsp+378h] [rbp+278h] BYREF
  int v110[4]; // [rsp+380h] [rbp+280h] BYREF
  _BYTE v111[336]; // [rsp+390h] [rbp+290h] BYREF

  v9 = a4;
  v10 = a8;
  v11 = a3;
  v75 = a5;
  v68 = a6;
  v67 = a4;
  v62 = a3;
  v65 = a2;
  v72 = a1;
  v69 = a8;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 56, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids);
  v64 = 0;
  v61 = 0;
  v71 = 0;
  v70 = 0;
  *(_OWORD *)v110 = 0;
  StringSid = 0;
  v76 = 0;
  v77 = 0;
  memset_0(&v98, 0, 0x78u);
  *(&v73.binaries.count + 1) = 0;
  memset_0(v78, 0, 0x1F8u);
  v108 = 132608;
  v109 = 161;
  memset_0(v111, 0, 0x142u);
  TickCount64 = GetTickCount64();
  v14 = -1;
  v15 = TickCount64;
  v63 = TickCount64;
  v66[0] = v111;
  v66[1] = &v109;
  v66[2] = &v75;
  v66[3] = v78;
  do
    ++v14;
  while ( *(_WORD *)(v75 + 2 * v14) );
  if ( v14 <= 0x40 )
  {
    if ( !v14 )
      goto LABEL_9;
    IsChildAppContainer = FwMoneisValidateCapabilitySids(a8, a9);
    v16 = IsChildAppContainer;
    if ( IsChildAppContainer )
    {
      v19 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || ((unsigned __int8)v18 & *(_BYTE *)(WPP_GLOBAL_Control + 28LL)) == 0 )
      {
        goto LABEL_29;
      }
      v20 = 58;
      goto LABEL_51;
    }
    DelaySignaled = v18;
    IsChildAppContainer = FwMoneisIsChildAppContainer(v9, &v64);
    v16 = IsChildAppContainer;
    if ( IsChildAppContainer )
    {
      v19 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_29;
      v20 = 59;
      goto LABEL_51;
    }
    IsChildAppContainer = FwMoneisValidateAppContainerOperation(v72, a2, v64, v11, v9, &v61);
    v16 = IsChildAppContainer;
    if ( IsChildAppContainer )
    {
      v19 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_29;
      v20 = 60;
      goto LABEL_51;
    }
    if ( !v61 )
    {
      v16 = 0;
      v19 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_29;
      v20 = 61;
      v21 = 0;
      goto LABEL_28;
    }
    FwMoneisComputeAppContainerSidsPresence(v110, a8, a9);
    IsChildAppContainer = FwMoneisOpenStores(a2, &v71, &v70);
    v16 = IsChildAppContainer;
    if ( IsChildAppContainer )
    {
      v19 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_29;
      v20 = 62;
      goto LABEL_51;
    }
    v22 = 0;
    if ( !ConvertSidToStringSidW(v11, &StringSid) )
    {
      LastError = GetLastError();
      v16 = LastError;
      v24 = WPP_GLOBAL_Control;
      v25 = 1;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_192;
      v26 = 63;
      goto LABEL_38;
    }
    if ( !ConvertSidToStringSidW(v9, &v76) )
    {
      LastError = GetLastError();
      v16 = LastError;
      v24 = WPP_GLOBAL_Control;
      v25 = 1;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_192;
      v26 = 64;
LABEL_38:
      WPP_SF_d(*(_QWORD *)(v24 + 16), v26, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids, LastError);
      goto LABEL_192;
    }
    v27 = FwStringBuild(&v77, v76, StringSid, 0);
    IsChildAppContainer = FwHResultToWindowsError(v27);
    v16 = IsChildAppContainer;
    if ( IsChildAppContainer )
    {
      v19 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_29;
      v20 = 65;
      goto LABEL_51;
    }
    v98 = 0;
    v99 = 545;
    v100 = v77;
    v103 = v75;
    v104 = v68;
    v101 = v9;
    v102 = v11;
    v105 = a7;
    v106 = a9;
    v107 = a8;
    v28 = FwAddRule(*((_QWORD *)gFwIsolationManager + 9), 3, &v98);
    IsChildAppContainer = FwHResultToWindowsError(v28);
    v16 = IsChildAppContainer;
    if ( IsChildAppContainer )
    {
      v19 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_29;
      v20 = 66;
LABEL_51:
      v21 = IsChildAppContainer;
LABEL_28:
      WPP_SF_d(*(_QWORD *)(v19 + 16), v20, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids, v21);
LABEL_29:
      v15 = v63;
      goto LABEL_199;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl'::`2'::impl) )
    {
      updated = FwMoneisUpdatePackageIdConditions(v9);
      v16 = updated;
      if ( updated )
      {
        v25 = 1;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 67, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids, updated);
        goto LABEL_195;
      }
    }
    v22 = 1;
    v61 = 1;
    v30 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl'::`2'::impl) )
      LOBYTE(v30) = dword_18012FC20 == 0;
    else
      LOBYTE(v30) = dword_18012FC20 == 0;
    if ( v64 )
    {
LABEL_176:
      if ( v30 )
      {
        v48 = (unsigned int)FwLock();
        v49 = FwHResultToWindowsError(v48);
        v16 = v49;
        if ( v49 )
        {
          v50 = WPP_GLOBAL_Control;
          v25 = 1;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v51 = 87;
LABEL_185:
            WPP_SF_d(*(_QWORD *)(v50 + 16), v51, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids, v49);
            goto LABEL_186;
          }
          goto LABEL_186;
        }
        v52 = FwUpdateFlushDelayedEnforced();
        v49 = FwHResultToWindowsError(v52);
        v16 = v49;
        if ( v49 )
        {
          v50 = WPP_GLOBAL_Control;
          v25 = 1;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v51 = 88;
            goto LABEL_185;
          }
LABEL_186:
          if ( (int)v48 >= 0 )
          {
            FwUnlockInternal(0, "FwMoneisCreateAppContainer");
            v11 = v62;
            goto LABEL_192;
          }
          goto LABEL_191;
        }
        FwUnlockInternal(0, "FwMoneisCreateAppContainer");
      }
      v11 = v62;
      v73.changeType = INET_FIREWALL_AC_CHANGE_CREATE;
      v73.createType = INET_FIREWALL_AC_PACKAGE_ID_ONLY;
      v73.displayName = v68;
      v73.userSid = v62;
      v73.appContainerSid = v9;
      v73.capabilities.count = a9;
      v73.capabilities.capabilities = v10;
      appIsolation::IsolationEvents::FwMoneisSendNotification(Block, v64, &v73);
      v25 = 1;
      goto LABEL_192;
    }
    memset_0(v78, 0, 0x1F8u);
    v81 = a7;
    v79 = 545;
    v25 = 1;
    v80 = v68;
    v89 = v68;
    v94 = StringSid;
    v88 = 1;
    v84 = 256;
    LOBYTE(v31) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppContainerPFN>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_AppContainerPFN>::GetImpl'::`2'::impl,
      v31);
    if ( v75 )
      v97 = v75;
    else
      v93 = v76;
    v32 = v71;
    v96 |= 8u;
    v87 = 2;
    v82 = 0x7FFFFFFF;
    v83 = 1;
    v33 = lambda_c2ad1a2ccf19b9d3d2263dbe0dc3c75c_::operator()(v66, L"-In-Block", v71, StringSid);
    if ( v33 < 0 )
    {
      v34 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_191;
      v35 = 68;
      goto LABEL_68;
    }
    v83 = 2;
    v33 = lambda_c2ad1a2ccf19b9d3d2263dbe0dc3c75c_::operator()(v66, L"-Out-Block", v32, StringSid);
    if ( v33 < 0 )
    {
      v34 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_191;
      v35 = 69;
      goto LABEL_68;
    }
    v87 = 3;
    if ( v110[3] == 1 )
    {
      v92 = *((_QWORD *)off_18012FBB8 + 10);
      v95 = 1;
      v83 = 1;
      v33 = lambda_c2ad1a2ccf19b9d3d2263dbe0dc3c75c_::operator()(v66, L"-In-Allow-Proximity", v32, StringSid);
      if ( v33 < 0 )
      {
        v34 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_191;
        v35 = 70;
        goto LABEL_68;
      }
      v83 = 2;
      v33 = lambda_c2ad1a2ccf19b9d3d2263dbe0dc3c75c_::operator()(v66, L"-Out-Allow-Proximity", v32, StringSid);
      if ( v33 < 0 )
      {
        v34 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_191;
        v35 = 71;
        goto LABEL_68;
      }
      v95 = 16;
      v86 = 2;
      v83 = 1;
      v33 = lambda_c2ad1a2ccf19b9d3d2263dbe0dc3c75c_::operator()(v66, L"-In-Allow-Proximity-Wireless", v32, StringSid);
      if ( v33 < 0 )
      {
        v34 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_191;
        v35 = 72;
        goto LABEL_68;
      }
      v83 = 2;
      v33 = lambda_c2ad1a2ccf19b9d3d2263dbe0dc3c75c_::operator()(v66, L"-Out-Allow-Proximity-Wireless", v32, StringSid);
      if ( v33 < 0 )
      {
        v34 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_191;
        v35 = 73;
LABEL_68:
        WPP_SF_d(*(_QWORD *)(v34 + 16), v35, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids, (unsigned int)v33);
LABEL_191:
        v11 = v62;
LABEL_192:
        if ( !v16 || !v22 )
        {
LABEL_198:
          v15 = v63;
          goto LABEL_199;
        }
        v9 = v67;
LABEL_195:
        v53 = FwMoneisDeleteAppContainer(v72, v65, v11, v9, v68);
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && ((unsigned __int8)v25 & *(_BYTE *)(WPP_GLOBAL_Control + 28LL)) != 0 )
        {
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 89, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids, v53);
        }
        goto LABEL_198;
      }
      v95 = 0;
      v86 = 0;
    }
    v36 = v110[2];
    if ( v110[2] == 1 )
    {
      v92 = *((_QWORD *)off_18012FBB8 + 7);
      v82 = 7;
      v85 = 0x2000000020LL;
      v83 = 1;
      v37 = lambda_c2ad1a2ccf19b9d3d2263dbe0dc3c75c_::operator()(v66, L"-In-Allow-Intranet", v32, StringSid);
      if ( v37 < 0 )
      {
        v38 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v39 = 74;
        goto LABEL_96;
      }
      v83 = 2;
      v37 = lambda_c2ad1a2ccf19b9d3d2263dbe0dc3c75c_::operator()(v66, L"-Out-Allow-Intranet", v32, StringSid);
      if ( v37 < 0 )
      {
        v38 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v39 = 75;
        goto LABEL_96;
      }
      v83 = 1;
      v88 |= 2u;
      v82 = 6;
      v85 = 0x10000000100LL;
      v37 = lambda_c2ad1a2ccf19b9d3d2263dbe0dc3c75c_::operator()(
              v66,
              L"-In-Allow-Intranet-Authenticate",
              v32,
              StringSid);
      if ( v37 < 0 )
      {
        v38 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v39 = 76;
        goto LABEL_96;
      }
      v83 = 2;
      v37 = lambda_c2ad1a2ccf19b9d3d2263dbe0dc3c75c_::operator()(
              v66,
              L"-Out-Allow-Intranet-Authenticate",
              v32,
              StringSid);
      if ( v37 < 0 )
      {
        v38 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v39 = 77;
        goto LABEL_96;
      }
      v88 &= ~2u;
    }
    v40 = v110[0];
    v41 = v110[1];
    if ( v110[0] == 1 )
    {
      v92 = *((_QWORD *)off_18012FBB8 + 1);
      v83 = 1;
      v82 = 7;
      v85 = 0x4000000040LL;
      v37 = lambda_c2ad1a2ccf19b9d3d2263dbe0dc3c75c_::operator()(v66, L"-In-Allow-Internet", v32, StringSid);
      if ( v37 < 0 )
      {
        v38 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          v25 = 1;
          if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_97;
          v39 = 78;
LABEL_96:
          WPP_SF_d(*(_QWORD *)(v38 + 16), v39, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids, (unsigned int)v37);
LABEL_97:
          v22 = 1;
          goto LABEL_191;
        }
LABEL_190:
        v22 = v61;
        v25 = v61;
        goto LABEL_191;
      }
      v83 = 2;
      v37 = lambda_c2ad1a2ccf19b9d3d2263dbe0dc3c75c_::operator()(v66, L"-Out-Allow-Internet", v32, StringSid);
      if ( v37 < 0 )
      {
        v38 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          v25 = 1;
          if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_97;
          v39 = 79;
          goto LABEL_96;
        }
        goto LABEL_190;
      }
    }
    else if ( !v110[0] && v110[1] == 1 )
    {
      v92 = *((_QWORD *)off_18012FBB8 + 4);
      v82 = 7;
      v85 = 0x4000000040LL;
      v83 = 2;
      v37 = lambda_c2ad1a2ccf19b9d3d2263dbe0dc3c75c_::operator()(v66, L"-Out-Allow-InternetClient", v32, StringSid);
      if ( v37 < 0 )
      {
        v38 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          v25 = 1;
          if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_97;
          v39 = 80;
          goto LABEL_96;
        }
        goto LABEL_190;
      }
    }
    if ( v65 != 1 )
      goto LABEL_175;
    v42 = v70;
    v91 = &v108;
    v82 = 0;
    v85 = 0;
    v92 = 0;
    v90 = 1;
    LOBYTE(v108) = 10;
    if ( v36 != 1 && v40 != 1 && v41 != 1 )
    {
LABEL_146:
      if ( v110[3] == 1 )
      {
        v95 = 1;
        v43 = 7;
        v82 = 7;
        v83 = 1;
        if ( v40 == 1 )
        {
          v82 = 3;
          if ( v36 != 1 )
            goto LABEL_153;
          v43 = 0;
          v82 = 0;
        }
        if ( !v40 )
          v88 |= 8u;
        if ( !v43 )
        {
LABEL_157:
          v95 = 16;
          v86 = 2;
          v82 = 4;
          v37 = lambda_c2ad1a2ccf19b9d3d2263dbe0dc3c75c_::operator()(v66, L"-In-Allow-WifiDirect", v42, StringSid);
          if ( v37 < 0 )
          {
            v38 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              v25 = 1;
              if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
                goto LABEL_97;
              v39 = 84;
              goto LABEL_96;
            }
            goto LABEL_190;
          }
          v86 = 0;
          v88 &= ~8u;
          v44 = v40 == 1;
          v95 = 1;
          v25 = 1;
          v82 = 7;
          v83 = 2;
          if ( !v44 && v41 != 1 || (v82 = 3, v36 != 1) )
          {
            v45 = lambda_c2ad1a2ccf19b9d3d2263dbe0dc3c75c_::operator()(v66, L"-Out-Allow-EdgeTraversal", v42, StringSid);
            if ( v45 < 0 )
            {
              v46 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
              {
                goto LABEL_169;
              }
              v47 = 85;
LABEL_168:
              WPP_SF_d(*(_QWORD *)(v46 + 16), v47, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids, (unsigned int)v45);
LABEL_169:
              v22 = v61;
              goto LABEL_191;
            }
          }
          v95 = 16;
          v86 = 2;
          v82 = 4;
          v45 = lambda_c2ad1a2ccf19b9d3d2263dbe0dc3c75c_::operator()(v66, L"-Out-Allow-WifiDirect", v42, StringSid);
          if ( v45 < 0 )
          {
            v46 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            {
              goto LABEL_169;
            }
            v47 = 86;
            goto LABEL_168;
          }
          v95 = 0;
          v86 = 0;
          goto LABEL_175;
        }
LABEL_153:
        v37 = lambda_c2ad1a2ccf19b9d3d2263dbe0dc3c75c_::operator()(v66, L"-In-Allow-EdgeTraversal", v42, StringSid);
        if ( v37 < 0 )
        {
          v38 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            v25 = 1;
            if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
              goto LABEL_97;
            v39 = 83;
            goto LABEL_96;
          }
          goto LABEL_190;
        }
        goto LABEL_157;
      }
LABEL_175:
      v10 = v69;
      v9 = v67;
      v22 = v61;
      goto LABEL_176;
    }
    v83 = 2;
    v82 = 3;
    if ( v40 == 1 || v41 == 1 )
      v82 = 7;
    v37 = lambda_c2ad1a2ccf19b9d3d2263dbe0dc3c75c_::operator()(v66, L"-Out-Allow-AllCapabilities", v70, StringSid);
    if ( v37 < 0 )
    {
      v38 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        v25 = 1;
        if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v39 = 81;
        goto LABEL_96;
      }
      goto LABEL_190;
    }
    v83 = 1;
    if ( v40 )
    {
      v88 |= 8u;
      if ( v40 == 1 )
        goto LABEL_141;
    }
    else
    {
      v82 &= ~4u;
    }
    if ( v36 != 1 )
    {
LABEL_145:
      v88 &= ~8u;
      goto LABEL_146;
    }
LABEL_141:
    v37 = lambda_c2ad1a2ccf19b9d3d2263dbe0dc3c75c_::operator()(v66, L"-In-Allow-ServerCapability", v42, StringSid);
    if ( v37 < 0 )
    {
      v38 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        v25 = 1;
        if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v39 = 82;
        goto LABEL_96;
      }
      goto LABEL_190;
    }
    goto LABEL_145;
  }
  MicrosoftTelemetryAssertTriggeredNoArgs(v14);
LABEL_9:
  v16 = 87;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 57, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids, 87);
LABEL_199:
  if ( v77 )
    FwFree(v77);
  if ( v76 )
    LocalFree(v76);
  if ( StringSid )
    LocalFree(StringSid);
  FwMoneisCloseStores(&v71, &v70);
  v54 = GetTickCount64();
  FwAggregateTelemetryEventWriteApiTimeout(v55, v54 - v15);
  if ( v54 - v15 > 0xBB8 )
  {
    v56 = 0;
    FwCriticalSectionEnter(&g_fwEventCriticalSection);
    v57 = g_fwEventLoggingStartTime;
    if ( g_fwEventLoggingStartTime && v54 - g_fwEventLoggingStartTime <= 0x3E8 )
    {
      v58 = g_fwEventCount;
    }
    else
    {
      v57 = v54;
      v58 = 0;
      g_fwEventLoggingStartTime = v54;
      g_fwEventCount = 0;
    }
    if ( v54 - v57 >= 28 * v58 )
    {
      v56 = 1;
      g_fwEventCount = v58 + 1;
    }
    FwCriticalSectionLeave(&g_fwEventCriticalSection);
    if ( v56 )
      FwTelemetryEventWriteApiTimeout(v59, v54 - v15);
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 90, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids);
  return v16;
}

```

## disassembly

```asm
0x180037aa0  push    rbp
0x180037aa2  push    rbx
0x180037aa3  push    rsi
0x180037aa4  push    rdi
0x180037aa5  push    r12
0x180037aa7  push    r13
0x180037aa9  push    r14
0x180037aab  push    r15
0x180037aad  lea     rbp, [rsp-3F8h]
0x180037ab5  sub     rsp, 4F8h
0x180037abc  mov     rax, cs:__security_cookie
0x180037ac3  xor     rax, rsp
0x180037ac6  mov     [rbp+430h+var_50], rax
0x180037acd  mov     rax, [rbp+430h+arg_20]
0x180037ad4  mov     r14, r9
0x180037ad7  mov     rsi, [rbp+430h+arg_38]
0x180037ade  mov     r12, r8
0x180037ae1  mov     rdi, [rbp+430h+arg_30]
0x180037ae8  mov     r15d, edx
0x180037aeb  mov     [rbp+430h+var_458], rax
0x180037aef  mov     rax, [rbp+430h+arg_28]
0x180037af6  mov     [rsp+530h+var_4B8], rax
0x180037afb  mov     [rsp+530h+var_4C0], r9
0x180037b00  mov     [rsp+530h+var_4F8], r8
0x180037b05  mov     [rsp+530h+var_4E4], edx
0x180037b09  mov     [rbp+430h+var_498], rcx
0x180037b0d  mov     [rbp+430h+var_4B0], rsi
0x180037b11  mov     rcx, cs:WPP_GLOBAL_Control
0x180037b18  lea     rax, WPP_GLOBAL_Control
0x180037b1f  cmp     rcx, rax
0x180037b22  jz      short loc_180037B3F
0x180037b24  test    byte ptr [rcx+1Ch], 8
0x180037b28  jz      short loc_180037B3F
0x180037b2a  mov     rcx, [rcx+10h]
0x180037b2e  lea     r8, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids
0x180037b35  mov     edx, 38h ; '8'
0x180037b3a  call    WPP_SF_
0x180037b3f  xor     ebx, ebx
0x180037b41  lea     rcx, [rbp+430h+var_240]; void *
0x180037b48  xorps   xmm0, xmm0
0x180037b4b  mov     [rsp+530h+var_4E8], ebx
0x180037b4f  xor     edx, edx; Val
0x180037b51  mov     [rsp+530h+var_500], ebx
0x180037b55  mov     [rbp+430h+var_4A0], rbx
0x180037b59  lea     r8d, [rbx+78h]; Size
0x180037b5d  mov     [rbp+430h+var_4A8], rbx
0x180037b61  movups  xmmword ptr [rbp+430h+var_1B0], xmm0
0x180037b68  mov     [rbp+430h+StringSid], rbx
0x180037b6c  mov     [rbp+430h+var_450], rbx
0x180037b70  mov     [rbp+430h+var_448], rbx
0x180037b74  call    memset_0
0x180037b79  xor     edx, edx; Val
0x180037b7b  mov     dword ptr [rbp+430h+var_490.20h+4], ebx
0x180037b7e  mov     r8d, 1F8h; Size
0x180037b84  lea     rcx, [rbp+430h+var_440]; void *
0x180037b88  call    memset_0
0x180037b8d  xor     edx, edx; Val
0x180037b8f  mov     [rbp+430h+var_1C0], 20600h
0x180037b99  mov     r8d, 142h; Size
0x180037b9f  mov     [rbp+430h+var_1B8], 0A1h
0x180037baa  lea     rcx, [rbp+430h+var_1A0]; void *
0x180037bb1  call    memset_0
0x180037bb6  call    cs:__imp_GetTickCount64
0x180037bbd  nop     dword ptr [rax+rax+00h]
0x180037bc2  mov     rdx, [rbp+430h+var_458]
0x180037bc6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180037bca  mov     r13, rax
0x180037bcd  mov     [rsp+530h+var_4F0], rax
0x180037bd2  lea     rax, [rbp+430h+var_1A0]
0x180037bd9  mov     [rsp+530h+var_4E0], rax
0x180037bde  lea     rax, [rbp+430h+var_1B8]
0x180037be5  mov     [rsp+530h+var_4D8], rax
0x180037bea  lea     rax, [rbp+430h+var_458]
0x180037bee  mov     [rsp+530h+var_4D0], rax
0x180037bf3  lea     rax, [rbp+430h+var_440]
0x180037bf7  mov     [rsp+530h+var_4C8], rax
0x180037bfc  inc     rcx
0x180037bff  cmp     [rdx+rcx*2], bx
0x180037c03  jnz     short loc_180037BFC
0x180037c05  mov     r9d, 1
0x180037c0b  cmp     rcx, 40h ; '@'
0x180037c0f  jbe     short loc_180037C1E
0x180037c11  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "(appContainerNameLength <= 64 || appContainerNameLength == 0)", "appContainerName is greater than 64 characters or 0")
0x180037c16  mov     r9d, 1
0x180037c1c  jmp     short loc_180037C23
0x180037c1e  test    rcx, rcx
0x180037c21  jnz     short loc_180037C64
0x180037c23  mov     ebx, 57h ; 'W'
0x180037c28  mov     rcx, cs:WPP_GLOBAL_Control
0x180037c2f  lea     rdi, WPP_GLOBAL_Control
0x180037c36  cmp     rcx, rdi
0x180037c39  jz      loc_180038AC5
0x180037c3f  test    [rcx+1Ch], r9b
0x180037c43  jz      loc_180038AC5
0x180037c49  mov     rcx, [rcx+10h]
0x180037c4d  lea     edx, [rbx-1Eh]
0x180037c50  mov     r9d, ebx
0x180037c53  lea     r8, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids
0x180037c5a  call    WPP_SF_d
0x180037c5f  jmp     loc_180038AC5
0x180037c64  mov     r13d, [rbp+430h+arg_40]
0x180037c6b  mov     rcx, rsi; struct _SID_AND_ATTRIBUTES *
0x180037c6e  mov     edx, r13d; unsigned int
0x180037c71  call    ?FwMoneisValidateCapabilitySids@@YAKPEAU_SID_AND_ATTRIBUTES@@K@Z; FwMoneisValidateCapabilitySids(_SID_AND_ATTRIBUTES *,ulong)
0x180037c76  mov     ebx, eax
0x180037c78  test    eax, eax
0x180037c7a  jz      short loc_180037CA7
0x180037c7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180037c83  lea     r12, WPP_GLOBAL_Control
0x180037c8a  cmp     rcx, r12
0x180037c8d  jz      loc_180037D70
0x180037c93  test    [rcx+1Ch], r9b
0x180037c97  jz      loc_180037D70
0x180037c9d  mov     edx, 3Ah ; ':'
0x180037ca2  jmp     loc_180037F8C
0x180037ca7  lea     rdx, [rsp+530h+var_4E8]; int *
0x180037cac  mov     cs:?DelaySignaled@@3KC, r9d; ulong volatile DelaySignaled
0x180037cb3  mov     rcx, r14; struct _SID *
0x180037cb6  call    ?FwMoneisIsChildAppContainer@@YAKPEAU_SID@@PEAH@Z; FwMoneisIsChildAppContainer(_SID *,int *)
0x180037cbb  mov     ebx, eax
0x180037cbd  test    eax, eax
0x180037cbf  jz      short loc_180037CEC
0x180037cc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180037cc8  lea     r12, WPP_GLOBAL_Control
0x180037ccf  cmp     rcx, r12
0x180037cd2  jz      loc_180037D70
0x180037cd8  test    byte ptr [rcx+1Ch], 1
0x180037cdc  jz      loc_180037D70
0x180037ce2  mov     edx, 3Bh ; ';'
0x180037ce7  jmp     loc_180037F8C
0x180037cec  mov     r8d, [rsp+530h+var_4E8]; int
0x180037cf1  lea     rax, [rsp+530h+var_500]
0x180037cf6  mov     rcx, [rbp+430h+var_498]; void *
0x180037cfa  mov     r9, r12; struct _SID *
0x180037cfd  mov     [rsp+530h+var_508], rax; int *
0x180037d02  mov     edx, r15d; int
0x180037d05  mov     [rsp+530h+var_510], r14; struct _SID *
0x180037d0a  call    ?FwMoneisValidateAppContainerOperation@@YAKPEAXHHPEAU_SID@@1PEAH@Z; FwMoneisValidateAppContainerOperation(void *,int,int,_SID *,_SID *,int *)
0x180037d0f  mov     ebx, eax
0x180037d11  test    eax, eax
0x180037d13  jz      short loc_180037D38
0x180037d15  mov     rcx, cs:WPP_GLOBAL_Control
0x180037d1c  lea     r12, WPP_GLOBAL_Control
0x180037d23  cmp     rcx, r12
0x180037d26  jz      short loc_180037D70
0x180037d28  test    byte ptr [rcx+1Ch], 1
0x180037d2c  jz      short loc_180037D70
0x180037d2e  mov     edx, 3Ch ; '<'
0x180037d33  jmp     loc_180037F8C
0x180037d38  cmp     [rsp+530h+var_500], 0
0x180037d3d  jnz     short loc_180037D7A
0x180037d3f  xor     ebx, ebx
0x180037d41  mov     rcx, cs:WPP_GLOBAL_Control
0x180037d48  lea     r12, WPP_GLOBAL_Control
0x180037d4f  cmp     rcx, r12
0x180037d52  jz      short loc_180037D70
0x180037d54  test    byte ptr [rcx+1Ch], 1
0x180037d58  jz      short loc_180037D70
0x180037d5a  lea     edx, [rbx+3Dh]
0x180037d5d  xor     r9d, r9d
0x180037d60  mov     rcx, [rcx+10h]
0x180037d64  lea     r8, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids
0x180037d6b  call    WPP_SF_d
0x180037d70  mov     r13, [rsp+530h+var_4F0]
0x180037d75  jmp     loc_180038ACC
0x180037d7a  mov     r8d, r13d; unsigned int
0x180037d7d  lea     rcx, [rbp+430h+var_1B0]; int *
0x180037d84  mov     rdx, rsi; struct _SID_AND_ATTRIBUTES *
0x180037d87  call    ?FwMoneisComputeAppContainerSidsPresence@@YAXPEAHPEAU_SID_AND_ATTRIBUTES@@K@Z; FwMoneisComputeAppContainerSidsPresence(int *,_SID_AND_ATTRIBUTES *,ulong)
0x180037d8c  lea     r8, [rbp+430h+var_4A8]; void **
0x180037d90  mov     ecx, r15d; int
0x180037d93  lea     rdx, [rbp+430h+var_4A0]; void **
0x180037d97  call    ?FwMoneisOpenStores@@YAKHPEAPEAX0@Z; FwMoneisOpenStores(int,void * *,void * *)
0x180037d9c  mov     ebx, eax
0x180037d9e  test    eax, eax
0x180037da0  jz      short loc_180037DC5
0x180037da2  mov     rcx, cs:WPP_GLOBAL_Control
0x180037da9  lea     r12, WPP_GLOBAL_Control
0x180037db0  cmp     rcx, r12
0x180037db3  jz      short loc_180037D70
0x180037db5  test    byte ptr [rcx+1Ch], 1
0x180037db9  jz      short loc_180037D70
0x180037dbb  mov     edx, 3Eh ; '>'
0x180037dc0  jmp     loc_180037F8C
0x180037dc5  lea     rdx, [rbp+430h+StringSid]; StringSid
0x180037dc9  mov     rcx, r12; Sid
0x180037dcc  xor     r15d, r15d
0x180037dcf  call    cs:__imp_ConvertSidToStringSidW
0x180037dd6  nop     dword ptr [rax+rax+00h]
0x180037ddb  test    eax, eax
0x180037ddd  jnz     short loc_180037E2D
0x180037ddf  call    cs:__imp_GetLastError
0x180037de6  nop     dword ptr [rax+rax+00h]
0x180037deb  mov     ebx, eax
0x180037ded  mov     rcx, cs:WPP_GLOBAL_Control
0x180037df4  lea     rdi, WPP_GLOBAL_Control
0x180037dfb  lea     esi, [r15+1]
0x180037dff  cmp     rcx, rdi
0x180037e02  jz      loc_180038A6B
0x180037e08  test    [rcx+1Ch], sil
0x180037e0c  jz      loc_180038A6B
0x180037e12  lea     edx, [rsi+3Eh]
0x180037e15  mov     rcx, [rcx+10h]
0x180037e19  lea     r8, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids
0x180037e20  mov     r9d, eax
0x180037e23  call    WPP_SF_d
0x180037e28  jmp     loc_180038A6B
0x180037e2d  lea     rdx, [rbp+430h+var_450]; StringSid
0x180037e31  mov     rcx, r14; Sid
0x180037e34  call    cs:__imp_ConvertSidToStringSidW
0x180037e3b  nop     dword ptr [rax+rax+00h]
0x180037e40  test    eax, eax
0x180037e42  jnz     short loc_180037E7D
0x180037e44  call    cs:__imp_GetLastError
0x180037e4b  nop     dword ptr [rax+rax+00h]
0x180037e50  mov     ebx, eax
0x180037e52  mov     rcx, cs:WPP_GLOBAL_Control
0x180037e59  lea     rdi, WPP_GLOBAL_Control
0x180037e60  mov     esi, 1
0x180037e65  cmp     rcx, rdi
0x180037e68  jz      loc_180038A6B
0x180037e6e  test    [rcx+1Ch], sil
0x180037e72  jz      loc_180038A6B
0x180037e78  lea     edx, [rsi+3Fh]
0x180037e7b  jmp     short loc_180037E15
0x180037e7d  mov     r8, [rbp+430h+StringSid]
0x180037e81  lea     rcx, [rbp+430h+var_448]
0x180037e85  mov     rdx, [rbp+430h+var_450]
0x180037e89  xor     r9d, r9d
0x180037e8c  call    cs:__imp_FwStringBuild
0x180037e93  nop     dword ptr [rax+rax+00h]
0x180037e98  mov     ecx, eax
0x180037e9a  call    cs:__imp_FwHResultToWindowsError
0x180037ea1  nop     dword ptr [rax+rax+00h]
0x180037ea6  mov     ebx, eax
0x180037ea8  test    eax, eax
0x180037eaa  jz      short loc_180037ED7
0x180037eac  mov     rcx, cs:WPP_GLOBAL_Control
0x180037eb3  lea     r12, WPP_GLOBAL_Control
0x180037eba  cmp     rcx, r12
0x180037ebd  jz      loc_180037D70
0x180037ec3  test    byte ptr [rcx+1Ch], 1
0x180037ec7  jz      loc_180037D70
0x180037ecd  mov     edx, 41h ; 'A'
0x180037ed2  jmp     loc_180037F8C
0x180037ed7  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x180037ede  lea     r8, [rbp+430h+var_240]
0x180037ee5  mov     eax, 221h
0x180037eea  mov     [rbp+430h+var_240], r15
0x180037ef1  mov     [rbp+430h+var_238], ax
0x180037ef8  mov     edx, 3
0x180037efd  mov     rax, [rbp+430h+var_448]
0x180037f01  mov     [rbp+430h+var_230], rax
0x180037f08  mov     rax, [rbp+430h+var_458]
0x180037f0c  mov     [rbp+430h+var_218], rax
0x180037f13  mov     rax, [rsp+530h+var_4B8]
0x180037f18  mov     [rbp+430h+var_210], rax
0x180037f1f  mov     [rbp+430h+var_228], r14
0x180037f26  mov     [rbp+430h+var_220], r12
0x180037f2d  mov     [rbp+430h+var_208], rdi
0x180037f34  mov     [rbp+430h+var_200], r13d
0x180037f3b  mov     [rbp+430h+var_1F8], rsi
0x180037f42  mov     rcx, [rcx+48h]
0x180037f46  call    cs:__imp_FwAddRule
0x180037f4d  nop     dword ptr [rax+rax+00h]
0x180037f52  mov     ecx, eax
0x180037f54  call    cs:__imp_FwHResultToWindowsError
0x180037f5b  nop     dword ptr [rax+rax+00h]
0x180037f60  mov     ebx, eax
0x180037f62  test    eax, eax
0x180037f64  jz      short loc_180037F94
0x180037f66  mov     rcx, cs:WPP_GLOBAL_Control
0x180037f6d  lea     r12, WPP_GLOBAL_Control
0x180037f74  cmp     rcx, r12
0x180037f77  jz      loc_180037D70
0x180037f7d  test    byte ptr [rcx+1Ch], 1
0x180037f81  jz      loc_180037D70
0x180037f87  mov     edx, 42h ; 'B'
0x180037f8c  mov     r9d, eax
0x180037f8f  jmp     loc_180037D60
0x180037f94  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_042024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024> `wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl(void)'::`2'::impl
0x180037f9b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(void)
0x180037fa0  test    al, al
0x180037fa2  jz      short loc_180037FF3
0x180037fa4  mov     rcx, r14; pSid2
0x180037fa7  call    ?FwMoneisUpdatePackageIdConditions@@YAKPEAU_SID@@@Z; FwMoneisUpdatePackageIdConditions(_SID *)
0x180037fac  mov     ebx, eax
0x180037fae  test    eax, eax
0x180037fb0  jz      short loc_180037FF3
0x180037fb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180037fb9  lea     rdi, WPP_GLOBAL_Control
0x180037fc0  mov     esi, 1
0x180037fc5  cmp     rcx, rdi
0x180037fc8  jz      loc_180038A79
0x180037fce  test    [rcx+1Ch], sil
0x180037fd2  jz      loc_180038A79
0x180037fd8  mov     rcx, [rcx+10h]
0x180037fdc  lea     edx, [rsi+42h]
0x180037fdf  mov     r9d, eax
0x180037fe2  lea     r8, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids
  ... truncated ...
```
