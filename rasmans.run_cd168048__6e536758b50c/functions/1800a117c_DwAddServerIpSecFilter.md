# DwAddServerIpSecFilter

- ea: `0x1800a117c`
- end: `0x1800a1f1a`
- name: `DwAddServerIpSecFilter`
- size: `3486`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003f69c`
- `0x180040094`

## callees

- `0x18009fcf8`
- `0x1800a0174`
- `0x1800a0230`
- `0x1800a0410`
- `0x1800a06f8`
- `0x1800a07b4`
- `0x1800a08a0`
- `0x1800a117c`
- `0x1800a257c`
- `0x1800a29c0`
- `0x1800a2b38`
- `0x1800a2cb0`
- `0x1800a2df4`
- `0x1800a3340`
- `0x1800a3928`
- `0x1800a3f98`
- `0x1800ab634`
- `0x1800b1984`
- `0x1800e7e28`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1280`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a144e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1280`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a144e`
- `RPCRT4!UuidCreate` at `0x1800a1726`
- `RPCRT4!UuidCreate` at `0x1800a174d`
- `RPCRT4!UuidCreate` at `0x1800a1726`
- `RPCRT4!UuidCreate` at `0x1800a174d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a156b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a158b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a156b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a158b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a14e2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a14e2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a1257`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a143a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a1547`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a1257`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a143a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a1547`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a12b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1308`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a12b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1308`
- `fwpuclnt!FwpmTransactionCommit0` at `0x1800a1aa5`
- `fwpuclnt!FwpmTransactionCommit0` at `0x1800a1aa5`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x1800a17dc`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x1800a17dc`
- `fwpuclnt!FwpmTransactionAbort0` at `0x1800a1eff`
- `fwpuclnt!FwpmTransactionAbort0` at `0x1800a1eff`
- `fwpuclnt!FwpmProviderContextAdd2` at `0x1800a17aa`
- `fwpuclnt!FwpmProviderContextAdd2` at `0x1800a17aa`

## string_xrefs

- `0x1800a173a`: `DwAddServerIpsecFilter: UuidCreate failed with 0x%x`
- `0x1800a14f4`: `DwAddServerIpSecFilter:OpenIkev2ConfigKey: Failed. error %d`
- `0x1800a159d`: `DwAddServerIpSecFilter:GetIkev2ConfigParams: Failed. error %d`
- `0x1800a14a4`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters\L2TP`

## pseudocode

```c
__int64 __fastcall DwAddServerIpSecFilter(unsigned int a1, __int64 a2, int a3)
{
  _DWORD *v3; // r13
  int v4; // r15d
  __int64 v7; // rsi
  _DWORD *v8; // r14
  int v9; // r12d
  DWORD LastError; // ebx
  void *v11; // rcx
  __int64 i; // rdi
  DWORD v14; // eax
  int v15; // r12d
  DWORD v16; // esi
  __int64 v17; // rax
  __int64 v18; // rax
  DWORD v19; // eax
  const CHAR *v20; // rcx
  int L2tpConfigParams; // ebx
  int v22; // esi
  int v23; // ebx
  _DWORD *v24; // rcx
  bool v25; // cf
  HLOCAL v26; // rbx
  const CHAR *v27; // rcx
  __int64 v28; // rdx
  unsigned int v29; // edi
  unsigned int v30; // edi
  unsigned int v31; // edi
  unsigned int v32; // edi
  int v33; // edx
  int v34; // edx
  int v35; // edx
  __int64 v36; // rdx
  __int64 v37; // rdx
  _BYTE *v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // rdx
  __int64 v43; // r8
  int v44; // edx
  int v45; // edx
  int v46; // edx
  int v47; // edx
  BYTE samDesired; // [rsp+28h] [rbp-D8h]
  REGSAM samDesireda; // [rsp+28h] [rbp-D8h]
  REGSAM samDesiredb; // [rsp+28h] [rbp-D8h]
  REGSAM samDesiredc; // [rsp+28h] [rbp-D8h]
  REGSAM samDesiredd; // [rsp+28h] [rbp-D8h]
  REGSAM samDesirede; // [rsp+28h] [rbp-D8h]
  REGSAM samDesiredf; // [rsp+28h] [rbp-D8h]
  REGSAM samDesiredg; // [rsp+28h] [rbp-D8h]
  DWORD lpdwDisposition; // [rsp+40h] [rbp-C0h]
  int v57; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v58; // [rsp+58h] [rbp-A8h]
  __int64 v59; // [rsp+60h] [rbp-A0h]
  int v60; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwDisposition; // [rsp+6Ch] [rbp-94h] BYREF
  int v62; // [rsp+70h] [rbp-90h] BYREF
  int v63; // [rsp+74h] [rbp-8Ch] BYREF
  HLOCAL v64; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL v66; // [rsp+88h] [rbp-78h] BYREF
  __int64 v67; // [rsp+90h] [rbp-70h]
  HLOCAL hMem; // [rsp+98h] [rbp-68h]
  __int128 v69; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v70; // [rsp+B0h] [rbp-50h]
  __int128 v71; // [rsp+C0h] [rbp-40h]
  __int64 v72; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v73; // [rsp+D8h] [rbp-28h]
  __int64 v74; // [rsp+E0h] [rbp-20h]
  int v75; // [rsp+E8h] [rbp-18h]
  int v76; // [rsp+ECh] [rbp-14h]
  __int128 v77; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v78; // [rsp+100h] [rbp+0h]
  int v79; // [rsp+110h] [rbp+10h]
  _BYTE v80[16]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v81[16]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v82[16]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v83[16]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v84[16]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v85[16]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v86[16]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v87[16]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v88[16]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v89[16]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v90[16]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v91[16]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v92[16]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v93[16]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v94[16]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v95[16]; // [rsp+210h] [rbp+110h] BYREF
  _BYTE v96[16]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v97[16]; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v98[16]; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v99[16]; // [rsp+250h] [rbp+150h] BYREF
  UUID v100; // [rsp+260h] [rbp+160h] BYREF
  const wchar_t *v101; // [rsp+270h] [rbp+170h]
  int v102; // [rsp+2A0h] [rbp+1A0h]
  __int128 *v103; // [rsp+2A8h] [rbp+1A8h]
  FWPM_PROVIDER_CONTEXT0 Uuid; // [rsp+2C0h] [rbp+1C0h] BYREF

  v3 = 0;
  v59 = a2;
  v4 = a3;
  v58 = a2;
  v67 = a2;
  v57 = a3;
  v7 = a2;
  v64 = 0;
  v66 = 0;
  v8 = 0;
  memset_0(&v100, 0, 0x58u);
  memset_0(&Uuid, 0, sizeof(Uuid));
  v62 = 0;
  v60 = 0;
  v79 = 0;
  v63 = 0;
  hKey = 0;
  v77 = 0;
  v9 = 0;
  v78 = 0;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  memset_0(v80, 0, 0x140u);
  RasIpsecTrace("DwAddServerIpSecFilter");
  hMem = LocalAlloc(0x40u, 0x118u);
  if ( !hMem )
  {
    RasIpsecTrace("DwAddServerIpsecFilter: failed to alloc");
    LastError = GetLastError();
    goto LABEL_3;
  }
  dwDisposition = 1;
  if ( !a2 )
  {
    DwGetPresharedKey(0, 256, (int)&v57);
    v7 = v67;
    v4 = v57;
    v58 = v67;
  }
  if ( v4 )
    v9 = 1;
  v57 = v9;
  v14 = GenerateCertificatesList(1, &v64, &v57, &dwDisposition);
  v15 = v57;
  LastError = v14;
  if ( !v4 )
  {
    v16 = dwDisposition;
    if ( !v14 && v57 && !dwDisposition )
    {
      v8 = v64;
      goto LABEL_37;
    }
    RasIpsecTrace("PSK=NULL. Failed to generate certificate list. rc=0x%x, Count=%d, MyStoreEmpty=%d");
    if ( !v15 || v16 )
      LastError = 766;
    v8 = v64;
    if ( v64 )
    {
      FreeAuthInfoList(v64);
      v8 = 0;
    }
    goto LABEL_33;
  }
  v8 = v64;
  v17 = 1;
  if ( v64 )
  {
LABEL_36:
    v18 = 10 * v17;
    v8[2 * v18] = 0;
    *(_QWORD *)&v8[2 * v18 + 4] = v7;
    v8[2 * v18 + 2] = v4;
    goto LABEL_37;
  }
  v8 = LocalAlloc(0x40u, 0x40u);
  if ( v8 )
  {
    v17 = 0;
    goto LABEL_36;
  }
  LastError = GetLastError();
LABEL_33:
  if ( LastError )
  {
    RasIpsecTrace("DwAddServerIpsecFilter: DwGetMMAuthMethodsForServer returned %d. PSK length is %d");
    goto LABEL_7;
  }
LABEL_37:
  dwDisposition = 0;
  if ( RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\L2TP",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         &dwDisposition) )
  {
    RasIpsecTrace("DwAddServerIpSecFilter:OpenIkev2ConfigKey: Failed. error %d");
LABEL_39:
    v19 = BuildIpsecOffers(a1, &v66, &v60);
    goto LABEL_40;
  }
  v3 = LocalAlloc(0x40u, 0x20u);
  if ( !v3 )
  {
    RasIpsecTrace("DwAddServerIpSecFilter: Memory allocation failed");
    RegCloseKey(hKey);
    goto LABEL_39;
  }
  L2tpConfigParams = GetL2tpConfigParams(hKey);
  RegCloseKey(hKey);
  if ( L2tpConfigParams )
    RasIpsecTrace("DwAddServerIpSecFilter:GetIkev2ConfigParams: Failed. error %d");
  a1 = v3[1];
  v22 = v3[2];
  v23 = v3[3];
  if ( a1 == 1 )
  {
    a1 = 4;
  }
  else if ( v3[1] == 2 )
  {
    a1 = 5;
  }
  v24 = (_DWORD *)*((_QWORD *)v3 + 2);
  if ( !v24 )
    goto LABEL_39;
  v25 = v24[2] < 9u;
  v76 = 0;
  if ( v25 )
    v73 = qword_1800EE5F0[v24[2]];
  else
    v73 = 0;
  if ( v24[3] >= 6u )
    v74 = 0;
  else
    v74 = off_1800EE638[v24[3]];
  v25 = v24[4] < 8u;
  v72 = 0;
  v75 = v25 ? v24[4] : 0;
  v19 = BuildCustomEncryption((int)&v66, (int)&v60, 0, v23, v22, samDesired, (__int64)&v72, 1, lpdwDisposition);
LABEL_40:
  LastError = v19;
  if ( v19 )
  {
    v20 = "DwAddServerIpsecFilter: BuildIpsecOffers returned %d";
LABEL_42:
    RasIpsecTrace(v20);
    goto LABEL_3;
  }
  BuildQMPolicy((unsigned int)&Uuid, (unsigned int)&v77, a1, (_DWORD)v66, v60, 0, 0);
  if ( v3 )
    DWORD2(v78) = *v3;
  v26 = hMem;
  BuildMMOffers((int)hMem, (int)&v63, (int)&v62, 1, 0, 0, (__int64)v3);
  v71 = (unsigned int)v62;
  DWORD1(v70) = v63;
  LODWORD(v70) = 0;
  LODWORD(v69) = 28800;
  *((_QWORD *)&v70 + 1) = v26;
  *((_QWORD *)&v69 + 1) = v8;
  DWORD1(v69) = v15;
  memset_0(&v100, 0, 0x58u);
  v102 = 5;
  v103 = &v69;
  v101 = L"L2TP Main Mode Policy";
  LastError = UuidCreate(&Uuid.providerContextKey);
  if ( LastError || (LastError = UuidCreate(&v100)) != 0 )
  {
    v20 = "DwAddServerIpsecFilter: UuidCreate failed with 0x%x";
    goto LABEL_42;
  }
  gServerMMPolicyGuid = v100;
  gServerQMPolicyGuid = Uuid.providerContextKey;
  LastError = FwpmTransactionBegin0Wrapper();
  if ( LastError )
  {
    v20 = "FwpmTransactionBegin0 failed with 0x%x";
    goto LABEL_42;
  }
  LastError = FwpmProviderContextAdd2(gFwpEngineHandle, &v100, 0, 0);
  if ( !LastError )
  {
    LastError = FwpmProviderContextAdd0(gFwpEngineHandle, &Uuid, 0, 0);
    if ( LastError )
    {
      v27 = "FwpmProviderContextAdd0 for QM policy failed with 0x%x";
      goto LABEL_143;
    }
    if ( a1 )
    {
      v29 = a1 - 1;
      if ( v29 )
      {
        v30 = v29 - 1;
        if ( !v30 )
          goto LABEL_76;
        v31 = v30 - 1;
        if ( !v31 )
          goto LABEL_76;
        v32 = v31 - 1;
        if ( v32 )
        {
          if ( v32 != 1 )
            goto LABEL_3;
LABEL_76:
          LastError = BuildOutTxFilter((unsigned int)v91, v28, 1, 1, 1);
          if ( LastError )
          {
LABEL_77:
            v27 = "BuildOutTxFilter for QM policy failed with 0x%x  Ipv6: TRUE";
            goto LABEL_143;
          }
          LastError = BuildOutTxFilter((unsigned int)v90, v33, 1, 1, 0);
          if ( LastError )
          {
LABEL_79:
            v27 = "BuildOutTxFilter for QM policy failed with 0x%x  Ipv6: FALSE";
            goto LABEL_143;
          }
          LastError = AddFilters(v91, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
          {
LABEL_81:
            v27 = "AddFilters for QM policy failed with 0x%x  Ipv6: TRUE";
            goto LABEL_143;
          }
          LastError = AddFilters(v90, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( !LastError )
          {
            LastError = BuildOutTxFilter((unsigned int)v95, v34, 1, 0, 1);
            if ( LastError )
              goto LABEL_77;
            LastError = BuildOutTxFilter((unsigned int)v94, v35, 1, 0, 0);
            if ( LastError )
              goto LABEL_79;
            LastError = AddFilters(v95, gServerFilterIds, &gNumServerFilterIds, 0);
            if ( LastError )
              goto LABEL_81;
            LastError = AddFilters(v94, gServerFilterIds, &gNumServerFilterIds, 0);
            if ( !LastError )
            {
              LastError = BuildInTxFilter(
                            (unsigned int)v93,
                            1,
                            0,
                            1701,
                            (__int64)L"L2TP Server Filter1",
                            samDesireda,
                            1);
              if ( LastError )
              {
LABEL_89:
                v27 = "BuildInTxFilter for QM policy failed with 0x%x  Ipv6: TRUE";
                goto LABEL_143;
              }
              LastError = BuildInTxFilter(
                            (unsigned int)v92,
                            1,
                            0,
                            1701,
                            (__int64)L"L2TP Server Filter1",
                            samDesiredb,
                            0);
              if ( LastError )
              {
LABEL_91:
                v27 = "BuildInTxFilter for QM policy failed with 0x%x  Ipv6: FALSE";
                goto LABEL_143;
              }
              LastError = AddFilters(v93, gServerFilterIds, &gNumServerFilterIds, 0);
              if ( LastError )
              {
LABEL_93:
                v27 = "AddFilters for QM policy failed with 0x%x  Ipv6: TRUE";
                goto LABEL_143;
              }
              LastError = AddFilters(v92, gServerFilterIds, &gNumServerFilterIds, 0);
              if ( LastError )
              {
LABEL_95:
                v27 = "AddFilters for QM policy failed with 0x%x  Ipv6: FALSE";
                goto LABEL_143;
              }
              LastError = BuildOutMMFilter(v97, v36, L"L2TP Server Inbound and Outbound Filter", 1);
              if ( LastError )
              {
                v27 = "BuildOutMMFilter for MM policy failed with 0x%x  Ipv6: TRUE";
                goto LABEL_143;
              }
              LastError = BuildOutMMFilter(v96, v37, L"L2TP Server Inbound and Outbound Filter", 0);
              if ( LastError )
              {
                v27 = "BuildOutMMFilter for MM policy failed with 0x%x  Ipv6: FALSE";
                goto LABEL_143;
              }
              LastError = AddFilters(v97, gServerFilterIds, &gNumServerFilterIds, 0);
              if ( LastError )
              {
LABEL_101:
                v27 = "AddFilters for MM policy failed with 0x%x  Ipv6: TRUE";
                goto LABEL_143;
              }
              v38 = v96;
              goto LABEL_141;
            }
          }
          goto LABEL_83;
        }
      }
    }
    LastError = BuildOutMMFilter(v97, v28, L"L2TP Server Outbound Filter", 1);
    if ( LastError )
    {
      v27 = "BuildOutMMFilter for MM policy failed with 0x%x  IPv6: TRUE";
      goto LABEL_143;
    }
    LastError = BuildOutMMFilter(v96, v39, L"L2TP Server Outbound Filter", 0);
    if ( LastError )
    {
      v27 = "BuildOutMMFilter for MM policy failed with 0x%x  IPv6: FALSE";
      goto LABEL_143;
    }
    LastError = BuildInMMFilter(v99, v40, v41, 1);
    if ( LastError )
    {
      v27 = "BuildInMMFilter for MM policy failed with 0x%x  IPv6: TRUE";
      goto LABEL_143;
    }
    LastError = BuildInMMFilter(v98, v42, v43, 0);
    if ( LastError )
    {
      v27 = "BuildInMMFilter for MM policy failed with 0x%x  IPv6: FALSE";
      goto LABEL_143;
    }
    LastError = BuildOutTxFilter((unsigned int)v81, v44, 0, 1, 1);
    if ( LastError )
      goto LABEL_77;
    LastError = BuildOutTxFilter((unsigned int)v80, v45, 0, 1, 0);
    if ( LastError )
      goto LABEL_79;
    LastError = AddFilters(v81, gServerFilterIds, &gNumServerFilterIds, 0);
    if ( LastError )
      goto LABEL_81;
    LastError = AddFilters(v80, gServerFilterIds, &gNumServerFilterIds, 0);
    if ( LastError )
      goto LABEL_83;
    LastError = BuildOutTxFilter((unsigned int)v83, v46, 0, 0, 1);
    if ( LastError )
      goto LABEL_77;
    LastError = BuildOutTxFilter((unsigned int)v82, v47, 0, 0, 0);
    if ( LastError )
    {
      v27 = "BuildOutTxFilter for QM policy failed with 0x%x";
      goto LABEL_143;
    }
    LastError = AddFilters(v83, gServerFilterIds, &gNumServerFilterIds, 0);
    if ( LastError )
      goto LABEL_81;
    LastError = AddFilters(v82, gServerFilterIds, &gNumServerFilterIds, 0);
    if ( LastError )
      goto LABEL_83;
    LastError = BuildInTxFilter((unsigned int)v85, 0, 1701, 0, (__int64)L"L2TP Server Inbound Filter", samDesireda, 1);
    if ( LastError )
    {
LABEL_123:
      v27 = "BuildInTxFilter for QM policy failed with 0x%x  Ipv6: TRUE";
      goto LABEL_143;
    }
    LastError = BuildInTxFilter((unsigned int)v84, 0, 1701, 0, (__int64)L"L2TP Server Inbound Filter", samDesiredc, 0);
    if ( !LastError )
    {
      LastError = AddFilters(v85, gServerFilterIds, &gNumServerFilterIds, 0);
      if ( LastError )
        goto LABEL_81;
      LastError = AddFilters(v84, gServerFilterIds, &gNumServerFilterIds, 0);
      if ( LastError )
        goto LABEL_83;
      LastError = BuildInTxFilter(
                    (unsigned int)v87,
                    0,
                    1701,
                    1701,
                    (__int64)L"L2TP Server Inbound Filter",
                    samDesiredd,
                    1);
      if ( LastError )
        goto LABEL_123;
      LastError = BuildInTxFilter(
                    (unsigned int)v86,
                    0,
                    1701,
                    1701,
                    (__int64)L"L2TP Server Inbound Filter",
                    samDesirede,
                    0);
      if ( !LastError )
      {
        LastError = AddFilters(v87, gServerFilterIds, &gNumServerFilterIds, 0);
        if ( LastError )
          goto LABEL_81;
        LastError = AddFilters(v86, gServerFilterIds, &gNumServerFilterIds, 0);
        if ( !LastError )
        {
          LastError = BuildInTxFilter((unsigned int)v89, 1, 0, 1701, (__int64)L"L2TP Server Filter1", samDesiredf, 1);
          if ( LastError )
            goto LABEL_89;
          LastError = BuildInTxFilter((unsigned int)v88, 1, 0, 1701, (__int64)L"L2TP Server Filter1", samDesiredg, 0);
          if ( LastError )
            goto LABEL_91;
          LastError = AddFilters(v89, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
            goto LABEL_93;
          LastError = AddFilters(v88, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
            goto LABEL_95;
          LastError = AddFilters(v97, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
            goto LABEL_101;
          LastError = AddFilters(v96, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
          {
LABEL_142:
            v27 = "AddFilters for MM policy failed with 0x%x  Ipv6: FALSE";
            goto LABEL_143;
          }
          LastError = AddFilters(v99, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
          {
            v27 = "AddFilters for MM policy failed with 0x%x  Ipv6:  TRUE";
            goto LABEL_143;
          }
          v38 = v98;
LABEL_141:
          LastError = AddFilters(v38, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( !LastError )
          {
            LastError = FwpmTransactionCommit0(gFwpEngineHandle);
            if ( v8 )
            {
              FreeAuthInfoList(v8);
              v8 = 0;
            }
            goto LABEL_3;
          }
          goto LABEL_142;
        }
LABEL_83:
        v27 = "AddFilters for QM policy failed with 0x%x  Ipv6: FALSE";
        goto LABEL_143;
      }
    }
    v27 = "BuildInTxFilter for QM policy failed with 0x%x  Ipv6: FALSE";
    goto LABEL_143;
  }
  v27 = "FwpmProviderContextAdd0 for MM policy failed with 0x%x";
LABEL_143:
  RasIpsecTrace(v27);
  FwpmTransactionAbort0(gFwpEngineHandle);
LABEL_3:
  if ( v3 )
  {
    v11 = (void *)*((_QWORD *)v3 + 2);
    if ( v11 )
    {
      MprCommonFree(v11);
      *((_QWORD *)v3 + 2) = 0;
    }
    LocalFree(v3);
  }
LABEL_7:
  if ( v66 )
    FreeIpsecOffers(v66);
  for ( i = 0; i != 20; ++i )
    WfpFilterListDestroy(&v80[16 * i], &v80[16 * i + 8]);
  if ( hMem )
    LocalFree(hMem);
  if ( v8 )
    FreeAuthInfoList(v8);
  RasIpsecTrace("DwAddServerIpSecFilter, rc=0x%x");
  return LastError;
}

```

## disassembly

```asm
0x1800a117c  mov     [rsp-8+arg_18], rbx
0x1800a1181  push    rbp
0x1800a1182  push    rsi
0x1800a1183  push    rdi
0x1800a1184  push    r12
0x1800a1186  push    r13
0x1800a1188  push    r14
0x1800a118a  push    r15
0x1800a118c  lea     rbp, [rsp-230h]
0x1800a1194  sub     rsp, 330h
0x1800a119b  mov     rax, cs:__security_cookie
0x1800a11a2  xor     rax, rsp
0x1800a11a5  mov     [rbp+260h+var_40], rax
0x1800a11ac  xor     r13d, r13d
0x1800a11af  mov     [rsp+360h+var_300], rdx
0x1800a11b4  mov     r15d, r8d
0x1800a11b7  mov     [rsp+360h+var_308], rdx
0x1800a11bc  mov     rbx, rdx
0x1800a11bf  mov     [rbp+260h+var_2D0], rdx
0x1800a11c3  mov     edi, ecx
0x1800a11c5  mov     [rsp+360h+var_310], r8d
0x1800a11ca  mov     rsi, rdx
0x1800a11cd  mov     [rsp+360h+var_2E8], r13
0x1800a11d2  lea     r12d, [r13+58h]
0x1800a11d6  mov     [rbp+260h+var_2D8], r13
0x1800a11da  mov     r8d, r12d; Size
0x1800a11dd  lea     rcx, [rbp+260h+var_100]; void *
0x1800a11e4  xor     edx, edx; Val
0x1800a11e6  mov     r14d, r13d
0x1800a11e9  call    memset_0
0x1800a11ee  mov     r8d, r12d; Size
0x1800a11f1  lea     rcx, [rbp+260h+Uuid]; void *
0x1800a11f8  xor     edx, edx; Val
0x1800a11fa  call    memset_0
0x1800a11ff  xorps   xmm0, xmm0
0x1800a1202  mov     [rsp+360h+var_2F0], r13d
0x1800a1207  xor     eax, eax
0x1800a1209  mov     [rsp+360h+var_2F8], r13d
0x1800a120e  xor     edx, edx; Val
0x1800a1210  mov     [rbp+260h+var_250], eax
0x1800a1213  mov     r8d, 140h; Size
0x1800a1219  mov     [rsp+360h+var_2EC], r13d
0x1800a121e  lea     rcx, [rbp+260h+var_240]; void *
0x1800a1222  mov     [rbp+260h+hKey], r13
0x1800a1226  movups  [rbp+260h+var_270], xmm0
0x1800a122a  mov     r12d, r13d
0x1800a122d  movups  [rbp+260h+var_260], xmm0
0x1800a1231  movups  [rbp+260h+var_2C0], xmm0
0x1800a1235  movups  [rbp+260h+var_2B0], xmm0
0x1800a1239  movups  [rbp+260h+var_2A0], xmm0
0x1800a123d  call    memset_0
0x1800a1242  lea     rcx, aDwaddserverips_2
0x1800a1249  call    RasIpsecTrace
0x1800a124e  mov     edx, 118h; uBytes
0x1800a1253  lea     ecx, [r13+40h]; uFlags
0x1800a1257  call    cs:__imp_LocalAlloc
0x1800a125e  nop     dword ptr [rax+rax+00h]
0x1800a1263  mov     [rbp+260h+hMem], rax
0x1800a1267  lea     ecx, [r13+1]
0x1800a126b  test    rax, rax
0x1800a126e  jnz     loc_1800A1369
0x1800a1274  lea     rcx, aDwaddserverips_4
0x1800a127b  call    RasIpsecTrace
0x1800a1280  call    cs:__imp_GetLastError
0x1800a1287  nop     dword ptr [rax+rax+00h]
0x1800a128c  mov     ebx, eax
0x1800a128e  mov     rsi, [rsp+360h+var_308]
0x1800a1293  mov     r15, [rsp+360h+var_300]
0x1800a1298  test    r13, r13
0x1800a129b  jz      short loc_1800A12C2
0x1800a129d  mov     rcx, [r13+10h]; lpMem
0x1800a12a1  test    rcx, rcx
0x1800a12a4  jz      short loc_1800A12B3
0x1800a12a6  call    MprCommonFree
0x1800a12ab  mov     qword ptr [r13+10h], 0
0x1800a12b3  mov     rcx, r13; hMem
0x1800a12b6  call    cs:__imp_LocalFree
0x1800a12bd  nop     dword ptr [rax+rax+00h]
0x1800a12c2  mov     rax, [rbp+260h+var_2D8]
0x1800a12c6  test    rax, rax
0x1800a12c9  jz      short loc_1800A12D7
0x1800a12cb  mov     edx, [rsp+360h+var_2F8]
0x1800a12cf  mov     rcx, rax; hMem
0x1800a12d2  call    FreeIpsecOffers
0x1800a12d7  xor     edi, edi
0x1800a12d9  mov     rax, rdi
0x1800a12dc  lea     rdx, [rbp+260h+var_238]
0x1800a12e0  shl     rax, 4
0x1800a12e4  lea     rcx, [rbp+260h+var_240]
0x1800a12e8  add     rdx, rax
0x1800a12eb  add     rcx, rax
0x1800a12ee  call    WfpFilterListDestroy
0x1800a12f3  inc     rdi
0x1800a12f6  cmp     rdi, 14h
0x1800a12fa  jnz     short loc_1800A12D9
0x1800a12fc  mov     rax, [rbp+260h+hMem]
0x1800a1300  test    rax, rax
0x1800a1303  jz      short loc_1800A1314
0x1800a1305  mov     rcx, rax; hMem
0x1800a1308  call    cs:__imp_LocalFree
0x1800a130f  nop     dword ptr [rax+rax+00h]
0x1800a1314  test    r14, r14
0x1800a1317  jz      short loc_1800A132E
0x1800a1319  xor     r8d, r8d
0x1800a131c  mov     edx, r12d
0x1800a131f  cmp     r15, rsi
0x1800a1322  mov     rcx, r14; hMem
0x1800a1325  setnz   r8b
0x1800a1329  call    FreeAuthInfoList
0x1800a132e  mov     edx, ebx
0x1800a1330  lea     rcx, aDwaddserverips_3
0x1800a1337  call    RasIpsecTrace
0x1800a133c  mov     eax, ebx
0x1800a133e  mov     rcx, [rbp+260h+var_40]
0x1800a1345  xor     rcx, rsp; StackCookie
0x1800a1348  call    __security_check_cookie
0x1800a134d  mov     rbx, [rsp+360h+arg_18]
0x1800a1355  add     rsp, 330h
0x1800a135c  pop     r15
0x1800a135e  pop     r14
0x1800a1360  pop     r13
0x1800a1362  pop     r12
0x1800a1364  pop     rdi
0x1800a1365  pop     rsi
0x1800a1366  pop     rbp
0x1800a1367  retn
0x1800a1369  mov     [rsp+360h+dwDisposition], ecx
0x1800a136d  test    rbx, rbx
0x1800a1370  jnz     short loc_1800A1398
0x1800a1372  lea     r9, [rbp+260h+var_2D0]
0x1800a1376  mov     edx, 100h; int
0x1800a137b  lea     r8, [rsp+360h+var_310]; int
0x1800a1380  xor     ecx, ecx; int
0x1800a1382  call    DwGetPresharedKey
0x1800a1387  mov     rsi, [rbp+260h+var_2D0]
0x1800a138b  lea     ecx, [rbx+1]
0x1800a138e  mov     r15d, [rsp+360h+var_310]
0x1800a1393  mov     [rsp+360h+var_308], rsi
0x1800a1398  test    r15d, r15d
0x1800a139b  lea     r9, [rsp+360h+dwDisposition]
0x1800a13a0  lea     r8, [rsp+360h+var_310]
0x1800a13a5  cmovnz  r12d, ecx
0x1800a13a9  lea     rdx, [rsp+360h+var_2E8]
0x1800a13ae  mov     [rsp+360h+var_310], r12d
0x1800a13b3  call    GenerateCertificatesList
0x1800a13b8  mov     r12d, [rsp+360h+var_310]
0x1800a13bd  mov     ebx, eax
0x1800a13bf  mov     [rsp+360h+var_310], r12d
0x1800a13c4  test    r15d, r15d
0x1800a13c7  jnz     short loc_1800A1423
0x1800a13c9  mov     esi, [rsp+360h+dwDisposition]
0x1800a13cd  test    eax, eax
0x1800a13cf  jnz     short loc_1800A13E4
0x1800a13d1  test    r12d, r12d
0x1800a13d4  jz      short loc_1800A13E4
0x1800a13d6  test    esi, esi
0x1800a13d8  jnz     short loc_1800A13E4
0x1800a13da  mov     r14, [rsp+360h+var_2E8]
0x1800a13df  jmp     loc_1800A1497
0x1800a13e4  mov     r9d, esi
0x1800a13e7  lea     rcx, aPskNullFailedT
0x1800a13ee  mov     r8d, r12d
0x1800a13f1  mov     edx, eax
0x1800a13f3  call    RasIpsecTrace
0x1800a13f8  test    r12d, r12d
0x1800a13fb  jz      short loc_1800A1401
0x1800a13fd  test    esi, esi
0x1800a13ff  jz      short loc_1800A1406
0x1800a1401  mov     ebx, 2FEh
0x1800a1406  mov     r14, [rsp+360h+var_2E8]
0x1800a140b  test    r14, r14
0x1800a140e  jz      short loc_1800A145C
0x1800a1410  xor     r8d, r8d
0x1800a1413  mov     edx, r12d
0x1800a1416  mov     rcx, r14; hMem
0x1800a1419  call    FreeAuthInfoList
0x1800a141e  xor     r14d, r14d
0x1800a1421  jmp     short loc_1800A145C
0x1800a1423  mov     r14, [rsp+360h+var_2E8]
0x1800a1428  mov     eax, 1
0x1800a142d  test    r14, r14
0x1800a1430  jnz     short loc_1800A1482
0x1800a1432  lea     eax, [r14+40h]
0x1800a1436  mov     edx, eax; uBytes
0x1800a1438  mov     ecx, eax; uFlags
0x1800a143a  call    cs:__imp_LocalAlloc
0x1800a1441  nop     dword ptr [rax+rax+00h]
0x1800a1446  mov     r14, rax
0x1800a1449  test    rax, rax
0x1800a144c  jnz     short loc_1800A1480
0x1800a144e  call    cs:__imp_GetLastError
0x1800a1455  nop     dword ptr [rax+rax+00h]
0x1800a145a  mov     ebx, eax
0x1800a145c  test    ebx, ebx
0x1800a145e  jz      short loc_1800A1497
0x1800a1460  mov     r8d, r15d
0x1800a1463  lea     rcx, aDwaddserverips
0x1800a146a  mov     edx, ebx
0x1800a146c  call    RasIpsecTrace
0x1800a1471  mov     rsi, [rsp+360h+var_308]
0x1800a1476  mov     r15, [rsp+360h+var_300]
0x1800a147b  jmp     loc_1800A12C2
0x1800a1480  xor     eax, eax
0x1800a1482  lea     rax, [rax+rax*4]
0x1800a1486  add     rax, rax
0x1800a1489  mov     [r14+rax*8], r13d
0x1800a148d  mov     [r14+rax*8+10h], rsi
0x1800a1492  mov     [r14+rax*8+8], r15d
0x1800a1497  xor     r15d, r15d
0x1800a149a  lea     rax, [rsp+360h+dwDisposition]
0x1800a149f  mov     [rsp+360h+lpdwDisposition], rax; cbData
0x1800a14a4  lea     rdx, aSystemCurrentc_4
0x1800a14ab  lea     rax, [rbp+260h+hKey]
0x1800a14af  mov     [rsp+360h+dwDisposition], r15d
0x1800a14b4  mov     [rsp+360h+phkResult], rax; phkResult
0x1800a14b9  xor     r9d, r9d; lpClass
0x1800a14bc  mov     [rsp+360h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800a14c1  xor     r8d, r8d; Reserved
0x1800a14c4  mov     [rsp+360h+samDesired], 0F003Fh; Data
0x1800a14cc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a14d3  mov     [rsp+360h+dwOptions], r15d; dwOptions
0x1800a14d8  mov     ebx, 3D090h
0x1800a14dd  mov     esi, 0E10h
0x1800a14e2  call    cs:__imp_RegCreateKeyExW
0x1800a14e9  nop     dword ptr [rax+rax+00h]
0x1800a14ee  test    eax, eax
0x1800a14f0  jz      short loc_1800A153F
0x1800a14f2  mov     edx, eax
0x1800a14f4  lea     rcx, aDwaddserverips_1
0x1800a14fb  call    RasIpsecTrace
0x1800a1500  mov     [rsp+360h+var_318], r15d
0x1800a1505  lea     r8, [rsp+360h+var_2F8]
0x1800a150a  mov     [rsp+360h+lpdwDisposition], r15
0x1800a150f  lea     rdx, [rbp+260h+var_2D8]
0x1800a1513  mov     [rsp+360h+samDesired], esi
0x1800a1517  mov     ecx, edi
0x1800a1519  mov     [rsp+360h+dwOptions], ebx
0x1800a151d  call    BuildIpsecOffers
0x1800a1522  mov     ebx, eax
0x1800a1524  test    eax, eax
0x1800a1526  jz      loc_1800A1657
0x1800a152c  mov     edx, eax
0x1800a152e  lea     rcx, aDwaddserverips_7
0x1800a1535  call    RasIpsecTrace
0x1800a153a  jmp     loc_1800A128E
0x1800a153f  mov     edx, 20h ; ' '; uBytes
0x1800a1544  lea     ecx, [rdx+20h]; uFlags
0x1800a1547  call    cs:__imp_LocalAlloc
0x1800a154e  nop     dword ptr [rax+rax+00h]
0x1800a1553  mov     r13, rax
0x1800a1556  test    rax, rax
0x1800a1559  jnz     short loc_1800A1579
0x1800a155b  lea     rcx, aDwaddserverips_5
0x1800a1562  call    RasIpsecTrace
0x1800a1567  mov     rcx, [rbp+260h+hKey]; hKey
0x1800a156b  call    cs:__imp_RegCloseKey
0x1800a1572  nop     dword ptr [rax+rax+00h]
0x1800a1577  jmp     short loc_1800A1500
0x1800a1579  mov     rcx, [rbp+260h+hKey]; hKey
0x1800a157d  mov     r8, r13
0x1800a1580  call    GetL2tpConfigParams
0x1800a1585  mov     rcx, [rbp+260h+hKey]; hKey
0x1800a1589  mov     ebx, eax
0x1800a158b  call    cs:__imp_RegCloseKey
0x1800a1592  nop     dword ptr [rax+rax+00h]
0x1800a1597  test    ebx, ebx
0x1800a1599  jz      short loc_1800A15A9
0x1800a159b  mov     edx, ebx
0x1800a159d  lea     rcx, aDwaddserverips_6
0x1800a15a4  call    RasIpsecTrace
0x1800a15a9  mov     edi, [r13+4]
0x1800a15ad  mov     eax, edi
0x1800a15af  mov     esi, [r13+8]
0x1800a15b3  mov     ebx, [r13+0Ch]
0x1800a15b7  sub     eax, 1
0x1800a15ba  jz      short loc_1800A15C6
0x1800a15bc  cmp     eax, 1
0x1800a15bf  jnz     short loc_1800A15CB
0x1800a15c1  lea     edi, [rax+4]
0x1800a15c4  jmp     short loc_1800A15CB
0x1800a15c6  mov     edi, 4
0x1800a15cb  mov     rcx, [r13+10h]
0x1800a15cf  test    rcx, rcx
0x1800a15d2  jz      loc_1800A1500
0x1800a15d8  cmp     dword ptr [rcx+8], 9
0x1800a15dc  lea     rdx, __ImageBase
0x1800a15e3  mov     [rbp+260h+var_274], r15d
0x1800a15e7  jnb     short loc_1800A15FA
0x1800a15e9  mov     eax, [rcx+8]
0x1800a15ec  mov     rax, ds:rva qword_1800EE5F0[rdx+rax*8]
0x1800a15f4  mov     [rbp+260h+var_288], rax
0x1800a15f8  jmp     short loc_1800A15FE
0x1800a15fa  mov     [rbp+260h+var_288], r15
0x1800a15fe  cmp     dword ptr [rcx+0Ch], 6
0x1800a1602  jnb     short loc_1800A1615
0x1800a1604  mov     eax, [rcx+0Ch]
0x1800a1607  mov     rax, ds:rva off_1800EE638[rdx+rax*8]
0x1800a160f  mov     [rbp+260h+var_280], rax
0x1800a1613  jmp     short loc_1800A1619
0x1800a1615  mov     [rbp+260h+var_280], r15
  ... truncated ...
```
