# KerbHttpSendRequest(_KDC_PROXY_CACHE_ENTRY *,_KERB_MESSAGE_BUFFER *,_KERB_MESSAGE_BUFFER *)

- ea: `0x180098a5c`
- end: `0x1800990eb`
- name: `?KerbHttpSendRequest@@YAKPEAU_KDC_PROXY_CACHE_ENTRY@@PEAU_KERB_MESSAGE_BUFFER@@1@Z`
- size: `1679`
- prototype: `__int64 __fastcall(struct _KDC_PROXY_CACHE_ENTRY *, struct _KERB_MESSAGE_BUFFER *, struct _KERB_MESSAGE_BUFFER *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18005228c`

## callees

- `0x1800069a0`
- `0x1800093f0`
- `0x180031f6c`
- `0x180032f70`
- `0x1800744cf`
- `0x18008b70c`
- `0x180095d90`
- `0x1800984d4`
- `0x180098a5c`
- `0x1800990f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098af7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098b76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098bb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098c40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098ea3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098fe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009905b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009909e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098af7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098b76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098bb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098c40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098ea3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098fe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009905b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009909e`
- `WINHTTP!WinHttpSetCredentials` at `0x180098e8e`
- `WINHTTP!WinHttpSetCredentials` at `0x180098e8e`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x180098fd4`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x180098fd4`
- `WINHTTP!WinHttpReadData` at `0x180098fb2`
- `WINHTTP!WinHttpReadData` at `0x180098fb2`
- `WINHTTP!WinHttpOpenRequest` at `0x180098ae9`
- `WINHTTP!WinHttpOpenRequest` at `0x180098ae9`
- `WINHTTP!WinHttpSetOption` at `0x180098b40`
- `WINHTTP!WinHttpSetOption` at `0x180098b6c`
- `WINHTTP!WinHttpSetOption` at `0x180098bac`
- `WINHTTP!WinHttpSetOption` at `0x180098b40`
- `WINHTTP!WinHttpSetOption` at `0x180098b6c`
- `WINHTTP!WinHttpSetOption` at `0x180098bac`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x180098c36`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x180098c36`
- `WINHTTP!WinHttpCloseHandle` at `0x1800990cf`
- `WINHTTP!WinHttpCloseHandle` at `0x1800990cf`

## string_xrefs

- `0x180098afd`: `WinHttpOpenRequest failed: %#x`
- `0x180098cc9`: `KerbGetAuthProxyCred failed to get BASIC credential for proxy %wZ: %#x, CacheEntry %p`
- `0x180098d1b`: `KerbGetAuthProxyCred failed to get DIGEST credential for proxy %wZ: %#x, CacheEntry %p`
- `0x180098d81`: `KerbHttpSendRequest cannot find a suitable auth scheme or creds for auth proxy: CacheEntry %p, SupportedSchemes %#x, FirstScheme %#x, DigestCred %d, BasicCred %d\n`
- `0x180098e1e`: `auth proxy settings: CacheEntry %p, Proxy %wZ, ProxyBypass %wZ, PorxyEpoch %d, Digest(%wZ, %d), Basic(%wZ, %d)\n`
- `0x180099061`: `WinHttpReadData failed: %#x`
- `0x180099048`: `WinHttpReadData returns unexpected amount of data: %#x`

## pseudocode

```c
__int64 __fastcall KerbHttpSendRequest(
        struct _KDC_PROXY_CACHE_ENTRY *a1,
        struct _KERB_MESSAGE_BUFFER *a2,
        struct _KERB_MESSAGE_BUFFER *a3)
{
  bool v3; // zf
  const WCHAR *v4; // r8
  void *v7; // rcx
  struct _KERB_AUTH_PROXY_CRED *v8; // r13
  void *v9; // r15
  DWORD LastError; // ebx
  __int64 v11; // rbx
  DWORD v12; // r12d
  _DWORD *v13; // rdi
  unsigned int v14; // eax
  const char *v15; // r9
  __int64 v16; // r8
  unsigned int v17; // edi
  int AuthProxyCred; // eax
  __int64 v19; // r8
  const char *v20; // r9
  BOOL v21; // ebx
  DWORD v22; // eax
  unsigned int v23; // eax
  char *v24; // rdi
  DWORD v25; // r14d
  DWORD v26; // ebx
  char *v27; // rax
  char *v28; // r12
  DWORD v29; // eax
  const char *v30; // r9
  __int64 v31; // r8
  struct _KERB_MESSAGE_BUFFER *v32; // rax
  LPCWSTR pwszReferrer; // [rsp+20h] [rbp-59h]
  LPCWSTR pwszReferrera; // [rsp+20h] [rbp-59h]
  LPCWSTR *ppwszAcceptTypes; // [rsp+28h] [rbp-51h]
  DWORD dwFlags[2]; // [rsp+30h] [rbp-49h]
  DWORD dwSupportedSchemes; // [rsp+60h] [rbp-19h] BYREF
  DWORD dwNumberOfBytesToRead; // [rsp+64h] [rbp-15h] BYREF
  unsigned int v40; // [rsp+68h] [rbp-11h] BYREF
  DWORD pdwAuthTarget; // [rsp+6Ch] [rbp-Dh] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+70h] [rbp-9h] BYREF
  struct _KERB_AUTH_PROXY_CRED *v43; // [rsp+78h] [rbp-1h] BYREF
  _DWORD v44[20]; // [rsp+80h] [rbp+7h] BYREF
  int Buffer; // [rsp+E0h] [rbp+67h] BYREF
  struct _KERB_MESSAGE_BUFFER *v46; // [rsp+E8h] [rbp+6Fh]
  struct _KERB_MESSAGE_BUFFER *v47; // [rsp+F0h] [rbp+77h]
  DWORD dwFirstScheme; // [rsp+F8h] [rbp+7Fh] BYREF

  v47 = a3;
  v46 = a2;
  *(_OWORD *)a3 = 0;
  v3 = *((_QWORD *)a1 + 11) == 0;
  v4 = L"KdcProxy";
  dwNumberOfBytesToRead = 0;
  if ( !v3 )
    v4 = (const WCHAR *)*((_QWORD *)a1 + 11);
  dwNumberOfBytesRead = 0;
  v7 = (void *)*((_QWORD *)a1 + 28);
  v40 = 0;
  v44[0] = 1;
  v8 = 0;
  v44[1] = 2;
  Buffer = 0;
  dwSupportedSchemes = 0;
  dwFirstScheme = 0;
  pdwAuthTarget = 0;
  v43 = 0;
  v9 = WinHttpOpenRequest(v7, L"POST", v4, 0, 0, 0, 0x800100u);
  if ( !v9 )
  {
    LastError = GetLastError();
    KerbTracerT::Log(1, "KerbHttpSendRequest", 3868, "WinHttpOpenRequest failed: %#x", LastError);
    return LastError;
  }
  v11 = 0;
  v12 = 1;
  do
  {
    v13 = &v44[v11];
    if ( !WinHttpSetOption(v9, 0x3Fu, v13, 4u) )
    {
      LastError = GetLastError();
      KerbTracerT::Log(1, "KerbHttpSendRequest", 3884, "WinHttpSetOption failed to set %#x: %#x", *v13, LastError);
      goto LABEL_70;
    }
    v11 = (unsigned int)(v11 + 1);
  }
  while ( (unsigned int)v11 < 2 );
  Buffer = 0;
  if ( !WinHttpSetOption(v9, 0x58u, &Buffer, 4u) )
  {
    LastError = GetLastError();
    KerbTracerT::Log(1, "KerbHttpSendRequest", 3901, "WinHttpSetOption failed to set %#x: %#x", Buffer, LastError);
    goto LABEL_70;
  }
  if ( !KerbGlobalNoRevocationCheck )
  {
    Buffer = 1;
    if ( !WinHttpSetOption(v9, 0x4Fu, &Buffer, 4u) )
    {
      LastError = GetLastError();
      KerbTracerT::Log(1, "KerbHttpSendRequest", 3919, "WinHttpSetOption failed to set %#x: %#x", Buffer, LastError);
      goto LABEL_70;
    }
  }
  v14 = KerbHttpSendRequestAndReceiveResponse(v9, *((const struct _CERT_CONTEXT **)a1 + 29), a2, &v40);
  LastError = v14;
  if ( v14 )
  {
    LODWORD(pwszReferrer) = v14;
    v15 = "KerbHttpSendRequestAndReceiveResponse failed: %#x";
    v16 = 3933;
    goto LABEL_15;
  }
  v17 = v40;
  if ( v40 != 407 )
    goto LABEL_46;
  if ( !WinHttpQueryAuthSchemes(v9, &dwSupportedSchemes, &dwFirstScheme, &pdwAuthTarget) )
  {
    LODWORD(pwszReferrer) = GetLastError();
    v15 = "WinHttpQueryAuthSchemes failed: %#x";
    LastError = (unsigned int)pwszReferrer;
    v16 = 3949;
    goto LABEL_15;
  }
  if ( pdwAuthTarget != 1 )
  {
    KerbTracerT::Log(1, "KerbHttpSendRequest", 3955, "WinHttpQueryAuthSchemes does not return schemes for auth proxy\n");
LABEL_47:
    LastError = v17;
    v15 = "WinHttpQueryHeaders returns http error: %d\n";
    LODWORD(pwszReferrer) = v17;
    v16 = 4083;
    goto LABEL_15;
  }
  KerbTracerT::Log(
    22,
    "KerbHttpSendRequest",
    3959,
    "WinHttpQueryAuthScheme returned proxy schemes: SupportedSchemes %#x, FirstScheme %#x\n",
    dwSupportedSchemes,
    dwFirstScheme);
  if ( dwFirstScheme != 1 )
    goto LABEL_27;
  AuthProxyCred = KerbGetAuthProxyCred(1u, (struct _KDC_PROXY_CACHE_ENTRY *)((char *)a1 + 96), &v43);
  if ( AuthProxyCred < 0 )
  {
    v19 = 3975;
LABEL_24:
    v20 = "KerbGetAuthProxyCred failed to get BASIC credential for proxy %wZ: %#x, CacheEntry %p";
LABEL_25:
    LODWORD(ppwszAcceptTypes) = AuthProxyCred;
    KerbTracerT::Log(1, "KerbHttpSendRequest", v19, v20, (char *)a1 + 96, ppwszAcceptTypes, WORD1(a1));
    goto LABEL_47;
  }
  v8 = v43;
  if ( !v43 )
  {
LABEL_27:
    if ( (dwSupportedSchemes & 8) != 0 )
    {
      AuthProxyCred = KerbGetAuthProxyCred(0, (struct _KDC_PROXY_CACHE_ENTRY *)((char *)a1 + 96), &v43);
      if ( AuthProxyCred < 0 )
      {
        v20 = "KerbGetAuthProxyCred failed to get DIGEST credential for proxy %wZ: %#x, CacheEntry %p";
        v19 = 3997;
        goto LABEL_25;
      }
      v8 = v43;
      if ( !v43 )
        goto LABEL_34;
      v12 = 8;
    }
    if ( !v8 )
    {
      v12 = 1;
LABEL_34:
      if ( dwFirstScheme == 1 || (dwSupportedSchemes & 1) == 0 )
        goto LABEL_39;
      AuthProxyCred = KerbGetAuthProxyCred(1u, (struct _KDC_PROXY_CACHE_ENTRY *)((char *)a1 + 96), &v43);
      if ( AuthProxyCred < 0 )
      {
        v19 = 4017;
        goto LABEL_24;
      }
      v8 = v43;
      if ( !v43 )
      {
LABEL_39:
        KerbTracerT::Log(
          1,
          "KerbHttpSendRequest",
          4031,
          "KerbHttpSendRequest cannot find a suitable auth scheme or creds for auth proxy: CacheEntry %p, SupportedScheme"
          "s %#x, FirstScheme %#x, DigestCred %d, BasicCred %d\n",
          (const void *)WORD1(a1),
          dwSupportedSchemes,
          dwFirstScheme,
          *((unsigned __int8 *)a1 + 136),
          *((unsigned __int8 *)a1 + 136));
        EventWriteNoAuthProxyCredHelper(a1, dwSupportedSchemes, dwFirstScheme);
        goto LABEL_47;
      }
    }
  }
  KerbTracerT::Log(
    22,
    "KerbHttpSendRequest",
    4040,
    "auth proxy settings: CacheEntry %p, Proxy %wZ, ProxyBypass %wZ, PorxyEpoch %d, Digest(%wZ, %d), Basic(%wZ, %d)\n",
    WORD1(a1),
    (char *)a1 + 96,
    (char *)a1 + 112,
    *((_DWORD *)a1 + 32),
    (char *)a1 + 144,
    *((_DWORD *)a1 + 35),
    (char *)a1 + 184,
    *((_DWORD *)a1 + 45));
  LODWORD(pwszReferrera) = v12;
  KerbTracerT::Log(
    22,
    "KerbHttpSendRequest",
    4042,
    "set auth proxy credential (%#x %wZ) and resend\n",
    pwszReferrera,
    (char *)v8 + 8);
  KerbRevealPassword((struct _UNICODE_STRING *)((char *)v8 + 24));
  v21 = WinHttpSetCredentials(v9, 1u, v12, *((LPCWSTR *)v8 + 2), *((LPCWSTR *)v8 + 4), 0);
  KerbHidePassword((struct _UNICODE_STRING *)((char *)v8 + 24));
  if ( !v21 )
  {
    v22 = GetLastError();
    v15 = "WinHttpSetCredentials failed: %#x";
    v16 = 4060;
    goto LABEL_42;
  }
  v23 = KerbHttpSendRequestAndReceiveResponse(v9, *((const struct _CERT_CONTEXT **)a1 + 29), v46, &v40);
  LastError = v23;
  if ( v23 )
  {
    dwFlags[0] = v23;
    LODWORD(pwszReferrer) = v12;
    KerbTracerT::Log(
      1,
      "KerbHttpSendRequest",
      4073,
      "KerbHttpSendRequestAndReceiveResponse failed with auth proxy credential (%#x %wZ): %#x",
      pwszReferrer,
      (char *)v8 + 8,
      *(_QWORD *)dwFlags);
    goto LABEL_70;
  }
  v17 = v40;
LABEL_46:
  if ( v17 != 200 )
    goto LABEL_47;
  v24 = 0;
  v25 = 0;
  while ( 1 )
  {
    if ( !WinHttpQueryDataAvailable(v9, &dwNumberOfBytesToRead) )
    {
      v29 = GetLastError();
      v30 = "WinHttpQueryDataAvailable failed: %#x";
      v31 = 4097;
LABEL_60:
      LODWORD(pwszReferrer) = v29;
      LastError = v29;
      KerbTracerT::Log(1, "KerbHttpSendRequest", v31, v30, pwszReferrer);
LABEL_61:
      if ( !v24 )
        goto LABEL_70;
LABEL_62:
      KerbFree(v24);
      goto LABEL_70;
    }
    if ( !dwNumberOfBytesToRead )
    {
      v32 = v47;
      *((_QWORD *)v47 + 1) = v24;
      *(_DWORD *)v32 = v25;
      goto LABEL_70;
    }
    v26 = dwNumberOfBytesToRead + v25;
    if ( dwNumberOfBytesToRead + v25 < v25 )
    {
      LastError = -1073741675;
      goto LABEL_61;
    }
    v27 = (char *)MIDL_user_allocate(v26);
    if ( !v24 )
      break;
    v28 = v27;
    if ( !v27 )
    {
      LastError = 8;
      KerbTracerT::Log(1, "KerbHttpSendRequest", 4120, "failed to allocate memory: %#x", 8);
      goto LABEL_62;
    }
    memcpy_0(v27, v24, v25);
    KerbFree(v24);
    v24 = v28;
LABEL_55:
    if ( !WinHttpReadData(v9, &v24[v25], dwNumberOfBytesToRead, &dwNumberOfBytesRead) )
    {
      v29 = GetLastError();
      v30 = "WinHttpReadData failed: %#x";
      v31 = 4156;
      goto LABEL_60;
    }
    if ( dwNumberOfBytesRead != dwNumberOfBytesToRead )
    {
      LastError = 24;
      LODWORD(pwszReferrer) = 24;
      KerbTracerT::Log(
        1,
        "KerbHttpSendRequest",
        4163,
        "WinHttpReadData returns unexpected amount of data: %#x",
        pwszReferrer);
      goto LABEL_61;
    }
    v25 = v26;
    LastError = 0;
  }
  v24 = v27;
  if ( v27 )
    goto LABEL_55;
  v22 = 8;
  v15 = "failed to allocate memory: %#x";
  v16 = 4141;
LABEL_42:
  LODWORD(pwszReferrer) = v22;
  LastError = v22;
LABEL_15:
  KerbTracerT::Log(1, "KerbHttpSendRequest", v16, v15, pwszReferrer);
LABEL_70:
  WinHttpCloseHandle(v9);
  return LastError;
}

```

## disassembly

```asm
0x180098a5c  mov     [rsp-8+arg_10], r8
0x180098a61  mov     [rsp-8+arg_8], rdx
0x180098a66  push    rbp
0x180098a67  push    rbx
0x180098a68  push    rsi
0x180098a69  push    rdi
0x180098a6a  push    r12
0x180098a6c  push    r13
0x180098a6e  push    r14
0x180098a70  push    r15
0x180098a72  lea     rbp, [rsp-1Fh]
0x180098a77  sub     rsp, 98h
0x180098a7e  xor     eax, eax
0x180098a80  mov     [rsp+0D0h+dwFlags], 800100h; dwFlags
0x180098a88  xorps   xmm0, xmm0
0x180098a8b  mov     [rsp+0D0h+ppwszAcceptTypes], rax; ppwszAcceptTypes
0x180098a90  movups  xmmword ptr [r8], xmm0
0x180098a94  cmp     [rcx+58h], rax
0x180098a98  lea     r8, aKdcproxy; "KdcProxy"
0x180098a9f  mov     rsi, rdx
0x180098aa2  mov     [rbp+57h+dwNumberOfBytesToRead], eax
0x180098aa5  cmovnz  r8, [rcx+58h]; pwszObjectName
0x180098aaa  lea     edi, [rax+1]
0x180098aad  mov     r14, rcx
0x180098ab0  mov     [rbp+57h+dwNumberOfBytesRead], eax
0x180098ab3  mov     rcx, [rcx+0E0h]; hConnect
0x180098aba  lea     rdx, pwszVerb; "POST"
0x180098ac1  xor     r9d, r9d; pwszVersion
0x180098ac4  mov     [rbp+57h+var_68], eax
0x180098ac7  mov     [rbp+57h+var_50], edi
0x180098aca  mov     r13d, eax
0x180098acd  mov     [rbp+57h+var_4C], 2
0x180098ad4  mov     [rbp+57h+Buffer], eax
0x180098ad7  mov     [rbp+57h+dwSupportedSchemes], eax
0x180098ada  mov     [rbp+57h+dwFirstScheme], eax
0x180098add  mov     [rbp+57h+pdwAuthTarget], eax
0x180098ae0  mov     [rbp+57h+var_58], rax
0x180098ae4  mov     [rsp+0D0h+pwszReferrer], rax; pwszReferrer
0x180098ae9  call    cs:__imp_WinHttpOpenRequest
0x180098aef  mov     r15, rax
0x180098af2  test    rax, rax
0x180098af5  jnz     short loc_180098B23
0x180098af7  call    cs:__imp_GetLastError
0x180098afd  lea     r9, aWinhttpopenreq_0; "WinHttpOpenRequest failed: %#x"
0x180098b04  mov     r8d, 0F1Ch
0x180098b0a  lea     rdx, aKerbhttpsendre_3; "KerbHttpSendRequest"
0x180098b11  mov     dword ptr [rsp+0D0h+pwszReferrer], eax
0x180098b15  mov     ecx, edi
0x180098b17  mov     ebx, eax
0x180098b19  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180098b1e  jmp     loc_1800990D5
0x180098b23  xor     ebx, ebx
0x180098b25  mov     r12d, edi
0x180098b28  mov     r9d, 4; dwBufferLength
0x180098b2e  lea     rdi, [rbp+57h+var_50]
0x180098b32  lea     rdi, [rdi+rbx*4]
0x180098b36  mov     rcx, r15; hInternet
0x180098b39  mov     r8, rdi; lpBuffer
0x180098b3c  lea     edx, [r9+3Bh]; dwOption
0x180098b40  call    cs:__imp_WinHttpSetOption
0x180098b46  test    eax, eax
0x180098b48  jz      loc_18009909E
0x180098b4e  add     ebx, r12d
0x180098b51  cmp     ebx, 2
0x180098b54  jb      short loc_180098B28
0x180098b56  mov     ebx, 4
0x180098b5b  mov     [rbp+57h+Buffer], r13d
0x180098b5f  mov     r9d, ebx; dwBufferLength
0x180098b62  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x180098b66  mov     rcx, r15; hInternet
0x180098b69  lea     edx, [rbx+54h]; dwOption
0x180098b6c  call    cs:__imp_WinHttpSetOption
0x180098b72  test    eax, eax
0x180098b74  jnz     short loc_180098B90
0x180098b76  call    cs:__imp_GetLastError
0x180098b7c  mov     ebx, eax
0x180098b7e  mov     dword ptr [rsp+0D0h+ppwszAcceptTypes], eax
0x180098b82  mov     eax, [rbp+57h+Buffer]
0x180098b85  mov     r8d, 0F3Dh
0x180098b8b  jmp     loc_1800990B2
0x180098b90  cmp     cs:?KerbGlobalNoRevocationCheck@@3KA, r13d; ulong KerbGlobalNoRevocationCheck
0x180098b97  jnz     short loc_180098BD0
0x180098b99  mov     r9d, ebx; dwBufferLength
0x180098b9c  mov     [rbp+57h+Buffer], r12d
0x180098ba0  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x180098ba4  mov     edx, 4Fh ; 'O'; dwOption
0x180098ba9  mov     rcx, r15; hInternet
0x180098bac  call    cs:__imp_WinHttpSetOption
0x180098bb2  test    eax, eax
0x180098bb4  jnz     short loc_180098BD0
0x180098bb6  call    cs:__imp_GetLastError
0x180098bbc  mov     ebx, eax
0x180098bbe  mov     dword ptr [rsp+0D0h+ppwszAcceptTypes], eax
0x180098bc2  mov     eax, [rbp+57h+Buffer]
0x180098bc5  mov     r8d, 0F4Fh
0x180098bcb  jmp     loc_1800990B2
0x180098bd0  mov     rdx, [r14+0E8h]; lpBuffer
0x180098bd7  lea     r9, [rbp+57h+var_68]; unsigned int *
0x180098bdb  mov     r8, rsi; struct _KERB_MESSAGE_BUFFER *
0x180098bde  mov     rcx, r15; void *
0x180098be1  call    ?KerbHttpSendRequestAndReceiveResponse@@YAKPEAXPEBU_CERT_CONTEXT@@PEAU_KERB_MESSAGE_BUFFER@@PEAK@Z; KerbHttpSendRequestAndReceiveResponse(void *,_CERT_CONTEXT const *,_KERB_MESSAGE_BUFFER *,ulong *)
0x180098be6  mov     ebx, eax
0x180098be8  test    eax, eax
0x180098bea  jz      short loc_180098C11
0x180098bec  mov     dword ptr [rsp+0D0h+pwszReferrer], eax
0x180098bf0  lea     r9, aKerbhttpsendre_2; "KerbHttpSendRequestAndReceiveResponse f"...
0x180098bf7  mov     r8d, 0F5Dh
0x180098bfd  lea     rdx, aKerbhttpsendre_3; "KerbHttpSendRequest"
0x180098c04  mov     ecx, r12d
0x180098c07  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180098c0c  jmp     loc_1800990CC
0x180098c11  mov     edi, [rbp+57h+var_68]
0x180098c14  lea     rsi, aKerbhttpsendre_3; "KerbHttpSendRequest"
0x180098c1b  cmp     edi, 197h
0x180098c21  jnz     loc_180098F20
0x180098c27  lea     r9, [rbp+57h+pdwAuthTarget]; pdwAuthTarget
0x180098c2b  mov     rcx, r15; hRequest
0x180098c2e  lea     r8, [rbp+57h+dwFirstScheme]; lpdwFirstScheme
0x180098c32  lea     rdx, [rbp+57h+dwSupportedSchemes]; lpdwSupportedSchemes
0x180098c36  call    cs:__imp_WinHttpQueryAuthSchemes
0x180098c3c  test    eax, eax
0x180098c3e  jnz     short loc_180098C5E
0x180098c40  call    cs:__imp_GetLastError
0x180098c46  mov     dword ptr [rsp+0D0h+pwszReferrer], eax
0x180098c4a  lea     r9, aWinhttpqueryau_0; "WinHttpQueryAuthSchemes failed: %#x"
0x180098c51  mov     ebx, eax
0x180098c53  mov     r8d, 0F6Dh
0x180098c59  mov     rdx, rsi
0x180098c5c  jmp     short loc_180098C04
0x180098c5e  mov     rdx, rsi
0x180098c61  cmp     [rbp+57h+pdwAuthTarget], r12d
0x180098c65  jz      short loc_180098C81
0x180098c67  lea     r9, aWinhttpqueryau_1; "WinHttpQueryAuthSchemes does not return"...
0x180098c6e  mov     r8d, 0F73h
0x180098c74  mov     ecx, r12d
0x180098c77  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180098c7c  jmp     loc_180098F28
0x180098c81  mov     eax, [rbp+57h+dwFirstScheme]
0x180098c84  lea     r9, aWinhttpqueryau_2; "WinHttpQueryAuthScheme returned proxy s"...
0x180098c8b  mov     dword ptr [rsp+0D0h+ppwszAcceptTypes], eax
0x180098c8f  mov     r8d, 0F77h
0x180098c95  mov     eax, [rbp+57h+dwSupportedSchemes]
0x180098c98  mov     ecx, 16h
0x180098c9d  mov     dword ptr [rsp+0D0h+pwszReferrer], eax
0x180098ca1  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180098ca6  lea     rbx, [r14+60h]
0x180098caa  cmp     [rbp+57h+dwFirstScheme], r12d
0x180098cae  jnz     short loc_180098D03
0x180098cb0  lea     r8, [rbp+57h+var_58]; struct _KERB_AUTH_PROXY_CRED **
0x180098cb4  mov     rdx, rbx; struct _KERB_AUTH_PROXY *
0x180098cb7  mov     ecx, r12d; unsigned int
0x180098cba  call    ?KerbGetAuthProxyCred@@YAJKPEAU_KERB_AUTH_PROXY@@PEAPEAU_KERB_AUTH_PROXY_CRED@@@Z; KerbGetAuthProxyCred(ulong,_KERB_AUTH_PROXY *,_KERB_AUTH_PROXY_CRED * *)
0x180098cbf  test    eax, eax
0x180098cc1  jns     short loc_180098CF6
0x180098cc3  mov     r8d, 0F87h
0x180098cc9  lea     r9, aKerbgetauthpro_0; "KerbGetAuthProxyCred failed to get BASI"...
0x180098cd0  shr     r14, 10h
0x180098cd4  mov     rdx, rsi
0x180098cd7  movzx   ecx, r14w
0x180098cdb  mov     qword ptr [rsp+0D0h+dwFlags], rcx
0x180098ce0  mov     ecx, r12d
0x180098ce3  mov     dword ptr [rsp+0D0h+ppwszAcceptTypes], eax
0x180098ce7  mov     [rsp+0D0h+pwszReferrer], rbx
0x180098cec  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180098cf1  jmp     loc_180098F28
0x180098cf6  mov     r13, [rbp+57h+var_58]
0x180098cfa  test    r13, r13
0x180098cfd  jnz     loc_180098DD4
0x180098d03  test    byte ptr [rbp+57h+dwSupportedSchemes], 8
0x180098d07  jz      short loc_180098D39
0x180098d09  lea     r8, [rbp+57h+var_58]; struct _KERB_AUTH_PROXY_CRED **
0x180098d0d  mov     rdx, rbx; struct _KERB_AUTH_PROXY *
0x180098d10  xor     ecx, ecx; unsigned int
0x180098d12  call    ?KerbGetAuthProxyCred@@YAJKPEAU_KERB_AUTH_PROXY@@PEAPEAU_KERB_AUTH_PROXY_CRED@@@Z; KerbGetAuthProxyCred(ulong,_KERB_AUTH_PROXY *,_KERB_AUTH_PROXY_CRED * *)
0x180098d17  test    eax, eax
0x180098d19  jns     short loc_180098D2A
0x180098d1b  lea     r9, aKerbgetauthpro_2; "KerbGetAuthProxyCred failed to get DIGE"...
0x180098d22  mov     r8d, 0F9Dh
0x180098d28  jmp     short loc_180098CD0
0x180098d2a  mov     r13, [rbp+57h+var_58]
0x180098d2e  test    r13, r13
0x180098d31  jz      short loc_180098D46
0x180098d33  mov     r12d, 8
0x180098d39  test    r13, r13
0x180098d3c  jnz     loc_180098DD4
0x180098d42  lea     r12d, [r13+1]
0x180098d46  cmp     [rbp+57h+dwFirstScheme], r12d
0x180098d4a  jz      short loc_180098D79
0x180098d4c  test    byte ptr [rbp+57h+dwSupportedSchemes], r12b
0x180098d50  jz      short loc_180098D79
0x180098d52  lea     r8, [rbp+57h+var_58]; struct _KERB_AUTH_PROXY_CRED **
0x180098d56  mov     rdx, rbx; struct _KERB_AUTH_PROXY *
0x180098d59  mov     ecx, r12d; unsigned int
0x180098d5c  call    ?KerbGetAuthProxyCred@@YAJKPEAU_KERB_AUTH_PROXY@@PEAPEAU_KERB_AUTH_PROXY_CRED@@@Z; KerbGetAuthProxyCred(ulong,_KERB_AUTH_PROXY *,_KERB_AUTH_PROXY_CRED * *)
0x180098d61  test    eax, eax
0x180098d63  jns     short loc_180098D70
0x180098d65  mov     r8d, 0FB1h
0x180098d6b  jmp     loc_180098CC9
0x180098d70  mov     r13, [rbp+57h+var_58]
0x180098d74  test    r13, r13
0x180098d77  jnz     short loc_180098DD4
0x180098d79  movzx   ecx, byte ptr [r14+88h]
0x180098d81  lea     r9, aKerbhttpsendre_1; "KerbHttpSendRequest cannot find a suita"...
0x180098d88  mov     r8d, [rbp+57h+dwSupportedSchemes]
0x180098d8c  mov     rax, r14
0x180098d8f  mov     dword ptr [rsp+0D0h+var_90], ecx
0x180098d93  mov     [rsp+0D0h+var_98], ecx
0x180098d97  mov     ecx, r12d
0x180098d9a  shr     rax, 10h
0x180098d9e  movzx   edx, ax
0x180098da1  mov     eax, [rbp+57h+dwFirstScheme]
0x180098da4  mov     [rsp+0D0h+dwFlags], eax
0x180098da8  mov     dword ptr [rsp+0D0h+ppwszAcceptTypes], r8d
0x180098dad  mov     r8d, 0FBFh
0x180098db3  mov     [rsp+0D0h+pwszReferrer], rdx
0x180098db8  mov     rdx, rsi
0x180098dbb  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180098dc0  mov     r8d, [rbp+57h+dwFirstScheme]; unsigned int
0x180098dc4  mov     rcx, r14; struct _KDC_PROXY_CACHE_ENTRY *
0x180098dc7  mov     edx, [rbp+57h+dwSupportedSchemes]; unsigned int
0x180098dca  call    ?EventWriteNoAuthProxyCredHelper@@YAXPEAU_KDC_PROXY_CACHE_ENTRY@@KK@Z; EventWriteNoAuthProxyCredHelper(_KDC_PROXY_CACHE_ENTRY *,ulong,ulong)
0x180098dcf  jmp     loc_180098F28
0x180098dd4  lea     rcx, [rbx+58h]
0x180098dd8  mov     rax, r14
0x180098ddb  shr     rax, 10h
0x180098ddf  lea     rdx, [rbx+30h]
0x180098de3  movzx   r8d, ax
0x180098de7  lea     r9, [rbx+10h]
0x180098deb  mov     eax, [r14+0B4h]
0x180098df2  mov     [rsp+0D0h+var_78], eax
0x180098df6  mov     eax, [r14+8Ch]
0x180098dfd  mov     [rsp+0D0h+var_80], rcx
0x180098e02  mov     [rsp+0D0h+var_88], eax
0x180098e06  mov     eax, [r14+80h]
0x180098e0d  mov     [rsp+0D0h+var_90], rdx
0x180098e12  mov     rdx, rsi
0x180098e15  mov     [rsp+0D0h+var_98], eax
0x180098e19  mov     qword ptr [rsp+0D0h+dwFlags], r9
0x180098e1e  lea     r9, aAuthProxySetti; "auth proxy settings: CacheEntry %p, Pro"...
0x180098e25  mov     [rsp+0D0h+ppwszAcceptTypes], rbx
0x180098e2a  mov     ebx, 16h
0x180098e2f  mov     [rsp+0D0h+pwszReferrer], r8
0x180098e34  mov     ecx, ebx
0x180098e36  mov     r8d, 0FC8h
0x180098e3c  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180098e41  lea     rax, [r13+8]
0x180098e45  mov     r8d, 0FCAh
0x180098e4b  mov     [rsp+0D0h+ppwszAcceptTypes], rax
0x180098e50  lea     r9, aSetAuthProxyCr; "set auth proxy credential (%#x %wZ) and"...
0x180098e57  mov     rdx, rsi
0x180098e5a  mov     dword ptr [rsp+0D0h+pwszReferrer], r12d
0x180098e5f  mov     ecx, ebx
0x180098e61  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180098e66  lea     rcx, [r13+18h]; struct _UNICODE_STRING *
0x180098e6a  call    ?KerbRevealPassword@@YAXPEAU_UNICODE_STRING@@@Z; KerbRevealPassword(_UNICODE_STRING *)
0x180098e6f  mov     rax, [r13+20h]
0x180098e73  lea     edx, [rbx-15h]; AuthTargets
0x180098e76  mov     r9, [r13+10h]; pwszUserName
0x180098e7a  mov     r8d, r12d; AuthScheme
0x180098e7d  mov     [rsp+0D0h+ppwszAcceptTypes], 0; pAuthParams
0x180098e86  mov     rcx, r15; hRequest
0x180098e89  mov     [rsp+0D0h+pwszReferrer], rax; pwszPassword
0x180098e8e  call    cs:__imp_WinHttpSetCredentials
0x180098e94  lea     rcx, [r13+18h]; struct _UNICODE_STRING *
0x180098e98  mov     ebx, eax
0x180098e9a  call    ?KerbHidePassword@@YAXPEAU_UNICODE_STRING@@@Z; KerbHidePassword(_UNICODE_STRING *)
0x180098e9f  test    ebx, ebx
0x180098ea1  jnz     short loc_180098EC9
0x180098ea3  call    cs:__imp_GetLastError
0x180098ea9  lea     r9, aWinhttpsetcred_0; "WinHttpSetCredentials failed: %#x"
0x180098eb0  mov     r8d, 0FDCh
0x180098eb6  mov     dword ptr [rsp+0D0h+pwszReferrer], eax
0x180098eba  mov     ebx, eax
0x180098ebc  mov     rdx, rsi
0x180098ebf  mov     ecx, 1
0x180098ec4  jmp     loc_180098C07
0x180098ec9  mov     r8, [rbp+57h+arg_8]; struct _KERB_MESSAGE_BUFFER *
0x180098ecd  lea     r9, [rbp+57h+var_68]; unsigned int *
0x180098ed1  mov     rdx, [r14+0E8h]; lpBuffer
0x180098ed8  mov     rcx, r15; void *
0x180098edb  call    ?KerbHttpSendRequestAndReceiveResponse@@YAKPEAXPEBU_CERT_CONTEXT@@PEAU_KERB_MESSAGE_BUFFER@@PEAK@Z; KerbHttpSendRequestAndReceiveResponse(void *,_CERT_CONTEXT const *,_KERB_MESSAGE_BUFFER *,ulong *)
0x180098ee0  mov     ebx, eax
0x180098ee2  test    eax, eax
0x180098ee4  jz      short loc_180098F17
0x180098ee6  mov     [rsp+0D0h+dwFlags], eax
0x180098eea  lea     r9, aKerbhttpsendre_0; "KerbHttpSendRequestAndReceiveResponse f"...
0x180098ef1  lea     rax, [r13+8]
0x180098ef5  mov     r8d, 0FE9h
0x180098efb  mov     [rsp+0D0h+ppwszAcceptTypes], rax
0x180098f00  mov     rdx, rsi
0x180098f03  mov     ecx, 1
0x180098f08  mov     dword ptr [rsp+0D0h+pwszReferrer], r12d
0x180098f0d  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180098f12  jmp     loc_1800990CC
0x180098f17  mov     edi, [rbp+57h+var_68]
0x180098f1a  mov     r12d, 1
0x180098f20  cmp     edi, 0C8h
0x180098f26  jz      short loc_180098F40
0x180098f28  mov     ebx, edi
0x180098f2a  lea     r9, aWinhttpqueryhe_1; "WinHttpQueryHeaders returns http error:"...
  ... truncated ...
```
