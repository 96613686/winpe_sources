# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180002ad4`
- end: `0x180002d8a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180003730`
- `0x1800054d0`
- `0x180008c30`

## callees

- `0x1800017a0`
- `0x18000213c`
- `0x180002ad4`
- `0x18000308c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002c87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002c87`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180002c06`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180002c06`

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
          v7 = (const char *)&word_180038EEA;
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
0x180002ad4  mov     [rsp+arg_18], rbx
0x180002ad9  push    rbp
0x180002ada  push    rsi
0x180002adb  push    rdi
0x180002adc  push    r14
0x180002ade  push    r15
0x180002ae0  sub     rsp, 250h
0x180002ae7  mov     rax, cs:__security_cookie
0x180002aee  xor     rax, rsp
0x180002af1  mov     [rsp+278h+var_38], rax
0x180002af9  mov     rbx, r8
0x180002afc  mov     rsi, rdx
0x180002aff  mov     r14, rcx
0x180002b02  xor     r15d, r15d
0x180002b05  test    rdx, rdx
0x180002b08  jz      loc_180002D61
0x180002b0e  test    rcx, rcx
0x180002b11  jz      loc_180002D61
0x180002b17  mov     [rcx], r15w
0x180002b1b  mov     rax, cs:g_pfnResultLoggingCallback
0x180002b22  test    rax, rax
0x180002b25  jz      short loc_180002B48
0x180002b27  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002b2e  jz      short loc_180002B48
0x180002b30  mov     r8, rdx
0x180002b33  mov     rdx, rcx
0x180002b36  mov     rcx, rbx
0x180002b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b3e  cmp     [r14], r15w
0x180002b42  jnz     loc_180002D61
0x180002b48  mov     ecx, [rbx]
0x180002b4a  mov     bpl, 8
0x180002b4d  test    ecx, ecx
0x180002b4f  jz      short loc_180002B9A
0x180002b51  sub     ecx, 1
0x180002b54  jz      short loc_180002B82
0x180002b56  sub     ecx, 1
0x180002b59  jz      short loc_180002B72
0x180002b5b  cmp     ecx, 1
0x180002b5e  jz      short loc_180002B69
0x180002b60  lea     rdi, word_180038EEA
0x180002b67  jmp     short loc_180002BA1
0x180002b69  lea     rdi, aFailfast; "FailFast"
0x180002b70  jmp     short loc_180002BA1
0x180002b72  lea     rax, aLoghr; "LogHr"
0x180002b79  lea     rdi, aLognt; "LogNt"
0x180002b80  jmp     short loc_180002B90
0x180002b82  lea     rax, aReturnhr; "ReturnHr"
0x180002b89  lea     rdi, aReturnnt; "ReturnNt"
0x180002b90  test    [rbx+4], bpl
0x180002b94  cmovz   rdi, rax
0x180002b98  jmp     short loc_180002BA1
0x180002b9a  lea     rdi, aException; "Exception"
0x180002ba1  xor     edx, edx; Val
0x180002ba3  mov     r8d, 200h; Size
0x180002ba9  lea     rcx, [rsp+278h+Buffer]; void *
0x180002bae  call    memset_0
0x180002bb3  test    [rbx+4], bpl
0x180002bb7  jz      short loc_180002BDC
0x180002bb9  mov     ebp, [rbx+0Ch]
0x180002bbc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180002bc3  test    rax, rax
0x180002bc6  jz      short loc_180002C0C
0x180002bc8  mov     r8d, 100h
0x180002bce  lea     rdx, [rsp+278h+Buffer]
0x180002bd3  mov     ecx, ebp
0x180002bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bda  jmp     short loc_180002C0C
0x180002bdc  mov     ebp, [rbx+8]
0x180002bdf  mov     [rsp+278h+Arguments], r15; Arguments
0x180002be4  mov     [rsp+278h+nSize], 100h; nSize
0x180002bec  lea     rax, [rsp+278h+Buffer]
0x180002bf1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180002bf6  mov     r9d, 400h; dwLanguageId
0x180002bfc  mov     r8d, ebp; dwMessageId
0x180002bff  xor     edx, edx; lpSource
0x180002c01  mov     ecx, 1200h; dwFlags
0x180002c06  call    cs:__imp_FormatMessageW
0x180002c0c  lea     rsi, [r14+rsi*2]
0x180002c10  mov     r9, [rbx+38h]; wchar_t *
0x180002c14  mov     rax, [rbx+88h]
0x180002c1b  mov     rcx, [rbx+80h]
0x180002c22  mov     rdx, rsi; wchar_t *
0x180002c25  test    r9, r9
0x180002c28  jz      short loc_180002C4C
0x180002c2a  mov     [rsp+278h+Arguments], rax
0x180002c2f  mov     qword ptr [rsp+278h+nSize], rcx
0x180002c34  mov     eax, [rbx+40h]
0x180002c37  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180002c3b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180002c42  mov     rcx, r14; this
0x180002c45  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002c4a  jmp     short loc_180002C63
0x180002c4c  mov     [rsp+278h+lpBuffer], rax
0x180002c51  mov     r9, rcx; wchar_t *
0x180002c54  lea     r8, aHsP; "%hs!%p: "
0x180002c5b  mov     rcx, r14; this
0x180002c5e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002c63  mov     r14, rax
0x180002c66  mov     r9, [rbx+90h]; wchar_t *
0x180002c6d  test    r9, r9
0x180002c70  jz      short loc_180002C87
0x180002c72  lea     r8, aCallerP; "(caller: %p) "
0x180002c79  mov     rdx, rsi; wchar_t *
0x180002c7c  mov     rcx, rax; this
0x180002c7f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002c84  mov     r14, rax
0x180002c87  call    cs:__imp_GetCurrentThreadId
0x180002c8d  lea     rcx, [rsp+278h+Buffer]
0x180002c92  mov     [rsp+278h+var_240], rcx
0x180002c97  mov     dword ptr [rsp+278h+Arguments], ebp
0x180002c9b  mov     [rsp+278h+nSize], eax
0x180002c9f  mov     eax, [rbx+44h]
0x180002ca2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180002ca6  mov     r9, rdi; wchar_t *
0x180002ca9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180002cb0  mov     rdx, rsi; wchar_t *
0x180002cb3  mov     rcx, r14; this
0x180002cb6  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002cbb  cmp     [rbx+18h], r15
0x180002cbf  jnz     short loc_180002CD1
0x180002cc1  cmp     [rbx+48h], r15
0x180002cc5  jnz     short loc_180002CD1
0x180002cc7  cmp     [rbx+30h], r15
0x180002ccb  jz      loc_180002D61
0x180002cd1  lea     r8, asc_180038FD8; "    "
0x180002cd8  mov     rdx, rsi; wchar_t *
0x180002cdb  mov     rcx, rax; this
0x180002cde  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002ce3  mov     r9, [rbx+18h]; wchar_t *
0x180002ce7  test    r9, r9
0x180002cea  jz      short loc_180002CFE
0x180002cec  lea     r8, aMsgWs; "Msg:[%ws] "
0x180002cf3  mov     rdx, rsi; wchar_t *
0x180002cf6  mov     rcx, rax; this
0x180002cf9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002cfe  mov     r9, [rbx+48h]; wchar_t *
0x180002d02  test    r9, r9
0x180002d05  jz      short loc_180002D19
0x180002d07  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180002d0e  mov     rdx, rsi; wchar_t *
0x180002d11  mov     rcx, rax; this
0x180002d14  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002d19  mov     rcx, [rbx+28h]
0x180002d1d  mov     r9, [rbx+30h]; wchar_t *
0x180002d21  mov     rdx, rsi; wchar_t *
0x180002d24  test    rcx, rcx
0x180002d27  jz      short loc_180002D3F
0x180002d29  mov     [rsp+278h+lpBuffer], rcx
0x180002d2e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180002d35  mov     rcx, rax; this
0x180002d38  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002d3d  jmp     short loc_180002D61
0x180002d3f  mov     rcx, rax; this
0x180002d42  test    r9, r9
0x180002d45  jz      short loc_180002D55
0x180002d47  lea     r8, aHs; "[%hs]\n"
0x180002d4e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002d53  jmp     short loc_180002D61
0x180002d55  lea     r8, asc_180039050; "\n"
0x180002d5c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002d61  xor     eax, eax
0x180002d63  mov     rcx, [rsp+278h+var_38]
0x180002d6b  xor     rcx, rsp; StackCookie
0x180002d6e  call    __security_check_cookie
0x180002d73  mov     rbx, [rsp+278h+arg_18]
0x180002d7b  add     rsp, 250h
0x180002d82  pop     r15
0x180002d84  pop     r14
0x180002d86  pop     rdi
0x180002d87  pop     rsi
0x180002d88  pop     rbp
0x180002d89  retn
```
