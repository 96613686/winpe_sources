# FwPolicy2::IsRuleGroupEnabledInStore(void *,long,ushort *,short *,int)

- ea: `0x180007e30`
- end: `0x180008f70`
- name: `?IsRuleGroupEnabledInStore@FwPolicy2@@AEAAJPEAXJPEAGPEAFH@Z`
- size: `4416`
- prototype: `int(FwPolicy2 *__hidden this, void *, int, unsigned __int16 *, __int16 *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x180006ec0`
- `0x18000c810`

## callees

- `0x180005e0c`
- `0x180006e14`
- `0x180007e30`
- `0x180009210`
- `0x180009780`
- `0x18000a530`
- `0x18000b290`
- `0x18000c3f0`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180008135`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180008135`
- `ntdll!EtwEventWrite` at `0x180007f39`
- `ntdll!EtwEventWrite` at `0x180007fd0`
- `ntdll!EtwEventWrite` at `0x180008023`
- `ntdll!EtwEventWrite` at `0x1800080b1`
- `ntdll!EtwEventWrite` at `0x1800081ee`
- `ntdll!EtwEventWrite` at `0x1800082a8`
- `ntdll!EtwEventWrite` at `0x1800084f4`
- `ntdll!EtwEventWrite` at `0x180008589`
- `ntdll!EtwEventWrite` at `0x1800085cd`
- `ntdll!EtwEventWrite` at `0x180008663`
- `ntdll!EtwEventWrite` at `0x1800086ab`
- `ntdll!EtwEventWrite` at `0x18000873d`
- `ntdll!EtwEventWrite` at `0x1800087e2`
- `ntdll!EtwEventWrite` at `0x18000884b`
- `ntdll!EtwEventWrite` at `0x180007f39`
- `ntdll!EtwEventWrite` at `0x180007fd0`
- `ntdll!EtwEventWrite` at `0x180008023`
- `ntdll!EtwEventWrite` at `0x1800080b1`
- `ntdll!EtwEventWrite` at `0x1800081ee`
- `ntdll!EtwEventWrite` at `0x1800082a8`
- `ntdll!EtwEventWrite` at `0x1800084f4`
- `ntdll!EtwEventWrite` at `0x180008589`
- `ntdll!EtwEventWrite` at `0x1800085cd`
- `ntdll!EtwEventWrite` at `0x180008663`
- `ntdll!EtwEventWrite` at `0x1800086ab`
- `ntdll!EtwEventWrite` at `0x18000873d`
- `ntdll!EtwEventWrite` at `0x1800087e2`
- `ntdll!EtwEventWrite` at `0x18000884b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180007f62`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000804d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180008217`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000851d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800085f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800086d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180007f62`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000804d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180008217`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000851d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800085f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800086d5`
- `OLEAUT32!__imp_SysStringLen` at `0x1800080ed`
- `OLEAUT32!__imp_SysStringLen` at `0x1800080ed`
- `fwbase!FwBaseFree` at `0x1800082ef`
- `fwbase!FwBaseFree` at `0x180008cc8`
- `fwbase!FwBaseFree` at `0x180008e61`
- `fwbase!FwBaseFree` at `0x1800082ef`
- `fwbase!FwBaseFree` at `0x180008cc8`
- `fwbase!FwBaseFree` at `0x180008e61`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180007f0e`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180008344`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18000839a`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800083f0`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180008479`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180007f0e`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180008344`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18000839a`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800083f0`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180008479`
- `fwbase!FwHResultToWindowsError` at `0x18000881e`
- `fwbase!FwHResultToWindowsError` at `0x18000881e`
- `fwbase!FwReportErrorAsWinError` at `0x180008bb5`
- `fwbase!FwReportErrorAsWinError` at `0x180008bb5`
- `fwbase!FwLoadIndirectString` at `0x180008c0d`
- `fwbase!FwLoadIndirectString` at `0x180008c0d`
- `fwbase!FwReportReturnError` at `0x1800087b4`
- `fwbase!FwReportReturnError` at `0x18000894c`
- `fwbase!FwReportReturnError` at `0x180008962`
- `fwbase!FwReportReturnError` at `0x180008ca5`
- `fwbase!FwReportReturnError` at `0x180008cde`
- `fwbase!FwReportReturnError` at `0x180008df3`
- `fwbase!FwReportReturnError` at `0x180008e3e`
- `fwbase!FwReportReturnError` at `0x1800087b4`
- `fwbase!FwReportReturnError` at `0x18000894c`
- `fwbase!FwReportReturnError` at `0x180008962`
- `fwbase!FwReportReturnError` at `0x180008ca5`
- `fwbase!FwReportReturnError` at `0x180008cde`
- `fwbase!FwReportReturnError` at `0x180008df3`
- `fwbase!FwReportReturnError` at `0x180008e3e`
- `fwbase!FwStringCopy` at `0x180008e0e`
- `fwbase!FwStringCopy` at `0x180008e29`
- `fwbase!FwStringCopy` at `0x180008e0e`
- `fwbase!FwStringCopy` at `0x180008e29`
- `FWPolicyIOMgr!FwFreeRules` at `0x180008810`
- `FWPolicyIOMgr!FwFreeRules` at `0x180008810`

## string_xrefs

- `0x180008117`: `@FirewallAPI.dll,-`
- `0x180008ba7`: `FWGetConfig`

## pseudocode

```c
__int64 __fastcall FwPolicy2::IsRuleGroupEnabledInStore(
        FwPolicy2 *this,
        void *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        __int16 *a5,
        unsigned int a6)
{
  unsigned int v8; // esi
  unsigned int i; // edi
  unsigned __int64 v10; // rbx
  int ProfileTypeFromProfileIndex; // esi
  signed int v12; // r15d
  FwPolicy2 *v13; // r11
  __int64 v14; // r10
  bool v15; // sf
  bool v16; // sf
  struct _tag_FW_RULE *v17; // r13
  unsigned int v18; // eax
  bool v19; // sf
  bool v20; // cc
  __int16 v21; // r12
  struct _tag_FW_RULE *v22; // rbx
  __int64 v23; // rcx
  int v24; // edx
  int v25; // eax
  __int64 v26; // rcx
  int v27; // edx
  int v28; // eax
  __int64 v29; // rcx
  int v30; // edx
  int v31; // eax
  __int64 v32; // rbx
  int v33; // edi
  int v34; // r14d
  BOOL v35; // r8d
  int j; // edx
  __int64 v37; // rcx
  __int64 v38; // rcx
  FwPolicy2 *v39; // r10
  FwPolicy2 *v40; // r10
  __int64 v41; // rcx
  unsigned int v42; // edi
  __int64 v43; // rdx
  unsigned int v44; // eax
  unsigned int v45; // eax
  int v47; // edx
  int v48; // r8d
  int v49; // edx
  int v50; // r8d
  int v51; // edx
  int v52; // r8d
  __int64 v53; // r8
  int v54; // eax
  int v55; // eax
  struct _tag_FW_RULE *v56; // rbx
  struct _tag_FW_RULE **v57; // rdi
  __int64 v58; // rdx
  unsigned int v59; // eax
  int v61; // [rsp+70h] [rbp-90h]
  struct _tag_FW_RULE *v62; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v63; // [rsp+80h] [rbp-80h] BYREF
  struct _tag_FW_RULE *v64; // [rsp+88h] [rbp-78h] BYREF
  _DWORD v65[2]; // [rsp+90h] [rbp-70h] BYREF
  int *v66; // [rsp+98h] [rbp-68h]
  __int64 v67; // [rsp+A0h] [rbp-60h]
  int v68; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v69; // [rsp+ACh] [rbp-54h] BYREF
  int v70; // [rsp+B0h] [rbp-50h] BYREF
  int v71; // [rsp+B4h] [rbp-4Ch] BYREF
  int v72; // [rsp+B8h] [rbp-48h] BYREF
  int v73; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v74; // [rsp+C8h] [rbp-38h]
  _QWORD v75[7]; // [rsp+D0h] [rbp-30h]
  int v76; // [rsp+108h] [rbp+8h]
  _DWORD v77[33]; // [rsp+10Ch] [rbp+Ch]
  __int64 v78; // [rsp+190h] [rbp+90h] BYREF
  int v79; // [rsp+198h] [rbp+98h]
  unsigned int v80; // [rsp+1A0h] [rbp+A0h]
  __int64 v81; // [rsp+1A8h] [rbp+A8h]
  int v82; // [rsp+1B0h] [rbp+B0h]
  int v83; // [rsp+1B8h] [rbp+B8h]
  int v84; // [rsp+1C0h] [rbp+C0h]
  int v85; // [rsp+1C4h] [rbp+C4h]
  int v86; // [rsp+1C8h] [rbp+C8h]
  unsigned __int16 *v87; // [rsp+1D0h] [rbp+D0h]

  v61 = (int)a2;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids);
  v8 = a6;
  for ( i = 0; i < 3; ++i )
  {
    v10 = (unsigned __int64)i << 6;
    *(_QWORD *)((char *)v75 + v10) = 0;
    *(_QWORD *)((char *)&v75[1] + v10) = 0;
    *(_QWORD *)((char *)&v75[2] + v10) = 0;
    *(_QWORD *)((char *)&v75[3] + v10) = 0;
    *(_QWORD *)((char *)&v75[4] + v10) = 0;
    *(_QWORD *)((char *)&v75[5] + v10) = 0;
    *(_QWORD *)((char *)&v75[6] + v10) = 0;
    if ( !v8 )
      continue;
    v68 = 0;
    v70 = 4;
    ProfileTypeFromProfileIndex = FwGetProfileTypeFromProfileIndex(i);
    v69 = 0;
    if ( g_Provider )
      EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_GetConfig, 0, 0);
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
    GetTickCount64();
    v12 = Int_FWGetOrSetConfig(
            1,
            (_DWORD)a2,
            17,
            ProfileTypeFromProfileIndex,
            1,
            (__int64)&v68,
            (__int64)&v70,
            (__int64)&v69);
    if ( v12 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_14;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        106,
        WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids,
        (unsigned int)v12);
    }
    v13 = WPP_GLOBAL_Control;
LABEL_14:
    v14 = g_Provider;
    if ( g_Provider )
    {
      EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
      v13 = WPP_GLOBAL_Control;
      v14 = g_Provider;
    }
    v15 = v12 < 0;
    if ( v12 > 0 )
    {
      v12 = (unsigned __int16)v12 | 0x80070000;
      v15 = v12 < 0;
    }
    if ( v15 )
      goto LABEL_154;
    v69 = 0;
    v77[16 * (unsigned __int64)i - 1] = 3 - (v68 != 0);
    if ( v14 )
    {
      EtwEventWrite(v14, MPS_CLNT_API_Enter_GetConfig, 0, 0);
      v13 = WPP_GLOBAL_Control;
    }
    if ( v13 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)v13 + 2), 105, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
    GetTickCount64();
    v12 = Int_FWGetOrSetConfig(
            1,
            (_DWORD)a2,
            16,
            ProfileTypeFromProfileIndex,
            1,
            (__int64)&v68,
            (__int64)&v70,
            (__int64)&v69);
    if ( v12 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        106,
        WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids,
        (unsigned int)v12);
    if ( g_Provider )
      EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
    v16 = v12 < 0;
    if ( v12 > 0 )
    {
      v12 = (unsigned __int16)v12 | 0x80070000;
      v16 = v12 < 0;
    }
    if ( v16 )
      goto LABEL_154;
    v8 = a6;
    v77[16 * (unsigned __int64)i] = 3 - (v68 != 0);
  }
  if ( !SysStringLen(a4) )
  {
    v12 = -2147024809;
LABEL_154:
    FwReportReturnError("FwPolicy2::IsRuleGroupEnabledInStore", (unsigned int)v12);
    return FwReportReturnError("FwPolicy2::IsRuleGroupEnabledInStore", (unsigned int)v12);
  }
  if ( !a5 )
  {
    v12 = -2147467261;
    goto LABEL_154;
  }
  v63 = 0;
  v64 = 0;
  v62 = 0;
  v17 = 0;
  v72 = 0;
  v69 = 0;
  if ( (unsigned int)_o__wcsnicmp(a4, L"@FirewallAPI.dll,-", 18) )
  {
    v54 = FwQueryRulesInRuleGroup(a2, a3, 7u, a4, &v69, &v62);
    v12 = v54;
    if ( v54 < 0 )
    {
      v58 = (unsigned int)v54;
      goto LABEL_201;
    }
    if ( v69 )
      goto LABEL_46;
    if ( (int)FwLoadIndirectString(a4, &v63) < 0 && (int)FwStringCopy(a4, &v63) < 0 )
    {
      v59 = FwStringCopy(a4, &v63);
      FwReportReturnError("FwEnumRulesFromRuleGroup", v59);
      FWFreeFirewallRules(v64);
      FWFreeFirewallRules(v62);
      FwBaseFree(v63);
      goto LABEL_203;
    }
    v55 = FWEnumFirewallRules((_DWORD)a2, 196608, a3, 7, (__int64)&v72, (__int64)&v64);
    v12 = v55;
    if ( v55 > 0 )
      v12 = (unsigned __int16)v55 | 0x80070000;
    if ( v12 < 0 )
      goto LABEL_213;
    v56 = v64;
    v57 = &v64;
    if ( v64 )
    {
      do
      {
        if ( FwRuleInGroup(v56, v63) )
        {
          *v57 = *(struct _tag_FW_RULE **)v56;
          *(_QWORD *)v56 = v62;
          ++v69;
          v62 = v56;
        }
        else
        {
          v57 = (struct _tag_FW_RULE **)v56;
        }
        v56 = *v57;
      }
      while ( *v57 );
    }
LABEL_46:
    v17 = v62;
    v62 = 0;
    v69 = 0;
    FWFreeFirewallRules(v64);
    FWFreeFirewallRules(v62);
    FwBaseFree(v63);
    v20 = v12 <= 0;
    if ( v12 < 0 )
      goto LABEL_202;
  }
  else
  {
    v73 = 3;
    v65[1] = 1;
    v81 = 1;
    v85 = 1;
    v74 = &v78;
    v65[0] = 545;
    v66 = &v73;
    v67 = 0x10000;
    v78 = 0;
    v79 = 3;
    v80 = a3;
    v82 = 3;
    v83 = 196608;
    v84 = 8;
    v86 = 5;
    v87 = a4;
    if ( g_Provider )
      EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_QueryFirewallRules, 0, 0);
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
    GetTickCount64();
    v18 = Int_FWQueryObject(
            0,
            (unsigned int)FWVerifyFirewallRuleQuery,
            (unsigned int)RPC_FWQueryFirewallRules,
            (unsigned int)RRPC_FWQueryFirewallRules,
            (__int64)Int_RPC_FWEnumFirewallRules2_0,
            (__int64)Int_RRPC_FWEnumFirewallRules2_0,
            (__int64)a2,
            (__int64)v65,
            7,
            (__int64)&v69,
            (__int64)&v62,
            0);
    v12 = v18;
    if ( v18 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v18);
    if ( g_Provider )
      EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_QueryFirewallRules, 0, 0);
    v19 = v12 < 0;
    if ( v12 > 0 )
    {
      v12 = (unsigned __int16)v12 | 0x80070000;
      v19 = v12 < 0;
    }
    if ( !v19 )
      goto LABEL_46;
    FwReportReturnError("FwQueryRulesInRuleGroup", (unsigned int)v12);
LABEL_213:
    v58 = (unsigned int)v12;
LABEL_201:
    FwReportReturnError("FwEnumRulesFromRuleGroup", v58);
    FWFreeFirewallRules(v64);
    FWFreeFirewallRules(v62);
    FwBaseFree(v63);
LABEL_202:
    v12 = FwReportReturnError("FwEnumRulesFromRuleGroup", (unsigned int)v12);
LABEL_203:
    v20 = v12 <= 0;
  }
  if ( !v20 )
    v12 = (unsigned __int16)v12 | 0x80070000;
  if ( v12 < 0 )
  {
    v43 = (unsigned int)v12;
    goto LABEL_125;
  }
  v21 = 0;
  v22 = v17;
  while ( 2 )
  {
    if ( !v22 )
    {
      v32 = 0;
      v12 = 1;
      *a5 = 0;
      while ( 1 )
      {
        while ( 1 )
        {
          if ( (unsigned int)v32 >= 3 )
            goto LABEL_126;
          v68 = 0;
          v70 = 4;
          v33 = FwGetProfileTypeFromProfileIndex((unsigned int)v32);
          if ( (v33 & a3) != 0 )
            break;
LABEL_121:
          v32 = (unsigned int)(v32 + 1);
        }
        v34 = 1;
        if ( v8 )
          break;
        v35 = 0;
LABEL_76:
        for ( j = 0; j < 7; ++j )
        {
          if ( !v35 || j == 2 )
          {
            v37 = j + 8 * v32;
            if ( LODWORD(v75[v37]) )
            {
              if ( !HIDWORD(v75[v37]) )
                goto LABEL_118;
              v34 = 0;
              v8 = 0;
            }
          }
        }
LABEL_116:
        if ( v34 )
        {
          v8 = a6;
          goto LABEL_121;
        }
        if ( v8 )
        {
LABEL_118:
          if ( v12 != 1 )
          {
            v8 = a6;
            if ( !*a5 )
            {
              *a5 = -1;
              v12 = 1;
            }
            goto LABEL_121;
          }
          v8 = a6;
          if ( *a5 )
            goto LABEL_121;
          v12 = 0;
          *a5 = -1;
          v32 = (unsigned int)(v32 + 1);
        }
        else if ( v12 == 1 )
        {
          v8 = a6;
          if ( *a5 )
            goto LABEL_121;
          v12 = 0;
          v32 = (unsigned int)(v32 + 1);
        }
        else
        {
          v8 = a6;
          if ( *a5 != -1 )
            goto LABEL_121;
          v12 = 1;
          v32 = (unsigned int)(v32 + 1);
        }
      }
      v38 = g_Provider;
      if ( v21 != -1 )
      {
        v39 = WPP_GLOBAL_Control;
        goto LABEL_94;
      }
      v71 = 0;
      if ( g_Provider )
        EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_GetConfig, 0, 0);
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
      GetTickCount64();
      v8 = Int_FWGetOrSetConfig(1, v61, 3, v33, 1, (__int64)&v68, (__int64)&v70, (__int64)&v71);
      if ( v8 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_89;
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v8);
      }
      v39 = WPP_GLOBAL_Control;
LABEL_89:
      v38 = g_Provider;
      if ( g_Provider )
      {
        EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
        v39 = WPP_GLOBAL_Control;
        v38 = g_Provider;
      }
      if ( v8 )
      {
LABEL_186:
        v53 = v8;
LABEL_187:
        v12 = FwReportErrorAsWinError("FwPolicy2::IsRuleGroupEnabledInStore", "FWGetConfig", v53);
        goto LABEL_126;
      }
      if ( v68 )
        v34 = 0;
LABEL_94:
      v71 = 0;
      if ( v38 )
      {
        EtwEventWrite(v38, MPS_CLNT_API_Enter_GetConfig, 0, 0);
        v39 = WPP_GLOBAL_Control;
      }
      if ( v39 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v39 + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)v39 + 2), 105, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
      GetTickCount64();
      v8 = Int_FWGetOrSetConfig(1, v61, 1, v33, 1, (__int64)&v68, (__int64)&v70, (__int64)&v71);
      if ( v8 )
      {
        v40 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
LABEL_101:
          v41 = g_Provider;
          if ( g_Provider )
          {
            EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
            v40 = WPP_GLOBAL_Control;
            v41 = g_Provider;
          }
          if ( v8 )
            goto LABEL_186;
          if ( !v68 )
          {
            v8 = 1;
            v34 = 0;
          }
          v71 = 0;
          if ( v41 )
          {
            EtwEventWrite(v41, MPS_CLNT_API_Enter_GetConfig, 0, 0);
            v40 = WPP_GLOBAL_Control;
          }
          if ( v40 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v40 + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)v40 + 2), 105, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
          GetTickCount64();
          v42 = Int_FWGetOrSetConfig(1, v61, 13, v33, 1, (__int64)&v68, (__int64)&v70, (__int64)&v71);
          if ( v42
            && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v42);
          }
          if ( g_Provider )
            EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
          if ( v42 )
          {
            v53 = v42;
            goto LABEL_187;
          }
          v35 = v68 == 0;
          if ( v34 != 1 )
            goto LABEL_116;
          goto LABEL_76;
        }
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v8);
      }
      v40 = WPP_GLOBAL_Control;
      goto LABEL_101;
    }
    if ( (unsigned int)(*((_DWORD *)v22 + 85) - 1) <= 5 )
    {
      if ( *((_DWORD *)v22 + 11) == 1 )
        v21 = -1;
      if ( ((unsigned int)FwGetProfileTypeFromProfileIndex(0) & *((_DWORD *)v22 + 10)) != 0 )
      {
        v23 = *((int *)v22 + 85);
        ++LODWORD(v75[v23]);
        if ( (*((_BYTE *)v22 + 292) & 1) == 0 )
        {
          v24 = *((_DWORD *)v22 + 72);
          if ( ((v24 - 1) & 0xFFFFFFFD) != 0 )
          {
            v25 = 0;
            if ( v24 == 2 )
              v25 = 2;
          }
          else
          {
            v25 = 3;
          }
          if ( !HIDWORD(v75[v23]) )
          {
            v47 = 1;
            if ( v8 )
            {
              if ( (v48 = *((_DWORD *)v22 + 11), v48 == 1) && v25 != v76 || (v47 = 0, v48 == 2) && v25 != v77[0] )
                v47 = 1;
            }
            HIDWORD(v75[v23]) = v47;
          }
        }
      }
      if ( ((unsigned int)FwGetProfileTypeFromProfileIndex(1) & *((_DWORD *)v22 + 10)) != 0 )
      {
        v26 = 8LL * *((int *)v22 + 85) + 64;
        ++*(_DWORD *)((char *)v75 + v26);
        if ( (*((_BYTE *)v22 + 292) & 1) == 0 )
        {
          v27 = *((_DWORD *)v22 + 72);
          if ( ((v27 - 1) & 0xFFFFFFFD) != 0 )
          {
            v28 = 0;
            if ( v27 == 2 )
              v28 = 2;
          }
          else
          {
            v28 = 3;
          }
          if ( !*(_DWORD *)((char *)v75 + v26 + 4) )
          {
            v49 = 1;
            if ( v8 )
            {
              if ( (v50 = *((_DWORD *)v22 + 11), v50 == 1) && v28 != v77[15] || (v49 = 0, v50 == 2) && v28 != v77[16] )
                v49 = 1;
            }
            *(_DWORD *)((char *)v75 + v26 + 4) = v49;
          }
        }
      }
      if ( ((unsigned int)FwGetProfileTypeFromProfileIndex(2) & *((_DWORD *)v22 + 10)) != 0 )
      {
        v29 = 8LL * *((int *)v22 + 85) + 128;
        ++*(_DWORD *)((char *)v75 + v29);
        if ( (*((_BYTE *)v22 + 292) & 1) == 0 )
        {
          v30 = *((_DWORD *)v22 + 72);
          if ( ((v30 - 1) & 0xFFFFFFFD) != 0 )
          {
            v31 = 0;
            if ( v30 == 2 )
              v31 = 2;
          }
          else
          {
            v31 = 3;
          }
          if ( !*(_DWORD *)((char *)v75 + v29 + 4) )
          {
            v51 = 1;
            if ( v8 )
            {
              if ( (v52 = *((_DWORD *)v22 + 11), v52 == 1) && v31 != v77[31] || (v51 = 0, v52 == 2) && v31 != v77[32] )
                v51 = 1;
            }
            *(_DWORD *)((char *)v75 + v29 + 4) = v51;
          }
        }
      }
      v22 = *(struct _tag_FW_RULE **)v22;
      continue;
    }
    break;
  }
  v43 = 2147549183LL;
LABEL_125:
  FwReportReturnError("FwPolicy2::IsRuleGroupEnabledInStore", v43);
LABEL_126:
  if ( v17 )
  {
    if ( g_Provider )
      EtwEventWrite(g_Provider, &MPS_CLNT_API_Enter_FreeFirewallRules, 0, 0);
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
    v44 = FwFreeRules(v17, 0);
    v45 = FwHResultToWindowsError(v44);
    if ( v45 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v45);
    if ( g_Provider )
      EtwEventWrite(g_Provider, &MPS_CLNT_API_Exit_FreeFirewallRules, 0, 0);
  }
  if ( v12 >= 0 )
    return (unsigned int)v12;
  return FwReportReturnError("FwPolicy2::IsRuleGroupEnabledInStore", (unsigned int)v12);
}

```

## disassembly

```asm
0x180007e30  mov     [rsp-8+arg_0], rbx
0x180007e35  push    rbp
0x180007e36  push    rsi
0x180007e37  push    rdi
0x180007e38  push    r12
0x180007e3a  push    r13
0x180007e3c  push    r14
0x180007e3e  push    r15
0x180007e40  lea     rbp, [rsp-0F0h]
0x180007e48  sub     rsp, 1F0h
0x180007e4f  mov     rax, cs:__security_cookie
0x180007e56  xor     rax, rsp
0x180007e59  mov     [rbp+120h+var_40], rax
0x180007e60  mov     rbx, [rbp+120h+arg_20]
0x180007e67  mov     r14, r9
0x180007e6a  mov     [rsp+220h+var_1B8], rbx
0x180007e6f  mov     r12, rdx
0x180007e72  mov     [rsp+220h+var_1C0], r8d
0x180007e77  mov     [rsp+220h+var_1B0], rdx
0x180007e7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e83  lea     rbx, WPP_GLOBAL_Control
0x180007e8a  cmp     rcx, rbx
0x180007e8d  jz      short loc_180007E99
0x180007e8f  test    byte ptr [rcx+1Ch], 8
0x180007e93  jnz     loc_180008D34
0x180007e99  mov     esi, [rbp+120h+arg_28]
0x180007e9f  xor     r15d, r15d
0x180007ea2  mov     edi, r15d
0x180007ea5  mov     r13d, 1
0x180007eab  cmp     edi, 3
0x180007eae  jnb     loc_1800080EA
0x180007eb4  mov     ebx, edi
0x180007eb6  shl     rbx, 6
0x180007eba  mov     [rbp+rbx+120h+var_150], 0
0x180007ec3  mov     [rbp+rbx+120h+var_148], 0
0x180007ecc  mov     [rbp+rbx+120h+var_140], 0
0x180007ed5  mov     [rbp+rbx+120h+var_138], 0
0x180007ede  mov     [rbp+rbx+120h+var_130], 0
0x180007ee7  mov     [rbp+rbx+120h+var_128], 0
0x180007ef0  mov     [rbp+rbx+120h+var_120], 0
0x180007ef9  test    esi, esi
0x180007efb  jz      loc_1800080E3
0x180007f01  mov     ecx, edi
0x180007f03  mov     [rbp+120h+var_178], r15d
0x180007f07  mov     [rbp+120h+var_170], 4
0x180007f0e  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x180007f15  nop     dword ptr [rax+rax+00h]
0x180007f1a  mov     rcx, cs:g_Provider
0x180007f21  mov     esi, eax
0x180007f23  mov     [rbp+120h+var_174], r15d
0x180007f27  test    rcx, rcx
0x180007f2a  jz      short loc_180007F45
0x180007f2c  xor     r9d, r9d
0x180007f2f  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x180007f36  xor     r8d, r8d
0x180007f39  call    cs:__imp_EtwEventWrite
0x180007f40  nop     dword ptr [rax+rax+00h]
0x180007f45  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f4c  lea     rax, WPP_GLOBAL_Control
0x180007f53  cmp     rcx, rax
0x180007f56  jz      short loc_180007F62
0x180007f58  test    byte ptr [rcx+1Ch], 8
0x180007f5c  jnz     loc_180008D4E
0x180007f62  call    cs:__imp_GetTickCount64
0x180007f69  nop     dword ptr [rax+rax+00h]
0x180007f6e  lea     rax, [rbp+120h+var_174]
0x180007f72  mov     r9d, esi
0x180007f75  mov     [rsp+220h+var_1E8], rax
0x180007f7a  mov     r8d, 11h
0x180007f80  lea     rax, [rbp+120h+var_170]
0x180007f84  mov     rdx, r12
0x180007f87  mov     [rsp+220h+var_1F0], rax
0x180007f8c  mov     ecx, r13d
0x180007f8f  lea     rax, [rbp+120h+var_178]
0x180007f93  mov     [rsp+220h+var_1F8], rax
0x180007f98  mov     dword ptr [rsp+220h+var_200], r13d
0x180007f9d  call    Int_FWGetOrSetConfig
0x180007fa2  mov     r15d, eax
0x180007fa5  test    eax, eax
0x180007fa7  jnz     loc_180008A13
0x180007fad  mov     r11, cs:WPP_GLOBAL_Control
0x180007fb4  mov     r10, cs:g_Provider
0x180007fbb  test    r10, r10
0x180007fbe  jz      short loc_180007FEA
0x180007fc0  xor     r9d, r9d
0x180007fc3  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x180007fca  xor     r8d, r8d
0x180007fcd  mov     rcx, r10
0x180007fd0  call    cs:__imp_EtwEventWrite
0x180007fd7  nop     dword ptr [rax+rax+00h]
0x180007fdc  mov     r11, cs:WPP_GLOBAL_Control
0x180007fe3  mov     r10, cs:g_Provider
0x180007fea  test    r15d, r15d
0x180007fed  jg      loc_18000899C
0x180007ff3  js      loc_180008942
0x180007ff9  mov     eax, [rbp+120h+var_178]
0x180007ffc  neg     eax
0x180007ffe  mov     [rbp+120h+var_174], 0
0x180008005  sbb     ecx, ecx
0x180008007  add     ecx, 3
0x18000800a  mov     [rbp+rbx+120h+var_118], ecx
0x18000800e  test    r10, r10
0x180008011  jz      short loc_180008036
0x180008013  xor     r9d, r9d
0x180008016  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x18000801d  xor     r8d, r8d
0x180008020  mov     rcx, r10
0x180008023  call    cs:__imp_EtwEventWrite
0x18000802a  nop     dword ptr [rax+rax+00h]
0x18000802f  mov     r11, cs:WPP_GLOBAL_Control
0x180008036  lea     rax, WPP_GLOBAL_Control
0x18000803d  cmp     r11, rax
0x180008040  jz      short loc_18000804D
0x180008042  test    byte ptr [r11+1Ch], 8
0x180008047  jnz     loc_180008D68
0x18000804d  call    cs:__imp_GetTickCount64
0x180008054  nop     dword ptr [rax+rax+00h]
0x180008059  lea     rax, [rbp+120h+var_174]
0x18000805d  mov     r9d, esi
0x180008060  mov     [rsp+220h+var_1E8], rax
0x180008065  mov     r8d, 10h
0x18000806b  lea     rax, [rbp+120h+var_170]
0x18000806f  mov     rdx, r12
0x180008072  mov     [rsp+220h+var_1F0], rax
0x180008077  mov     ecx, r13d
0x18000807a  lea     rax, [rbp+120h+var_178]
0x18000807e  mov     [rsp+220h+var_1F8], rax
0x180008083  mov     dword ptr [rsp+220h+var_200], r13d
0x180008088  call    Int_FWGetOrSetConfig
0x18000808d  mov     r15d, eax
0x180008090  test    eax, eax
0x180008092  jnz     loc_180008A51
0x180008098  mov     rcx, cs:g_Provider
0x18000809f  test    rcx, rcx
0x1800080a2  jz      short loc_1800080BD
0x1800080a4  xor     r9d, r9d
0x1800080a7  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x1800080ae  xor     r8d, r8d
0x1800080b1  call    cs:__imp_EtwEventWrite
0x1800080b8  nop     dword ptr [rax+rax+00h]
0x1800080bd  test    r15d, r15d
0x1800080c0  jg      loc_180008A00
0x1800080c6  js      loc_180008942
0x1800080cc  mov     eax, [rbp+120h+var_178]
0x1800080cf  mov     esi, [rbp+120h+arg_28]
0x1800080d5  neg     eax
0x1800080d7  sbb     ecx, ecx
0x1800080d9  add     ecx, 3
0x1800080dc  mov     [rbp+rbx+120h+var_114], ecx
0x1800080e0  xor     r15d, r15d
0x1800080e3  inc     edi
0x1800080e5  jmp     loc_180007EAB
0x1800080ea  mov     rcx, r14; pbstr
0x1800080ed  call    cs:__imp_SysStringLen
0x1800080f4  nop     dword ptr [rax+rax+00h]
0x1800080f9  test    eax, eax
0x1800080fb  jz      loc_180008D82
0x180008101  cmp     [rsp+220h+var_1B8], 0
0x180008107  jz      loc_180008D8D
0x18000810d  mov     r8d, 12h
0x180008113  mov     [rbp+120h+var_1A0], r15
0x180008117  lea     rdx, aFirewallapiDll_14; "@FirewallAPI.dll,-"
0x18000811e  mov     [rbp+120h+var_198], r15
0x180008122  mov     rcx, r14
0x180008125  mov     [rsp+220h+var_1A8], r15
0x18000812a  mov     r13, r15
0x18000812d  mov     [rbp+120h+var_168], r15d
0x180008131  mov     [rbp+120h+var_174], r15d
0x180008135  call    cs:__imp__o__wcsnicmp
0x18000813c  nop     dword ptr [rax+rax+00h]
0x180008141  mov     edi, [rsp+220h+var_1C0]
0x180008145  test    eax, eax
0x180008147  jnz     loc_180008BC9
0x18000814d  mov     ecx, 1
0x180008152  mov     [rbp+120h+var_160], 3
0x180008159  lea     rax, [rbp+120h+var_90]
0x180008160  mov     [rbp+120h+var_18C], ecx
0x180008163  mov     [rbp+120h+var_78], rcx
0x18000816a  mov     [rbp+120h+var_5C], ecx
0x180008170  mov     rcx, cs:g_Provider
0x180008177  mov     [rbp+120h+var_158], rax
0x18000817b  lea     rax, [rbp+120h+var_160]
0x18000817f  mov     [rbp+120h+var_190], 221h
0x180008186  mov     [rbp+120h+var_188], rax
0x18000818a  mov     [rbp+120h+var_180], 10000h
0x180008192  mov     [rbp+120h+var_90], 0
0x18000819d  mov     [rbp+120h+var_88], 3
0x1800081a7  mov     [rbp+120h+var_80], edi
0x1800081ad  mov     [rbp+120h+var_70], 3
0x1800081b7  mov     [rbp+120h+var_68], 30000h
0x1800081c1  mov     [rbp+120h+var_60], 8
0x1800081cb  mov     [rbp+120h+var_58], 5
0x1800081d5  mov     [rbp+120h+var_50], r14
0x1800081dc  test    rcx, rcx
0x1800081df  jz      short loc_1800081FA
0x1800081e1  xor     r9d, r9d
0x1800081e4  lea     rdx, MPS_CLNT_API_Enter_QueryFirewallRules
0x1800081eb  xor     r8d, r8d
0x1800081ee  call    cs:__imp_EtwEventWrite
0x1800081f5  nop     dword ptr [rax+rax+00h]
0x1800081fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180008201  lea     rdi, WPP_GLOBAL_Control
0x180008208  cmp     rcx, rdi
0x18000820b  jz      short loc_180008217
0x18000820d  test    byte ptr [rcx+1Ch], 8
0x180008211  jnz     loc_180008D98
0x180008217  call    cs:__imp_GetTickCount64
0x18000821e  nop     dword ptr [rax+rax+00h]
0x180008223  mov     [rsp+220h+var_1C8], r15d
0x180008228  lea     rax, [rsp+220h+var_1A8]
0x18000822d  mov     [rsp+220h+var_1D0], rax
0x180008232  lea     r9, RRPC_FWQueryFirewallRules
0x180008239  lea     rax, [rbp+120h+var_174]
0x18000823d  xor     ecx, ecx
0x18000823f  mov     [rsp+220h+var_1D8], rax
0x180008244  lea     r8, RPC_FWQueryFirewallRules
0x18000824b  mov     [rsp+220h+var_1E0], 7
0x180008252  lea     rax, [rbp+120h+var_190]
0x180008256  mov     [rsp+220h+var_1E8], rax
0x18000825b  lea     rdx, FWVerifyFirewallRuleQuery
0x180008262  lea     rax, ?Int_RRPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RRPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x180008269  mov     [rsp+220h+var_1F0], r12
0x18000826e  mov     [rsp+220h+var_1F8], rax
0x180008273  lea     rax, ?Int_RPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x18000827a  mov     [rsp+220h+var_200], rax
0x18000827f  call    Int_FWQueryObject
0x180008284  mov     r15d, eax
0x180008287  test    eax, eax
0x180008289  jnz     loc_180008DB2
0x18000828f  mov     rcx, cs:g_Provider
0x180008296  test    rcx, rcx
0x180008299  jz      short loc_1800082B4
0x18000829b  xor     r9d, r9d
0x18000829e  lea     rdx, MPS_CLNT_API_Exit_QueryFirewallRules
0x1800082a5  xor     r8d, r8d
0x1800082a8  call    cs:__imp_EtwEventWrite
0x1800082af  nop     dword ptr [rax+rax+00h]
0x1800082b4  test    r15d, r15d
0x1800082b7  jg      loc_180008A9F
0x1800082bd  js      loc_180008DE9
0x1800082c3  mov     r13, [rsp+220h+var_1A8]
0x1800082c8  mov     [rsp+220h+var_1A8], 0
0x1800082d1  mov     [rbp+120h+var_174], 0
0x1800082d8  mov     rcx, [rbp+120h+var_198]
0x1800082dc  call    FWFreeFirewallRules
0x1800082e1  mov     rcx, [rsp+220h+var_1A8]
0x1800082e6  call    FWFreeFirewallRules
0x1800082eb  mov     rcx, [rbp+120h+var_1A0]
0x1800082ef  call    cs:__imp_FwBaseFree
0x1800082f6  nop     dword ptr [rax+rax+00h]
0x1800082fb  test    r15d, r15d
0x1800082fe  js      loc_180008CD4
0x180008304  jg      loc_180008A8F
0x18000830a  test    r15d, r15d
0x18000830d  js      loc_180008D1C
0x180008313  xor     r12d, r12d
0x180008316  mov     rbx, r13
0x180008319  mov     ecx, 0FFFFFFFFh
0x18000831e  test    rbx, rbx
0x180008321  jz      loc_180008449
0x180008327  mov     eax, [rbx+154h]
0x18000832d  dec     eax
0x18000832f  cmp     eax, 5
0x180008332  ja      loc_1800087A8
0x180008338  cmp     dword ptr [rbx+2Ch], 1
0x18000833c  jnz     short loc_180008342
0x18000833e  movzx   r12d, cx
0x180008342  xor     ecx, ecx
0x180008344  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x18000834b  nop     dword ptr [rax+rax+00h]
0x180008350  test    [rbx+28h], eax
0x180008353  jz      short loc_180008395
0x180008355  movsxd  rax, dword ptr [rbx+154h]
0x18000835c  lea     rcx, ds:0[rax*8]
0x180008364  inc     dword ptr [rbp+rcx+120h+var_150]
0x180008368  test    byte ptr [rbx+124h], 1
0x18000836f  jnz     short loc_180008395
0x180008371  mov     edx, [rbx+120h]
0x180008377  lea     eax, [rdx-1]
0x18000837a  test    eax, 0FFFFFFFDh
0x18000837f  jnz     loc_180008E8D
0x180008385  mov     eax, 3
0x18000838a  cmp     dword ptr [rbp+rcx+120h+var_150+4], 0
0x18000838f  jz      loc_18000888E
0x180008395  mov     ecx, 1
0x18000839a  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x1800083a1  nop     dword ptr [rax+rax+00h]
0x1800083a6  test    [rbx+28h], eax
0x1800083a9  jz      short loc_1800083EB
0x1800083ab  movsxd  rax, dword ptr [rbx+154h]
0x1800083b2  lea     rcx, ds:40h[rax*8]
0x1800083ba  inc     dword ptr [rbp+rcx+120h+var_150]
0x1800083be  test    byte ptr [rbx+124h], 1
0x1800083c5  jnz     short loc_1800083EB
0x1800083c7  mov     edx, [rbx+120h]
0x1800083cd  lea     eax, [rdx-1]
0x1800083d0  test    eax, 0FFFFFFFDh
0x1800083d5  jnz     loc_180008E9F
0x1800083db  mov     eax, 3
0x1800083e0  cmp     dword ptr [rbp+rcx+120h+var_150+4], 0
  ... truncated ...
```
