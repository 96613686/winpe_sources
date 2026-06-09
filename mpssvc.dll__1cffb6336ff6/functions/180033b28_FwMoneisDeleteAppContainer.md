# FwMoneisDeleteAppContainer

- ea: `0x180033b28`
- end: `0x180034614`
- name: `FwMoneisDeleteAppContainer`
- size: `2796`
- prototype: `__int64 __fastcall(void *, int, struct _SID *, struct _SID *, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002f7d4`
- `0x180033ab0`
- `0x1800b5890`
- `0x1800c6d00`

## callees

- `0x18000af3c`
- `0x18002b87c`
- `0x18002f478`
- `0x180032080`
- `0x180033b28`
- `0x18003b4a0`
- `0x18003be24`
- `0x18003ca2c`
- `0x18003d0d8`
- `0x180059270`
- `0x1800620b8`
- `0x18006f520`
- `0x1800bb620`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033cf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033d35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033cf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033d35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800345ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800345c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800345ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800345c9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180033ce7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180033d2b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180033ce7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180033d2b`
- `fwbase!FwHResultToWindowsError` at `0x180033d7f`
- `fwbase!FwHResultToWindowsError` at `0x180033dd6`
- `fwbase!FwHResultToWindowsError` at `0x180033f3a`
- `fwbase!FwHResultToWindowsError` at `0x180034062`
- `fwbase!FwHResultToWindowsError` at `0x18003413f`
- `fwbase!FwHResultToWindowsError` at `0x180034257`
- `fwbase!FwHResultToWindowsError` at `0x18003437f`
- `fwbase!FwHResultToWindowsError` at `0x180034458`
- `fwbase!FwHResultToWindowsError` at `0x1800344b2`
- `fwbase!FwHResultToWindowsError` at `0x18003452b`
- `fwbase!FwHResultToWindowsError` at `0x180034579`
- `fwbase!FwHResultToWindowsError` at `0x180033d7f`
- `fwbase!FwHResultToWindowsError` at `0x180033dd6`
- `fwbase!FwHResultToWindowsError` at `0x180033f3a`
- `fwbase!FwHResultToWindowsError` at `0x180034062`
- `fwbase!FwHResultToWindowsError` at `0x18003413f`
- `fwbase!FwHResultToWindowsError` at `0x180034257`
- `fwbase!FwHResultToWindowsError` at `0x18003437f`
- `fwbase!FwHResultToWindowsError` at `0x180034458`
- `fwbase!FwHResultToWindowsError` at `0x1800344b2`
- `fwbase!FwHResultToWindowsError` at `0x18003452b`
- `fwbase!FwHResultToWindowsError` at `0x180034579`
- `fwbase!FwStringBuild` at `0x180033d77`
- `fwbase!FwStringBuild` at `0x180033d77`
- `fwbase!FwFree` at `0x1800345ab`
- `fwbase!FwFree` at `0x1800345ab`
- `FWPolicyIOMgr!FwDeleteRule` at `0x1800344aa`
- `FWPolicyIOMgr!FwDeleteRule` at `0x1800344aa`
- `FWPolicyIOMgr!FwGetRule` at `0x180033dce`
- `FWPolicyIOMgr!FwGetRule` at `0x180033dce`
- `FWPolicyIOMgr!FwFreeRules` at `0x180033f32`
- `FWPolicyIOMgr!FwFreeRules` at `0x18003405a`
- `FWPolicyIOMgr!FwFreeRules` at `0x180034137`
- `FWPolicyIOMgr!FwFreeRules` at `0x18003424f`
- `FWPolicyIOMgr!FwFreeRules` at `0x180034377`
- `FWPolicyIOMgr!FwFreeRules` at `0x180034450`
- `FWPolicyIOMgr!FwFreeRules` at `0x180034523`
- `FWPolicyIOMgr!FwFreeRules` at `0x180034571`
- `FWPolicyIOMgr!FwFreeRules` at `0x180033f32`
- `FWPolicyIOMgr!FwFreeRules` at `0x18003405a`
- `FWPolicyIOMgr!FwFreeRules` at `0x180034137`
- `FWPolicyIOMgr!FwFreeRules` at `0x18003424f`
- `FWPolicyIOMgr!FwFreeRules` at `0x180034377`
- `FWPolicyIOMgr!FwFreeRules` at `0x180034450`
- `FWPolicyIOMgr!FwFreeRules` at `0x180034523`
- `FWPolicyIOMgr!FwFreeRules` at `0x180034571`

## pseudocode

```c
__int64 __fastcall FwMoneisDeleteAppContainer(void *a1, int a2, struct _SID *a3, struct _SID *a4, unsigned __int16 *a5)
{
  struct _tag_FW_RULE *v7; // rdi
  struct _SID *v8; // r12
  unsigned int IsChildAppContainer; // ebx
  unsigned int LastError; // eax
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
        86,
        WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids,
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
        v13 = 88;
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
        v13 = 89;
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
        v13 = 90;
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
        v13 = 91;
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
        v13 = 92;
        goto LABEL_137;
      }
      goto LABEL_131;
    }
    Rule = FwGetRule(*((_QWORD *)gFwIsolationManager + 12), 3, v49, &v48);
    LastError = FwHResultToWindowsError(Rule);
    IsChildAppContainer = LastError;
    if ( LastError )
    {
      v12 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v13 = 93;
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
        v22 = 94;
LABEL_41:
        WPP_SF_d(*(_QWORD *)(v21 + 16), v22, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids, v20);
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
          v13 = 95;
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
          v13 = 96;
          goto LABEL_137;
        }
        goto LABEL_131;
      }
      if ( !v7 )
      {
        LastError = SvrImpl_FWOpenPolicyStore(0, 545, 4, 2u, 0, (__int64 *)&v37);
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
        v20 = FwMoneisQueryRules(v37, (struct _tag_FW_QUERY *)&v44, &v35);
        IsChildAppContainer = v20;
        if ( v20 )
        {
          v21 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_42;
          v22 = 98;
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
            v13 = 99;
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
            v13 = 100;
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
          v22 = 101;
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
            v13 = 102;
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
            v13 = 103;
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
        v22 = 104;
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
          v13 = 105;
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
          v13 = 106;
          goto LABEL_137;
        }
        goto LABEL_131;
      }
      if ( !v7 )
      {
        LastError = SvrImpl_FWOpenPolicyStore(0, 545, 4, 2u, 0, (__int64 *)&v37);
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
        v20 = FwMoneisQueryRules(v37, (struct _tag_FW_QUERY *)&v44, &v35);
        IsChildAppContainer = v20;
        if ( v20 )
        {
          v21 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_42;
          v22 = 108;
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
            v13 = 109;
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
            v13 = 110;
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
          v22 = 111;
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
            v13 = 112;
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
            v13 = 113;
            goto LABEL_137;
          }
          goto LABEL_131;
        }
        v7 = 0;
      }
      v8 = v41;
    }
    v31 = FwDeleteRule(*((_QWORD *)gFwIsolationManager + 12), 3, v49);
    LastError = FwHResultToWindowsError(v31);
    IsChildAppContainer = LastError;
    if ( LastError )
    {
      v12 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v13 = 114;
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
    v13 = 87;
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
        v13 = 115;
LABEL_137:
        v14 = LastError;
LABEL_138:
        WPP_SF_d(*(_QWORD *)(v12 + 16), v13, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids, v14);
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
      v13 = 116;
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
0x180033b28  push    rbp
0x180033b2a  push    rbx
0x180033b2b  push    rsi
0x180033b2c  push    rdi
0x180033b2d  push    r12
0x180033b2f  push    r13
0x180033b31  push    r14
0x180033b33  push    r15
0x180033b35  lea     rbp, [rsp-48h]
0x180033b3a  sub     rsp, 148h
0x180033b41  mov     rax, cs:__security_cookie
0x180033b48  xor     rax, rsp
0x180033b4b  mov     [rbp+80h+var_50], rax
0x180033b4f  mov     r15, [rbp+80h+arg_20]
0x180033b56  mov     rsi, rcx
0x180033b59  xor     ecx, ecx
0x180033b5b  mov     [rbp+80h+var_E0], 221h
0x180033b62  mov     r13d, edx
0x180033b65  mov     [rbp+80h+StringSid], rcx
0x180033b69  xorps   xmm0, xmm0
0x180033b6c  mov     [rbp+80h+var_B8], rcx
0x180033b70  mov     [rbp+80h+var_C0], rcx
0x180033b74  mov     edi, ecx
0x180033b76  lea     edx, [rcx+1]
0x180033b79  mov     [rbp+80h+var_C8], rcx
0x180033b7d  mov     [rbp+80h+var_DC], edx
0x180033b80  mov     r12, r9
0x180033b83  mov     [rbp+80h+var_D8], rcx
0x180033b87  mov     r14, r8
0x180033b8a  movups  [rbp+80h+var_A8], xmm0
0x180033b8e  mov     [rbp+80h+var_D0], 10000h
0x180033b96  mov     cs:?DelaySignaled@@3KC, edx; ulong volatile DelaySignaled
0x180033b9c  lea     rdx, [rsp+180h+var_148]; int *
0x180033ba1  mov     [rsp+180h+var_148], ecx
0x180033ba5  mov     [rsp+180h+var_138], ecx
0x180033ba9  mov     [rsp+180h+var_140], rcx
0x180033bae  mov     [rsp+180h+var_128], rcx
0x180033bb3  mov     [rsp+180h+var_130], rcx
0x180033bb8  mov     [rsp+180h+var_150], rcx
0x180033bbd  mov     rcx, r9; struct _SID *
0x180033bc0  mov     [rsp+180h+var_120], r9
0x180033bc5  mov     [rsp+180h+var_118], r8
0x180033bca  movdqu  xmmword ptr [rbp+80h+var_110.20h], xmm0
0x180033bcf  call    ?FwMoneisIsChildAppContainer@@YAKPEAU_SID@@PEAH@Z; FwMoneisIsChildAppContainer(_SID *,int *)
0x180033bd4  mov     ebx, eax
0x180033bd6  lea     rax, WPP_GLOBAL_Control
0x180033bdd  test    ebx, ebx
0x180033bdf  jz      short loc_180033C16
0x180033be1  mov     rcx, cs:WPP_GLOBAL_Control
0x180033be8  cmp     rcx, rax
0x180033beb  jz      loc_18003450E
0x180033bf1  test    byte ptr [rcx+1Ch], 1
0x180033bf5  jz      loc_18003450E
0x180033bfb  mov     rcx, [rcx+10h]
0x180033bff  lea     edx, [rdi+56h]
0x180033c02  mov     r9d, ebx
0x180033c05  lea     r8, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids
0x180033c0c  call    WPP_SF_d
0x180033c11  jmp     loc_18003450E
0x180033c16  mov     r8d, [rsp+180h+var_148]; int
0x180033c1b  lea     rax, [rsp+180h+var_138]
0x180033c20  mov     [rsp+180h+var_158], rax; int *
0x180033c25  mov     r9, r14; struct _SID *
0x180033c28  mov     edx, r13d; int
0x180033c2b  mov     [rsp+180h+var_160], r12; struct _SID *
0x180033c30  mov     rcx, rsi; void *
0x180033c33  call    ?FwMoneisValidateAppContainerOperation@@YAKPEAXHHPEAU_SID@@1PEAH@Z; FwMoneisValidateAppContainerOperation(void *,int,int,_SID *,_SID *,int *)
0x180033c38  mov     ebx, eax
0x180033c3a  test    eax, eax
0x180033c3c  jz      short loc_180033C69
0x180033c3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180033c45  lea     rsi, WPP_GLOBAL_Control
0x180033c4c  cmp     rcx, rsi
0x180033c4f  jz      loc_180034515
0x180033c55  test    byte ptr [rcx+1Ch], 1
0x180033c59  jz      loc_180034515
0x180033c5f  mov     edx, 57h ; 'W'
0x180033c64  jmp     loc_18003454E
0x180033c69  cmp     [rsp+180h+var_138], edi
0x180033c6d  jnz     short loc_180033C9D
0x180033c6f  xor     ebx, ebx
0x180033c71  mov     rcx, cs:WPP_GLOBAL_Control
0x180033c78  lea     rsi, WPP_GLOBAL_Control
0x180033c7f  cmp     rcx, rsi
0x180033c82  jz      loc_180034515
0x180033c88  test    byte ptr [rcx+1Ch], 1
0x180033c8c  jz      loc_180034515
0x180033c92  lea     edx, [rbx+58h]
0x180033c95  xor     r9d, r9d
0x180033c98  jmp     loc_180034551
0x180033c9d  lea     r8, [rsp+180h+var_130]; void **
0x180033ca2  mov     ecx, r13d; int
0x180033ca5  lea     rdx, [rsp+180h+var_128]; void **
0x180033caa  call    ?FwMoneisOpenStores@@YAKHPEAPEAX0@Z; FwMoneisOpenStores(int,void * *,void * *)
0x180033caf  mov     ebx, eax
0x180033cb1  test    eax, eax
0x180033cb3  jz      short loc_180033CE0
0x180033cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180033cbc  lea     rsi, WPP_GLOBAL_Control
0x180033cc3  cmp     rcx, rsi
0x180033cc6  jz      loc_180034515
0x180033ccc  test    byte ptr [rcx+1Ch], 1
0x180033cd0  jz      loc_180034515
0x180033cd6  mov     edx, 59h ; 'Y'
0x180033cdb  jmp     loc_18003454E
0x180033ce0  lea     rdx, [rbp+80h+StringSid]; StringSid
0x180033ce4  mov     rcx, r14; Sid
0x180033ce7  call    cs:__imp_ConvertSidToStringSidW
0x180033ced  test    eax, eax
0x180033cef  jnz     short loc_180033D24
0x180033cf1  call    cs:__imp_GetLastError
0x180033cf7  mov     ebx, eax
0x180033cf9  mov     rcx, cs:WPP_GLOBAL_Control
0x180033d00  lea     rsi, WPP_GLOBAL_Control
0x180033d07  cmp     rcx, rsi
0x180033d0a  jz      loc_180034515
0x180033d10  test    byte ptr [rcx+1Ch], 1
0x180033d14  jz      loc_180034515
0x180033d1a  mov     edx, 5Ah ; 'Z'
0x180033d1f  jmp     loc_18003454E
0x180033d24  lea     rdx, [rbp+80h+var_B8]; StringSid
0x180033d28  mov     rcx, r12; Sid
0x180033d2b  call    cs:__imp_ConvertSidToStringSidW
0x180033d31  test    eax, eax
0x180033d33  jnz     short loc_180033D68
0x180033d35  call    cs:__imp_GetLastError
0x180033d3b  mov     ebx, eax
0x180033d3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180033d44  lea     rsi, WPP_GLOBAL_Control
0x180033d4b  cmp     rcx, rsi
0x180033d4e  jz      loc_180034515
0x180033d54  test    byte ptr [rcx+1Ch], 1
0x180033d58  jz      loc_180034515
0x180033d5e  mov     edx, 5Bh ; '['
0x180033d63  jmp     loc_18003454E
0x180033d68  mov     r8, [rbp+80h+StringSid]
0x180033d6c  lea     rcx, [rbp+80h+var_C0]
0x180033d70  mov     rdx, [rbp+80h+var_B8]
0x180033d74  xor     r9d, r9d
0x180033d77  call    cs:__imp_FwStringBuild
0x180033d7d  mov     ecx, eax
0x180033d7f  call    cs:__imp_FwHResultToWindowsError
0x180033d85  mov     ebx, eax
0x180033d87  test    eax, eax
0x180033d89  jz      short loc_180033DB6
0x180033d8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180033d92  lea     rsi, WPP_GLOBAL_Control
0x180033d99  cmp     rcx, rsi
0x180033d9c  jz      loc_180034515
0x180033da2  test    byte ptr [rcx+1Ch], 1
0x180033da6  jz      loc_180034515
0x180033dac  mov     edx, 5Ch ; '\'
0x180033db1  jmp     loc_18003454E
0x180033db6  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x180033dbd  lea     r9, [rbp+80h+var_C8]
0x180033dc1  mov     r8, [rbp+80h+var_C0]
0x180033dc5  mov     edx, 3
0x180033dca  mov     rcx, [rcx+60h]
0x180033dce  call    cs:__imp_FwGetRule
0x180033dd4  mov     ecx, eax
0x180033dd6  call    cs:__imp_FwHResultToWindowsError
0x180033ddc  mov     ebx, eax
0x180033dde  test    eax, eax
0x180033de0  jz      short loc_180033E0D
0x180033de2  mov     rcx, cs:WPP_GLOBAL_Control
0x180033de9  lea     rsi, WPP_GLOBAL_Control
0x180033df0  cmp     rcx, rsi
0x180033df3  jz      loc_180034515
0x180033df9  test    byte ptr [rcx+1Ch], 1
0x180033dfd  jz      loc_180034515
0x180033e03  mov     edx, 5Dh ; ']'
0x180033e08  jmp     loc_18003454E
0x180033e0d  xor     r14d, r14d
0x180033e10  xor     esi, esi
0x180033e12  cmp     [rbp+80h+var_C8], rsi
0x180033e16  jz      short loc_180033E33
0x180033e18  mov     dl, 1
0x180033e1a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppContainerPFN@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppContainerPFN@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppContainerPFN> `wil::Feature<__WilFeatureTraits_Feature_AppContainerPFN>::GetImpl(void)'::`2'::impl
0x180033e21  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppContainerPFN@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppContainerPFN>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180033e26  mov     rax, [rbp+80h+var_C8]
0x180033e2a  cmp     [rax+28h], rsi
0x180033e2e  cmovnz  r14, [rax+28h]
0x180033e33  cmp     [rsp+180h+var_148], esi
0x180033e37  jnz     loc_180034496
0x180033e3d  mov     r12, [rsp+180h+var_128]
0x180033e42  lea     rax, [rbp+80h+var_80]
0x180033e46  mov     qword ptr [rbp+80h+var_A8+8], rax
0x180033e4a  lea     r8, [rsp+180h+var_150]; struct _tag_FW_RULE **
0x180033e4f  mov     ecx, 5
0x180033e54  mov     dword ptr [rbp+80h+var_A8], 2
0x180033e5b  lea     rax, [rbp+80h+var_A8]
0x180033e5f  mov     [rbp+80h+var_78], ecx
0x180033e62  mov     [rbp+80h+var_D8], rax
0x180033e66  lea     rdx, [rbp+80h+var_E0]; struct _tag_FW_QUERY *
0x180033e6a  mov     rax, [rbp+80h+StringSid]
0x180033e6e  mov     [rbp+80h+var_70], rax
0x180033e72  mov     rax, [rbp+80h+var_B8]
0x180033e76  mov     [rbp+80h+var_60], ecx
0x180033e79  mov     rcx, r12; void *
0x180033e7c  mov     [rbp+80h+var_58], rax
0x180033e80  mov     [rbp+80h+var_DC], 1
0x180033e87  mov     [rbp+80h+var_80], 0Bh
0x180033e8e  mov     [rbp+80h+var_7C], 1
0x180033e95  mov     [rbp+80h+var_68], 0Ch
0x180033e9c  mov     [rbp+80h+var_64], 1
0x180033ea3  call    ?FwMoneisQueryRules@@YAKPEAXPEAU_tag_FW_QUERY@@PEAPEAU_tag_FW_RULE@@@Z; FwMoneisQueryRules(void *,_tag_FW_QUERY *,_tag_FW_RULE * *)
0x180033ea8  mov     ebx, eax
0x180033eaa  test    eax, eax
0x180033eac  jz      short loc_180033EE9
0x180033eae  mov     rcx, cs:WPP_GLOBAL_Control
0x180033eb5  lea     rsi, WPP_GLOBAL_Control
0x180033ebc  cmp     rcx, rsi
0x180033ebf  jz      short loc_180033EDF
0x180033ec1  test    byte ptr [rcx+1Ch], 1
0x180033ec5  jz      short loc_180033EDF
0x180033ec7  mov     edx, 5Eh ; '^'
0x180033ecc  mov     rcx, [rcx+10h]
0x180033ed0  lea     r8, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids
0x180033ed7  mov     r9d, eax
0x180033eda  call    WPP_SF_d
0x180033edf  mov     rdi, [rsp+180h+var_150]
0x180033ee4  jmp     loc_180034515
0x180033ee9  mov     rdi, [rsp+180h+var_150]
0x180033eee  mov     r8, r15; unsigned __int16 *
0x180033ef1  mov     rdx, rdi; struct _tag_FW_RULE *
0x180033ef4  mov     rcx, r12; void *
0x180033ef7  call    ?FwMoneisDeleteRules@@YAKPEAXPEAU_tag_FW_RULE@@PEBG@Z; FwMoneisDeleteRules(void *,_tag_FW_RULE *,ushort const *)
0x180033efc  mov     ebx, eax
0x180033efe  test    eax, eax
0x180033f00  jz      short loc_180033F2D
0x180033f02  mov     rcx, cs:WPP_GLOBAL_Control
0x180033f09  lea     rsi, WPP_GLOBAL_Control
0x180033f10  cmp     rcx, rsi
0x180033f13  jz      loc_180034515
0x180033f19  test    byte ptr [rcx+1Ch], 1
0x180033f1d  jz      loc_180034515
0x180033f23  mov     edx, 5Fh ; '_'
0x180033f28  jmp     loc_18003454E
0x180033f2d  xor     edx, edx
0x180033f2f  mov     rcx, rdi
0x180033f32  call    cs:__imp_FwFreeRules
0x180033f38  mov     ecx, eax
0x180033f3a  call    cs:__imp_FwHResultToWindowsError
0x180033f40  mov     ebx, eax
0x180033f42  test    eax, eax
0x180033f44  jz      short loc_180033F71
0x180033f46  mov     rcx, cs:WPP_GLOBAL_Control
0x180033f4d  lea     rsi, WPP_GLOBAL_Control
0x180033f54  cmp     rcx, rsi
0x180033f57  jz      loc_180034515
0x180033f5d  test    byte ptr [rcx+1Ch], 1
0x180033f61  jz      loc_180034515
0x180033f67  mov     edx, 60h ; '`'
0x180033f6c  jmp     loc_18003454E
0x180033f71  test    rdi, rdi
0x180033f74  jnz     loc_180034099
0x180033f7a  lea     rax, [rsp+180h+var_140]
0x180033f7f  mov     edx, 221h
0x180033f84  mov     [rsp+180h+var_158], rax
0x180033f89  lea     r9d, [rdi+2]
0x180033f8d  xor     ecx, ecx
0x180033f8f  mov     dword ptr [rsp+180h+var_160], esi
0x180033f93  lea     r8d, [rdi+4]
0x180033f97  call    ?SvrImpl_FWOpenPolicyStore@@YAKPEAXGW4_tag_FW_STORE_TYPE@@W4_tag_FW_POLICY_ACCESS_RIGHT@@KPEAPEAX@Z; SvrImpl_FWOpenPolicyStore(void *,ushort,_tag_FW_STORE_TYPE,_tag_FW_POLICY_ACCESS_RIGHT,ulong,void * *)
0x180033f9c  mov     ebx, eax
0x180033f9e  test    eax, eax
0x180033fa0  jz      short loc_180033FCB
0x180033fa2  mov     rcx, cs:WPP_GLOBAL_Control
0x180033fa9  lea     rsi, WPP_GLOBAL_Control
0x180033fb0  cmp     rcx, rsi
0x180033fb3  jz      loc_180034515
0x180033fb9  test    byte ptr [rcx+1Ch], 1
0x180033fbd  jz      loc_180034515
0x180033fc3  lea     edx, [rdi+61h]
0x180033fc6  jmp     loc_18003454E
0x180033fcb  mov     rcx, [rsp+180h+var_140]; void *
0x180033fd0  lea     r8, [rsp+180h+var_150]; struct _tag_FW_RULE **
0x180033fd5  lea     rdx, [rbp+80h+var_E0]; struct _tag_FW_QUERY *
0x180033fd9  call    ?FwMoneisQueryRules@@YAKPEAXPEAU_tag_FW_QUERY@@PEAPEAU_tag_FW_RULE@@@Z; FwMoneisQueryRules(void *,_tag_FW_QUERY *,_tag_FW_RULE * *)
0x180033fde  mov     ebx, eax
0x180033fe0  test    eax, eax
0x180033fe2  jz      short loc_18003400F
0x180033fe4  mov     rcx, cs:WPP_GLOBAL_Control
0x180033feb  lea     rsi, WPP_GLOBAL_Control
0x180033ff2  cmp     rcx, rsi
0x180033ff5  jz      loc_180033EDF
0x180033ffb  test    byte ptr [rcx+1Ch], 1
0x180033fff  jz      loc_180033EDF
0x180034005  mov     edx, 62h ; 'b'
0x18003400a  jmp     loc_180033ECC
0x18003400f  mov     rdi, [rsp+180h+var_150]
0x180034014  mov     r8, r15; unsigned __int16 *
0x180034017  mov     rcx, [rsp+180h+var_140]; void *
0x18003401c  mov     rdx, rdi; struct _tag_FW_RULE *
0x18003401f  call    ?FwMoneisDeleteRules@@YAKPEAXPEAU_tag_FW_RULE@@PEBG@Z; FwMoneisDeleteRules(void *,_tag_FW_RULE *,ushort const *)
0x180034024  mov     ebx, eax
0x180034026  test    eax, eax
0x180034028  jz      short loc_180034055
0x18003402a  mov     rcx, cs:WPP_GLOBAL_Control
0x180034031  lea     rsi, WPP_GLOBAL_Control
  ... truncated ...
```
