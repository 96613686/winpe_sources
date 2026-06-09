# GetSstpDestinationInfo

- ea: `0x1800021c0`
- end: `0x180002602`
- name: `GetSstpDestinationInfo`
- size: `1090`
- prototype: `__int64 __fastcall(unsigned __int64, _QWORD *, _DWORD *, char, DWORD *, void *Src, void *, size_t Size, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800014bc`
- `0x1800021c0`
- `0x180002660`
- `0x180002f68`
- `0x180002fa0`
- `0x180002fec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002490`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002490`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800024a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800024a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002265`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000258c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002265`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000258c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180002456`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000246a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000247e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180002456`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000246a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000247e`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18000257c`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18000257c`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x180002253`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x180002253`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800022c9`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800022c9`
- `WINHTTP!WinHttpCloseHandle` at `0x1800025d7`
- `WINHTTP!WinHttpCloseHandle` at `0x1800025d7`
- `WINHTTP!WinHttpOpen` at `0x18000250f`
- `WINHTTP!WinHttpOpen` at `0x18000250f`

## pseudocode

```c
__int64 __fastcall GetSstpDestinationInfo(
        unsigned __int64 a1,
        _QWORD *a2,
        _DWORD *a3,
        char a4,
        DWORD *a5,
        void *Src,
        void *a7,
        size_t Size,
        unsigned int a9)
{
  _DWORD *v10; // rsi
  LPWSTR lpszAutoConfigUrl; // r12
  LPWSTR lpszProxyBypass; // r14
  LPWSTR lpszProxy; // r15
  DWORD LastError; // ebx
  __int64 v16; // r8
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  BOOL fAutoDetect; // eax
  DWORD dwFlags; // ecx
  __int64 v21; // r8
  LPWSTR v22; // r9
  LPWSTR v23; // rcx
  unsigned int v24; // ebx
  HANDLE ProcessHeap; // rax
  void *v27; // rax
  void *v28; // rsi
  __int64 v29; // r8
  __int64 v30; // r8
  size_t v31; // [rsp+40h] [rbp-61h]
  LPVOID lpMem; // [rsp+48h] [rbp-59h] BYREF
  WINHTTP_PROXY_INFO pProxyInfo; // [rsp+50h] [rbp-51h] BYREF
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig; // [rsp+68h] [rbp-39h] BYREF
  WINHTTP_AUTOPROXY_OPTIONS pAutoProxyOptions; // [rsp+88h] [rbp-19h] BYREF

  lpMem = 0;
  v10 = a3;
  lpszAutoConfigUrl = 0;
  lpszProxyBypass = 0;
  lpszProxy = 0;
  memset(&pProxyConfig, 0, sizeof(pProxyConfig));
  memset(&pAutoProxyOptions, 0, sizeof(pAutoProxyOptions));
  memset(&pProxyInfo, 0, sizeof(pProxyInfo));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0xC0) == 0xC0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33);
  if ( !a4 )
  {
    LastError = 0;
    if ( WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig) )
    {
      fAutoDetect = pProxyConfig.fAutoDetect;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError != 2 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          v18 = 35;
          goto LABEL_10;
        }
LABEL_62:
        *a5 = LastError;
        if ( !LastError )
          goto LABEL_63;
LABEL_36:
        v22 = 0;
        v23 = 0;
        goto LABEL_37;
      }
      fAutoDetect = 1;
      pProxyConfig.fAutoDetect = 1;
    }
    if ( fAutoDetect )
    {
      dwFlags = 1;
      pAutoProxyOptions.dwAutoDetectFlags = 3;
      pAutoProxyOptions.dwFlags = 1;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)&WPP_GLOBAL_Control,
          0,
          pProxyConfig.lpszProxy,
          (__int64)pProxyConfig.lpszProxyBypass);
        fAutoDetect = pProxyConfig.fAutoDetect;
      }
      lpszProxy = pProxyConfig.lpszProxy;
      lpszProxyBypass = pProxyConfig.lpszProxyBypass;
      dwFlags = pAutoProxyOptions.dwFlags;
    }
    if ( pProxyConfig.lpszAutoConfigUrl && *pProxyConfig.lpszAutoConfigUrl )
    {
      fAutoDetect = 1;
      pAutoProxyOptions.lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
      pProxyConfig.fAutoDetect = 1;
      pAutoProxyOptions.dwFlags = dwFlags | 2;
      lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
    }
    if ( fAutoDetect )
    {
      LastError = GetSstpUrlForDestination(a9, a1, &lpMem);
      if ( LastError )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, v21);
          *a5 = LastError;
          goto LABEL_36;
        }
      }
      else
      {
        v27 = WinHttpOpen(L"SSTP", 1u, 0, 0, 0);
        v28 = v27;
        if ( v27 )
        {
          if ( WinHttpGetProxyForUrl(v27, (LPCWSTR)lpMem, &pAutoProxyOptions, &pProxyInfo) )
          {
            lpszProxy = pProxyInfo.lpszProxy;
            lpszProxyBypass = pProxyInfo.lpszProxyBypass;
          }
          else
          {
            LastError = GetLastError();
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, v30);
            }
          }
          WinHttpCloseHandle(v28);
        }
        else
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, v29);
          }
        }
        v10 = a3;
      }
    }
    goto LABEL_62;
  }
  if ( !WinHttpGetDefaultProxyConfiguration(&pProxyInfo) )
  {
    LastError = GetLastError();
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v18 = 34;
LABEL_10:
      WPP_SF_d(v17[2], v18, v16);
      goto LABEL_62;
    }
    goto LABEL_62;
  }
  lpszProxy = pProxyInfo.lpszProxy;
  lpszProxyBypass = pProxyInfo.lpszProxyBypass;
  *a5 = 0;
LABEL_63:
  v22 = lpszProxy;
  v23 = lpszProxyBypass;
LABEL_37:
  LODWORD(v31) = Size;
  v24 = ConstructDestinationInfo(a2, v10, a1, v22, v23, Src, a7, v31);
  if ( lpszAutoConfigUrl )
    GlobalFree(lpszAutoConfigUrl);
  if ( lpszProxy )
    GlobalFree(lpszProxy);
  if ( lpszProxyBypass )
    GlobalFree(lpszProxyBypass);
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0xC0) == 0xC0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40);
  return v24;
}

```

## disassembly

```asm
0x1800021c0  mov     rax, rsp
0x1800021c3  mov     [rax+8], rbx
0x1800021c7  mov     [rax+18h], r8
0x1800021cb  mov     [rax+10h], rdx
0x1800021cf  push    rbp
0x1800021d0  push    rsi
0x1800021d1  push    rdi
0x1800021d2  push    r12
0x1800021d4  push    r13
0x1800021d6  push    r14
0x1800021d8  push    r15
0x1800021da  lea     rbp, [rax-3Fh]
0x1800021de  sub     rsp, 0A0h
0x1800021e5  xor     edx, edx
0x1800021e7  xorps   xmm0, xmm0
0x1800021ea  xorps   xmm1, xmm1
0x1800021ed  mov     [rbp+37h+lpMem], rdx
0x1800021f1  xor     eax, eax
0x1800021f3  mov     bl, r9b
0x1800021f6  mov     [rbp+37h+pProxyInfo.lpszProxyBypass], rax
0x1800021fa  mov     rsi, r8
0x1800021fd  mov     r13, rcx
0x180002200  mov     r12d, edx
0x180002203  mov     r14d, edx
0x180002206  mov     r15d, edx
0x180002209  movups  xmmword ptr [rbp+37h+pProxyConfig.fAutoDetect], xmm0
0x18000220d  movups  xmmword ptr [rbp+37h+pProxyConfig.lpszProxy], xmm0
0x180002211  movups  xmmword ptr [rbp+37h+pAutoProxyOptions.dwFlags], xmm1
0x180002215  movups  xmmword ptr [rbp+37h+pAutoProxyOptions.lpvReserved], xmm1
0x180002219  movups  xmmword ptr [rbp+37h+pProxyInfo.dwAccessType], xmm0
0x18000221d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002224  lea     rdi, WPP_GLOBAL_Control
0x18000222b  cmp     rcx, rdi
0x18000222e  jz      short loc_18000224B
0x180002230  mov     eax, [rcx+1Ch]
0x180002233  and     eax, 0C0h
0x180002238  cmp     al, 0C0h
0x18000223a  jnz     short loc_18000224B
0x18000223c  mov     rcx, [rcx+10h]
0x180002240  lea     edx, [r15+21h]
0x180002244  call    WPP_SF_
0x180002249  xor     edx, edx
0x18000224b  test    bl, bl
0x18000224d  jz      short loc_1800022C3
0x18000224f  lea     rcx, [rbp+37h+pProxyInfo]; pProxyInfo
0x180002253  call    cs:__imp_WinHttpGetDefaultProxyConfiguration
0x18000225a  nop     dword ptr [rax+rax+00h]
0x18000225f  xor     ecx, ecx
0x180002261  test    eax, eax
0x180002263  jnz     short loc_1800022B0
0x180002265  call    cs:__imp_GetLastError
0x18000226c  nop     dword ptr [rax+rax+00h]
0x180002271  mov     ebx, eax
0x180002273  mov     rcx, cs:WPP_GLOBAL_Control
0x18000227a  cmp     rcx, rdi
0x18000227d  jz      loc_1800025E7
0x180002283  test    byte ptr [rcx+1Ch], 40h
0x180002287  jz      loc_1800025E7
0x18000228d  mov     edi, 1
0x180002292  cmp     [rcx+19h], dil
0x180002296  jb      loc_1800025E7
0x18000229c  lea     edx, [rdi+21h]
0x18000229f  mov     rcx, [rcx+10h]
0x1800022a3  mov     r9d, eax
0x1800022a6  call    WPP_SF_d
0x1800022ab  jmp     loc_1800025E7
0x1800022b0  mov     rax, [rbp+37h+arg_20]
0x1800022b4  mov     r15, [rbp+37h+pProxyInfo.lpszProxy]
0x1800022b8  mov     r14, [rbp+37h+pProxyInfo.lpszProxyBypass]
0x1800022bc  mov     [rax], ecx
0x1800022be  jmp     loc_1800025F7
0x1800022c3  lea     rcx, [rbp+37h+pProxyConfig]; pProxyConfig
0x1800022c7  mov     ebx, edx
0x1800022c9  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x1800022d0  nop     dword ptr [rax+rax+00h]
0x1800022d5  xor     r8d, r8d
0x1800022d8  mov     edi, 1
0x1800022dd  test    eax, eax
0x1800022df  jnz     short loc_180002331
0x1800022e1  call    cs:__imp_GetLastError
0x1800022e8  nop     dword ptr [rax+rax+00h]
0x1800022ed  mov     ebx, eax
0x1800022ef  cmp     eax, 2
0x1800022f2  jz      short loc_180002327
0x1800022f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800022fb  lea     rdx, WPP_GLOBAL_Control
0x180002302  cmp     rcx, rdx
0x180002305  jz      loc_1800025E7
0x18000230b  test    byte ptr [rcx+1Ch], 40h
0x18000230f  jz      loc_1800025E7
0x180002315  cmp     [rcx+19h], dil
0x180002319  jb      loc_1800025E7
0x18000231f  lea     edx, [rdi+22h]
0x180002322  jmp     loc_18000229F
0x180002327  mov     eax, edi
0x180002329  xor     r8d, r8d
0x18000232c  mov     [rbp+37h+pProxyConfig.fAutoDetect], eax
0x18000232f  jmp     short loc_180002334
0x180002331  mov     eax, [rbp+37h+pProxyConfig.fAutoDetect]
0x180002334  test    eax, eax
0x180002336  jnz     short loc_180002380
0x180002338  mov     rcx, cs:WPP_GLOBAL_Control
0x18000233f  lea     rdx, WPP_GLOBAL_Control
0x180002346  cmp     rcx, rdx
0x180002349  jz      short loc_180002373
0x18000234b  test    byte ptr [rcx+1Ch], 40h
0x18000234f  jz      short loc_180002373
0x180002351  cmp     byte ptr [rcx+19h], 2
0x180002355  jb      short loc_180002373
0x180002357  mov     rax, [rbp+37h+pProxyConfig.lpszProxyBypass]
0x18000235b  mov     r9, [rbp+37h+pProxyConfig.lpszProxy]
0x18000235f  mov     rcx, [rcx+10h]
0x180002363  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x180002368  call    WPP_SF_SS
0x18000236d  mov     eax, [rbp+37h+pProxyConfig.fAutoDetect]
0x180002370  xor     r8d, r8d
0x180002373  mov     r15, [rbp+37h+pProxyConfig.lpszProxy]
0x180002377  mov     r14, [rbp+37h+pProxyConfig.lpszProxyBypass]
0x18000237b  mov     ecx, [rbp+37h+pAutoProxyOptions.dwFlags]
0x18000237e  jmp     short loc_18000238C
0x180002380  mov     ecx, edi
0x180002382  mov     [rbp+37h+pAutoProxyOptions.dwAutoDetectFlags], 3
0x180002389  mov     [rbp+37h+pAutoProxyOptions.dwFlags], ecx
0x18000238c  mov     rdx, [rbp+37h+pProxyConfig.lpszAutoConfigUrl]
0x180002390  test    rdx, rdx
0x180002393  jz      short loc_1800023AD
0x180002395  cmp     [rdx], r8w
0x180002399  jz      short loc_1800023AD
0x18000239b  mov     eax, edi
0x18000239d  mov     [rbp+37h+pAutoProxyOptions.lpszAutoConfigUrl], rdx
0x1800023a1  or      ecx, 2
0x1800023a4  mov     [rbp+37h+pProxyConfig.fAutoDetect], eax
0x1800023a7  mov     [rbp+37h+pAutoProxyOptions.dwFlags], ecx
0x1800023aa  mov     r12, rdx
0x1800023ad  test    eax, eax
0x1800023af  jz      loc_1800025E7
0x1800023b5  mov     ecx, [rbp+37h+arg_40]
0x1800023bb  lea     r8, [rbp+37h+lpMem]
0x1800023bf  mov     rdx, r13
0x1800023c2  call    GetSstpUrlForDestination
0x1800023c7  mov     ebx, eax
0x1800023c9  xor     eax, eax
0x1800023cb  test    ebx, ebx
0x1800023cd  jz      loc_1800024FC
0x1800023d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800023da  lea     rax, WPP_GLOBAL_Control
0x1800023e1  cmp     rcx, rax
0x1800023e4  jz      loc_1800025E7
0x1800023ea  test    byte ptr [rcx+1Ch], 40h
0x1800023ee  jz      loc_1800025E7
0x1800023f4  cmp     [rcx+19h], dil
0x1800023f8  jb      loc_1800025E7
0x1800023fe  mov     rcx, [rcx+10h]
0x180002402  mov     edx, 25h ; '%'
0x180002407  mov     r9d, ebx
0x18000240a  call    WPP_SF_d
0x18000240f  mov     rax, [rbp+37h+arg_20]
0x180002413  mov     [rax], ebx
0x180002415  xor     eax, eax
0x180002417  mov     r9, rax; int
0x18000241a  mov     rcx, rax
0x18000241d  mov     eax, dword ptr [rbp+37h+Size]
0x180002420  mov     r8, r13; int
0x180002423  mov     [rsp+38h], eax; Size
0x180002427  mov     rdx, rsi; int
0x18000242a  mov     rax, [rbp+37h+arg_30]
0x18000242e  mov     [rsp+0D0h+var_A0], rax; void *
0x180002433  mov     rax, [rbp+37h+arg_28]
0x180002437  mov     [rsp+0D0h+Src], rax; Src
0x18000243c  mov     qword ptr [rsp+0D0h+dwFlags], rcx; __int64
0x180002441  mov     rcx, qword ptr [rbp+37h+arg_8]; int
0x180002445  call    ConstructDestinationInfo
0x18000244a  xor     esi, esi
0x18000244c  mov     ebx, eax
0x18000244e  test    r12, r12
0x180002451  jz      short loc_180002462
0x180002453  mov     rcx, r12; hMem
0x180002456  call    cs:__imp_GlobalFree
0x18000245d  nop     dword ptr [rax+rax+00h]
0x180002462  test    r15, r15
0x180002465  jz      short loc_180002476
0x180002467  mov     rcx, r15; hMem
0x18000246a  call    cs:__imp_GlobalFree
0x180002471  nop     dword ptr [rax+rax+00h]
0x180002476  test    r14, r14
0x180002479  jz      short loc_18000248A
0x18000247b  mov     rcx, r14; hMem
0x18000247e  call    cs:__imp_GlobalFree
0x180002485  nop     dword ptr [rax+rax+00h]
0x18000248a  cmp     [rbp+37h+lpMem], rsi
0x18000248e  jz      short loc_1800024B1
0x180002490  call    cs:__imp_GetProcessHeap
0x180002497  nop     dword ptr [rax+rax+00h]
0x18000249c  mov     r8, [rbp+37h+lpMem]; lpMem
0x1800024a0  xor     edx, edx; dwFlags
0x1800024a2  mov     rcx, rax; hHeap
0x1800024a5  call    cs:__imp_HeapFree
0x1800024ac  nop     dword ptr [rax+rax+00h]
0x1800024b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800024b8  lea     rax, WPP_GLOBAL_Control
0x1800024bf  cmp     rcx, rax
0x1800024c2  jz      short loc_1800024DE
0x1800024c4  mov     eax, [rcx+1Ch]
0x1800024c7  and     eax, 0C0h
0x1800024cc  cmp     al, 0C0h
0x1800024ce  jnz     short loc_1800024DE
0x1800024d0  mov     rcx, [rcx+10h]
0x1800024d4  mov     edx, 28h ; '('
0x1800024d9  call    WPP_SF_
0x1800024de  mov     eax, ebx
0x1800024e0  mov     rbx, [rsp+0D0h+arg_0]
0x1800024e8  add     rsp, 0A0h
0x1800024ef  pop     r15
0x1800024f1  pop     r14
0x1800024f3  pop     r13
0x1800024f5  pop     r12
0x1800024f7  pop     rdi
0x1800024f8  pop     rsi
0x1800024f9  pop     rbp
0x1800024fa  retn
0x1800024fc  xor     r9d, r9d; pszProxyBypassW
0x1800024ff  mov     [rsp+0D0h+dwFlags], eax; dwFlags
0x180002503  xor     r8d, r8d; pszProxyW
0x180002506  lea     rcx, pszAgentW; "SSTP"
0x18000250d  mov     edx, edi; dwAccessType
0x18000250f  call    cs:__imp_WinHttpOpen
0x180002516  nop     dword ptr [rax+rax+00h]
0x18000251b  mov     rsi, rax
0x18000251e  test    rax, rax
0x180002521  jnz     short loc_18000256D
0x180002523  call    cs:__imp_GetLastError
0x18000252a  nop     dword ptr [rax+rax+00h]
0x18000252f  mov     ebx, eax
0x180002531  mov     rcx, cs:WPP_GLOBAL_Control
0x180002538  lea     rax, WPP_GLOBAL_Control
0x18000253f  cmp     rcx, rax
0x180002542  jz      loc_1800025E3
0x180002548  test    byte ptr [rcx+1Ch], 40h
0x18000254c  jz      loc_1800025E3
0x180002552  cmp     [rcx+19h], dil
0x180002556  jb      loc_1800025E3
0x18000255c  mov     rcx, [rcx+10h]
0x180002560  lea     edx, [rsi+26h]
0x180002563  mov     r9d, ebx
0x180002566  call    WPP_SF_d
0x18000256b  jmp     short loc_1800025E3
0x18000256d  mov     rdx, [rbp+37h+lpMem]; lpcwszUrl
0x180002571  lea     r9, [rbp+37h+pProxyInfo]; pProxyInfo
0x180002575  lea     r8, [rbp+37h+pAutoProxyOptions]; pAutoProxyOptions
0x180002579  mov     rcx, rsi; hSession
0x18000257c  call    cs:__imp_WinHttpGetProxyForUrl
0x180002583  nop     dword ptr [rax+rax+00h]
0x180002588  test    eax, eax
0x18000258a  jnz     short loc_1800025CC
0x18000258c  call    cs:__imp_GetLastError
0x180002593  nop     dword ptr [rax+rax+00h]
0x180002598  mov     ebx, eax
0x18000259a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800025a1  lea     rax, WPP_GLOBAL_Control
0x1800025a8  cmp     rcx, rax
0x1800025ab  jz      short loc_1800025D4
0x1800025ad  test    byte ptr [rcx+1Ch], 40h
0x1800025b1  jz      short loc_1800025D4
0x1800025b3  cmp     [rcx+19h], dil
0x1800025b7  jb      short loc_1800025D4
0x1800025b9  mov     rcx, [rcx+10h]
0x1800025bd  mov     edx, 27h ; '''
0x1800025c2  mov     r9d, ebx
0x1800025c5  call    WPP_SF_d
0x1800025ca  jmp     short loc_1800025D4
0x1800025cc  mov     r15, [rbp+37h+pProxyInfo.lpszProxy]
0x1800025d0  mov     r14, [rbp+37h+pProxyInfo.lpszProxyBypass]
0x1800025d4  mov     rcx, rsi; hInternet
0x1800025d7  call    cs:__imp_WinHttpCloseHandle
0x1800025de  nop     dword ptr [rax+rax+00h]
0x1800025e3  mov     rsi, [rbp+37h+arg_10]
0x1800025e7  mov     rax, [rbp+37h+arg_20]
0x1800025eb  mov     [rax], ebx
0x1800025ed  xor     eax, eax
0x1800025ef  test    ebx, ebx
0x1800025f1  jnz     loc_180002417
0x1800025f7  mov     r9, r15
0x1800025fa  mov     rcx, r14
0x1800025fd  jmp     loc_18000241D
```
