# Int_FWExportPolicy(ushort const *,_tag_FW_STORE_TYPE,ushort const *,int *)

- ea: `0x180027370`
- end: `0x180027e82`
- name: `?Int_FWExportPolicy@@YAKPEBGW4_tag_FW_STORE_TYPE@@0PEAH@Z`
- size: `2834`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800509b0`

## callees

- `0x180005e0c`
- `0x1800090d0`
- `0x180009780`
- `0x18000c3f0`
- `0x18000cc80`
- `0x18000d0f0`
- `0x180010990`
- `0x180022c90`
- `0x180026c9c`
- `0x180027370`
- `0x180027e90`
- `0x180028030`
- `0x1800281f0`
- `0x180028370`
- `0x1800284e0`
- `0x1800285b0`
- `0x1800294b0`
- `0x18002a1f4`
- `0x18003336c`
- `0x180050d30`
- `0x180051100`
- `0x18005c34c`
- `0x18005c3ac`
- `0x18005c5f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSaveKeyExW` at `0x180027e33`
- `api-ms-win-core-registry-l1-1-0!RegSaveKeyExW` at `0x180027e33`
- `fwbase!FwBaseAlloc` at `0x180027ba2`
- `fwbase!FwBaseAlloc` at `0x180027ba2`
- `fwbase!FwBaseFree` at `0x180027b92`
- `fwbase!FwBaseFree` at `0x180027c76`
- `fwbase!FwBaseFree` at `0x180027dd6`
- `fwbase!FwBaseFree` at `0x180027b92`
- `fwbase!FwBaseFree` at `0x180027c76`
- `fwbase!FwBaseFree` at `0x180027dd6`
- `fwbase!FwHResultToWindowsError` at `0x180027de4`
- `fwbase!FwHResultToWindowsError` at `0x180027de4`
- `fwbase!FwReleasePrivilege` at `0x180027d68`
- `fwbase!FwReleasePrivilege` at `0x180027d68`
- `FWPolicyIOMgr!FwSetConfig` at `0x180027623`
- `FWPolicyIOMgr!FwSetConfig` at `0x180027623`
- `FWPolicyIOMgr!FwAddRule` at `0x18002773c`
- `FWPolicyIOMgr!FwAddRule` at `0x180027822`
- `FWPolicyIOMgr!FwAddRule` at `0x180027910`
- `FWPolicyIOMgr!FwAddRule` at `0x18002773c`
- `FWPolicyIOMgr!FwAddRule` at `0x180027822`
- `FWPolicyIOMgr!FwAddRule` at `0x180027910`
- `FWPolicyIOMgr!FwAddSet` at `0x1800279d8`
- `FWPolicyIOMgr!FwAddSet` at `0x180027a6c`
- `FWPolicyIOMgr!FwAddSet` at `0x1800279d8`
- `FWPolicyIOMgr!FwAddSet` at `0x180027a6c`
- `FWPolicyIOMgr!FwCreateLocalTempStore` at `0x180027487`
- `FWPolicyIOMgr!FwCreateLocalTempStore` at `0x180027487`
- `FWPolicyIOMgr!FwDestroyLocalTempStore` at `0x180027d7e`
- `FWPolicyIOMgr!FwDestroyLocalTempStore` at `0x180027d7e`
- `FWPolicyIOMgr!FwSetGlobalConfigInLocalTempStore` at `0x180027c55`
- `FWPolicyIOMgr!FwSetGlobalConfigInLocalTempStore` at `0x180027c55`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Int_FWExportPolicy(__int64 a1, unsigned int a2, const WCHAR *a3, _DWORD *a4)
{
  _BYTE *v7; // r12
  int v8; // eax
  signed int v9; // ebx
  FwPolicy2 *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  int v13; // eax
  int v14; // eax
  unsigned int v15; // r14d
  unsigned int kk; // esi
  int v17; // eax
  unsigned int v18; // eax
  int v19; // eax
  __int64 *i; // rsi
  int v21; // eax
  __int64 *j; // rsi
  signed int v23; // eax
  bool v24; // sf
  __int64 *k; // rsi
  unsigned int m; // r14d
  int v27; // eax
  __int64 *n; // rsi
  int v29; // eax
  __int64 *ii; // rsi
  unsigned int jj; // esi
  int v32; // eax
  FwPolicy2 *v33; // rcx
  __int64 v34; // rdx
  unsigned int v35; // ebx
  LSTATUS v37; // eax
  __int128 v38; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B0h]
  LPCWSTR lpFile; // [rsp+58h] [rbp-A8h]
  unsigned int v41; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v42; // [rsp+68h] [rbp-98h] BYREF
  __int64 v43; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v44; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v45; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v46; // [rsp+88h] [rbp-78h] BYREF
  __int64 *v47; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v48; // [rsp+98h] [rbp-68h] BYREF
  int v49; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v50[3]; // [rsp+A4h] [rbp-5Ch] BYREF
  void **v51; // [rsp+B0h] [rbp-50h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp-48h]
  __int128 v53; // [rsp+C0h] [rbp-40h]
  _BYTE v54[176]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v55[1024]; // [rsp+180h] [rbp+80h] BYREF

  lpFile = a3;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids);
  v43 = 0;
  v42 = 0;
  v44 = 0;
  v46 = 0;
  v45 = 0;
  v47 = 0;
  v48 = 0;
  v7 = 0;
  v41 = 0;
  v50[0] = 0;
  *a4 = 0;
  memset_0(&v51, 0, 0xD0u);
  v51 = &CTempRegKey::`vftable';
  hKey = 0;
  v53 = 0;
  v8 = CTempRegKey::Init((CTempRegKey *)&v51);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_174;
    v11 = 20;
LABEL_8:
    v12 = (unsigned int)v8;
    goto LABEL_9;
  }
  v8 = FwCreateLocalTempStore(v54, hKey, &v43);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_174;
    v11 = 21;
    goto LABEL_8;
  }
  v13 = FWOpenPolicyStore(0x221u, a1, a2, 1u, 0, &v42);
  v9 = v13;
  if ( v13 > 0 )
    v9 = (unsigned __int16)v13 | 0x80070000;
  if ( v9 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_174;
    v11 = 22;
    goto LABEL_20;
  }
  if ( a2 == 6 )
  {
    v14 = FWChangeTransactionalState(v42, 1);
    v9 = v14;
    if ( v14 > 0 )
      v9 = (unsigned __int16)v14 | 0x80070000;
    if ( v9 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_174;
      v11 = 23;
      goto LABEL_20;
    }
  }
  v15 = 0;
LABEL_29:
  if ( v15 >= 3 )
  {
    v19 = FWEnumFirewallRules(v42, 458752, 0x7FFFFFFF, 0, (__int64)&v41, (__int64)&v44);
    v9 = v19;
    if ( v19 > 0 )
      v9 = (unsigned __int16)v19 | 0x80070000;
    if ( v9 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_174;
      v11 = 26;
      goto LABEL_20;
    }
    for ( i = v44; i; i = (__int64 *)*i )
    {
      if ( (i[42] & 0x60000) != 0 )
        *a4 = 1;
      if ( (i[42] & 0x40000) == 0 )
      {
        v9 = FwAddRule(v43, 0, i);
        if ( v9 < 0 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_174;
          v11 = 27;
          goto LABEL_20;
        }
      }
    }
    FWFreeFirewallRules(v44);
    v44 = 0;
    v21 = FWEnumConnectionSecurityRules(v42, 458752, 0x7FFFFFFF, 0, (__int64)&v41, (__int64)&v46);
    v9 = v21;
    if ( v21 > 0 )
      v9 = (unsigned __int16)v21 | 0x80070000;
    if ( v9 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_174;
      v11 = 28;
      goto LABEL_20;
    }
    for ( j = v46; j; j = (__int64 *)*j )
    {
      if ( (j[48] & 0x60000) != 0 )
        *a4 = 1;
      if ( (j[48] & 0x40000) == 0 )
      {
        v9 = FwAddRule(v43, 1, j);
        if ( v9 < 0 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_174;
          v11 = 29;
          goto LABEL_20;
        }
      }
    }
    FWFreeConnectionSecurityRules(v46);
    v46 = 0;
    v23 = FWEnumMainModeRules(v42, 458752, 0x7FFFFFFF, 0, (__int64)&v41, (__int64)&v45);
    v9 = 0;
    if ( v23 != 50 )
      v9 = v23;
    v24 = v9 < 0;
    if ( v9 > 0 )
    {
      v9 = (unsigned __int16)v9 | 0x80070000;
      v24 = v9 < 0;
    }
    if ( v24 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_174;
      v11 = 30;
      goto LABEL_20;
    }
    for ( k = v45; k; k = (__int64 *)*k )
    {
      if ( (k[32] & 0x60000) != 0 )
        *a4 = 1;
      if ( (k[32] & 0x40000) == 0 )
      {
        v9 = FwAddRule(v43, 2, k);
        if ( v9 < 0 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_174;
          v11 = 31;
          goto LABEL_20;
        }
      }
    }
    FWFreeMainModeRules(v45);
    v45 = 0;
    for ( m = 1; m <= 2; ++m )
    {
      v27 = FWEnumAuthenticationSets(v42, m, 458752, 0, (__int64)&v41, (__int64)&v47);
      v9 = v27;
      if ( v27 > 0 )
        v9 = (unsigned __int16)v27 | 0x80070000;
      if ( v9 < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_174;
        v11 = 32;
        goto LABEL_20;
      }
      for ( n = v47; n; n = (__int64 *)*n )
      {
        if ( (n[10] & 0x60000) != 0 )
          *a4 = 1;
        if ( (n[10] & 0x40000) == 0 )
        {
          v9 = FwAddSet(v43, 0, m, n);
          if ( v9 < 0 )
          {
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_174;
            }
            v11 = 33;
            goto LABEL_20;
          }
        }
      }
      FWFreeAuthenticationSets(v47);
      v47 = 0;
      v29 = FWEnumCryptoSets(v42, m, 458752, 0, (__int64)&v41, (__int64)&v48);
      v9 = v29;
      if ( v29 > 0 )
        v9 = (unsigned __int16)v29 | 0x80070000;
      if ( v9 < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_174;
        v11 = 34;
        goto LABEL_20;
      }
      for ( ii = v48; ii; ii = (__int64 *)*ii )
      {
        if ( (ii[11] & 0x60000) != 0 )
          *a4 = 1;
        if ( (ii[11] & 0x40000) == 0 )
        {
          v9 = FwAddSet(v43, 1, m, ii);
          if ( v9 < 0 )
          {
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_174;
            }
            v11 = 35;
            goto LABEL_20;
          }
        }
      }
      FWFreeCryptoSets(v48);
      v48 = 0;
    }
    for ( jj = 1; jj < 0x13; ++jj )
    {
      if ( jj - 1 <= 1 || jj == 11 )
        continue;
      v7 = v55;
      v41 = 1024;
      v9 = 0;
      do
      {
        if ( v9 == 234 )
        {
          if ( v7 != v55 )
            FwBaseFree(v7);
          v7 = (_BYTE *)FwBaseAlloc(v41);
          if ( !v7 )
          {
            v9 = -2147024882;
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_174;
            }
            v11 = 36;
            goto LABEL_20;
          }
        }
        v32 = FWGetGlobalConfig3(v42, jj, 0, (_DWORD)v7, (__int64)&v41, (__int64)v50);
        v9 = v32;
      }
      while ( v32 == 234 );
      if ( v32 != 2 && v32 != 50 )
      {
        if ( v32 > 0 )
          v9 = (unsigned __int16)v32 | 0x80070000;
LABEL_149:
        if ( v9 < 0 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_174;
          v11 = 37;
        }
        else
        {
          if ( !v41 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          if ( jj == 10 && *(_DWORD *)v7 > 0x221u )
          {
            *a4 = 1;
            *(_DWORD *)v7 = 545;
            v41 = 4;
          }
          v9 = FwSetGlobalConfigInLocalTempStore(hKey, jj, v7, v41);
          if ( v9 >= 0 )
          {
            if ( v7 != v55 )
            {
              FwBaseFree(v7);
              v7 = 0;
            }
            continue;
          }
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_174;
          v11 = 38;
        }
LABEL_20:
        v12 = (unsigned int)v9;
LABEL_9:
        WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids, v12);
        goto LABEL_174;
      }
      if ( jj == 10 )
      {
        *(_DWORD *)v7 = 545;
        v41 = 4;
        v9 = 0;
        goto LABEL_149;
      }
    }
    v38 = 0;
    v39 = 0;
    CPrivilegeEnabler::CPrivilegeEnabler((CPrivilegeEnabler *)&v38, 0x11u);
    v9 = DWORD2(v38);
    if ( (SDWORD2(v38) & 0x80000000) == 0 )
    {
      v37 = RegSaveKeyExW(hKey, lpFile, 0, 2u);
      v9 = v37;
      if ( v37 > 0 )
        v9 = (unsigned __int16)v37 | 0x80070000;
      if ( v9 >= 0 )
        goto LABEL_173;
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_173;
      v34 = 40;
    }
    else
    {
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_173;
      v34 = 39;
    }
    WPP_SF_d(*((_QWORD *)v33 + 2), v34, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids, (unsigned int)v9);
LABEL_173:
    FwReleasePrivilege(v39);
    goto LABEL_174;
  }
  for ( kk = 1; ; ++kk )
  {
    if ( kk >= 0x13 )
    {
      ++v15;
      goto LABEL_29;
    }
    v41 = 1024;
    v49 = 0;
    v17 = FWGetConfig2(v42, kk, *((_DWORD *)qword_18008E2D0 + v15), 0, (__int64)v55, (__int64)&v41, (__int64)&v49);
    v9 = v17;
    if ( v17 == 2 || v17 == 50 )
      continue;
    if ( v17 > 0 )
      v9 = (unsigned __int16)v17 | 0x80070000;
    if ( v9 < 0 )
      break;
    v18 = v41;
    if ( !v41 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v18 = v41;
    }
    v9 = FwSetConfig(v43, kk, *((unsigned int *)qword_18008E2D0 + v15), v55, v18);
    if ( v9 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 25;
        goto LABEL_20;
      }
      goto LABEL_174;
    }
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = 24;
    goto LABEL_20;
  }
LABEL_174:
  if ( v43 )
    FwDestroyLocalTempStore();
  if ( v42 )
    FWClosePolicyStore();
  FWFreeFirewallRules(v44);
  FWFreeMainModeRules(v45);
  FWFreeConnectionSecurityRules(v46);
  FWFreeAuthenticationSets(v47);
  FWFreeCryptoSets(v48);
  if ( v7 != v55 )
    FwBaseFree(v7);
  v35 = FwHResultToWindowsError((unsigned int)v9);
  CTempRegKey::~CTempRegKey((CTempRegKey *)&v51);
  return v35;
}

```

## disassembly

```asm
0x180027370  push    rbp
0x180027372  push    rbx
0x180027373  push    rsi
0x180027374  push    rdi
0x180027375  push    r12
0x180027377  push    r13
0x180027379  push    r14
0x18002737b  push    r15
0x18002737d  lea     rbp, [rsp-498h]
0x180027385  sub     rsp, 598h
0x18002738c  mov     rax, cs:__security_cookie
0x180027393  xor     rax, rsp
0x180027396  mov     [rbp+4D0h+var_50], rax
0x18002739d  mov     r13, r9
0x1800273a0  mov     [rsp+5D0h+lpFile], r8
0x1800273a5  mov     esi, edx
0x1800273a7  mov     r14, rcx
0x1800273aa  lea     rdi, WPP_GLOBAL_Control
0x1800273b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800273b8  cmp     rcx, rdi
0x1800273bb  jz      short loc_1800273D8
0x1800273bd  test    byte ptr [rcx+1Ch], 8
0x1800273c1  jz      short loc_1800273D8
0x1800273c3  mov     edx, 13h
0x1800273c8  lea     r8, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids
0x1800273cf  mov     rcx, [rcx+10h]
0x1800273d3  call    WPP_SF_
0x1800273d8  xor     r15d, r15d
0x1800273db  mov     [rsp+5D0h+var_560], r15
0x1800273e0  mov     [rsp+5D0h+var_568], r15
0x1800273e5  mov     [rsp+5D0h+var_558], r15
0x1800273ea  mov     [rbp+4D0h+var_548], r15
0x1800273ee  mov     [rbp+4D0h+var_550], r15
0x1800273f2  mov     [rbp+4D0h+var_540], r15
0x1800273f6  mov     [rbp+4D0h+var_538], r15
0x1800273fa  mov     r12d, r15d
0x1800273fd  mov     [rsp+5D0h+var_570], r15d
0x180027402  mov     [rbp+4D0h+var_52C], r15d
0x180027406  mov     [r13+0], r15d
0x18002740a  xor     edx, edx; Val
0x18002740c  mov     r8d, 0D0h; Size
0x180027412  lea     rcx, [rbp+4D0h+var_520]; void *
0x180027416  call    memset_0
0x18002741b  lea     rax, ??_7CTempRegKey@@6B@; const CTempRegKey::`vftable'
0x180027422  mov     [rbp+4D0h+var_520], rax
0x180027426  mov     [rbp+4D0h+hKey], r15
0x18002742a  xorps   xmm0, xmm0
0x18002742d  movdqa  [rbp+4D0h+var_510], xmm0
0x180027432  lea     rcx, [rbp+4D0h+var_520]; this
0x180027436  call    ?Init@CTempRegKey@@QEAAJXZ; CTempRegKey::Init(void)
0x18002743b  mov     ebx, eax
0x18002743d  test    eax, eax
0x18002743f  jns     short loc_18002747A
0x180027441  mov     rcx, cs:WPP_GLOBAL_Control
0x180027448  cmp     rcx, rdi
0x18002744b  jz      loc_180027D74
0x180027451  lea     edi, [r15+1]
0x180027455  test    [rcx+1Ch], dil
0x180027459  jz      loc_180027D74
0x18002745f  lea     edx, [rdi+13h]
0x180027462  mov     r9d, eax
0x180027465  lea     r8, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids
0x18002746c  mov     rcx, [rcx+10h]
0x180027470  call    WPP_SF_d
0x180027475  jmp     loc_180027D74
0x18002747a  lea     r8, [rsp+5D0h+var_560]
0x18002747f  mov     rdx, [rbp+4D0h+hKey]
0x180027483  lea     rcx, [rbp+4D0h+var_500]
0x180027487  call    cs:__imp_FwCreateLocalTempStore
0x18002748e  nop     dword ptr [rax+rax+00h]
0x180027493  mov     ebx, eax
0x180027495  test    eax, eax
0x180027497  jns     short loc_1800274BD
0x180027499  mov     rcx, cs:WPP_GLOBAL_Control
0x1800274a0  cmp     rcx, rdi
0x1800274a3  jz      loc_180027D74
0x1800274a9  mov     edi, 1
0x1800274ae  test    [rcx+1Ch], dil
0x1800274b2  jz      loc_180027D74
0x1800274b8  lea     edx, [rdi+14h]
0x1800274bb  jmp     short loc_180027462
0x1800274bd  mov     ecx, 221h
0x1800274c2  lea     rax, [rsp+5D0h+var_568]
0x1800274c7  mov     [rsp+5D0h+var_5A8], rax
0x1800274cc  mov     dword ptr [rsp+5D0h+var_5B0], r15d
0x1800274d1  mov     edi, 1
0x1800274d6  mov     r9d, edi
0x1800274d9  mov     r8d, esi
0x1800274dc  mov     rdx, r14
0x1800274df  call    FWOpenPolicyStore
0x1800274e4  mov     ebx, eax
0x1800274e6  mov     r14d, 80070000h
0x1800274ec  test    eax, eax
0x1800274ee  jle     short loc_1800274F6
0x1800274f0  movzx   ebx, ax
0x1800274f3  or      ebx, r14d
0x1800274f6  test    ebx, ebx
0x1800274f8  jns     short loc_180027528
0x1800274fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180027501  lea     rax, WPP_GLOBAL_Control
0x180027508  cmp     rcx, rax
0x18002750b  jz      loc_180027D74
0x180027511  test    [rcx+1Ch], dil
0x180027515  jz      loc_180027D74
0x18002751b  mov     edx, 16h
0x180027520  mov     r9d, ebx
0x180027523  jmp     loc_180027465
0x180027528  cmp     esi, 6
0x18002752b  jnz     short loc_180027571
0x18002752d  mov     edx, edi
0x18002752f  mov     rcx, [rsp+5D0h+var_568]
0x180027534  call    FWChangeTransactionalState
0x180027539  mov     ebx, eax
0x18002753b  test    eax, eax
0x18002753d  jle     short loc_180027545
0x18002753f  movzx   ebx, ax
0x180027542  or      ebx, r14d
0x180027545  test    ebx, ebx
0x180027547  jns     short loc_180027571
0x180027549  mov     rcx, cs:WPP_GLOBAL_Control
0x180027550  lea     rax, WPP_GLOBAL_Control
0x180027557  cmp     rcx, rax
0x18002755a  jz      loc_180027D74
0x180027560  test    [rcx+1Ch], dil
0x180027564  jz      loc_180027D74
0x18002756a  mov     edx, 17h
0x18002756f  jmp     short loc_180027520
0x180027571  mov     r14d, r15d
0x180027574  cmp     r14d, 3
0x180027578  jnb     loc_18002769F
0x18002757e  mov     esi, edi
0x180027580  cmp     esi, 13h
0x180027583  jnb     loc_18002766C
0x180027589  mov     [rsp+5D0h+var_570], 400h
0x180027591  mov     r15d, r14d
0x180027594  lea     rcx, qword_18008E2D0
0x18002759b  mov     [rbp+4D0h+var_530], 0
0x1800275a2  lea     rax, [rbp+4D0h+var_530]
0x1800275a6  mov     [rsp+5D0h+var_5A0], rax
0x1800275ab  lea     rax, [rsp+5D0h+var_570]
0x1800275b0  mov     [rsp+5D0h+var_5A8], rax
0x1800275b5  lea     rax, [rbp+4D0h+var_450]
0x1800275bc  mov     [rsp+5D0h+var_5B0], rax
0x1800275c1  xor     r9d, r9d
0x1800275c4  mov     r8d, [rcx+r15*4]
0x1800275c8  mov     edx, esi
0x1800275ca  mov     rcx, [rsp+5D0h+var_568]
0x1800275cf  call    FWGetConfig2
0x1800275d4  mov     ebx, eax
0x1800275d6  cmp     eax, 2
0x1800275d9  jz      loc_180027662
0x1800275df  cmp     eax, 32h ; '2'
0x1800275e2  jz      short loc_180027662
0x1800275e4  test    eax, eax
0x1800275e6  jle     short loc_1800275F1
0x1800275e8  movzx   ebx, ax
0x1800275eb  or      ebx, 80070000h
0x1800275f1  test    ebx, ebx
0x1800275f3  js      short loc_180027674
0x1800275f5  mov     eax, [rsp+5D0h+var_570]
0x1800275f9  test    eax, eax
0x1800275fb  jnz     short loc_180027606
0x1800275fd  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "dwNumItems > 0", "enumerating global profiles")
0x180027602  mov     eax, [rsp+5D0h+var_570]
0x180027606  mov     dword ptr [rsp+5D0h+var_5B0], eax
0x18002760a  lea     r9, [rbp+4D0h+var_450]
0x180027611  lea     r8, qword_18008E2D0
0x180027618  mov     r8d, [r8+r15*4]
0x18002761c  mov     edx, esi
0x18002761e  mov     rcx, [rsp+5D0h+var_560]
0x180027623  call    cs:__imp_FwSetConfig
0x18002762a  nop     dword ptr [rax+rax+00h]
0x18002762f  mov     ebx, eax
0x180027631  xor     r15d, r15d
0x180027634  test    eax, eax
0x180027636  jns     short loc_180027665
0x180027638  mov     rcx, cs:WPP_GLOBAL_Control
0x18002763f  lea     rax, WPP_GLOBAL_Control
0x180027646  cmp     rcx, rax
0x180027649  jz      loc_180027D74
0x18002764f  test    [rcx+1Ch], dil
0x180027653  jz      loc_180027D74
0x180027659  lea     edx, [r15+19h]
0x18002765d  jmp     loc_180027520
0x180027662  xor     r15d, r15d
0x180027665  add     esi, edi
0x180027667  jmp     loc_180027580
0x18002766c  add     r14d, edi
0x18002766f  jmp     loc_180027574
0x180027674  mov     rcx, cs:WPP_GLOBAL_Control
0x18002767b  lea     rax, WPP_GLOBAL_Control
0x180027682  cmp     rcx, rax
0x180027685  jz      loc_180027D74
0x18002768b  test    [rcx+1Ch], dil
0x18002768f  jz      loc_180027D74
0x180027695  mov     edx, 18h
0x18002769a  jmp     loc_180027520
0x18002769f  xor     r9d, r9d
0x1800276a2  lea     rax, [rsp+5D0h+var_558]
0x1800276a7  mov     [rsp+5D0h+var_5A8], rax
0x1800276ac  lea     rax, [rsp+5D0h+var_570]
0x1800276b1  mov     [rsp+5D0h+var_5B0], rax
0x1800276b6  mov     r14d, 7FFFFFFFh
0x1800276bc  mov     r8d, r14d
0x1800276bf  mov     edx, 70000h
0x1800276c4  mov     rcx, [rsp+5D0h+var_568]
0x1800276c9  call    FWEnumFirewallRules
0x1800276ce  mov     ebx, eax
0x1800276d0  test    eax, eax
0x1800276d2  jle     short loc_1800276DD
0x1800276d4  movzx   ebx, ax
0x1800276d7  or      ebx, 80070000h
0x1800276dd  test    ebx, ebx
0x1800276df  jns     short loc_18002770C
0x1800276e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800276e8  lea     rax, WPP_GLOBAL_Control
0x1800276ef  cmp     rcx, rax
0x1800276f2  jz      loc_180027D74
0x1800276f8  test    [rcx+1Ch], dil
0x1800276fc  jz      loc_180027D74
0x180027702  mov     edx, 1Ah
0x180027707  jmp     loc_180027520
0x18002770c  mov     rsi, [rsp+5D0h+var_558]
0x180027711  test    rsi, rsi
0x180027714  jz      short loc_18002777E
0x180027716  test    dword ptr [rsi+150h], 60000h
0x180027720  jz      short loc_180027726
0x180027722  mov     [r13+0], edi
0x180027726  test    dword ptr [rsi+150h], 40000h
0x180027730  jnz     short loc_18002774E
0x180027732  mov     r8, rsi
0x180027735  xor     edx, edx
0x180027737  mov     rcx, [rsp+5D0h+var_560]
0x18002773c  call    cs:__imp_FwAddRule
0x180027743  nop     dword ptr [rax+rax+00h]
0x180027748  mov     ebx, eax
0x18002774a  test    eax, eax
0x18002774c  js      short loc_180027753
0x18002774e  mov     rsi, [rsi]
0x180027751  jmp     short loc_180027711
0x180027753  mov     rcx, cs:WPP_GLOBAL_Control
0x18002775a  lea     rax, WPP_GLOBAL_Control
0x180027761  cmp     rcx, rax
0x180027764  jz      loc_180027D74
0x18002776a  test    [rcx+1Ch], dil
0x18002776e  jz      loc_180027D74
0x180027774  mov     edx, 1Bh
0x180027779  jmp     loc_180027520
0x18002777e  mov     rcx, [rsp+5D0h+var_558]
0x180027783  call    FWFreeFirewallRules
0x180027788  mov     [rsp+5D0h+var_558], r15
0x18002778d  xor     r9d, r9d
0x180027790  lea     rax, [rbp+4D0h+var_548]
0x180027794  mov     [rsp+5D0h+var_5A8], rax
0x180027799  lea     rax, [rsp+5D0h+var_570]
0x18002779e  mov     [rsp+5D0h+var_5B0], rax
0x1800277a3  mov     r8d, r14d
0x1800277a6  mov     edx, 70000h
0x1800277ab  mov     rcx, [rsp+5D0h+var_568]
0x1800277b0  call    FWEnumConnectionSecurityRules
0x1800277b5  mov     ebx, eax
0x1800277b7  test    eax, eax
0x1800277b9  jle     short loc_1800277C4
0x1800277bb  movzx   ebx, ax
0x1800277be  or      ebx, 80070000h
0x1800277c4  test    ebx, ebx
0x1800277c6  jns     short loc_1800277F3
0x1800277c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800277cf  lea     rax, WPP_GLOBAL_Control
0x1800277d6  cmp     rcx, rax
0x1800277d9  jz      loc_180027D74
0x1800277df  test    [rcx+1Ch], dil
0x1800277e3  jz      loc_180027D74
0x1800277e9  mov     edx, 1Ch
0x1800277ee  jmp     loc_180027520
0x1800277f3  mov     rsi, [rbp+4D0h+var_548]
0x1800277f7  test    rsi, rsi
0x1800277fa  jz      short loc_180027864
0x1800277fc  test    dword ptr [rsi+180h], 60000h
0x180027806  jz      short loc_18002780C
0x180027808  mov     [r13+0], edi
0x18002780c  test    dword ptr [rsi+180h], 40000h
0x180027816  jnz     short loc_180027834
0x180027818  mov     r8, rsi
0x18002781b  mov     edx, edi
0x18002781d  mov     rcx, [rsp+5D0h+var_560]
0x180027822  call    cs:__imp_FwAddRule
0x180027829  nop     dword ptr [rax+rax+00h]
0x18002782e  mov     ebx, eax
0x180027830  test    eax, eax
0x180027832  js      short loc_180027839
0x180027834  mov     rsi, [rsi]
0x180027837  jmp     short loc_1800277F7
0x180027839  mov     rcx, cs:WPP_GLOBAL_Control
0x180027840  lea     rax, WPP_GLOBAL_Control
0x180027847  cmp     rcx, rax
0x18002784a  jz      loc_180027D74
0x180027850  test    [rcx+1Ch], dil
0x180027854  jz      loc_180027D74
0x18002785a  mov     edx, 1Dh
  ... truncated ...
```
