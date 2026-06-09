# DwAddServerIpSecFilter

- ea: `0x180083de8`
- end: `0x180084bb0`
- name: `DwAddServerIpSecFilter`
- size: `3528`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800154ec`

## callees

- `0x180076ea0`
- `0x18007717c`
- `0x1800772c0`
- `0x1800828f8`
- `0x180082e2c`
- `0x180082f00`
- `0x1800830ec`
- `0x1800833a4`
- `0x180083478`
- `0x180083584`
- `0x180083de8`
- `0x180085714`
- `0x180085b20`
- `0x180085cb4`
- `0x180085e24`
- `0x180085f44`
- `0x1800864c4`
- `0x180086adc`
- `0x1800871ac`
- `0x180091790`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18008408f`
- `KERNEL32!LocalFree` at `0x1800840de`
- `KERNEL32!LocalFree` at `0x18008408f`
- `KERNEL32!LocalFree` at `0x1800840de`
- `KERNEL32!GetLastError` at `0x180083ee6`
- `KERNEL32!GetLastError` at `0x180083fe5`
- `KERNEL32!GetLastError` at `0x180083ee6`
- `KERNEL32!GetLastError` at `0x180083fe5`
- `KERNEL32!LocalAlloc` at `0x180083ec2`
- `KERNEL32!LocalAlloc` at `0x180083fd1`
- `KERNEL32!LocalAlloc` at `0x180084177`
- `KERNEL32!LocalAlloc` at `0x180083ec2`
- `KERNEL32!LocalAlloc` at `0x180083fd1`
- `KERNEL32!LocalAlloc` at `0x180084177`
- `ADVAPI32!RegCloseKey` at `0x18008419b`
- `ADVAPI32!RegCloseKey` at `0x1800841c4`
- `ADVAPI32!RegCloseKey` at `0x18008419b`
- `ADVAPI32!RegCloseKey` at `0x1800841c4`
- `RPCRT4!UuidCreate` at `0x180084333`
- `RPCRT4!UuidCreate` at `0x180084357`
- `RPCRT4!UuidCreate` at `0x180084333`
- `RPCRT4!UuidCreate` at `0x180084357`
- `fwpuclnt!FwpmTransactionCommit0` at `0x1800846d2`
- `fwpuclnt!FwpmTransactionCommit0` at `0x180084b75`
- `fwpuclnt!FwpmTransactionCommit0` at `0x1800846d2`
- `fwpuclnt!FwpmTransactionCommit0` at `0x180084b75`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x1800843e2`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x1800843e2`
- `fwpuclnt!FwpmTransactionAbort0` at `0x180084b5d`
- `fwpuclnt!FwpmTransactionAbort0` at `0x180084b5d`
- `fwpuclnt!FwpmProviderContextAdd2` at `0x1800843ae`
- `fwpuclnt!FwpmProviderContextAdd2` at `0x1800843ae`

## string_xrefs

- `0x180084029`: `DwAddServerIpSecFilter:OpenIkev2ConfigKey: Failed. error %d`
- `0x1800841d6`: `DwAddServerIpSecFilter:GetIkev2ConfigParams: Failed. error %d`
- `0x180084347`: `DwAddServerIpsecFilter: UuidCreate failed with 0x%x`

## pseudocode

```c
__int64 __fastcall DwAddServerIpSecFilter(unsigned int a1)
{
  _DWORD *v2; // r12
  _DWORD *v3; // r13
  DWORD LastError; // ebx
  int v5; // r15d
  __int64 v6; // rcx
  int v7; // r14d
  __int64 v8; // rax
  __int64 v9; // rax
  DWORD v10; // eax
  const CHAR *v11; // rcx
  void *v12; // rcx
  _BYTE *v13; // rsi
  __int64 v14; // r14
  int L2tpConfigParams; // ebx
  _DWORD *v17; // rcx
  bool v18; // cf
  HLOCAL v19; // rbx
  const CHAR *v20; // rcx
  DWORD v21; // eax
  unsigned int v22; // esi
  unsigned int v23; // esi
  unsigned int v24; // esi
  unsigned int v25; // esi
  __int64 v26; // r8
  __int64 v27; // r8
  int v28; // [rsp+28h] [rbp-E0h]
  BYTE Data; // [rsp+30h] [rbp-D8h]
  BYTE Dataa; // [rsp+30h] [rbp-D8h]
  int Datab; // [rsp+30h] [rbp-D8h]
  int Datac; // [rsp+30h] [rbp-D8h]
  int Datad; // [rsp+30h] [rbp-D8h]
  int Datae; // [rsp+30h] [rbp-D8h]
  int Dataf; // [rsp+30h] [rbp-D8h]
  int Datag; // [rsp+30h] [rbp-D8h]
  int Datah; // [rsp+30h] [rbp-D8h]
  DWORD v38; // [rsp+48h] [rbp-C0h]
  int v39; // [rsp+58h] [rbp-B0h]
  int v40[4]; // [rsp+78h] [rbp-90h] BYREF
  int v41; // [rsp+88h] [rbp-80h] BYREF
  int v42; // [rsp+8Ch] [rbp-7Ch]
  int v43; // [rsp+90h] [rbp-78h]
  int v44; // [rsp+94h] [rbp-74h] BYREF
  int v45; // [rsp+98h] [rbp-70h] BYREF
  int v46; // [rsp+9Ch] [rbp-6Ch] BYREF
  HLOCAL v47; // [rsp+A0h] [rbp-68h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp-60h] BYREF
  HLOCAL v49; // [rsp+B0h] [rbp-58h] BYREF
  HLOCAL hMem; // [rsp+B8h] [rbp-50h]
  __int128 v51; // [rsp+C0h] [rbp-48h] BYREF
  __int128 v52; // [rsp+D0h] [rbp-38h]
  __int128 v53; // [rsp+E0h] [rbp-28h]
  __int64 v54; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v55; // [rsp+F8h] [rbp-10h]
  __int64 *v56; // [rsp+100h] [rbp-8h]
  int v57; // [rsp+108h] [rbp+0h]
  int v58; // [rsp+10Ch] [rbp+4h]
  __int128 v59; // [rsp+110h] [rbp+8h] BYREF
  __int128 v60; // [rsp+120h] [rbp+18h]
  int v61; // [rsp+130h] [rbp+28h]
  UUID v62; // [rsp+138h] [rbp+30h] BYREF
  const wchar_t *v63; // [rsp+148h] [rbp+40h]
  int v64; // [rsp+178h] [rbp+70h]
  __int128 *v65; // [rsp+180h] [rbp+78h]
  FWPM_PROVIDER_CONTEXT0 Uuid; // [rsp+198h] [rbp+90h] BYREF
  _BYTE v67[16]; // [rsp+1F8h] [rbp+F0h] BYREF
  _BYTE v68[16]; // [rsp+208h] [rbp+100h] BYREF
  _BYTE v69[16]; // [rsp+218h] [rbp+110h] BYREF
  _BYTE v70[16]; // [rsp+228h] [rbp+120h] BYREF
  _BYTE v71[16]; // [rsp+238h] [rbp+130h] BYREF
  _BYTE v72[16]; // [rsp+248h] [rbp+140h] BYREF
  _BYTE v73[16]; // [rsp+258h] [rbp+150h] BYREF
  _BYTE v74[16]; // [rsp+268h] [rbp+160h] BYREF
  _BYTE v75[16]; // [rsp+278h] [rbp+170h] BYREF
  _BYTE v76[16]; // [rsp+288h] [rbp+180h] BYREF
  _BYTE v77[16]; // [rsp+298h] [rbp+190h] BYREF
  _BYTE v78[16]; // [rsp+2A8h] [rbp+1A0h] BYREF
  _BYTE v79[16]; // [rsp+2B8h] [rbp+1B0h] BYREF
  _BYTE v80[16]; // [rsp+2C8h] [rbp+1C0h] BYREF
  _BYTE v81[16]; // [rsp+2D8h] [rbp+1D0h] BYREF
  _BYTE v82[16]; // [rsp+2E8h] [rbp+1E0h] BYREF
  _BYTE v83[16]; // [rsp+2F8h] [rbp+1F0h] BYREF
  _BYTE v84[16]; // [rsp+308h] [rbp+200h] BYREF
  _BYTE v85[16]; // [rsp+318h] [rbp+210h] BYREF
  _BYTE v86[16]; // [rsp+328h] [rbp+220h] BYREF

  v40[0] = 0;
  v2 = 0;
  v47 = 0;
  v49 = 0;
  memset_0(&v62, 0, 0x58u);
  memset_0(&Uuid, 0, sizeof(Uuid));
  v45 = 0;
  v61 = 0;
  v41 = 0;
  v46 = 0;
  v59 = 0;
  v43 = 250000;
  v60 = 0;
  v42 = 3600;
  v3 = 0;
  v51 = 0;
  hKey = 0;
  v52 = 0;
  v53 = 0;
  memset_0(v67, 0, 0x140u);
  RasIpsecTrace("DwAddServerIpSecFilter");
  hMem = LocalAlloc(0x40u, 0x118u);
  if ( !hMem )
  {
    RasIpsecTrace("DwAddServerIpsecFilter: failed to alloc");
    LastError = GetLastError();
    goto LABEL_24;
  }
  v44 = 1;
  DwGetPresharedKey(0, 256, (int)v40);
  v5 = v40[0];
  v40[0] = v40[0] != 0;
  LastError = GenerateCertificatesList(1, &v47, v40, &v44);
  v39 = v40[0];
  if ( v5 )
  {
    v2 = v47;
    v8 = 1;
    if ( !v47 )
    {
      v2 = LocalAlloc(0x40u, 0x40u);
      if ( !v2 )
      {
        LastError = GetLastError();
        goto LABEL_37;
      }
      v8 = 0;
    }
    v9 = 10 * v8;
    v2[2 * v9] = 0;
    *(_QWORD *)&v2[2 * v9 + 4] = 0;
    v2[2 * v9 + 2] = v5;
    goto LABEL_18;
  }
  v7 = v44;
  if ( LastError || !v40[0] || v44 )
  {
    RasIpsecTrace("PSK=NULL. Failed to generate certificate list. rc=0x%x, Count=%d, MyStoreEmpty=%d");
    if ( !v39 || v7 )
      LastError = 766;
    v2 = v47;
    if ( v47 )
    {
      FreeAuthInfoList(v47);
      v2 = 0;
    }
  }
  else
  {
    v2 = v47;
  }
LABEL_37:
  if ( LastError )
  {
    RasIpsecTrace("DwAddServerIpsecFilter: DwGetMMAuthMethodsForServer returned %d. PSK length is %d");
    goto LABEL_28;
  }
LABEL_18:
  if ( (unsigned int)OpenL2tpConfigKey(v6, &hKey) )
  {
    RasIpsecTrace("DwAddServerIpSecFilter:OpenIkev2ConfigKey: Failed. error %d");
LABEL_20:
    v10 = BuildIpsecOffers(a1, &v49, &v41);
    goto LABEL_21;
  }
  v3 = LocalAlloc(0x40u, 0x20u);
  if ( !v3 )
  {
    RasIpsecTrace("DwAddServerIpSecFilter: Memory allocation failed");
    RegCloseKey(hKey);
    goto LABEL_20;
  }
  L2tpConfigParams = GetL2tpConfigParams(hKey);
  RegCloseKey(hKey);
  if ( L2tpConfigParams )
    RasIpsecTrace("DwAddServerIpSecFilter:GetIkev2ConfigParams: Failed. error %d");
  a1 = v3[1];
  v42 = v3[2];
  v43 = v3[3];
  if ( a1 == 1 )
  {
    a1 = 4;
  }
  else if ( a1 == 2 )
  {
    a1 = 5;
  }
  v17 = (_DWORD *)*((_QWORD *)v3 + 2);
  if ( !v17 )
    goto LABEL_20;
  v18 = v17[2] < 9u;
  v58 = 0;
  if ( v18 )
    v55 = qword_180096D40[v17[2]];
  else
    v55 = 0;
  if ( v17[3] >= 6u )
    v56 = 0;
  else
    v56 = off_180096D10[v17[3]];
  v57 = v17[4] < 8u ? v17[4] : 0;
  v54 = 0;
  v10 = BuildCustomEncryption((int)&v49, (int)&v41, 0, v43, v42, Data, (__int64)&v54, 1, v38);
LABEL_21:
  LastError = v10;
  if ( v10 )
  {
    v11 = "DwAddServerIpsecFilter: BuildIpsecOffers returned %d";
LABEL_23:
    RasIpsecTrace(v11);
    goto LABEL_24;
  }
  BuildQMPolicy((unsigned int)&Uuid, (unsigned int)&v59, a1, (_DWORD)v49, v41, 0);
  if ( v3 )
    DWORD2(v60) = *v3;
  v19 = hMem;
  BuildMMOffers((int)hMem, (int)&v46, (int)&v45, 1, v28, Dataa, (__int64)v3);
  v53 = (unsigned int)v45;
  DWORD1(v52) = v46;
  DWORD1(v51) = v39;
  v65 = &v51;
  v63 = L"L2TP Main Mode Policy";
  LODWORD(v52) = 0;
  LODWORD(v51) = 28800;
  *((_QWORD *)&v52 + 1) = v19;
  *((_QWORD *)&v51 + 1) = v2;
  v64 = 5;
  LastError = UuidCreate(&Uuid.providerContextKey);
  if ( LastError || (LastError = UuidCreate(&v62)) != 0 )
  {
    v11 = "DwAddServerIpsecFilter: UuidCreate failed with 0x%x";
    goto LABEL_23;
  }
  gServerMMPolicyGuid = v62;
  gServerQMPolicyGuid = Uuid.providerContextKey;
  LastError = FwpmTransactionBegin0Wrapper();
  if ( LastError )
  {
    v11 = "FwpmTransactionBegin0 failed with 0x%x";
    goto LABEL_23;
  }
  LastError = FwpmProviderContextAdd2(gFwpEngineHandle, &v62, 0, 0);
  if ( LastError )
  {
    v20 = "FwpmProviderContextAdd0 for MM policy failed with 0x%x";
LABEL_134:
    RasIpsecTrace(v20);
    FwpmTransactionAbort0(gFwpEngineHandle);
    goto LABEL_24;
  }
  v21 = FwpmProviderContextAdd0(gFwpEngineHandle, &Uuid, 0, 0);
  LastError = v21;
  if ( v21 )
  {
    v20 = "FwpmProviderContextAdd0 for QM policy failed with 0x%x";
    goto LABEL_134;
  }
  if ( a1 )
  {
    v22 = a1 - 1;
    if ( v22 )
    {
      v23 = v22 - 1;
      if ( !v23 || (v24 = v23 - 1) == 0 )
      {
LABEL_72:
        LastError = BuildOutTxFilter((unsigned int)v78, v21, 1, 1, 1);
        if ( LastError )
        {
LABEL_77:
          v20 = "BuildOutTxFilter for QM policy failed with 0x%x  Ipv6: TRUE";
          goto LABEL_134;
        }
        LastError = BuildOutTxFilter((unsigned int)v77, 0, 1, 1, 0);
        if ( LastError )
        {
LABEL_79:
          v20 = "BuildOutTxFilter for QM policy failed with 0x%x  Ipv6: FALSE";
          goto LABEL_134;
        }
        LastError = AddFilters(v78, gServerFilterIds, &gNumServerFilterIds, 0);
        if ( LastError )
          goto LABEL_87;
        LastError = AddFilters(v77, gServerFilterIds, &gNumServerFilterIds, 0);
        if ( LastError )
          goto LABEL_89;
        LastError = BuildOutTxFilter((unsigned int)v82, 0, 1, 0, 1);
        if ( LastError )
          goto LABEL_77;
        LastError = BuildOutTxFilter((unsigned int)v81, 0, 1, 0, 0);
        if ( LastError )
          goto LABEL_79;
        LastError = AddFilters(v82, gServerFilterIds, &gNumServerFilterIds, 0);
        if ( LastError )
          goto LABEL_87;
        LastError = AddFilters(v81, gServerFilterIds, &gNumServerFilterIds, 0);
        if ( LastError )
          goto LABEL_89;
        LastError = BuildInTxFilter((unsigned int)v80, 1, 0, 1701, (__int64)L"L2TP Server Filter1", Datab, 1);
        if ( LastError )
        {
LABEL_83:
          v20 = "BuildInTxFilter for QM policy failed with 0x%x  Ipv6: TRUE";
          goto LABEL_134;
        }
        LastError = BuildInTxFilter((unsigned int)v79, 1, 0, 1701, (__int64)L"L2TP Server Filter1", Datac, 0);
        if ( LastError )
        {
LABEL_85:
          v20 = "BuildInTxFilter for QM policy failed with 0x%x  Ipv6: FALSE";
          goto LABEL_134;
        }
        LastError = AddFilters(v80, gServerFilterIds, &gNumServerFilterIds, 0);
        if ( LastError )
        {
LABEL_87:
          v20 = "AddFilters for QM policy failed with 0x%x  Ipv6: TRUE";
          goto LABEL_134;
        }
        LastError = AddFilters(v79, gServerFilterIds, &gNumServerFilterIds, 0);
        if ( LastError )
        {
LABEL_89:
          v20 = "AddFilters for QM policy failed with 0x%x  Ipv6: FALSE";
          goto LABEL_134;
        }
        LastError = BuildOutMMFilter(v84, 0, L"L2TP Server Inbound and Outbound Filter", 1);
        if ( LastError )
        {
          v20 = "BuildOutMMFilter for MM policy failed with 0x%x  Ipv6: TRUE";
          goto LABEL_134;
        }
        LastError = BuildOutMMFilter(v83, 0, L"L2TP Server Inbound and Outbound Filter", 0);
        if ( LastError )
        {
          v20 = "BuildOutMMFilter for MM policy failed with 0x%x  Ipv6: FALSE";
          goto LABEL_134;
        }
        LastError = AddFilters(v84, gServerFilterIds, &gNumServerFilterIds, 0);
        if ( LastError )
        {
LABEL_95:
          v20 = "AddFilters for MM policy failed with 0x%x  Ipv6: TRUE";
          goto LABEL_134;
        }
        LastError = AddFilters(v83, gServerFilterIds, &gNumServerFilterIds, 0);
        if ( !LastError )
        {
          LastError = FwpmTransactionCommit0(gFwpEngineHandle);
          if ( !v2 )
            goto LABEL_24;
          goto LABEL_98;
        }
LABEL_133:
        v20 = "AddFilters for MM policy failed with 0x%x  Ipv6: FALSE";
        goto LABEL_134;
      }
      v25 = v24 - 1;
      if ( v25 )
      {
        if ( v25 != 1 )
          goto LABEL_24;
        goto LABEL_72;
      }
    }
  }
  LastError = BuildOutMMFilter(v84, v21, L"L2TP Server Outbound Filter", 1);
  if ( LastError )
  {
    v20 = "BuildOutMMFilter for MM policy failed with 0x%x  IPv6: TRUE";
    goto LABEL_134;
  }
  LastError = BuildOutMMFilter(v83, 0, L"L2TP Server Outbound Filter", 0);
  if ( LastError )
  {
    v20 = "BuildOutMMFilter for MM policy failed with 0x%x  IPv6: FALSE";
    goto LABEL_134;
  }
  LastError = BuildInMMFilter(v86, 0, v26, 1);
  if ( LastError )
  {
    v20 = "BuildInMMFilter for MM policy failed with 0x%x  IPv6: TRUE";
    goto LABEL_134;
  }
  LastError = BuildInMMFilter(v85, 0, v27, 0);
  if ( LastError )
  {
    v20 = "BuildInMMFilter for MM policy failed with 0x%x  IPv6: FALSE";
    goto LABEL_134;
  }
  LastError = BuildOutTxFilter((unsigned int)v68, 0, 0, 1, 1);
  if ( LastError )
    goto LABEL_77;
  LastError = BuildOutTxFilter((unsigned int)v67, 0, 0, 1, 0);
  if ( LastError )
    goto LABEL_79;
  LastError = AddFilters(v68, gServerFilterIds, &gNumServerFilterIds, 0);
  if ( LastError )
    goto LABEL_87;
  LastError = AddFilters(v67, gServerFilterIds, &gNumServerFilterIds, 0);
  if ( LastError )
    goto LABEL_89;
  LastError = BuildOutTxFilter((unsigned int)v70, 0, 0, 0, 1);
  if ( LastError )
    goto LABEL_77;
  LastError = BuildOutTxFilter((unsigned int)v69, 0, 0, 0, 0);
  if ( LastError )
  {
    v20 = "BuildOutTxFilter for QM policy failed with 0x%x";
    goto LABEL_134;
  }
  LastError = AddFilters(v70, gServerFilterIds, &gNumServerFilterIds, 0);
  if ( LastError )
    goto LABEL_87;
  LastError = AddFilters(v69, gServerFilterIds, &gNumServerFilterIds, 0);
  if ( LastError )
    goto LABEL_89;
  LastError = BuildInTxFilter((unsigned int)v72, 0, 1701, 0, (__int64)L"L2TP Server Inbound Filter", Datab, 1);
  if ( LastError )
    goto LABEL_83;
  LastError = BuildInTxFilter((unsigned int)v71, 0, 1701, 0, (__int64)L"L2TP Server Inbound Filter", Datad, 0);
  if ( LastError )
    goto LABEL_85;
  LastError = AddFilters(v72, gServerFilterIds, &gNumServerFilterIds, 0);
  if ( LastError )
    goto LABEL_87;
  LastError = AddFilters(v71, gServerFilterIds, &gNumServerFilterIds, 0);
  if ( LastError )
    goto LABEL_89;
  LastError = BuildInTxFilter((unsigned int)v74, 0, 1701, 1701, (__int64)L"L2TP Server Inbound Filter", Datae, 1);
  if ( LastError )
    goto LABEL_83;
  LastError = BuildInTxFilter((unsigned int)v73, 0, 1701, 1701, (__int64)L"L2TP Server Inbound Filter", Dataf, 0);
  if ( LastError )
    goto LABEL_85;
  LastError = AddFilters(v74, gServerFilterIds, &gNumServerFilterIds, 0);
  if ( LastError )
    goto LABEL_87;
  LastError = AddFilters(v73, gServerFilterIds, &gNumServerFilterIds, 0);
  if ( LastError )
    goto LABEL_89;
  LastError = BuildInTxFilter((unsigned int)v76, 1, 0, 1701, (__int64)L"L2TP Server Filter1", Datag, 1);
  if ( LastError )
    goto LABEL_83;
  LastError = BuildInTxFilter((unsigned int)v75, 1, 0, 1701, (__int64)L"L2TP Server Filter1", Datah, 0);
  if ( LastError )
    goto LABEL_85;
  LastError = AddFilters(v76, gServerFilterIds, &gNumServerFilterIds, 0);
  if ( LastError )
    goto LABEL_87;
  LastError = AddFilters(v75, gServerFilterIds, &gNumServerFilterIds, 0);
  if ( LastError )
    goto LABEL_89;
  LastError = AddFilters(v84, gServerFilterIds, &gNumServerFilterIds, 0);
  if ( LastError )
    goto LABEL_95;
  LastError = AddFilters(v83, gServerFilterIds, &gNumServerFilterIds, 0);
  if ( LastError )
    goto LABEL_133;
  LastError = AddFilters(v86, gServerFilterIds, &gNumServerFilterIds, 0);
  if ( LastError )
  {
    v20 = "AddFilters for MM policy failed with 0x%x  Ipv6:  TRUE";
    goto LABEL_134;
  }
  LastError = AddFilters(v85, gServerFilterIds, &gNumServerFilterIds, 0);
  if ( LastError )
    goto LABEL_133;
  LastError = FwpmTransactionCommit0(gFwpEngineHandle);
  if ( v2 )
  {
LABEL_98:
    FreeAuthInfoList(v2);
    v2 = 0;
  }
LABEL_24:
  if ( v3 )
  {
    v12 = (void *)*((_QWORD *)v3 + 2);
    if ( v12 )
    {
      MprCommonFree(v12);
      *((_QWORD *)v3 + 2) = 0;
    }
    LocalFree(v3);
  }
LABEL_28:
  if ( v49 )
    FreeIpsecOffers(v49);
  v13 = v67;
  v14 = 20;
  do
  {
    WfpFilterListDestroy(v13, v13 + 8);
    v13 += 16;
    --v14;
  }
  while ( v14 );
  if ( hMem )
    LocalFree(hMem);
  if ( v2 )
    FreeAuthInfoList(v2);
  RasIpsecTrace("DwAddServerIpSecFilter, rc=0x%x");
  return LastError;
}

```

## disassembly

```asm
0x180083de8  mov     rax, rsp
0x180083deb  mov     [rax+10h], rbx
0x180083def  mov     [rax+18h], rsi
0x180083df3  mov     [rax+20h], rdi
0x180083df7  push    rbp
0x180083df8  push    r12
0x180083dfa  push    r13
0x180083dfc  push    r14
0x180083dfe  push    r15
0x180083e00  lea     rbp, [rax-268h]
0x180083e07  sub     rsp, 340h
0x180083e0e  mov     rax, cs:__security_cookie
0x180083e15  xor     rax, rsp
0x180083e18  mov     [rbp+260h+var_30], rax
0x180083e1f  xor     edi, edi
0x180083e21  mov     esi, ecx
0x180083e23  xor     edx, edx; Val
0x180083e25  mov     [rsp+360h+var_2F0], edi
0x180083e29  lea     rcx, [rbp+260h+var_230]; void *
0x180083e2d  mov     [rsp+360h+var_300], rdi
0x180083e32  mov     r12d, edi
0x180083e35  mov     [rbp+260h+var_2C8], rdi
0x180083e39  lea     ebx, [rdi+58h]
0x180083e3c  mov     [rbp+260h+var_2B8], rdi
0x180083e40  mov     r8d, ebx; Size
0x180083e43  call    memset_0
0x180083e48  mov     r8d, ebx; Size
0x180083e4b  lea     rcx, [rbp+260h+Uuid]; void *
0x180083e52  xor     edx, edx; Val
0x180083e54  call    memset_0
0x180083e59  xorps   xmm0, xmm0
0x180083e5c  mov     [rbp+260h+var_2D0], edi
0x180083e5f  xor     eax, eax
0x180083e61  mov     [rsp+360h+var_310], edi
0x180083e65  xor     edx, edx; Val
0x180083e67  mov     [rbp+260h+var_238], eax
0x180083e6a  mov     r8d, 140h; Size
0x180083e70  mov     [rbp+260h+var_2E0], edi
0x180083e73  lea     rcx, [rbp+260h+var_170]; void *
0x180083e7a  mov     [rbp+260h+var_2CC], edi
0x180083e7d  movups  [rbp+260h+var_258], xmm0
0x180083e81  mov     r14d, edi
0x180083e84  mov     [rbp+260h+var_2D8], 3D090h
0x180083e8b  movups  [rbp+260h+var_248], xmm0
0x180083e8f  mov     [rbp+260h+var_2DC], 0E10h
0x180083e96  mov     r13d, edi
0x180083e99  movups  [rbp+260h+var_2A8], xmm0
0x180083e9d  mov     [rbp+260h+hKey], rdi
0x180083ea1  movups  [rbp+260h+var_298], xmm0
0x180083ea5  movups  [rbp+260h+var_288], xmm0
0x180083ea9  call    memset_0
0x180083eae  lea     rcx, aDwaddserverips_2; "DwAddServerIpSecFilter"
0x180083eb5  call    RasIpsecTrace
0x180083eba  mov     edx, 118h; uBytes
0x180083ebf  lea     ecx, [rdi+40h]; uFlags
0x180083ec2  call    cs:__imp_LocalAlloc
0x180083ec9  nop     dword ptr [rax+rax+00h]
0x180083ece  mov     [rbp+260h+hMem], rax
0x180083ed2  lea     ebx, [rdi+1]
0x180083ed5  test    rax, rax
0x180083ed8  jnz     short loc_180083EFC
0x180083eda  lea     rcx, aDwaddserverips_4; "DwAddServerIpsecFilter: failed to alloc"
0x180083ee1  call    RasIpsecTrace
0x180083ee6  call    cs:__imp_GetLastError
0x180083eed  nop     dword ptr [rax+rax+00h]
0x180083ef2  mov     ebx, eax
0x180083ef4  mov     r15, rdi
0x180083ef7  jmp     loc_180084075
0x180083efc  lea     r9, [rsp+360h+var_300]
0x180083f01  mov     [rbp+260h+var_2D4], ebx
0x180083f04  lea     r8, [rsp+360h+var_2F0]; int
0x180083f09  mov     edx, 100h; int
0x180083f0e  xor     ecx, ecx; int
0x180083f10  call    DwGetPresharedKey
0x180083f15  mov     r15d, [rsp+360h+var_2F0]
0x180083f1a  lea     r9, [rbp+260h+var_2D4]
0x180083f1e  test    r15d, r15d
0x180083f21  lea     r8, [rsp+360h+var_2F0]
0x180083f26  lea     rdx, [rbp+260h+var_2C8]
0x180083f2a  mov     ecx, ebx
0x180083f2c  cmovnz  r14d, ebx
0x180083f30  mov     [rsp+360h+var_2F0], r14d
0x180083f35  call    GenerateCertificatesList
0x180083f3a  mov     r14, [rsp+360h+var_300]
0x180083f3f  mov     ebx, eax
0x180083f41  mov     eax, [rsp+360h+var_2F0]
0x180083f45  mov     [rsp+360h+var_310], eax
0x180083f49  mov     [rsp+360h+var_300], r14
0x180083f4e  test    r15d, r15d
0x180083f51  jnz     short loc_180083FBA
0x180083f53  mov     r14d, [rbp+260h+var_2D4]
0x180083f57  test    ebx, ebx
0x180083f59  jnz     short loc_180083F64
0x180083f5b  test    eax, eax
0x180083f5d  jz      short loc_180083F64
0x180083f5f  test    r14d, r14d
0x180083f62  jz      short loc_180083FAC
0x180083f64  mov     r9d, r14d
0x180083f67  lea     rcx, aPskNullFailedT; "PSK=NULL. Failed to generate certificat"...
0x180083f6e  mov     r8d, eax
0x180083f71  mov     edx, ebx
0x180083f73  call    RasIpsecTrace
0x180083f78  mov     eax, [rsp+360h+var_310]
0x180083f7c  test    eax, eax
0x180083f7e  jz      short loc_180083F85
0x180083f80  test    r14d, r14d
0x180083f83  jz      short loc_180083F8A
0x180083f85  mov     ebx, 2FEh
0x180083f8a  mov     r12, [rbp+260h+var_2C8]
0x180083f8e  test    r12, r12
0x180083f91  jz      loc_18008414A
0x180083f97  xor     r8d, r8d
0x180083f9a  mov     edx, eax
0x180083f9c  mov     rcx, r12; hMem
0x180083f9f  call    FreeAuthInfoList
0x180083fa4  mov     r12, rdi
0x180083fa7  jmp     loc_18008414A
0x180083fac  mov     r14, [rsp+360h+var_300]
0x180083fb1  test    r15d, r15d
0x180083fb4  jz      loc_180084146
0x180083fba  mov     r12, [rbp+260h+var_2C8]
0x180083fbe  mov     eax, 1
0x180083fc3  test    r12, r12
0x180083fc6  jnz     short loc_180083FFB
0x180083fc8  lea     eax, [r12+40h]
0x180083fcd  mov     edx, eax; uBytes
0x180083fcf  mov     ecx, eax; uFlags
0x180083fd1  call    cs:__imp_LocalAlloc
0x180083fd8  nop     dword ptr [rax+rax+00h]
0x180083fdd  mov     r12, rax
0x180083fe0  test    rax, rax
0x180083fe3  jnz     short loc_180083FF8
0x180083fe5  call    cs:__imp_GetLastError
0x180083fec  nop     dword ptr [rax+rax+00h]
0x180083ff1  mov     ebx, eax
0x180083ff3  jmp     loc_18008414A
0x180083ff8  mov     rax, rdi
0x180083ffb  lea     rax, [rax+rax*4]
0x180083fff  add     rax, rax
0x180084002  mov     [r12+rax*8], edi
0x180084006  mov     [r12+rax*8+10h], r14
0x18008400b  mov     [r12+rax*8+8], r15d
0x180084010  lea     rdx, [rbp+260h+hKey]
0x180084014  call    OpenL2tpConfigKey
0x180084019  mov     r14d, 5
0x18008401f  test    eax, eax
0x180084021  jz      loc_18008416D
0x180084027  mov     edx, eax
0x180084029  lea     rcx, aDwaddserverips_1; "DwAddServerIpSecFilter:OpenIkev2ConfigK"...
0x180084030  call    RasIpsecTrace
0x180084035  mov     eax, [rbp+260h+var_2DC]
0x180084038  lea     r8, [rbp+260h+var_2E0]
0x18008403c  mov     dword ptr [rsp+360h+Data], eax
0x180084040  lea     rdx, [rbp+260h+var_2B8]
0x180084044  mov     eax, [rbp+260h+var_2D8]
0x180084047  mov     ecx, esi
0x180084049  mov     [rsp+360h+var_340], eax
0x18008404d  call    BuildIpsecOffers
0x180084052  mov     r15d, 1
0x180084058  mov     ebx, eax
0x18008405a  test    eax, eax
0x18008405c  jz      loc_18008429B
0x180084062  mov     edx, eax
0x180084064  lea     rcx, aDwaddserverips_7; "DwAddServerIpsecFilter: BuildIpsecOffer"...
0x18008406b  call    RasIpsecTrace
0x180084070  mov     r15, [rsp+360h+var_300]
0x180084075  test    r13, r13
0x180084078  jz      short loc_18008409B
0x18008407a  mov     rcx, [r13+10h]; lpMem
0x18008407e  test    rcx, rcx
0x180084081  jz      short loc_18008408C
0x180084083  call    MprCommonFree
0x180084088  mov     [r13+10h], rdi
0x18008408c  mov     rcx, r13; hMem
0x18008408f  call    cs:__imp_LocalFree
0x180084096  nop     dword ptr [rax+rax+00h]
0x18008409b  mov     rax, [rbp+260h+var_2B8]
0x18008409f  test    rax, rax
0x1800840a2  jz      short loc_1800840AF
0x1800840a4  mov     edx, [rbp+260h+var_2E0]
0x1800840a7  mov     rcx, rax; hMem
0x1800840aa  call    FreeIpsecOffers
0x1800840af  lea     rsi, [rbp+260h+var_170]
0x1800840b6  mov     r14d, 14h
0x1800840bc  lea     rdx, [rsi+8]
0x1800840c0  mov     rcx, rsi
0x1800840c3  call    WfpFilterListDestroy
0x1800840c8  add     rsi, 10h
0x1800840cc  sub     r14, 1
0x1800840d0  jnz     short loc_1800840BC
0x1800840d2  mov     rax, [rbp+260h+hMem]
0x1800840d6  test    rax, rax
0x1800840d9  jz      short loc_1800840EA
0x1800840db  mov     rcx, rax; hMem
0x1800840de  call    cs:__imp_LocalFree
0x1800840e5  nop     dword ptr [rax+rax+00h]
0x1800840ea  test    r12, r12
0x1800840ed  jz      short loc_180084105
0x1800840ef  mov     edx, [rsp+360h+var_310]
0x1800840f3  test    r15, r15
0x1800840f6  mov     rcx, r12; hMem
0x1800840f9  setnz   dil
0x1800840fd  mov     r8d, edi
0x180084100  call    FreeAuthInfoList
0x180084105  mov     edx, ebx
0x180084107  lea     rcx, aDwaddserverips_3; "DwAddServerIpSecFilter, rc=0x%x"
0x18008410e  call    RasIpsecTrace
0x180084113  mov     eax, ebx
0x180084115  mov     rcx, [rbp+260h+var_30]
0x18008411c  xor     rcx, rsp; StackCookie
0x18008411f  call    __security_check_cookie
0x180084124  lea     r11, [rsp+360h+var_20]
0x18008412c  mov     rbx, [r11+38h]
0x180084130  mov     rsi, [r11+40h]
0x180084134  mov     rdi, [r11+48h]
0x180084138  mov     rsp, r11
0x18008413b  pop     r15
0x18008413d  pop     r14
0x18008413f  pop     r13
0x180084141  pop     r12
0x180084143  pop     rbp
0x180084144  retn
0x180084146  mov     r12, [rbp+260h+var_2C8]
0x18008414a  test    ebx, ebx
0x18008414c  jz      loc_180084010
0x180084152  mov     r8d, r15d
0x180084155  lea     rcx, aDwaddserverips; "DwAddServerIpsecFilter: DwGetMMAuthMeth"...
0x18008415c  mov     edx, ebx
0x18008415e  call    RasIpsecTrace
0x180084163  mov     r15, [rsp+360h+var_300]
0x180084168  jmp     loc_18008409B
0x18008416d  mov     ebx, 20h ; ' '
0x180084172  mov     edx, ebx; uBytes
0x180084174  lea     ecx, [rbx+20h]; uFlags
0x180084177  call    cs:__imp_LocalAlloc
0x18008417e  nop     dword ptr [rax+rax+00h]
0x180084183  mov     r13, rax
0x180084186  test    rax, rax
0x180084189  jnz     short loc_1800841AC
0x18008418b  lea     rcx, aDwaddserverips_5; "DwAddServerIpSecFilter: Memory allocati"...
0x180084192  call    RasIpsecTrace
0x180084197  mov     rcx, [rbp+260h+hKey]; hKey
0x18008419b  call    cs:__imp_RegCloseKey
0x1800841a2  nop     dword ptr [rax+rax+00h]
0x1800841a7  jmp     loc_180084035
0x1800841ac  mov     rcx, [rbp+260h+hKey]; hKey
0x1800841b0  mov     r9d, ebx
0x1800841b3  mov     r8, r13
0x1800841b6  mov     dl, r14b
0x1800841b9  call    GetL2tpConfigParams
0x1800841be  mov     rcx, [rbp+260h+hKey]; hKey
0x1800841c2  mov     ebx, eax
0x1800841c4  call    cs:__imp_RegCloseKey
0x1800841cb  nop     dword ptr [rax+rax+00h]
0x1800841d0  test    ebx, ebx
0x1800841d2  jz      short loc_1800841E2
0x1800841d4  mov     edx, ebx
0x1800841d6  lea     rcx, aDwaddserverips_6; "DwAddServerIpSecFilter:GetIkev2ConfigPa"...
0x1800841dd  call    RasIpsecTrace
0x1800841e2  mov     eax, [r13+8]
0x1800841e6  mov     esi, [r13+4]
0x1800841ea  mov     [rbp+260h+var_2DC], eax
0x1800841ed  mov     eax, [r13+0Ch]
0x1800841f1  mov     [rbp+260h+var_2D8], eax
0x1800841f4  mov     eax, esi
0x1800841f6  sub     eax, 1
0x1800841f9  jz      short loc_180084205
0x1800841fb  cmp     eax, 1
0x1800841fe  jnz     short loc_18008420A
0x180084200  mov     esi, r14d
0x180084203  jmp     short loc_18008420A
0x180084205  mov     esi, 4
0x18008420a  mov     rcx, [r13+10h]
0x18008420e  test    rcx, rcx
0x180084211  jz      loc_180084035
0x180084217  cmp     dword ptr [rcx+8], 9
0x18008421b  lea     rdx, cs:180000000h
0x180084222  mov     [rbp+260h+var_25C], edi
0x180084225  jnb     short loc_180084238
0x180084227  mov     eax, [rcx+8]
0x18008422a  mov     rax, ds:rva qword_180096D40[rdx+rax*8]
0x180084232  mov     [rbp+260h+var_270], rax
0x180084236  jmp     short loc_18008423C
0x180084238  mov     [rbp+260h+var_270], rdi
0x18008423c  cmp     dword ptr [rcx+0Ch], 6
0x180084240  jnb     short loc_180084253
0x180084242  mov     eax, [rcx+0Ch]
0x180084245  mov     rax, ds:rva off_180096D10[rdx+rax*8]
0x18008424d  mov     [rbp+260h+var_268], rax
0x180084251  jmp     short loc_180084257
0x180084253  mov     [rbp+260h+var_268], rdi
0x180084257  cmp     dword ptr [rcx+10h], 8
0x18008425b  lea     rdx, [rbp+260h+var_2E0]; int
0x18008425f  mov     r9d, [rbp+260h+var_2D8]; int
0x180084263  mov     r15d, 1
0x180084269  sbb     eax, eax
0x18008426b  mov     [rsp+360h+var_328], r15d; int
0x180084270  and     eax, [rcx+10h]
0x180084273  xor     r8d, r8d; int
0x180084276  mov     [rbp+260h+var_260], eax
  ... truncated ...
```
