# EapPeapBegin

- ea: `0x180059200`
- end: `0x180059b1b`
- name: `EapPeapBegin`
- size: `2331`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800042dc`
- `0x180004bd0`
- `0x1800060f0`
- `0x1800075b0`
- `0x18001dec0`
- `0x18001e320`
- `0x18001e960`
- `0x18001f020`
- `0x180021adc`
- `0x180023b60`
- `0x18003256c`
- `0x180032670`
- `0x180035680`
- `0x180036254`
- `0x1800589e8`
- `0x180059200`
- `0x18005aa28`
- `0x1800706d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180059493`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800595eb`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180059802`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180059a79`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180059493`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800595eb`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180059802`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180059a79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059506`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059586`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800597c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800599d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059506`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059586`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800597c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800599d1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800592ec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800594f8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005957b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800592ec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800594f8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005957b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059a07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059aba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059ac8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059a07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059aba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059ac8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059680`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059680`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180059653`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180059653`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800599b7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800599b7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800597a0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800597a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005938e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005938e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005939d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005939d`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 341, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
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
    WPP_SF_(*((_QWORD *)v8 + 2), v9, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
    goto LABEL_130;
  }
  v10 = (char *)LocalAlloc(0x40u, 0xB88u);
  if ( !v10 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 344, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
    v7 = 14;
    goto LABEL_130;
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      345,
      &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
      *((unsigned int *)a2 + 36));
  *((_DWORD *)v10 + 734) = *((_DWORD *)a2 + 36);
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      346,
      &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
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
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 347, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
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
        WPP_SF_d(*((_QWORD *)v20 + 2), v21, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, LastError);
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
              &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
              Identity);
          v4 = v54;
          goto LABEL_130;
        }
        if ( *((_QWORD *)v10 + 1)
          && !RevertToSelf()
          && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          v45 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 356, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v45);
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
                       (BYTE **)v10 + 326);
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
      ConnectionData = PeapReadUserData(0, *((unsigned __int8 **)a2 + 13), *((_DWORD *)a2 + 28), (BYTE **)v10 + 343);
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
    WPP_SF_d(*((_QWORD *)v42 + 2), v43, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, ConnectionData);
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 357, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
  return v7;
}

```

## disassembly

```asm
0x180059200  mov     [rsp-8+arg_10], rbx
0x180059205  push    rbp
0x180059206  push    rsi
0x180059207  push    rdi
0x180059208  push    r12
0x18005920a  push    r13
0x18005920c  push    r14
0x18005920e  push    r15
0x180059210  lea     rbp, [rsp-0B0h]
0x180059218  sub     rsp, 1B0h
0x18005921f  mov     rax, cs:__security_cookie
0x180059226  xor     rax, rsp
0x180059229  mov     [rbp+0E0h+var_40], rax
0x180059230  mov     rsi, rdx
0x180059233  mov     qword ptr [rbp+0E0h+cbData], rcx
0x180059237  mov     r15, rcx
0x18005923a  mov     ebx, 98h
0x18005923f  mov     r8d, ebx; Size
0x180059242  lea     rcx, [rbp+0E0h+var_130]; void *
0x180059246  xor     edx, edx; Val
0x180059248  call    memset_0
0x18005924d  xor     edx, edx; Val
0x18005924f  lea     r8d, [rbx-50h]; Size
0x180059253  lea     rcx, [rbp+0E0h+var_90]; void *
0x180059257  call    memset_0
0x18005925c  xor     r14d, r14d
0x18005925f  mov     qword ptr [rbp+0E0h+Data], r14
0x180059263  mov     r12d, r14d
0x180059266  mov     [rbp+0E0h+var_140], r14
0x18005926a  mov     [rbp+0E0h+hKey], r14
0x18005926e  mov     rcx, cs:WPP_GLOBAL_Control
0x180059275  lea     r13, WPP_GLOBAL_Control
0x18005927c  cmp     rcx, r13
0x18005927f  jz      short loc_180059296
0x180059281  mov     rcx, [rcx+10h]
0x180059285  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18005928c  mov     edx, 155h
0x180059291  call    WPP_SF_
0x180059296  mov     rcx, rbx
0x180059299  lea     rax, [rbp+0E0h+var_130]
0x18005929d  mov     [rax], r14b
0x1800592a0  inc     rax
0x1800592a3  sub     rcx, 1; void *
0x1800592a7  jnz     short loc_18005929D
0x1800592a9  test    r15, r15
0x1800592ac  jz      loc_180059A8B
0x1800592b2  test    rsi, rsi
0x1800592b5  jz      loc_180059A8B
0x1800592bb  call    ?VerifyCallerTrust@@YAKPEAX@Z; VerifyCallerTrust(void *)
0x1800592c0  mov     edi, eax
0x1800592c2  test    eax, eax
0x1800592c4  jz      short loc_1800592E0
0x1800592c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800592cd  cmp     rcx, r13
0x1800592d0  jz      loc_180059AB1
0x1800592d6  mov     edx, 157h
0x1800592db  jmp     loc_180059AA1
0x1800592e0  mov     edi, 40h ; '@'
0x1800592e5  mov     edx, 0B88h; uBytes
0x1800592ea  mov     ecx, edi; uFlags
0x1800592ec  call    cs:__imp_LocalAlloc
0x1800592f2  mov     rbx, rax
0x1800592f5  test    rax, rax
0x1800592f8  jnz     short loc_180059325
0x1800592fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180059301  cmp     rcx, r13
0x180059304  jz      short loc_18005931B
0x180059306  mov     rcx, [rcx+10h]
0x18005930a  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180059311  mov     edx, 158h
0x180059316  call    WPP_SF_
0x18005931b  mov     edi, 0Eh
0x180059320  jmp     loc_180059AB1
0x180059325  mov     rcx, cs:WPP_GLOBAL_Control
0x18005932c  cmp     rcx, r13
0x18005932f  jz      short loc_18005934D
0x180059331  mov     r9d, [rsi+90h]
0x180059338  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18005933f  mov     rcx, [rcx+10h]
0x180059343  mov     edx, 159h
0x180059348  call    WPP_SF_d
0x18005934d  mov     eax, [rsi+90h]
0x180059353  mov     [rbx+0B78h], eax
0x180059359  mov     rcx, cs:WPP_GLOBAL_Control
0x180059360  cmp     rcx, r13
0x180059363  jz      short loc_18005937E
0x180059365  mov     r9d, [rsi+4]
0x180059369  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180059370  mov     rcx, [rcx+10h]
0x180059374  mov     edx, 15Ah
0x180059379  call    WPP_SF_d
0x18005937e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Eaphost_TVS_Fixes@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Eaphost_TVS_Fixes@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Eaphost_TVS_Fixes> `wil::Feature<__WilFeatureTraits_Feature_Eaphost_TVS_Fixes>::GetImpl(void)'::`2'::impl
0x180059385  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Eaphost_TVS_Fixes@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Eaphost_TVS_Fixes>::__private_IsEnabled(void)
0x18005938a  test    al, al
0x18005938c  jz      short loc_18005939D
0x18005938e  call    cs:__imp_GetTickCount64
0x180059394  mov     [rbx+0B60h], rax
0x18005939b  jmp     short loc_1800593A9
0x18005939d  call    cs:__imp_GetTickCount
0x1800593a3  mov     [rbx+0B5Ch], eax
0x1800593a9  mov     ecx, [rbx+4]
0x1800593ac  mov     [rbx], r14d
0x1800593af  cmp     [rsi+8], r14d
0x1800593b3  jz      short loc_1800593BB
0x1800593b5  or      ecx, 1
0x1800593b8  mov     [rbx+4], ecx
0x1800593bb  test    byte ptr [rsi+4], 1
0x1800593bf  jz      short loc_1800593C7
0x1800593c1  or      ecx, 2
0x1800593c4  mov     [rbx+4], ecx
0x1800593c7  test    byte ptr [rsi+4], 2
0x1800593cb  jz      short loc_1800593D3
0x1800593cd  or      ecx, 4
0x1800593d0  mov     [rbx+4], ecx
0x1800593d3  test    byte ptr [rsi+4], 4
0x1800593d7  jz      short loc_1800593DF
0x1800593d9  or      ecx, 8
0x1800593dc  mov     [rbx+4], ecx
0x1800593df  test    byte ptr [rsi+4], 8
0x1800593e3  jz      short loc_1800593EB
0x1800593e5  or      ecx, 10h
0x1800593e8  mov     [rbx+4], ecx
0x1800593eb  test    byte ptr [rsi+4], 10h
0x1800593ef  jz      short loc_1800593F7
0x1800593f1  or      ecx, 20h
0x1800593f4  mov     [rbx+4], ecx
0x1800593f7  test    byte ptr [rsi+4], 20h
0x1800593fb  jz      short loc_180059402
0x1800593fd  or      ecx, edi
0x1800593ff  mov     [rbx+4], ecx
0x180059402  test    [rsi+4], dil
0x180059406  jz      short loc_18005940F
0x180059408  bts     ecx, 7
0x18005940c  mov     [rbx+4], ecx
0x18005940f  test    byte ptr [rsi+4], 80h
0x180059413  mov     edx, 100h
0x180059418  jz      short loc_18005941F
0x18005941a  or      ecx, edx
0x18005941c  mov     [rbx+4], ecx
0x18005941f  mov     r8d, 100000h
0x180059425  test    [rsi+4], r8d
0x180059429  jz      short loc_180059431
0x18005942b  or      ecx, r8d
0x18005942e  mov     [rbx+4], ecx
0x180059431  test    dword ptr [rsi+4], 400h
0x180059438  mov     eax, 800h
0x18005943d  jz      short loc_180059444
0x18005943f  or      ecx, eax
0x180059441  mov     [rbx+4], ecx
0x180059444  test    [rsi+4], eax
0x180059447  jz      short loc_180059450
0x180059449  bts     ecx, 0Eh
0x18005944d  mov     [rbx+4], ecx
0x180059450  test    dword ptr [rsi+4], 200000h
0x180059457  jz      short loc_180059460
0x180059459  bts     ecx, 12h
0x18005945d  mov     [rbx+4], ecx
0x180059460  mov     [rbx+0B54h], r14d
0x180059467  lea     r13, String
0x18005946e  mov     rax, [rsi+38h]
0x180059472  mov     [rbx+8], rax
0x180059476  test    cl, 1
0x180059479  jz      short loc_1800594BF
0x18005947b  mov     r8, [rsi+18h]
0x18005947f  test    r8, r8
0x180059482  jz      short loc_180059499
0x180059484  mov     r9, rdx
0x180059487  lea     rcx, [rbx+816h]
0x18005948e  mov     edx, 101h
0x180059493  call    cs:__imp__o_wcsncpy_s
0x180059499  mov     r8d, [rsi+60h]; unsigned int
0x18005949d  mov     rcx, rbx; struct _PEAP_CONTROL_BLOCK *
0x1800594a0  mov     rdx, [rsi+58h]; unsigned __int8 *
0x1800594a4  call    ?PeapConfigureServer@@YAKPEAU_PEAP_CONTROL_BLOCK@@PEAEK@Z; PeapConfigureServer(_PEAP_CONTROL_BLOCK *,uchar *,ulong)
0x1800594a9  mov     edi, eax
0x1800594ab  test    eax, eax
0x1800594ad  jnz     loc_180059A82
0x1800594b3  lea     r14, [rbx+0A30h]
0x1800594ba  jmp     loc_180059613
0x1800594bf  test    [rsi+4], r8d
0x1800594c3  jz      loc_1800597EA
0x1800594c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800594d0  lea     rax, WPP_GLOBAL_Control
0x1800594d7  cmp     rcx, rax
0x1800594da  jz      short loc_1800594F1
0x1800594dc  mov     rcx, [rcx+10h]
0x1800594e0  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x1800594e7  mov     edx, 15Bh
0x1800594ec  call    WPP_SF_
0x1800594f1  mov     edx, 26h ; '&'; uBytes
0x1800594f6  mov     ecx, edi; uFlags
0x1800594f8  call    cs:__imp_LocalAlloc
0x1800594fe  mov     rdi, rax
0x180059501  test    rax, rax
0x180059504  jnz     short loc_180059542
0x180059506  call    cs:__imp_GetLastError
0x18005950c  mov     edi, eax
0x18005950e  mov     rcx, cs:WPP_GLOBAL_Control
0x180059515  lea     r13, WPP_GLOBAL_Control
0x18005951c  cmp     rcx, r13
0x18005951f  jz      loc_180059AB1
0x180059525  mov     edx, 15Ch
0x18005952a  mov     rcx, [rcx+10h]
0x18005952e  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180059535  mov     r9d, eax
0x180059538  call    WPP_SF_d
0x18005953d  jmp     loc_180059AB1
0x180059542  or      dword ptr [rdi+0Ch], 2
0x180059546  mov     edx, 28h ; '('; uBytes
0x18005954b  mov     dword ptr [rax], 1
0x180059551  mov     dword ptr [rax+4], 24h ; '$'
0x180059558  mov     dword ptr [rax+10h], 1
0x18005955f  mov     dword ptr [rax+14h], 14h
0x180059566  lea     ecx, [rdx+18h]; uFlags
0x180059569  mov     eax, [rax+18h]
0x18005956c  and     eax, 0FFFFFFEDh
0x18005956f  mov     [rdi+8], r14d
0x180059573  or      eax, 0A5h
0x180059578  mov     [rdi+18h], eax
0x18005957b  call    cs:__imp_LocalAlloc
0x180059581  test    rax, rax
0x180059584  jnz     short loc_1800595AF
0x180059586  call    cs:__imp_GetLastError
0x18005958c  mov     edi, eax
0x18005958e  mov     rcx, cs:WPP_GLOBAL_Control
0x180059595  lea     r13, WPP_GLOBAL_Control
0x18005959c  cmp     rcx, r13
0x18005959f  jz      loc_180059AB1
0x1800595a5  mov     edx, 15Dh
0x1800595aa  jmp     loc_18005952A
0x1800595af  mov     [rax+24h], r14d
0x1800595b3  lea     r14, [rbx+0A30h]
0x1800595ba  mov     dword ptr [rax], 2
0x1800595c0  mov     dword ptr [rax+4], 28h ; '('
0x1800595c7  mov     [r14], rdi
0x1800595ca  mov     [rbx+0AB8h], rax
0x1800595d1  cmp     [rsi+18h], r12
0x1800595d5  jz      short loc_1800595F1
0x1800595d7  mov     r9d, 100h
0x1800595dd  lea     rcx, [rbx+816h]
0x1800595e4  mov     r8, r13
0x1800595e7  lea     edx, [r9+1]
0x1800595eb  call    cs:__imp__o_wcsncpy_s
0x1800595f1  mov     rax, [r14]
0x1800595f4  test    byte ptr [rax+0Ch], 1
0x1800595f8  setnz   cl; unsigned __int16 *
0x1800595fb  test    dword ptr [rsi+4], 1000h
0x180059602  setz    al
0x180059605  test    al, cl
0x180059607  jz      short loc_18005960E
0x180059609  bts     dword ptr [rbx+4], 0Ah
0x18005960e  bts     dword ptr [rbx+4], 13h
0x180059613  lea     r8, [rbp+0E0h+hKey]; HKEY *
0x180059617  call    ?OpenPeapRegistryKey@@YAKPEBGKPEAPEAUHKEY__@@@Z; OpenPeapRegistryKey(ushort const *,ulong,HKEY__ * *)
0x18005961c  xor     edi, edi
0x18005961e  test    eax, eax
0x180059620  jnz     short loc_180059686
0x180059622  mov     rcx, [rbp+0E0h+hKey]; hKey
0x180059626  lea     rax, [rbp+0E0h+cbData]
0x18005962a  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x18005962f  lea     r9, [rbp+0E0h+Type]; lpType
0x180059633  lea     rax, [rbp+0E0h+Data]
0x180059637  mov     [rbp+0E0h+Type], edi
0x18005963a  xor     r8d, r8d; lpReserved
0x18005963d  mov     [rsp+1E0h+lpData], rax; lpData
0x180059642  lea     rdx, aIdentityencodi; "IdentityEncodingFormat"
0x180059649  mov     dword ptr [rbp+0E0h+Data], edi
0x18005964c  mov     [rbp+0E0h+cbData], 4
0x180059653  call    cs:__imp_RegQueryValueExW
0x180059659  test    eax, eax
0x18005965b  jnz     short loc_180059673
0x18005965d  cmp     [rbp+0E0h+Type], 4
0x180059661  jnz     short loc_180059673
0x180059663  cmp     [rbp+0E0h+cbData], 4
0x180059667  jnz     short loc_180059673
0x180059669  cmp     dword ptr [rbp+0E0h+Data], edi
0x18005966c  jz      short loc_180059673
0x18005966e  bts     dword ptr [rbx+4], 10h
0x180059673  mov     rcx, [rbp+0E0h+hKey]; hKey
0x180059677  call    ?ReadCapabilitiesNegotiationKey@@YAXPEAUHKEY__@@@Z; ReadCapabilitiesNegotiationKey(HKEY__ *)
0x18005967c  mov     rcx, [rbp+0E0h+hKey]; hKey
0x180059680  call    cs:__imp_RegCloseKey
0x180059686  movups  xmm0, xmmword ptr [rsi+80h]
0x18005968d  movdqu  xmmword ptr [rbx+0B68h], xmm0
0x180059695  mov     rax, [rsi+90h]
0x18005969c  movups  xmm1, xmmword ptr [rsi]
0x18005969f  mov     [rbp+0E0h+var_A0], rax
0x1800596a3  movups  xmm0, xmmword ptr [rsi+10h]
0x1800596a7  movups  [rbp+0E0h+var_130], xmm1
0x1800596ab  movups  xmm1, xmmword ptr [rsi+20h]
0x1800596af  movups  [rbp+0E0h+var_120], xmm0
0x1800596b3  movups  xmm0, xmmword ptr [rsi+30h]
0x1800596b7  movups  [rbp+0E0h+var_110], xmm1
0x1800596bb  movups  xmm1, xmmword ptr [rsi+40h]
0x1800596bf  movups  [rbp+0E0h+var_100], xmm0
0x1800596c3  movups  xmm0, xmmword ptr [rsi+50h]
0x1800596c7  movups  [rbp+0E0h+var_F0], xmm1
0x1800596cb  movups  xmm1, xmmword ptr [rsi+60h]
0x1800596cf  movups  xmmword ptr [rbp+0E0h+hMem], xmm0
0x1800596d3  movups  xmm0, xmmword ptr [rsi+70h]
  ... truncated ...
```
