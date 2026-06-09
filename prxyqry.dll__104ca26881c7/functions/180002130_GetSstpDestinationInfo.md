# GetSstpDestinationInfo

- ea: `0x180002130`
- end: `0x180002512`
- name: `GetSstpDestinationInfo`
- size: `994`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64, void *, void *, size_t Size, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800014bc`
- `0x180002130`
- `0x180002560`
- `0x180002dd4`
- `0x180002e04`
- `0x180002e48`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800023d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800023d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800023e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800023e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000223f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002453`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800024a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000223f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002453`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800024a8`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800023ab`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800023b9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800023c7`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800023ab`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800023b9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800023c7`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18000249e`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18000249e`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x1800021c3`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x1800021c3`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18000222d`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18000222d`
- `WINHTTP!WinHttpCloseHandle` at `0x1800024ed`
- `WINHTTP!WinHttpCloseHandle` at `0x1800024ed`
- `WINHTTP!WinHttpOpen` at `0x180002445`
- `WINHTTP!WinHttpOpen` at `0x180002445`

## pseudocode

```c
__int64 __fastcall GetSstpDestinationInfo(
        __int64 a1,
        int a2,
        int a3,
        char a4,
        DWORD *a5,
        void *Src,
        void *a7,
        size_t Size,
        unsigned int a9)
{
  int v10; // esi
  LPWSTR lpszAutoConfigUrl; // r12
  LPWSTR lpszProxyBypass; // r14
  LPWSTR lpszProxy; // r15
  DWORD LastError; // eax
  __int64 v16; // r8
  DWORD SstpUrlForDestination; // ebx
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  BOOL fAutoDetect; // eax
  DWORD dwFlags; // ecx
  __int64 v22; // r8
  int v23; // r9d
  __int64 v24; // rcx
  unsigned int v25; // ebx
  HANDLE ProcessHeap; // rax
  void *v28; // rax
  void *v29; // rsi
  __int64 v30; // r8
  __int64 v31; // r8
  size_t v32; // [rsp+40h] [rbp-61h]
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
    SstpUrlForDestination = 0;
    if ( WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig) )
    {
      fAutoDetect = pProxyConfig.fAutoDetect;
    }
    else
    {
      LastError = GetLastError();
      SstpUrlForDestination = LastError;
      if ( LastError != 2 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          v19 = 35;
          goto LABEL_10;
        }
LABEL_62:
        *a5 = SstpUrlForDestination;
        if ( !SstpUrlForDestination )
          goto LABEL_63;
LABEL_36:
        v23 = 0;
        v24 = 0;
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
      SstpUrlForDestination = GetSstpUrlForDestination(a9, a1, &lpMem);
      if ( SstpUrlForDestination )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, v22, SstpUrlForDestination);
          *a5 = SstpUrlForDestination;
          goto LABEL_36;
        }
      }
      else
      {
        v28 = WinHttpOpen(L"SSTP", 1u, 0, 0, 0);
        v29 = v28;
        if ( v28 )
        {
          if ( WinHttpGetProxyForUrl(v28, (LPCWSTR)lpMem, &pAutoProxyOptions, &pProxyInfo) )
          {
            lpszProxy = pProxyInfo.lpszProxy;
            lpszProxyBypass = pProxyInfo.lpszProxyBypass;
          }
          else
          {
            SstpUrlForDestination = GetLastError();
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, v31, SstpUrlForDestination);
            }
          }
          WinHttpCloseHandle(v29);
        }
        else
        {
          SstpUrlForDestination = GetLastError();
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, v30, SstpUrlForDestination);
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
    SstpUrlForDestination = LastError;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v19 = 34;
LABEL_10:
      WPP_SF_d(v18[2], v19, v16, LastError);
      goto LABEL_62;
    }
    goto LABEL_62;
  }
  lpszProxy = pProxyInfo.lpszProxy;
  lpszProxyBypass = pProxyInfo.lpszProxyBypass;
  *a5 = 0;
LABEL_63:
  v23 = (int)lpszProxy;
  v24 = (__int64)lpszProxyBypass;
LABEL_37:
  LODWORD(v32) = Size;
  v25 = ConstructDestinationInfo(a2, v10, a1, v23, v24, Src, a7, v32);
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
  return v25;
}

```

## disassembly

```asm
0x180002130  mov     rax, rsp
0x180002133  mov     [rax+8], rbx
0x180002137  mov     [rax+18h], r8
0x18000213b  mov     [rax+10h], rdx
0x18000213f  push    rbp
0x180002140  push    rsi
0x180002141  push    rdi
0x180002142  push    r12
0x180002144  push    r13
0x180002146  push    r14
0x180002148  push    r15
0x18000214a  lea     rbp, [rax-3Fh]
0x18000214e  sub     rsp, 0A0h
0x180002155  xor     edx, edx
0x180002157  xorps   xmm0, xmm0
0x18000215a  xorps   xmm1, xmm1
0x18000215d  mov     [rbp+37h+lpMem], rdx
0x180002161  xor     eax, eax
0x180002163  mov     bl, r9b
0x180002166  mov     [rbp+37h+pProxyInfo.lpszProxyBypass], rax
0x18000216a  mov     rsi, r8
0x18000216d  mov     r13, rcx
0x180002170  mov     r12d, edx
0x180002173  mov     r14d, edx
0x180002176  mov     r15d, edx
0x180002179  movups  xmmword ptr [rbp+37h+pProxyConfig.fAutoDetect], xmm0
0x18000217d  movups  xmmword ptr [rbp+37h+pProxyConfig.lpszProxy], xmm0
0x180002181  movups  xmmword ptr [rbp+37h+pAutoProxyOptions.dwFlags], xmm1
0x180002185  movups  xmmword ptr [rbp+37h+pAutoProxyOptions.lpvReserved], xmm1
0x180002189  movups  xmmword ptr [rbp+37h+pProxyInfo.dwAccessType], xmm0
0x18000218d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002194  lea     rdi, WPP_GLOBAL_Control
0x18000219b  cmp     rcx, rdi
0x18000219e  jz      short loc_1800021BB
0x1800021a0  mov     eax, [rcx+1Ch]
0x1800021a3  and     eax, 0C0h
0x1800021a8  cmp     al, 0C0h
0x1800021aa  jnz     short loc_1800021BB
0x1800021ac  mov     rcx, [rcx+10h]
0x1800021b0  lea     edx, [r15+21h]
0x1800021b4  call    WPP_SF_
0x1800021b9  xor     edx, edx
0x1800021bb  test    bl, bl
0x1800021bd  jz      short loc_180002227
0x1800021bf  lea     rcx, [rbp+37h+pProxyInfo]; pProxyInfo
0x1800021c3  call    cs:__imp_WinHttpGetDefaultProxyConfiguration
0x1800021c9  xor     ecx, ecx
0x1800021cb  test    eax, eax
0x1800021cd  jnz     short loc_180002214
0x1800021cf  call    cs:__imp_GetLastError
0x1800021d5  mov     ebx, eax
0x1800021d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800021de  cmp     rcx, rdi
0x1800021e1  jz      loc_1800024F7
0x1800021e7  test    byte ptr [rcx+1Ch], 40h
0x1800021eb  jz      loc_1800024F7
0x1800021f1  mov     edi, 1
0x1800021f6  cmp     [rcx+19h], dil
0x1800021fa  jb      loc_1800024F7
0x180002200  lea     edx, [rdi+21h]
0x180002203  mov     rcx, [rcx+10h]
0x180002207  mov     r9d, eax
0x18000220a  call    WPP_SF_d
0x18000220f  jmp     loc_1800024F7
0x180002214  mov     rax, [rbp+37h+arg_20]
0x180002218  mov     r15, [rbp+37h+pProxyInfo.lpszProxy]
0x18000221c  mov     r14, [rbp+37h+pProxyInfo.lpszProxyBypass]
0x180002220  mov     [rax], ecx
0x180002222  jmp     loc_180002507
0x180002227  lea     rcx, [rbp+37h+pProxyConfig]; pProxyConfig
0x18000222b  mov     ebx, edx
0x18000222d  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x180002233  xor     r8d, r8d
0x180002236  mov     edi, 1
0x18000223b  test    eax, eax
0x18000223d  jnz     short loc_180002286
0x18000223f  call    cs:__imp_GetLastError
0x180002245  mov     ebx, eax
0x180002247  cmp     eax, 2
0x18000224a  jz      short loc_18000227C
0x18000224c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002253  lea     rdx, WPP_GLOBAL_Control
0x18000225a  cmp     rcx, rdx
0x18000225d  jz      loc_1800024F7
0x180002263  test    byte ptr [rcx+1Ch], 40h
0x180002267  jz      loc_1800024F7
0x18000226d  cmp     [rcx+19h], dil
0x180002271  jb      loc_1800024F7
0x180002277  lea     edx, [rdi+22h]
0x18000227a  jmp     short loc_180002203
0x18000227c  mov     eax, edi
0x18000227e  xor     r8d, r8d
0x180002281  mov     [rbp+37h+pProxyConfig.fAutoDetect], eax
0x180002284  jmp     short loc_180002289
0x180002286  mov     eax, [rbp+37h+pProxyConfig.fAutoDetect]
0x180002289  test    eax, eax
0x18000228b  jnz     short loc_1800022D5
0x18000228d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002294  lea     rdx, WPP_GLOBAL_Control
0x18000229b  cmp     rcx, rdx
0x18000229e  jz      short loc_1800022C8
0x1800022a0  test    byte ptr [rcx+1Ch], 40h
0x1800022a4  jz      short loc_1800022C8
0x1800022a6  cmp     byte ptr [rcx+19h], 2
0x1800022aa  jb      short loc_1800022C8
0x1800022ac  mov     rax, [rbp+37h+pProxyConfig.lpszProxyBypass]
0x1800022b0  mov     r9, [rbp+37h+pProxyConfig.lpszProxy]
0x1800022b4  mov     rcx, [rcx+10h]
0x1800022b8  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x1800022bd  call    WPP_SF_SS
0x1800022c2  mov     eax, [rbp+37h+pProxyConfig.fAutoDetect]
0x1800022c5  xor     r8d, r8d
0x1800022c8  mov     r15, [rbp+37h+pProxyConfig.lpszProxy]
0x1800022cc  mov     r14, [rbp+37h+pProxyConfig.lpszProxyBypass]
0x1800022d0  mov     ecx, [rbp+37h+pAutoProxyOptions.dwFlags]
0x1800022d3  jmp     short loc_1800022E1
0x1800022d5  mov     ecx, edi
0x1800022d7  mov     [rbp+37h+pAutoProxyOptions.dwAutoDetectFlags], 3
0x1800022de  mov     [rbp+37h+pAutoProxyOptions.dwFlags], ecx
0x1800022e1  mov     rdx, [rbp+37h+pProxyConfig.lpszAutoConfigUrl]
0x1800022e5  test    rdx, rdx
0x1800022e8  jz      short loc_180002302
0x1800022ea  cmp     [rdx], r8w
0x1800022ee  jz      short loc_180002302
0x1800022f0  mov     eax, edi
0x1800022f2  mov     [rbp+37h+pAutoProxyOptions.lpszAutoConfigUrl], rdx
0x1800022f6  or      ecx, 2
0x1800022f9  mov     [rbp+37h+pProxyConfig.fAutoDetect], eax
0x1800022fc  mov     [rbp+37h+pAutoProxyOptions.dwFlags], ecx
0x1800022ff  mov     r12, rdx
0x180002302  test    eax, eax
0x180002304  jz      loc_1800024F7
0x18000230a  mov     ecx, [rbp+37h+arg_40]
0x180002310  lea     r8, [rbp+37h+lpMem]
0x180002314  mov     rdx, r13
0x180002317  call    GetSstpUrlForDestination
0x18000231c  mov     ebx, eax
0x18000231e  xor     eax, eax
0x180002320  test    ebx, ebx
0x180002322  jz      loc_180002432
0x180002328  mov     rcx, cs:WPP_GLOBAL_Control
0x18000232f  lea     rax, WPP_GLOBAL_Control
0x180002336  cmp     rcx, rax
0x180002339  jz      loc_1800024F7
0x18000233f  test    byte ptr [rcx+1Ch], 40h
0x180002343  jz      loc_1800024F7
0x180002349  cmp     [rcx+19h], dil
0x18000234d  jb      loc_1800024F7
0x180002353  mov     rcx, [rcx+10h]
0x180002357  mov     edx, 25h ; '%'
0x18000235c  mov     r9d, ebx
0x18000235f  call    WPP_SF_d
0x180002364  mov     rax, [rbp+37h+arg_20]
0x180002368  mov     [rax], ebx
0x18000236a  xor     eax, eax
0x18000236c  mov     r9, rax; int
0x18000236f  mov     rcx, rax
0x180002372  mov     eax, dword ptr [rbp+37h+Size]
0x180002375  mov     r8, r13; int
0x180002378  mov     [rsp+38h], eax; Size
0x18000237c  mov     rdx, rsi; int
0x18000237f  mov     rax, [rbp+37h+arg_30]
0x180002383  mov     [rsp+0D0h+var_A0], rax; void *
0x180002388  mov     rax, [rbp+37h+arg_28]
0x18000238c  mov     [rsp+0D0h+Src], rax; Src
0x180002391  mov     qword ptr [rsp+0D0h+dwFlags], rcx; __int64
0x180002396  mov     rcx, qword ptr [rbp+37h+arg_8]; int
0x18000239a  call    ConstructDestinationInfo
0x18000239f  xor     esi, esi
0x1800023a1  mov     ebx, eax
0x1800023a3  test    r12, r12
0x1800023a6  jz      short loc_1800023B1
0x1800023a8  mov     rcx, r12; hMem
0x1800023ab  call    cs:__imp_GlobalFree
0x1800023b1  test    r15, r15
0x1800023b4  jz      short loc_1800023BF
0x1800023b6  mov     rcx, r15; hMem
0x1800023b9  call    cs:__imp_GlobalFree
0x1800023bf  test    r14, r14
0x1800023c2  jz      short loc_1800023CD
0x1800023c4  mov     rcx, r14; hMem
0x1800023c7  call    cs:__imp_GlobalFree
0x1800023cd  cmp     [rbp+37h+lpMem], rsi
0x1800023d1  jz      short loc_1800023E8
0x1800023d3  call    cs:__imp_GetProcessHeap
0x1800023d9  mov     r8, [rbp+37h+lpMem]; lpMem
0x1800023dd  xor     edx, edx; dwFlags
0x1800023df  mov     rcx, rax; hHeap
0x1800023e2  call    cs:__imp_HeapFree
0x1800023e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800023ef  lea     rax, WPP_GLOBAL_Control
0x1800023f6  cmp     rcx, rax
0x1800023f9  jz      short loc_180002415
0x1800023fb  mov     eax, [rcx+1Ch]
0x1800023fe  and     eax, 0C0h
0x180002403  cmp     al, 0C0h
0x180002405  jnz     short loc_180002415
0x180002407  mov     rcx, [rcx+10h]
0x18000240b  mov     edx, 28h ; '('
0x180002410  call    WPP_SF_
0x180002415  mov     eax, ebx
0x180002417  mov     rbx, [rsp+0D0h+arg_0]
0x18000241f  add     rsp, 0A0h
0x180002426  pop     r15
0x180002428  pop     r14
0x18000242a  pop     r13
0x18000242c  pop     r12
0x18000242e  pop     rdi
0x18000242f  pop     rsi
0x180002430  pop     rbp
0x180002431  retn
0x180002432  xor     r9d, r9d; pszProxyBypassW
0x180002435  mov     [rsp+0D0h+dwFlags], eax; dwFlags
0x180002439  xor     r8d, r8d; pszProxyW
0x18000243c  lea     rcx, pszAgentW; "SSTP"
0x180002443  mov     edx, edi; dwAccessType
0x180002445  call    cs:__imp_WinHttpOpen
0x18000244b  mov     rsi, rax
0x18000244e  test    rax, rax
0x180002451  jnz     short loc_18000248F
0x180002453  call    cs:__imp_GetLastError
0x180002459  mov     ebx, eax
0x18000245b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002462  lea     rax, WPP_GLOBAL_Control
0x180002469  cmp     rcx, rax
0x18000246c  jz      loc_1800024F3
0x180002472  test    byte ptr [rcx+1Ch], 40h
0x180002476  jz      short loc_1800024F3
0x180002478  cmp     [rcx+19h], dil
0x18000247c  jb      short loc_1800024F3
0x18000247e  mov     rcx, [rcx+10h]
0x180002482  lea     edx, [rsi+26h]
0x180002485  mov     r9d, ebx
0x180002488  call    WPP_SF_d
0x18000248d  jmp     short loc_1800024F3
0x18000248f  mov     rdx, [rbp+37h+lpMem]; lpcwszUrl
0x180002493  lea     r9, [rbp+37h+pProxyInfo]; pProxyInfo
0x180002497  lea     r8, [rbp+37h+pAutoProxyOptions]; pAutoProxyOptions
0x18000249b  mov     rcx, rsi; hSession
0x18000249e  call    cs:__imp_WinHttpGetProxyForUrl
0x1800024a4  test    eax, eax
0x1800024a6  jnz     short loc_1800024E2
0x1800024a8  call    cs:__imp_GetLastError
0x1800024ae  mov     ebx, eax
0x1800024b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800024b7  lea     rax, WPP_GLOBAL_Control
0x1800024be  cmp     rcx, rax
0x1800024c1  jz      short loc_1800024EA
0x1800024c3  test    byte ptr [rcx+1Ch], 40h
0x1800024c7  jz      short loc_1800024EA
0x1800024c9  cmp     [rcx+19h], dil
0x1800024cd  jb      short loc_1800024EA
0x1800024cf  mov     rcx, [rcx+10h]
0x1800024d3  mov     edx, 27h ; '''
0x1800024d8  mov     r9d, ebx
0x1800024db  call    WPP_SF_d
0x1800024e0  jmp     short loc_1800024EA
0x1800024e2  mov     r15, [rbp+37h+pProxyInfo.lpszProxy]
0x1800024e6  mov     r14, [rbp+37h+pProxyInfo.lpszProxyBypass]
0x1800024ea  mov     rcx, rsi; hInternet
0x1800024ed  call    cs:__imp_WinHttpCloseHandle
0x1800024f3  mov     rsi, [rbp+37h+arg_10]
0x1800024f7  mov     rax, [rbp+37h+arg_20]
0x1800024fb  mov     [rax], ebx
0x1800024fd  xor     eax, eax
0x1800024ff  test    ebx, ebx
0x180002501  jnz     loc_18000236C
0x180002507  mov     r9, r15
0x18000250a  mov     rcx, r14
0x18000250d  jmp     loc_180002372
```
