# DwAddServerIpSecFilter

- ea: `0x18007eb50`
- end: `0x18007f8af`
- name: `DwAddServerIpSecFilter`
- size: `3423`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800150b8`

## callees

- `0x18007339c`
- `0x180073634`
- `0x18007374c`
- `0x18007d7f0`
- `0x18007dc40`
- `0x18007dcfc`
- `0x18007dedc`
- `0x18007e164`
- `0x18007e220`
- `0x18007e30c`
- `0x18007eb50`
- `0x18007fe84`
- `0x180080264`
- `0x1800803a8`
- `0x1800804dc`
- `0x1800805f8`
- `0x180080ab4`
- `0x180081078`
- `0x18008a780`
- `0x18008b464`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18007f7ef`
- `KERNEL32!LocalFree` at `0x18007f823`
- `KERNEL32!LocalFree` at `0x18007f85a`
- `KERNEL32!LocalFree` at `0x18007f7ef`
- `KERNEL32!LocalFree` at `0x18007f823`
- `KERNEL32!LocalFree` at `0x18007f85a`
- `KERNEL32!GetLastError` at `0x18007ec33`
- `KERNEL32!GetLastError` at `0x18007ed38`
- `KERNEL32!GetLastError` at `0x18007ec33`
- `KERNEL32!GetLastError` at `0x18007ed38`
- `KERNEL32!LocalAlloc` at `0x18007ec18`
- `KERNEL32!LocalAlloc` at `0x18007ed2a`
- `KERNEL32!LocalAlloc` at `0x18007edc4`
- `KERNEL32!LocalAlloc` at `0x18007ec18`
- `KERNEL32!LocalAlloc` at `0x18007ed2a`
- `KERNEL32!LocalAlloc` at `0x18007edc4`
- `ADVAPI32!RegCloseKey` at `0x18007ede2`
- `ADVAPI32!RegCloseKey` at `0x18007ee04`
- `ADVAPI32!RegCloseKey` at `0x18007ede2`
- `ADVAPI32!RegCloseKey` at `0x18007ee04`
- `RPCRT4!UuidCreate` at `0x18007ef8b`
- `RPCRT4!UuidCreate` at `0x18007efa7`
- `RPCRT4!UuidCreate` at `0x18007ef8b`
- `RPCRT4!UuidCreate` at `0x18007efa7`
- `fwpuclnt!FwpmTransactionCommit0` at `0x18007f31d`
- `fwpuclnt!FwpmTransactionCommit0` at `0x18007f78d`
- `fwpuclnt!FwpmTransactionCommit0` at `0x18007f31d`
- `fwpuclnt!FwpmTransactionCommit0` at `0x18007f78d`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x18007f02f`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x18007f02f`
- `fwpuclnt!FwpmTransactionAbort0` at `0x18007f77e`
- `fwpuclnt!FwpmTransactionAbort0` at `0x18007f77e`
- `fwpuclnt!FwpmProviderContextAdd2` at `0x18007f003`
- `fwpuclnt!FwpmProviderContextAdd2` at `0x18007f003`

## string_xrefs

- `0x18007ed7a`: `DwAddServerIpSecFilter:OpenIkev2ConfigKey: Failed. error %d`
- `0x18007ee10`: `DwAddServerIpSecFilter:GetIkev2ConfigParams: Failed. error %d`
- `0x18007ef97`: `DwAddServerIpsecFilter: UuidCreate failed with 0x%x`

## pseudocode

```c
__int64 __fastcall DwAddServerIpSecFilter(unsigned int a1)
{
  _DWORD *v2; // r15
  char *v3; // rsi
  _DWORD *v4; // r13
  DWORD LastError; // ebx
  int v6; // r14d
  DWORD v7; // eax
  __int64 v8; // rcx
  int v9; // r12d
  int v10; // esi
  __int64 v11; // rax
  __int64 v12; // rax
  DWORD v13; // eax
  int L2tpConfigParams; // ebx
  int v15; // esi
  int v16; // ebx
  _DWORD *v17; // rcx
  bool v18; // cf
  HLOCAL v19; // rbx
  const CHAR *v20; // rcx
  const CHAR *v21; // rcx
  __int64 v22; // rdx
  unsigned int v23; // edi
  unsigned int v24; // edi
  unsigned int v25; // edi
  unsigned int v26; // edi
  int v27; // edx
  int v28; // edx
  int v29; // edx
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rdi
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rdx
  __int64 v37; // r8
  int v38; // edx
  int v39; // edx
  int v40; // edx
  int v41; // edx
  __int64 v42; // rdi
  void *v43; // rcx
  unsigned int v44; // r14d
  unsigned int i; // edi
  __int64 j; // rdi
  int v48; // [rsp+20h] [rbp-E0h]
  BYTE cbData; // [rsp+28h] [rbp-D8h]
  DWORD cbDataa; // [rsp+28h] [rbp-D8h]
  DWORD cbDatab; // [rsp+28h] [rbp-D8h]
  DWORD cbDatac; // [rsp+28h] [rbp-D8h]
  DWORD cbDatad; // [rsp+28h] [rbp-D8h]
  DWORD cbDatae; // [rsp+28h] [rbp-D8h]
  DWORD cbDataf; // [rsp+28h] [rbp-D8h]
  DWORD cbDatag; // [rsp+28h] [rbp-D8h]
  DWORD cbDatah; // [rsp+28h] [rbp-D8h]
  DWORD v58; // [rsp+40h] [rbp-C0h]
  int v59[4]; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-A0h] BYREF
  int v61; // [rsp+68h] [rbp-98h] BYREF
  __int64 v62; // [rsp+70h] [rbp-90h]
  int v63; // [rsp+78h] [rbp-88h] BYREF
  int v64; // [rsp+7Ch] [rbp-84h] BYREF
  int v65; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL v66; // [rsp+88h] [rbp-78h] BYREF
  HKEY hKey[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v68; // [rsp+A0h] [rbp-60h]
  HLOCAL v69; // [rsp+B0h] [rbp-50h]
  __int128 v70; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v71; // [rsp+C8h] [rbp-38h]
  __int128 v72; // [rsp+D8h] [rbp-28h]
  __int64 v73; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v74; // [rsp+F0h] [rbp-10h]
  __int64 *v75; // [rsp+F8h] [rbp-8h]
  int v76; // [rsp+100h] [rbp+0h]
  int v77; // [rsp+104h] [rbp+4h]
  __int128 v78; // [rsp+108h] [rbp+8h] BYREF
  __int128 v79; // [rsp+118h] [rbp+18h]
  int v80; // [rsp+128h] [rbp+28h]
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
  _BYTE v100[16]; // [rsp+260h] [rbp+160h] BYREF
  UUID v101; // [rsp+270h] [rbp+170h] BYREF
  const wchar_t *v102; // [rsp+280h] [rbp+180h]
  int v103; // [rsp+2B0h] [rbp+1B0h]
  __int128 *v104; // [rsp+2B8h] [rbp+1B8h]
  FWPM_PROVIDER_CONTEXT0 Uuid; // [rsp+2D0h] [rbp+1D0h] BYREF

  v59[0] = 0;
  v62 = 0;
  v68 = 0;
  v2 = 0;
  v66 = 0;
  hMem = 0;
  v3 = 0;
  memset_0(&v101, 0, 0x58u);
  memset_0(&Uuid, 0, sizeof(Uuid));
  v64 = 0;
  v61 = 0;
  v80 = 0;
  v65 = 0;
  hKey[0] = 0;
  v78 = 0;
  v4 = 0;
  v79 = 0;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  memset_0(v81, 0, 0x140u);
  RasIpsecTrace("DwAddServerIpSecFilter");
  v69 = LocalAlloc(0x40u, 0x118u);
  if ( !v69 )
  {
    RasIpsecTrace("DwAddServerIpsecFilter: failed to alloc");
    LastError = GetLastError();
    goto LABEL_135;
  }
  v63 = 1;
  DwGetPresharedKey(0, 256, (int)v59);
  v6 = v59[0];
  v59[0] = v59[0] != 0;
  v7 = GenerateCertificatesList(1, &v66, v59, &v63);
  v9 = v59[0];
  LastError = v7;
  v62 = v68;
  if ( !v6 )
  {
    v10 = v63;
    if ( !v7 && v59[0] && !v63 )
    {
      v2 = v66;
      goto LABEL_21;
    }
    RasIpsecTrace("PSK=NULL. Failed to generate certificate list. rc=0x%x, Count=%d, MyStoreEmpty=%d");
    if ( !v9 || v10 )
      LastError = 766;
    v2 = v66;
    if ( v66 )
    {
      FreeAuthInfoList(v66);
      v2 = 0;
    }
    v3 = (char *)hMem;
    goto LABEL_14;
  }
  v11 = 1;
  v2 = v66;
  if ( v66 )
  {
LABEL_20:
    v8 = v62;
    v12 = 10 * v11;
    v2[2 * v12] = 0;
    *(_QWORD *)&v2[2 * v12 + 4] = v8;
    v2[2 * v12 + 2] = v6;
    goto LABEL_21;
  }
  v2 = LocalAlloc(0x40u, 0x40u);
  if ( v2 )
  {
    v11 = 0;
    goto LABEL_20;
  }
  LastError = GetLastError();
LABEL_14:
  if ( LastError )
  {
    RasIpsecTrace("DwAddServerIpsecFilter: DwGetMMAuthMethodsForServer returned %d. PSK length is %d");
    goto LABEL_139;
  }
LABEL_21:
  if ( (unsigned int)OpenL2tpConfigKey(v8, hKey) )
  {
    RasIpsecTrace("DwAddServerIpSecFilter:OpenIkev2ConfigKey: Failed. error %d");
LABEL_23:
    v13 = BuildIpsecOffers(a1, &hMem, &v61);
    goto LABEL_24;
  }
  v4 = LocalAlloc(0x40u, 0x20u);
  if ( !v4 )
  {
    RasIpsecTrace("DwAddServerIpSecFilter: Memory allocation failed");
    RegCloseKey(hKey[0]);
    goto LABEL_23;
  }
  L2tpConfigParams = GetL2tpConfigParams(hKey[0]);
  RegCloseKey(hKey[0]);
  if ( L2tpConfigParams )
    RasIpsecTrace("DwAddServerIpSecFilter:GetIkev2ConfigParams: Failed. error %d");
  a1 = v4[1];
  v15 = v4[2];
  v16 = v4[3];
  if ( a1 == 1 )
  {
    a1 = 4;
  }
  else if ( v4[1] == 2 )
  {
    a1 = 5;
  }
  v17 = (_DWORD *)*((_QWORD *)v4 + 2);
  if ( !v17 )
    goto LABEL_23;
  v18 = v17[2] < 9u;
  v77 = 0;
  if ( v18 )
    v74 = qword_18008FD40[v17[2]];
  else
    v74 = 0;
  if ( v17[3] >= 6u )
    v75 = 0;
  else
    v75 = off_18008FD10[v17[3]];
  v18 = v17[4] < 8u;
  v73 = 0;
  v76 = v18 ? v17[4] : 0;
  v13 = BuildCustomEncryption((int)&hMem, (int)&v61, 0, v16, v15, cbData, (__int64)&v73, 1, v58);
LABEL_24:
  LastError = v13;
  if ( !v13 )
  {
    v3 = (char *)hMem;
    BuildQMPolicy((unsigned int)&Uuid, (unsigned int)&v78, a1, (_DWORD)hMem, v61, 0);
    if ( v4 )
      DWORD2(v79) = *v4;
    v19 = v69;
    BuildMMOffers((int)v69, (int)&v65, (int)&v64, 1, v48, cbDataa, (__int64)v4);
    v72 = (unsigned int)v64;
    LODWORD(v71) = 0;
    LODWORD(v70) = 28800;
    *((_QWORD *)&v71 + 1) = v19;
    DWORD1(v71) = v65;
    *((_QWORD *)&v70 + 1) = v2;
    DWORD1(v70) = v9;
    memset_0(&v101, 0, 0x58u);
    v103 = 5;
    v104 = &v70;
    v102 = L"L2TP Main Mode Policy";
    LastError = UuidCreate(&Uuid.providerContextKey);
    if ( LastError || (LastError = UuidCreate(&v101)) != 0 )
    {
      v20 = "DwAddServerIpsecFilter: UuidCreate failed with 0x%x";
LABEL_49:
      RasIpsecTrace(v20);
      goto LABEL_135;
    }
    gServerMMPolicyGuid = v101;
    gServerQMPolicyGuid = Uuid.providerContextKey;
    LastError = FwpmTransactionBegin0Wrapper();
    if ( LastError )
    {
      v20 = "FwpmTransactionBegin0 failed with 0x%x";
      goto LABEL_49;
    }
    LastError = FwpmProviderContextAdd2(gFwpEngineHandle, &v101, 0, 0);
    if ( LastError )
    {
      v21 = "FwpmProviderContextAdd0 for MM policy failed with 0x%x";
LABEL_130:
      RasIpsecTrace(v21);
      FwpmTransactionAbort0(gFwpEngineHandle);
      goto LABEL_135;
    }
    LastError = FwpmProviderContextAdd0(gFwpEngineHandle, &Uuid, 0, 0);
    if ( LastError )
    {
      v21 = "FwpmProviderContextAdd0 for QM policy failed with 0x%x";
      goto LABEL_130;
    }
    if ( a1 )
    {
      v23 = a1 - 1;
      if ( v23 )
      {
        v24 = v23 - 1;
        if ( !v24 || (v25 = v24 - 1) == 0 )
        {
LABEL_60:
          LastError = BuildOutTxFilter((unsigned int)v92, v22, 1, 1, 1);
          if ( LastError )
          {
LABEL_61:
            v21 = "BuildOutTxFilter for QM policy failed with 0x%x  Ipv6: TRUE";
            goto LABEL_130;
          }
          LastError = BuildOutTxFilter((unsigned int)v91, v27, 1, 1, 0);
          if ( LastError )
          {
LABEL_63:
            v21 = "BuildOutTxFilter for QM policy failed with 0x%x  Ipv6: FALSE";
            goto LABEL_130;
          }
          LastError = AddFilters(v92, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
            goto LABEL_65;
          LastError = AddFilters(v91, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
          {
LABEL_67:
            v21 = "AddFilters for QM policy failed with 0x%x  Ipv6: FALSE";
            goto LABEL_129;
          }
          LastError = BuildOutTxFilter((unsigned int)v96, v28, 1, 0, 1);
          if ( LastError )
          {
LABEL_69:
            v21 = "BuildOutTxFilter for QM policy failed with 0x%x  Ipv6: TRUE";
            goto LABEL_129;
          }
          LastError = BuildOutTxFilter((unsigned int)v95, v29, 1, 0, 0);
          if ( LastError )
          {
            v21 = "BuildOutTxFilter for QM policy failed with 0x%x  Ipv6: FALSE";
            goto LABEL_129;
          }
          LastError = AddFilters(v96, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
            goto LABEL_65;
          LastError = AddFilters(v95, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
            goto LABEL_67;
          LastError = BuildInTxFilter((unsigned int)v94, 1, 0, 1701, (__int64)L"L2TP Server Filter1", cbDatab, 1);
          if ( LastError )
          {
LABEL_75:
            v21 = "BuildInTxFilter for QM policy failed with 0x%x  Ipv6: TRUE";
            goto LABEL_129;
          }
          LastError = BuildInTxFilter((unsigned int)v93, 1, 0, 1701, (__int64)L"L2TP Server Filter1", cbDatac, 0);
          if ( LastError )
          {
LABEL_77:
            v21 = "BuildInTxFilter for QM policy failed with 0x%x  Ipv6: FALSE";
            goto LABEL_129;
          }
          LastError = AddFilters(v94, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
          {
LABEL_79:
            v21 = "AddFilters for QM policy failed with 0x%x  Ipv6: TRUE";
            goto LABEL_129;
          }
          LastError = AddFilters(v93, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
          {
LABEL_81:
            v21 = "AddFilters for QM policy failed with 0x%x  Ipv6: FALSE";
            goto LABEL_129;
          }
          LastError = BuildOutMMFilter(v98, v30, L"L2TP Server Inbound and Outbound Filter", 1);
          if ( LastError )
          {
            v21 = "BuildOutMMFilter for MM policy failed with 0x%x  Ipv6: TRUE";
            goto LABEL_129;
          }
          LastError = BuildOutMMFilter(v97, v31, L"L2TP Server Inbound and Outbound Filter", 0);
          if ( LastError )
          {
            v21 = "BuildOutMMFilter for MM policy failed with 0x%x  Ipv6: FALSE";
            goto LABEL_129;
          }
          LastError = AddFilters(v98, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
          {
LABEL_87:
            v21 = "AddFilters for MM policy failed with 0x%x  Ipv6: TRUE";
            goto LABEL_129;
          }
          LastError = AddFilters(v97, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( !LastError )
          {
            LastError = FwpmTransactionCommit0(gFwpEngineHandle);
            if ( v2 )
            {
              v32 = v62;
              FreeAuthInfoList(v2);
              v3 = (char *)hMem;
              v2 = 0;
              if ( v32 )
                v62 = 0;
              goto LABEL_135;
            }
            goto LABEL_134;
          }
LABEL_128:
          v21 = "AddFilters for MM policy failed with 0x%x  Ipv6: FALSE";
          goto LABEL_129;
        }
        v26 = v25 - 1;
        if ( v26 )
        {
          if ( v26 != 1 )
            goto LABEL_135;
          goto LABEL_60;
        }
      }
    }
    LastError = BuildOutMMFilter(v98, v22, L"L2TP Server Outbound Filter", 1);
    if ( LastError )
    {
      v21 = "BuildOutMMFilter for MM policy failed with 0x%x  IPv6: TRUE";
      goto LABEL_130;
    }
    LastError = BuildOutMMFilter(v97, v33, L"L2TP Server Outbound Filter", 0);
    if ( LastError )
    {
      v21 = "BuildOutMMFilter for MM policy failed with 0x%x  IPv6: FALSE";
      goto LABEL_130;
    }
    LastError = BuildInMMFilter(v100, v34, v35, 1);
    if ( LastError )
    {
      v21 = "BuildInMMFilter for MM policy failed with 0x%x  IPv6: TRUE";
      goto LABEL_130;
    }
    LastError = BuildInMMFilter(v99, v36, v37, 0);
    if ( LastError )
    {
      v21 = "BuildInMMFilter for MM policy failed with 0x%x  IPv6: FALSE";
      goto LABEL_130;
    }
    LastError = BuildOutTxFilter((unsigned int)v82, v38, 0, 1, 1);
    if ( LastError )
      goto LABEL_61;
    LastError = BuildOutTxFilter((unsigned int)v81, v39, 0, 1, 0);
    if ( LastError )
      goto LABEL_63;
    LastError = AddFilters(v82, gServerFilterIds, &gNumServerFilterIds, 0);
    if ( !LastError )
    {
      LastError = AddFilters(v81, gServerFilterIds, &gNumServerFilterIds, 0);
      if ( LastError )
        goto LABEL_67;
      LastError = BuildOutTxFilter((unsigned int)v84, v40, 0, 0, 1);
      if ( LastError )
        goto LABEL_69;
      LastError = BuildOutTxFilter((unsigned int)v83, v41, 0, 0, 0);
      if ( LastError )
      {
        v21 = "BuildOutTxFilter for QM policy failed with 0x%x";
        goto LABEL_129;
      }
      LastError = AddFilters(v84, gServerFilterIds, &gNumServerFilterIds, 0);
      if ( LastError )
        goto LABEL_65;
      LastError = AddFilters(v83, gServerFilterIds, &gNumServerFilterIds, 0);
      if ( LastError )
        goto LABEL_67;
      LastError = BuildInTxFilter((unsigned int)v86, 0, 1701, 0, (__int64)L"L2TP Server Inbound Filter", cbDatab, 1);
      if ( LastError )
      {
LABEL_110:
        v21 = "BuildInTxFilter for QM policy failed with 0x%x  Ipv6: TRUE";
        goto LABEL_129;
      }
      LastError = BuildInTxFilter((unsigned int)v85, 0, 1701, 0, (__int64)L"L2TP Server Inbound Filter", cbDatad, 0);
      if ( LastError )
      {
LABEL_112:
        v21 = "BuildInTxFilter for QM policy failed with 0x%x  Ipv6: FALSE";
        goto LABEL_129;
      }
      LastError = AddFilters(v86, gServerFilterIds, &gNumServerFilterIds, 0);
      if ( !LastError )
      {
        LastError = AddFilters(v85, gServerFilterIds, &gNumServerFilterIds, 0);
        if ( LastError )
          goto LABEL_67;
        LastError = BuildInTxFilter(
                      (unsigned int)v88,
                      0,
                      1701,
                      1701,
                      (__int64)L"L2TP Server Inbound Filter",
                      cbDatae,
                      1);
        if ( LastError )
          goto LABEL_110;
        LastError = BuildInTxFilter(
                      (unsigned int)v87,
                      0,
                      1701,
                      1701,
                      (__int64)L"L2TP Server Inbound Filter",
                      cbDataf,
                      0);
        if ( LastError )
          goto LABEL_112;
        LastError = AddFilters(v88, gServerFilterIds, &gNumServerFilterIds, 0);
        if ( !LastError )
        {
          LastError = AddFilters(v87, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
            goto LABEL_67;
          LastError = BuildInTxFilter((unsigned int)v90, 1, 0, 1701, (__int64)L"L2TP Server Filter1", cbDatag, 1);
          if ( LastError )
            goto LABEL_75;
          LastError = BuildInTxFilter((unsigned int)v89, 1, 0, 1701, (__int64)L"L2TP Server Filter1", cbDatah, 0);
          if ( LastError )
            goto LABEL_77;
          LastError = AddFilters(v90, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
            goto LABEL_79;
          LastError = AddFilters(v89, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
            goto LABEL_81;
          LastError = AddFilters(v98, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
            goto LABEL_87;
          LastError = AddFilters(v97, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( !LastError )
          {
            LastError = AddFilters(v100, gServerFilterIds, &gNumServerFilterIds, 0);
            if ( LastError )
            {
              v21 = "AddFilters for MM policy failed with 0x%x  Ipv6:  TRUE";
              goto LABEL_129;
            }
            LastError = AddFilters(v99, gServerFilterIds, &gNumServerFilterIds, 0);
            if ( !LastError )
            {
              LastError = FwpmTransactionCommit0(gFwpEngineHandle);
              if ( v2 )
              {
                v42 = v62;
                FreeAuthInfoList(v2);
                v2 = 0;
                if ( v42 )
                  v62 = 0;
              }
              goto LABEL_134;
            }
          }
          goto LABEL_128;
        }
      }
    }
LABEL_65:
    v21 = "AddFilters for QM policy failed with 0x%x  Ipv6: TRUE";
LABEL_129:
    v3 = (char *)hMem;
    goto LABEL_130;
  }
  RasIpsecTrace("DwAddServerIpsecFilter: BuildIpsecOffers returned %d");
LABEL_134:
  v3 = (char *)hMem;
LABEL_135:
  if ( v4 )
  {
    v43 = (void *)*((_QWORD *)v4 + 2);
    if ( v43 )
    {
      MprCommonFree(v43);
      *((_QWORD *)v4 + 2) = 0;
    }
    LocalFree(v4);
  }
LABEL_139:
  if ( v3 )
  {
    v44 = v61;
    for ( i = 0; i < v44; ++i )
      WfpClearIpsecProposal(&v3[32 * i]);
    LocalFree(v3);
  }
  for ( j = 0; j != 20; ++j )
    WfpFilterListDestroy(&v81[16 * j], &v81[16 * j + 8]);
  if ( v69 )
    LocalFree(v69);
  if ( v2 )
    FreeAuthInfoList(v2);
  RasIpsecTrace("DwAddServerIpSecFilter, rc=0x%x");
  return LastError;
}

```

## disassembly

```asm
0x18007eb50  push    rbp
0x18007eb52  push    rbx
0x18007eb53  push    rsi
0x18007eb54  push    rdi
0x18007eb55  push    r12
0x18007eb57  push    r13
0x18007eb59  push    r14
0x18007eb5b  push    r15
0x18007eb5d  lea     rbp, [rsp-248h]
0x18007eb65  sub     rsp, 348h
0x18007eb6c  mov     rax, cs:__security_cookie
0x18007eb73  xor     rax, rsp
0x18007eb76  mov     [rbp+280h+var_50], rax
0x18007eb7d  xor     ebx, ebx
0x18007eb7f  mov     edi, ecx
0x18007eb81  xor     edx, edx; Val
0x18007eb83  mov     [rsp+380h+var_330], ebx
0x18007eb87  lea     rcx, [rbp+280h+var_110]; void *
0x18007eb8e  mov     [rsp+380h+var_310], rbx
0x18007eb93  mov     [rbp+280h+var_2E0], rbx
0x18007eb97  mov     r15d, ebx
0x18007eb9a  lea     r14d, [rbx+58h]
0x18007eb9e  mov     [rbp+280h+var_2F8], rbx
0x18007eba2  mov     r8d, r14d; Size
0x18007eba5  mov     [rsp+380h+hMem], rbx
0x18007ebaa  mov     esi, ebx
0x18007ebac  call    memset_0
0x18007ebb1  mov     r8d, r14d; Size
0x18007ebb4  lea     rcx, [rbp+280h+Uuid]; void *
0x18007ebbb  xor     edx, edx; Val
0x18007ebbd  call    memset_0
0x18007ebc2  xorps   xmm0, xmm0
0x18007ebc5  mov     [rsp+380h+var_304], ebx
0x18007ebc9  xor     eax, eax
0x18007ebcb  mov     [rsp+380h+var_318], ebx
0x18007ebcf  xor     edx, edx; Val
0x18007ebd1  mov     [rbp+280h+var_258], eax
0x18007ebd4  mov     r8d, 140h; Size
0x18007ebda  mov     [rbp+280h+var_300], ebx
0x18007ebdd  lea     rcx, [rbp+280h+var_250]; void *
0x18007ebe1  mov     [rbp+280h+hKey], rbx
0x18007ebe5  movups  [rbp+280h+var_278], xmm0
0x18007ebe9  mov     r12d, ebx
0x18007ebec  mov     r13d, ebx
0x18007ebef  movups  [rbp+280h+var_268], xmm0
0x18007ebf3  movups  [rbp+280h+var_2C8], xmm0
0x18007ebf7  movups  [rbp+280h+var_2B8], xmm0
0x18007ebfb  movups  [rbp+280h+var_2A8], xmm0
0x18007ebff  call    memset_0
0x18007ec04  lea     rcx, aDwaddserverips_2; "DwAddServerIpSecFilter"
0x18007ec0b  call    RasIpsecTrace
0x18007ec10  mov     edx, 118h; uBytes
0x18007ec15  lea     ecx, [rbx+40h]; uFlags
0x18007ec18  call    cs:__imp_LocalAlloc
0x18007ec1e  mov     [rbp+280h+var_2D0], rax
0x18007ec22  test    rax, rax
0x18007ec25  jnz     short loc_18007EC40
0x18007ec27  lea     rcx, aDwaddserverips_4; "DwAddServerIpsecFilter: failed to alloc"
0x18007ec2e  call    RasIpsecTrace
0x18007ec33  call    cs:__imp_GetLastError
0x18007ec39  mov     ebx, eax
0x18007ec3b  jmp     loc_18007F7D1
0x18007ec40  mov     r15d, 1
0x18007ec46  lea     r9, [rbp+280h+var_2E0]
0x18007ec4a  lea     r8, [rsp+380h+var_330]; int
0x18007ec4f  mov     [rsp+380h+var_308], r15d
0x18007ec54  mov     edx, 100h; int
0x18007ec59  xor     ecx, ecx; int
0x18007ec5b  call    DwGetPresharedKey
0x18007ec60  mov     r14d, [rsp+380h+var_330]
0x18007ec65  lea     r9, [rsp+380h+var_308]
0x18007ec6a  test    r14d, r14d
0x18007ec6d  lea     r8, [rsp+380h+var_330]
0x18007ec72  lea     rdx, [rbp+280h+var_2F8]
0x18007ec76  mov     ecx, r15d
0x18007ec79  cmovnz  r12d, r15d
0x18007ec7d  mov     [rsp+380h+var_330], r12d
0x18007ec82  call    GenerateCertificatesList
0x18007ec87  mov     r12d, [rsp+380h+var_330]
0x18007ec8c  mov     ebx, eax
0x18007ec8e  mov     rax, [rbp+280h+var_2E0]
0x18007ec92  mov     [rsp+380h+var_310], rax
0x18007ec97  mov     [rsp+380h+var_330], r12d
0x18007ec9c  test    r14d, r14d
0x18007ec9f  jnz     short loc_18007ED16
0x18007eca1  mov     esi, [rsp+380h+var_308]
0x18007eca5  test    ebx, ebx
0x18007eca7  jnz     short loc_18007ECBB
0x18007eca9  test    r12d, r12d
0x18007ecac  jz      short loc_18007ECBB
0x18007ecae  test    esi, esi
0x18007ecb0  jnz     short loc_18007ECBB
0x18007ecb2  mov     r15, [rbp+280h+var_2F8]
0x18007ecb6  jmp     loc_18007ED5E
0x18007ecbb  mov     r9d, esi
0x18007ecbe  lea     rcx, aPskNullFailedT; "PSK=NULL. Failed to generate certificat"...
0x18007ecc5  mov     r8d, r12d
0x18007ecc8  mov     edx, ebx
0x18007ecca  call    RasIpsecTrace
0x18007eccf  test    r12d, r12d
0x18007ecd2  jz      short loc_18007ECD8
0x18007ecd4  test    esi, esi
0x18007ecd6  jz      short loc_18007ECDD
0x18007ecd8  mov     ebx, 2FEh
0x18007ecdd  mov     r15, [rbp+280h+var_2F8]
0x18007ece1  test    r15, r15
0x18007ece4  jz      short loc_18007ECF7
0x18007ece6  xor     r8d, r8d
0x18007ece9  mov     edx, r12d
0x18007ecec  mov     rcx, r15; hMem
0x18007ecef  call    FreeAuthInfoList
0x18007ecf4  xor     r15d, r15d
0x18007ecf7  mov     rsi, [rsp+380h+hMem]
0x18007ecfc  test    ebx, ebx
0x18007ecfe  jz      short loc_18007ED5E
0x18007ed00  mov     r8d, r14d
0x18007ed03  lea     rcx, aDwaddserverips; "DwAddServerIpsecFilter: DwGetMMAuthMeth"...
0x18007ed0a  mov     edx, ebx
0x18007ed0c  call    RasIpsecTrace
0x18007ed11  jmp     loc_18007F7F5
0x18007ed16  mov     rax, r15
0x18007ed19  mov     r15, [rbp+280h+var_2F8]
0x18007ed1d  test    r15, r15
0x18007ed20  jnz     short loc_18007ED44
0x18007ed22  lea     eax, [r15+40h]
0x18007ed26  mov     edx, eax; uBytes
0x18007ed28  mov     ecx, eax; uFlags
0x18007ed2a  call    cs:__imp_LocalAlloc
0x18007ed30  mov     r15, rax
0x18007ed33  test    rax, rax
0x18007ed36  jnz     short loc_18007ED42
0x18007ed38  call    cs:__imp_GetLastError
0x18007ed3e  mov     ebx, eax
0x18007ed40  jmp     short loc_18007ECFC
0x18007ed42  xor     eax, eax
0x18007ed44  mov     rcx, [rsp+380h+var_310]
0x18007ed49  lea     rax, [rax+rax*4]
0x18007ed4d  add     rax, rax
0x18007ed50  mov     [r15+rax*8], esi
0x18007ed54  mov     [r15+rax*8+10h], rcx
0x18007ed59  mov     [r15+rax*8+8], r14d
0x18007ed5e  lea     rdx, [rbp+280h+hKey]
0x18007ed62  mov     ebx, 3D090h
0x18007ed67  mov     esi, 0E10h
0x18007ed6c  call    OpenL2tpConfigKey
0x18007ed71  xor     r14d, r14d
0x18007ed74  test    eax, eax
0x18007ed76  jz      short loc_18007EDBC
0x18007ed78  mov     edx, eax
0x18007ed7a  lea     rcx, aDwaddserverips_1; "DwAddServerIpSecFilter:OpenIkev2ConfigK"...
0x18007ed81  call    RasIpsecTrace
0x18007ed86  mov     [rsp+380h+cbData], esi
0x18007ed8a  lea     r8, [rsp+380h+var_318]
0x18007ed8f  lea     rdx, [rsp+380h+hMem]
0x18007ed94  mov     [rsp+380h+var_360], ebx
0x18007ed98  mov     ecx, edi
0x18007ed9a  call    BuildIpsecOffers
0x18007ed9f  mov     ebx, eax
0x18007eda1  test    eax, eax
0x18007eda3  jz      loc_18007EECB
0x18007eda9  mov     edx, eax
0x18007edab  lea     rcx, aDwaddserverips_7; "DwAddServerIpsecFilter: BuildIpsecOffer"...
0x18007edb2  call    RasIpsecTrace
0x18007edb7  jmp     loc_18007F7CC
0x18007edbc  mov     edx, 20h ; ' '; uBytes
0x18007edc1  lea     ecx, [rdx+20h]; uFlags
0x18007edc4  call    cs:__imp_LocalAlloc
0x18007edca  mov     r13, rax
0x18007edcd  test    rax, rax
0x18007edd0  jnz     short loc_18007EDEA
0x18007edd2  lea     rcx, aDwaddserverips_5; "DwAddServerIpSecFilter: Memory allocati"...
0x18007edd9  call    RasIpsecTrace
0x18007edde  mov     rcx, [rbp+280h+hKey]; hKey
0x18007ede2  call    cs:__imp_RegCloseKey
0x18007ede8  jmp     short loc_18007ED86
0x18007edea  mov     rcx, [rbp+280h+hKey]; hKey
0x18007edee  mov     r9d, 20h ; ' '
0x18007edf4  mov     r8, r13
0x18007edf7  mov     dl, 5
0x18007edf9  call    GetL2tpConfigParams
0x18007edfe  mov     rcx, [rbp+280h+hKey]; hKey
0x18007ee02  mov     ebx, eax
0x18007ee04  call    cs:__imp_RegCloseKey
0x18007ee0a  test    ebx, ebx
0x18007ee0c  jz      short loc_18007EE1C
0x18007ee0e  mov     edx, ebx
0x18007ee10  lea     rcx, aDwaddserverips_6; "DwAddServerIpSecFilter:GetIkev2ConfigPa"...
0x18007ee17  call    RasIpsecTrace
0x18007ee1c  mov     edi, [r13+4]
0x18007ee20  mov     eax, edi
0x18007ee22  mov     esi, [r13+8]
0x18007ee26  mov     ebx, [r13+0Ch]
0x18007ee2a  sub     eax, 1
0x18007ee2d  jz      short loc_18007EE39
0x18007ee2f  cmp     eax, 1
0x18007ee32  jnz     short loc_18007EE3E
0x18007ee34  lea     edi, [rax+4]
0x18007ee37  jmp     short loc_18007EE3E
0x18007ee39  mov     edi, 4
0x18007ee3e  mov     rcx, [r13+10h]
0x18007ee42  test    rcx, rcx
0x18007ee45  jz      loc_18007ED86
0x18007ee4b  cmp     dword ptr [rcx+8], 9
0x18007ee4f  lea     rdx, cs:180000000h
0x18007ee56  mov     [rbp+280h+var_27C], r14d
0x18007ee5a  jnb     short loc_18007EE6D
0x18007ee5c  mov     eax, [rcx+8]
0x18007ee5f  mov     rax, ds:rva qword_18008FD40[rdx+rax*8]
0x18007ee67  mov     [rbp+280h+var_290], rax
0x18007ee6b  jmp     short loc_18007EE71
0x18007ee6d  mov     [rbp+280h+var_290], r14
0x18007ee71  cmp     dword ptr [rcx+0Ch], 6
0x18007ee75  jnb     short loc_18007EE88
0x18007ee77  mov     eax, [rcx+0Ch]
0x18007ee7a  mov     rax, ds:rva off_18008FD10[rdx+rax*8]
0x18007ee82  mov     [rbp+280h+var_288], rax
0x18007ee86  jmp     short loc_18007EE8C
0x18007ee88  mov     [rbp+280h+var_288], r14
0x18007ee8c  cmp     dword ptr [rcx+10h], 8
0x18007ee90  lea     rdx, [rsp+380h+var_318]; int
0x18007ee95  mov     [rsp+380h+var_348], 1; int
0x18007ee9d  mov     r9d, ebx; int
0x18007eea0  sbb     eax, eax
0x18007eea2  mov     [rbp+280h+var_298], r14
0x18007eea6  and     eax, [rcx+10h]
0x18007eea9  xor     r8d, r8d; int
0x18007eeac  mov     [rbp+280h+var_280], eax
0x18007eeaf  lea     rcx, [rsp+380h+hMem]; int
0x18007eeb4  lea     rax, [rbp+280h+var_298]
0x18007eeb8  mov     [rsp+380h+var_350], rax; __int64
0x18007eebd  mov     [rsp+380h+var_360], esi; int
0x18007eec1  call    BuildCustomEncryption
0x18007eec6  jmp     loc_18007ED9F
0x18007eecb  mov     eax, [rsp+380h+var_318]
0x18007eecf  lea     rdx, [rbp+280h+var_278]
0x18007eed3  mov     rsi, [rsp+380h+hMem]
0x18007eed8  lea     rcx, [rbp+280h+Uuid]
0x18007eedf  mov     r9, rsi
0x18007eee2  mov     [rsp+380h+cbData], r14d; cbData
0x18007eee7  mov     r8d, edi
0x18007eeea  mov     [rsp+380h+var_360], eax; int
0x18007eeee  call    BuildQMPolicy
0x18007eef3  test    r13, r13
0x18007eef6  jz      short loc_18007EEFF
0x18007eef8  mov     eax, [r13+0]
0x18007eefc  mov     dword ptr [rbp+280h+var_268+8], eax
0x18007eeff  mov     rbx, [rbp+280h+var_2D0]
0x18007ef03  lea     r8, [rsp+380h+var_304]; int
0x18007ef08  mov     rcx, rbx; int
0x18007ef0b  mov     [rsp+380h+var_350], r13; __int64
0x18007ef10  mov     r9d, 1; int
0x18007ef16  lea     rdx, [rbp+280h+var_300]; int
0x18007ef1a  call    BuildMMOffers
0x18007ef1f  mov     eax, [rsp+380h+var_304]
0x18007ef23  lea     rcx, [rbp+280h+var_110]; void *
0x18007ef2a  xor     edx, edx; Val
0x18007ef2c  mov     dword ptr [rbp+280h+var_2A8], eax
0x18007ef2f  mov     eax, [rbp+280h+var_300]
0x18007ef32  mov     dword ptr [rbp+280h+var_2B8], r14d
0x18007ef36  mov     dword ptr [rbp+280h+var_2A8+4], r14d
0x18007ef3a  lea     r8d, [rdx+58h]; Size
0x18007ef3e  mov     qword ptr [rbp+280h+var_2A8+8], 708h
0x18007ef46  mov     dword ptr [rbp+280h+var_2C8], 7080h
0x18007ef4d  mov     qword ptr [rbp+280h+var_2B8+8], rbx
0x18007ef51  mov     dword ptr [rbp+280h+var_2B8+4], eax
0x18007ef54  mov     qword ptr [rbp+280h+var_2C8+8], r15
0x18007ef58  mov     dword ptr [rbp+280h+var_2C8+4], r12d
0x18007ef5c  call    memset_0
0x18007ef61  lea     rax, [rbp+280h+var_2C8]
0x18007ef65  mov     [rbp+280h+var_D0], 5
0x18007ef6f  mov     [rbp+280h+var_C8], rax
0x18007ef76  lea     rcx, [rbp+280h+Uuid]; Uuid
0x18007ef7d  lea     rax, aL2tpMainModePo; "L2TP Main Mode Policy"
0x18007ef84  mov     [rbp+280h+var_100], rax
0x18007ef8b  call    cs:__imp_UuidCreate
0x18007ef91  mov     ebx, eax
0x18007ef93  test    eax, eax
0x18007ef95  jz      short loc_18007EFA0
0x18007ef97  lea     rcx, aDwaddserverips_0; "DwAddServerIpsecFilter: UuidCreate fail"...
0x18007ef9e  jmp     short loc_18007EFE3
0x18007efa0  lea     rcx, [rbp+280h+var_110]; Uuid
0x18007efa7  call    cs:__imp_UuidCreate
0x18007efad  mov     ebx, eax
0x18007efaf  test    eax, eax
0x18007efb1  jnz     short loc_18007EF97
0x18007efb3  movaps  xmm0, xmmword ptr [rbp+280h+var_110.Data1]
0x18007efba  movaps  xmm1, xmmword ptr [rbp+280h+Uuid.Data1]
0x18007efc1  movdqu  xmmword ptr cs:gServerMMPolicyGuid.Data1, xmm0
0x18007efc9  movdqu  xmmword ptr cs:gServerQMPolicyGuid.Data1, xmm1
0x18007efd1  call    FwpmTransactionBegin0Wrapper
0x18007efd6  mov     ebx, eax
0x18007efd8  test    eax, eax
0x18007efda  jz      short loc_18007EFEF
0x18007efdc  lea     rcx, aFwpmtransactio_0; "FwpmTransactionBegin0 failed with 0x%x"
0x18007efe3  mov     edx, eax
0x18007efe5  call    RasIpsecTrace
0x18007efea  jmp     loc_18007F7D1
0x18007efef  mov     rcx, cs:gFwpEngineHandle
0x18007eff6  lea     rdx, [rbp+280h+var_110]
0x18007effd  xor     r9d, r9d
  ... truncated ...
```
