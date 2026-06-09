# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800f0894`
- end: `0x1800f0b55`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800efa68`
- `0x1800f10ac`
- `0x1800f2440`

## callees

- `0x1800d6354`
- `0x1800f0894`
- `0x1800f13b4`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f0a52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f0a52`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800f09d1`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800f09d1`

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
  LPWSTR lpBuffer; // [rsp+20h] [rbp-268h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-268h]
  DWORD nSize[2]; // [rsp+28h] [rbp-260h]
  va_list *Arguments; // [rsp+30h] [rbp-258h]
  WCHAR Buffer[256]; // [rsp+50h] [rbp-238h] BYREF

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
          v7 = (const char *)&word_180139126;
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
                          Buffer,
                          -2);
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
0x1800f0894  mov     rax, rsp
0x1800f0897  push    rbp
0x1800f0898  push    rsi
0x1800f0899  push    rdi
0x1800f089a  push    r14
0x1800f089c  push    r15
0x1800f089e  sub     rsp, 260h
0x1800f08a5  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x1800f08ae  mov     [rax+20h], rbx
0x1800f08b2  mov     rax, cs:__security_cookie
0x1800f08b9  xor     rax, rsp
0x1800f08bc  mov     [rsp+288h+var_38], rax
0x1800f08c4  mov     rbx, r8
0x1800f08c7  mov     rsi, rdx
0x1800f08ca  mov     r14, rcx
0x1800f08cd  xor     r15d, r15d
0x1800f08d0  test    rdx, rdx
0x1800f08d3  jz      loc_1800F0B2C
0x1800f08d9  test    rcx, rcx
0x1800f08dc  jz      loc_1800F0B2C
0x1800f08e2  mov     [rcx], r15w
0x1800f08e6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800f08ed  test    rax, rax
0x1800f08f0  jz      short loc_1800F0913
0x1800f08f2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800f08f9  jz      short loc_1800F0913
0x1800f08fb  mov     r8, rdx
0x1800f08fe  mov     rdx, rcx
0x1800f0901  mov     rcx, rbx
0x1800f0904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0909  cmp     [r14], r15w
0x1800f090d  jnz     loc_1800F0B2C
0x1800f0913  mov     ecx, [rbx]
0x1800f0915  mov     bpl, 8
0x1800f0918  test    ecx, ecx
0x1800f091a  jz      short loc_1800F0965
0x1800f091c  sub     ecx, 1
0x1800f091f  jz      short loc_1800F094D
0x1800f0921  sub     ecx, 1
0x1800f0924  jz      short loc_1800F093D
0x1800f0926  cmp     ecx, 1
0x1800f0929  jz      short loc_1800F0934
0x1800f092b  lea     rdi, word_180139126
0x1800f0932  jmp     short loc_1800F096C
0x1800f0934  lea     rdi, aFailfast; "FailFast"
0x1800f093b  jmp     short loc_1800F096C
0x1800f093d  lea     rax, aLoghr; "LogHr"
0x1800f0944  lea     rdi, aLognt; "LogNt"
0x1800f094b  jmp     short loc_1800F095B
0x1800f094d  lea     rax, aReturnhr; "ReturnHr"
0x1800f0954  lea     rdi, aReturnnt; "ReturnNt"
0x1800f095b  test    [rbx+4], bpl
0x1800f095f  cmovz   rdi, rax
0x1800f0963  jmp     short loc_1800F096C
0x1800f0965  lea     rdi, aException; "Exception"
0x1800f096c  xor     edx, edx; Val
0x1800f096e  mov     r8d, 200h; Size
0x1800f0974  lea     rcx, [rsp+288h+Buffer]; void *
0x1800f0979  call    memset_0
0x1800f097e  test    [rbx+4], bpl
0x1800f0982  jz      short loc_1800F09A7
0x1800f0984  mov     ebp, [rbx+0Ch]
0x1800f0987  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x1800f098e  test    rax, rax
0x1800f0991  jz      short loc_1800F09D7
0x1800f0993  mov     r8d, 100h
0x1800f0999  lea     rdx, [rsp+288h+Buffer]
0x1800f099e  mov     ecx, ebp
0x1800f09a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f09a5  jmp     short loc_1800F09D7
0x1800f09a7  mov     ebp, [rbx+8]
0x1800f09aa  mov     [rsp+288h+Arguments], r15; Arguments
0x1800f09af  mov     [rsp+288h+nSize], 100h; nSize
0x1800f09b7  lea     rax, [rsp+288h+Buffer]
0x1800f09bc  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x1800f09c1  mov     r9d, 400h; dwLanguageId
0x1800f09c7  mov     r8d, ebp; dwMessageId
0x1800f09ca  xor     edx, edx; lpSource
0x1800f09cc  mov     ecx, 1200h; dwFlags
0x1800f09d1  call    cs:__imp_FormatMessageW
0x1800f09d7  lea     rsi, [r14+rsi*2]
0x1800f09db  mov     r9, [rbx+38h]; wchar_t *
0x1800f09df  mov     rax, [rbx+88h]
0x1800f09e6  mov     rcx, [rbx+80h]
0x1800f09ed  mov     rdx, rsi; wchar_t *
0x1800f09f0  test    r9, r9
0x1800f09f3  jz      short loc_1800F0A17
0x1800f09f5  mov     [rsp+288h+Arguments], rax
0x1800f09fa  mov     qword ptr [rsp+288h+nSize], rcx
0x1800f09ff  mov     eax, [rbx+40h]
0x1800f0a02  mov     dword ptr [rsp+288h+lpBuffer], eax
0x1800f0a06  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800f0a0d  mov     rcx, r14; this
0x1800f0a10  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800f0a15  jmp     short loc_1800F0A2E
0x1800f0a17  mov     [rsp+288h+lpBuffer], rax
0x1800f0a1c  mov     r9, rcx; wchar_t *
0x1800f0a1f  lea     r8, aHsP; "%hs!%p: "
0x1800f0a26  mov     rcx, r14; this
0x1800f0a29  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800f0a2e  mov     r14, rax
0x1800f0a31  mov     r9, [rbx+90h]; wchar_t *
0x1800f0a38  test    r9, r9
0x1800f0a3b  jz      short loc_1800F0A52
0x1800f0a3d  lea     r8, aCallerP; "(caller: %p) "
0x1800f0a44  mov     rdx, rsi; wchar_t *
0x1800f0a47  mov     rcx, rax; this
0x1800f0a4a  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800f0a4f  mov     r14, rax
0x1800f0a52  call    cs:__imp_GetCurrentThreadId
0x1800f0a58  lea     rcx, [rsp+288h+Buffer]
0x1800f0a5d  mov     [rsp+288h+var_250], rcx
0x1800f0a62  mov     dword ptr [rsp+288h+Arguments], ebp
0x1800f0a66  mov     [rsp+288h+nSize], eax
0x1800f0a6a  mov     eax, [rbx+44h]
0x1800f0a6d  mov     dword ptr [rsp+288h+lpBuffer], eax
0x1800f0a71  mov     r9, rdi; wchar_t *
0x1800f0a74  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800f0a7b  mov     rdx, rsi; wchar_t *
0x1800f0a7e  mov     rcx, r14; this
0x1800f0a81  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800f0a86  cmp     [rbx+18h], r15
0x1800f0a8a  jnz     short loc_1800F0A9C
0x1800f0a8c  cmp     [rbx+48h], r15
0x1800f0a90  jnz     short loc_1800F0A9C
0x1800f0a92  cmp     [rbx+30h], r15
0x1800f0a96  jz      loc_1800F0B2C
0x1800f0a9c  lea     r8, asc_18014A108; "    "
0x1800f0aa3  mov     rdx, rsi; wchar_t *
0x1800f0aa6  mov     rcx, rax; this
0x1800f0aa9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800f0aae  mov     r9, [rbx+18h]; wchar_t *
0x1800f0ab2  test    r9, r9
0x1800f0ab5  jz      short loc_1800F0AC9
0x1800f0ab7  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800f0abe  mov     rdx, rsi; wchar_t *
0x1800f0ac1  mov     rcx, rax; this
0x1800f0ac4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800f0ac9  mov     r9, [rbx+48h]; wchar_t *
0x1800f0acd  test    r9, r9
0x1800f0ad0  jz      short loc_1800F0AE4
0x1800f0ad2  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800f0ad9  mov     rdx, rsi; wchar_t *
0x1800f0adc  mov     rcx, rax; this
0x1800f0adf  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800f0ae4  mov     rcx, [rbx+28h]
0x1800f0ae8  mov     r9, [rbx+30h]; wchar_t *
0x1800f0aec  mov     rdx, rsi; wchar_t *
0x1800f0aef  test    rcx, rcx
0x1800f0af2  jz      short loc_1800F0B0A
0x1800f0af4  mov     [rsp+288h+lpBuffer], rcx
0x1800f0af9  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800f0b00  mov     rcx, rax; this
0x1800f0b03  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800f0b08  jmp     short loc_1800F0B2C
0x1800f0b0a  mov     rcx, rax; this
0x1800f0b0d  test    r9, r9
0x1800f0b10  jz      short loc_1800F0B20
0x1800f0b12  lea     r8, aHs; "[%hs]\n"
0x1800f0b19  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800f0b1e  jmp     short loc_1800F0B2C
0x1800f0b20  lea     r8, asc_18014A158; "\n"
0x1800f0b27  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800f0b2c  xor     eax, eax
0x1800f0b2e  mov     rcx, [rsp+288h+var_38]
0x1800f0b36  xor     rcx, rsp; StackCookie
0x1800f0b39  call    __security_check_cookie
0x1800f0b3e  mov     rbx, [rsp+288h+arg_18]
0x1800f0b46  add     rsp, 260h
0x1800f0b4d  pop     r15
0x1800f0b4f  pop     r14
0x1800f0b51  pop     rdi
0x1800f0b52  pop     rsi
0x1800f0b53  pop     rbp
0x1800f0b54  retn
```
