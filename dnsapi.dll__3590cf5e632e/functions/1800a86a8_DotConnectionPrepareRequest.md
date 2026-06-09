# DotConnectionPrepareRequest

- ea: `0x1800a86a8`
- end: `0x1800a89d9`
- name: `DotConnectionPrepareRequest`
- size: `817`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180082cf8`

## callees

- `0x180043180`
- `0x180045078`
- `0x180045474`
- `0x1800455c8`
- `0x180045790`
- `0x180083df8`
- `0x18008b5f0`
- `0x1800a097c`
- `0x1800a86a8`
- `0x1800dbfe0`
- `0x1800dc9e0`
- `0x1800ddfa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a87e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a882c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a88d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a87e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a882c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a88d6`
- `WINHTTP!WinHttpCloseHandle` at `0x1800a894a`
- `WINHTTP!WinHttpCloseHandle` at `0x1800a895e`
- `WINHTTP!WinHttpCloseHandle` at `0x1800a894a`
- `WINHTTP!WinHttpCloseHandle` at `0x1800a895e`
- `WINHTTP!WinHttpOpenRequest` at `0x1800a8818`
- `WINHTTP!WinHttpOpenRequest` at `0x1800a8818`
- `WINHTTP!WinHttpConnect` at `0x1800a87cc`
- `WINHTTP!WinHttpConnect` at `0x1800a87cc`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800a88c4`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800a88c4`
- `WINHTTP!WinHttpSetOption` at `0x1800a884d`
- `WINHTTP!WinHttpSetOption` at `0x1800a889f`
- `WINHTTP!WinHttpSetOption` at `0x1800a884d`
- `WINHTTP!WinHttpSetOption` at `0x1800a889f`

## pseudocode

```c
__int64 __fastcall DotConnectionPrepareRequest(__int64 a1)
{
  DWORD WinhttpStaticResolverCacheEntry; // eax
  DWORD LastError; // ebx
  const WCHAR *v4; // rbx
  __int64 v5; // rdx
  void *v6; // rax
  void *v7; // rbp
  void *v8; // rax
  void *v9; // rsi
  DWORD v10; // eax
  __int64 v11; // rdx
  LPVOID lpMem; // [rsp+40h] [rbp-58h] BYREF
  __int64 Buffer; // [rsp+48h] [rbp-50h] BYREF

  Buffer = 0;
  lpMem = 0;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_q(1035, 63, WPP_e56dd19b1cdc30a42d7776c3f5a09aa5_Traceguids, a1);
  WinhttpStaticResolverCacheEntry = Send_PrepareWinhttpSession(
                                      0,
                                      2,
                                      *(_QWORD *)(a1 + 136),
                                      *(_QWORD *)(a1 + 128),
                                      *(_QWORD *)(a1 + 152),
                                      *(_WORD *)(a1 + 202),
                                      *(_DWORD *)(a1 + 100),
                                      &lpMem);
  LastError = WinhttpStaticResolverCacheEntry;
  if ( WinhttpStaticResolverCacheEntry )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
      goto LABEL_31;
    v5 = 64;
    goto LABEL_30;
  }
  if ( *(_QWORD *)(a1 + 152) )
  {
    WinhttpStaticResolverCacheEntry = DotCreateWinhttpStaticResolverCacheEntry(lpMem, *(_QWORD *)(a1 + 136));
    LastError = WinhttpStaticResolverCacheEntry;
    if ( !WinhttpStaticResolverCacheEntry )
    {
      v4 = *(const WCHAR **)(a1 + 152);
      goto LABEL_10;
    }
    if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
      goto LABEL_31;
    v5 = 65;
LABEL_30:
    WPP_SF_d(1035, v5, WPP_e56dd19b1cdc30a42d7776c3f5a09aa5_Traceguids, WinhttpStaticResolverCacheEntry);
    goto LABEL_31;
  }
  v4 = *(const WCHAR **)(a1 + 144);
LABEL_10:
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_S(1035, 66, WPP_e56dd19b1cdc30a42d7776c3f5a09aa5_Traceguids, v4);
  v6 = WinHttpConnect(*((HINTERNET *)lpMem + 1), v4, *(_WORD *)(a1 + 202), 0);
  v7 = v6;
  if ( !v6 )
  {
    LastError = GetLastError();
    goto LABEL_31;
  }
  v8 = WinHttpOpenRequest(v6, 0, 0, 0, 0, 0, 0x800000u);
  v9 = v8;
  if ( !v8 || !WinHttpSetOption(v8, 0xC5u, 0, 0) )
    goto LABEL_15;
  DdrSkipCertVerification(*(PCWSTR *)(a1 + 136), *(PCWSTR *)(a1 + 128));
  v10 = PrepareWinhttpRequestCommon(v9);
  LastError = v10;
  if ( !v10 )
  {
    Buffer = a1;
    if ( WinHttpSetOption(v9, 0x2Du, &Buffer, 8u) )
    {
      if ( WinHttpSetStatusCallback(v9, DotCompleteUpgradeWinhttpStatusCallback, 0xFFFFFFFF, 0) != (WINHTTP_STATUS_CALLBACK)-1LL )
      {
        LastError = 0;
        *(_QWORD *)(a1 + 160) = lpMem;
        lpMem = 0;
        *(_QWORD *)(a1 + 120) = v7;
        DotConnectionAddRef(a1);
        InitializeDnsWinhttpHandle(v9, a1 + 216);
        *(_DWORD *)(a1 + 68) = 1;
        goto LABEL_31;
      }
      v10 = GetLastError();
      LastError = v10;
      if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
        goto LABEL_26;
      v11 = 68;
      goto LABEL_25;
    }
LABEL_15:
    LastError = GetLastError();
    goto LABEL_26;
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
    goto LABEL_26;
  v11 = 67;
LABEL_25:
  WPP_SF_d(1035, v11, WPP_e56dd19b1cdc30a42d7776c3f5a09aa5_Traceguids, v10);
LABEL_26:
  WinHttpCloseHandle(v7);
  if ( v9 )
    WinHttpCloseHandle(v9);
LABEL_31:
  if ( lpMem )
  {
    DeRefDnsWinhttpSession(lpMem);
    lpMem = 0;
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 69, WPP_e56dd19b1cdc30a42d7776c3f5a09aa5_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x1800a86a8  push    rbx
0x1800a86aa  push    rbp
0x1800a86ab  push    rsi
0x1800a86ac  push    rdi
0x1800a86ad  push    r12
0x1800a86af  push    r13
0x1800a86b1  sub     rsp, 68h
0x1800a86b5  mov     rax, cs:__security_cookie
0x1800a86bc  xor     rax, rsp
0x1800a86bf  mov     [rsp+98h+var_48], rax
0x1800a86c4  mov     rdi, rcx
0x1800a86c7  mov     [rsp+98h+Buffer], 0
0x1800a86d0  mov     [rsp+98h+lpMem], 0
0x1800a86d9  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800a86e0  lea     r13, WPP_e56dd19b1cdc30a42d7776c3f5a09aa5_Traceguids
0x1800a86e7  mov     r12d, 40Bh
0x1800a86ed  jz      short loc_1800A8702
0x1800a86ef  mov     edx, 3Fh ; '?'
0x1800a86f4  mov     ecx, r12d
0x1800a86f7  mov     r9, rdi
0x1800a86fa  mov     r8, r13
0x1800a86fd  call    WPP_SF_q
0x1800a8702  mov     r9, [rdi+80h]
0x1800a8709  lea     rax, [rsp+98h+lpMem]
0x1800a870e  mov     r8, [rdi+88h]
0x1800a8715  mov     edx, 2
0x1800a871a  mov     [rsp+98h+var_60], rax
0x1800a871f  xor     ecx, ecx
0x1800a8721  mov     eax, [rdi+64h]
0x1800a8724  mov     [rsp+98h+dwFlags], eax
0x1800a8728  movzx   eax, word ptr [rdi+0CAh]
0x1800a872f  mov     word ptr [rsp+98h+ppwszAcceptTypes], ax
0x1800a8734  mov     rax, [rdi+98h]
0x1800a873b  mov     [rsp+98h+pwszReferrer], rax
0x1800a8740  call    Send_PrepareWinhttpSession
0x1800a8745  mov     ebx, eax
0x1800a8747  test    eax, eax
0x1800a8749  jnz     loc_1800A896C
0x1800a874f  mov     r8, [rdi+98h]
0x1800a8756  test    r8, r8
0x1800a8759  jz      short loc_1800A8792
0x1800a875b  mov     rdx, [rdi+88h]
0x1800a8762  mov     rcx, [rsp+98h+lpMem]
0x1800a8767  call    DotCreateWinhttpStaticResolverCacheEntry
0x1800a876c  mov     ebx, eax
0x1800a876e  test    eax, eax
0x1800a8770  jnz     short loc_1800A877B
0x1800a8772  mov     rbx, [rdi+98h]
0x1800a8779  jmp     short loc_1800A8799
0x1800a877b  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800a8782  jz      loc_1800A8988
0x1800a8788  mov     edx, 41h ; 'A'
0x1800a878d  jmp     loc_1800A897A
0x1800a8792  mov     rbx, [rdi+90h]
0x1800a8799  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800a87a0  jz      short loc_1800A87B5
0x1800a87a2  mov     edx, 42h ; 'B'
0x1800a87a7  mov     ecx, r12d
0x1800a87aa  mov     r9, rbx
0x1800a87ad  mov     r8, r13
0x1800a87b0  call    WPP_SF_S
0x1800a87b5  mov     rcx, [rsp+98h+lpMem]
0x1800a87ba  xor     r9d, r9d; dwReserved
0x1800a87bd  movzx   r8d, word ptr [rdi+0CAh]; nServerPort
0x1800a87c5  mov     rdx, rbx; pswzServerName
0x1800a87c8  mov     rcx, [rcx+8]; hSession
0x1800a87cc  call    cs:__imp_WinHttpConnect
0x1800a87d3  nop     dword ptr [rax+rax+00h]
0x1800a87d8  mov     rbp, rax
0x1800a87db  test    rax, rax
0x1800a87de  jnz     short loc_1800A87F3
0x1800a87e0  call    cs:__imp_GetLastError
0x1800a87e7  nop     dword ptr [rax+rax+00h]
0x1800a87ec  mov     ebx, eax
0x1800a87ee  jmp     loc_1800A8988
0x1800a87f3  mov     [rsp+98h+dwFlags], 800000h; dwFlags
0x1800a87fb  xor     r9d, r9d; pwszVersion
0x1800a87fe  mov     [rsp+98h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x1800a8807  xor     r8d, r8d; pwszObjectName
0x1800a880a  xor     edx, edx; pwszVerb
0x1800a880c  mov     [rsp+98h+pwszReferrer], 0; pwszReferrer
0x1800a8815  mov     rcx, rbp; hConnect
0x1800a8818  call    cs:__imp_WinHttpOpenRequest
0x1800a881f  nop     dword ptr [rax+rax+00h]
0x1800a8824  mov     rsi, rax
0x1800a8827  test    rax, rax
0x1800a882a  jnz     short loc_1800A883F
0x1800a882c  call    cs:__imp_GetLastError
0x1800a8833  nop     dword ptr [rax+rax+00h]
0x1800a8838  mov     ebx, eax
0x1800a883a  jmp     loc_1800A8947
0x1800a883f  xor     r9d, r9d; dwBufferLength
0x1800a8842  xor     r8d, r8d; lpBuffer
0x1800a8845  mov     edx, 0C5h; dwOption
0x1800a884a  mov     rcx, rsi; hInternet
0x1800a884d  call    cs:__imp_WinHttpSetOption
0x1800a8854  nop     dword ptr [rax+rax+00h]
0x1800a8859  test    eax, eax
0x1800a885b  jz      short loc_1800A882C
0x1800a885d  mov     rdx, [rdi+80h]; PCWSTR
0x1800a8864  mov     rcx, [rdi+88h]; AddressString
0x1800a886b  call    DdrSkipCertVerification
0x1800a8870  mov     r8, [rdi+0C0h]
0x1800a8877  mov     edx, eax
0x1800a8879  mov     rcx, rsi; hInternet
0x1800a887c  call    PrepareWinhttpRequestCommon
0x1800a8881  mov     ebx, eax
0x1800a8883  test    eax, eax
0x1800a8885  jnz     loc_1800A892B
0x1800a888b  lea     r9d, [rax+8]; dwBufferLength
0x1800a888f  mov     [rsp+98h+Buffer], rdi
0x1800a8894  lea     r8, [rsp+98h+Buffer]; lpBuffer
0x1800a8899  mov     rcx, rsi; hInternet
0x1800a889c  lea     edx, [rax+2Dh]; dwOption
0x1800a889f  call    cs:__imp_WinHttpSetOption
0x1800a88a6  nop     dword ptr [rax+rax+00h]
0x1800a88ab  test    eax, eax
0x1800a88ad  jz      loc_1800A882C
0x1800a88b3  xor     r9d, r9d; dwReserved
0x1800a88b6  lea     rdx, DotCompleteUpgradeWinhttpStatusCallback; lpfnInternetCallback
0x1800a88bd  or      r8d, 0FFFFFFFFh; dwNotificationFlags
0x1800a88c1  mov     rcx, rsi; hInternet
0x1800a88c4  call    cs:__imp_WinHttpSetStatusCallback
0x1800a88cb  nop     dword ptr [rax+rax+00h]
0x1800a88d0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a88d4  jnz     short loc_1800A88F4
0x1800a88d6  call    cs:__imp_GetLastError
0x1800a88dd  nop     dword ptr [rax+rax+00h]
0x1800a88e2  mov     ebx, eax
0x1800a88e4  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800a88eb  jz      short loc_1800A8947
0x1800a88ed  mov     edx, 44h ; 'D'
0x1800a88f2  jmp     short loc_1800A8939
0x1800a88f4  mov     rax, [rsp+98h+lpMem]
0x1800a88f9  xor     ebx, ebx
0x1800a88fb  mov     rcx, rdi
0x1800a88fe  mov     [rdi+0A0h], rax
0x1800a8905  mov     [rsp+98h+lpMem], rbx
0x1800a890a  mov     [rdi+78h], rbp
0x1800a890e  call    DotConnectionAddRef
0x1800a8913  lea     rdx, [rdi+0D8h]
0x1800a891a  mov     rcx, rsi
0x1800a891d  call    InitializeDnsWinhttpHandle
0x1800a8922  mov     dword ptr [rdi+44h], 1
0x1800a8929  jmp     short loc_1800A8988
0x1800a892b  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800a8932  jz      short loc_1800A8947
0x1800a8934  mov     edx, 43h ; 'C'
0x1800a8939  mov     r9d, eax
0x1800a893c  mov     r8, r13
0x1800a893f  mov     ecx, r12d
0x1800a8942  call    WPP_SF_d
0x1800a8947  mov     rcx, rbp; hInternet
0x1800a894a  call    cs:__imp_WinHttpCloseHandle
0x1800a8951  nop     dword ptr [rax+rax+00h]
0x1800a8956  test    rsi, rsi
0x1800a8959  jz      short loc_1800A8988
0x1800a895b  mov     rcx, rsi; hInternet
0x1800a895e  call    cs:__imp_WinHttpCloseHandle
0x1800a8965  nop     dword ptr [rax+rax+00h]
0x1800a896a  jmp     short loc_1800A8988
0x1800a896c  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800a8973  jz      short loc_1800A8988
0x1800a8975  mov     edx, 40h ; '@'
0x1800a897a  mov     r9d, eax
0x1800a897d  mov     r8, r13
0x1800a8980  mov     ecx, r12d
0x1800a8983  call    WPP_SF_d
0x1800a8988  mov     rcx, [rsp+98h+lpMem]; lpMem
0x1800a898d  test    rcx, rcx
0x1800a8990  jz      short loc_1800A89A0
0x1800a8992  call    DeRefDnsWinhttpSession
0x1800a8997  mov     [rsp+98h+lpMem], 0
0x1800a89a0  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800a89a7  jz      short loc_1800A89BC
0x1800a89a9  mov     edx, 45h ; 'E'
0x1800a89ae  mov     ecx, r12d
0x1800a89b1  mov     r9d, ebx
0x1800a89b4  mov     r8, r13
0x1800a89b7  call    WPP_SF_d
0x1800a89bc  mov     eax, ebx
0x1800a89be  mov     rcx, [rsp+98h+var_48]
0x1800a89c3  xor     rcx, rsp; StackCookie
0x1800a89c6  call    __security_check_cookie
0x1800a89cb  add     rsp, 68h
0x1800a89cf  pop     r13
0x1800a89d1  pop     r12
0x1800a89d3  pop     rdi
0x1800a89d4  pop     rsi
0x1800a89d5  pop     rbp
0x1800a89d6  pop     rbx
0x1800a89d7  retn
```
