# OneCore::Base::Telemetry::OneSettingsQuery::SetUserProxyInfoAndGetCredentials(void * &,ushort const *,bool,ushort *,unsigned __int64,ushort *,unsigned __int64)

- ea: `0x180007170`
- end: `0x1800074fc`
- name: `?SetUserProxyInfoAndGetCredentials@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJAEAPEAXPEBG_NPEAG_K34@Z`
- size: `908`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *this, void **, const unsigned __int16 *, char, unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180004d68`

## callees

- `0x180003770`
- `0x180003894`
- `0x180007170`
- `0x180007b54`
- `0x1800191f0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000733a`
- `msvcrt!_wcsnicmp` at `0x18000733a`
- `msvcrt!wcsrchr` at `0x1800074b4`
- `msvcrt!wcsrchr` at `0x1800074b4`
- `ADVAPI32!RevertToSelf` at `0x1800074df`
- `ADVAPI32!RevertToSelf` at `0x1800074df`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180007212`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180007212`
- `KERNEL32!GetLastError` at `0x18000721c`
- `KERNEL32!GetLastError` at `0x180007275`
- `KERNEL32!GetLastError` at `0x180007280`
- `KERNEL32!GetLastError` at `0x1800072b4`
- `KERNEL32!GetLastError` at `0x1800074ed`
- `KERNEL32!GetLastError` at `0x18000721c`
- `KERNEL32!GetLastError` at `0x180007275`
- `KERNEL32!GetLastError` at `0x180007280`
- `KERNEL32!GetLastError` at `0x1800072b4`
- `KERNEL32!GetLastError` at `0x1800074ed`
- `KERNEL32!GlobalFree` at `0x180007303`
- `KERNEL32!GlobalFree` at `0x180007318`
- `KERNEL32!GlobalFree` at `0x1800073d1`
- `KERNEL32!GlobalFree` at `0x1800073eb`
- `KERNEL32!GlobalFree` at `0x18000741d`
- `KERNEL32!GlobalFree` at `0x180007432`
- `KERNEL32!GlobalFree` at `0x180007303`
- `KERNEL32!GlobalFree` at `0x180007318`
- `KERNEL32!GlobalFree` at `0x1800073d1`
- `KERNEL32!GlobalFree` at `0x1800073eb`
- `KERNEL32!GlobalFree` at `0x18000741d`
- `KERNEL32!GlobalFree` at `0x180007432`
- `KERNEL32!ExitProcess` at `0x1800074f5`
- `KERNEL32!ExitProcess` at `0x1800074f5`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x180007385`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x180007385`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18000726b`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18000726b`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x180007442`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x180007442`
- `WINHTTP!WinHttpSetOption` at `0x180007485`
- `WINHTTP!WinHttpSetOption` at `0x180007485`

## string_xrefs

- `0x180007323`: `settings-win.data.microsoft.com`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::SetUserProxyInfoAndGetCredentials(
        OneCore::Base::Telemetry::OneSettingsQuery *this,
        void **a2,
        const unsigned __int16 *a3,
        char a4,
        unsigned __int16 *a5,
        unsigned __int64 a6,
        unsigned __int16 *a7)
{
  char v8; // si
  signed int UserSession; // ebx
  signed int LastError; // eax
  signed int v12; // eax
  char v13; // bl
  unsigned __int64 v14; // rdi
  BOOL ProxyForUrl; // eax
  unsigned __int16 *v16; // rdx
  WCHAR *lpszProxy; // rax
  const unsigned __int16 *v18; // rbx
  wchar_t *v19; // rax
  OneCore::Base::Telemetry::OneSettingsQuery *v20; // rcx
  unsigned __int64 v21; // r9
  UINT v22; // eax
  unsigned __int64 v23; // [rsp+28h] [rbp-D8h]
  WINHTTP_PROXY_INFO hMem; // [rsp+30h] [rbp-D0h] BYREF
  int v25; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hToken; // [rsp+50h] [rbp-B0h] BYREF
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig; // [rsp+58h] [rbp-A8h] BYREF
  WINHTTP_AUTOPROXY_OPTIONS pAutoProxyOptions; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v29[264]; // [rsp+A0h] [rbp-60h] BYREF

  hToken = 0;
  v25 = 0;
  *a5 = 0;
  *a7 = 0;
  v8 = 0;
  memset(&pAutoProxyOptions, 0, sizeof(pAutoProxyOptions));
  memset(&pProxyConfig, 0, sizeof(pProxyConfig));
  memset(&hMem, 0, sizeof(hMem));
  if ( !a4 )
  {
    UserSession = OneCore::Base::Telemetry::OneSettingsQuery::FindUserSession(this, &hToken, &v25);
    if ( UserSession < 0 )
      return (unsigned int)UserSession;
    if ( v25 )
    {
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        LastError = GetLastError();
        UserSession = LastError;
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
        return (unsigned int)UserSession;
      }
      v8 = 1;
    }
  }
  memset(&pProxyConfig, 0, sizeof(pProxyConfig));
  if ( WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig) || GetLastError() == 2 )
  {
    v13 = 0;
    v14 = 0;
    ProxyForUrl = 0;
    do
    {
      if ( ProxyForUrl )
        goto LABEL_52;
      if ( v14 )
      {
        if ( GetLastError() != 12015 )
          goto LABEL_32;
        pAutoProxyOptions.fAutoLogonIfChallenged = 1;
      }
      pAutoProxyOptions.lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
      if ( pProxyConfig.lpszAutoConfigUrl )
      {
        *(_QWORD *)&pAutoProxyOptions.dwFlags = 2;
      }
      else
      {
        pAutoProxyOptions.dwFlags = 1;
        pAutoProxyOptions.dwAutoDetectFlags = 3;
      }
      if ( v13 )
      {
        if ( hMem.lpszProxy )
        {
          GlobalFree(hMem.lpszProxy);
          hMem.lpszProxy = 0;
        }
        if ( hMem.lpszProxyBypass )
        {
          GlobalFree(hMem.lpszProxyBypass);
          hMem.lpszProxyBypass = 0;
        }
      }
      if ( _wcsnicmp(L"settings-win.data.microsoft.com", L"https://", 8u) )
      {
        UserSession = StringCchPrintfW(v29, 0x104u, L"%ls%ls", L"https://", L"settings-win.data.microsoft.com");
        if ( UserSession < 0 )
          goto LABEL_61;
        v16 = v29;
      }
      else
      {
        v16 = L"settings-win.data.microsoft.com";
      }
      ProxyForUrl = WinHttpGetProxyForUrl(*a2, v16, &pAutoProxyOptions, &hMem);
      ++v14;
      v13 = 1;
    }
    while ( v14 < 2 );
    if ( !ProxyForUrl )
    {
LABEL_32:
      lpszProxy = pProxyConfig.lpszProxy;
      if ( pProxyConfig.lpszProxy
        && *pProxyConfig.lpszProxy
        && (*pProxyConfig.lpszProxy != 58 || pProxyConfig.lpszProxy[1]) )
      {
        if ( v13 )
        {
          if ( hMem.lpszProxy )
          {
            GlobalFree(hMem.lpszProxy);
            lpszProxy = pProxyConfig.lpszProxy;
            hMem.lpszProxy = 0;
          }
          if ( hMem.lpszProxyBypass )
          {
            GlobalFree(hMem.lpszProxyBypass);
            lpszProxy = pProxyConfig.lpszProxy;
          }
        }
        hMem.lpszProxy = lpszProxy;
        hMem.lpszProxyBypass = pProxyConfig.lpszProxyBypass;
        hMem.dwAccessType = 3;
      }
      else
      {
        if ( v13 )
        {
          if ( hMem.lpszProxy )
          {
            GlobalFree(hMem.lpszProxy);
            hMem.lpszProxy = 0;
          }
          if ( hMem.lpszProxyBypass )
          {
            GlobalFree(hMem.lpszProxyBypass);
            hMem.lpszProxyBypass = 0;
          }
        }
        if ( !WinHttpGetDefaultProxyConfiguration(&hMem) )
          goto LABEL_11;
        if ( !hMem.lpszProxy || !*hMem.lpszProxy || *hMem.lpszProxy == 58 && !hMem.lpszProxy[1] )
        {
LABEL_60:
          UserSession = 0;
          goto LABEL_61;
        }
      }
    }
LABEL_52:
    if ( !WinHttpSetOption(*a2, 0x26u, &hMem, 0x18u) )
      goto LABEL_11;
    v18 = hMem.lpszProxy;
    if ( hMem.lpszProxy && *hMem.lpszProxy && (*hMem.lpszProxy != 58 || hMem.lpszProxy[1]) )
    {
      v19 = wcsrchr(hMem.lpszProxy, 0x3Au);
      if ( v19 )
        *v19 = 0;
      OneCore::Base::Telemetry::OneSettingsQuery::GetCredentialsForBasicProxyIfPresent(v20, v18, a5, v21, a7, v23);
    }
    goto LABEL_60;
  }
LABEL_11:
  v12 = GetLastError();
  UserSession = v12;
  if ( v12 > 0 )
    UserSession = (unsigned __int16)v12 | 0x80070000;
LABEL_61:
  if ( v8 && !RevertToSelf() )
  {
    v22 = GetLastError();
    ExitProcess(v22);
  }
  return (unsigned int)UserSession;
}

```

## disassembly

```asm
0x180007170  push    rbp
0x180007172  push    rbx
0x180007173  push    rsi
0x180007174  push    rdi
0x180007175  push    r12
0x180007177  push    r13
0x180007179  push    r14
0x18000717b  push    r15
0x18000717d  lea     rbp, [rsp-1C8h]
0x180007185  sub     rsp, 2C8h
0x18000718c  mov     rax, cs:__security_cookie
0x180007193  xor     rax, rsp
0x180007196  mov     [rbp+200h+var_50], rax
0x18000719d  mov     r15, [rbp+200h+arg_20]
0x1800071a4  xor     r13d, r13d
0x1800071a7  mov     r12, [rbp+200h+arg_30]
0x1800071ae  xorps   xmm0, xmm0
0x1800071b1  xor     eax, eax
0x1800071b3  mov     [rsp+300h+hToken], r13
0x1800071b8  mov     [rsp+300h+var_2B8], r13d
0x1800071bd  xorps   xmm1, xmm1
0x1800071c0  mov     [r15], r13w
0x1800071c4  mov     r14, rdx
0x1800071c7  mov     [r12], r13w
0x1800071cc  mov     sil, r13b
0x1800071cf  mov     [rsp+300h+var_2C0], rax
0x1800071d4  movups  xmmword ptr [rsp+300h+pAutoProxyOptions.dwFlags], xmm0
0x1800071d9  movups  xmmword ptr [rbp+200h+pAutoProxyOptions.lpvReserved], xmm0
0x1800071dd  movups  xmmword ptr [rsp+300h+pProxyConfig.fAutoDetect], xmm1
0x1800071e2  movups  xmmword ptr [rsp+300h+pProxyConfig.lpszProxy], xmm1
0x1800071e7  movups  xmmword ptr [rsp+300h+hMem], xmm0
0x1800071ec  test    r9b, r9b
0x1800071ef  jnz     short loc_180007259
0x1800071f1  lea     r8, [rsp+300h+var_2B8]; int *
0x1800071f6  lea     rdx, [rsp+300h+hToken]; void **
0x1800071fb  call    ?FindUserSession@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAPEAXPEAH@Z; OneCore::Base::Telemetry::OneSettingsQuery::FindUserSession(void * *,int *)
0x180007200  mov     ebx, eax
0x180007202  test    eax, eax
0x180007204  js      short loc_180007231
0x180007206  cmp     [rsp+300h+var_2B8], r13d
0x18000720b  jz      short loc_180007259
0x18000720d  mov     rcx, [rsp+300h+hToken]; hToken
0x180007212  call    cs:__imp_ImpersonateLoggedOnUser
0x180007218  test    eax, eax
0x18000721a  jnz     short loc_180007256
0x18000721c  call    cs:__imp_GetLastError
0x180007222  mov     ebx, eax
0x180007224  test    eax, eax
0x180007226  jle     short loc_180007231
0x180007228  movzx   ebx, ax
0x18000722b  or      ebx, 80070000h
0x180007231  mov     eax, ebx
0x180007233  mov     rcx, [rbp+200h+var_50]
0x18000723a  xor     rcx, rsp; StackCookie
0x18000723d  call    __security_check_cookie
0x180007242  add     rsp, 2C8h
0x180007249  pop     r15
0x18000724b  pop     r14
0x18000724d  pop     r13
0x18000724f  pop     r12
0x180007251  pop     rdi
0x180007252  pop     rsi
0x180007253  pop     rbx
0x180007254  pop     rbp
0x180007255  retn
0x180007256  mov     sil, 1
0x180007259  xorps   xmm0, xmm0
0x18000725c  lea     rcx, [rsp+300h+pProxyConfig]; pProxyConfig
0x180007261  movups  xmmword ptr [rsp+300h+pProxyConfig.fAutoDetect], xmm0
0x180007266  movups  xmmword ptr [rsp+300h+pProxyConfig.lpszProxy], xmm0
0x18000726b  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x180007271  test    eax, eax
0x180007273  jnz     short loc_18000729E
0x180007275  call    cs:__imp_GetLastError
0x18000727b  cmp     eax, 2
0x18000727e  jz      short loc_18000729E
0x180007280  call    cs:__imp_GetLastError
0x180007286  mov     ebx, eax
0x180007288  test    eax, eax
0x18000728a  jle     loc_1800074D6
0x180007290  movzx   ebx, ax
0x180007293  or      ebx, 80070000h
0x180007299  jmp     loc_1800074D6
0x18000729e  mov     bl, r13b
0x1800072a1  mov     rdi, r13
0x1800072a4  mov     eax, r13d
0x1800072a7  test    eax, eax
0x1800072a9  jnz     loc_18000746E
0x1800072af  test    rdi, rdi
0x1800072b2  jz      short loc_1800072CC
0x1800072b4  call    cs:__imp_GetLastError
0x1800072ba  cmp     eax, 2EEFh
0x1800072bf  jnz     loc_1800073A2
0x1800072c5  mov     [rbp+200h+pAutoProxyOptions.fAutoLogonIfChallenged], 1
0x1800072cc  mov     rax, [rsp+300h+pProxyConfig.lpszAutoConfigUrl]
0x1800072d1  mov     [rbp+200h+pAutoProxyOptions.lpszAutoConfigUrl], rax
0x1800072d5  test    rax, rax
0x1800072d8  jnz     short loc_1800072EC
0x1800072da  mov     [rsp+300h+pAutoProxyOptions.dwFlags], 1
0x1800072e2  mov     [rsp+300h+pAutoProxyOptions.dwAutoDetectFlags], 3
0x1800072ea  jmp     short loc_1800072F5
0x1800072ec  mov     qword ptr [rsp+300h+pAutoProxyOptions.dwFlags], 2
0x1800072f5  test    bl, bl
0x1800072f7  jz      short loc_180007323
0x1800072f9  mov     rcx, [rsp+300h+hMem+8]; hMem
0x1800072fe  test    rcx, rcx
0x180007301  jz      short loc_18000730E
0x180007303  call    cs:__imp_GlobalFree
0x180007309  mov     [rsp+300h+hMem+8], r13
0x18000730e  mov     rcx, [rsp+300h+var_2C0]; hMem
0x180007313  test    rcx, rcx
0x180007316  jz      short loc_180007323
0x180007318  call    cs:__imp_GlobalFree
0x18000731e  mov     [rsp+300h+var_2C0], r13
0x180007323  lea     rbx, aSettingsWinDat; "settings-win.data.microsoft.com"
0x18000732a  mov     r8d, 8; MaxCount
0x180007330  mov     rcx, rbx; String1
0x180007333  lea     rdx, aHttps; "https://"
0x18000733a  call    cs:__imp__wcsnicmp
0x180007340  test    eax, eax
0x180007342  jz      short loc_180007375
0x180007344  lea     r9, aHttps; "https://"
0x18000734b  mov     [rsp+300h+var_2E0], rbx
0x180007350  lea     r8, aLsLs; "%ls%ls"
0x180007357  mov     edx, 104h; unsigned __int64
0x18000735c  lea     rcx, [rbp+200h+var_260]; unsigned __int16 *
0x180007360  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007365  mov     ebx, eax
0x180007367  test    eax, eax
0x180007369  js      loc_1800074D6
0x18000736f  lea     rdx, [rbp+200h+var_260]
0x180007373  jmp     short loc_180007378
0x180007375  mov     rdx, rbx; lpcwszUrl
0x180007378  mov     rcx, [r14]; hSession
0x18000737b  lea     r9, [rsp+300h+hMem]; pProxyInfo
0x180007380  lea     r8, [rsp+300h+pAutoProxyOptions]; pAutoProxyOptions
0x180007385  call    cs:__imp_WinHttpGetProxyForUrl
0x18000738b  inc     rdi
0x18000738e  mov     bl, 1
0x180007390  cmp     rdi, 2
0x180007394  jb      loc_1800072A7
0x18000739a  test    eax, eax
0x18000739c  jnz     loc_18000746E
0x1800073a2  mov     rax, [rsp+300h+pProxyConfig.lpszProxy]
0x1800073a7  mov     edi, 3Ah ; ':'
0x1800073ac  test    rax, rax
0x1800073af  jz      short loc_18000740F
0x1800073b1  cmp     [rax], r13w
0x1800073b5  jz      short loc_18000740F
0x1800073b7  cmp     [rax], di
0x1800073ba  jnz     short loc_1800073C3
0x1800073bc  cmp     [rax+2], r13w
0x1800073c1  jz      short loc_18000740F
0x1800073c3  test    bl, bl
0x1800073c5  jz      short loc_1800073F6
0x1800073c7  mov     rcx, [rsp+300h+hMem+8]; hMem
0x1800073cc  test    rcx, rcx
0x1800073cf  jz      short loc_1800073E1
0x1800073d1  call    cs:__imp_GlobalFree
0x1800073d7  mov     rax, [rsp+300h+pProxyConfig.lpszProxy]
0x1800073dc  mov     [rsp+300h+hMem+8], r13
0x1800073e1  mov     rcx, [rsp+300h+var_2C0]; hMem
0x1800073e6  test    rcx, rcx
0x1800073e9  jz      short loc_1800073F6
0x1800073eb  call    cs:__imp_GlobalFree
0x1800073f1  mov     rax, [rsp+300h+pProxyConfig.lpszProxy]
0x1800073f6  mov     [rsp+300h+hMem+8], rax
0x1800073fb  mov     rax, [rsp+300h+pProxyConfig.lpszProxyBypass]
0x180007400  mov     [rsp+300h+var_2C0], rax
0x180007405  mov     dword ptr [rsp+300h+hMem], 3
0x18000740d  jmp     short loc_180007473
0x18000740f  test    bl, bl
0x180007411  jz      short loc_18000743D
0x180007413  mov     rcx, [rsp+300h+hMem+8]; hMem
0x180007418  test    rcx, rcx
0x18000741b  jz      short loc_180007428
0x18000741d  call    cs:__imp_GlobalFree
0x180007423  mov     [rsp+300h+hMem+8], r13
0x180007428  mov     rcx, [rsp+300h+var_2C0]; hMem
0x18000742d  test    rcx, rcx
0x180007430  jz      short loc_18000743D
0x180007432  call    cs:__imp_GlobalFree
0x180007438  mov     [rsp+300h+var_2C0], r13
0x18000743d  lea     rcx, [rsp+300h+hMem]; pProxyInfo
0x180007442  call    cs:__imp_WinHttpGetDefaultProxyConfiguration
0x180007448  test    eax, eax
0x18000744a  jz      loc_180007280
0x180007450  mov     rax, [rsp+300h+hMem+8]
0x180007455  test    rax, rax
0x180007458  jz      short loc_1800074D3
0x18000745a  cmp     [rax], r13w
0x18000745e  jz      short loc_1800074D3
0x180007460  cmp     [rax], di
0x180007463  jnz     short loc_180007473
0x180007465  cmp     [rax+2], r13w
0x18000746a  jz      short loc_1800074D3
0x18000746c  jmp     short loc_180007473
0x18000746e  mov     edi, 3Ah ; ':'
0x180007473  mov     rcx, [r14]; hInternet
0x180007476  lea     r8, [rsp+300h+hMem]; lpBuffer
0x18000747b  mov     r9d, 18h; dwBufferLength
0x180007481  lea     edx, [r9+0Eh]; dwOption
0x180007485  call    cs:__imp_WinHttpSetOption
0x18000748b  test    eax, eax
0x18000748d  jz      loc_180007280
0x180007493  mov     rbx, [rsp+300h+hMem+8]
0x180007498  test    rbx, rbx
0x18000749b  jz      short loc_1800074D3
0x18000749d  cmp     [rbx], r13w
0x1800074a1  jz      short loc_1800074D3
0x1800074a3  cmp     [rbx], di
0x1800074a6  jnz     short loc_1800074AF
0x1800074a8  cmp     [rbx+2], r13w
0x1800074ad  jz      short loc_1800074D3
0x1800074af  mov     edx, edi; Ch
0x1800074b1  mov     rcx, rbx; Str
0x1800074b4  call    cs:__imp_wcsrchr
0x1800074ba  test    rax, rax
0x1800074bd  jz      short loc_1800074C3
0x1800074bf  mov     [rax], r13w
0x1800074c3  mov     r8, r15; unsigned __int16 *
0x1800074c6  mov     [rsp+300h+var_2E0], r12; unsigned __int16 *
0x1800074cb  mov     rdx, rbx; unsigned __int16 *
0x1800074ce  call    ?GetCredentialsForBasicProxyIfPresent@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBGPEAG_K12@Z; OneCore::Base::Telemetry::OneSettingsQuery::GetCredentialsForBasicProxyIfPresent(ushort const *,ushort *,unsigned __int64,ushort *,unsigned __int64)
0x1800074d3  mov     ebx, r13d
0x1800074d6  test    sil, sil
0x1800074d9  jz      loc_180007231
0x1800074df  call    cs:__imp_RevertToSelf
0x1800074e5  test    eax, eax
0x1800074e7  jnz     loc_180007231
0x1800074ed  call    cs:__imp_GetLastError
0x1800074f3  mov     ecx, eax; uExitCode
0x1800074f5  call    cs:__imp_ExitProcess
```
