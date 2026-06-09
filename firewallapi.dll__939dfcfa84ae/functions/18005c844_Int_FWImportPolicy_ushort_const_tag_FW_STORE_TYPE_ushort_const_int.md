# Int_FWImportPolicy(ushort const *,_tag_FW_STORE_TYPE,ushort const *,int *)

- ea: `0x18005c844`
- end: `0x18005d836`
- name: `?Int_FWImportPolicy@@YAKPEBGW4_tag_FW_STORE_TYPE@@0PEAH@Z`
- size: `4082`
- prototype: `unsigned int __high(const unsigned __int16 *, enum _tag_FW_STORE_TYPE, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800518a0`

## callees

- `0x180005e0c`
- `0x18000cc80`
- `0x18000d0f0`
- `0x180014110`
- `0x180025c68`
- `0x180026c9c`
- `0x180028370`
- `0x180028eb0`
- `0x1800294b0`
- `0x18002a1f4`
- `0x18003336c`
- `0x18004db80`
- `0x18004dbc0`
- `0x18004dd60`
- `0x18004df00`
- `0x18004e3c0`
- `0x18004e730`
- `0x18004edb0`
- `0x18004eea0`
- `0x18004ef90`
- `0x18004f080`
- `0x18004f170`
- `0x180053880`
- `0x18005c34c`
- `0x18005c3ac`
- `0x18005c5f8`
- `0x18005c844`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegRestoreKeyW` at `0x18005ca4d`
- `api-ms-win-core-registry-l1-1-0!RegRestoreKeyW` at `0x18005ca4d`
- `fwbase!FwBaseAlloc` at `0x18005cc07`
- `fwbase!FwBaseAlloc` at `0x18005cc07`
- `fwbase!FwBaseFree` at `0x18005cbf8`
- `fwbase!FwBaseFree` at `0x18005ccfa`
- `fwbase!FwBaseFree` at `0x18005d6e3`
- `fwbase!FwBaseFree` at `0x18005cbf8`
- `fwbase!FwBaseFree` at `0x18005ccfa`
- `fwbase!FwBaseFree` at `0x18005d6e3`
- `fwbase!FwHResultToWindowsError` at `0x18005d6f1`
- `fwbase!FwHResultToWindowsError` at `0x18005d6f1`
- `fwbase!FwReleasePrivilege` at `0x18005c9f9`
- `fwbase!FwReleasePrivilege` at `0x18005ca0a`
- `fwbase!FwReleasePrivilege` at `0x18005ca9c`
- `fwbase!FwReleasePrivilege` at `0x18005caad`
- `fwbase!FwReleasePrivilege` at `0x18005c9f9`
- `fwbase!FwReleasePrivilege` at `0x18005ca0a`
- `fwbase!FwReleasePrivilege` at `0x18005ca9c`
- `fwbase!FwReleasePrivilege` at `0x18005caad`
- `FWPolicyIOMgr!FwEnumRules` at `0x18005d24f`
- `FWPolicyIOMgr!FwEnumRules` at `0x18005d3cc`
- `FWPolicyIOMgr!FwEnumRules` at `0x18005d4e6`
- `FWPolicyIOMgr!FwEnumRules` at `0x18005d24f`
- `FWPolicyIOMgr!FwEnumRules` at `0x18005d3cc`
- `FWPolicyIOMgr!FwEnumRules` at `0x18005d4e6`
- `FWPolicyIOMgr!FwGetConfig` at `0x18005cf1c`
- `FWPolicyIOMgr!FwGetConfig` at `0x18005cf1c`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005d39a`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005d4b4`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005d5c7`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005d67e`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005d691`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005d6a3`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005d39a`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005d4b4`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005d5c7`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005d67e`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005d691`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005d6a3`
- `FWPolicyIOMgr!FwFreeSets` at `0x18005d13f`
- `FWPolicyIOMgr!FwFreeSets` at `0x18005d203`
- `FWPolicyIOMgr!FwFreeSets` at `0x18005d6b5`
- `FWPolicyIOMgr!FwFreeSets` at `0x18005d6c8`
- `FWPolicyIOMgr!FwFreeSets` at `0x18005d13f`
- `FWPolicyIOMgr!FwFreeSets` at `0x18005d203`
- `FWPolicyIOMgr!FwFreeSets` at `0x18005d6b5`
- `FWPolicyIOMgr!FwFreeSets` at `0x18005d6c8`
- `FWPolicyIOMgr!FwCreateLocalTempStore` at `0x18005cac5`
- `FWPolicyIOMgr!FwCreateLocalTempStore` at `0x18005cac5`
- `FWPolicyIOMgr!FwDestroyLocalTempStore` at `0x18005d646`
- `FWPolicyIOMgr!FwDestroyLocalTempStore` at `0x18005d646`
- `FWPolicyIOMgr!FwGetGlobalConfigFromLocalTempStore` at `0x18005cc2c`
- `FWPolicyIOMgr!FwGetGlobalConfigFromLocalTempStore` at `0x18005cc2c`
- `FWPolicyIOMgr!FwEnumSets` at `0x18005d0b4`
- `FWPolicyIOMgr!FwEnumSets` at `0x18005d177`
- `FWPolicyIOMgr!FwEnumSets` at `0x18005d0b4`
- `FWPolicyIOMgr!FwEnumSets` at `0x18005d177`

## string_xrefs

- `0x18005d600`: `Imported %lu rules: %lu firewall rules, %lu connection security rules, %lu main mode rules`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Int_FWImportPolicy(__int64 a1, unsigned int a2, const WCHAR *a3, _DWORD *a4)
{
  unsigned int v6; // r14d
  _BYTE *v8; // r13
  signed int v9; // ebx
  FwPolicy2 *v10; // rcx
  __int64 v11; // rdx
  FwPolicy2 *v12; // rcx
  __int64 v13; // rdx
  LSTATUS v14; // eax
  int v15; // eax
  int v16; // eax
  unsigned int i; // edi
  int GlobalConfigFromLocalTempStore; // eax
  __int64 v19; // r9
  int v20; // eax
  FwPolicy2 *v21; // rcx
  __int64 v22; // rdx
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  __int64 v27; // rsi
  unsigned int v28; // edi
  int Config; // eax
  char v30; // al
  int v31; // eax
  FwPolicy2 *v32; // rcx
  __int64 v33; // rdx
  FwPolicy2 *v34; // rcx
  __int64 v35; // rdx
  int v36; // eax
  unsigned int j; // esi
  int v38; // eax
  _DWORD *v39; // rdi
  int v40; // eax
  int v41; // eax
  _DWORD *v42; // rdi
  int v43; // eax
  int v44; // r15d
  _DWORD *v45; // rdi
  int v46; // esi
  int v47; // eax
  int v48; // r14d
  _DWORD *v49; // rdi
  int v50; // eax
  _DWORD *v51; // rdi
  int v52; // eax
  unsigned int v53; // ebx
  __int64 v55; // [rsp+20h] [rbp-E0h]
  __int64 v56; // [rsp+28h] [rbp-D8h]
  __int64 v57; // [rsp+30h] [rbp-D0h]
  __int128 v59; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v60; // [rsp+58h] [rbp-A8h]
  __int128 v61; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v62; // [rsp+70h] [rbp-90h]
  const WCHAR *v63; // [rsp+78h] [rbp-88h]
  unsigned int v64; // [rsp+80h] [rbp-80h] BYREF
  __int64 v65; // [rsp+88h] [rbp-78h] BYREF
  __int64 v66; // [rsp+90h] [rbp-70h] BYREF
  void *v67; // [rsp+98h] [rbp-68h] BYREF
  void *v68; // [rsp+A0h] [rbp-60h] BYREF
  void *v69; // [rsp+A8h] [rbp-58h] BYREF
  void *Src; // [rsp+B0h] [rbp-50h] BYREF
  void *v71; // [rsp+B8h] [rbp-48h] BYREF
  void **v72; // [rsp+C0h] [rbp-40h] BYREF
  HKEY hKey; // [rsp+C8h] [rbp-38h]
  __int128 v74; // [rsp+D0h] [rbp-30h]
  _BYTE v75[176]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v76[120]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v77[1024]; // [rsp+280h] [rbp+180h] BYREF

  v63 = a3;
  v6 = a2;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids);
  v66 = 0;
  v65 = 0;
  v69 = 0;
  v68 = 0;
  v67 = 0;
  Src = 0;
  v71 = 0;
  v8 = 0;
  v64 = 0;
  memset_0(v76, 0, 0xEEu);
  *a4 = 0;
  memset_0(&v72, 0, 0xD0u);
  v72 = &CTempRegKey::`vftable';
  hKey = 0;
  v74 = 0;
  v9 = CTempRegKey::Init((CTempRegKey *)&v72);
  if ( v9 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_234;
    v11 = 42;
    goto LABEL_8;
  }
  v61 = 0;
  v62 = 0;
  CPrivilegeEnabler::CPrivilegeEnabler((CPrivilegeEnabler *)&v61, 0x11u);
  v59 = 0;
  v60 = 0;
  CPrivilegeEnabler::CPrivilegeEnabler((CPrivilegeEnabler *)&v59, 0x12u);
  v9 = DWORD2(v59);
  if ( SDWORD2(v59) < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_14;
    v13 = 43;
LABEL_13:
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids, (unsigned int)v9);
LABEL_14:
    FwReleasePrivilege(v60);
    FwReleasePrivilege(v62);
    goto LABEL_234;
  }
  v9 = DWORD2(v61);
  if ( SDWORD2(v61) < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_14;
    v13 = 44;
    goto LABEL_13;
  }
  v14 = RegRestoreKeyW(hKey, a3, 0);
  v9 = v14;
  if ( v14 > 0 )
    v9 = (unsigned __int16)v14 | 0x80070000;
  if ( v9 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_14;
    v13 = 45;
    goto LABEL_13;
  }
  FwReleasePrivilege(v60);
  FwReleasePrivilege(v62);
  v9 = FwCreateLocalTempStore(v75, hKey, &v66);
  if ( v9 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_234;
    v11 = 46;
    goto LABEL_8;
  }
  v15 = FWOpenPolicyStore(0x221u, a1, v6, 2u, 0, &v65);
  v9 = v15;
  if ( v15 > 0 )
    v9 = (unsigned __int16)v15 | 0x80070000;
  if ( v9 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_234;
    v11 = 47;
    goto LABEL_8;
  }
  if ( v6 == 6 )
  {
    v16 = FWChangeTransactionalState(v65, 1);
    v9 = v16;
    if ( v16 > 0 )
      v9 = (unsigned __int16)v16 | 0x80070000;
    if ( v9 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_234;
      v11 = 48;
      goto LABEL_8;
    }
  }
  for ( i = 1; i < 0x13; ++i )
  {
    if ( i - 1 > 1 && i != 11 )
    {
      v8 = v77;
      v64 = 1024;
      v9 = 0;
      do
      {
        if ( v9 == -2147024662 )
        {
          if ( v8 != v77 )
            FwBaseFree(v8);
          v8 = (_BYTE *)FwBaseAlloc(v64);
          if ( !v8 )
          {
            v9 = -2147024882;
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_234;
            }
            v11 = 49;
            goto LABEL_8;
          }
        }
        GlobalConfigFromLocalTempStore = FwGetGlobalConfigFromLocalTempStore(hKey, i, v8, &v64);
        v9 = GlobalConfigFromLocalTempStore;
      }
      while ( GlobalConfigFromLocalTempStore == -2147024662 );
      if ( GlobalConfigFromLocalTempStore != -2147024894 && GlobalConfigFromLocalTempStore != -2147024846 )
      {
        if ( GlobalConfigFromLocalTempStore >= 0 )
        {
          v19 = v64;
          goto LABEL_57;
        }
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_234;
        v11 = 52;
LABEL_8:
        WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids, (unsigned int)v9);
        goto LABEL_234;
      }
      if ( i == 10 )
      {
        *(_DWORD *)v8 = 545;
        v19 = 4;
        v64 = 4;
LABEL_57:
        if ( !(_DWORD)v19 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
          v19 = v64;
        }
        if ( i == 10 && *(_DWORD *)v8 > 0x221u )
        {
          *a4 = 1;
          *(_DWORD *)v8 = 545;
          v19 = 4;
          v64 = 4;
        }
        v20 = FWSetGlobalConfig2(v65, i, v8, v19);
        v9 = v20;
        if ( v20 == 50 )
        {
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v22 = 53;
LABEL_75:
            WPP_SF_d(*((_QWORD *)v21 + 2), v22, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids, i);
            continue;
          }
        }
        else
        {
          if ( v20 > 0 )
            v9 = (unsigned __int16)v20 | 0x80070000;
          if ( v9 < 0 )
          {
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_234;
            }
            v11 = 54;
            goto LABEL_8;
          }
          if ( v8 != v77 )
          {
            FwBaseFree(v8);
            v8 = 0;
          }
        }
      }
      else
      {
        v23 = FWSetGlobalConfig2(v65, i, 0, 0);
        v9 = v23;
        if ( v23 == 50 )
        {
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v22 = 50;
            goto LABEL_75;
          }
        }
        else
        {
          if ( v23 > 0 )
            v9 = (unsigned __int16)v23 | 0x80070000;
          if ( v9 < 0 )
          {
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_234;
            }
            v11 = 51;
            goto LABEL_8;
          }
        }
      }
    }
  }
  v24 = FWDeleteAllMainModeRules(v65);
  v9 = v24;
  if ( v24 > 0 )
    v9 = (unsigned __int16)v24 | 0x80070000;
  if ( v9 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_234;
    v11 = 55;
    goto LABEL_8;
  }
  v25 = FWDeleteAllConnectionSecurityRules(v65);
  v9 = v25;
  if ( v25 > 0 )
    v9 = (unsigned __int16)v25 | 0x80070000;
  if ( v9 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_234;
    v11 = 56;
    goto LABEL_8;
  }
  v26 = FWDeleteAllFirewallRules(v65);
  v9 = v26;
  if ( v26 > 0 )
    v9 = (unsigned __int16)v26 | 0x80070000;
  if ( v9 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_234;
    v11 = 57;
    goto LABEL_8;
  }
  v27 = 0;
  while ( 2 )
  {
    v28 = 1;
    while ( 2 )
    {
      v64 = 1024;
      Config = FwGetConfig(v66, v28, *((unsigned int *)qword_18008E2D0 + v27), v77, &v64);
      v9 = Config;
      if ( Config == -2147024894 || Config == -2147024846 )
      {
        v36 = FWSetConfig(v65, v28, *((_DWORD *)qword_18008E2D0 + v27), 0, 0);
        v9 = v36;
        if ( v36 == 50 )
        {
          v32 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v33 = (unsigned int)(v36 + 8);
LABEL_133:
            WPP_SF_d(*((_QWORD *)v32 + 2), v33, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids, v28);
          }
        }
        else
        {
          if ( v36 > 0 )
            v9 = (unsigned __int16)v36 | 0x80070000;
          if ( v9 < 0 )
          {
            v34 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_233;
            }
            v35 = 59;
LABEL_128:
            WPP_SF_d(*((_QWORD *)v34 + 2), v35, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids, (unsigned int)v9);
            goto LABEL_233;
          }
        }
      }
      else
      {
        if ( Config < 0 )
        {
          v34 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v35 = 60;
            goto LABEL_128;
          }
          goto LABEL_233;
        }
        v30 = v64;
        if ( !v64 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
          v30 = v64;
        }
        v31 = FWSetConfig(v65, v28, *((_DWORD *)qword_18008E2D0 + v27), (unsigned int)v77, v30);
        v9 = v31;
        if ( v31 == 50 )
        {
          v32 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v33 = (unsigned int)(v31 + 11);
            goto LABEL_133;
          }
        }
        else
        {
          if ( v31 > 0 )
            v9 = (unsigned __int16)v31 | 0x80070000;
          if ( v9 < 0 )
          {
            v34 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v35 = 62;
              goto LABEL_128;
            }
            goto LABEL_233;
          }
        }
      }
      if ( ++v28 < 0x13 )
        continue;
      break;
    }
    v27 = (unsigned int)(v27 + 1);
    if ( (unsigned int)v27 < 3 )
      continue;
    break;
  }
  for ( j = 1; j <= 2; ++j )
  {
    v9 = FwEnumSets(v66, 0, j, &Src, &v64, 458752, 0);
    if ( v9 < 0 )
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_233;
      v35 = 63;
      goto LABEL_128;
    }
    v38 = FWDeleteAllAuthenticationSets(v65, j);
    v9 = v38;
    if ( v38 > 0 )
      v9 = (unsigned __int16)v38 | 0x80070000;
    if ( v9 < 0 )
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_233;
      v35 = 64;
      goto LABEL_128;
    }
    v39 = Src;
    if ( Src )
    {
      do
      {
        if ( (v39[20] & 0x60000) != 0 )
          *a4 = 1;
        if ( (v39[20] & 0x40000) == 0 )
        {
          v40 = FWAddAuthenticationSet(v65, v39);
          v9 = v40;
          if ( v40 > 0 )
            v9 = (unsigned __int16)v40 | 0x80070000;
          if ( v9 < 0 )
          {
            v34 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v35 = 65;
              goto LABEL_128;
            }
            goto LABEL_233;
          }
        }
        v39 = *(_DWORD **)v39;
      }
      while ( v39 );
      v39 = Src;
    }
    FwFreeSets(v39, 0);
    Src = 0;
    v9 = FwEnumSets(v66, 1, j, &v71, &v64, 458752, 0);
    if ( v9 < 0 )
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_233;
      v35 = 66;
      goto LABEL_128;
    }
    v41 = FWDeleteAllCryptoSets(v65, j);
    v9 = v41;
    if ( v41 > 0 )
      v9 = (unsigned __int16)v41 | 0x80070000;
    if ( v9 < 0 )
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_233;
      v35 = 67;
      goto LABEL_128;
    }
    v42 = v71;
    if ( v71 )
    {
      do
      {
        if ( (v42[22] & 0x60000) != 0 )
          *a4 = 1;
        if ( (v42[22] & 0x40000) == 0 )
        {
          v43 = FWAddCryptoSet(v65, v42);
          v9 = v43;
          if ( v43 > 0 )
            v9 = (unsigned __int16)v43 | 0x80070000;
          if ( v9 < 0 )
          {
            v34 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v35 = 68;
              goto LABEL_128;
            }
            goto LABEL_233;
          }
        }
        v42 = *(_DWORD **)v42;
      }
      while ( v42 );
      v42 = v71;
    }
    FwFreeSets(v42, 1);
    v71 = 0;
  }
  v9 = FwEnumRules(v66, 2, &v67, &v64, 458752, 0x7FFFFFFF, 0);
  if ( v9 < 0 )
  {
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v35 = 69;
      goto LABEL_128;
    }
    goto LABEL_233;
  }
  v44 = 0;
  v45 = v67;
  v46 = 0;
  if ( v67 )
  {
    do
    {
      if ( (v45[64] & 0x60000) != 0 )
        *a4 = 1;
      if ( (v45[64] & 0x40000) == 0 )
      {
        v47 = FWAddMainModeRule(v65, v45);
        v9 = v47;
        if ( v47 == 50 )
        {
          v9 = 0;
          *a4 = 1;
        }
        else if ( v47 > 0 )
        {
          v9 = (unsigned __int16)v47 | 0x80070000;
        }
        if ( v9 < 0 )
        {
          v34 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v35 = 70;
            goto LABEL_128;
          }
          goto LABEL_233;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_New_ZTN_Audit_Events>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_New_ZTN_Audit_Events>::GetImpl'::`2'::impl) )
          ++v44;
      }
      v45 = *(_DWORD **)v45;
    }
    while ( v45 );
    v45 = v67;
  }
  FwFreeRules(v45, 2);
  v67 = 0;
  v9 = FwEnumRules(v66, 1, &v68, &v64, 458752, 0x7FFFFFFF, 0);
  if ( v9 < 0 )
  {
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v35 = 71;
      goto LABEL_128;
    }
    goto LABEL_233;
  }
  v48 = 0;
  v49 = v68;
  if ( v68 )
  {
    do
    {
      if ( (v49[96] & 0x60000) != 0 )
        *a4 = 1;
      if ( (v49[96] & 0x40000) == 0 )
      {
        v50 = FWAddConnectionSecurityRule(v65, v49);
        v9 = v50;
        if ( v50 > 0 )
          v9 = (unsigned __int16)v50 | 0x80070000;
        if ( v9 < 0 )
        {
          v34 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v35 = 72;
            goto LABEL_128;
          }
          goto LABEL_233;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_New_ZTN_Audit_Events>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_New_ZTN_Audit_Events>::GetImpl'::`2'::impl) )
          ++v48;
      }
      v49 = *(_DWORD **)v49;
    }
    while ( v49 );
    v49 = v68;
  }
  FwFreeRules(v49, 1);
  v68 = 0;
  v9 = FwEnumRules(v66, 0, &v69, &v64, 458752, 0x7FFFFFFF, 0);
  if ( v9 < 0 )
  {
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v35 = 73;
      goto LABEL_128;
    }
    goto LABEL_233;
  }
  v51 = v69;
  if ( !v69 )
  {
LABEL_229:
    FwFreeRules(v51, 0);
    v69 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_New_ZTN_Audit_Events>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_New_ZTN_Audit_Events>::GetImpl'::`2'::impl) )
    {
      LODWORD(v57) = v44;
      LODWORD(v56) = v48;
      LODWORD(v55) = v46;
      if ( (int)StringCchPrintfW(
                  v76,
                  0x77u,
                  L"Imported %lu rules: %lu firewall rules, %lu connection security rules, %lu main mode rules",
                  (unsigned int)(v44 + v46 + v48),
                  v55,
                  v56,
                  v57) < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      FWAuditLogPolicyImported(v63, v76);
    }
    goto LABEL_233;
  }
  while ( 2 )
  {
    if ( (v51[84] & 0x60000) != 0 )
      *a4 = 1;
    if ( (v51[84] & 0x40000) != 0 )
    {
LABEL_227:
      v51 = *(_DWORD **)v51;
      if ( !v51 )
      {
        v51 = v69;
        goto LABEL_229;
      }
      continue;
    }
    break;
  }
  v52 = FWAddFirewallRule(v65, v51);
  v9 = v52;
  if ( v52 > 0 )
    v9 = (unsigned __int16)v52 | 0x80070000;
  if ( v9 >= 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_New_ZTN_Audit_Events>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_New_ZTN_Audit_Events>::GetImpl'::`2'::impl) )
      ++v46;
    goto LABEL_227;
  }
  v34 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v35 = 74;
    goto LABEL_128;
  }
LABEL_233:
  v6 = a2;
LABEL_234:
  if ( v66 )
    FwDestroyLocalTempStore();
  if ( v65 )
  {
    if ( v6 == 6 && v9 >= 0 )
      FWChangeTransactionalState(v65, 0);
    FWClosePolicyStore();
  }
  FwFreeRules(v67, 2);
  FwFreeRules(v68, 1);
  FwFreeRules(v69, 0);
  FwFreeSets(Src, 0);
  FwFreeSets(v71, 1);
  if ( v8 != v77 )
    FwBaseFree(v8);
  v53 = FwHResultToWindowsError((unsigned int)v9);
  CTempRegKey::~CTempRegKey((CTempRegKey *)&v72);
  return v53;
}

```

## disassembly

```asm
0x18005c844  push    rbp
0x18005c846  push    rbx
0x18005c847  push    rsi
0x18005c848  push    rdi
0x18005c849  push    r12
0x18005c84b  push    r13
0x18005c84d  push    r14
0x18005c84f  push    r15
0x18005c851  lea     rbp, [rsp-598h]
0x18005c859  sub     rsp, 698h
0x18005c860  mov     rax, cs:__security_cookie
0x18005c867  xor     rax, rsp
0x18005c86a  mov     [rbp+5D0h+var_50], rax
0x18005c871  mov     r12, r9
0x18005c874  mov     rsi, r8
0x18005c877  mov     [rsp+6D0h+var_658], r8
0x18005c87c  mov     r14d, edx
0x18005c87f  mov     [rsp+6D0h+var_690], edx
0x18005c883  mov     rdi, rcx
0x18005c886  lea     rax, WPP_GLOBAL_Control
0x18005c88d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c894  cmp     rcx, rax
0x18005c897  jz      short loc_18005C8B4
0x18005c899  test    byte ptr [rcx+1Ch], 8
0x18005c89d  jz      short loc_18005C8B4
0x18005c89f  mov     edx, 29h ; ')'
0x18005c8a4  lea     r8, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids
0x18005c8ab  mov     rcx, [rcx+10h]
0x18005c8af  call    WPP_SF_
0x18005c8b4  mov     [rbp+5D0h+var_640], 0
0x18005c8bc  mov     [rbp+5D0h+var_648], 0
0x18005c8c4  mov     [rbp+5D0h+var_628], 0
0x18005c8cc  mov     [rbp+5D0h+var_630], 0
0x18005c8d4  mov     [rbp+5D0h+var_638], 0
0x18005c8dc  mov     [rbp+5D0h+Src], 0
0x18005c8e4  mov     [rbp+5D0h+var_618], 0
0x18005c8ec  xor     r13d, r13d
0x18005c8ef  mov     [rbp+5D0h+var_650], r13d
0x18005c8f3  xor     edx, edx; Val
0x18005c8f5  mov     r8d, 0EEh; Size
0x18005c8fb  lea     rcx, [rbp+5D0h+var_540]; void *
0x18005c902  call    memset_0
0x18005c907  mov     [r12], r13d
0x18005c90b  xor     edx, edx; Val
0x18005c90d  mov     r8d, 0D0h; Size
0x18005c913  lea     rcx, [rbp+5D0h+var_610]; void *
0x18005c917  call    memset_0
0x18005c91c  lea     rax, ??_7CTempRegKey@@6B@; const CTempRegKey::`vftable'
0x18005c923  mov     [rbp+5D0h+var_610], rax
0x18005c927  mov     [rbp+5D0h+hKey], r13
0x18005c92b  xorps   xmm0, xmm0
0x18005c92e  movdqa  [rbp+5D0h+var_600], xmm0
0x18005c933  lea     rcx, [rbp+5D0h+var_610]; this
0x18005c937  call    ?Init@CTempRegKey@@QEAAJXZ; CTempRegKey::Init(void)
0x18005c93c  mov     ebx, eax
0x18005c93e  lea     r15d, [r13+1]
0x18005c942  test    eax, eax
0x18005c944  jns     short loc_18005C983
0x18005c946  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c94d  lea     rax, WPP_GLOBAL_Control
0x18005c954  cmp     rcx, rax
0x18005c957  jz      loc_18005D63D
0x18005c95d  test    [rcx+1Ch], r15b
0x18005c961  jz      loc_18005D63D
0x18005c967  lea     edx, [r13+2Ah]
0x18005c96b  mov     r9d, ebx
0x18005c96e  lea     r8, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids
0x18005c975  mov     rcx, [rcx+10h]
0x18005c979  call    WPP_SF_d
0x18005c97e  jmp     loc_18005D63D
0x18005c983  xorps   xmm0, xmm0
0x18005c986  xor     eax, eax
0x18005c988  movups  [rsp+6D0h+var_670], xmm0
0x18005c98d  mov     [rsp+6D0h+var_660], rax
0x18005c992  lea     edx, [rax+11h]; unsigned int
0x18005c995  lea     rcx, [rsp+6D0h+var_670]; this
0x18005c99a  call    ??0CPrivilegeEnabler@@QEAA@K@Z; CPrivilegeEnabler::CPrivilegeEnabler(ulong)
0x18005c99f  xorps   xmm0, xmm0
0x18005c9a2  xor     eax, eax
0x18005c9a4  movups  [rsp+6D0h+var_688], xmm0
0x18005c9a9  mov     [rsp+6D0h+var_678], rax
0x18005c9ae  lea     edx, [rax+12h]; unsigned int
0x18005c9b1  lea     rcx, [rsp+6D0h+var_688]; this
0x18005c9b6  call    ??0CPrivilegeEnabler@@QEAA@K@Z; CPrivilegeEnabler::CPrivilegeEnabler(ulong)
0x18005c9bb  mov     ebx, dword ptr [rsp+6D0h+var_688+8]
0x18005c9bf  test    ebx, ebx
0x18005c9c1  jns     short loc_18005CA1B
0x18005c9c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c9ca  lea     rax, WPP_GLOBAL_Control
0x18005c9d1  cmp     rcx, rax
0x18005c9d4  jz      short loc_18005C9F4
0x18005c9d6  test    [rcx+1Ch], r15b
0x18005c9da  jz      short loc_18005C9F4
0x18005c9dc  mov     edx, 2Bh ; '+'
0x18005c9e1  mov     r9d, ebx
0x18005c9e4  lea     r8, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids
0x18005c9eb  mov     rcx, [rcx+10h]
0x18005c9ef  call    WPP_SF_d
0x18005c9f4  mov     rcx, [rsp+6D0h+var_678]
0x18005c9f9  call    cs:__imp_FwReleasePrivilege
0x18005ca00  nop     dword ptr [rax+rax+00h]
0x18005ca05  mov     rcx, [rsp+6D0h+var_660]
0x18005ca0a  call    cs:__imp_FwReleasePrivilege
0x18005ca11  nop     dword ptr [rax+rax+00h]
0x18005ca16  jmp     loc_18005D63D
0x18005ca1b  mov     ebx, dword ptr [rsp+6D0h+var_670+8]
0x18005ca1f  test    ebx, ebx
0x18005ca21  jns     short loc_18005CA43
0x18005ca23  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ca2a  lea     rax, WPP_GLOBAL_Control
0x18005ca31  cmp     rcx, rax
0x18005ca34  jz      short loc_18005C9F4
0x18005ca36  test    [rcx+1Ch], r15b
0x18005ca3a  jz      short loc_18005C9F4
0x18005ca3c  mov     edx, 2Ch ; ','
0x18005ca41  jmp     short loc_18005C9E1
0x18005ca43  xor     r8d, r8d; dwFlags
0x18005ca46  mov     rdx, rsi; lpFile
0x18005ca49  mov     rcx, [rbp+5D0h+hKey]; hKey
0x18005ca4d  call    cs:__imp_RegRestoreKeyW
0x18005ca54  nop     dword ptr [rax+rax+00h]
0x18005ca59  mov     ebx, eax
0x18005ca5b  test    eax, eax
0x18005ca5d  jle     short loc_18005CA68
0x18005ca5f  movzx   ebx, ax
0x18005ca62  or      ebx, 80070000h
0x18005ca68  test    ebx, ebx
0x18005ca6a  jns     short loc_18005CA97
0x18005ca6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ca73  lea     rax, WPP_GLOBAL_Control
0x18005ca7a  cmp     rcx, rax
0x18005ca7d  jz      loc_18005C9F4
0x18005ca83  test    [rcx+1Ch], r15b
0x18005ca87  jz      loc_18005C9F4
0x18005ca8d  mov     edx, 2Dh ; '-'
0x18005ca92  jmp     loc_18005C9E1
0x18005ca97  mov     rcx, [rsp+6D0h+var_678]
0x18005ca9c  call    cs:__imp_FwReleasePrivilege
0x18005caa3  nop     dword ptr [rax+rax+00h]
0x18005caa8  mov     rcx, [rsp+6D0h+var_660]
0x18005caad  call    cs:__imp_FwReleasePrivilege
0x18005cab4  nop     dword ptr [rax+rax+00h]
0x18005cab9  lea     r8, [rbp+5D0h+var_640]
0x18005cabd  mov     rdx, [rbp+5D0h+hKey]
0x18005cac1  lea     rcx, [rbp+5D0h+var_5F0]
0x18005cac5  call    cs:__imp_FwCreateLocalTempStore
0x18005cacc  nop     dword ptr [rax+rax+00h]
0x18005cad1  mov     ebx, eax
0x18005cad3  test    eax, eax
0x18005cad5  jns     short loc_18005CB02
0x18005cad7  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cade  lea     rax, WPP_GLOBAL_Control
0x18005cae5  cmp     rcx, rax
0x18005cae8  jz      loc_18005D63D
0x18005caee  test    [rcx+1Ch], r15b
0x18005caf2  jz      loc_18005D63D
0x18005caf8  mov     edx, 2Eh ; '.'
0x18005cafd  jmp     loc_18005C96B
0x18005cb02  mov     esi, 221h
0x18005cb07  mov     ecx, esi
0x18005cb09  lea     rax, [rbp+5D0h+var_648]
0x18005cb0d  mov     [rsp+6D0h+var_6A8], rax
0x18005cb12  mov     dword ptr [rsp+6D0h+var_6B0], 0
0x18005cb1a  mov     r9d, 2
0x18005cb20  mov     r8d, r14d
0x18005cb23  mov     rdx, rdi
0x18005cb26  call    FWOpenPolicyStore
0x18005cb2b  mov     ebx, eax
0x18005cb2d  test    eax, eax
0x18005cb2f  jle     short loc_18005CB3A
0x18005cb31  movzx   ebx, ax
0x18005cb34  or      ebx, 80070000h
0x18005cb3a  test    ebx, ebx
0x18005cb3c  jns     short loc_18005CB69
0x18005cb3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cb45  lea     rax, WPP_GLOBAL_Control
0x18005cb4c  cmp     rcx, rax
0x18005cb4f  jz      loc_18005D63D
0x18005cb55  test    [rcx+1Ch], r15b
0x18005cb59  jz      loc_18005D63D
0x18005cb5f  mov     edx, 2Fh ; '/'
0x18005cb64  jmp     loc_18005C96B
0x18005cb69  cmp     r14d, 6
0x18005cb6d  jnz     short loc_18005CBB9
0x18005cb6f  mov     edx, r15d
0x18005cb72  mov     rcx, [rbp+5D0h+var_648]
0x18005cb76  call    FWChangeTransactionalState
0x18005cb7b  mov     ebx, eax
0x18005cb7d  test    eax, eax
0x18005cb7f  jle     short loc_18005CB8A
0x18005cb81  movzx   ebx, ax
0x18005cb84  or      ebx, 80070000h
0x18005cb8a  test    ebx, ebx
0x18005cb8c  jns     short loc_18005CBB9
0x18005cb8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cb95  lea     rax, WPP_GLOBAL_Control
0x18005cb9c  cmp     rcx, rax
0x18005cb9f  jz      loc_18005D63D
0x18005cba5  test    [rcx+1Ch], r15b
0x18005cba9  jz      loc_18005D63D
0x18005cbaf  mov     edx, 30h ; '0'
0x18005cbb4  jmp     loc_18005C96B
0x18005cbb9  mov     edi, r15d
0x18005cbbc  lea     eax, [rdi-1]
0x18005cbbf  cmp     eax, r15d
0x18005cbc2  jbe     loc_18005CD68
0x18005cbc8  cmp     edi, 0Bh
0x18005cbcb  jz      loc_18005CD68
0x18005cbd1  lea     r13, [rbp+5D0h+var_450]
0x18005cbd8  mov     [rbp+5D0h+var_650], 400h
0x18005cbdf  xor     ebx, ebx
0x18005cbe1  cmp     ebx, 800700EAh
0x18005cbe7  jnz     short loc_18005CC1F
0x18005cbe9  lea     rax, [rbp+5D0h+var_450]
0x18005cbf0  cmp     r13, rax
0x18005cbf3  jz      short loc_18005CC04
0x18005cbf5  mov     rcx, r13
0x18005cbf8  call    cs:__imp_FwBaseFree
0x18005cbff  nop     dword ptr [rax+rax+00h]
0x18005cc04  mov     ecx, [rbp+5D0h+var_650]
0x18005cc07  call    cs:__imp_FwBaseAlloc
0x18005cc0e  nop     dword ptr [rax+rax+00h]
0x18005cc13  mov     r13, rax
0x18005cc16  test    rax, rax
0x18005cc19  jz      loc_18005CD85
0x18005cc1f  lea     r9, [rbp+5D0h+var_650]
0x18005cc23  mov     r8, r13
0x18005cc26  mov     edx, edi
0x18005cc28  mov     rcx, [rbp+5D0h+hKey]
0x18005cc2c  call    cs:__imp_FwGetGlobalConfigFromLocalTempStore
0x18005cc33  nop     dword ptr [rax+rax+00h]
0x18005cc38  mov     ebx, eax
0x18005cc3a  cmp     eax, 800700EAh
0x18005cc3f  jz      short loc_18005CBE1
0x18005cc41  cmp     eax, 80070002h
0x18005cc46  jz      short loc_18005CC5D
0x18005cc48  cmp     eax, 80070032h
0x18005cc4d  jz      short loc_18005CC5D
0x18005cc4f  test    eax, eax
0x18005cc51  js      loc_18005CDB5
0x18005cc57  mov     r9d, [rbp+5D0h+var_650]
0x18005cc5b  jmp     short loc_18005CC72
0x18005cc5d  cmp     edi, 0Ah
0x18005cc60  jnz     loc_18005CD0B
0x18005cc66  mov     [r13+0], esi
0x18005cc6a  lea     r9d, [rdi-6]
0x18005cc6e  mov     [rbp+5D0h+var_650], r9d
0x18005cc72  test    r9d, r9d
0x18005cc75  jnz     short loc_18005CC80
0x18005cc77  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "dwNumItems > 0", "enumerating global configs")
0x18005cc7c  mov     r9d, [rbp+5D0h+var_650]
0x18005cc80  cmp     edi, 0Ah
0x18005cc83  jnz     short loc_18005CC9B
0x18005cc85  cmp     [r13+0], esi
0x18005cc89  jbe     short loc_18005CC9B
0x18005cc8b  mov     [r12], r15d
0x18005cc8f  mov     [r13+0], esi
0x18005cc93  lea     r9d, [rdi-6]
0x18005cc97  mov     [rbp+5D0h+var_650], r9d
0x18005cc9b  mov     r8, r13
0x18005cc9e  mov     edx, edi
0x18005cca0  mov     rcx, [rbp+5D0h+var_648]
0x18005cca4  call    FWSetGlobalConfig2
0x18005cca9  mov     ebx, eax
0x18005ccab  cmp     eax, 32h ; '2'
0x18005ccae  jnz     short loc_18005CCD6
0x18005ccb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ccb7  lea     rsi, WPP_GLOBAL_Control
0x18005ccbe  cmp     rcx, rsi
0x18005ccc1  jz      loc_18005CD6F
0x18005ccc7  test    byte ptr [rcx+1Ch], 2
0x18005cccb  jz      loc_18005CD6F
0x18005ccd1  lea     edx, [rax+3]
0x18005ccd4  jmp     short loc_18005CD3E
0x18005ccd6  test    eax, eax
0x18005ccd8  jle     short loc_18005CCE3
0x18005ccda  movzx   ebx, ax
0x18005ccdd  or      ebx, 80070000h
0x18005cce3  test    ebx, ebx
0x18005cce5  js      loc_18005CDE0
0x18005cceb  lea     rax, [rbp+5D0h+var_450]
0x18005ccf2  cmp     r13, rax
0x18005ccf5  jz      short loc_18005CD68
0x18005ccf7  mov     rcx, r13
0x18005ccfa  call    cs:__imp_FwBaseFree
0x18005cd01  nop     dword ptr [rax+rax+00h]
0x18005cd06  xor     r13d, r13d
0x18005cd09  jmp     short loc_18005CD68
0x18005cd0b  xor     r9d, r9d
0x18005cd0e  xor     r8d, r8d
0x18005cd11  mov     edx, edi
0x18005cd13  mov     rcx, [rbp+5D0h+var_648]
0x18005cd17  call    FWSetGlobalConfig2
0x18005cd1c  mov     ebx, eax
0x18005cd1e  cmp     eax, 32h ; '2'
0x18005cd21  jnz     short loc_18005CD53
0x18005cd23  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cd2a  lea     rsi, WPP_GLOBAL_Control
0x18005cd31  cmp     rcx, rsi
0x18005cd34  jz      short loc_18005CD6F
  ... truncated ...
```
