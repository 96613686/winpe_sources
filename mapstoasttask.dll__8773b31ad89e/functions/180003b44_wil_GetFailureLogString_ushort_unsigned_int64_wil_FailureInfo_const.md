# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180003b44`
- end: `0x180003dfa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x180006b00`
- `0x1800070a4`
- `0x1800075f0`
- `0x180007c24`
- `0x1800098cf`
- `0x180009a03`

## callees

- `0x1800015b0`
- `0x180001fe2`
- `0x180003b44`
- `0x180004310`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003cf7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003cf7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003c76`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003c76`

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
          v7 = (const char *)&qword_18000B9E0;
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
0x180003b44  mov     [rsp+arg_18], rbx
0x180003b49  push    rbp
0x180003b4a  push    rsi
0x180003b4b  push    rdi
0x180003b4c  push    r14
0x180003b4e  push    r15
0x180003b50  sub     rsp, 250h
0x180003b57  mov     rax, cs:__security_cookie
0x180003b5e  xor     rax, rsp
0x180003b61  mov     [rsp+278h+var_38], rax
0x180003b69  mov     rbx, r8
0x180003b6c  mov     rsi, rdx
0x180003b6f  mov     r14, rcx
0x180003b72  xor     r15d, r15d
0x180003b75  test    rdx, rdx
0x180003b78  jz      loc_180003DD1
0x180003b7e  test    rcx, rcx
0x180003b81  jz      loc_180003DD1
0x180003b87  mov     [rcx], r15w
0x180003b8b  mov     rax, cs:g_pfnResultLoggingCallback
0x180003b92  test    rax, rax
0x180003b95  jz      short loc_180003BB8
0x180003b97  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003b9e  jz      short loc_180003BB8
0x180003ba0  mov     r8, rdx
0x180003ba3  mov     rdx, rcx
0x180003ba6  mov     rcx, rbx
0x180003ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bae  cmp     [r14], r15w
0x180003bb2  jnz     loc_180003DD1
0x180003bb8  mov     ecx, [rbx]
0x180003bba  mov     bpl, 8
0x180003bbd  test    ecx, ecx
0x180003bbf  jz      short loc_180003C0A
0x180003bc1  sub     ecx, 1
0x180003bc4  jz      short loc_180003BF2
0x180003bc6  sub     ecx, 1
0x180003bc9  jz      short loc_180003BE2
0x180003bcb  cmp     ecx, 1
0x180003bce  jz      short loc_180003BD9
0x180003bd0  lea     rdi, qword_18000B9E0
0x180003bd7  jmp     short loc_180003C11
0x180003bd9  lea     rdi, aFailfast; "FailFast"
0x180003be0  jmp     short loc_180003C11
0x180003be2  lea     rax, aLoghr; "LogHr"
0x180003be9  lea     rdi, aLognt; "LogNt"
0x180003bf0  jmp     short loc_180003C00
0x180003bf2  lea     rax, aReturnhr; "ReturnHr"
0x180003bf9  lea     rdi, aReturnnt; "ReturnNt"
0x180003c00  test    [rbx+4], bpl
0x180003c04  cmovz   rdi, rax
0x180003c08  jmp     short loc_180003C11
0x180003c0a  lea     rdi, aException; "Exception"
0x180003c11  xor     edx, edx; Val
0x180003c13  mov     r8d, 200h; Size
0x180003c19  lea     rcx, [rsp+278h+Buffer]; void *
0x180003c1e  call    memset_0
0x180003c23  test    [rbx+4], bpl
0x180003c27  jz      short loc_180003C4C
0x180003c29  mov     ebp, [rbx+0Ch]
0x180003c2c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180003c33  test    rax, rax
0x180003c36  jz      short loc_180003C7C
0x180003c38  mov     r8d, 100h
0x180003c3e  lea     rdx, [rsp+278h+Buffer]
0x180003c43  mov     ecx, ebp
0x180003c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c4a  jmp     short loc_180003C7C
0x180003c4c  mov     ebp, [rbx+8]
0x180003c4f  mov     [rsp+278h+Arguments], r15; Arguments
0x180003c54  mov     [rsp+278h+nSize], 100h; nSize
0x180003c5c  lea     rax, [rsp+278h+Buffer]
0x180003c61  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180003c66  mov     r9d, 400h; dwLanguageId
0x180003c6c  mov     r8d, ebp; dwMessageId
0x180003c6f  xor     edx, edx; lpSource
0x180003c71  mov     ecx, 1200h; dwFlags
0x180003c76  call    cs:__imp_FormatMessageW
0x180003c7c  lea     rsi, [r14+rsi*2]
0x180003c80  mov     r9, [rbx+38h]; unsigned __int16 *
0x180003c84  mov     rax, [rbx+88h]
0x180003c8b  mov     rcx, [rbx+80h]
0x180003c92  mov     rdx, rsi; unsigned __int16 *
0x180003c95  test    r9, r9
0x180003c98  jz      short loc_180003CBC
0x180003c9a  mov     [rsp+278h+Arguments], rax
0x180003c9f  mov     qword ptr [rsp+278h+nSize], rcx
0x180003ca4  mov     eax, [rbx+40h]
0x180003ca7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003cab  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180003cb2  mov     rcx, r14; this
0x180003cb5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003cba  jmp     short loc_180003CD3
0x180003cbc  mov     [rsp+278h+lpBuffer], rax
0x180003cc1  mov     r9, rcx; unsigned __int16 *
0x180003cc4  lea     r8, aHsP; "%hs!%p: "
0x180003ccb  mov     rcx, r14; this
0x180003cce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003cd3  mov     r14, rax
0x180003cd6  mov     r9, [rbx+90h]; unsigned __int16 *
0x180003cdd  test    r9, r9
0x180003ce0  jz      short loc_180003CF7
0x180003ce2  lea     r8, aCallerP; "(caller: %p) "
0x180003ce9  mov     rdx, rsi; unsigned __int16 *
0x180003cec  mov     rcx, rax; this
0x180003cef  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003cf4  mov     r14, rax
0x180003cf7  call    cs:__imp_GetCurrentThreadId
0x180003cfd  lea     rcx, [rsp+278h+Buffer]
0x180003d02  mov     [rsp+278h+var_240], rcx
0x180003d07  mov     dword ptr [rsp+278h+Arguments], ebp
0x180003d0b  mov     [rsp+278h+nSize], eax
0x180003d0f  mov     eax, [rbx+44h]
0x180003d12  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003d16  mov     r9, rdi; unsigned __int16 *
0x180003d19  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180003d20  mov     rdx, rsi; unsigned __int16 *
0x180003d23  mov     rcx, r14; this
0x180003d26  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003d2b  cmp     [rbx+18h], r15
0x180003d2f  jnz     short loc_180003D41
0x180003d31  cmp     [rbx+48h], r15
0x180003d35  jnz     short loc_180003D41
0x180003d37  cmp     [rbx+30h], r15
0x180003d3b  jz      loc_180003DD1
0x180003d41  lea     r8, asc_18000BB48; "    "
0x180003d48  mov     rdx, rsi; unsigned __int16 *
0x180003d4b  mov     rcx, rax; this
0x180003d4e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003d53  mov     r9, [rbx+18h]; unsigned __int16 *
0x180003d57  test    r9, r9
0x180003d5a  jz      short loc_180003D6E
0x180003d5c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180003d63  mov     rdx, rsi; unsigned __int16 *
0x180003d66  mov     rcx, rax; this
0x180003d69  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003d6e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180003d72  test    r9, r9
0x180003d75  jz      short loc_180003D89
0x180003d77  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180003d7e  mov     rdx, rsi; unsigned __int16 *
0x180003d81  mov     rcx, rax; this
0x180003d84  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003d89  mov     rcx, [rbx+28h]
0x180003d8d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180003d91  mov     rdx, rsi; unsigned __int16 *
0x180003d94  test    rcx, rcx
0x180003d97  jz      short loc_180003DAF
0x180003d99  mov     [rsp+278h+lpBuffer], rcx
0x180003d9e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180003da5  mov     rcx, rax; this
0x180003da8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003dad  jmp     short loc_180003DD1
0x180003daf  mov     rcx, rax; this
0x180003db2  test    r9, r9
0x180003db5  jz      short loc_180003DC5
0x180003db7  lea     r8, aHs; "[%hs]\n"
0x180003dbe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003dc3  jmp     short loc_180003DD1
0x180003dc5  lea     r8, asc_18000BBC0; "\n"
0x180003dcc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003dd1  xor     eax, eax
0x180003dd3  mov     rcx, [rsp+278h+var_38]
0x180003ddb  xor     rcx, rsp; StackCookie
0x180003dde  call    __security_check_cookie
0x180003de3  mov     rbx, [rsp+278h+arg_18]
0x180003deb  add     rsp, 250h
0x180003df2  pop     r15
0x180003df4  pop     r14
0x180003df6  pop     rdi
0x180003df7  pop     rsi
0x180003df8  pop     rbp
0x180003df9  retn
```
