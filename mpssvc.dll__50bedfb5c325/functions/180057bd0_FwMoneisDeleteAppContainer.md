# FwMoneisDeleteAppContainer

- ea: `0x180057bd0`
- end: `0x18005876f`
- name: `FwMoneisDeleteAppContainer`
- size: `2975`
- prototype: `__int64 __fastcall(void *, int, struct _SID *, struct _SID *, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180037aa0`
- `0x180057b50`
- `0x1800bc0b0`
- `0x1800ce210`

## callees

- `0x18000a710`
- `0x18002ee68`
- `0x180034660`
- `0x180036220`
- `0x180038c1c`
- `0x180039644`
- `0x18003cfe0`
- `0x18003d708`
- `0x1800511b4`
- `0x180057bd0`
- `0x18005db50`
- `0x1800729c0`
- `0x1800c2860`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057d9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057def`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057d9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057def`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180058708`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005871d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180058708`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005871d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180057d8f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180057ddf`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180057d8f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180057ddf`
- `fwbase!FwHResultToWindowsError` at `0x180057e45`
- `fwbase!FwHResultToWindowsError` at `0x180057ea8`
- `fwbase!FwHResultToWindowsError` at `0x180058018`
- `fwbase!FwHResultToWindowsError` at `0x18005814c`
- `fwbase!FwHResultToWindowsError` at `0x180058235`
- `fwbase!FwHResultToWindowsError` at `0x180058359`
- `fwbase!FwHResultToWindowsError` at `0x18005848d`
- `fwbase!FwHResultToWindowsError` at `0x180058572`
- `fwbase!FwHResultToWindowsError` at `0x1800585d8`
- `fwbase!FwHResultToWindowsError` at `0x18005865d`
- `fwbase!FwHResultToWindowsError` at `0x1800586b7`
- `fwbase!FwHResultToWindowsError` at `0x180057e45`
- `fwbase!FwHResultToWindowsError` at `0x180057ea8`
- `fwbase!FwHResultToWindowsError` at `0x180058018`
- `fwbase!FwHResultToWindowsError` at `0x18005814c`
- `fwbase!FwHResultToWindowsError` at `0x180058235`
- `fwbase!FwHResultToWindowsError` at `0x180058359`
- `fwbase!FwHResultToWindowsError` at `0x18005848d`
- `fwbase!FwHResultToWindowsError` at `0x180058572`
- `fwbase!FwHResultToWindowsError` at `0x1800585d8`
- `fwbase!FwHResultToWindowsError` at `0x18005865d`
- `fwbase!FwHResultToWindowsError` at `0x1800586b7`
- `fwbase!FwStringBuild` at `0x180057e37`
- `fwbase!FwStringBuild` at `0x180057e37`
- `fwbase!FwFree` at `0x1800586f3`
- `fwbase!FwFree` at `0x1800586f3`
- `FWPolicyIOMgr!FwGetRule` at `0x180057e9a`
- `FWPolicyIOMgr!FwGetRule` at `0x180057e9a`
- `FWPolicyIOMgr!FwDeleteRule` at `0x1800585ca`
- `FWPolicyIOMgr!FwDeleteRule` at `0x1800585ca`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005800a`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005813e`
- `FWPolicyIOMgr!FwFreeRules` at `0x180058227`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005834b`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005847f`
- `FWPolicyIOMgr!FwFreeRules` at `0x180058564`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005864f`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800586a9`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005800a`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005813e`
- `FWPolicyIOMgr!FwFreeRules` at `0x180058227`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005834b`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005847f`
- `FWPolicyIOMgr!FwFreeRules` at `0x180058564`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005864f`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800586a9`

## pseudocode

```c
__int64 __fastcall FwMoneisDeleteAppContainer(void *a1, int a2, struct _SID *a3, struct _SID *a4, unsigned __int16 *a5)
{
  struct _tag_FW_RULE *v7; // rdi
  struct _SID *v8; // r12
  unsigned int IsChildAppContainer; // ebx
  DWORD LastError; // eax
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  unsigned int v15; // eax
  unsigned int Rule; // eax
  __int64 v17; // rdx
  __int64 v18; // r14
  void *v19; // r12
  unsigned int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rdx
  unsigned int v23; // eax
  __int64 v24; // rdx
  unsigned int v25; // eax
  void *v26; // rsi
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  struct _tag_FW_RULE *v35; // [rsp+30h] [rbp-D0h] BYREF
  int v36; // [rsp+38h] [rbp-C8h] BYREF
  void *v37; // [rsp+40h] [rbp-C0h] BYREF
  int v38; // [rsp+48h] [rbp-B8h] BYREF
  void *v39; // [rsp+50h] [rbp-B0h] BYREF
  void *v40; // [rsp+58h] [rbp-A8h] BYREF
  struct _SID *v41; // [rsp+60h] [rbp-A0h]
  SID *v42; // [rsp+68h] [rbp-98h]
  struct _INET_FIREWALL_AC_CHANGE v43; // [rsp+70h] [rbp-90h] BYREF
  int v44; // [rsp+A0h] [rbp-60h] BYREF
  int v45; // [rsp+A4h] [rbp-5Ch]
  __int128 *v46; // [rsp+A8h] [rbp-58h]
  __int64 v47; // [rsp+B0h] [rbp-50h]
  __int64 v48; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v49; // [rsp+C0h] [rbp-40h] BYREF
  LPWSTR v50; // [rsp+C8h] [rbp-38h] BYREF
  LPWSTR StringSid; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v52; // [rsp+D8h] [rbp-28h] BYREF
  _DWORD v53[4]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v54; // [rsp+F8h] [rbp-8h]
  _DWORD v55[4]; // [rsp+100h] [rbp+0h] BYREF
  LPWSTR v56; // [rsp+110h] [rbp+10h]
  int v57; // [rsp+118h] [rbp+18h]
  int v58; // [rsp+11Ch] [rbp+1Ch]
  int v59; // [rsp+120h] [rbp+20h]
  LPWSTR v60; // [rsp+128h] [rbp+28h]

  v44 = 545;
  StringSid = 0;
  v50 = 0;
  v49 = 0;
  v7 = 0;
  v48 = 0;
  v45 = 1;
  v8 = a4;
  v46 = 0;
  v52 = 0;
  v47 = 0x10000;
  DelaySignaled = 1;
  v36 = 0;
  v38 = 0;
  v37 = 0;
  v40 = 0;
  v39 = 0;
  v35 = 0;
  v41 = a4;
  v42 = a3;
  v43.32 = 0;
  IsChildAppContainer = FwMoneisIsChildAppContainer(a4, &v36);
  if ( IsChildAppContainer )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        91,
        WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids,
        IsChildAppContainer);
    goto LABEL_131;
  }
  LastError = FwMoneisValidateAppContainerOperation(a1, a2, v36, a3, v8, &v38);
  IsChildAppContainer = LastError;
  if ( !LastError )
  {
    if ( !v38 )
    {
      IsChildAppContainer = 0;
      v12 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v13 = 93;
        v14 = 0;
        goto LABEL_138;
      }
      goto LABEL_131;
    }
    LastError = FwMoneisOpenStores(a2, &v40, &v39);
    IsChildAppContainer = LastError;
    if ( LastError )
    {
      v12 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v13 = 94;
        goto LABEL_137;
      }
      goto LABEL_131;
    }
    if ( !ConvertSidToStringSidW(a3, &StringSid) )
    {
      LastError = GetLastError();
      IsChildAppContainer = LastError;
      v12 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v13 = 95;
        goto LABEL_137;
      }
      goto LABEL_131;
    }
    if ( !ConvertSidToStringSidW(v8, &v50) )
    {
      LastError = GetLastError();
      IsChildAppContainer = LastError;
      v12 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v13 = 96;
        goto LABEL_137;
      }
      goto LABEL_131;
    }
    v15 = FwStringBuild(&v49, v50, StringSid, 0);
    LastError = FwHResultToWindowsError(v15);
    IsChildAppContainer = LastError;
    if ( LastError )
    {
      v12 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v13 = 97;
        goto LABEL_137;
      }
      goto LABEL_131;
    }
    Rule = FwGetRule(*((_QWORD *)gFwIsolationManager + 9), 3, v49, &v48);
    LastError = FwHResultToWindowsError(Rule);
    IsChildAppContainer = LastError;
    if ( LastError )
    {
      v12 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v13 = 98;
        goto LABEL_137;
      }
      goto LABEL_131;
    }
    v18 = 0;
    if ( v48 )
    {
      LOBYTE(v17) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppContainerPFN>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_AppContainerPFN>::GetImpl'::`2'::impl,
        v17);
      if ( *(_QWORD *)(v48 + 40) )
        v18 = *(_QWORD *)(v48 + 40);
    }
    if ( !v36 )
    {
      v19 = v40;
      *((_QWORD *)&v52 + 1) = v55;
      LODWORD(v52) = 2;
      v55[2] = 5;
      v46 = &v52;
      v56 = StringSid;
      v59 = 5;
      v60 = v50;
      v45 = 1;
      v55[0] = 11;
      v55[1] = 1;
      v57 = 12;
      v58 = 1;
      v20 = FwMoneisQueryRules(v40, (struct _tag_FW_QUERY *)&v44, &v35);
      IsChildAppContainer = v20;
      if ( v20 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_42;
        v22 = 99;
LABEL_41:
        WPP_SF_d(*(_QWORD *)(v21 + 16), v22, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids, v20);
LABEL_42:
        v7 = v35;
        goto LABEL_131;
      }
      v7 = v35;
      LastError = FwMoneisDeleteRules(v19, v35, a5);
      IsChildAppContainer = LastError;
      if ( LastError )
      {
        v12 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v13 = 100;
          goto LABEL_137;
        }
        goto LABEL_131;
      }
      v23 = FwFreeRules(v7, 0);
      LastError = FwHResultToWindowsError(v23);
      IsChildAppContainer = LastError;
      if ( LastError )
      {
        v12 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v13 = 101;
          goto LABEL_137;
        }
        goto LABEL_131;
      }
      if ( !v7 )
      {
        LastError = SvrImpl_FWOpenPolicyStore(0, 545, 4, 2, 0, &v37);
        IsChildAppContainer = LastError;
        if ( LastError )
        {
          v12 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v13 = 102;
            goto LABEL_137;
          }
          goto LABEL_131;
        }
        v20 = FwMoneisQueryRules(v37, (struct _tag_FW_QUERY *)&v44, &v35);
        IsChildAppContainer = v20;
        if ( v20 )
        {
          v21 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_42;
          v22 = 103;
          goto LABEL_41;
        }
        v7 = v35;
        LastError = FwMoneisDeleteRules(v37, v35, a5);
        IsChildAppContainer = LastError;
        if ( LastError )
        {
          v12 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v13 = 104;
            goto LABEL_137;
          }
          goto LABEL_131;
        }
        v25 = FwFreeRules(v7, 0);
        LastError = FwHResultToWindowsError(v25);
        IsChildAppContainer = LastError;
        if ( LastError )
        {
          v12 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v13 = 105;
            goto LABEL_137;
          }
          goto LABEL_131;
        }
      }
      v35 = 0;
      v26 = v39;
      if ( a2 == 1 )
      {
        v20 = FwMoneisQueryRules(v39, (struct _tag_FW_QUERY *)&v44, &v35);
        IsChildAppContainer = v20;
        if ( v20 )
        {
          v21 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_42;
          v22 = 106;
          goto LABEL_41;
        }
        v7 = v35;
        LastError = FwMoneisDeleteRules(v26, v35, a5);
        IsChildAppContainer = LastError;
        if ( LastError )
        {
          v12 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v13 = 107;
            goto LABEL_137;
          }
          goto LABEL_131;
        }
        v27 = FwFreeRules(v7, 0);
        LastError = FwHResultToWindowsError(v27);
        IsChildAppContainer = LastError;
        if ( LastError )
        {
          v12 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v13 = 108;
            goto LABEL_137;
          }
          goto LABEL_131;
        }
        v35 = 0;
      }
      LOBYTE(v24) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppContainerPFN>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_AppContainerPFN>::GetImpl'::`2'::impl,
        v24);
      LODWORD(v52) = 1;
      *((_QWORD *)&v52 + 1) = v53;
      v45 = 1;
      v46 = &v52;
      v53[0] = 16;
      v53[1] = 1;
      v53[2] = 5;
      v54 = v18;
      v20 = FwMoneisQueryRules(v19, (struct _tag_FW_QUERY *)&v44, &v35);
      IsChildAppContainer = v20;
      if ( v20 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_42;
        v22 = 109;
        goto LABEL_41;
      }
      v7 = v35;
      LastError = FwMoneisDeleteRules(v19, v35, a5);
      IsChildAppContainer = LastError;
      if ( LastError )
      {
        v12 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v13 = 110;
          goto LABEL_137;
        }
        goto LABEL_131;
      }
      v28 = FwFreeRules(v7, 0);
      LastError = FwHResultToWindowsError(v28);
      IsChildAppContainer = LastError;
      if ( LastError )
      {
        v12 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v13 = 111;
          goto LABEL_137;
        }
        goto LABEL_131;
      }
      if ( !v7 )
      {
        LastError = SvrImpl_FWOpenPolicyStore(0, 545, 4, 2, 0, &v37);
        IsChildAppContainer = LastError;
        if ( LastError )
        {
          v12 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v13 = 112;
            goto LABEL_137;
          }
          goto LABEL_131;
        }
        v20 = FwMoneisQueryRules(v37, (struct _tag_FW_QUERY *)&v44, &v35);
        IsChildAppContainer = v20;
        if ( v20 )
        {
          v21 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_42;
          v22 = 113;
          goto LABEL_41;
        }
        v7 = v35;
        LastError = FwMoneisDeleteRules(v37, v35, a5);
        IsChildAppContainer = LastError;
        if ( LastError )
        {
          v12 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v13 = 114;
            goto LABEL_137;
          }
          goto LABEL_131;
        }
        v29 = FwFreeRules(v7, 0);
        LastError = FwHResultToWindowsError(v29);
        IsChildAppContainer = LastError;
        if ( LastError )
        {
          v12 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v13 = 115;
            goto LABEL_137;
          }
          goto LABEL_131;
        }
      }
      v7 = 0;
      v35 = 0;
      if ( a2 == 1 )
      {
        v20 = FwMoneisQueryRules(v26, (struct _tag_FW_QUERY *)&v44, &v35);
        IsChildAppContainer = v20;
        if ( v20 )
        {
          v21 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_42;
          v22 = 116;
          goto LABEL_41;
        }
        v7 = v35;
        LastError = FwMoneisDeleteRules(v26, v35, a5);
        IsChildAppContainer = LastError;
        if ( LastError )
        {
          v12 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v13 = 117;
            goto LABEL_137;
          }
          goto LABEL_131;
        }
        v30 = FwFreeRules(v7, 0);
        LastError = FwHResultToWindowsError(v30);
        IsChildAppContainer = LastError;
        if ( LastError )
        {
          v12 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v13 = 118;
            goto LABEL_137;
          }
          goto LABEL_131;
        }
        v7 = 0;
      }
      v8 = v41;
    }
    v31 = FwDeleteRule(*((_QWORD *)gFwIsolationManager + 9), 3, v49);
    LastError = FwHResultToWindowsError(v31);
    IsChildAppContainer = LastError;
    if ( LastError )
    {
      v12 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v13 = 119;
        goto LABEL_137;
      }
    }
    else
    {
      v43.userSid = v42;
      *(_QWORD *)&v43.changeType = 2;
      v43.appContainerSid = v8;
      v43.displayName = a5;
      appIsolation::IsolationEvents::FwMoneisSendNotification(Block, v36, &v43);
    }
    goto LABEL_131;
  }
  v12 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v13 = 92;
    goto LABEL_137;
  }
  while ( 1 )
  {
LABEL_131:
    while ( IsChildAppContainer )
    {
      if ( !v7 )
        break;
      v32 = FwFreeRules(v7, 0);
      LastError = FwHResultToWindowsError(v32);
      IsChildAppContainer = LastError;
      if ( !LastError )
        break;
      v12 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v13 = 120;
LABEL_137:
        v14 = LastError;
LABEL_138:
        WPP_SF_d(*(_QWORD *)(v12 + 16), v13, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids, v14);
      }
    }
    if ( !v48 )
      break;
    v33 = FwFreeRules(v48, 3);
    LastError = FwHResultToWindowsError(v33);
    IsChildAppContainer = LastError;
    if ( !LastError )
      break;
    v12 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v13 = 121;
      goto LABEL_137;
    }
  }
  if ( v49 )
    FwFree(v49);
  if ( v50 )
    LocalFree(v50);
  if ( StringSid )
    LocalFree(StringSid);
  FwMoneisCloseStores(&v40, &v39);
  if ( v37 )
    SvrImpl_FWClosePolicyStore(0, &v37);
  return IsChildAppContainer;
}

```

## disassembly

```asm
0x180057bd0  push    rbp
0x180057bd2  push    rbx
0x180057bd3  push    rsi
0x180057bd4  push    rdi
0x180057bd5  push    r12
0x180057bd7  push    r13
0x180057bd9  push    r14
0x180057bdb  push    r15
0x180057bdd  lea     rbp, [rsp-48h]
0x180057be2  sub     rsp, 148h
0x180057be9  mov     rax, cs:__security_cookie
0x180057bf0  xor     rax, rsp
0x180057bf3  mov     [rbp+80h+var_50], rax
0x180057bf7  mov     r15, [rbp+80h+arg_20]
0x180057bfe  mov     rsi, rcx
0x180057c01  xor     ecx, ecx
0x180057c03  mov     [rbp+80h+var_E0], 221h
0x180057c0a  mov     r13d, edx
0x180057c0d  mov     [rbp+80h+StringSid], rcx
0x180057c11  xorps   xmm0, xmm0
0x180057c14  mov     [rbp+80h+var_B8], rcx
0x180057c18  mov     [rbp+80h+var_C0], rcx
0x180057c1c  mov     edi, ecx
0x180057c1e  lea     edx, [rcx+1]
0x180057c21  mov     [rbp+80h+var_C8], rcx
0x180057c25  mov     [rbp+80h+var_DC], edx
0x180057c28  mov     r12, r9
0x180057c2b  mov     [rbp+80h+var_D8], rcx
0x180057c2f  mov     r14, r8
0x180057c32  movups  [rbp+80h+var_A8], xmm0
0x180057c36  mov     [rbp+80h+var_D0], 10000h
0x180057c3e  mov     cs:?DelaySignaled@@3KC, edx; ulong volatile DelaySignaled
0x180057c44  lea     rdx, [rsp+180h+var_148]; int *
0x180057c49  mov     [rsp+180h+var_148], ecx
0x180057c4d  mov     [rsp+180h+var_138], ecx
0x180057c51  mov     [rsp+180h+var_140], rcx
0x180057c56  mov     [rsp+180h+var_128], rcx
0x180057c5b  mov     [rsp+180h+var_130], rcx
0x180057c60  mov     [rsp+180h+var_150], rcx
0x180057c65  mov     rcx, r9; struct _SID *
0x180057c68  mov     [rsp+180h+var_120], r9
0x180057c6d  mov     [rsp+180h+var_118], r8
0x180057c72  movdqu  xmmword ptr [rbp+80h+var_110.20h], xmm0
0x180057c77  call    ?FwMoneisIsChildAppContainer@@YAKPEAU_SID@@PEAH@Z; FwMoneisIsChildAppContainer(_SID *,int *)
0x180057c7c  mov     ebx, eax
0x180057c7e  lea     rax, WPP_GLOBAL_Control
0x180057c85  test    ebx, ebx
0x180057c87  jz      short loc_180057CBE
0x180057c89  mov     rcx, cs:WPP_GLOBAL_Control
0x180057c90  cmp     rcx, rax
0x180057c93  jz      loc_18005863A
0x180057c99  test    byte ptr [rcx+1Ch], 1
0x180057c9d  jz      loc_18005863A
0x180057ca3  mov     rcx, [rcx+10h]
0x180057ca7  lea     edx, [rdi+5Bh]
0x180057caa  mov     r9d, ebx
0x180057cad  lea     r8, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids
0x180057cb4  call    WPP_SF_d
0x180057cb9  jmp     loc_18005863A
0x180057cbe  mov     r8d, [rsp+180h+var_148]; int
0x180057cc3  lea     rax, [rsp+180h+var_138]
0x180057cc8  mov     [rsp+180h+var_158], rax; int *
0x180057ccd  mov     r9, r14; struct _SID *
0x180057cd0  mov     edx, r13d; int
0x180057cd3  mov     [rsp+180h+var_160], r12; struct _SID *
0x180057cd8  mov     rcx, rsi; void *
0x180057cdb  call    ?FwMoneisValidateAppContainerOperation@@YAKPEAXHHPEAU_SID@@1PEAH@Z; FwMoneisValidateAppContainerOperation(void *,int,int,_SID *,_SID *,int *)
0x180057ce0  mov     ebx, eax
0x180057ce2  test    eax, eax
0x180057ce4  jz      short loc_180057D11
0x180057ce6  mov     rcx, cs:WPP_GLOBAL_Control
0x180057ced  lea     rsi, WPP_GLOBAL_Control
0x180057cf4  cmp     rcx, rsi
0x180057cf7  jz      loc_180058641
0x180057cfd  test    byte ptr [rcx+1Ch], 1
0x180057d01  jz      loc_180058641
0x180057d07  mov     edx, 5Ch ; '\'
0x180057d0c  jmp     loc_180058686
0x180057d11  cmp     [rsp+180h+var_138], edi
0x180057d15  jnz     short loc_180057D45
0x180057d17  xor     ebx, ebx
0x180057d19  mov     rcx, cs:WPP_GLOBAL_Control
0x180057d20  lea     rsi, WPP_GLOBAL_Control
0x180057d27  cmp     rcx, rsi
0x180057d2a  jz      loc_180058641
0x180057d30  test    byte ptr [rcx+1Ch], 1
0x180057d34  jz      loc_180058641
0x180057d3a  lea     edx, [rbx+5Dh]
0x180057d3d  xor     r9d, r9d
0x180057d40  jmp     loc_180058689
0x180057d45  lea     r8, [rsp+180h+var_130]; void **
0x180057d4a  mov     ecx, r13d; int
0x180057d4d  lea     rdx, [rsp+180h+var_128]; void **
0x180057d52  call    ?FwMoneisOpenStores@@YAKHPEAPEAX0@Z; FwMoneisOpenStores(int,void * *,void * *)
0x180057d57  mov     ebx, eax
0x180057d59  test    eax, eax
0x180057d5b  jz      short loc_180057D88
0x180057d5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180057d64  lea     rsi, WPP_GLOBAL_Control
0x180057d6b  cmp     rcx, rsi
0x180057d6e  jz      loc_180058641
0x180057d74  test    byte ptr [rcx+1Ch], 1
0x180057d78  jz      loc_180058641
0x180057d7e  mov     edx, 5Eh ; '^'
0x180057d83  jmp     loc_180058686
0x180057d88  lea     rdx, [rbp+80h+StringSid]; StringSid
0x180057d8c  mov     rcx, r14; Sid
0x180057d8f  call    cs:__imp_ConvertSidToStringSidW
0x180057d96  nop     dword ptr [rax+rax+00h]
0x180057d9b  test    eax, eax
0x180057d9d  jnz     short loc_180057DD8
0x180057d9f  call    cs:__imp_GetLastError
0x180057da6  nop     dword ptr [rax+rax+00h]
0x180057dab  mov     ebx, eax
0x180057dad  mov     rcx, cs:WPP_GLOBAL_Control
0x180057db4  lea     rsi, WPP_GLOBAL_Control
0x180057dbb  cmp     rcx, rsi
0x180057dbe  jz      loc_180058641
0x180057dc4  test    byte ptr [rcx+1Ch], 1
0x180057dc8  jz      loc_180058641
0x180057dce  mov     edx, 5Fh ; '_'
0x180057dd3  jmp     loc_180058686
0x180057dd8  lea     rdx, [rbp+80h+var_B8]; StringSid
0x180057ddc  mov     rcx, r12; Sid
0x180057ddf  call    cs:__imp_ConvertSidToStringSidW
0x180057de6  nop     dword ptr [rax+rax+00h]
0x180057deb  test    eax, eax
0x180057ded  jnz     short loc_180057E28
0x180057def  call    cs:__imp_GetLastError
0x180057df6  nop     dword ptr [rax+rax+00h]
0x180057dfb  mov     ebx, eax
0x180057dfd  mov     rcx, cs:WPP_GLOBAL_Control
0x180057e04  lea     rsi, WPP_GLOBAL_Control
0x180057e0b  cmp     rcx, rsi
0x180057e0e  jz      loc_180058641
0x180057e14  test    byte ptr [rcx+1Ch], 1
0x180057e18  jz      loc_180058641
0x180057e1e  mov     edx, 60h ; '`'
0x180057e23  jmp     loc_180058686
0x180057e28  mov     r8, [rbp+80h+StringSid]
0x180057e2c  lea     rcx, [rbp+80h+var_C0]
0x180057e30  mov     rdx, [rbp+80h+var_B8]
0x180057e34  xor     r9d, r9d
0x180057e37  call    cs:__imp_FwStringBuild
0x180057e3e  nop     dword ptr [rax+rax+00h]
0x180057e43  mov     ecx, eax
0x180057e45  call    cs:__imp_FwHResultToWindowsError
0x180057e4c  nop     dword ptr [rax+rax+00h]
0x180057e51  mov     ebx, eax
0x180057e53  test    eax, eax
0x180057e55  jz      short loc_180057E82
0x180057e57  mov     rcx, cs:WPP_GLOBAL_Control
0x180057e5e  lea     rsi, WPP_GLOBAL_Control
0x180057e65  cmp     rcx, rsi
0x180057e68  jz      loc_180058641
0x180057e6e  test    byte ptr [rcx+1Ch], 1
0x180057e72  jz      loc_180058641
0x180057e78  mov     edx, 61h ; 'a'
0x180057e7d  jmp     loc_180058686
0x180057e82  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x180057e89  lea     r9, [rbp+80h+var_C8]
0x180057e8d  mov     r8, [rbp+80h+var_C0]
0x180057e91  mov     edx, 3
0x180057e96  mov     rcx, [rcx+48h]
0x180057e9a  call    cs:__imp_FwGetRule
0x180057ea1  nop     dword ptr [rax+rax+00h]
0x180057ea6  mov     ecx, eax
0x180057ea8  call    cs:__imp_FwHResultToWindowsError
0x180057eaf  nop     dword ptr [rax+rax+00h]
0x180057eb4  mov     ebx, eax
0x180057eb6  test    eax, eax
0x180057eb8  jz      short loc_180057EE5
0x180057eba  mov     rcx, cs:WPP_GLOBAL_Control
0x180057ec1  lea     rsi, WPP_GLOBAL_Control
0x180057ec8  cmp     rcx, rsi
0x180057ecb  jz      loc_180058641
0x180057ed1  test    byte ptr [rcx+1Ch], 1
0x180057ed5  jz      loc_180058641
0x180057edb  mov     edx, 62h ; 'b'
0x180057ee0  jmp     loc_180058686
0x180057ee5  xor     r14d, r14d
0x180057ee8  xor     esi, esi
0x180057eea  cmp     [rbp+80h+var_C8], rsi
0x180057eee  jz      short loc_180057F0B
0x180057ef0  mov     dl, 1
0x180057ef2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppContainerPFN@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppContainerPFN@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppContainerPFN> `wil::Feature<__WilFeatureTraits_Feature_AppContainerPFN>::GetImpl(void)'::`2'::impl
0x180057ef9  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppContainerPFN@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppContainerPFN>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180057efe  mov     rax, [rbp+80h+var_C8]
0x180057f02  cmp     [rax+28h], rsi
0x180057f06  cmovnz  r14, [rax+28h]
0x180057f0b  cmp     [rsp+180h+var_148], esi
0x180057f0f  jnz     loc_1800585B6
0x180057f15  mov     r12, [rsp+180h+var_128]
0x180057f1a  lea     rax, [rbp+80h+var_80]
0x180057f1e  mov     qword ptr [rbp+80h+var_A8+8], rax
0x180057f22  lea     r8, [rsp+180h+var_150]; struct _tag_FW_RULE **
0x180057f27  mov     ecx, 5
0x180057f2c  mov     dword ptr [rbp+80h+var_A8], 2
0x180057f33  lea     rax, [rbp+80h+var_A8]
0x180057f37  mov     [rbp+80h+var_78], ecx
0x180057f3a  mov     [rbp+80h+var_D8], rax
0x180057f3e  lea     rdx, [rbp+80h+var_E0]; struct _tag_FW_QUERY *
0x180057f42  mov     rax, [rbp+80h+StringSid]
0x180057f46  mov     [rbp+80h+var_70], rax
0x180057f4a  mov     rax, [rbp+80h+var_B8]
0x180057f4e  mov     [rbp+80h+var_60], ecx
0x180057f51  mov     rcx, r12; void *
0x180057f54  mov     [rbp+80h+var_58], rax
0x180057f58  mov     [rbp+80h+var_DC], 1
0x180057f5f  mov     [rbp+80h+var_80], 0Bh
0x180057f66  mov     [rbp+80h+var_7C], 1
0x180057f6d  mov     [rbp+80h+var_68], 0Ch
0x180057f74  mov     [rbp+80h+var_64], 1
0x180057f7b  call    ?FwMoneisQueryRules@@YAKPEAXPEAU_tag_FW_QUERY@@PEAPEAU_tag_FW_RULE@@@Z; FwMoneisQueryRules(void *,_tag_FW_QUERY *,_tag_FW_RULE * *)
0x180057f80  mov     ebx, eax
0x180057f82  test    eax, eax
0x180057f84  jz      short loc_180057FC1
0x180057f86  mov     rcx, cs:WPP_GLOBAL_Control
0x180057f8d  lea     rsi, WPP_GLOBAL_Control
0x180057f94  cmp     rcx, rsi
0x180057f97  jz      short loc_180057FB7
0x180057f99  test    byte ptr [rcx+1Ch], 1
0x180057f9d  jz      short loc_180057FB7
0x180057f9f  mov     edx, 63h ; 'c'
0x180057fa4  mov     rcx, [rcx+10h]
0x180057fa8  lea     r8, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids
0x180057faf  mov     r9d, eax
0x180057fb2  call    WPP_SF_d
0x180057fb7  mov     rdi, [rsp+180h+var_150]
0x180057fbc  jmp     loc_180058641
0x180057fc1  mov     rdi, [rsp+180h+var_150]
0x180057fc6  mov     r8, r15; unsigned __int16 *
0x180057fc9  mov     rdx, rdi; struct _tag_FW_RULE *
0x180057fcc  mov     rcx, r12; void *
0x180057fcf  call    ?FwMoneisDeleteRules@@YAKPEAXPEAU_tag_FW_RULE@@PEBG@Z; FwMoneisDeleteRules(void *,_tag_FW_RULE *,ushort const *)
0x180057fd4  mov     ebx, eax
0x180057fd6  test    eax, eax
0x180057fd8  jz      short loc_180058005
0x180057fda  mov     rcx, cs:WPP_GLOBAL_Control
0x180057fe1  lea     rsi, WPP_GLOBAL_Control
0x180057fe8  cmp     rcx, rsi
0x180057feb  jz      loc_180058641
0x180057ff1  test    byte ptr [rcx+1Ch], 1
0x180057ff5  jz      loc_180058641
0x180057ffb  mov     edx, 64h ; 'd'
0x180058000  jmp     loc_180058686
0x180058005  xor     edx, edx
0x180058007  mov     rcx, rdi
0x18005800a  call    cs:__imp_FwFreeRules
0x180058011  nop     dword ptr [rax+rax+00h]
0x180058016  mov     ecx, eax
0x180058018  call    cs:__imp_FwHResultToWindowsError
0x18005801f  nop     dword ptr [rax+rax+00h]
0x180058024  mov     ebx, eax
0x180058026  test    eax, eax
0x180058028  jz      short loc_180058055
0x18005802a  mov     rcx, cs:WPP_GLOBAL_Control
0x180058031  lea     rsi, WPP_GLOBAL_Control
0x180058038  cmp     rcx, rsi
0x18005803b  jz      loc_180058641
0x180058041  test    byte ptr [rcx+1Ch], 1
0x180058045  jz      loc_180058641
0x18005804b  mov     edx, 65h ; 'e'
0x180058050  jmp     loc_180058686
0x180058055  test    rdi, rdi
0x180058058  jnz     loc_180058189
0x18005805e  lea     rax, [rsp+180h+var_140]
0x180058063  mov     edx, 221h
0x180058068  mov     [rsp+180h+var_158], rax
0x18005806d  lea     r9d, [rdi+2]
0x180058071  xor     ecx, ecx
0x180058073  mov     dword ptr [rsp+180h+var_160], esi
0x180058077  lea     r8d, [rdi+4]
0x18005807b  call    ?SvrImpl_FWOpenPolicyStore@@YAKPEAXGW4_tag_FW_STORE_TYPE@@W4_tag_FW_POLICY_ACCESS_RIGHT@@KPEAPEAX@Z; SvrImpl_FWOpenPolicyStore(void *,ushort,_tag_FW_STORE_TYPE,_tag_FW_POLICY_ACCESS_RIGHT,ulong,void * *)
0x180058080  mov     ebx, eax
0x180058082  test    eax, eax
0x180058084  jz      short loc_1800580AF
0x180058086  mov     rcx, cs:WPP_GLOBAL_Control
0x18005808d  lea     rsi, WPP_GLOBAL_Control
0x180058094  cmp     rcx, rsi
0x180058097  jz      loc_180058641
0x18005809d  test    byte ptr [rcx+1Ch], 1
0x1800580a1  jz      loc_180058641
0x1800580a7  lea     edx, [rdi+66h]
0x1800580aa  jmp     loc_180058686
0x1800580af  mov     rcx, [rsp+180h+var_140]; void *
0x1800580b4  lea     r8, [rsp+180h+var_150]; struct _tag_FW_RULE **
0x1800580b9  lea     rdx, [rbp+80h+var_E0]; struct _tag_FW_QUERY *
0x1800580bd  call    ?FwMoneisQueryRules@@YAKPEAXPEAU_tag_FW_QUERY@@PEAPEAU_tag_FW_RULE@@@Z; FwMoneisQueryRules(void *,_tag_FW_QUERY *,_tag_FW_RULE * *)
0x1800580c2  mov     ebx, eax
0x1800580c4  test    eax, eax
0x1800580c6  jz      short loc_1800580F3
0x1800580c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800580cf  lea     rsi, WPP_GLOBAL_Control
0x1800580d6  cmp     rcx, rsi
0x1800580d9  jz      loc_180057FB7
0x1800580df  test    byte ptr [rcx+1Ch], 1
0x1800580e3  jz      loc_180057FB7
0x1800580e9  mov     edx, 67h ; 'g'
0x1800580ee  jmp     loc_180057FA4
  ... truncated ...
```
