# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004bd4`
- end: `0x180004e8a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180003218`
- `0x1800034ec`
- `0x180003780`

## callees

- `0x180001550`
- `0x180002158`
- `0x180004bd4`
- `0x1800059c4`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d87`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004d06`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004d06`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  unsigned __int16 *v10; // rsi
  const unsigned __int16 *v11; // r9
  __int64 v12; // rax
  const unsigned __int16 *v13; // rcx
  unsigned __int16 *v14; // rax
  wil::details *v15; // r14
  const unsigned __int16 *v16; // r9
  wil::details *v17; // rax
  const unsigned __int16 *v18; // r9
  unsigned __int16 *v19; // rax
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
          v7 = (const char *)&qword_1800149E0;
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
  v10 = (unsigned __int16 *)((char *)this + 2 * (_QWORD)a2);
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const unsigned __int16 **)(a3 + 128);
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
  v16 = *(const unsigned __int16 **)(a3 + 144);
  if ( v16 )
    v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v15,
                          v10,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const unsigned __int16 *)v7,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v10, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
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
0x180004bd4  mov     [rsp+arg_18], rbx
0x180004bd9  push    rbp
0x180004bda  push    rsi
0x180004bdb  push    rdi
0x180004bdc  push    r14
0x180004bde  push    r15
0x180004be0  sub     rsp, 250h
0x180004be7  mov     rax, cs:__security_cookie
0x180004bee  xor     rax, rsp
0x180004bf1  mov     [rsp+278h+var_38], rax
0x180004bf9  mov     rbx, r8
0x180004bfc  mov     rsi, rdx
0x180004bff  mov     r14, rcx
0x180004c02  xor     r15d, r15d
0x180004c05  test    rdx, rdx
0x180004c08  jz      loc_180004E61
0x180004c0e  test    rcx, rcx
0x180004c11  jz      loc_180004E61
0x180004c17  mov     [rcx], r15w
0x180004c1b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004c22  test    rax, rax
0x180004c25  jz      short loc_180004C48
0x180004c27  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004c2e  jz      short loc_180004C48
0x180004c30  mov     r8, rdx
0x180004c33  mov     rdx, rcx
0x180004c36  mov     rcx, rbx
0x180004c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c3e  cmp     [r14], r15w
0x180004c42  jnz     loc_180004E61
0x180004c48  mov     ecx, [rbx]
0x180004c4a  mov     bpl, 8
0x180004c4d  test    ecx, ecx
0x180004c4f  jz      short loc_180004C9A
0x180004c51  sub     ecx, 1
0x180004c54  jz      short loc_180004C82
0x180004c56  sub     ecx, 1
0x180004c59  jz      short loc_180004C72
0x180004c5b  cmp     ecx, 1
0x180004c5e  jz      short loc_180004C69
0x180004c60  lea     rdi, qword_1800149E0
0x180004c67  jmp     short loc_180004CA1
0x180004c69  lea     rdi, aFailfast; "FailFast"
0x180004c70  jmp     short loc_180004CA1
0x180004c72  lea     rax, aLoghr; "LogHr"
0x180004c79  lea     rdi, aLognt; "LogNt"
0x180004c80  jmp     short loc_180004C90
0x180004c82  lea     rax, aReturnhr; "ReturnHr"
0x180004c89  lea     rdi, aReturnnt; "ReturnNt"
0x180004c90  test    [rbx+4], bpl
0x180004c94  cmovz   rdi, rax
0x180004c98  jmp     short loc_180004CA1
0x180004c9a  lea     rdi, aException; "Exception"
0x180004ca1  xor     edx, edx; Val
0x180004ca3  mov     r8d, 200h; Size
0x180004ca9  lea     rcx, [rsp+278h+Buffer]; void *
0x180004cae  call    memset_0
0x180004cb3  test    [rbx+4], bpl
0x180004cb7  jz      short loc_180004CDC
0x180004cb9  mov     ebp, [rbx+0Ch]
0x180004cbc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004cc3  test    rax, rax
0x180004cc6  jz      short loc_180004D0C
0x180004cc8  mov     r8d, 100h
0x180004cce  lea     rdx, [rsp+278h+Buffer]
0x180004cd3  mov     ecx, ebp
0x180004cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cda  jmp     short loc_180004D0C
0x180004cdc  mov     ebp, [rbx+8]
0x180004cdf  mov     [rsp+278h+Arguments], r15; Arguments
0x180004ce4  mov     [rsp+278h+nSize], 100h; nSize
0x180004cec  lea     rax, [rsp+278h+Buffer]
0x180004cf1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004cf6  mov     r9d, 400h; dwLanguageId
0x180004cfc  mov     r8d, ebp; dwMessageId
0x180004cff  xor     edx, edx; lpSource
0x180004d01  mov     ecx, 1200h; dwFlags
0x180004d06  call    cs:__imp_FormatMessageW
0x180004d0c  lea     rsi, [r14+rsi*2]
0x180004d10  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004d14  mov     rax, [rbx+88h]
0x180004d1b  mov     rcx, [rbx+80h]
0x180004d22  mov     rdx, rsi; unsigned __int16 *
0x180004d25  test    r9, r9
0x180004d28  jz      short loc_180004D4C
0x180004d2a  mov     [rsp+278h+Arguments], rax
0x180004d2f  mov     qword ptr [rsp+278h+nSize], rcx
0x180004d34  mov     eax, [rbx+40h]
0x180004d37  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004d3b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004d42  mov     rcx, r14; this
0x180004d45  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004d4a  jmp     short loc_180004D63
0x180004d4c  mov     [rsp+278h+lpBuffer], rax
0x180004d51  mov     r9, rcx; unsigned __int16 *
0x180004d54  lea     r8, aHsP; "%hs!%p: "
0x180004d5b  mov     rcx, r14; this
0x180004d5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004d63  mov     r14, rax
0x180004d66  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004d6d  test    r9, r9
0x180004d70  jz      short loc_180004D87
0x180004d72  lea     r8, aCallerP; "(caller: %p) "
0x180004d79  mov     rdx, rsi; unsigned __int16 *
0x180004d7c  mov     rcx, rax; this
0x180004d7f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004d84  mov     r14, rax
0x180004d87  call    cs:__imp_GetCurrentThreadId
0x180004d8d  lea     rcx, [rsp+278h+Buffer]
0x180004d92  mov     [rsp+278h+var_240], rcx
0x180004d97  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004d9b  mov     [rsp+278h+nSize], eax
0x180004d9f  mov     eax, [rbx+44h]
0x180004da2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004da6  mov     r9, rdi; unsigned __int16 *
0x180004da9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004db0  mov     rdx, rsi; unsigned __int16 *
0x180004db3  mov     rcx, r14; this
0x180004db6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004dbb  cmp     [rbx+18h], r15
0x180004dbf  jnz     short loc_180004DD1
0x180004dc1  cmp     [rbx+48h], r15
0x180004dc5  jnz     short loc_180004DD1
0x180004dc7  cmp     [rbx+30h], r15
0x180004dcb  jz      loc_180004E61
0x180004dd1  lea     r8, asc_180014AD0; "    "
0x180004dd8  mov     rdx, rsi; unsigned __int16 *
0x180004ddb  mov     rcx, rax; this
0x180004dde  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004de3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004de7  test    r9, r9
0x180004dea  jz      short loc_180004DFE
0x180004dec  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004df3  mov     rdx, rsi; unsigned __int16 *
0x180004df6  mov     rcx, rax; this
0x180004df9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004dfe  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004e02  test    r9, r9
0x180004e05  jz      short loc_180004E19
0x180004e07  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180004e0e  mov     rdx, rsi; unsigned __int16 *
0x180004e11  mov     rcx, rax; this
0x180004e14  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004e19  mov     rcx, [rbx+28h]
0x180004e1d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004e21  mov     rdx, rsi; unsigned __int16 *
0x180004e24  test    rcx, rcx
0x180004e27  jz      short loc_180004E3F
0x180004e29  mov     [rsp+278h+lpBuffer], rcx
0x180004e2e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004e35  mov     rcx, rax; this
0x180004e38  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004e3d  jmp     short loc_180004E61
0x180004e3f  mov     rcx, rax; this
0x180004e42  test    r9, r9
0x180004e45  jz      short loc_180004E55
0x180004e47  lea     r8, aHs; "[%hs]\n"
0x180004e4e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004e53  jmp     short loc_180004E61
0x180004e55  lea     r8, asc_180014B48; "\n"
0x180004e5c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004e61  xor     eax, eax
0x180004e63  mov     rcx, [rsp+278h+var_38]
0x180004e6b  xor     rcx, rsp; StackCookie
0x180004e6e  call    __security_check_cookie
0x180004e73  mov     rbx, [rsp+278h+arg_18]
0x180004e7b  add     rsp, 250h
0x180004e82  pop     r15
0x180004e84  pop     r14
0x180004e86  pop     rdi
0x180004e87  pop     rsi
0x180004e88  pop     rbp
0x180004e89  retn
```
