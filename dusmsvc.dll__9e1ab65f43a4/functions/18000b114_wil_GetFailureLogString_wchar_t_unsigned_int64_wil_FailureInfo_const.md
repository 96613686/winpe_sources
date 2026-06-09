# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000b114`
- end: `0x18000b3ca`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a22c`
- `0x18000bad4`
- `0x18000bfac`
- `0x18000d220`

## callees

- `0x180007c90`
- `0x180008704`
- `0x18000b114`
- `0x18000bdd4`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b2c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b2c7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b246`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b246`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rsi
  const wchar_t *v11; // r9
  __int64 v12; // rax
  const wchar_t *v13; // rcx
  wchar_t *v14; // rax
  wil::details *v15; // r14
  const wchar_t *v16; // r9
  wil::details *v17; // rax
  const wchar_t *v18; // r9
  wchar_t *v19; // rax
  const wchar_t *v20; // r9
  const wchar_t *v21; // r9
  const wchar_t *v22; // r9
  LPWSTR lpBuffer; // [rsp+20h] [rbp-258h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-258h]
  DWORD nSize[2]; // [rsp+28h] [rbp-250h]
  va_list *Arguments; // [rsp+30h] [rbp-248h]
  WCHAR Buffer[256]; // [rsp+40h] [rbp-238h] BYREF

  if ( !a2 )
    return 0;
  if ( !this )
    return 0;
  *(_WORD *)this = 0;
  if ( g_pfnResultLoggingCallback )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      g_pfnResultLoggingCallback(a3, this, a2);
      if ( *(_WORD *)this )
        return 0;
    }
  }
  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      v8 = "ReturnHr";
      v7 = "ReturnNt";
    }
    else
    {
      if ( *(_DWORD *)a3 != 2 )
      {
        if ( *(_DWORD *)a3 == 3 )
          v7 = "FailFast";
        else
          v7 = (const char *)&word_18004F692;
        goto LABEL_18;
      }
      v8 = "LogHr";
      v7 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v7 = v8;
    goto LABEL_18;
  }
  v7 = "Exception";
LABEL_18:
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
  {
    v9 = *(_DWORD *)(a3 + 12);
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(v9, Buffer, 0x100u);
  }
  else
  {
    v9 = *(_DWORD *)(a3 + 8);
    FormatMessageW(0x1200u, 0, v9, 0x400u, Buffer, 0x100u, 0);
  }
  v10 = (wchar_t *)((char *)this + 2 * (_QWORD)a2);
  v11 = *(const wchar_t **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const wchar_t **)(a3 + 128);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v10, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, v13, v12);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v10, L"%hs!%p: ", v13, v12);
  }
  v15 = (wil::details *)v14;
  v16 = *(const wchar_t **)(a3 + 144);
  if ( v16 )
    v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v15,
                          v10,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const wchar_t *)v7,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v10, L"    ", v18);
    v20 = *(const wchar_t **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const wchar_t **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const wchar_t **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v10, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v10, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf((wil::details *)v19, v10, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000b114  mov     [rsp+arg_18], rbx
0x18000b119  push    rbp
0x18000b11a  push    rsi
0x18000b11b  push    rdi
0x18000b11c  push    r14
0x18000b11e  push    r15
0x18000b120  sub     rsp, 250h
0x18000b127  mov     rax, cs:__security_cookie
0x18000b12e  xor     rax, rsp
0x18000b131  mov     [rsp+278h+var_38], rax
0x18000b139  mov     rbx, r8
0x18000b13c  mov     rsi, rdx
0x18000b13f  mov     r14, rcx
0x18000b142  xor     r15d, r15d
0x18000b145  test    rdx, rdx
0x18000b148  jz      loc_18000B3A1
0x18000b14e  test    rcx, rcx
0x18000b151  jz      loc_18000B3A1
0x18000b157  mov     [rcx], r15w
0x18000b15b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b162  test    rax, rax
0x18000b165  jz      short loc_18000B188
0x18000b167  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000b16e  jz      short loc_18000B188
0x18000b170  mov     r8, rdx
0x18000b173  mov     rdx, rcx
0x18000b176  mov     rcx, rbx
0x18000b179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b17e  cmp     [r14], r15w
0x18000b182  jnz     loc_18000B3A1
0x18000b188  mov     ecx, [rbx]
0x18000b18a  mov     bpl, 8
0x18000b18d  test    ecx, ecx
0x18000b18f  jz      short loc_18000B1DA
0x18000b191  sub     ecx, 1
0x18000b194  jz      short loc_18000B1C2
0x18000b196  sub     ecx, 1
0x18000b199  jz      short loc_18000B1B2
0x18000b19b  cmp     ecx, 1
0x18000b19e  jz      short loc_18000B1A9
0x18000b1a0  lea     rdi, word_18004F692
0x18000b1a7  jmp     short loc_18000B1E1
0x18000b1a9  lea     rdi, aFailfast; "FailFast"
0x18000b1b0  jmp     short loc_18000B1E1
0x18000b1b2  lea     rax, aLoghr; "LogHr"
0x18000b1b9  lea     rdi, aLognt; "LogNt"
0x18000b1c0  jmp     short loc_18000B1D0
0x18000b1c2  lea     rax, aReturnhr; "ReturnHr"
0x18000b1c9  lea     rdi, aReturnnt; "ReturnNt"
0x18000b1d0  test    [rbx+4], bpl
0x18000b1d4  cmovz   rdi, rax
0x18000b1d8  jmp     short loc_18000B1E1
0x18000b1da  lea     rdi, aException; "Exception"
0x18000b1e1  xor     edx, edx; Val
0x18000b1e3  mov     r8d, 200h; Size
0x18000b1e9  lea     rcx, [rsp+278h+Buffer]; void *
0x18000b1ee  call    memset_0
0x18000b1f3  test    [rbx+4], bpl
0x18000b1f7  jz      short loc_18000B21C
0x18000b1f9  mov     ebp, [rbx+0Ch]
0x18000b1fc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x18000b203  test    rax, rax
0x18000b206  jz      short loc_18000B24C
0x18000b208  mov     r8d, 100h
0x18000b20e  lea     rdx, [rsp+278h+Buffer]
0x18000b213  mov     ecx, ebp
0x18000b215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b21a  jmp     short loc_18000B24C
0x18000b21c  mov     ebp, [rbx+8]
0x18000b21f  mov     [rsp+278h+Arguments], r15; Arguments
0x18000b224  mov     [rsp+278h+nSize], 100h; nSize
0x18000b22c  lea     rax, [rsp+278h+Buffer]
0x18000b231  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000b236  mov     r9d, 400h; dwLanguageId
0x18000b23c  mov     r8d, ebp; dwMessageId
0x18000b23f  xor     edx, edx; lpSource
0x18000b241  mov     ecx, 1200h; dwFlags
0x18000b246  call    cs:__imp_FormatMessageW
0x18000b24c  lea     rsi, [r14+rsi*2]
0x18000b250  mov     r9, [rbx+38h]; wchar_t *
0x18000b254  mov     rax, [rbx+88h]
0x18000b25b  mov     rcx, [rbx+80h]
0x18000b262  mov     rdx, rsi; wchar_t *
0x18000b265  test    r9, r9
0x18000b268  jz      short loc_18000B28C
0x18000b26a  mov     [rsp+278h+Arguments], rax
0x18000b26f  mov     qword ptr [rsp+278h+nSize], rcx
0x18000b274  mov     eax, [rbx+40h]
0x18000b277  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000b27b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000b282  mov     rcx, r14; this
0x18000b285  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000b28a  jmp     short loc_18000B2A3
0x18000b28c  mov     [rsp+278h+lpBuffer], rax
0x18000b291  mov     r9, rcx; wchar_t *
0x18000b294  lea     r8, aHsP; "%hs!%p: "
0x18000b29b  mov     rcx, r14; this
0x18000b29e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000b2a3  mov     r14, rax
0x18000b2a6  mov     r9, [rbx+90h]; wchar_t *
0x18000b2ad  test    r9, r9
0x18000b2b0  jz      short loc_18000B2C7
0x18000b2b2  lea     r8, aCallerP; "(caller: %p) "
0x18000b2b9  mov     rdx, rsi; wchar_t *
0x18000b2bc  mov     rcx, rax; this
0x18000b2bf  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000b2c4  mov     r14, rax
0x18000b2c7  call    cs:__imp_GetCurrentThreadId
0x18000b2cd  lea     rcx, [rsp+278h+Buffer]
0x18000b2d2  mov     [rsp+278h+var_240], rcx
0x18000b2d7  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000b2db  mov     [rsp+278h+nSize], eax
0x18000b2df  mov     eax, [rbx+44h]
0x18000b2e2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000b2e6  mov     r9, rdi; wchar_t *
0x18000b2e9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000b2f0  mov     rdx, rsi; wchar_t *
0x18000b2f3  mov     rcx, r14; this
0x18000b2f6  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000b2fb  cmp     [rbx+18h], r15
0x18000b2ff  jnz     short loc_18000B311
0x18000b301  cmp     [rbx+48h], r15
0x18000b305  jnz     short loc_18000B311
0x18000b307  cmp     [rbx+30h], r15
0x18000b30b  jz      loc_18000B3A1
0x18000b311  lea     r8, asc_18004F780; "    "
0x18000b318  mov     rdx, rsi; wchar_t *
0x18000b31b  mov     rcx, rax; this
0x18000b31e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000b323  mov     r9, [rbx+18h]; wchar_t *
0x18000b327  test    r9, r9
0x18000b32a  jz      short loc_18000B33E
0x18000b32c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000b333  mov     rdx, rsi; wchar_t *
0x18000b336  mov     rcx, rax; this
0x18000b339  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000b33e  mov     r9, [rbx+48h]; wchar_t *
0x18000b342  test    r9, r9
0x18000b345  jz      short loc_18000B359
0x18000b347  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000b34e  mov     rdx, rsi; wchar_t *
0x18000b351  mov     rcx, rax; this
0x18000b354  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000b359  mov     rcx, [rbx+28h]
0x18000b35d  mov     r9, [rbx+30h]; wchar_t *
0x18000b361  mov     rdx, rsi; wchar_t *
0x18000b364  test    rcx, rcx
0x18000b367  jz      short loc_18000B37F
0x18000b369  mov     [rsp+278h+lpBuffer], rcx
0x18000b36e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000b375  mov     rcx, rax; this
0x18000b378  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000b37d  jmp     short loc_18000B3A1
0x18000b37f  mov     rcx, rax; this
0x18000b382  test    r9, r9
0x18000b385  jz      short loc_18000B395
0x18000b387  lea     r8, aHs; "[%hs]\n"
0x18000b38e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000b393  jmp     short loc_18000B3A1
0x18000b395  lea     r8, asc_18004F7F8; "\n"
0x18000b39c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000b3a1  xor     eax, eax
0x18000b3a3  mov     rcx, [rsp+278h+var_38]
0x18000b3ab  xor     rcx, rsp; StackCookie
0x18000b3ae  call    __security_check_cookie
0x18000b3b3  mov     rbx, [rsp+278h+arg_18]
0x18000b3bb  add     rsp, 250h
0x18000b3c2  pop     r15
0x18000b3c4  pop     r14
0x18000b3c6  pop     rdi
0x18000b3c7  pop     rsi
0x18000b3c8  pop     rbp
0x18000b3c9  retn
```
