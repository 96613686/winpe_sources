# GetProxiesForUrl

- ea: `0x1800cfb78`
- end: `0x1800cfd10`
- name: `GetProxiesForUrl`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800cf748`

## callees

- `0x180008618`
- `0x18000933c`
- `0x1800a840c`
- `0x1800cfb78`
- `0x1800d004c`
- `0x1800f82f0`

## import_xrefs

- `WINHTTP!WinHttpGetProxyForUrlEx` at `0x1800cfc7a`
- `WINHTTP!WinHttpGetProxyForUrlEx` at `0x1800cfc7a`
- `WINHTTP!WinHttpCreateProxyResolver` at `0x1800cfba9`
- `WINHTTP!WinHttpCreateProxyResolver` at `0x1800cfba9`
- `WINHTTP!WinHttpSetOption` at `0x1800cfc0b`
- `WINHTTP!WinHttpSetOption` at `0x1800cfc0b`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800cfc30`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800cfc30`
- `WINHTTP!WinHttpCloseHandle` at `0x1800cfcf1`
- `WINHTTP!WinHttpCloseHandle` at `0x1800cfcf1`

## string_xrefs

- `0x1800cfbc5`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\HttpAgent.cpp`
- `0x1800cfc45`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\HttpAgent.cpp`
- `0x1800cfccb`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\HttpAgent.cpp`

## pseudocode

```c
__int64 __fastcall GetProxiesForUrl(void *a1, const WCHAR *a2, WINHTTP_AUTOPROXY_OPTIONS *a3, __int64 a4)
{
  signed int v7; // eax
  unsigned int LastError; // ebx
  const char *v9; // r9
  __int64 v10; // rdx
  signed int ProxyForUrl; // eax
  __int64 v12; // rdx
  _QWORD v14[2]; // [rsp+20h] [rbp-50h] BYREF
  char v15; // [rsp+30h] [rbp-40h]
  unsigned int *Buffer; // [rsp+38h] [rbp-38h] BYREF
  unsigned int v17; // [rsp+40h] [rbp-30h] BYREF
  __int64 v18; // [rsp+48h] [rbp-28h]
  __int64 v19; // [rsp+50h] [rbp-20h] BYREF
  HINTERNET phResolver; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  phResolver = 0;
  v7 = WinHttpCreateProxyResolver(a1, &phResolver);
  LastError = (unsigned __int16)v7 | 0x80070000;
  if ( v7 <= 0 )
    LastError = v7;
  if ( (LastError & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5DA,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\HttpAgent.cpp",
      (const char *)LastError,
      v14[0]);
    goto LABEL_21;
  }
  v17 = 0;
  v19 = 0;
  v18 = a4;
  Buffer = &v17;
  if ( !WinHttpSetOption(phResolver, 0x2Du, &Buffer, 8u) )
  {
    v10 = 1569;
LABEL_9:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v10,
                  (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\HttpAgent.cpp",
                  v9);
    goto LABEL_21;
  }
  if ( WinHttpSetStatusCallback(phResolver, GetProxiesForUrl_::_2_::_lambda_1_::_lambda_invoker_cdecl_, 0x1200800u, 0) == (WINHTTP_STATUS_CALLBACK)-1LL )
  {
    v10 = 1574;
    goto LABEL_9;
  }
  v14[0] = &phResolver;
  v15 = 1;
  v14[1] = &v17;
  ProxyForUrl = WinHttpGetProxyForUrlEx(phResolver, a2, a3, (DWORD_PTR)Buffer);
  if ( ProxyForUrl == 997 )
  {
    if ( CAutoResetEvent::Wait((CAutoResetEvent *)&v19, 0x1388u) )
    {
      LastError = v17;
      goto LABEL_20;
    }
    LastError = -2147023436;
    v12 = 1593;
  }
  else
  {
    if ( ProxyForUrl )
    {
      LastError = (unsigned __int16)ProxyForUrl | 0x80070000;
      if ( ProxyForUrl <= 0 )
        LastError = ProxyForUrl;
    }
    else
    {
      LastError = -2147467259;
    }
    v12 = 1588;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\HttpAgent.cpp",
    (const char *)LastError,
    v14[0]);
LABEL_20:
  wil::details::lambda_call__GetProxiesForUrl_::_2_::_lambda_2___::_lambda_call__GetProxiesForUrl_::_2_::_lambda_2___(v14);
LABEL_21:
  if ( phResolver )
    WinHttpCloseHandle(phResolver);
  return LastError;
}

```

## disassembly

```asm
0x1800cfb78  push    rbp
0x1800cfb7a  push    rbx
0x1800cfb7b  push    rsi
0x1800cfb7c  push    rdi
0x1800cfb7d  push    r14
0x1800cfb7f  mov     rbp, rsp
0x1800cfb82  sub     rsp, 70h
0x1800cfb86  mov     rax, cs:__security_cookie
0x1800cfb8d  xor     rax, rsp
0x1800cfb90  mov     [rbp+var_10], rax
0x1800cfb94  mov     rsi, rdx
0x1800cfb97  mov     [rbp+phResolver], 0
0x1800cfb9f  lea     rdx, [rbp+phResolver]; phResolver
0x1800cfba3  mov     rdi, r9
0x1800cfba6  mov     r14, r8
0x1800cfba9  call    cs:__imp_WinHttpCreateProxyResolver
0x1800cfbaf  movzx   ebx, ax
0x1800cfbb2  or      ebx, 80070000h
0x1800cfbb8  test    eax, eax
0x1800cfbba  cmovle  ebx, eax
0x1800cfbbd  test    ebx, ebx
0x1800cfbbf  jns     short loc_1800CFBDE
0x1800cfbc1  mov     rcx, [rbp+28h]; this
0x1800cfbc5  lea     r8, aCW1SSrcDeliver_73; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800cfbcc  mov     r9d, ebx; char *
0x1800cfbcf  mov     edx, 5DAh; void *
0x1800cfbd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cfbd9  jmp     loc_1800CFCE8
0x1800cfbde  mov     rcx, [rbp+phResolver]; hInternet
0x1800cfbe2  lea     rax, [rbp+var_30]
0x1800cfbe6  mov     r9d, 8; dwBufferLength
0x1800cfbec  mov     [rbp+var_30], 0
0x1800cfbf3  lea     r8, [rbp+Buffer]; lpBuffer
0x1800cfbf7  mov     [rbp+var_20], 0
0x1800cfbff  mov     [rbp+var_28], rdi
0x1800cfc03  mov     [rbp+Buffer], rax
0x1800cfc07  lea     edx, [r9+25h]; dwOption
0x1800cfc0b  call    cs:__imp_WinHttpSetOption
0x1800cfc11  test    eax, eax
0x1800cfc13  jnz     short loc_1800CFC1C
0x1800cfc15  mov     edx, 621h
0x1800cfc1a  jmp     short loc_1800CFC41
0x1800cfc1c  mov     rcx, [rbp+phResolver]; hInternet
0x1800cfc20  lea     rdx, _GetProxiesForUrl____2____lambda_1____lambda_invoker_cdecl_; lpfnInternetCallback
0x1800cfc27  xor     r9d, r9d; dwReserved
0x1800cfc2a  mov     r8d, 1200800h; dwNotificationFlags
0x1800cfc30  call    cs:__imp_WinHttpSetStatusCallback
0x1800cfc36  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800cfc3a  jnz     short loc_1800CFC58
0x1800cfc3c  mov     edx, 626h; void *
0x1800cfc41  mov     rcx, [rbp+28h]; this
0x1800cfc45  lea     r8, aCW1SSrcDeliver_73; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800cfc4c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800cfc51  mov     ebx, eax
0x1800cfc53  jmp     loc_1800CFCE8
0x1800cfc58  mov     r9, [rbp+Buffer]; pContext
0x1800cfc5c  lea     rax, [rbp+phResolver]
0x1800cfc60  mov     rcx, [rbp+phResolver]; hResolver
0x1800cfc64  mov     r8, r14; pAutoProxyOptions
0x1800cfc67  mov     [rbp+var_50], rax
0x1800cfc6b  mov     rdx, rsi; pcwszUrl
0x1800cfc6e  lea     rax, [rbp+var_30]
0x1800cfc72  mov     [rbp+var_40], 1
0x1800cfc76  mov     [rbp+var_48], rax
0x1800cfc7a  call    cs:__imp_WinHttpGetProxyForUrlEx
0x1800cfc80  cmp     eax, 3E5h
0x1800cfc85  jz      short loc_1800CFCAB
0x1800cfc87  test    eax, eax
0x1800cfc89  jnz     short loc_1800CFC92
0x1800cfc8b  mov     ebx, 80004005h
0x1800cfc90  jmp     short loc_1800CFCA4
0x1800cfc92  movzx   ebx, ax
0x1800cfc95  or      ebx, 80070000h
0x1800cfc9b  test    eax, eax
0x1800cfc9d  cmovle  ebx, eax
0x1800cfca0  test    ebx, ebx
0x1800cfca2  jns     short loc_1800CFCDF
0x1800cfca4  mov     edx, 634h
0x1800cfca9  jmp     short loc_1800CFCC7
0x1800cfcab  mov     edx, 1388h; unsigned int
0x1800cfcb0  lea     rcx, [rbp+var_20]; this
0x1800cfcb4  call    ?Wait@CAutoResetEvent@@QEAA_NI@Z; CAutoResetEvent::Wait(uint)
0x1800cfcb9  test    al, al
0x1800cfcbb  jnz     short loc_1800CFCDC
0x1800cfcbd  mov     ebx, 800705B4h
0x1800cfcc2  mov     edx, 639h; void *
0x1800cfcc7  mov     rcx, [rbp+28h]; this
0x1800cfccb  lea     r8, aCW1SSrcDeliver_73; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800cfcd2  mov     r9d, ebx; char *
0x1800cfcd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cfcda  jmp     short loc_1800CFCDF
0x1800cfcdc  mov     ebx, [rbp+var_30]
0x1800cfcdf  lea     rcx, [rbp+var_50]
0x1800cfce3  call    wil__details__lambda_call__GetProxiesForUrl____2____lambda_2______lambda_call__GetProxiesForUrl____2____lambda_2___
0x1800cfce8  mov     rcx, [rbp+phResolver]; hInternet
0x1800cfcec  test    rcx, rcx
0x1800cfcef  jz      short loc_1800CFCF7
0x1800cfcf1  call    cs:__imp_WinHttpCloseHandle
0x1800cfcf7  mov     eax, ebx
0x1800cfcf9  mov     rcx, [rbp+var_10]
0x1800cfcfd  xor     rcx, rsp; StackCookie
0x1800cfd00  call    __security_check_cookie
0x1800cfd05  add     rsp, 70h
0x1800cfd09  pop     r14
0x1800cfd0b  pop     rdi
0x1800cfd0c  pop     rsi
0x1800cfd0d  pop     rbx
0x1800cfd0e  pop     rbp
0x1800cfd0f  retn
```
