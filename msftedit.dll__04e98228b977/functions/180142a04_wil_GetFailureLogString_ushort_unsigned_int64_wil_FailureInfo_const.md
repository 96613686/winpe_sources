# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180142a04`
- end: `0x180142cc7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1801410bc`
- `0x180143488`
- `0x18027d700`

## callees

- `0x18013ce80`
- `0x18013dce6`
- `0x180142a04`
- `0x18014379c`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180142bbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180142bbd`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180142b36`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180142b36`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        STRSAFE_LPWSTR pszDest,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, STRSAFE_LPWSTR, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rdi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rsi
  __int64 v13; // rax
  wchar_t *v14; // rax
  const unsigned __int16 *v15; // r9
  wchar_t *v16; // r14
  wchar_t *v17; // rax
  const unsigned __int16 *v18; // r9
  wchar_t *v19; // rax
  const unsigned __int16 *v20; // r9
  const unsigned __int16 *v21; // r9
  const unsigned __int16 *v22; // r9
  LPWSTR lpBuffer; // [rsp+20h] [rbp-258h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-258h]
  DWORD nSize[2]; // [rsp+28h] [rbp-250h]
  va_list *Arguments; // [rsp+30h] [rbp-248h]
  WCHAR Buffer[256]; // [rsp+40h] [rbp-238h] BYREF

  if ( !a2 )
    return 0;
  if ( !pszDest )
    return 0;
  v7 = (void (__fastcall *)(__int64, STRSAFE_LPWSTR, unsigned __int16 *, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
  *pszDest = 0;
  if ( v7 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      v7(a3, pszDest, a2, a4);
      if ( *pszDest )
        return 0;
    }
  }
  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      v9 = "ReturnHr";
      v8 = "ReturnNt";
    }
    else
    {
      if ( *(_DWORD *)a3 != 2 )
      {
        if ( *(_DWORD *)a3 == 3 )
          v8 = "FailFast";
        else
          v8 = &byte_1802AD8C7;
        goto LABEL_18;
      }
      v9 = "LogHr";
      v8 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v8 = v9;
    goto LABEL_18;
  }
  v8 = "Exception";
LABEL_18:
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
  {
    v10 = *(_DWORD *)(a3 + 12);
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(v10, Buffer, 0x100u);
  }
  else
  {
    v10 = *(_DWORD *)(a3 + 8);
    FormatMessageW(0x1200u, 0, v10, 0x400u, Buffer, 0x100u, 0);
  }
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = &pszDest[(_QWORD)a2];
  v13 = *(_QWORD *)(a3 + 136);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(pszDest, v12, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, *(_QWORD *)(a3 + 128), v13);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(pszDest, v12, L"%hs!%p: ", *(const unsigned __int16 **)(a3 + 128), v13);
  }
  v15 = *(const unsigned __int16 **)(a3 + 144);
  v16 = v14;
  if ( v15 )
    v16 = wil::details::LogStringPrintf(v14, v12, L"(caller: %p) ", v15);
  LODWORD(Arguments) = v10;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = wil::details::LogStringPrintf(
          v16,
          v12,
          L"%hs(%d) tid(%x) %08X %ws",
          (const unsigned __int16 *)v8,
          lpBuffera,
          *(_QWORD *)nSize,
          Arguments,
          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v12, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf(v19, v12, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf(v19, v12, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf(v19, v12, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf(v19, v12, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf(v19, v12, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180142a04  mov     [rsp+arg_18], rbx
0x180142a09  push    rbp
0x180142a0a  push    rsi
0x180142a0b  push    rdi
0x180142a0c  push    r14
0x180142a0e  push    r15
0x180142a10  sub     rsp, 250h
0x180142a17  mov     rax, cs:__security_cookie
0x180142a1e  xor     rax, rsp
0x180142a21  mov     [rsp+278h+var_38], rax
0x180142a29  xor     r15d, r15d
0x180142a2c  mov     rbx, r8
0x180142a2f  mov     rsi, rdx
0x180142a32  mov     r14, rcx
0x180142a35  test    rdx, rdx
0x180142a38  jz      loc_180142C9D
0x180142a3e  test    rcx, rcx
0x180142a41  jz      loc_180142C9D
0x180142a47  mov     rax, cs:g_pfnResultLoggingCallback
0x180142a4e  mov     [rcx], r15w
0x180142a52  test    rax, rax
0x180142a55  jz      short loc_180142A78
0x180142a57  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180142a5e  jz      short loc_180142A78
0x180142a60  mov     r8, rdx
0x180142a63  mov     rdx, rcx
0x180142a66  mov     rcx, rbx
0x180142a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180142a6e  cmp     [r14], r15w
0x180142a72  jnz     loc_180142C9D
0x180142a78  mov     ecx, [rbx]
0x180142a7a  mov     bpl, 8
0x180142a7d  test    ecx, ecx
0x180142a7f  jz      short loc_180142ACA
0x180142a81  sub     ecx, 1
0x180142a84  jz      short loc_180142AB2
0x180142a86  sub     ecx, 1
0x180142a89  jz      short loc_180142AA2
0x180142a8b  cmp     ecx, 1
0x180142a8e  jz      short loc_180142A99
0x180142a90  lea     rdi, byte_1802AD8C7
0x180142a97  jmp     short loc_180142AD1
0x180142a99  lea     rdi, aFailfast; "FailFast"
0x180142aa0  jmp     short loc_180142AD1
0x180142aa2  lea     rax, aLoghr; "LogHr"
0x180142aa9  lea     rdi, aLognt; "LogNt"
0x180142ab0  jmp     short loc_180142AC0
0x180142ab2  lea     rax, aReturnhr; "ReturnHr"
0x180142ab9  lea     rdi, aReturnnt; "ReturnNt"
0x180142ac0  test    [rbx+4], bpl
0x180142ac4  cmovz   rdi, rax
0x180142ac8  jmp     short loc_180142AD1
0x180142aca  lea     rdi, aException; "Exception"
0x180142ad1  xor     edx, edx; Val
0x180142ad3  lea     rcx, [rsp+278h+Buffer]; void *
0x180142ad8  mov     r8d, 200h; Size
0x180142ade  call    memset_0
0x180142ae3  test    [rbx+4], bpl
0x180142ae7  jz      short loc_180142B0C
0x180142ae9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180142af0  mov     ebp, [rbx+0Ch]
0x180142af3  test    rax, rax
0x180142af6  jz      short loc_180142B42
0x180142af8  mov     r8d, 100h
0x180142afe  lea     rdx, [rsp+278h+Buffer]
0x180142b03  mov     ecx, ebp
0x180142b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180142b0a  jmp     short loc_180142B42
0x180142b0c  mov     ebp, [rbx+8]
0x180142b0f  lea     rax, [rsp+278h+Buffer]
0x180142b14  mov     [rsp+278h+Arguments], r15; Arguments
0x180142b19  mov     r8d, ebp; dwMessageId
0x180142b1c  mov     [rsp+278h+nSize], 100h; nSize
0x180142b24  mov     r9d, 400h; dwLanguageId
0x180142b2a  xor     edx, edx; lpSource
0x180142b2c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180142b31  mov     ecx, 1200h; dwFlags
0x180142b36  call    cs:__imp_FormatMessageW
0x180142b3d  nop     dword ptr [rax+rax+00h]
0x180142b42  mov     r9, [rbx+38h]; unsigned __int16 *
0x180142b46  lea     rsi, [r14+rsi*2]
0x180142b4a  mov     rax, [rbx+88h]
0x180142b51  mov     rdx, rsi; unsigned __int16 *
0x180142b54  mov     rcx, [rbx+80h]
0x180142b5b  test    r9, r9
0x180142b5e  jz      short loc_180142B82
0x180142b60  mov     [rsp+278h+Arguments], rax
0x180142b65  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180142b6c  mov     eax, [rbx+40h]
0x180142b6f  mov     qword ptr [rsp+278h+nSize], rcx
0x180142b74  mov     rcx, r14; pszDest
0x180142b77  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180142b7b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180142b80  jmp     short loc_180142B99
0x180142b82  mov     r9, rcx; unsigned __int16 *
0x180142b85  mov     [rsp+278h+lpBuffer], rax
0x180142b8a  mov     rcx, r14; pszDest
0x180142b8d  lea     r8, aHsP; "%hs!%p: "
0x180142b94  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180142b99  mov     r9, [rbx+90h]; unsigned __int16 *
0x180142ba0  mov     r14, rax
0x180142ba3  test    r9, r9
0x180142ba6  jz      short loc_180142BBD
0x180142ba8  lea     r8, aCallerP; "(caller: %p) "
0x180142baf  mov     rdx, rsi; unsigned __int16 *
0x180142bb2  mov     rcx, rax; pszDest
0x180142bb5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180142bba  mov     r14, rax
0x180142bbd  call    cs:__imp_GetCurrentThreadId
0x180142bc4  nop     dword ptr [rax+rax+00h]
0x180142bc9  lea     rcx, [rsp+278h+Buffer]
0x180142bce  mov     r9, rdi; unsigned __int16 *
0x180142bd1  mov     [rsp+278h+var_240], rcx
0x180142bd6  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180142bdd  mov     dword ptr [rsp+278h+Arguments], ebp
0x180142be1  mov     rdx, rsi; unsigned __int16 *
0x180142be4  mov     [rsp+278h+nSize], eax
0x180142be8  mov     rcx, r14; pszDest
0x180142beb  mov     eax, [rbx+44h]
0x180142bee  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180142bf2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180142bf7  cmp     [rbx+18h], r15
0x180142bfb  jnz     short loc_180142C0D
0x180142bfd  cmp     [rbx+48h], r15
0x180142c01  jnz     short loc_180142C0D
0x180142c03  cmp     [rbx+30h], r15
0x180142c07  jz      loc_180142C9D
0x180142c0d  lea     r8, asc_1802AD9B0; "    "
0x180142c14  mov     rdx, rsi; unsigned __int16 *
0x180142c17  mov     rcx, rax; pszDest
0x180142c1a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180142c1f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180142c23  test    r9, r9
0x180142c26  jz      short loc_180142C3A
0x180142c28  lea     r8, aMsgWs; "Msg:[%ws] "
0x180142c2f  mov     rdx, rsi; unsigned __int16 *
0x180142c32  mov     rcx, rax; pszDest
0x180142c35  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180142c3a  mov     r9, [rbx+48h]; unsigned __int16 *
0x180142c3e  test    r9, r9
0x180142c41  jz      short loc_180142C55
0x180142c43  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180142c4a  mov     rdx, rsi; unsigned __int16 *
0x180142c4d  mov     rcx, rax; pszDest
0x180142c50  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180142c55  mov     rcx, [rbx+28h]
0x180142c59  mov     rdx, rsi; unsigned __int16 *
0x180142c5c  mov     r9, [rbx+30h]; unsigned __int16 *
0x180142c60  test    rcx, rcx
0x180142c63  jz      short loc_180142C7B
0x180142c65  mov     [rsp+278h+lpBuffer], rcx
0x180142c6a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180142c71  mov     rcx, rax; pszDest
0x180142c74  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180142c79  jmp     short loc_180142C9D
0x180142c7b  mov     rcx, rax; pszDest
0x180142c7e  test    r9, r9
0x180142c81  jz      short loc_180142C91
0x180142c83  lea     r8, aHs; "[%hs]\n"
0x180142c8a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180142c8f  jmp     short loc_180142C9D
0x180142c91  lea     r8, asc_1802ADA28; "\n"
0x180142c98  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180142c9d  xor     eax, eax
0x180142c9f  mov     rcx, [rsp+278h+var_38]
0x180142ca7  xor     rcx, rsp; StackCookie
0x180142caa  call    __security_check_cookie
0x180142caf  mov     rbx, [rsp+278h+arg_18]
0x180142cb7  add     rsp, 250h
0x180142cbe  pop     r15
0x180142cc0  pop     r14
0x180142cc2  pop     rdi
0x180142cc3  pop     rsi
0x180142cc4  pop     rbp
0x180142cc5  retn
```
