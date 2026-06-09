# GetProxyList(void *,ushort const *,_PROXY_LIST *)

- ea: `0x140050ff0`
- end: `0x14005115d`
- name: `?GetProxyList@@YAJPEAXPEBGPEAU_PROXY_LIST@@@Z`
- size: `365`
- prototype: `__int64 __fastcall(HINTERNET hSession, LPCWSTR lpcwszUrl, struct _PROXY_LIST *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400506ac`

## callees

- `0x140050260`
- `0x140050ff0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140051035`
- `KERNEL32!GetLastError` at `0x14005107e`
- `KERNEL32!GetLastError` at `0x140051121`
- `KERNEL32!GetLastError` at `0x140051035`
- `KERNEL32!GetLastError` at `0x14005107e`
- `KERNEL32!GetLastError` at `0x140051121`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x14005106e`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x14005106e`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x140051111`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x140051111`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x140051023`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x140051023`

## pseudocode

```c
__int64 __fastcall GetProxyList(HINTERNET hSession, LPCWSTR lpcwszUrl, struct _PROXY_LIST *a3)
{
  unsigned int v6; // ebx
  signed int LastError; // eax
  bool v8; // sf
  __int64 result; // rax
  signed int v10; // eax
  bool v11; // sf
  bool v12; // zf
  DWORD dwFlags; // eax
  char *v14; // rbx
  signed int v15; // eax
  bool v16; // sf
  WINHTTP_AUTOPROXY_OPTIONS pAutoProxyOptions; // [rsp+20h] [rbp-48h] BYREF
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig; // [rsp+40h] [rbp-28h] BYREF

  memset(&pProxyConfig, 0, sizeof(pProxyConfig));
  memset(&pAutoProxyOptions, 0, sizeof(pAutoProxyOptions));
  if ( WinHttpGetDefaultProxyConfiguration((WINHTTP_PROXY_INFO *)((char *)a3 + 32)) )
    goto LABEL_5;
  v6 = 0;
  LastError = GetLastError();
  v8 = LastError < 0;
  if ( LastError > 0 )
    v8 = 1;
  if ( !v8 )
  {
LABEL_5:
    result = AddProxyServers(a3, (struct _PROXY_LIST *)((char *)a3 + 32));
    if ( (int)result < 0 )
      return result;
    v6 = 1;
  }
  if ( !WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig) )
  {
    v10 = GetLastError();
    v11 = v10 < 0;
    if ( v10 > 0 )
      v11 = 1;
    if ( v11 )
      goto LABEL_18;
  }
  v12 = !pProxyConfig.fAutoDetect;
  *((_QWORD *)a3 + 3 * v6 + 5) = pProxyConfig.lpszProxy;
  *((_QWORD *)a3 + 3 * v6 + 6) = pProxyConfig.lpszProxyBypass;
  if ( v12 )
  {
    dwFlags = pAutoProxyOptions.dwFlags;
  }
  else
  {
    dwFlags = 1;
    pAutoProxyOptions.dwAutoDetectFlags = 3;
    pAutoProxyOptions.dwFlags = 1;
  }
  if ( pProxyConfig.lpszAutoConfigUrl )
  {
    pAutoProxyOptions.lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
    pAutoProxyOptions.dwFlags = dwFlags | 2;
  }
  result = AddProxyServers(a3, (struct _PROXY_LIST *)((char *)a3 + 24 * v6 + 32));
  if ( (int)result >= 0 )
  {
    ++v6;
LABEL_18:
    v14 = (char *)a3 + 24 * v6;
    if ( !WinHttpGetProxyForUrl(hSession, lpcwszUrl, &pAutoProxyOptions, (WINHTTP_PROXY_INFO *)(v14 + 32)) )
    {
      v15 = GetLastError();
      v16 = v15 < 0;
      if ( v15 > 0 )
        v16 = 1;
      if ( v16 )
        return 0;
    }
    result = AddProxyServers(a3, (struct _WINHTTP_PROXY_INFO *)(v14 + 32));
    if ( (int)result >= 0 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140050ff0  push    rbp
0x140050ff2  push    rbx
0x140050ff3  push    rsi
0x140050ff4  push    rdi
0x140050ff5  push    r14
0x140050ff7  push    r15
0x140050ff9  mov     rbp, rsp
0x140050ffc  sub     rsp, 68h
0x140051000  xorps   xmm0, xmm0
0x140051003  xorps   xmm1, xmm1
0x140051006  mov     r15, rcx
0x140051009  mov     rdi, r8
0x14005100c  lea     rcx, [r8+20h]; pProxyInfo
0x140051010  mov     r14, rdx
0x140051013  movups  xmmword ptr [rbp+pProxyConfig.fAutoDetect], xmm0
0x140051017  movups  xmmword ptr [rbp+pProxyConfig.lpszProxy], xmm0
0x14005101b  movups  xmmword ptr [rbp+pAutoProxyOptions.dwFlags], xmm1
0x14005101f  movups  xmmword ptr [rbp+pAutoProxyOptions.lpvReserved], xmm1
0x140051023  call    cs:__imp_WinHttpGetDefaultProxyConfiguration
0x14005102a  nop     dword ptr [rax+rax+00h]
0x14005102f  test    eax, eax
0x140051031  jnz     short loc_140051051
0x140051033  xor     ebx, ebx
0x140051035  call    cs:__imp_GetLastError
0x14005103c  nop     dword ptr [rax+rax+00h]
0x140051041  test    eax, eax
0x140051043  jle     short loc_14005104F
0x140051045  movzx   eax, ax
0x140051048  or      eax, 80070000h
0x14005104d  test    eax, eax
0x14005104f  js      short loc_14005106A
0x140051051  lea     rdx, [rdi+20h]; struct _WINHTTP_PROXY_INFO *
0x140051055  mov     rcx, rdi; struct _PROXY_LIST *
0x140051058  call    ?AddProxyServers@@YAJPEAU_PROXY_LIST@@PEAU_WINHTTP_PROXY_INFO@@@Z; AddProxyServers(_PROXY_LIST *,_WINHTTP_PROXY_INFO *)
0x14005105d  test    eax, eax
0x14005105f  js      loc_14005114F
0x140051065  mov     ebx, 1
0x14005106a  lea     rcx, [rbp+pProxyConfig]; pProxyConfig
0x14005106e  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x140051075  nop     dword ptr [rax+rax+00h]
0x14005107a  test    eax, eax
0x14005107c  jnz     short loc_14005109A
0x14005107e  call    cs:__imp_GetLastError
0x140051085  nop     dword ptr [rax+rax+00h]
0x14005108a  test    eax, eax
0x14005108c  jle     short loc_140051098
0x14005108e  movzx   eax, ax
0x140051091  or      eax, 80070000h
0x140051096  test    eax, eax
0x140051098  js      short loc_1400510F9
0x14005109a  cmp     [rbp+pProxyConfig.fAutoDetect], 0
0x14005109e  mov     rax, [rbp+pProxyConfig.lpszProxy]
0x1400510a2  mov     ecx, ebx
0x1400510a4  lea     rdx, [rcx+rcx*2]
0x1400510a8  mov     [rdi+rdx*8+28h], rax
0x1400510ad  lea     rcx, [rcx+rcx*2]
0x1400510b1  mov     rax, [rbp+pProxyConfig.lpszProxyBypass]
0x1400510b5  mov     [rdi+rcx*8+30h], rax
0x1400510ba  jz      short loc_1400510CD
0x1400510bc  mov     eax, 1
0x1400510c1  mov     [rbp+pAutoProxyOptions.dwAutoDetectFlags], 3
0x1400510c8  mov     [rbp+pAutoProxyOptions.dwFlags], eax
0x1400510cb  jmp     short loc_1400510D0
0x1400510cd  mov     eax, [rbp+pAutoProxyOptions.dwFlags]
0x1400510d0  mov     rcx, [rbp+pProxyConfig.lpszAutoConfigUrl]
0x1400510d4  test    rcx, rcx
0x1400510d7  jz      short loc_1400510E3
0x1400510d9  or      eax, 2
0x1400510dc  mov     [rbp+pAutoProxyOptions.lpszAutoConfigUrl], rcx
0x1400510e0  mov     [rbp+pAutoProxyOptions.dwFlags], eax
0x1400510e3  add     rdx, 4
0x1400510e7  mov     rcx, rdi; struct _PROXY_LIST *
0x1400510ea  lea     rdx, [rdi+rdx*8]; struct _WINHTTP_PROXY_INFO *
0x1400510ee  call    ?AddProxyServers@@YAJPEAU_PROXY_LIST@@PEAU_WINHTTP_PROXY_INFO@@@Z; AddProxyServers(_PROXY_LIST *,_WINHTTP_PROXY_INFO *)
0x1400510f3  test    eax, eax
0x1400510f5  js      short loc_14005114F
0x1400510f7  inc     ebx
0x1400510f9  mov     eax, ebx
0x1400510fb  lea     r8, [rbp+pAutoProxyOptions]; pAutoProxyOptions
0x1400510ff  mov     rdx, r14; lpcwszUrl
0x140051102  lea     rcx, [rax+rax*2]
0x140051106  lea     rbx, [rdi+rcx*8]
0x14005110a  mov     rcx, r15; hSession
0x14005110d  lea     r9, [rbx+20h]; pProxyInfo
0x140051111  call    cs:__imp_WinHttpGetProxyForUrl
0x140051118  nop     dword ptr [rax+rax+00h]
0x14005111d  test    eax, eax
0x14005111f  jnz     short loc_14005113D
0x140051121  call    cs:__imp_GetLastError
0x140051128  nop     dword ptr [rax+rax+00h]
0x14005112d  test    eax, eax
0x14005112f  jle     short loc_14005113B
0x140051131  movzx   eax, ax
0x140051134  or      eax, 80070000h
0x140051139  test    eax, eax
0x14005113b  js      short loc_14005114D
0x14005113d  lea     rdx, [rbx+20h]; struct _WINHTTP_PROXY_INFO *
0x140051141  mov     rcx, rdi; struct _PROXY_LIST *
0x140051144  call    ?AddProxyServers@@YAJPEAU_PROXY_LIST@@PEAU_WINHTTP_PROXY_INFO@@@Z; AddProxyServers(_PROXY_LIST *,_WINHTTP_PROXY_INFO *)
0x140051149  test    eax, eax
0x14005114b  js      short loc_14005114F
0x14005114d  xor     eax, eax
0x14005114f  add     rsp, 68h
0x140051153  pop     r15
0x140051155  pop     r14
0x140051157  pop     rdi
0x140051158  pop     rsi
0x140051159  pop     rbx
0x14005115a  pop     rbp
0x14005115b  retn
```
