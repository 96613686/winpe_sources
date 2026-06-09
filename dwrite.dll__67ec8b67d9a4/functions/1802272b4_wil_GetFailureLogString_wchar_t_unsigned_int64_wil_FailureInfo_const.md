# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1802272b4`
- end: `0x18022756a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180225d28`
- `0x180227b70`
- `0x18022820c`
- `0x18022a420`

## callees

- `0x180212490`
- `0x180212f4c`
- `0x1802272b4`
- `0x180227e70`
- `0x180330010`

## import_xrefs

- `kernel32!FormatMessageW` at `0x1802273e6`
- `kernel32!FormatMessageW` at `0x1802273e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180227467`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180227467`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        STRSAFE_LPWSTR pszDest,
        wchar_t *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rsi
  const wchar_t *v11; // r9
  __int64 v12; // rax
  const wchar_t *v13; // rcx
  wchar_t *v14; // rax
  wchar_t *v15; // r14
  const wchar_t *v16; // r9
  wchar_t *v17; // rax
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
  if ( !pszDest )
    return 0;
  *pszDest = 0;
  if ( g_pfnResultLoggingCallback )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      g_pfnResultLoggingCallback(a3, pszDest, a2);
      if ( *pszDest )
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
          v7 = (const char *)&qword_180374320;
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
  v10 = &pszDest[(_QWORD)a2];
  v11 = *(const wchar_t **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const wchar_t **)(a3 + 128);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(pszDest, v10, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, v13, v12);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(pszDest, v10, L"%hs!%p: ", v13, v12);
  }
  v15 = v14;
  v16 = *(const wchar_t **)(a3 + 144);
  if ( v16 )
    v15 = wil::details::LogStringPrintf(v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = wil::details::LogStringPrintf(
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
      v19 = wil::details::LogStringPrintf(v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const wchar_t **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf(v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const wchar_t **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf(v19, v10, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf(v19, v10, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf(v19, v10, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1802272b4  mov     [rsp+arg_18], rbx
0x1802272b9  push    rbp
0x1802272ba  push    rsi
0x1802272bb  push    rdi
0x1802272bc  push    r14
0x1802272be  push    r15
0x1802272c0  sub     rsp, 250h
0x1802272c7  mov     rax, cs:__security_cookie
0x1802272ce  xor     rax, rsp
0x1802272d1  mov     [rsp+278h+var_38], rax
0x1802272d9  mov     rbx, r8
0x1802272dc  mov     rsi, rdx
0x1802272df  mov     r14, rcx
0x1802272e2  xor     r15d, r15d
0x1802272e5  test    rdx, rdx
0x1802272e8  jz      loc_180227541
0x1802272ee  test    rcx, rcx
0x1802272f1  jz      loc_180227541
0x1802272f7  mov     [rcx], r15w
0x1802272fb  mov     rax, cs:g_pfnResultLoggingCallback
0x180227302  test    rax, rax
0x180227305  jz      short loc_180227328
0x180227307  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18022730e  jz      short loc_180227328
0x180227310  mov     r8, rdx
0x180227313  mov     rdx, rcx
0x180227316  mov     rcx, rbx
0x180227319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022731e  cmp     [r14], r15w
0x180227322  jnz     loc_180227541
0x180227328  mov     ecx, [rbx]
0x18022732a  mov     bpl, 8
0x18022732d  test    ecx, ecx
0x18022732f  jz      short loc_18022737A
0x180227331  sub     ecx, 1
0x180227334  jz      short loc_180227362
0x180227336  sub     ecx, 1
0x180227339  jz      short loc_180227352
0x18022733b  cmp     ecx, 1
0x18022733e  jz      short loc_180227349
0x180227340  lea     rdi, qword_180374320
0x180227347  jmp     short loc_180227381
0x180227349  lea     rdi, aFailfast; "FailFast"
0x180227350  jmp     short loc_180227381
0x180227352  lea     rax, aLoghr; "LogHr"
0x180227359  lea     rdi, aLognt; "LogNt"
0x180227360  jmp     short loc_180227370
0x180227362  lea     rax, aReturnhr; "ReturnHr"
0x180227369  lea     rdi, aReturnnt; "ReturnNt"
0x180227370  test    [rbx+4], bpl
0x180227374  cmovz   rdi, rax
0x180227378  jmp     short loc_180227381
0x18022737a  lea     rdi, aException; "Exception"
0x180227381  xor     edx, edx; Val
0x180227383  mov     r8d, 200h; Size
0x180227389  lea     rcx, [rsp+278h+Buffer]; void *
0x18022738e  call    memset_0
0x180227393  test    [rbx+4], bpl
0x180227397  jz      short loc_1802273BC
0x180227399  mov     ebp, [rbx+0Ch]
0x18022739c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x1802273a3  test    rax, rax
0x1802273a6  jz      short loc_1802273EC
0x1802273a8  mov     r8d, 100h
0x1802273ae  lea     rdx, [rsp+278h+Buffer]
0x1802273b3  mov     ecx, ebp
0x1802273b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802273ba  jmp     short loc_1802273EC
0x1802273bc  mov     ebp, [rbx+8]
0x1802273bf  mov     [rsp+278h+Arguments], r15; Arguments
0x1802273c4  mov     [rsp+278h+nSize], 100h; nSize
0x1802273cc  lea     rax, [rsp+278h+Buffer]
0x1802273d1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1802273d6  mov     r9d, 400h; dwLanguageId
0x1802273dc  mov     r8d, ebp; dwMessageId
0x1802273df  xor     edx, edx; lpSource
0x1802273e1  mov     ecx, 1200h; dwFlags
0x1802273e6  call    cs:__imp_FormatMessageW
0x1802273ec  lea     rsi, [r14+rsi*2]
0x1802273f0  mov     r9, [rbx+38h]; wchar_t *
0x1802273f4  mov     rax, [rbx+88h]
0x1802273fb  mov     rcx, [rbx+80h]
0x180227402  mov     rdx, rsi; wchar_t *
0x180227405  test    r9, r9
0x180227408  jz      short loc_18022742C
0x18022740a  mov     [rsp+278h+Arguments], rax
0x18022740f  mov     qword ptr [rsp+278h+nSize], rcx
0x180227414  mov     eax, [rbx+40h]
0x180227417  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18022741b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180227422  mov     rcx, r14; pszDest
0x180227425  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18022742a  jmp     short loc_180227443
0x18022742c  mov     [rsp+278h+lpBuffer], rax
0x180227431  mov     r9, rcx; wchar_t *
0x180227434  lea     r8, aHsP; "%hs!%p: "
0x18022743b  mov     rcx, r14; pszDest
0x18022743e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180227443  mov     r14, rax
0x180227446  mov     r9, [rbx+90h]; wchar_t *
0x18022744d  test    r9, r9
0x180227450  jz      short loc_180227467
0x180227452  lea     r8, aCallerP; "(caller: %p) "
0x180227459  mov     rdx, rsi; wchar_t *
0x18022745c  mov     rcx, rax; pszDest
0x18022745f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180227464  mov     r14, rax
0x180227467  call    cs:__imp_GetCurrentThreadId
0x18022746d  lea     rcx, [rsp+278h+Buffer]
0x180227472  mov     [rsp+278h+var_240], rcx
0x180227477  mov     dword ptr [rsp+278h+Arguments], ebp
0x18022747b  mov     [rsp+278h+nSize], eax
0x18022747f  mov     eax, [rbx+44h]
0x180227482  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180227486  mov     r9, rdi; wchar_t *
0x180227489  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180227490  mov     rdx, rsi; wchar_t *
0x180227493  mov     rcx, r14; pszDest
0x180227496  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18022749b  cmp     [rbx+18h], r15
0x18022749f  jnz     short loc_1802274B1
0x1802274a1  cmp     [rbx+48h], r15
0x1802274a5  jnz     short loc_1802274B1
0x1802274a7  cmp     [rbx+30h], r15
0x1802274ab  jz      loc_180227541
0x1802274b1  lea     r8, asc_180408948; "    "
0x1802274b8  mov     rdx, rsi; wchar_t *
0x1802274bb  mov     rcx, rax; pszDest
0x1802274be  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1802274c3  mov     r9, [rbx+18h]; wchar_t *
0x1802274c7  test    r9, r9
0x1802274ca  jz      short loc_1802274DE
0x1802274cc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1802274d3  mov     rdx, rsi; wchar_t *
0x1802274d6  mov     rcx, rax; pszDest
0x1802274d9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1802274de  mov     r9, [rbx+48h]; wchar_t *
0x1802274e2  test    r9, r9
0x1802274e5  jz      short loc_1802274F9
0x1802274e7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1802274ee  mov     rdx, rsi; wchar_t *
0x1802274f1  mov     rcx, rax; pszDest
0x1802274f4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1802274f9  mov     rcx, [rbx+28h]
0x1802274fd  mov     r9, [rbx+30h]; wchar_t *
0x180227501  mov     rdx, rsi; wchar_t *
0x180227504  test    rcx, rcx
0x180227507  jz      short loc_18022751F
0x180227509  mov     [rsp+278h+lpBuffer], rcx
0x18022750e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180227515  mov     rcx, rax; pszDest
0x180227518  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18022751d  jmp     short loc_180227541
0x18022751f  mov     rcx, rax; pszDest
0x180227522  test    r9, r9
0x180227525  jz      short loc_180227535
0x180227527  lea     r8, aHs; "[%hs]\n"
0x18022752e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180227533  jmp     short loc_180227541
0x180227535  lea     r8, asc_1804089C0; "\n"
0x18022753c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180227541  xor     eax, eax
0x180227543  mov     rcx, [rsp+278h+var_38]
0x18022754b  xor     rcx, rsp; StackCookie
0x18022754e  call    __security_check_cookie
0x180227553  mov     rbx, [rsp+278h+arg_18]
0x18022755b  add     rsp, 250h
0x180227562  pop     r15
0x180227564  pop     r14
0x180227566  pop     rdi
0x180227567  pop     rsi
0x180227568  pop     rbp
0x180227569  retn
```
