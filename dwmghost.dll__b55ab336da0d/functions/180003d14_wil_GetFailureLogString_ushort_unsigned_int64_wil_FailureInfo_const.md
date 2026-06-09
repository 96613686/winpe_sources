# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180003d14`
- end: `0x180003fca`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002c88`
- `0x180002ef8`
- `0x18000468c`

## callees

- `0x180001190`
- `0x180001962`
- `0x180003d14`
- `0x18000498c`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003ec7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003ec7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003e46`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003e46`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rdi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rsi
  __int64 v13; // rax
  unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // r9
  wil::details *v16; // r14
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
  v7 = (void (__fastcall *)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
  *(_WORD *)this = 0;
  if ( v7 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      v7(a3, this, a2, a4);
      if ( *(_WORD *)this )
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
          v8 = (const char *)&word_18000E17E;
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
  v12 = (unsigned __int16 *)((char *)this + 2 * (_QWORD)a2);
  v13 = *(_QWORD *)(a3 + 136);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, *(_QWORD *)(a3 + 128), v13);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs!%p: ", *(const unsigned __int16 **)(a3 + 128), v13);
  }
  v15 = *(const unsigned __int16 **)(a3 + 144);
  v16 = (wil::details *)v14;
  if ( v15 )
    v16 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v12, L"(caller: %p) ", v15);
  LODWORD(Arguments) = v10;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
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
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180003d14  mov     [rsp+arg_18], rbx
0x180003d19  push    rbp
0x180003d1a  push    rsi
0x180003d1b  push    rdi
0x180003d1c  push    r14
0x180003d1e  push    r15
0x180003d20  sub     rsp, 250h
0x180003d27  mov     rax, cs:__security_cookie
0x180003d2e  xor     rax, rsp
0x180003d31  mov     [rsp+278h+var_38], rax
0x180003d39  xor     r15d, r15d
0x180003d3c  mov     rbx, r8
0x180003d3f  mov     rsi, rdx
0x180003d42  mov     r14, rcx
0x180003d45  test    rdx, rdx
0x180003d48  jz      loc_180003FA1
0x180003d4e  test    rcx, rcx
0x180003d51  jz      loc_180003FA1
0x180003d57  mov     rax, cs:g_pfnResultLoggingCallback
0x180003d5e  mov     [rcx], r15w
0x180003d62  test    rax, rax
0x180003d65  jz      short loc_180003D88
0x180003d67  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003d6e  jz      short loc_180003D88
0x180003d70  mov     r8, rdx
0x180003d73  mov     rdx, rcx
0x180003d76  mov     rcx, rbx
0x180003d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d7e  cmp     [r14], r15w
0x180003d82  jnz     loc_180003FA1
0x180003d88  mov     ecx, [rbx]
0x180003d8a  mov     bpl, 8
0x180003d8d  test    ecx, ecx
0x180003d8f  jz      short loc_180003DDA
0x180003d91  sub     ecx, 1
0x180003d94  jz      short loc_180003DC2
0x180003d96  sub     ecx, 1
0x180003d99  jz      short loc_180003DB2
0x180003d9b  cmp     ecx, 1
0x180003d9e  jz      short loc_180003DA9
0x180003da0  lea     rdi, word_18000E17E
0x180003da7  jmp     short loc_180003DE1
0x180003da9  lea     rdi, aFailfast; "FailFast"
0x180003db0  jmp     short loc_180003DE1
0x180003db2  lea     rax, aLoghr; "LogHr"
0x180003db9  lea     rdi, aLognt; "LogNt"
0x180003dc0  jmp     short loc_180003DD0
0x180003dc2  lea     rax, aReturnhr; "ReturnHr"
0x180003dc9  lea     rdi, aReturnnt; "ReturnNt"
0x180003dd0  test    [rbx+4], bpl
0x180003dd4  cmovz   rdi, rax
0x180003dd8  jmp     short loc_180003DE1
0x180003dda  lea     rdi, aException; "Exception"
0x180003de1  xor     edx, edx; Val
0x180003de3  lea     rcx, [rsp+278h+Buffer]; void *
0x180003de8  mov     r8d, 200h; Size
0x180003dee  call    memset_0
0x180003df3  test    [rbx+4], bpl
0x180003df7  jz      short loc_180003E1C
0x180003df9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180003e00  mov     ebp, [rbx+0Ch]
0x180003e03  test    rax, rax
0x180003e06  jz      short loc_180003E4C
0x180003e08  mov     r8d, 100h
0x180003e0e  lea     rdx, [rsp+278h+Buffer]
0x180003e13  mov     ecx, ebp
0x180003e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e1a  jmp     short loc_180003E4C
0x180003e1c  mov     ebp, [rbx+8]
0x180003e1f  lea     rax, [rsp+278h+Buffer]
0x180003e24  mov     [rsp+278h+Arguments], r15; Arguments
0x180003e29  mov     r8d, ebp; dwMessageId
0x180003e2c  mov     [rsp+278h+nSize], 100h; nSize
0x180003e34  mov     r9d, 400h; dwLanguageId
0x180003e3a  xor     edx, edx; lpSource
0x180003e3c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180003e41  mov     ecx, 1200h; dwFlags
0x180003e46  call    cs:__imp_FormatMessageW
0x180003e4c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180003e50  lea     rsi, [r14+rsi*2]
0x180003e54  mov     rax, [rbx+88h]
0x180003e5b  mov     rdx, rsi; unsigned __int16 *
0x180003e5e  mov     rcx, [rbx+80h]
0x180003e65  test    r9, r9
0x180003e68  jz      short loc_180003E8C
0x180003e6a  mov     [rsp+278h+Arguments], rax
0x180003e6f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180003e76  mov     eax, [rbx+40h]
0x180003e79  mov     qword ptr [rsp+278h+nSize], rcx
0x180003e7e  mov     rcx, r14; this
0x180003e81  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003e85  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003e8a  jmp     short loc_180003EA3
0x180003e8c  mov     r9, rcx; unsigned __int16 *
0x180003e8f  mov     [rsp+278h+lpBuffer], rax
0x180003e94  mov     rcx, r14; this
0x180003e97  lea     r8, aHsP; "%hs!%p: "
0x180003e9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003ea3  mov     r9, [rbx+90h]; unsigned __int16 *
0x180003eaa  mov     r14, rax
0x180003ead  test    r9, r9
0x180003eb0  jz      short loc_180003EC7
0x180003eb2  lea     r8, aCallerP; "(caller: %p) "
0x180003eb9  mov     rdx, rsi; unsigned __int16 *
0x180003ebc  mov     rcx, rax; this
0x180003ebf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003ec4  mov     r14, rax
0x180003ec7  call    cs:__imp_GetCurrentThreadId
0x180003ecd  lea     rcx, [rsp+278h+Buffer]
0x180003ed2  mov     r9, rdi; unsigned __int16 *
0x180003ed5  mov     [rsp+278h+var_240], rcx
0x180003eda  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180003ee1  mov     dword ptr [rsp+278h+Arguments], ebp
0x180003ee5  mov     rdx, rsi; unsigned __int16 *
0x180003ee8  mov     [rsp+278h+nSize], eax
0x180003eec  mov     rcx, r14; this
0x180003eef  mov     eax, [rbx+44h]
0x180003ef2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003ef6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003efb  cmp     [rbx+18h], r15
0x180003eff  jnz     short loc_180003F11
0x180003f01  cmp     [rbx+48h], r15
0x180003f05  jnz     short loc_180003F11
0x180003f07  cmp     [rbx+30h], r15
0x180003f0b  jz      loc_180003FA1
0x180003f11  lea     r8, asc_18000E268; "    "
0x180003f18  mov     rdx, rsi; unsigned __int16 *
0x180003f1b  mov     rcx, rax; this
0x180003f1e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003f23  mov     r9, [rbx+18h]; unsigned __int16 *
0x180003f27  test    r9, r9
0x180003f2a  jz      short loc_180003F3E
0x180003f2c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180003f33  mov     rdx, rsi; unsigned __int16 *
0x180003f36  mov     rcx, rax; this
0x180003f39  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003f3e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180003f42  test    r9, r9
0x180003f45  jz      short loc_180003F59
0x180003f47  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180003f4e  mov     rdx, rsi; unsigned __int16 *
0x180003f51  mov     rcx, rax; this
0x180003f54  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003f59  mov     rcx, [rbx+28h]
0x180003f5d  mov     rdx, rsi; unsigned __int16 *
0x180003f60  mov     r9, [rbx+30h]; unsigned __int16 *
0x180003f64  test    rcx, rcx
0x180003f67  jz      short loc_180003F7F
0x180003f69  mov     [rsp+278h+lpBuffer], rcx
0x180003f6e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180003f75  mov     rcx, rax; this
0x180003f78  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003f7d  jmp     short loc_180003FA1
0x180003f7f  mov     rcx, rax; this
0x180003f82  test    r9, r9
0x180003f85  jz      short loc_180003F95
0x180003f87  lea     r8, aHs; "[%hs]\n"
0x180003f8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003f93  jmp     short loc_180003FA1
0x180003f95  lea     r8, asc_18000E2E0; "\n"
0x180003f9c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003fa1  xor     eax, eax
0x180003fa3  mov     rcx, [rsp+278h+var_38]
0x180003fab  xor     rcx, rsp; StackCookie
0x180003fae  call    __security_check_cookie
0x180003fb3  mov     rbx, [rsp+278h+arg_18]
0x180003fbb  add     rsp, 250h
0x180003fc2  pop     r15
0x180003fc4  pop     r14
0x180003fc6  pop     rdi
0x180003fc7  pop     rsi
0x180003fc8  pop     rbp
0x180003fc9  retn
```
