# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800119d4`
- end: `0x180011c8a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001258c`

## callees

- `0x1800119d4`
- `0x180012888`
- `0x18001ecee`
- `0x18001ed20`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180011b06`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180011b06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011b87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011b87`

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
          v8 = (const char *)&qword_180021E18;
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
0x1800119d4  mov     [rsp+arg_18], rbx
0x1800119d9  push    rbp
0x1800119da  push    rsi
0x1800119db  push    rdi
0x1800119dc  push    r14
0x1800119de  push    r15
0x1800119e0  sub     rsp, 250h
0x1800119e7  mov     rax, cs:__security_cookie
0x1800119ee  xor     rax, rsp
0x1800119f1  mov     [rsp+278h+var_38], rax
0x1800119f9  xor     r15d, r15d
0x1800119fc  mov     rbx, r8
0x1800119ff  mov     rsi, rdx
0x180011a02  mov     r14, rcx
0x180011a05  test    rdx, rdx
0x180011a08  jz      loc_180011C61
0x180011a0e  test    rcx, rcx
0x180011a11  jz      loc_180011C61
0x180011a17  mov     rax, cs:g_pfnResultLoggingCallback
0x180011a1e  mov     [rcx], r15w
0x180011a22  test    rax, rax
0x180011a25  jz      short loc_180011A48
0x180011a27  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180011a2e  jz      short loc_180011A48
0x180011a30  mov     r8, rdx
0x180011a33  mov     rdx, rcx
0x180011a36  mov     rcx, rbx
0x180011a39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a3e  cmp     [r14], r15w
0x180011a42  jnz     loc_180011C61
0x180011a48  mov     ecx, [rbx]
0x180011a4a  mov     bpl, 8
0x180011a4d  test    ecx, ecx
0x180011a4f  jz      short loc_180011A9A
0x180011a51  sub     ecx, 1
0x180011a54  jz      short loc_180011A82
0x180011a56  sub     ecx, 1
0x180011a59  jz      short loc_180011A72
0x180011a5b  cmp     ecx, 1
0x180011a5e  jz      short loc_180011A69
0x180011a60  lea     rdi, qword_180021E18
0x180011a67  jmp     short loc_180011AA1
0x180011a69  lea     rdi, aFailfast; "FailFast"
0x180011a70  jmp     short loc_180011AA1
0x180011a72  lea     rax, aLoghr; "LogHr"
0x180011a79  lea     rdi, aLognt; "LogNt"
0x180011a80  jmp     short loc_180011A90
0x180011a82  lea     rax, aReturnhr; "ReturnHr"
0x180011a89  lea     rdi, aReturnnt; "ReturnNt"
0x180011a90  test    [rbx+4], bpl
0x180011a94  cmovz   rdi, rax
0x180011a98  jmp     short loc_180011AA1
0x180011a9a  lea     rdi, aException; "Exception"
0x180011aa1  xor     edx, edx; Val
0x180011aa3  lea     rcx, [rsp+278h+Buffer]; void *
0x180011aa8  mov     r8d, 200h; Size
0x180011aae  call    memset_0
0x180011ab3  test    [rbx+4], bpl
0x180011ab7  jz      short loc_180011ADC
0x180011ab9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180011ac0  mov     ebp, [rbx+0Ch]
0x180011ac3  test    rax, rax
0x180011ac6  jz      short loc_180011B0C
0x180011ac8  mov     r8d, 100h
0x180011ace  lea     rdx, [rsp+278h+Buffer]
0x180011ad3  mov     ecx, ebp
0x180011ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ada  jmp     short loc_180011B0C
0x180011adc  mov     ebp, [rbx+8]
0x180011adf  lea     rax, [rsp+278h+Buffer]
0x180011ae4  mov     [rsp+278h+Arguments], r15; Arguments
0x180011ae9  mov     r8d, ebp; dwMessageId
0x180011aec  mov     [rsp+278h+nSize], 100h; nSize
0x180011af4  mov     r9d, 400h; dwLanguageId
0x180011afa  xor     edx, edx; lpSource
0x180011afc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180011b01  mov     ecx, 1200h; dwFlags
0x180011b06  call    cs:__imp_FormatMessageW
0x180011b0c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180011b10  lea     rsi, [r14+rsi*2]
0x180011b14  mov     rax, [rbx+88h]
0x180011b1b  mov     rdx, rsi; unsigned __int16 *
0x180011b1e  mov     rcx, [rbx+80h]
0x180011b25  test    r9, r9
0x180011b28  jz      short loc_180011B4C
0x180011b2a  mov     [rsp+278h+Arguments], rax
0x180011b2f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180011b36  mov     eax, [rbx+40h]
0x180011b39  mov     qword ptr [rsp+278h+nSize], rcx
0x180011b3e  mov     rcx, r14; pszDest
0x180011b41  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180011b45  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011b4a  jmp     short loc_180011B63
0x180011b4c  mov     r9, rcx; unsigned __int16 *
0x180011b4f  mov     [rsp+278h+lpBuffer], rax
0x180011b54  mov     rcx, r14; pszDest
0x180011b57  lea     r8, aHsP; "%hs!%p: "
0x180011b5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011b63  mov     r9, [rbx+90h]; unsigned __int16 *
0x180011b6a  mov     r14, rax
0x180011b6d  test    r9, r9
0x180011b70  jz      short loc_180011B87
0x180011b72  lea     r8, aCallerP; "(caller: %p) "
0x180011b79  mov     rdx, rsi; unsigned __int16 *
0x180011b7c  mov     rcx, rax; pszDest
0x180011b7f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011b84  mov     r14, rax
0x180011b87  call    cs:__imp_GetCurrentThreadId
0x180011b8d  lea     rcx, [rsp+278h+Buffer]
0x180011b92  mov     r9, rdi; unsigned __int16 *
0x180011b95  mov     [rsp+278h+var_240], rcx
0x180011b9a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180011ba1  mov     dword ptr [rsp+278h+Arguments], ebp
0x180011ba5  mov     rdx, rsi; unsigned __int16 *
0x180011ba8  mov     [rsp+278h+nSize], eax
0x180011bac  mov     rcx, r14; pszDest
0x180011baf  mov     eax, [rbx+44h]
0x180011bb2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180011bb6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011bbb  cmp     [rbx+18h], r15
0x180011bbf  jnz     short loc_180011BD1
0x180011bc1  cmp     [rbx+48h], r15
0x180011bc5  jnz     short loc_180011BD1
0x180011bc7  cmp     [rbx+30h], r15
0x180011bcb  jz      loc_180011C61
0x180011bd1  lea     r8, asc_180021F08; "    "
0x180011bd8  mov     rdx, rsi; unsigned __int16 *
0x180011bdb  mov     rcx, rax; pszDest
0x180011bde  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011be3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180011be7  test    r9, r9
0x180011bea  jz      short loc_180011BFE
0x180011bec  lea     r8, aMsgWs; "Msg:[%ws] "
0x180011bf3  mov     rdx, rsi; unsigned __int16 *
0x180011bf6  mov     rcx, rax; pszDest
0x180011bf9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011bfe  mov     r9, [rbx+48h]; unsigned __int16 *
0x180011c02  test    r9, r9
0x180011c05  jz      short loc_180011C19
0x180011c07  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180011c0e  mov     rdx, rsi; unsigned __int16 *
0x180011c11  mov     rcx, rax; pszDest
0x180011c14  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011c19  mov     rcx, [rbx+28h]
0x180011c1d  mov     rdx, rsi; unsigned __int16 *
0x180011c20  mov     r9, [rbx+30h]; unsigned __int16 *
0x180011c24  test    rcx, rcx
0x180011c27  jz      short loc_180011C3F
0x180011c29  mov     [rsp+278h+lpBuffer], rcx
0x180011c2e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180011c35  mov     rcx, rax; pszDest
0x180011c38  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011c3d  jmp     short loc_180011C61
0x180011c3f  mov     rcx, rax; pszDest
0x180011c42  test    r9, r9
0x180011c45  jz      short loc_180011C55
0x180011c47  lea     r8, aHs; "[%hs]\n"
0x180011c4e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011c53  jmp     short loc_180011C61
0x180011c55  lea     r8, asc_180021F80; "\n"
0x180011c5c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011c61  xor     eax, eax
0x180011c63  mov     rcx, [rsp+278h+var_38]
0x180011c6b  xor     rcx, rsp; StackCookie
0x180011c6e  call    __security_check_cookie
0x180011c73  mov     rbx, [rsp+278h+arg_18]
0x180011c7b  add     rsp, 250h
0x180011c82  pop     r15
0x180011c84  pop     r14
0x180011c86  pop     rdi
0x180011c87  pop     rsi
0x180011c88  pop     rbp
0x180011c89  retn
```
