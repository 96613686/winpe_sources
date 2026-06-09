# EapPeapBegin

- ea: `0x18005c4f0`
- end: `0x18005ce84`
- name: `EapPeapBegin`
- size: `2452`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180004688`
- `0x180005010`
- `0x180006620`
- `0x180007d00`
- `0x18001fa30`
- `0x180020040`
- `0x1800206a0`
- `0x180020d80`
- `0x1800239a0`
- `0x180024528`
- `0x180034e48`
- `0x180034f2c`
- `0x180038270`
- `0x180038e64`
- `0x18005bc24`
- `0x18005c4f0`
- `0x18005de34`
- `0x180075400`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18005c795`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18005c90b`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18005cb40`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18005cdcf`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18005c795`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18005c90b`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18005cb40`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18005cdcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c8a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cafa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cd1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c8a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cafa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cd1b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c5dc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c800`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c88f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c5dc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c800`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c88f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005cd57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ce16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ce2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005cd57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ce16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ce2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c9ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c9ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005c979`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005c979`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005ccfb`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005ccfb`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005cad2`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005cad2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005c684`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005c684`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005c699`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005c699`

## pseudocode

```c
__int64 __fastcall EapPeapBegin(_QWORD *a1, __int128 *a2)
{
  _QWORD *v3; // r15
  unsigned __int16 *v4; // r12
  __int64 v5; // rcx
  __int128 *v6; // rax
  unsigned int v7; // edi
  struct _EAPTLS_CONTROL_BLOCK *v8; // rcx
  __int64 v9; // rdx
  char *v10; // rbx
  int v11; // ecx
  const WCHAR *v12; // r13
  __int64 v13; // r8
  struct _PEAP_EAP_INFO *v14; // rdx
  const unsigned __int16 *v15; // rcx
  struct _PEAP_CONN_PROPERTIES **v16; // r14
  _DWORD *v17; // rax
  _DWORD *v18; // rdi
  DWORD LastError; // eax
  struct _EAPTLS_CONTROL_BLOCK *v20; // rcx
  __int64 v21; // rdx
  unsigned int v22; // eax
  _DWORD *v23; // rax
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  int v33; // eax
  unsigned int v34; // edx
  __int64 v35; // rax
  __int64 v36; // xmm1_8
  void *v37; // rcx
  DWORD v38; // eax
  __int64 v39; // r8
  __int64 v40; // r8
  unsigned int ConnectionData; // eax
  struct _EAPTLS_CONTROL_BLOCK *v42; // rcx
  __int64 v43; // rdx
  unsigned int Identity; // eax
  DWORD v45; // eax
  __int64 v46; // r9
  void *v47; // r8
  struct _PEAP_INPLACE_INFO *v49; // [rsp+70h] [rbp-90h]
  DWORD cbData[2]; // [rsp+80h] [rbp-80h] BYREF
  BYTE Data[8]; // [rsp+88h] [rbp-78h] BYREF
  DWORD Type; // [rsp+90h] [rbp-70h] BYREF
  HKEY hKey; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v54; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v55; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v56; // [rsp+C0h] [rbp-40h]
  __int128 v57; // [rsp+D0h] [rbp-30h]
  __int128 v58; // [rsp+E0h] [rbp-20h]
  __int128 v59; // [rsp+F0h] [rbp-10h]
  HLOCAL hMem[2]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v61; // [rsp+110h] [rbp+10h]
  __int128 v62; // [rsp+120h] [rbp+20h]
  __int128 v63; // [rsp+130h] [rbp+30h]
  __int64 v64; // [rsp+140h] [rbp+40h]
  _BYTE v65[4]; // [rsp+150h] [rbp+50h] BYREF
  int v66; // [rsp+154h] [rbp+54h]
  int v67; // [rsp+158h] [rbp+58h]
  __int128 v68; // [rsp+160h] [rbp+60h]
  __int64 v69; // [rsp+170h] [rbp+70h]

  *(_QWORD *)cbData = a1;
  v3 = a1;
  memset_0(&v55, 0, 0x98u);
  memset_0(v65, 0, 0x48u);
  *(_QWORD *)Data = 0;
  v4 = 0;
  v54 = 0;
  hKey = 0;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 341, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
  v5 = 152;
  v6 = &v55;
  do
  {
    *(_BYTE *)v6 = 0;
    v6 = (__int128 *)((char *)v6 + 1);
    --v5;
  }
  while ( v5 );
  if ( !v3 || !a2 )
  {
    v7 = 87;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_130;
    v9 = 342;
    goto LABEL_129;
  }
  v7 = VerifyCallerTrust(0);
  if ( v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_130;
    v9 = 343;
LABEL_129:
    WPP_SF_(*((_QWORD *)v8 + 2), v9, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
    goto LABEL_130;
  }
  v10 = (char *)LocalAlloc(0x40u, 0xB88u);
  if ( !v10 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 344, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
    v7 = 14;
    goto LABEL_130;
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      345,
      &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids,
      *((unsigned int *)a2 + 36));
  *((_DWORD *)v10 + 734) = *((_DWORD *)a2 + 36);
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      346,
      &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids,
      *((unsigned int *)a2 + 1));
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Eaphost_TVS_Fixes>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Eaphost_TVS_Fixes>::GetImpl'::`2'::impl) )
    *((_QWORD *)v10 + 364) = GetTickCount64();
  else
    *((_DWORD *)v10 + 727) = GetTickCount();
  v11 = *((_DWORD *)v10 + 1);
  *(_DWORD *)v10 = 0;
  if ( *((_DWORD *)a2 + 2) )
  {
    v11 |= 1u;
    *((_DWORD *)v10 + 1) = v11;
  }
  if ( (*((_BYTE *)a2 + 4) & 1) != 0 )
  {
    v11 |= 2u;
    *((_DWORD *)v10 + 1) = v11;
  }
  if ( (*((_BYTE *)a2 + 4) & 2) != 0 )
  {
    v11 |= 4u;
    *((_DWORD *)v10 + 1) = v11;
  }
  if ( (*((_BYTE *)a2 + 4) & 4) != 0 )
  {
    v11 |= 8u;
    *((_DWORD *)v10 + 1) = v11;
  }
  if ( (*((_BYTE *)a2 + 4) & 8) != 0 )
  {
    v11 |= 0x10u;
    *((_DWORD *)v10 + 1) = v11;
  }
  if ( (*((_BYTE *)a2 + 4) & 0x10) != 0 )
  {
    v11 |= 0x20u;
    *((_DWORD *)v10 + 1) = v11;
  }
  if ( (*((_BYTE *)a2 + 4) & 0x20) != 0 )
  {
    v11 |= 0x40u;
    *((_DWORD *)v10 + 1) = v11;
  }
  if ( (*((_BYTE *)a2 + 4) & 0x40) != 0 )
  {
    v11 |= 0x80u;
    *((_DWORD *)v10 + 1) = v11;
  }
  if ( *((char *)a2 + 4) < 0 )
  {
    v11 |= 0x100u;
    *((_DWORD *)v10 + 1) = v11;
  }
  if ( (*((_DWORD *)a2 + 1) & 0x100000) != 0 )
  {
    v11 |= 0x100000u;
    *((_DWORD *)v10 + 1) = v11;
  }
  if ( (*((_DWORD *)a2 + 1) & 0x400) != 0 )
  {
    v11 |= 0x800u;
    *((_DWORD *)v10 + 1) = v11;
  }
  if ( (*((_DWORD *)a2 + 1) & 0x800) != 0 )
  {
    v11 |= 0x4000u;
    *((_DWORD *)v10 + 1) = v11;
  }
  if ( (*((_DWORD *)a2 + 1) & 0x200000) != 0 )
  {
    v11 |= 0x40000u;
    *((_DWORD *)v10 + 1) = v11;
  }
  *((_DWORD *)v10 + 725) = 0;
  v12 = &String;
  *((_QWORD *)v10 + 1) = *((_QWORD *)a2 + 7);
  if ( (v11 & 1) == 0 )
  {
    if ( (*((_DWORD *)a2 + 1) & 0x100000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 347, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
      v17 = LocalAlloc(0x40u, 0x26u);
      v18 = v17;
      if ( !v17 )
      {
        LastError = GetLastError();
        v7 = LastError;
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_130;
        v21 = 348;
        goto LABEL_58;
      }
      v17[3] |= 2u;
      *v17 = 1;
      v17[1] = 36;
      v17[4] = 1;
      v17[5] = 20;
      v22 = v17[6] & 0xFFFFFFED;
      v18[2] = 0;
      v18[6] = v22 | 0xA5;
      v23 = LocalAlloc(0x40u, 0x28u);
      if ( !v23 )
      {
        LastError = GetLastError();
        v7 = LastError;
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_130;
        v21 = 349;
LABEL_58:
        WPP_SF_d(*((_QWORD *)v20 + 2), v21, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, LastError);
        goto LABEL_130;
      }
      v23[9] = 0;
      v16 = (struct _PEAP_CONN_PROPERTIES **)(v10 + 2608);
      *v23 = 2;
      v23[1] = 40;
      *((_QWORD *)v10 + 326) = v18;
      *((_QWORD *)v10 + 343) = v23;
      if ( *((_QWORD *)a2 + 3) )
        _o_wcsncpy_s(v10 + 2070, 257, &String, 256);
LABEL_64:
      LOBYTE(v15) = (*((_BYTE *)*v16 + 12) & 1) != 0;
      if ( ((unsigned __int8)v15 & ((*((_DWORD *)a2 + 1) & 0x1000) == 0)) != 0 )
        *((_DWORD *)v10 + 1) |= 0x400u;
      *((_DWORD *)v10 + 1) |= 0x80000u;
LABEL_67:
      if ( !(unsigned int)OpenPeapRegistryKey(v15, (__int64)v14, &hKey) )
      {
        Type = 0;
        *(_DWORD *)Data = 0;
        cbData[0] = 4;
        if ( !RegQueryValueExW(hKey, L"IdentityEncodingFormat", 0, &Type, Data, cbData)
          && Type == 4
          && cbData[0] == 4
          && *(_DWORD *)Data )
        {
          *((_DWORD *)v10 + 1) |= 0x10000u;
        }
        ReadCapabilitiesNegotiationKey(hKey);
        RegCloseKey(hKey);
      }
      *(_OWORD *)(v10 + 2920) = a2[8];
      v24 = *a2;
      v64 = *((_QWORD *)a2 + 18);
      v25 = a2[1];
      v55 = v24;
      v26 = a2[2];
      v56 = v25;
      v27 = a2[3];
      v57 = v26;
      v28 = a2[4];
      v58 = v27;
      v29 = a2[5];
      v59 = v28;
      v30 = a2[6];
      *(_OWORD *)hMem = v29;
      v31 = a2[7];
      v61 = v30;
      v32 = a2[8];
      v62 = v31;
      v63 = v32;
      if ( (v10[4] & 1) != 0 )
      {
        hMem[1] = 0;
        LODWORD(v61) = 0;
      }
      v33 = *((_DWORD *)a2 + 1) | 0x4000;
      LODWORD(v55) = 152;
      DWORD1(v55) = v33;
      if ( *v16 )
      {
        ConnPropGetV0Struct(
          (struct _PEAP_CONN_PROPERTIES *)((char *)*v16 + 16),
          (struct _EAPTLS_CONN_PROPERTIES **)&hMem[1]);
        LODWORD(v61) = *((_DWORD *)hMem[1] + 1);
      }
      memset_0(v65, 0, 0x48u);
      v66 = 1;
      v67 = 72;
      v35 = *((_QWORD *)v10 + 343);
      v68 = *(_OWORD *)(v35 + 12);
      v36 = *(_QWORD *)(v35 + 28);
      *((_QWORD *)&v61 + 1) = v65;
      v69 = v36;
      LODWORD(v62) = 72;
      if ( *v16 && (v10[4] & 1) == 0 && (*((_BYTE *)*v16 + 12) & 0x10) != 0 )
      {
        v37 = (void *)*((_QWORD *)v10 + 1);
        *(_QWORD *)cbData = 0;
        *(_DWORD *)Data = 0;
        if ( v37 && !ImpersonateLoggedOnUser(v37) )
        {
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          {
            v38 = GetLastError();
            WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 354, v39, *((_QWORD *)v10 + 1), v38);
          }
          goto LABEL_113;
        }
        Identity = PeapGetIdentity(
                     *((_DWORD *)a2 + 1) | 2,
                     v34,
                     0,
                     0,
                     *((_DWORD *)a2 + 1) | 2,
                     0,
                     0,
                     *((unsigned __int8 **)a2 + 11),
                     *((_DWORD *)a2 + 24),
                     *((unsigned __int8 **)a2 + 13),
                     *((_DWORD *)a2 + 28),
                     (unsigned __int8 **)cbData,
                     (unsigned int *)Data,
                     &v54,
                     v49);
        v7 = Identity;
        if ( Identity )
        {
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              355,
              &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids,
              Identity);
          v4 = v54;
          goto LABEL_130;
        }
        if ( *((_QWORD *)v10 + 1)
          && !RevertToSelf()
          && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          v45 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 356, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v45);
        }
        v4 = v54;
        *(_QWORD *)&v56 = v54;
        if ( *(_QWORD *)cbData )
          LocalFree(*(HLOCAL *)cbData);
      }
LABEL_113:
      v7 = EapTlsBegin((_QWORD *)v10 + 352, (__int64)&v55);
      if ( (*((_DWORD *)a2 + 1) & 0x100000) == 0 )
      {
        if ( *v16 && (v10[4] & 1) == 0 && (*((_BYTE *)*v16 + 12) & 0x10) != 0 && v4 && *v4 )
        {
          v46 = -1;
          do
            ++v46;
          while ( v4[v46] );
          v47 = v4;
          goto LABEL_125;
        }
        if ( *((_QWORD *)a2 + 2) )
          v12 = (const WCHAR *)*((_QWORD *)a2 + 2);
      }
      v46 = 512;
      v47 = (void *)v12;
LABEL_125:
      _o_wcsncpy_s(v10 + 18, 513, v47, v46);
      *v3 = v10;
      goto LABEL_130;
    }
    v40 = *((_QWORD *)a2 + 3);
    if ( v40 )
      _o_wcsncpy_s(v10 + 2070, 257, v40, 256);
    v16 = (struct _PEAP_CONN_PROPERTIES **)(v10 + 2608);
    ConnectionData = PeapReadConnectionData(
                       *((_DWORD *)a2 + 1),
                       *((unsigned __int8 **)a2 + 11),
                       *((_DWORD *)a2 + 24),
                       (struct _PEAP_CONN_PROPERTIES **)v10 + 326);
    v7 = ConnectionData;
    if ( ConnectionData )
    {
      v42 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_130;
      v43 = 350;
    }
    else
    {
      ConnectionData = PeapReadUserData(
                         0,
                         *((unsigned __int8 **)a2 + 13),
                         *((_DWORD *)a2 + 28),
                         (struct _PEAP_USER_PROPERTIES **)v10 + 343);
      v7 = ConnectionData;
      if ( ConnectionData )
      {
        v42 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_130;
        v43 = 351;
      }
      else
      {
        ConnectionData = PeapGetFirstEntryConnProp(*v16, (struct _PEAP_ENTRY_CONN_PROPERTIES **)Data);
        v7 = ConnectionData;
        if ( !ConnectionData )
        {
          v15 = *(const unsigned __int16 **)Data;
          if ( *(_QWORD *)Data )
          {
            v7 = PeapEapInfoCopyListNode(*(_DWORD *)(*(_QWORD *)Data + 8LL), v14, (struct _PEAP_EAP_INFO **)v10 + 353);
            if ( v7 || !*((_QWORD *)v10 + 353) )
            {
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                goto LABEL_130;
              v9 = 353;
              goto LABEL_129;
            }
            v3 = *(_QWORD **)cbData;
          }
          goto LABEL_64;
        }
        v42 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_130;
        v43 = 352;
      }
    }
    WPP_SF_d(*((_QWORD *)v42 + 2), v43, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, ConnectionData);
    goto LABEL_130;
  }
  v13 = *((_QWORD *)a2 + 3);
  if ( v13 )
    _o_wcsncpy_s(v10 + 2070, 257, v13, 256);
  v7 = PeapConfigureServer((struct _PEAP_CONTROL_BLOCK *)v10, *((unsigned __int8 **)a2 + 11), *((_DWORD *)a2 + 24));
  if ( !v7 )
  {
    v16 = (struct _PEAP_CONN_PROPERTIES **)(v10 + 2608);
    goto LABEL_67;
  }
LABEL_130:
  if ( hMem[1] )
    LocalFree(hMem[1]);
  if ( v4 )
    LocalFree(v4);
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 357, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
  return v7;
}

```

## disassembly

```asm
0x18005c4f0  mov     [rsp-8+arg_10], rbx
0x18005c4f5  push    rbp
0x18005c4f6  push    rsi
0x18005c4f7  push    rdi
0x18005c4f8  push    r12
0x18005c4fa  push    r13
0x18005c4fc  push    r14
0x18005c4fe  push    r15
0x18005c500  lea     rbp, [rsp-0B0h]
0x18005c508  sub     rsp, 1B0h
0x18005c50f  mov     rax, cs:__security_cookie
0x18005c516  xor     rax, rsp
0x18005c519  mov     [rbp+0E0h+var_40], rax
0x18005c520  mov     rsi, rdx
0x18005c523  mov     qword ptr [rbp+0E0h+cbData], rcx
0x18005c527  mov     r15, rcx
0x18005c52a  mov     ebx, 98h
0x18005c52f  mov     r8d, ebx; Size
0x18005c532  lea     rcx, [rbp+0E0h+var_130]; void *
0x18005c536  xor     edx, edx; Val
0x18005c538  call    memset_0
0x18005c53d  xor     edx, edx; Val
0x18005c53f  lea     r8d, [rbx-50h]; Size
0x18005c543  lea     rcx, [rbp+0E0h+var_90]; void *
0x18005c547  call    memset_0
0x18005c54c  xor     r14d, r14d
0x18005c54f  mov     qword ptr [rbp+0E0h+Data], r14
0x18005c553  mov     r12d, r14d
0x18005c556  mov     [rbp+0E0h+var_140], r14
0x18005c55a  mov     [rbp+0E0h+hKey], r14
0x18005c55e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c565  lea     r13, WPP_GLOBAL_Control
0x18005c56c  cmp     rcx, r13
0x18005c56f  jz      short loc_18005C586
0x18005c571  mov     rcx, [rcx+10h]
0x18005c575  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18005c57c  mov     edx, 155h
0x18005c581  call    WPP_SF_
0x18005c586  mov     rcx, rbx
0x18005c589  lea     rax, [rbp+0E0h+var_130]
0x18005c58d  mov     [rax], r14b
0x18005c590  inc     rax
0x18005c593  sub     rcx, 1; void *
0x18005c597  jnz     short loc_18005C58D
0x18005c599  test    r15, r15
0x18005c59c  jz      loc_18005CDE7
0x18005c5a2  test    rsi, rsi
0x18005c5a5  jz      loc_18005CDE7
0x18005c5ab  call    ?VerifyCallerTrust@@YAKPEAX@Z; VerifyCallerTrust(void *)
0x18005c5b0  mov     edi, eax
0x18005c5b2  test    eax, eax
0x18005c5b4  jz      short loc_18005C5D0
0x18005c5b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c5bd  cmp     rcx, r13
0x18005c5c0  jz      loc_18005CE0D
0x18005c5c6  mov     edx, 157h
0x18005c5cb  jmp     loc_18005CDFD
0x18005c5d0  mov     edi, 40h ; '@'
0x18005c5d5  mov     edx, 0B88h; uBytes
0x18005c5da  mov     ecx, edi; uFlags
0x18005c5dc  call    cs:__imp_LocalAlloc
0x18005c5e3  nop     dword ptr [rax+rax+00h]
0x18005c5e8  mov     rbx, rax
0x18005c5eb  test    rax, rax
0x18005c5ee  jnz     short loc_18005C61B
0x18005c5f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c5f7  cmp     rcx, r13
0x18005c5fa  jz      short loc_18005C611
0x18005c5fc  mov     rcx, [rcx+10h]
0x18005c600  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18005c607  mov     edx, 158h
0x18005c60c  call    WPP_SF_
0x18005c611  mov     edi, 0Eh
0x18005c616  jmp     loc_18005CE0D
0x18005c61b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c622  cmp     rcx, r13
0x18005c625  jz      short loc_18005C643
0x18005c627  mov     r9d, [rsi+90h]
0x18005c62e  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18005c635  mov     rcx, [rcx+10h]
0x18005c639  mov     edx, 159h
0x18005c63e  call    WPP_SF_d
0x18005c643  mov     eax, [rsi+90h]
0x18005c649  mov     [rbx+0B78h], eax
0x18005c64f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c656  cmp     rcx, r13
0x18005c659  jz      short loc_18005C674
0x18005c65b  mov     r9d, [rsi+4]
0x18005c65f  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18005c666  mov     rcx, [rcx+10h]
0x18005c66a  mov     edx, 15Ah
0x18005c66f  call    WPP_SF_d
0x18005c674  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Eaphost_TVS_Fixes@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Eaphost_TVS_Fixes@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Eaphost_TVS_Fixes> `wil::Feature<__WilFeatureTraits_Feature_Eaphost_TVS_Fixes>::GetImpl(void)'::`2'::impl
0x18005c67b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Eaphost_TVS_Fixes@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Eaphost_TVS_Fixes>::__private_IsEnabled(void)
0x18005c680  test    al, al
0x18005c682  jz      short loc_18005C699
0x18005c684  call    cs:__imp_GetTickCount64
0x18005c68b  nop     dword ptr [rax+rax+00h]
0x18005c690  mov     [rbx+0B60h], rax
0x18005c697  jmp     short loc_18005C6AB
0x18005c699  call    cs:__imp_GetTickCount
0x18005c6a0  nop     dword ptr [rax+rax+00h]
0x18005c6a5  mov     [rbx+0B5Ch], eax
0x18005c6ab  mov     ecx, [rbx+4]
0x18005c6ae  mov     [rbx], r14d
0x18005c6b1  cmp     [rsi+8], r14d
0x18005c6b5  jz      short loc_18005C6BD
0x18005c6b7  or      ecx, 1
0x18005c6ba  mov     [rbx+4], ecx
0x18005c6bd  test    byte ptr [rsi+4], 1
0x18005c6c1  jz      short loc_18005C6C9
0x18005c6c3  or      ecx, 2
0x18005c6c6  mov     [rbx+4], ecx
0x18005c6c9  test    byte ptr [rsi+4], 2
0x18005c6cd  jz      short loc_18005C6D5
0x18005c6cf  or      ecx, 4
0x18005c6d2  mov     [rbx+4], ecx
0x18005c6d5  test    byte ptr [rsi+4], 4
0x18005c6d9  jz      short loc_18005C6E1
0x18005c6db  or      ecx, 8
0x18005c6de  mov     [rbx+4], ecx
0x18005c6e1  test    byte ptr [rsi+4], 8
0x18005c6e5  jz      short loc_18005C6ED
0x18005c6e7  or      ecx, 10h
0x18005c6ea  mov     [rbx+4], ecx
0x18005c6ed  test    byte ptr [rsi+4], 10h
0x18005c6f1  jz      short loc_18005C6F9
0x18005c6f3  or      ecx, 20h
0x18005c6f6  mov     [rbx+4], ecx
0x18005c6f9  test    byte ptr [rsi+4], 20h
0x18005c6fd  jz      short loc_18005C704
0x18005c6ff  or      ecx, edi
0x18005c701  mov     [rbx+4], ecx
0x18005c704  test    [rsi+4], dil
0x18005c708  jz      short loc_18005C711
0x18005c70a  bts     ecx, 7
0x18005c70e  mov     [rbx+4], ecx
0x18005c711  test    byte ptr [rsi+4], 80h
0x18005c715  mov     edx, 100h
0x18005c71a  jz      short loc_18005C721
0x18005c71c  or      ecx, edx
0x18005c71e  mov     [rbx+4], ecx
0x18005c721  mov     r8d, 100000h
0x18005c727  test    [rsi+4], r8d
0x18005c72b  jz      short loc_18005C733
0x18005c72d  or      ecx, r8d
0x18005c730  mov     [rbx+4], ecx
0x18005c733  test    dword ptr [rsi+4], 400h
0x18005c73a  mov     eax, 800h
0x18005c73f  jz      short loc_18005C746
0x18005c741  or      ecx, eax
0x18005c743  mov     [rbx+4], ecx
0x18005c746  test    [rsi+4], eax
0x18005c749  jz      short loc_18005C752
0x18005c74b  bts     ecx, 0Eh
0x18005c74f  mov     [rbx+4], ecx
0x18005c752  test    dword ptr [rsi+4], 200000h
0x18005c759  jz      short loc_18005C762
0x18005c75b  bts     ecx, 12h
0x18005c75f  mov     [rbx+4], ecx
0x18005c762  mov     [rbx+0B54h], r14d
0x18005c769  lea     r13, String
0x18005c770  mov     rax, [rsi+38h]
0x18005c774  mov     [rbx+8], rax
0x18005c778  test    cl, 1
0x18005c77b  jz      short loc_18005C7C7
0x18005c77d  mov     r8, [rsi+18h]
0x18005c781  test    r8, r8
0x18005c784  jz      short loc_18005C7A1
0x18005c786  mov     r9, rdx
0x18005c789  lea     rcx, [rbx+816h]
0x18005c790  mov     edx, 101h
0x18005c795  call    cs:__imp__o_wcsncpy_s
0x18005c79c  nop     dword ptr [rax+rax+00h]
0x18005c7a1  mov     r8d, [rsi+60h]; unsigned int
0x18005c7a5  mov     rcx, rbx; struct _PEAP_CONTROL_BLOCK *
0x18005c7a8  mov     rdx, [rsi+58h]; unsigned __int8 *
0x18005c7ac  call    ?PeapConfigureServer@@YAKPEAU_PEAP_CONTROL_BLOCK@@PEAEK@Z; PeapConfigureServer(_PEAP_CONTROL_BLOCK *,uchar *,ulong)
0x18005c7b1  mov     edi, eax
0x18005c7b3  test    eax, eax
0x18005c7b5  jnz     loc_18005CDDE
0x18005c7bb  lea     r14, [rbx+0A30h]
0x18005c7c2  jmp     loc_18005C939
0x18005c7c7  test    [rsi+4], r8d
0x18005c7cb  jz      loc_18005CB28
0x18005c7d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c7d8  lea     rax, WPP_GLOBAL_Control
0x18005c7df  cmp     rcx, rax
0x18005c7e2  jz      short loc_18005C7F9
0x18005c7e4  mov     rcx, [rcx+10h]
0x18005c7e8  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18005c7ef  mov     edx, 15Bh
0x18005c7f4  call    WPP_SF_
0x18005c7f9  mov     edx, 26h ; '&'; uBytes
0x18005c7fe  mov     ecx, edi; uFlags
0x18005c800  call    cs:__imp_LocalAlloc
0x18005c807  nop     dword ptr [rax+rax+00h]
0x18005c80c  mov     rdi, rax
0x18005c80f  test    rax, rax
0x18005c812  jnz     short loc_18005C856
0x18005c814  call    cs:__imp_GetLastError
0x18005c81b  nop     dword ptr [rax+rax+00h]
0x18005c820  mov     edi, eax
0x18005c822  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c829  lea     r13, WPP_GLOBAL_Control
0x18005c830  cmp     rcx, r13
0x18005c833  jz      loc_18005CE0D
0x18005c839  mov     edx, 15Ch
0x18005c83e  mov     rcx, [rcx+10h]
0x18005c842  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18005c849  mov     r9d, eax
0x18005c84c  call    WPP_SF_d
0x18005c851  jmp     loc_18005CE0D
0x18005c856  or      dword ptr [rdi+0Ch], 2
0x18005c85a  mov     edx, 28h ; '('; uBytes
0x18005c85f  mov     dword ptr [rax], 1
0x18005c865  mov     dword ptr [rax+4], 24h ; '$'
0x18005c86c  mov     dword ptr [rax+10h], 1
0x18005c873  mov     dword ptr [rax+14h], 14h
0x18005c87a  lea     ecx, [rdx+18h]; uFlags
0x18005c87d  mov     eax, [rax+18h]
0x18005c880  and     eax, 0FFFFFFEDh
0x18005c883  mov     [rdi+8], r14d
0x18005c887  or      eax, 0A5h
0x18005c88c  mov     [rdi+18h], eax
0x18005c88f  call    cs:__imp_LocalAlloc
0x18005c896  nop     dword ptr [rax+rax+00h]
0x18005c89b  test    rax, rax
0x18005c89e  jnz     short loc_18005C8CF
0x18005c8a0  call    cs:__imp_GetLastError
0x18005c8a7  nop     dword ptr [rax+rax+00h]
0x18005c8ac  mov     edi, eax
0x18005c8ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c8b5  lea     r13, WPP_GLOBAL_Control
0x18005c8bc  cmp     rcx, r13
0x18005c8bf  jz      loc_18005CE0D
0x18005c8c5  mov     edx, 15Dh
0x18005c8ca  jmp     loc_18005C83E
0x18005c8cf  mov     [rax+24h], r14d
0x18005c8d3  lea     r14, [rbx+0A30h]
0x18005c8da  mov     dword ptr [rax], 2
0x18005c8e0  mov     dword ptr [rax+4], 28h ; '('
0x18005c8e7  mov     [r14], rdi
0x18005c8ea  mov     [rbx+0AB8h], rax
0x18005c8f1  cmp     [rsi+18h], r12
0x18005c8f5  jz      short loc_18005C917
0x18005c8f7  mov     r9d, 100h
0x18005c8fd  lea     rcx, [rbx+816h]
0x18005c904  mov     r8, r13
0x18005c907  lea     edx, [r9+1]
0x18005c90b  call    cs:__imp__o_wcsncpy_s
0x18005c912  nop     dword ptr [rax+rax+00h]
0x18005c917  mov     rax, [r14]
0x18005c91a  test    byte ptr [rax+0Ch], 1
0x18005c91e  setnz   cl; unsigned __int16 *
0x18005c921  test    dword ptr [rsi+4], 1000h
0x18005c928  setz    al
0x18005c92b  test    al, cl
0x18005c92d  jz      short loc_18005C934
0x18005c92f  bts     dword ptr [rbx+4], 0Ah
0x18005c934  bts     dword ptr [rbx+4], 13h
0x18005c939  lea     r8, [rbp+0E0h+hKey]; HKEY *
0x18005c93d  call    ?OpenPeapRegistryKey@@YAKPEBGKPEAPEAUHKEY__@@@Z; OpenPeapRegistryKey(ushort const *,ulong,HKEY__ * *)
0x18005c942  xor     edi, edi
0x18005c944  test    eax, eax
0x18005c946  jnz     short loc_18005C9B8
0x18005c948  mov     rcx, [rbp+0E0h+hKey]; hKey
0x18005c94c  lea     rax, [rbp+0E0h+cbData]
0x18005c950  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x18005c955  lea     r9, [rbp+0E0h+Type]; lpType
0x18005c959  lea     rax, [rbp+0E0h+Data]
0x18005c95d  mov     [rbp+0E0h+Type], edi
0x18005c960  xor     r8d, r8d; lpReserved
0x18005c963  mov     [rsp+1E0h+lpData], rax; lpData
0x18005c968  lea     rdx, aIdentityencodi; "IdentityEncodingFormat"
0x18005c96f  mov     dword ptr [rbp+0E0h+Data], edi
0x18005c972  mov     [rbp+0E0h+cbData], 4
0x18005c979  call    cs:__imp_RegQueryValueExW
0x18005c980  nop     dword ptr [rax+rax+00h]
0x18005c985  test    eax, eax
0x18005c987  jnz     short loc_18005C99F
0x18005c989  cmp     [rbp+0E0h+Type], 4
0x18005c98d  jnz     short loc_18005C99F
0x18005c98f  cmp     [rbp+0E0h+cbData], 4
0x18005c993  jnz     short loc_18005C99F
0x18005c995  cmp     dword ptr [rbp+0E0h+Data], edi
0x18005c998  jz      short loc_18005C99F
0x18005c99a  bts     dword ptr [rbx+4], 10h
0x18005c99f  mov     rcx, [rbp+0E0h+hKey]; hKey
0x18005c9a3  call    ?ReadCapabilitiesNegotiationKey@@YAXPEAUHKEY__@@@Z; ReadCapabilitiesNegotiationKey(HKEY__ *)
0x18005c9a8  mov     rcx, [rbp+0E0h+hKey]; hKey
0x18005c9ac  call    cs:__imp_RegCloseKey
0x18005c9b3  nop     dword ptr [rax+rax+00h]
0x18005c9b8  movups  xmm0, xmmword ptr [rsi+80h]
0x18005c9bf  movdqu  xmmword ptr [rbx+0B68h], xmm0
0x18005c9c7  mov     rax, [rsi+90h]
0x18005c9ce  movups  xmm1, xmmword ptr [rsi]
0x18005c9d1  mov     [rbp+0E0h+var_A0], rax
0x18005c9d5  movups  xmm0, xmmword ptr [rsi+10h]
0x18005c9d9  movups  [rbp+0E0h+var_130], xmm1
  ... truncated ...
```
