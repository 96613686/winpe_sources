# WinHttpRequest::GetCopyOfResponseBuffer(ushort * *,ulong *)

- ea: `0x180078720`
- end: `0x180078945`
- name: `?GetCopyOfResponseBuffer@WinHttpRequest@@QEAAJPEAPEAGPEAK@Z`
- size: `549`
- prototype: `__int64 __fastcall(WinHttpRequest *__hidden this, unsigned __int16 **, unsigned int *)`
- caller_count: `9`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180064b4c`
- `0x180066938`
- `0x18007a6bc`
- `0x180084728`
- `0x180088478`
- `0x1800b5be0`
- `0x1800b82ec`
- `0x1800ba15c`
- `0x1800ba4c8`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x18001cb8c`
- `0x1800307c4`
- `0x18003334c`
- `0x180043ef8`
- `0x180044d30`
- `0x18004654c`
- `0x180078720`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800788da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800788da`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18007883b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800788cd`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18007883b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800788cd`

## string_xrefs

- `0x180078749`: `WinHttpRequest::GetCopyOfResponseBuffer`
- `0x180078763`: `WinHttpRequest::GetCopyOfResponseBuffer`
- `0x180078785`: `WinHttpRequest::GetCopyOfResponseBuffer`
- `0x1800787cb`: `WinHttpRequest::GetCopyOfResponseBuffer`
- `0x18007885f`: `WinHttpRequest::GetCopyOfResponseBuffer`
- `0x18007889a`: `WinHttpRequest::GetCopyOfResponseBuffer`
- `0x180078921`: `WinHttpRequest::GetCopyOfResponseBuffer`

## pseudocode

```c
__int64 __fastcall WinHttpRequest::GetCopyOfResponseBuffer(
        WinHttpRequest *this,
        unsigned __int16 **a2,
        unsigned int *a3)
{
  unsigned int v6; // ebx
  const unsigned __int16 *v7; // rdx
  void *v8; // rax
  void *v9; // rbp
  int v10; // edi
  unsigned int v11; // eax
  unsigned __int64 cchWideChar; // rbx
  DWORD LastError; // eax
  unsigned __int16 *v14; // rsi
  unsigned __int64 v15; // rax
  WCHAR *lpWideCharStr; // rax
  int v17; // r12d

  if ( !a2 )
  {
    v6 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"WinHttpRequest::GetCopyOfResponseBuffer", L"ppszOut");
    v7 = L"ppszOut";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"WinHttpRequest::GetCopyOfResponseBuffer", v7);
    goto LABEL_25;
  }
  if ( !a3 )
  {
    v6 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"WinHttpRequest::GetCopyOfResponseBuffer", L"pdwOut");
    v7 = L"pdwOut";
    goto LABEL_3;
  }
  *a2 = 0;
  *a3 = 0;
  v8 = operator new[]((unsigned int)(*((_DWORD *)this + 34) + 1), (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( !v8 )
  {
    v6 = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"WinHttpRequest::GetCopyOfResponseBuffer");
    goto LABEL_25;
  }
  v10 = 0;
  memset_0(v8, 0, (unsigned int)(*((_DWORD *)this + 34) + 1));
  memcpy_s_0(v9, *((unsigned int *)this + 34), *((const void *const *)this + 16), *((unsigned int *)this + 34));
  *((_BYTE *)v9 + *((unsigned int *)this + 34)) = 0;
  v11 = MultiByteToWideChar(0xFDE9u, 8u, (LPCCH)v9, -1, 0, 0);
  cchWideChar = v11;
  if ( v11 || (LastError = GetLastError(), (v10 = LastError) == 0) )
  {
    v15 = 2 * cchWideChar;
    if ( !is_mul_ok(cchWideChar, 2u) )
      v15 = -1;
    lpWideCharStr = (WCHAR *)operator new[](v15, (const struct std::nothrow_t *)&std::nothrow);
    v14 = lpWideCharStr;
    if ( lpWideCharStr )
    {
      v17 = MultiByteToWideChar(0xFDE9u, 8u, (LPCCH)v9, -1, lpWideCharStr, cchWideChar);
      if ( !v17 )
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError )
          goto LABEL_11;
      }
      *a2 = v14;
      v6 = 0;
      v14 = 0;
      *a3 = v17;
    }
    else
    {
      v6 = -2147024882;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"WinHttpRequest::GetCopyOfResponseBuffer");
    }
    if ( !v10 )
      goto LABEL_23;
    goto LABEL_20;
  }
  v14 = 0;
LABEL_11:
  Logger::TraceError(
    L"%s: %s failed with win32 error code: 0x%08x.",
    L"WinHttpRequest::GetCopyOfResponseBuffer",
    L"MultiByteToWideChar",
    LastError);
LABEL_20:
  if ( v10 > 0 )
    v6 = (unsigned __int16)v10 | 0x80070000;
  else
    v6 = v10;
LABEL_23:
  operator delete(v9);
  if ( v14 )
    operator delete(v14);
LABEL_25:
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"WinHttpRequest::GetCopyOfResponseBuffer", v6);
  return v6;
}

```

## disassembly

```asm
0x180078720  push    rbx
0x180078722  push    rbp
0x180078723  push    rsi
0x180078724  push    rdi
0x180078725  push    r12
0x180078727  push    r14
0x180078729  push    r15
0x18007872b  sub     rsp, 30h
0x18007872f  mov     r14, r8
0x180078732  mov     r15, rdx
0x180078735  mov     rbx, rcx
0x180078738  test    rdx, rdx
0x18007873b  jnz     short loc_180078774
0x18007873d  lea     r8, cbBinary; "ppszOut"
0x180078744  mov     ebx, 80070057h
0x180078749  lea     rdx, aWinhttprequest_8; "WinHttpRequest::GetCopyOfResponseBuffer"
0x180078750  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180078757  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007875c  lea     rdx, cbBinary; "ppszOut"
0x180078763  lea     rcx, aWinhttprequest_8; "WinHttpRequest::GetCopyOfResponseBuffer"
0x18007876a  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18007876f  jmp     loc_18007891E
0x180078774  test    r14, r14
0x180078777  jnz     short loc_1800787A1
0x180078779  lea     r8, aPdwout; "pdwOut"
0x180078780  mov     ebx, 80070057h
0x180078785  lea     rdx, aWinhttprequest_8; "WinHttpRequest::GetCopyOfResponseBuffer"
0x18007878c  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180078793  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180078798  lea     rdx, aPdwout; "pdwOut"
0x18007879f  jmp     short loc_180078763
0x1800787a1  mov     qword ptr [rdx], 0
0x1800787a8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800787af  mov     dword ptr [r8], 0
0x1800787b6  mov     ecx, [rcx+88h]
0x1800787bc  inc     ecx; unsigned __int64
0x1800787be  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800787c3  mov     rbp, rax
0x1800787c6  test    rax, rax
0x1800787c9  jnz     short loc_1800787E8
0x1800787cb  lea     rdx, aWinhttprequest_8; "WinHttpRequest::GetCopyOfResponseBuffer"
0x1800787d2  mov     ebx, 8007000Eh
0x1800787d7  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x1800787de  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x1800787e3  jmp     loc_18007891E
0x1800787e8  mov     r8d, [rbx+88h]
0x1800787ef  xor     edx, edx; Val
0x1800787f1  inc     r8d; Size
0x1800787f4  mov     rcx, rbp; void *
0x1800787f7  xor     edi, edi
0x1800787f9  call    memset_0
0x1800787fe  mov     edx, [rbx+88h]; DestinationSize
0x180078804  mov     rcx, rbp; Destination
0x180078807  mov     r8, [rbx+80h]; Source
0x18007880e  mov     r9d, edx; SourceSize
0x180078811  call    memcpy_s_0
0x180078816  mov     eax, [rbx+88h]
0x18007881c  lea     edx, [rdi+8]; dwFlags
0x18007881f  or      r12, 0FFFFFFFFFFFFFFFFh
0x180078823  mov     [rsp+68h+cchWideChar], edi; cchWideChar
0x180078827  mov     r9d, r12d; cbMultiByte
0x18007882a  mov     [rsp+68h+lpWideCharStr], rdi; lpWideCharStr
0x18007882f  mov     r8, rbp; lpMultiByteStr
0x180078832  mov     ecx, 0FDE9h; CodePage
0x180078837  mov     [rax+rbp], dil
0x18007883b  call    cs:__imp_MultiByteToWideChar
0x180078841  mov     ebx, eax
0x180078843  test    eax, eax
0x180078845  jnz     short loc_180078877
0x180078847  call    cs:__imp_GetLastError
0x18007884d  mov     edi, eax
0x18007884f  test    eax, eax
0x180078851  jz      short loc_180078877
0x180078853  xor     esi, esi
0x180078855  mov     r9d, eax
0x180078858  lea     r8, aMultibytetowid; "MultiByteToWideChar"
0x18007885f  lea     rdx, aWinhttprequest_8; "WinHttpRequest::GetCopyOfResponseBuffer"
0x180078866  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18007886d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180078872  jmp     loc_1800788F8
0x180078877  mov     eax, 2
0x18007887c  mul     rbx
0x18007887f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180078886  cmovb   rax, r12
0x18007888a  mov     rcx, rax; unsigned __int64
0x18007888d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180078892  mov     rsi, rax
0x180078895  test    rax, rax
0x180078898  jnz     short loc_1800788B4
0x18007889a  lea     rdx, aWinhttprequest_8; "WinHttpRequest::GetCopyOfResponseBuffer"
0x1800788a1  mov     ebx, 8007000Eh
0x1800788a6  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x1800788ad  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x1800788b2  jmp     short loc_1800788F4
0x1800788b4  mov     [rsp+68h+cchWideChar], ebx; cchWideChar
0x1800788b8  mov     r9d, r12d; cbMultiByte
0x1800788bb  mov     r8, rbp; lpMultiByteStr
0x1800788be  mov     [rsp+68h+lpWideCharStr], rsi; lpWideCharStr
0x1800788c3  mov     edx, 8; dwFlags
0x1800788c8  mov     ecx, 0FDE9h; CodePage
0x1800788cd  call    cs:__imp_MultiByteToWideChar
0x1800788d3  mov     r12d, eax
0x1800788d6  test    eax, eax
0x1800788d8  jnz     short loc_1800788EA
0x1800788da  call    cs:__imp_GetLastError
0x1800788e0  mov     edi, eax
0x1800788e2  test    eax, eax
0x1800788e4  jnz     loc_180078855
0x1800788ea  mov     [r15], rsi
0x1800788ed  xor     ebx, ebx
0x1800788ef  xor     esi, esi
0x1800788f1  mov     [r14], r12d
0x1800788f4  test    edi, edi
0x1800788f6  jz      short loc_180078909
0x1800788f8  test    edi, edi
0x1800788fa  jg      short loc_180078900
0x1800788fc  mov     ebx, edi
0x1800788fe  jmp     short loc_180078909
0x180078900  movzx   ebx, di
0x180078903  or      ebx, 80070000h
0x180078909  mov     rcx, rbp; Block
0x18007890c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180078911  test    rsi, rsi
0x180078914  jz      short loc_18007891E
0x180078916  mov     rcx, rsi; Block
0x180078919  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007891e  mov     r8d, ebx
0x180078921  lea     rdx, aWinhttprequest_8; "WinHttpRequest::GetCopyOfResponseBuffer"
0x180078928  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18007892f  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180078934  mov     eax, ebx
0x180078936  add     rsp, 30h
0x18007893a  pop     r15
0x18007893c  pop     r14
0x18007893e  pop     r12
0x180078940  pop     rdi
0x180078941  pop     rsi
0x180078942  pop     rbp
0x180078943  pop     rbx
0x180078944  retn
```
