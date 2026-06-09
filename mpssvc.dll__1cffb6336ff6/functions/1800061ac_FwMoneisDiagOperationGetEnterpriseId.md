# FwMoneisDiagOperationGetEnterpriseId

- ea: `0x1800061ac`
- end: `0x180006cd8`
- name: `FwMoneisDiagOperationGetEnterpriseId`
- size: `2860`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800055a8`

## callees

- `0x1800052d8`
- `0x180005aa0`
- `0x1800061ac`
- `0x180006ce0`
- `0x180008618`
- `0x180009720`
- `0x18000ae9c`
- `0x18000af3c`
- `0x180017110`
- `0x18006f520`
- `0x18008abb0`
- `0x1800ba0a4`
- `0x1800ba98c`
- `0x1800bab6c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800066f3`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800066f3`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800066ad`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800067bd`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006b06`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800066ad`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800067bd`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006b06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006849`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800068ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006849`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800068ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069af`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800064fb`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800064fb`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180006773`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180006773`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180006c9a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180006ca5`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180006cb0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180006cc6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180006c9a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180006ca5`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180006cb0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180006cc6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180006337`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180006337`
- `DNSAPI!DnsFreeProxyName` at `0x180006cbb`
- `DNSAPI!DnsFreeProxyName` at `0x180006cbb`
- `DNSAPI!DnsGetProxyInformation` at `0x180006ae7`
- `DNSAPI!DnsGetProxyInformation` at `0x180006ae7`
- `WINHTTP!WinHttpGetProxyForUrlEx` at `0x180006a37`
- `WINHTTP!WinHttpGetProxyForUrlEx` at `0x180006a37`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800069a3`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800069a3`
- `WINHTTP!WinHttpOpen` at `0x180006836`
- `WINHTTP!WinHttpOpen` at `0x180006836`
- `WINHTTP!WinHttpCreateProxyResolver` at `0x18000691d`
- `WINHTTP!WinHttpCreateProxyResolver` at `0x18000691d`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18000673c`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18000673c`
- `WINHTTP!WinHttpCloseHandle` at `0x180006959`
- `WINHTTP!WinHttpCloseHandle` at `0x1800069e5`
- `WINHTTP!WinHttpCloseHandle` at `0x1800069ef`
- `WINHTTP!WinHttpCloseHandle` at `0x180006a4e`
- `WINHTTP!WinHttpCloseHandle` at `0x180006a58`
- `WINHTTP!WinHttpCloseHandle` at `0x180006959`
- `WINHTTP!WinHttpCloseHandle` at `0x1800069e5`
- `WINHTTP!WinHttpCloseHandle` at `0x1800069ef`
- `WINHTTP!WinHttpCloseHandle` at `0x180006a4e`
- `WINHTTP!WinHttpCloseHandle` at `0x180006a58`
- `fwbase!FwHResultToWindowsError` at `0x18000621f`
- `fwbase!FwHResultToWindowsError` at `0x18000621f`
- `fwbase!FwAlloc` at `0x1800062a1`
- `fwbase!FwAlloc` at `0x1800062a1`
- `fwbase!FwCriticalSectionLeave` at `0x18000630b`
- `fwbase!FwCriticalSectionLeave` at `0x180006494`
- `fwbase!FwCriticalSectionLeave` at `0x18000630b`
- `fwbase!FwCriticalSectionLeave` at `0x180006494`

## pseudocode

```c
__int64 FwMoneisDiagOperationGetEnterpriseId()
{
  DWORD_PTR v0; // rdi
  int v1; // r13d
  unsigned int v2; // eax
  DWORD v3; // eax
  int v4; // eax
  _QWORD *v5; // rsi
  __int64 v6; // rax
  int v7; // r14d
  __int64 v8; // rax
  __int64 v9; // rcx
  unsigned int v10; // eax
  __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // r15d
  const char *v15; // r12
  _QWORD *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rdx
  _QWORD *v19; // rbx
  __int64 v20; // rcx
  const char **v21; // rax
  const char *v22; // r8
  __int64 v23; // rdx
  __int64 v24; // r9
  __int64 v25; // rcx
  size_t v26; // rbx
  const WCHAR *v27; // rax
  HINTERNET v28; // rax
  DWORD LastError; // eax
  HINTERNET *v30; // rbx
  DWORD ProxyResolver; // eax
  DWORD v32; // eax
  const WCHAR *proxyName; // r15
  DWORD v34; // eax
  int v35; // r8d
  int v36; // r8d
  _QWORD *v37; // rbx
  const char **v38; // rax
  int v39; // [rsp+30h] [rbp-59h]
  int v40; // [rsp+34h] [rbp-55h]
  WINHTTP_AUTOPROXY_OPTIONS pAutoProxyOptions; // [rsp+38h] [rbp-51h] BYREF
  DNS_PROXY_INFORMATION proxyInformation; // [rsp+58h] [rbp-31h] BYREF
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig; // [rsp+68h] [rbp-21h] BYREF
  DWORD Reply; // [rsp+88h] [rbp-1h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 91, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids);
  v0 = 0;
  memset(&pAutoProxyOptions, 0, sizeof(pAutoProxyOptions));
  v1 = 0;
  memset(&pProxyConfig, 0, sizeof(pProxyConfig));
  proxyInformation = 0;
  v2 = FwAcquireRPCSharedLock("FwMoneisDiagOperationGetEnterpriseId");
  v3 = FwHResultToWindowsError(v2);
  Reply = v3;
  if ( v3 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_Ds(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        92,
        (unsigned int)WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids,
        v3,
        (__int64)"FwAcquireRPCSharedLock");
    goto LABEL_35;
  }
  v39 = 0;
  v40 = 0;
  v4 = EdpFieldsLock();
  if ( v4 < 0 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_15;
    v18 = 93;
LABEL_56:
    WPP_SF_d(*(_QWORD *)(v17 + 16), v18, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids, (unsigned int)v4);
    goto LABEL_15;
  }
  v5 = (_QWORD *)qword_18012C720;
  if ( *(__int64 **)(qword_18012C720 + 8) != &qword_18012C720
    || (v6 = *(_QWORD *)qword_18012C720, *(_QWORD *)(*(_QWORD *)qword_18012C720 + 8LL) != qword_18012C720) )
  {
LABEL_164:
    __fastfail(3u);
  }
  qword_18012C720 = *(_QWORD *)qword_18012C720;
  v0 = (DWORD_PTR)(v5 - 5);
  *(_QWORD *)(v6 + 8) = &qword_18012C720;
  v7 = 0;
  if ( qword_18012C7C0 )
    LOBYTE(v7) = *(_WORD *)qword_18012C7C0 != 0;
  *(_DWORD *)(v0 + 120) = dword_18012C7D8 != 0;
  v8 = FwAlloc(600);
  *(_QWORD *)(v0 + 112) = v8;
  if ( !v8 )
  {
    v12 = 14;
    Reply = 14;
    v9 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_14;
    v13 = 94;
LABEL_58:
    WPP_SF_d(*(_QWORD *)(v9 + 16), v13, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids, v12);
    goto LABEL_14;
  }
  v39 = dword_18012C7E8;
  v40 = dword_18012C7F8;
  if ( (*(_BYTE *)(v0 + 16) & 4) == 0 && !dword_18012C7E8 && !dword_18012C7F8 )
  {
    Reply = 0;
    v9 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_14;
    v13 = 95;
    v12 = 0;
    goto LABEL_58;
  }
  v14 = dword_18012C804;
  FwCriticalSectionLeave(qword_18012C740);
  v15 = L"<null>";
  if ( *(_DWORD *)(v0 + 120) && v14 )
  {
    if ( (unsigned int)FwMoneisDiagIsServerInPolicy(*(LPCWSTR *)(v0 + 8)) )
    {
      v19 = *(_QWORD **)(v0 + 32);
      *v19 = FwMoneisGetEnterpriseIdReference();
      v1 = 1;
      **(_DWORD **)(v0 + 24) = 1;
    }
    v20 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      v21 = *(const char ***)(v0 + 32);
      v22 = L"<null>";
      if ( *v21 )
        v22 = *v21;
      WPP_SF_SdS(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 96, (_DWORD)v22, *(_QWORD *)(v0 + 8), v1, (__int64)v22);
      v20 = WPP_GLOBAL_Control;
    }
    if ( v1 == 1 )
    {
      Reply = 0;
      if ( (_UNKNOWN *)v20 != &WPP_GLOBAL_Control && (*(_BYTE *)(v20 + 28) & 1) != 0 )
      {
        v23 = 97;
LABEL_71:
        v24 = 0;
LABEL_72:
        WPP_SF_d(*(_QWORD *)(v20 + 16), v23, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids, v24);
        goto LABEL_15;
      }
      goto LABEL_15;
    }
  }
  if ( v7 )
  {
    if ( !v14 )
      goto LABEL_135;
    v25 = *(_QWORD *)(v0 + 112);
    if ( v25 )
    {
      if ( (unsigned int)_o_wcscpy_s(v25, 300, L"https://") )
      {
        v24 = 14;
        Reply = 14;
        v20 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v23 = 98;
          goto LABEL_72;
        }
        goto LABEL_15;
      }
      if ( (unsigned int)_o_wcscat_s(*(_QWORD *)(v0 + 112), 300, *(_QWORD *)(v0 + 8)) )
      {
        v24 = 14;
        Reply = 14;
        v20 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v23 = 99;
          goto LABEL_72;
        }
        goto LABEL_15;
      }
    }
    pAutoProxyOptions.dwFlags = 1536;
    if ( WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig) )
    {
      if ( pProxyConfig.lpszAutoConfigUrl )
      {
        pAutoProxyOptions.dwFlags |= 0x100u;
        v26 = wcsnlen_s(pProxyConfig.lpszAutoConfigUrl, 0x7FFFFFFFu) + 1;
        v27 = (const WCHAR *)GlobalAlloc(0x40u, 2 * v26);
        pAutoProxyOptions.lpszAutoConfigUrl = v27;
        if ( !v27 )
        {
          v24 = 14;
          Reply = 14;
          v20 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v23 = 100;
            goto LABEL_72;
          }
          goto LABEL_15;
        }
        if ( (unsigned int)_o_wcscpy_s(v27, v26, pProxyConfig.lpszAutoConfigUrl) )
        {
          v24 = 14;
          Reply = 14;
          v20 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v23 = 101;
            goto LABEL_72;
          }
          goto LABEL_15;
        }
      }
      if ( pProxyConfig.fAutoDetect )
      {
        pAutoProxyOptions.dwFlags |= 1u;
        pAutoProxyOptions.dwAutoDetectFlags = 3;
      }
    }
    else
    {
      LastError = GetLastError();
      Reply = LastError;
      v20 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          102,
          WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids,
          LastError);
        LastError = Reply;
        v20 = WPP_GLOBAL_Control;
      }
      if ( LastError )
      {
        if ( (_UNKNOWN *)v20 == &WPP_GLOBAL_Control || (*(_BYTE *)(v20 + 28) & 1) == 0 )
          goto LABEL_15;
        v23 = 103;
        goto LABEL_103;
      }
    }
    pAutoProxyOptions.lpvReserved = 0;
    *(_QWORD *)&pAutoProxyOptions.dwReserved = 0;
    v28 = WinHttpOpen(L"Mpssvc Proxy Detection", 4u, 0, 0, 0x10000000u);
    *(_QWORD *)(v0 + 80) = v28;
    if ( v28 )
      goto LABEL_111;
    LastError = GetLastError();
    Reply = LastError;
    v20 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 104, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids, LastError);
      LastError = Reply;
      v20 = WPP_GLOBAL_Control;
    }
    if ( !LastError )
    {
LABEL_111:
      v30 = (HINTERNET *)(v0 + 72);
      ProxyResolver = WinHttpCreateProxyResolver(*(HINTERNET *)(v0 + 80), (HINTERNET *)(v0 + 72));
      Reply = ProxyResolver;
      if ( *(_QWORD *)(v0 + 72) )
        goto LABEL_167;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          106,
          WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids,
          ProxyResolver);
      WinHttpCloseHandle(*(HINTERNET *)(v0 + 80));
      *(_QWORD *)(v0 + 80) = 0;
      v24 = Reply;
      if ( !Reply )
      {
LABEL_167:
        if ( WinHttpSetStatusCallback(*v30, GetProxyForUrlCallback, 0x1200000u, 0) != (WINHTTP_STATUS_CALLBACK)-1LL )
          goto LABEL_127;
        v32 = GetLastError();
        Reply = v32;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 108, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids, v32);
        WinHttpCloseHandle(*v30);
        WinHttpCloseHandle(*(HINTERNET *)(v0 + 80));
        *v30 = 0;
        *(_QWORD *)(v0 + 80) = 0;
        v24 = Reply;
        if ( Reply )
        {
          v20 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v23 = 109;
            goto LABEL_72;
          }
        }
        else
        {
LABEL_127:
          Reply = WinHttpGetProxyForUrlEx(*v30, *(PCWSTR *)(v0 + 112), &pAutoProxyOptions, v0);
          if ( Reply != 997 )
          {
            WinHttpCloseHandle(*v30);
            WinHttpCloseHandle(*(HINTERNET *)(v0 + 80));
            *v30 = 0;
            *(_QWORD *)(v0 + 80) = 0;
            v20 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                110,
                WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids,
                Reply);
              v20 = WPP_GLOBAL_Control;
            }
            v24 = Reply;
            if ( Reply )
            {
              if ( (_UNKNOWN *)v20 != &WPP_GLOBAL_Control && (*(_BYTE *)(v20 + 28) & 1) != 0 )
              {
                v23 = 111;
                goto LABEL_72;
              }
            }
          }
        }
      }
      else
      {
        v20 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v23 = 107;
          goto LABEL_72;
        }
      }
      goto LABEL_15;
    }
    if ( (_UNKNOWN *)v20 == &WPP_GLOBAL_Control || (*(_BYTE *)(v20 + 28) & 1) == 0 )
      goto LABEL_15;
    v23 = 105;
LABEL_103:
    v24 = LastError;
    goto LABEL_72;
  }
  if ( v14 )
    goto LABEL_15;
LABEL_135:
  proxyName = *(const WCHAR **)(v0 + 8);
  if ( v7 )
  {
    proxyInformation.version = 1;
    v34 = DnsGetProxyInformation(*(PCWSTR *)(v0 + 8), &proxyInformation, 0, 0, 0);
    Reply = v34;
    if ( proxyInformation.proxyInformationType == DNS_PROXY_INFORMATION_PROXY_NAME )
    {
      proxyName = proxyInformation.proxyName;
      if ( (unsigned int)_o_wcscpy_s(*(_QWORD *)(v0 + 112), 300, proxyInformation.proxyName) )
      {
        Reply = 14;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 112, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids, 14);
        goto LABEL_15;
      }
      LOBYTE(v34) = Reply;
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_SSD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 113, v35, *(_QWORD *)(v0 + 8), (__int64)proxyName, v34);
  }
  if ( !*(_DWORD *)(v0 + 120) )
    goto LABEL_157;
  if ( (unsigned int)FwMoneisDiagIsServerInPolicy(proxyName) )
  {
    v37 = *(_QWORD **)(v0 + 32);
    *v37 = FwMoneisGetEnterpriseIdReference();
    v1 = 1;
    **(_DWORD **)(v0 + 24) = 1;
  }
  v20 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
  {
    v38 = *(const char ***)(v0 + 32);
    if ( *v38 )
      v15 = *v38;
    WPP_SF_SdS(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 114, v36, (_DWORD)proxyName, v1, (__int64)v15);
    v20 = WPP_GLOBAL_Control;
  }
  if ( v1 != 1 )
  {
LABEL_157:
    v4 = EdpFieldsLock();
    if ( v4 < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_15;
      v18 = 116;
      goto LABEL_56;
    }
    v16 = (_QWORD *)qword_18012C738;
    if ( *(__int64 **)qword_18012C738 == &qword_18012C730 )
    {
      *v5 = &qword_18012C730;
      v5[1] = v16;
      *v16 = v5;
      qword_18012C738 = (__int64)v5;
      SubmitThreadpoolWork(pwk);
      Reply = 997;
LABEL_14:
      FwCriticalSectionLeave(qword_18012C740);
      goto LABEL_15;
    }
    goto LABEL_164;
  }
  Reply = 0;
  if ( (_UNKNOWN *)v20 != &WPP_GLOBAL_Control && (*(_BYTE *)(v20 + 28) & 1) != 0 )
  {
    v23 = 115;
    goto LABEL_71;
  }
LABEL_15:
  FwReleaseRPCSharedLock("FwMoneisDiagOperationGetEnterpriseId");
  if ( v39 || v40 )
  {
LABEL_16:
    if ( !v1 && (!Reply || Reply == 997) )
      goto LABEL_19;
    goto LABEL_17;
  }
LABEL_35:
  if ( Reply == 997 )
    goto LABEL_16;
LABEL_17:
  v10 = RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)v0, &Reply);
  if ( v10 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 117, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids, v10);
  FwMoneisDiagCleanupOpList(v0, 0, 0);
LABEL_19:
  if ( pProxyConfig.lpszProxy )
    GlobalFree(pProxyConfig.lpszProxy);
  if ( pProxyConfig.lpszAutoConfigUrl )
    GlobalFree(pProxyConfig.lpszAutoConfigUrl);
  if ( pProxyConfig.lpszProxyBypass )
    GlobalFree(pProxyConfig.lpszProxyBypass);
  if ( proxyInformation.proxyName )
    DnsFreeProxyName(proxyInformation.proxyName);
  if ( pAutoProxyOptions.lpszAutoConfigUrl )
    GlobalFree((HGLOBAL)pAutoProxyOptions.lpszAutoConfigUrl);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 118, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids);
  return Reply;
}

```

## disassembly

```asm
0x1800061ac  push    rbp
0x1800061ae  push    rbx
0x1800061af  push    rsi
0x1800061b0  push    rdi
0x1800061b1  push    r12
0x1800061b3  push    r13
0x1800061b5  push    r14
0x1800061b7  push    r15
0x1800061b9  lea     rbp, [rsp-1Fh]
0x1800061be  sub     rsp, 0A8h
0x1800061c5  mov     rax, cs:__security_cookie
0x1800061cc  xor     rax, rsp
0x1800061cf  mov     [rbp+57h+var_50], rax
0x1800061d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800061da  lea     r14, WPP_GLOBAL_Control
0x1800061e1  cmp     rcx, r14
0x1800061e4  jnz     loc_180006462
0x1800061ea  xorps   xmm0, xmm0
0x1800061ed  lea     rcx, aFwmoneisdiagop; "FwMoneisDiagOperationGetEnterpriseId"
0x1800061f4  xor     r12d, r12d
0x1800061f7  xorps   xmm1, xmm1
0x1800061fa  mov     [rbp+57h+Reply], r12d
0x1800061fe  mov     edi, r12d
0x180006201  movups  xmmword ptr [rbp+57h+pAutoProxyOptions.dwFlags], xmm0
0x180006205  mov     r13d, r12d
0x180006208  movups  xmmword ptr [rbp+57h+pAutoProxyOptions.lpvReserved], xmm0
0x18000620c  movups  xmmword ptr [rbp+57h+pProxyConfig.fAutoDetect], xmm1
0x180006210  movups  xmmword ptr [rbp+57h+pProxyConfig.lpszProxy], xmm1
0x180006214  movups  xmmword ptr [rbp+57h+proxyInformation.version], xmm0
0x180006218  call    FwAcquireRPCSharedLock
0x18000621d  mov     ecx, eax
0x18000621f  call    cs:__imp_FwHResultToWindowsError
0x180006225  mov     [rbp+57h+Reply], eax
0x180006228  test    eax, eax
0x18000622a  jnz     loc_18000650D
0x180006230  mov     [rbp+57h+var_B0], r12d
0x180006234  mov     [rbp+57h+var_AC], r12d
0x180006238  call    EdpFieldsLock
0x18000623d  test    eax, eax
0x18000623f  js      loc_180006550
0x180006245  mov     rsi, cs:qword_18012C720
0x18000624c  lea     rcx, qword_18012C720
0x180006253  cmp     [rsi+8], rcx
0x180006257  jnz     loc_180006CD1
0x18000625d  mov     rax, [rsi]
0x180006260  cmp     [rax+8], rsi
0x180006264  jnz     loc_180006CD1
0x18000626a  mov     cs:qword_18012C720, rax
0x180006271  lea     rdi, [rsi-28h]
0x180006275  mov     [rax+8], rcx
0x180006279  mov     r14d, r12d
0x18000627c  mov     rax, cs:qword_18012C7C0
0x180006283  test    rax, rax
0x180006286  jnz     loc_1800063C6
0x18000628c  cmp     cs:dword_18012C7D8, r12d
0x180006293  mov     eax, r12d
0x180006296  mov     ecx, 258h
0x18000629b  setnz   al
0x18000629e  mov     [rdi+78h], eax
0x1800062a1  call    cs:__imp_FwAlloc
0x1800062a7  mov     [rdi+70h], rax
0x1800062ab  test    rax, rax
0x1800062ae  jz      loc_18000640A
0x1800062b4  test    byte ptr [rdi+10h], 4
0x1800062b8  mov     r15d, cs:dword_18012C7E8
0x1800062bf  mov     ebx, cs:dword_18012C7F8
0x1800062c5  mov     [rbp+57h+var_B0], r15d
0x1800062c9  mov     [rbp+57h+var_AC], ebx
0x1800062cc  jnz     loc_180006486
0x1800062d2  test    r15d, r15d
0x1800062d5  jnz     loc_180006486
0x1800062db  test    ebx, ebx
0x1800062dd  jnz     loc_180006486
0x1800062e3  mov     [rbp+57h+Reply], r12d
0x1800062e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062ee  lea     r14, WPP_GLOBAL_Control
0x1800062f5  cmp     rcx, r14
0x1800062f8  jz      short loc_180006304
0x1800062fa  test    byte ptr [rcx+1Ch], 1
0x1800062fe  jnz     loc_18000658E
0x180006304  lea     rcx, qword_18012C740
0x18000630b  call    cs:__imp_FwCriticalSectionLeave
0x180006311  lea     rcx, aFwmoneisdiagop; "FwMoneisDiagOperationGetEnterpriseId"
0x180006318  call    FwReleaseRPCSharedLock
0x18000631d  cmp     [rbp+57h+var_B0], r12d
0x180006321  jz      loc_1800063EE
0x180006327  test    r13d, r13d
0x18000632a  jz      loc_1800063D3
0x180006330  mov     rcx, [rdi]; pAsync
0x180006333  lea     rdx, [rbp+57h+Reply]; Reply
0x180006337  call    cs:__imp_RpcAsyncCompleteCall
0x18000633d  test    eax, eax
0x18000633f  jnz     loc_180006C63
0x180006345  xor     r8d, r8d
0x180006348  xor     edx, edx
0x18000634a  mov     rcx, rdi
0x18000634d  call    FwMoneisDiagCleanupOpList
0x180006352  mov     rcx, [rbp+57h+pProxyConfig.lpszProxy]; hMem
0x180006356  test    rcx, rcx
0x180006359  jnz     loc_180006C9A
0x18000635f  mov     rcx, [rbp+57h+pProxyConfig.lpszAutoConfigUrl]; hMem
0x180006363  test    rcx, rcx
0x180006366  jnz     loc_180006CA5
0x18000636c  mov     rcx, [rbp+57h+pProxyConfig.lpszProxyBypass]; hMem
0x180006370  test    rcx, rcx
0x180006373  jnz     loc_180006CB0
0x180006379  mov     rcx, [rbp+57h+proxyInformation.proxyName]; proxyName
0x18000637d  test    rcx, rcx
0x180006380  jnz     loc_180006CBB
0x180006386  mov     rcx, [rbp+57h+pAutoProxyOptions.lpszAutoConfigUrl]; hMem
0x18000638a  test    rcx, rcx
0x18000638d  jnz     loc_180006CC6
0x180006393  mov     rcx, cs:WPP_GLOBAL_Control
0x18000639a  cmp     rcx, r14
0x18000639d  jnz     loc_18000643E
0x1800063a3  mov     eax, [rbp+57h+Reply]
0x1800063a6  mov     rcx, [rbp+57h+var_50]
0x1800063aa  xor     rcx, rsp; StackCookie
0x1800063ad  call    __security_check_cookie
0x1800063b2  add     rsp, 0A8h
0x1800063b9  pop     r15
0x1800063bb  pop     r14
0x1800063bd  pop     r13
0x1800063bf  pop     r12
0x1800063c1  pop     rdi
0x1800063c2  pop     rsi
0x1800063c3  pop     rbx
0x1800063c4  pop     rbp
0x1800063c5  retn
0x1800063c6  cmp     [rax], r12w
0x1800063ca  setnz   r14b
0x1800063ce  jmp     loc_18000628C
0x1800063d3  mov     eax, [rbp+57h+Reply]
0x1800063d6  test    eax, eax
0x1800063d8  jz      loc_180006352
0x1800063de  cmp     eax, 3E5h
0x1800063e3  jz      loc_180006352
0x1800063e9  jmp     loc_180006330
0x1800063ee  cmp     [rbp+57h+var_AC], r12d
0x1800063f2  jnz     loc_180006327
0x1800063f8  cmp     [rbp+57h+Reply], 3E5h
0x1800063ff  jnz     loc_180006330
0x180006405  jmp     loc_180006327
0x18000640a  mov     r9d, 0Eh
0x180006410  mov     [rbp+57h+Reply], r9d
0x180006414  mov     rcx, cs:WPP_GLOBAL_Control
0x18000641b  lea     r14, WPP_GLOBAL_Control
0x180006422  cmp     rcx, r14
0x180006425  jz      loc_180006304
0x18000642b  test    byte ptr [rcx+1Ch], 1
0x18000642f  jz      loc_180006304
0x180006435  lea     edx, [r9+50h]
0x180006439  jmp     loc_180006596
0x18000643e  test    byte ptr [rcx+1Ch], 8
0x180006442  jz      loc_1800063A3
0x180006448  mov     rcx, [rcx+10h]
0x18000644c  lea     r8, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids
0x180006453  mov     edx, 76h ; 'v'
0x180006458  call    WPP_SF_
0x18000645d  jmp     loc_1800063A3
0x180006462  test    byte ptr [rcx+1Ch], 8
0x180006466  jz      loc_1800061EA
0x18000646c  mov     rcx, [rcx+10h]
0x180006470  lea     r8, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids
0x180006477  mov     edx, 5Bh ; '['
0x18000647c  call    WPP_SF_
0x180006481  jmp     loc_1800061EA
0x180006486  mov     r15d, cs:dword_18012C804
0x18000648d  lea     rcx, qword_18012C740
0x180006494  call    cs:__imp_FwCriticalSectionLeave
0x18000649a  lea     r12, aNull; "<null>"
0x1800064a1  cmp     [rdi+78h], r13d
0x1800064a5  jnz     loc_1800065AB
0x1800064ab  test    r14d, r14d
0x1800064ae  jnz     loc_180006686
0x1800064b4  test    r15d, r15d
0x1800064b7  jz      loc_180006ABC
0x1800064bd  lea     r14, WPP_GLOBAL_Control
0x1800064c4  xor     r12d, r12d
0x1800064c7  jmp     loc_180006311
0x1800064cc  mov     rax, cs:qword_18012C738
0x1800064d3  lea     rdx, qword_18012C730
0x1800064da  cmp     [rax], rdx
0x1800064dd  jnz     loc_180006CD1
0x1800064e3  mov     [rsi], rdx
0x1800064e6  mov     [rsi+8], rax
0x1800064ea  mov     [rax], rsi
0x1800064ed  mov     rcx, cs:pwk; pwk
0x1800064f4  mov     cs:qword_18012C738, rsi
0x1800064fb  call    cs:__imp_SubmitThreadpoolWork
0x180006501  mov     [rbp+57h+Reply], 3E5h
0x180006508  jmp     loc_180006304
0x18000650d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006514  cmp     rcx, r14
0x180006517  jz      loc_1800063F8
0x18000651d  test    byte ptr [rcx+1Ch], 1
0x180006521  jz      loc_1800063F8
0x180006527  mov     rcx, [rcx+10h]
0x18000652b  lea     r8, aFwacquirerpcsh; "FwAcquireRPCSharedLock"
0x180006532  mov     qword ptr [rsp+0E0h+dwFlags], r8
0x180006537  mov     edx, 5Ch ; '\'
0x18000653c  lea     r8, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids
0x180006543  mov     r9d, eax
0x180006546  call    WPP_SF_Ds
0x18000654b  jmp     loc_1800063F8
0x180006550  mov     rcx, cs:WPP_GLOBAL_Control
0x180006557  cmp     rcx, r14
0x18000655a  jz      loc_180006311
0x180006560  test    byte ptr [rcx+1Ch], 1
0x180006564  jz      loc_180006311
0x18000656a  mov     edx, 5Dh ; ']'
0x18000656f  jmp     short loc_180006576
0x180006571  mov     edx, 74h ; 't'
0x180006576  mov     rcx, [rcx+10h]
0x18000657a  lea     r8, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids
0x180006581  mov     r9d, eax
0x180006584  call    WPP_SF_d
0x180006589  jmp     loc_180006311
0x18000658e  mov     edx, 5Fh ; '_'
0x180006593  xor     r9d, r9d
0x180006596  mov     rcx, [rcx+10h]
0x18000659a  lea     r8, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids
0x1800065a1  call    WPP_SF_d
0x1800065a6  jmp     loc_180006304
0x1800065ab  test    r15d, r15d
0x1800065ae  jz      loc_1800064AB
0x1800065b4  mov     rcx, [rdi+8]; lpUnicodeCharStr
0x1800065b8  lea     r8, dword_18012C7D8
0x1800065bf  xor     edx, edx
0x1800065c1  call    FwMoneisDiagIsServerInPolicy
0x1800065c6  test    eax, eax
0x1800065c8  jz      short loc_1800065E6
0x1800065ca  mov     rbx, [rdi+20h]
0x1800065ce  call    FwMoneisGetEnterpriseIdReference
0x1800065d3  mov     [rbx], rax
0x1800065d6  mov     r13d, 1
0x1800065dc  mov     rax, [rdi+18h]
0x1800065e0  mov     dword ptr [rax], 1
0x1800065e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800065ed  lea     rax, WPP_GLOBAL_Control
0x1800065f4  cmp     rcx, rax
0x1800065f7  jz      short loc_180006631
0x1800065f9  test    byte ptr [rcx+1Ch], 4
0x1800065fd  jz      short loc_180006631
0x1800065ff  mov     rax, [rdi+20h]
0x180006603  mov     r8, r12
0x180006606  mov     r9, [rdi+8]
0x18000660a  mov     edx, 60h ; '`'
0x18000660f  mov     rcx, [rcx+10h]
0x180006613  cmp     qword ptr [rax], 0
0x180006617  cmovnz  r8, [rax]
0x18000661b  mov     [rsp+0E0h+var_B8], r8
0x180006620  mov     [rsp+0E0h+dwFlags], r13d
0x180006625  call    WPP_SF_SdS
0x18000662a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006631  cmp     r13d, 1
0x180006635  jnz     loc_1800064AB
0x18000663b  xor     r12d, r12d
0x18000663e  mov     [rbp+57h+Reply], r12d
0x180006642  lea     r14, WPP_GLOBAL_Control
0x180006649  cmp     rcx, r14
0x18000664c  jz      loc_180006311
0x180006652  test    [rcx+1Ch], r13b
0x180006656  jz      loc_180006311
0x18000665c  lea     edx, [r13+60h]
0x180006660  jmp     short loc_180006667
0x180006662  mov     edx, 73h ; 's'
0x180006667  xor     r9d, r9d
0x18000666a  jmp     short loc_180006671
0x18000666c  mov     edx, 6Fh ; 'o'
0x180006671  mov     rcx, [rcx+10h]
0x180006675  lea     r8, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids
0x18000667c  call    WPP_SF_d
0x180006681  jmp     loc_180006311
0x180006686  test    r15d, r15d
0x180006689  jz      loc_180006ABC
0x18000668f  mov     rcx, [rdi+70h]
0x180006693  xor     r12d, r12d
0x180006696  test    rcx, rcx
0x180006699  jz      loc_180006731
0x18000669f  mov     ebx, 12Ch
0x1800066a4  lea     r8, aHttps; "https://"
0x1800066ab  mov     edx, ebx
0x1800066ad  call    cs:__imp__o_wcscpy_s
0x1800066b3  test    eax, eax
0x1800066b5  jz      short loc_1800066E8
0x1800066b7  lea     r9d, [r12+0Eh]
0x1800066bc  mov     [rbp+57h+Reply], r9d
0x1800066c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066c7  lea     r14, WPP_GLOBAL_Control
0x1800066ce  cmp     rcx, r14
0x1800066d1  jz      loc_180006311
0x1800066d7  test    byte ptr [rcx+1Ch], 1
0x1800066db  jz      loc_180006311
0x1800066e1  lea     edx, [r12+62h]
0x1800066e6  jmp     short loc_180006671
0x1800066e8  mov     r8, [rdi+8]
0x1800066ec  mov     rdx, rbx
0x1800066ef  mov     rcx, [rdi+70h]
0x1800066f3  call    cs:__imp__o_wcscat_s
  ... truncated ...
```
