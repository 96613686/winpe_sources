# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180059fb4`
- end: `0x18005a26a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180058258`
- `0x1800584d8`
- `0x18005ac78`
- `0x18005b29c`
- `0x18005de40`

## callees

- `0x18000df90`
- `0x18000ebf4`
- `0x180059fb4`
- `0x18005af78`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a167`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a167`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18005a0e6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18005a0e6`

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
          v7 = (const char *)&word_180111902;
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
0x180059fb4  mov     [rsp+arg_18], rbx
0x180059fb9  push    rbp
0x180059fba  push    rsi
0x180059fbb  push    rdi
0x180059fbc  push    r14
0x180059fbe  push    r15
0x180059fc0  sub     rsp, 250h
0x180059fc7  mov     rax, cs:__security_cookie
0x180059fce  xor     rax, rsp
0x180059fd1  mov     [rsp+278h+var_38], rax
0x180059fd9  mov     rbx, r8
0x180059fdc  mov     rsi, rdx
0x180059fdf  mov     r14, rcx
0x180059fe2  xor     r15d, r15d
0x180059fe5  test    rdx, rdx
0x180059fe8  jz      loc_18005A241
0x180059fee  test    rcx, rcx
0x180059ff1  jz      loc_18005A241
0x180059ff7  mov     [rcx], r15w
0x180059ffb  mov     rax, cs:g_pfnResultLoggingCallback
0x18005a002  test    rax, rax
0x18005a005  jz      short loc_18005A028
0x18005a007  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18005a00e  jz      short loc_18005A028
0x18005a010  mov     r8, rdx
0x18005a013  mov     rdx, rcx
0x18005a016  mov     rcx, rbx
0x18005a019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a01e  cmp     [r14], r15w
0x18005a022  jnz     loc_18005A241
0x18005a028  mov     ecx, [rbx]
0x18005a02a  mov     bpl, 8
0x18005a02d  test    ecx, ecx
0x18005a02f  jz      short loc_18005A07A
0x18005a031  sub     ecx, 1
0x18005a034  jz      short loc_18005A062
0x18005a036  sub     ecx, 1
0x18005a039  jz      short loc_18005A052
0x18005a03b  cmp     ecx, 1
0x18005a03e  jz      short loc_18005A049
0x18005a040  lea     rdi, word_180111902
0x18005a047  jmp     short loc_18005A081
0x18005a049  lea     rdi, aFailfast; "FailFast"
0x18005a050  jmp     short loc_18005A081
0x18005a052  lea     rax, aLoghr; "LogHr"
0x18005a059  lea     rdi, aLognt; "LogNt"
0x18005a060  jmp     short loc_18005A070
0x18005a062  lea     rax, aReturnhr; "ReturnHr"
0x18005a069  lea     rdi, aReturnnt; "ReturnNt"
0x18005a070  test    [rbx+4], bpl
0x18005a074  cmovz   rdi, rax
0x18005a078  jmp     short loc_18005A081
0x18005a07a  lea     rdi, aException; "Exception"
0x18005a081  xor     edx, edx; Val
0x18005a083  mov     r8d, 200h; Size
0x18005a089  lea     rcx, [rsp+278h+Buffer]; void *
0x18005a08e  call    memset_0
0x18005a093  test    [rbx+4], bpl
0x18005a097  jz      short loc_18005A0BC
0x18005a099  mov     ebp, [rbx+0Ch]
0x18005a09c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18005a0a3  test    rax, rax
0x18005a0a6  jz      short loc_18005A0EC
0x18005a0a8  mov     r8d, 100h
0x18005a0ae  lea     rdx, [rsp+278h+Buffer]
0x18005a0b3  mov     ecx, ebp
0x18005a0b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a0ba  jmp     short loc_18005A0EC
0x18005a0bc  mov     ebp, [rbx+8]
0x18005a0bf  mov     [rsp+278h+Arguments], r15; Arguments
0x18005a0c4  mov     [rsp+278h+nSize], 100h; nSize
0x18005a0cc  lea     rax, [rsp+278h+Buffer]
0x18005a0d1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18005a0d6  mov     r9d, 400h; dwLanguageId
0x18005a0dc  mov     r8d, ebp; dwMessageId
0x18005a0df  xor     edx, edx; lpSource
0x18005a0e1  mov     ecx, 1200h; dwFlags
0x18005a0e6  call    cs:__imp_FormatMessageW
0x18005a0ec  lea     rsi, [r14+rsi*2]
0x18005a0f0  mov     r9, [rbx+38h]; unsigned __int16 *
0x18005a0f4  mov     rax, [rbx+88h]
0x18005a0fb  mov     rcx, [rbx+80h]
0x18005a102  mov     rdx, rsi; unsigned __int16 *
0x18005a105  test    r9, r9
0x18005a108  jz      short loc_18005A12C
0x18005a10a  mov     [rsp+278h+Arguments], rax
0x18005a10f  mov     qword ptr [rsp+278h+nSize], rcx
0x18005a114  mov     eax, [rbx+40h]
0x18005a117  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18005a11b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18005a122  mov     rcx, r14; this
0x18005a125  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005a12a  jmp     short loc_18005A143
0x18005a12c  mov     [rsp+278h+lpBuffer], rax
0x18005a131  mov     r9, rcx; unsigned __int16 *
0x18005a134  lea     r8, aHsP; "%hs!%p: "
0x18005a13b  mov     rcx, r14; this
0x18005a13e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005a143  mov     r14, rax
0x18005a146  mov     r9, [rbx+90h]; unsigned __int16 *
0x18005a14d  test    r9, r9
0x18005a150  jz      short loc_18005A167
0x18005a152  lea     r8, aCallerP; "(caller: %p) "
0x18005a159  mov     rdx, rsi; unsigned __int16 *
0x18005a15c  mov     rcx, rax; this
0x18005a15f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005a164  mov     r14, rax
0x18005a167  call    cs:__imp_GetCurrentThreadId
0x18005a16d  lea     rcx, [rsp+278h+Buffer]
0x18005a172  mov     [rsp+278h+var_240], rcx
0x18005a177  mov     dword ptr [rsp+278h+Arguments], ebp
0x18005a17b  mov     [rsp+278h+nSize], eax
0x18005a17f  mov     eax, [rbx+44h]
0x18005a182  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18005a186  mov     r9, rdi; unsigned __int16 *
0x18005a189  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18005a190  mov     rdx, rsi; unsigned __int16 *
0x18005a193  mov     rcx, r14; this
0x18005a196  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005a19b  cmp     [rbx+18h], r15
0x18005a19f  jnz     short loc_18005A1B1
0x18005a1a1  cmp     [rbx+48h], r15
0x18005a1a5  jnz     short loc_18005A1B1
0x18005a1a7  cmp     [rbx+30h], r15
0x18005a1ab  jz      loc_18005A241
0x18005a1b1  lea     r8, asc_1801119F0; "    "
0x18005a1b8  mov     rdx, rsi; unsigned __int16 *
0x18005a1bb  mov     rcx, rax; this
0x18005a1be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005a1c3  mov     r9, [rbx+18h]; unsigned __int16 *
0x18005a1c7  test    r9, r9
0x18005a1ca  jz      short loc_18005A1DE
0x18005a1cc  lea     r8, aMsgWs; "Msg:[%ws] "
0x18005a1d3  mov     rdx, rsi; unsigned __int16 *
0x18005a1d6  mov     rcx, rax; this
0x18005a1d9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005a1de  mov     r9, [rbx+48h]; unsigned __int16 *
0x18005a1e2  test    r9, r9
0x18005a1e5  jz      short loc_18005A1F9
0x18005a1e7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18005a1ee  mov     rdx, rsi; unsigned __int16 *
0x18005a1f1  mov     rcx, rax; this
0x18005a1f4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005a1f9  mov     rcx, [rbx+28h]
0x18005a1fd  mov     r9, [rbx+30h]; unsigned __int16 *
0x18005a201  mov     rdx, rsi; unsigned __int16 *
0x18005a204  test    rcx, rcx
0x18005a207  jz      short loc_18005A21F
0x18005a209  mov     [rsp+278h+lpBuffer], rcx
0x18005a20e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18005a215  mov     rcx, rax; this
0x18005a218  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005a21d  jmp     short loc_18005A241
0x18005a21f  mov     rcx, rax; this
0x18005a222  test    r9, r9
0x18005a225  jz      short loc_18005A235
0x18005a227  lea     r8, aHs; "[%hs]\n"
0x18005a22e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005a233  jmp     short loc_18005A241
0x18005a235  lea     r8, asc_180111A68; "\n"
0x18005a23c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005a241  xor     eax, eax
0x18005a243  mov     rcx, [rsp+278h+var_38]
0x18005a24b  xor     rcx, rsp; StackCookie
0x18005a24e  call    __security_check_cookie
0x18005a253  mov     rbx, [rsp+278h+arg_18]
0x18005a25b  add     rsp, 250h
0x18005a262  pop     r15
0x18005a264  pop     r14
0x18005a266  pop     rdi
0x18005a267  pop     rsi
0x18005a268  pop     rbp
0x18005a269  retn
```
