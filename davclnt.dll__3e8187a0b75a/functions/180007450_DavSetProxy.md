# DavSetProxy

- ea: `0x180007450`
- end: `0x1800079ab`
- name: `DavSetProxy`
- size: `1371`
- prototype: `unsigned int __fastcall(HINTERNET hInternet, HINTERNET, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006600`

## callees

- `0x180007450`
- `0x180009de0`
- `0x180010a14`
- `0x180010be8`
- `0x180010c28`
- `0x180010d00`
- `0x180011b40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007914`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007914`
- `KERNEL32!GlobalFree` at `0x180007616`
- `KERNEL32!GlobalFree` at `0x180007637`
- `KERNEL32!GlobalFree` at `0x18000794d`
- `KERNEL32!GlobalFree` at `0x18000795c`
- `KERNEL32!GlobalFree` at `0x180007974`
- `KERNEL32!GlobalFree` at `0x180007983`
- `KERNEL32!GlobalFree` at `0x180007616`
- `KERNEL32!GlobalFree` at `0x180007637`
- `KERNEL32!GlobalFree` at `0x18000794d`
- `KERNEL32!GlobalFree` at `0x18000795c`
- `KERNEL32!GlobalFree` at `0x180007974`
- `KERNEL32!GlobalFree` at `0x180007983`
- `KERNEL32!LocalFree` at `0x180007991`
- `KERNEL32!LocalFree` at `0x180007991`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800074e8`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800074e8`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x1800075b7`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x1800075b7`
- `WINHTTP!WinHttpSetOption` at `0x1800078be`
- `WINHTTP!WinHttpSetOption` at `0x18000790a`
- `WINHTTP!WinHttpSetOption` at `0x1800078be`
- `WINHTTP!WinHttpSetOption` at `0x18000790a`

## pseudocode

```c
unsigned int __fastcall DavSetProxy(HINTERNET hInternet, HINTERNET a2, __int64 a3)
{
  BOOL ProxyForUrl; // esi
  int v5; // r13d
  WCHAR *PathFromRequest; // rdi
  __int64 v9; // rbx
  DWORD LastError; // eax
  const WCHAR *lpszAutoConfigUrl; // rax
  _QWORD *v12; // r10
  DWORD v13; // eax
  __int64 v14; // rdx
  WCHAR *v15; // rbx
  WCHAR v16; // cx
  __int64 v17; // rcx
  WCHAR v18; // ax
  WCHAR *v19; // rcx
  unsigned int v20; // edx
  WCHAR v21; // ax
  LPWSTR lpszProxyBypass; // rax
  DWORD v23; // eax
  unsigned int result; // eax
  WINHTTP_PROXY_INFO pProxyInfo; // [rsp+30h] [rbp-49h] BYREF
  WINHTTP_AUTOPROXY_OPTIONS pAutoProxyOptions; // [rsp+48h] [rbp-31h] BYREF
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig; // [rsp+68h] [rbp-11h] BYREF

  memset(&pProxyInfo, 0, sizeof(pProxyInfo));
  ProxyForUrl = 0;
  v5 = 0;
  memset(&pAutoProxyOptions, 0, sizeof(pAutoProxyOptions));
  memset(&pProxyConfig, 0, sizeof(pProxyConfig));
  PathFromRequest = (WCHAR *)DavQueryPathFromRequest(a2);
  if ( !PathFromRequest
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v9 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    LastError = GetLastError();
    WPP_SF_d(v9, 16, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids, LastError);
  }
  if ( !WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig) )
    goto LABEL_32;
  lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
  if ( !pProxyConfig.fAutoDetect && !pProxyConfig.lpszAutoConfigUrl )
    goto LABEL_26;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids);
    lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
    v12 = WPP_GLOBAL_Control;
  }
  pAutoProxyOptions.fAutoLogonIfChallenged = 1;
  if ( lpszAutoConfigUrl )
  {
    *(_QWORD *)&pAutoProxyOptions.dwFlags = 65538;
    pAutoProxyOptions.lpszAutoConfigUrl = lpszAutoConfigUrl;
  }
  else
  {
    pAutoProxyOptions.dwFlags = 65537;
    pAutoProxyOptions.lpszAutoConfigUrl = 0;
    pAutoProxyOptions.dwAutoDetectFlags = 3;
  }
  pAutoProxyOptions.lpvReserved = 0;
  pAutoProxyOptions.dwReserved = 0;
  if ( !PathFromRequest )
    goto LABEL_27;
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
    WPP_SF_S(v12[2], 18, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids, PathFromRequest);
  ProxyForUrl = WinHttpGetProxyForUrl(hInternet, PathFromRequest, &pAutoProxyOptions, &pProxyInfo);
  if ( ProxyForUrl )
  {
LABEL_32:
    v12 = WPP_GLOBAL_Control;
    goto LABEL_33;
  }
  v13 = GetLastError();
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids, v13);
    v12 = WPP_GLOBAL_Control;
  }
  if ( pProxyInfo.lpszProxy )
  {
    GlobalFree(pProxyInfo.lpszProxy);
    v12 = WPP_GLOBAL_Control;
    pProxyInfo.lpszProxy = 0;
  }
  if ( !pProxyInfo.lpszProxyBypass )
    goto LABEL_27;
  GlobalFree(pProxyInfo.lpszProxyBypass);
  pProxyInfo.lpszProxyBypass = 0;
LABEL_26:
  v12 = WPP_GLOBAL_Control;
LABEL_27:
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
  {
    WPP_SF_(v12[2], 20, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids);
    v12 = WPP_GLOBAL_Control;
  }
  if ( pProxyConfig.lpszProxy )
  {
    pProxyInfo.lpszProxy = pProxyConfig.lpszProxy;
    pProxyInfo.lpszProxyBypass = pProxyConfig.lpszProxyBypass;
    pProxyInfo.dwAccessType = 3;
  }
LABEL_33:
  if ( pProxyInfo.lpszProxy )
  {
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
    {
      lpszProxyBypass = L"NULL";
      if ( pProxyInfo.lpszProxyBypass )
        lpszProxyBypass = pProxyInfo.lpszProxyBypass;
      WPP_SF_SS(
        v12[2],
        25,
        (unsigned int)WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids,
        pProxyInfo.lpszProxy,
        (__int64)lpszProxyBypass);
    }
  }
  else
  {
    v14 = 0;
    v15 = PathFromRequest;
    if ( PathFromRequest )
    {
      while ( 1 )
      {
        v16 = PathFromRequest[v14];
        if ( !v16 )
          break;
        if ( v16 == 47 && PathFromRequest[(unsigned int)(v14 + 1)] == 47 )
        {
          v15 = &PathFromRequest[(unsigned int)(v14 + 2)];
          break;
        }
        v14 = (unsigned int)(v14 + 1);
      }
    }
    v17 = 0;
    if ( v15 )
    {
      while ( 1 )
      {
        v18 = v15[v17];
        if ( !v18 )
          break;
        if ( v18 == 58 || v18 == 47 )
        {
          v15[v17] = 0;
          v12 = WPP_GLOBAL_Control;
          break;
        }
        v17 = (unsigned int)(v17 + 1);
      }
    }
    if ( ProxyForUrl )
    {
      pProxyInfo.dwAccessType = 3;
      pProxyInfo.lpszProxy = L"none";
      if ( PathFromRequest && v15 )
      {
        pProxyInfo.lpszProxyBypass = v15;
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
          WPP_SF_S(v12[2], 22, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids, v15);
      }
      else
      {
        pProxyInfo.lpszProxyBypass = L"<local>";
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
          WPP_SF_(v12[2], 21, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids);
      }
      v5 = 1;
    }
    else
    {
      pProxyInfo.dwAccessType = 1;
      if ( PathFromRequest )
      {
        v19 = PathFromRequest;
        v20 = 0;
        while ( 1 )
        {
          v21 = *v19;
          if ( !*v19 || v20 >= 3 )
            break;
          switch ( v21 )
          {
            case '/':
              goto LABEL_63;
            case '.':
              goto LABEL_69;
            case '\\':
LABEL_63:
              ++v20;
              break;
          }
          ++v19;
        }
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
          WPP_SF_(v12[2], 23, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids);
        pProxyInfo.dwAccessType = 3;
        pProxyInfo.lpszProxy = L"none";
        pProxyInfo.lpszProxyBypass = L"<local>";
      }
      else
      {
LABEL_69:
        if ( (unsigned int)DavIsHostInAdminBypassList(a3, PathFromRequest) )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids, v15);
          pProxyInfo.dwAccessType = 3;
          pProxyInfo.lpszProxy = L"none";
          pProxyInfo.lpszProxyBypass = v15;
        }
      }
    }
  }
  if ( !WinHttpSetOption(hInternet, 0x26u, &pProxyInfo, 0x18u) )
  {
    v23 = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids, v23);
  }
  result = WinHttpSetOption(a2, 0x26u, &pProxyInfo, 0x18u);
  if ( !result )
  {
    result = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      result = WPP_SF_d(
                 *((_QWORD *)WPP_GLOBAL_Control + 2),
                 27,
                 WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids,
                 result);
  }
  if ( pProxyConfig.lpszProxy )
    result = (unsigned int)GlobalFree(pProxyConfig.lpszProxy);
  if ( pProxyConfig.lpszProxyBypass )
    result = (unsigned int)GlobalFree(pProxyConfig.lpszProxyBypass);
  if ( ProxyForUrl && !v5 )
  {
    if ( pProxyInfo.lpszProxy )
      result = (unsigned int)GlobalFree(pProxyInfo.lpszProxy);
    if ( pProxyInfo.lpszProxyBypass )
      result = (unsigned int)GlobalFree(pProxyInfo.lpszProxyBypass);
  }
  if ( PathFromRequest )
    return (unsigned int)LocalFree(PathFromRequest);
  return result;
}

```

## disassembly

```asm
0x180007450  push    rbp
0x180007452  push    rbx
0x180007453  push    rsi
0x180007454  push    rdi
0x180007455  push    r12
0x180007457  push    r13
0x180007459  push    r14
0x18000745b  push    r15
0x18000745d  lea     rbp, [rsp-1Fh]
0x180007462  sub     rsp, 98h
0x180007469  xorps   xmm0, xmm0
0x18000746c  xor     ebx, ebx
0x18000746e  xorps   xmm1, xmm1
0x180007471  mov     qword ptr [rbp+57h+pProxyInfo.dwAccessType], rbx
0x180007475  mov     r15, rcx
0x180007478  mov     esi, ebx
0x18000747a  mov     rcx, rdx; hInternet
0x18000747d  mov     r13d, ebx
0x180007480  movups  xmmword ptr [rbp+57h+pAutoProxyOptions.dwFlags], xmm0
0x180007484  mov     r12, r8
0x180007487  mov     r14, rdx
0x18000748a  movups  xmmword ptr [rbp+57h+pAutoProxyOptions.lpvReserved], xmm0
0x18000748e  movups  xmmword ptr [rbp+57h+pProxyConfig.fAutoDetect], xmm1
0x180007492  movups  xmmword ptr [rbp+57h+pProxyConfig.lpszProxy], xmm1
0x180007496  movdqu  xmmword ptr [rbp+57h+pProxyInfo.lpszProxy], xmm0
0x18000749b  call    DavQueryPathFromRequest
0x1800074a0  mov     rdi, rax
0x1800074a3  lea     rax, WPP_GLOBAL_Control
0x1800074aa  test    rdi, rdi
0x1800074ad  jnz     short loc_1800074E4
0x1800074af  mov     rbx, cs:WPP_GLOBAL_Control
0x1800074b6  cmp     rbx, rax
0x1800074b9  jz      short loc_1800074E2
0x1800074bb  test    byte ptr [rbx+1Ch], 1
0x1800074bf  jz      short loc_1800074E2
0x1800074c1  mov     rbx, [rbx+10h]
0x1800074c5  call    cs:__imp_GetLastError
0x1800074cb  mov     edx, 10h
0x1800074d0  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x1800074d7  mov     r9d, eax
0x1800074da  mov     rcx, rbx
0x1800074dd  call    WPP_SF_d
0x1800074e2  xor     ebx, ebx
0x1800074e4  lea     rcx, [rbp+57h+pProxyConfig]; pProxyConfig
0x1800074e8  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x1800074ee  test    eax, eax
0x1800074f0  jz      loc_18000769C
0x1800074f6  mov     rax, [rbp+57h+pProxyConfig.lpszAutoConfigUrl]
0x1800074fa  cmp     [rbp+57h+pProxyConfig.fAutoDetect], esi
0x1800074fd  jnz     short loc_180007508
0x1800074ff  test    rax, rax
0x180007502  jz      loc_180007641
0x180007508  mov     r10, cs:WPP_GLOBAL_Control
0x18000750f  lea     r8, WPP_GLOBAL_Control
0x180007516  cmp     r10, r8
0x180007519  jz      short loc_180007549
0x18000751b  test    byte ptr [r10+1Ch], 2
0x180007520  jz      short loc_180007549
0x180007522  mov     rcx, [r10+10h]
0x180007526  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x18000752d  mov     edx, 11h
0x180007532  call    WPP_SF_
0x180007537  mov     rax, [rbp+57h+pProxyConfig.lpszAutoConfigUrl]
0x18000753b  lea     r8, WPP_GLOBAL_Control
0x180007542  mov     r10, cs:WPP_GLOBAL_Control
0x180007549  mov     [rbp+57h+pAutoProxyOptions.fAutoLogonIfChallenged], 1
0x180007550  test    rax, rax
0x180007553  jz      short loc_180007563
0x180007555  mov     qword ptr [rbp+57h+pAutoProxyOptions.dwFlags], 10002h
0x18000755d  mov     [rbp+57h+pAutoProxyOptions.lpszAutoConfigUrl], rax
0x180007561  jmp     short loc_180007575
0x180007563  mov     [rbp+57h+pAutoProxyOptions.dwFlags], 10001h
0x18000756a  mov     [rbp+57h+pAutoProxyOptions.lpszAutoConfigUrl], rbx
0x18000756e  mov     [rbp+57h+pAutoProxyOptions.dwAutoDetectFlags], 3
0x180007575  mov     [rbp+57h+pAutoProxyOptions.lpvReserved], rbx
0x180007579  mov     [rbp+57h+pAutoProxyOptions.dwReserved], ebx
0x18000757c  test    rdi, rdi
0x18000757f  jz      loc_18000764F
0x180007585  cmp     r10, r8
0x180007588  jz      short loc_1800075A9
0x18000758a  test    byte ptr [r10+1Ch], 2
0x18000758f  jz      short loc_1800075A9
0x180007591  mov     rcx, [r10+10h]
0x180007595  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x18000759c  mov     edx, 12h
0x1800075a1  mov     r9, rdi
0x1800075a4  call    WPP_SF_S
0x1800075a9  lea     r9, [rbp+57h+pProxyInfo]; pProxyInfo
0x1800075ad  mov     rdx, rdi; lpcwszUrl
0x1800075b0  lea     r8, [rbp+57h+pAutoProxyOptions]; pAutoProxyOptions
0x1800075b4  mov     rcx, r15; hSession
0x1800075b7  call    cs:__imp_WinHttpGetProxyForUrl
0x1800075bd  mov     esi, eax
0x1800075bf  test    eax, eax
0x1800075c1  jnz     loc_18000769C
0x1800075c7  call    cs:__imp_GetLastError
0x1800075cd  mov     r10, cs:WPP_GLOBAL_Control
0x1800075d4  lea     r8, WPP_GLOBAL_Control
0x1800075db  cmp     r10, r8
0x1800075de  jz      short loc_18000760D
0x1800075e0  test    byte ptr [r10+1Ch], 1
0x1800075e5  jz      short loc_18000760D
0x1800075e7  mov     rcx, [r10+10h]
0x1800075eb  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x1800075f2  mov     edx, 13h
0x1800075f7  mov     r9d, eax
0x1800075fa  call    WPP_SF_d
0x1800075ff  mov     r10, cs:WPP_GLOBAL_Control
0x180007606  lea     r8, WPP_GLOBAL_Control
0x18000760d  mov     rcx, [rbp+57h+pProxyInfo.lpszProxy]; hMem
0x180007611  test    rcx, rcx
0x180007614  jz      short loc_18000762E
0x180007616  call    cs:__imp_GlobalFree
0x18000761c  mov     r10, cs:WPP_GLOBAL_Control
0x180007623  lea     r8, WPP_GLOBAL_Control
0x18000762a  mov     [rbp+57h+pProxyInfo.lpszProxy], rbx
0x18000762e  mov     rcx, [rbp+57h+pProxyInfo.lpszProxyBypass]; hMem
0x180007632  test    rcx, rcx
0x180007635  jz      short loc_18000764F
0x180007637  call    cs:__imp_GlobalFree
0x18000763d  mov     [rbp+57h+pProxyInfo.lpszProxyBypass], rbx
0x180007641  mov     r10, cs:WPP_GLOBAL_Control
0x180007648  lea     r8, WPP_GLOBAL_Control
0x18000764f  cmp     r10, r8
0x180007652  jz      short loc_18000767E
0x180007654  test    byte ptr [r10+1Ch], 2
0x180007659  jz      short loc_18000767E
0x18000765b  mov     rcx, [r10+10h]
0x18000765f  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x180007666  mov     edx, 14h
0x18000766b  call    WPP_SF_
0x180007670  mov     r10, cs:WPP_GLOBAL_Control
0x180007677  lea     r8, WPP_GLOBAL_Control
0x18000767e  mov     rax, [rbp+57h+pProxyConfig.lpszProxy]
0x180007682  test    rax, rax
0x180007685  jz      short loc_1800076AA
0x180007687  mov     [rbp+57h+pProxyInfo.lpszProxy], rax
0x18000768b  mov     rax, [rbp+57h+pProxyConfig.lpszProxyBypass]
0x18000768f  mov     [rbp+57h+pProxyInfo.lpszProxyBypass], rax
0x180007693  mov     [rbp+57h+pProxyInfo.dwAccessType], 3
0x18000769a  jmp     short loc_1800076AA
0x18000769c  mov     r10, cs:WPP_GLOBAL_Control
0x1800076a3  lea     r8, WPP_GLOBAL_Control
0x1800076aa  cmp     [rbp+57h+pProxyInfo.lpszProxy], r13
0x1800076ae  jnz     loc_180007869
0x1800076b4  xor     edx, edx
0x1800076b6  mov     rbx, rdi
0x1800076b9  test    rdi, rdi
0x1800076bc  jz      short loc_1800076E1
0x1800076be  movzx   ecx, word ptr [rdi+rdx*2]
0x1800076c2  test    cx, cx
0x1800076c5  jz      short loc_1800076E1
0x1800076c7  cmp     cx, 2Fh ; '/'
0x1800076cb  jnz     short loc_1800076D6
0x1800076cd  lea     eax, [rdx+1]
0x1800076d0  cmp     [rdi+rax*2], cx
0x1800076d4  jz      short loc_1800076DA
0x1800076d6  inc     edx
0x1800076d8  jmp     short loc_1800076BE
0x1800076da  lea     eax, [rdx+2]
0x1800076dd  lea     rbx, [rdi+rax*2]
0x1800076e1  xor     ecx, ecx
0x1800076e3  test    rbx, rbx
0x1800076e6  jz      short loc_180007711
0x1800076e8  movzx   eax, word ptr [rbx+rcx*2]
0x1800076ec  lea     rdx, [rbx+rcx*2]
0x1800076f0  test    ax, ax
0x1800076f3  jz      short loc_180007711
0x1800076f5  cmp     ax, 3Ah ; ':'
0x1800076f9  jz      short loc_180007705
0x1800076fb  cmp     ax, 2Fh ; '/'
0x1800076ff  jz      short loc_180007705
0x180007701  inc     ecx
0x180007703  jmp     short loc_1800076E8
0x180007705  xor     eax, eax
0x180007707  mov     [rdx], ax
0x18000770a  mov     r10, cs:WPP_GLOBAL_Control
0x180007711  test    esi, esi
0x180007713  jz      short loc_180007792
0x180007715  mov     [rbp+57h+pProxyInfo.dwAccessType], 3
0x18000771c  lea     rax, aNone; "none"
0x180007723  mov     [rbp+57h+pProxyInfo.lpszProxy], rax
0x180007727  test    rdi, rdi
0x18000772a  jz      short loc_18000775B
0x18000772c  test    rbx, rbx
0x18000772f  jz      short loc_18000775B
0x180007731  mov     [rbp+57h+pProxyInfo.lpszProxyBypass], rbx
0x180007735  cmp     r10, r8
0x180007738  jz      short loc_180007787
0x18000773a  test    byte ptr [r10+1Ch], 2
0x18000773f  jz      short loc_180007787
0x180007741  mov     rcx, [r10+10h]
0x180007745  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x18000774c  mov     edx, 16h
0x180007751  mov     r9, rbx
0x180007754  call    WPP_SF_S
0x180007759  jmp     short loc_180007787
0x18000775b  lea     rax, aLocal; "<local>"
0x180007762  mov     [rbp+57h+pProxyInfo.lpszProxyBypass], rax
0x180007766  cmp     r10, r8
0x180007769  jz      short loc_180007787
0x18000776b  test    byte ptr [r10+1Ch], 2
0x180007770  jz      short loc_180007787
0x180007772  mov     rcx, [r10+10h]
0x180007776  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x18000777d  mov     edx, 15h
0x180007782  call    WPP_SF_
0x180007787  mov     r13d, 1
0x18000778d  jmp     loc_1800078A5
0x180007792  mov     [rbp+57h+pProxyInfo.dwAccessType], 1
0x180007799  test    rdi, rdi
0x18000779c  jz      short loc_18000780D
0x18000779e  mov     rcx, rdi
0x1800077a1  xor     edx, edx
0x1800077a3  movzx   eax, word ptr [rcx]
0x1800077a6  test    ax, ax
0x1800077a9  jz      short loc_1800077CA
0x1800077ab  cmp     edx, 3
0x1800077ae  jnb     short loc_1800077CA
0x1800077b0  cmp     ax, 2Fh ; '/'
0x1800077b4  jz      short loc_1800077C2
0x1800077b6  cmp     ax, 2Eh ; '.'
0x1800077ba  jz      short loc_18000780D
0x1800077bc  cmp     ax, 5Ch ; '\'
0x1800077c0  jnz     short loc_1800077C4
0x1800077c2  inc     edx
0x1800077c4  add     rcx, 2
0x1800077c8  jmp     short loc_1800077A3
0x1800077ca  cmp     r10, r8
0x1800077cd  jz      short loc_1800077EB
0x1800077cf  test    byte ptr [r10+1Ch], 2
0x1800077d4  jz      short loc_1800077EB
0x1800077d6  mov     rcx, [r10+10h]
0x1800077da  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x1800077e1  mov     edx, 17h
0x1800077e6  call    WPP_SF_
0x1800077eb  lea     rax, aNone; "none"
0x1800077f2  mov     [rbp+57h+pProxyInfo.dwAccessType], 3
0x1800077f9  mov     [rbp+57h+pProxyInfo.lpszProxy], rax
0x1800077fd  lea     rax, aLocal; "<local>"
0x180007804  mov     [rbp+57h+pProxyInfo.lpszProxyBypass], rax
0x180007808  jmp     loc_1800078A5
0x18000780d  mov     rdx, rdi
0x180007810  mov     rcx, r12
0x180007813  call    DavIsHostInAdminBypassList
0x180007818  test    eax, eax
0x18000781a  jz      loc_1800078A5
0x180007820  mov     rcx, cs:WPP_GLOBAL_Control
0x180007827  lea     r12, WPP_GLOBAL_Control
0x18000782e  cmp     rcx, r12
0x180007831  jz      short loc_180007851
0x180007833  test    byte ptr [rcx+1Ch], 2
0x180007837  jz      short loc_180007851
0x180007839  mov     rcx, [rcx+10h]
0x18000783d  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x180007844  mov     edx, 18h
0x180007849  mov     r9, rbx
0x18000784c  call    WPP_SF_S
0x180007851  lea     rax, aNone; "none"
0x180007858  mov     [rbp+57h+pProxyInfo.dwAccessType], 3
0x18000785f  mov     [rbp+57h+pProxyInfo.lpszProxy], rax
0x180007863  mov     [rbp+57h+pProxyInfo.lpszProxyBypass], rbx
0x180007867  jmp     short loc_1800078AC
0x180007869  cmp     r10, r8
0x18000786c  jz      short loc_1800078A5
0x18000786e  test    byte ptr [r10+1Ch], 2
0x180007873  jz      short loc_1800078A5
0x180007875  mov     rcx, [rbp+57h+pProxyInfo.lpszProxyBypass]
0x180007879  lea     rax, aNull_0; "NULL"
0x180007880  mov     r9, [rbp+57h+pProxyInfo.lpszProxy]
0x180007884  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x18000788b  test    rcx, rcx
0x18000788e  mov     edx, 19h
0x180007893  cmovnz  rax, rcx
0x180007897  mov     rcx, [r10+10h]
0x18000789b  mov     [rsp+0D0h+var_B0], rax
0x1800078a0  call    WPP_SF_SS
0x1800078a5  lea     r12, WPP_GLOBAL_Control
0x1800078ac  mov     r9d, 18h; dwBufferLength
0x1800078b2  lea     r8, [rbp+57h+pProxyInfo]; lpBuffer
0x1800078b6  mov     edx, 26h ; '&'; dwOption
0x1800078bb  mov     rcx, r15; hInternet
0x1800078be  call    cs:__imp_WinHttpSetOption
0x1800078c4  test    eax, eax
0x1800078c6  jnz     short loc_1800078F8
0x1800078c8  call    cs:__imp_GetLastError
0x1800078ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078d5  cmp     rcx, r12
0x1800078d8  jz      short loc_1800078F8
0x1800078da  test    byte ptr [rcx+1Ch], 1
0x1800078de  jz      short loc_1800078F8
0x1800078e0  mov     rcx, [rcx+10h]
0x1800078e4  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x1800078eb  mov     edx, 1Ah
0x1800078f0  mov     r9d, eax
0x1800078f3  call    WPP_SF_d
0x1800078f8  mov     r9d, 18h; dwBufferLength
0x1800078fe  lea     r8, [rbp+57h+pProxyInfo]; lpBuffer
0x180007902  mov     edx, 26h ; '&'; dwOption
0x180007907  mov     rcx, r14; hInternet
  ... truncated ...
```
