# DohContextPrepare

- ea: `0x180044884`
- end: `0x180044ca8`
- name: `DohContextPrepare`
- size: `1060`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800464f8`

## callees

- `0x18002b050`
- `0x180043180`
- `0x180044884`
- `0x180044cb0`
- `0x180045078`
- `0x180045474`
- `0x1800455c8`
- `0x18004573c`
- `0x180045790`
- `0x180083954`
- `0x18008b5f0`
- `0x1800dc9e0`
- `0x1800ddfa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044b1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044b9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044c1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044b1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044b9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044c1f`
- `WINHTTP!WinHttpCloseHandle` at `0x180044b2e`
- `WINHTTP!WinHttpCloseHandle` at `0x180044c44`
- `WINHTTP!WinHttpCloseHandle` at `0x180044b2e`
- `WINHTTP!WinHttpCloseHandle` at `0x180044c44`
- `WINHTTP!WinHttpOpenRequest` at `0x1800449ca`
- `WINHTTP!WinHttpOpenRequest` at `0x1800449ca`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x1800449f6`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x1800449f6`
- `WINHTTP!WinHttpConnect` at `0x18004498b`
- `WINHTTP!WinHttpConnect` at `0x18004498b`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180044ace`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180044ace`
- `WINHTTP!WinHttpSetOption` at `0x180044a1e`
- `WINHTTP!WinHttpSetOption` at `0x180044a41`
- `WINHTTP!WinHttpSetOption` at `0x180044a62`
- `WINHTTP!WinHttpSetOption` at `0x180044aad`
- `WINHTTP!WinHttpSetOption` at `0x180044a1e`
- `WINHTTP!WinHttpSetOption` at `0x180044a41`
- `WINHTTP!WinHttpSetOption` at `0x180044a62`
- `WINHTTP!WinHttpSetOption` at `0x180044aad`

## pseudocode

```c
__int64 __fastcall DohContextPrepare(__int64 a1)
{
  DWORD v2; // eax
  DWORD LastError; // ebx
  INTERNET_PORT v4; // r8
  void *v5; // r14
  void *v6; // rax
  void *v7; // rsi
  DWORD v8; // eax
  __int64 v10; // rdx
  __int64 v11; // rdx
  INTERNET_PORT v12; // [rsp+40h] [rbp-19h] BYREF
  LPCWSTR pswzServerName; // [rsp+48h] [rbp-11h] BYREF
  LPCWSTR pwszObjectName; // [rsp+50h] [rbp-9h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-1h] BYREF
  int Buffer; // [rsp+60h] [rbp+7h] BYREF
  int v17; // [rsp+64h] [rbp+Bh] BYREF
  int v18; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v19; // [rsp+70h] [rbp+17h] BYREF
  LPCWSTR ppwszAcceptTypes[2]; // [rsp+78h] [rbp+1Fh] BYREF

  pwszObjectName = 0;
  ppwszAcceptTypes[0] = L"application/dns-message";
  ppwszAcceptTypes[1] = 0;
  pswzServerName = 0;
  Buffer = 1;
  v18 = 1;
  v17 = 1;
  v19 = 0;
  lpMem = 0;
  v12 = 0;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_q(1035, 39, WPP_2c80e66c209e3b063fd9ee6d3755b8b2_Traceguids, a1);
  if ( !a1 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
    LastError = 87;
    goto LABEL_21;
  }
  v2 = Send_PrepareWinhttpSession(
         *(_QWORD *)a1,
         1,
         *(_QWORD *)(a1 + 8),
         *(_QWORD *)(a1 + 16),
         *(_QWORD *)(a1 + 24),
         0,
         *(_DWORD *)(a1 + 32),
         &lpMem);
  LastError = v2;
  if ( v2 )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
      goto LABEL_21;
    v11 = 40;
    goto LABEL_37;
  }
  v2 = DohCreateWinhttpStaticResolverCacheEntry(
         lpMem,
         *(_QWORD *)(a1 + 8),
         *(_QWORD *)(a1 + 24),
         &pswzServerName,
         &pwszObjectName,
         &v12);
  LastError = v2;
  if ( v2 )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
      goto LABEL_21;
    v11 = 41;
LABEL_37:
    WPP_SF_d(1035, v11, WPP_2c80e66c209e3b063fd9ee6d3755b8b2_Traceguids, v2);
    goto LABEL_21;
  }
  v4 = v12;
  if ( !v12 )
    v4 = 443;
  v5 = WinHttpConnect(*((HINTERNET *)lpMem + 1), pswzServerName, v4, 0);
  if ( !v5 )
  {
    LastError = GetLastError();
    goto LABEL_21;
  }
  v6 = WinHttpOpenRequest(v5, L"POST", pwszObjectName, 0, 0, ppwszAcceptTypes, 0x800000u);
  v7 = v6;
  if ( !v6
    || !WinHttpAddRequestHeaders(v6, L"Content-Type: application/dns-message", 0xFFFFFFFF, 0x20000000u)
    || !WinHttpSetOption(v7, 0x85u, &Buffer, 4u)
    || !WinHttpSetOption(v7, 0x91u, &v17, 4u)
    || !WinHttpSetOption(v7, 0x3Fu, &v18, 4u) )
  {
    goto LABEL_18;
  }
  DdrSkipCertVerification(*(PCWSTR *)(a1 + 8), *(PCWSTR *)(a1 + 16));
  v8 = PrepareWinhttpRequestCommon(v7);
  LastError = v8;
  if ( !v8 )
  {
    v19 = a1;
    if ( WinHttpSetOption(v7, 0x2Du, &v19, 8u) )
    {
      if ( WinHttpSetStatusCallback(v7, DohWinhttpStatusCallback, 0xFFFFFFFF, 0) != (WINHTTP_STATUS_CALLBACK)-1LL )
      {
        *(_QWORD *)(a1 + 128) = lpMem;
        LastError = 0;
        lpMem = 0;
        *(_QWORD *)(a1 + 152) = v5;
        DohContextAddRef(a1);
        InitializeDnsWinhttpHandle(v7, a1 + 136);
        *(_DWORD *)(a1 + 56) = 1;
        goto LABEL_21;
      }
      v8 = GetLastError();
      LastError = v8;
      if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
        goto LABEL_19;
      v10 = 43;
      goto LABEL_30;
    }
LABEL_18:
    LastError = GetLastError();
    goto LABEL_19;
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
    goto LABEL_19;
  v10 = 42;
LABEL_30:
  WPP_SF_d(1035, v10, WPP_2c80e66c209e3b063fd9ee6d3755b8b2_Traceguids, v8);
LABEL_19:
  WinHttpCloseHandle(v5);
  if ( v7 )
    WinHttpCloseHandle(v7);
LABEL_21:
  if ( lpMem )
  {
    DeRefDnsWinhttpSession(lpMem);
    lpMem = 0;
  }
  DnsApiFree((LPVOID)pswzServerName);
  DnsApiFree((LPVOID)pwszObjectName);
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 44, WPP_2c80e66c209e3b063fd9ee6d3755b8b2_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180044884  mov     [rsp-8+arg_8], rbx
0x180044889  mov     [rsp-8+arg_10], rsi
0x18004488e  push    rbp
0x18004488f  push    rdi
0x180044890  push    r13
0x180044892  push    r14
0x180044894  push    r15
0x180044896  lea     rbp, [rsp-37h]
0x18004489b  sub     rsp, 90h
0x1800448a2  mov     rax, cs:__security_cookie
0x1800448a9  xor     rax, rsp
0x1800448ac  mov     [rbp+57h+var_28], rax
0x1800448b0  xor     r15d, r15d
0x1800448b3  lea     rax, aApplicationDns; "application/dns-message"
0x1800448ba  mov     rdi, rcx
0x1800448bd  mov     [rbp+57h+pwszObjectName], r15
0x1800448c1  mov     [rbp+57h+var_38], rax
0x1800448c5  mov     [rbp+57h+var_30], r15
0x1800448c9  lea     edx, [r15+1]
0x1800448cd  mov     [rbp+57h+pswzServerName], r15
0x1800448d1  mov     [rbp+57h+Buffer], edx
0x1800448d4  mov     [rbp+57h+var_48], edx
0x1800448d7  mov     [rbp+57h+var_4C], edx
0x1800448da  mov     [rbp+57h+var_40], r15
0x1800448de  mov     [rbp+57h+lpMem], r15
0x1800448e2  mov     [rbp+57h+var_70], r15w
0x1800448e7  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800448ee  mov     r13d, 40Bh
0x1800448f4  jnz     loc_180044BF3
0x1800448fa  test    rdi, rdi
0x1800448fd  jz      loc_180044BAA
0x180044903  mov     r9, [rdi+10h]
0x180044907  lea     rax, [rbp+57h+lpMem]
0x18004490b  mov     r8, [rdi+8]
0x18004490f  mov     rcx, [rdi]
0x180044912  mov     [rsp+0B0h+var_78], rax
0x180044917  mov     eax, [rdi+20h]
0x18004491a  mov     [rsp+0B0h+dwFlags], eax
0x18004491e  mov     rax, [rdi+18h]
0x180044922  mov     word ptr [rsp+0B0h+ppwszAcceptTypes], r15w
0x180044928  mov     [rsp+0B0h+pwszReferrer], rax
0x18004492d  call    Send_PrepareWinhttpSession
0x180044932  mov     ebx, eax
0x180044934  test    eax, eax
0x180044936  jnz     loc_180044C55
0x18004493c  mov     r8, [rdi+18h]
0x180044940  lea     rax, [rbp+57h+var_70]
0x180044944  mov     rdx, [rdi+8]
0x180044948  lea     r9, [rbp+57h+pswzServerName]
0x18004494c  mov     rcx, [rbp+57h+lpMem]
0x180044950  mov     [rsp+0B0h+ppwszAcceptTypes], rax
0x180044955  lea     rax, [rbp+57h+pwszObjectName]
0x180044959  mov     [rsp+0B0h+pwszReferrer], rax
0x18004495e  call    DohCreateWinhttpStaticResolverCacheEntry
0x180044963  mov     ebx, eax
0x180044965  test    eax, eax
0x180044967  jnz     loc_180044BDF
0x18004496d  movzx   r8d, [rbp+57h+var_70]; nServerPort
0x180044972  test    r8w, r8w
0x180044976  jz      loc_180044C14
0x18004497c  mov     rcx, [rbp+57h+lpMem]
0x180044980  xor     r9d, r9d; dwReserved
0x180044983  mov     rdx, [rbp+57h+pswzServerName]; pswzServerName
0x180044987  mov     rcx, [rcx+8]; hSession
0x18004498b  call    cs:__imp_WinHttpConnect
0x180044992  nop     dword ptr [rax+rax+00h]
0x180044997  mov     r14, rax
0x18004499a  test    rax, rax
0x18004499d  jz      loc_180044B9A
0x1800449a3  mov     r8, [rbp+57h+pwszObjectName]; pwszObjectName
0x1800449a7  lea     rax, [rbp+57h+var_38]
0x1800449ab  mov     [rsp+0B0h+dwFlags], 800000h; dwFlags
0x1800449b3  lea     rdx, pwszVerb; "POST"
0x1800449ba  mov     [rsp+0B0h+ppwszAcceptTypes], rax; ppwszAcceptTypes
0x1800449bf  xor     r9d, r9d; pwszVersion
0x1800449c2  mov     rcx, r14; hConnect
0x1800449c5  mov     [rsp+0B0h+pwszReferrer], r15; pwszReferrer
0x1800449ca  call    cs:__imp_WinHttpOpenRequest
0x1800449d1  nop     dword ptr [rax+rax+00h]
0x1800449d6  mov     rsi, rax
0x1800449d9  test    rax, rax
0x1800449dc  jz      loc_180044B1D
0x1800449e2  mov     r9d, 20000000h; dwModifiers
0x1800449e8  lea     rdx, szHeaders; "Content-Type: application/dns-message"
0x1800449ef  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x1800449f3  mov     rcx, rax; hRequest
0x1800449f6  call    cs:__imp_WinHttpAddRequestHeaders
0x1800449fd  nop     dword ptr [rax+rax+00h]
0x180044a02  test    eax, eax
0x180044a04  jz      loc_180044B1D
0x180044a0a  mov     ebx, 4
0x180044a0f  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x180044a13  mov     r9d, ebx; dwBufferLength
0x180044a16  mov     edx, 85h; dwOption
0x180044a1b  mov     rcx, rsi; hInternet
0x180044a1e  call    cs:__imp_WinHttpSetOption
0x180044a25  nop     dword ptr [rax+rax+00h]
0x180044a2a  test    eax, eax
0x180044a2c  jz      loc_180044B1D
0x180044a32  mov     r9d, ebx; dwBufferLength
0x180044a35  lea     r8, [rbp+57h+var_4C]; lpBuffer
0x180044a39  mov     edx, 91h; dwOption
0x180044a3e  mov     rcx, rsi; hInternet
0x180044a41  call    cs:__imp_WinHttpSetOption
0x180044a48  nop     dword ptr [rax+rax+00h]
0x180044a4d  test    eax, eax
0x180044a4f  jz      loc_180044B1D
0x180044a55  mov     r9d, ebx; dwBufferLength
0x180044a58  lea     r8, [rbp+57h+var_48]; lpBuffer
0x180044a5c  lea     edx, [rbx+3Bh]; dwOption
0x180044a5f  mov     rcx, rsi; hInternet
0x180044a62  call    cs:__imp_WinHttpSetOption
0x180044a69  nop     dword ptr [rax+rax+00h]
0x180044a6e  test    eax, eax
0x180044a70  jz      loc_180044B1D
0x180044a76  mov     rdx, [rdi+10h]; PCWSTR
0x180044a7a  mov     rcx, [rdi+8]; AddressString
0x180044a7e  call    DdrSkipCertVerification
0x180044a83  mov     r8, [rdi+50h]
0x180044a87  mov     edx, eax
0x180044a89  mov     rcx, rsi; hInternet
0x180044a8c  call    PrepareWinhttpRequestCommon
0x180044a91  mov     ebx, eax
0x180044a93  test    eax, eax
0x180044a95  jnz     loc_180044BB6
0x180044a9b  lea     r9d, [rax+8]; dwBufferLength
0x180044a9f  mov     [rbp+57h+var_40], rdi
0x180044aa3  lea     r8, [rbp+57h+var_40]; lpBuffer
0x180044aa7  mov     rcx, rsi; hInternet
0x180044aaa  lea     edx, [rax+2Dh]; dwOption
0x180044aad  call    cs:__imp_WinHttpSetOption
0x180044ab4  nop     dword ptr [rax+rax+00h]
0x180044ab9  test    eax, eax
0x180044abb  jz      short loc_180044B1D
0x180044abd  xor     r9d, r9d; dwReserved
0x180044ac0  lea     rdx, DohWinhttpStatusCallback; lpfnInternetCallback
0x180044ac7  or      r8d, 0FFFFFFFFh; dwNotificationFlags
0x180044acb  mov     rcx, rsi; hInternet
0x180044ace  call    cs:__imp_WinHttpSetStatusCallback
0x180044ad5  nop     dword ptr [rax+rax+00h]
0x180044ada  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180044ade  jz      loc_180044C1F
0x180044ae4  mov     rax, [rbp+57h+lpMem]
0x180044ae8  mov     rcx, rdi
0x180044aeb  mov     [rdi+80h], rax
0x180044af2  mov     ebx, r15d
0x180044af5  mov     [rbp+57h+lpMem], r15
0x180044af9  mov     [rdi+98h], r14
0x180044b00  call    DohContextAddRef
0x180044b05  lea     rdx, [rdi+88h]
0x180044b0c  mov     rcx, rsi
0x180044b0f  call    InitializeDnsWinhttpHandle
0x180044b14  mov     dword ptr [rdi+38h], 1
0x180044b1b  jmp     short loc_180044B43
0x180044b1d  call    cs:__imp_GetLastError
0x180044b24  nop     dword ptr [rax+rax+00h]
0x180044b29  mov     ebx, eax
0x180044b2b  mov     rcx, r14; hInternet
0x180044b2e  call    cs:__imp_WinHttpCloseHandle
0x180044b35  nop     dword ptr [rax+rax+00h]
0x180044b3a  test    rsi, rsi
0x180044b3d  jnz     loc_180044C41
0x180044b43  mov     rcx, [rbp+57h+lpMem]; lpMem
0x180044b47  test    rcx, rcx
0x180044b4a  jnz     loc_180044C7E
0x180044b50  mov     rcx, [rbp+57h+pswzServerName]; lpMem
0x180044b54  call    DnsApiFree
0x180044b59  mov     rcx, [rbp+57h+pwszObjectName]; lpMem
0x180044b5d  call    DnsApiFree
0x180044b62  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180044b69  jnz     loc_180044C8C
0x180044b6f  mov     eax, ebx
0x180044b71  mov     rcx, [rbp+57h+var_28]
0x180044b75  xor     rcx, rsp; StackCookie
0x180044b78  call    __security_check_cookie
0x180044b7d  lea     r11, [rsp+0B0h+var_20]
0x180044b85  mov     rbx, [r11+38h]
0x180044b89  mov     rsi, [r11+40h]
0x180044b8d  mov     rsp, r11
0x180044b90  pop     r15
0x180044b92  pop     r14
0x180044b94  pop     r13
0x180044b96  pop     rdi
0x180044b97  pop     rbp
0x180044b98  retn
0x180044b9a  call    cs:__imp_GetLastError
0x180044ba1  nop     dword ptr [rax+rax+00h]
0x180044ba6  mov     ebx, eax
0x180044ba8  jmp     short loc_180044B43
0x180044baa  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180044baf  mov     ebx, 57h ; 'W'
0x180044bb4  jmp     short loc_180044B43
0x180044bb6  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180044bbd  jz      loc_180044B2B
0x180044bc3  mov     edx, 2Ah ; '*'
0x180044bc8  mov     r9d, eax
0x180044bcb  lea     r8, WPP_2c80e66c209e3b063fd9ee6d3755b8b2_Traceguids
0x180044bd2  mov     ecx, r13d
0x180044bd5  call    WPP_SF_d
0x180044bda  jmp     loc_180044B2B
0x180044bdf  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180044be6  jz      loc_180044B43
0x180044bec  mov     edx, 29h ; ')'
0x180044bf1  jmp     short loc_180044C67
0x180044bf3  mov     edx, 27h ; '''
0x180044bf8  lea     r8, WPP_2c80e66c209e3b063fd9ee6d3755b8b2_Traceguids
0x180044bff  mov     ecx, r13d
0x180044c02  mov     r9, rdi
0x180044c05  call    WPP_SF_q
0x180044c0a  mov     edx, 1
0x180044c0f  jmp     loc_1800448FA
0x180044c14  mov     r8d, 1BBh
0x180044c1a  jmp     loc_18004497C
0x180044c1f  call    cs:__imp_GetLastError
0x180044c26  nop     dword ptr [rax+rax+00h]
0x180044c2b  mov     ebx, eax
0x180044c2d  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180044c34  jz      loc_180044B2B
0x180044c3a  mov     edx, 2Bh ; '+'
0x180044c3f  jmp     short loc_180044BC8
0x180044c41  mov     rcx, rsi; hInternet
0x180044c44  call    cs:__imp_WinHttpCloseHandle
0x180044c4b  nop     dword ptr [rax+rax+00h]
0x180044c50  jmp     loc_180044B43
0x180044c55  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180044c5c  jz      loc_180044B43
0x180044c62  mov     edx, 28h ; '('
0x180044c67  mov     r9d, eax
0x180044c6a  lea     r8, WPP_2c80e66c209e3b063fd9ee6d3755b8b2_Traceguids
0x180044c71  mov     ecx, r13d
0x180044c74  call    WPP_SF_d
0x180044c79  jmp     loc_180044B43
0x180044c7e  call    DeRefDnsWinhttpSession
0x180044c83  mov     [rbp+57h+lpMem], r15
0x180044c87  jmp     loc_180044B50
0x180044c8c  mov     edx, 2Ch ; ','
0x180044c91  lea     r8, WPP_2c80e66c209e3b063fd9ee6d3755b8b2_Traceguids
0x180044c98  mov     ecx, r13d
0x180044c9b  mov     r9d, ebx
0x180044c9e  call    WPP_SF_d
0x180044ca3  jmp     loc_180044B6F
```
