# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000a91c`
- end: `0x18000abd2`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180007104`
- `0x18000c9c8`
- `0x180014030`

## callees

- `0x180002270`
- `0x180002c2c`
- `0x18000a91c`
- `0x18000ccc8`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000aacf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000aacf`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000aa4e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000aa4e`

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
          v7 = (const char *)&word_180027A38;
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
0x18000a91c  mov     [rsp+arg_18], rbx
0x18000a921  push    rbp
0x18000a922  push    rsi
0x18000a923  push    rdi
0x18000a924  push    r14
0x18000a926  push    r15
0x18000a928  sub     rsp, 250h
0x18000a92f  mov     rax, cs:__security_cookie
0x18000a936  xor     rax, rsp
0x18000a939  mov     [rsp+278h+var_38], rax
0x18000a941  mov     rbx, r8
0x18000a944  mov     rsi, rdx
0x18000a947  mov     r14, rcx
0x18000a94a  xor     r15d, r15d
0x18000a94d  test    rdx, rdx
0x18000a950  jz      loc_18000ABA9
0x18000a956  test    rcx, rcx
0x18000a959  jz      loc_18000ABA9
0x18000a95f  mov     [rcx], r15w
0x18000a963  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a96a  test    rax, rax
0x18000a96d  jz      short loc_18000A990
0x18000a96f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000a976  jz      short loc_18000A990
0x18000a978  mov     r8, rdx
0x18000a97b  mov     rdx, rcx
0x18000a97e  mov     rcx, rbx
0x18000a981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a986  cmp     [r14], r15w
0x18000a98a  jnz     loc_18000ABA9
0x18000a990  mov     ecx, [rbx]
0x18000a992  mov     bpl, 8
0x18000a995  test    ecx, ecx
0x18000a997  jz      short loc_18000A9E2
0x18000a999  sub     ecx, 1
0x18000a99c  jz      short loc_18000A9CA
0x18000a99e  sub     ecx, 1
0x18000a9a1  jz      short loc_18000A9BA
0x18000a9a3  cmp     ecx, 1
0x18000a9a6  jz      short loc_18000A9B1
0x18000a9a8  lea     rdi, word_180027A38
0x18000a9af  jmp     short loc_18000A9E9
0x18000a9b1  lea     rdi, aFailfast; "FailFast"
0x18000a9b8  jmp     short loc_18000A9E9
0x18000a9ba  lea     rax, aLoghr; "LogHr"
0x18000a9c1  lea     rdi, aLognt; "LogNt"
0x18000a9c8  jmp     short loc_18000A9D8
0x18000a9ca  lea     rax, aReturnhr; "ReturnHr"
0x18000a9d1  lea     rdi, aReturnnt; "ReturnNt"
0x18000a9d8  test    [rbx+4], bpl
0x18000a9dc  cmovz   rdi, rax
0x18000a9e0  jmp     short loc_18000A9E9
0x18000a9e2  lea     rdi, aException; "Exception"
0x18000a9e9  xor     edx, edx; Val
0x18000a9eb  mov     r8d, 200h; Size
0x18000a9f1  lea     rcx, [rsp+278h+Buffer]; void *
0x18000a9f6  call    memset_0
0x18000a9fb  test    [rbx+4], bpl
0x18000a9ff  jz      short loc_18000AA24
0x18000aa01  mov     ebp, [rbx+0Ch]
0x18000aa04  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000aa0b  test    rax, rax
0x18000aa0e  jz      short loc_18000AA54
0x18000aa10  mov     r8d, 100h
0x18000aa16  lea     rdx, [rsp+278h+Buffer]
0x18000aa1b  mov     ecx, ebp
0x18000aa1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa22  jmp     short loc_18000AA54
0x18000aa24  mov     ebp, [rbx+8]
0x18000aa27  mov     [rsp+278h+Arguments], r15; Arguments
0x18000aa2c  mov     [rsp+278h+nSize], 100h; nSize
0x18000aa34  lea     rax, [rsp+278h+Buffer]
0x18000aa39  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000aa3e  mov     r9d, 400h; dwLanguageId
0x18000aa44  mov     r8d, ebp; dwMessageId
0x18000aa47  xor     edx, edx; lpSource
0x18000aa49  mov     ecx, 1200h; dwFlags
0x18000aa4e  call    cs:__imp_FormatMessageW
0x18000aa54  lea     rsi, [r14+rsi*2]
0x18000aa58  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000aa5c  mov     rax, [rbx+88h]
0x18000aa63  mov     rcx, [rbx+80h]
0x18000aa6a  mov     rdx, rsi; unsigned __int16 *
0x18000aa6d  test    r9, r9
0x18000aa70  jz      short loc_18000AA94
0x18000aa72  mov     [rsp+278h+Arguments], rax
0x18000aa77  mov     qword ptr [rsp+278h+nSize], rcx
0x18000aa7c  mov     eax, [rbx+40h]
0x18000aa7f  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000aa83  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000aa8a  mov     rcx, r14; this
0x18000aa8d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000aa92  jmp     short loc_18000AAAB
0x18000aa94  mov     [rsp+278h+lpBuffer], rax
0x18000aa99  mov     r9, rcx; unsigned __int16 *
0x18000aa9c  lea     r8, aHsP; "%hs!%p: "
0x18000aaa3  mov     rcx, r14; this
0x18000aaa6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000aaab  mov     r14, rax
0x18000aaae  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000aab5  test    r9, r9
0x18000aab8  jz      short loc_18000AACF
0x18000aaba  lea     r8, aCallerP; "(caller: %p) "
0x18000aac1  mov     rdx, rsi; unsigned __int16 *
0x18000aac4  mov     rcx, rax; this
0x18000aac7  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000aacc  mov     r14, rax
0x18000aacf  call    cs:__imp_GetCurrentThreadId
0x18000aad5  lea     rcx, [rsp+278h+Buffer]
0x18000aada  mov     [rsp+278h+var_240], rcx
0x18000aadf  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000aae3  mov     [rsp+278h+nSize], eax
0x18000aae7  mov     eax, [rbx+44h]
0x18000aaea  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000aaee  mov     r9, rdi; unsigned __int16 *
0x18000aaf1  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000aaf8  mov     rdx, rsi; unsigned __int16 *
0x18000aafb  mov     rcx, r14; this
0x18000aafe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ab03  cmp     [rbx+18h], r15
0x18000ab07  jnz     short loc_18000AB19
0x18000ab09  cmp     [rbx+48h], r15
0x18000ab0d  jnz     short loc_18000AB19
0x18000ab0f  cmp     [rbx+30h], r15
0x18000ab13  jz      loc_18000ABA9
0x18000ab19  lea     r8, asc_180027B90; "    "
0x18000ab20  mov     rdx, rsi; unsigned __int16 *
0x18000ab23  mov     rcx, rax; this
0x18000ab26  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ab2b  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000ab2f  test    r9, r9
0x18000ab32  jz      short loc_18000AB46
0x18000ab34  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000ab3b  mov     rdx, rsi; unsigned __int16 *
0x18000ab3e  mov     rcx, rax; this
0x18000ab41  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ab46  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000ab4a  test    r9, r9
0x18000ab4d  jz      short loc_18000AB61
0x18000ab4f  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000ab56  mov     rdx, rsi; unsigned __int16 *
0x18000ab59  mov     rcx, rax; this
0x18000ab5c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ab61  mov     rcx, [rbx+28h]
0x18000ab65  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000ab69  mov     rdx, rsi; unsigned __int16 *
0x18000ab6c  test    rcx, rcx
0x18000ab6f  jz      short loc_18000AB87
0x18000ab71  mov     [rsp+278h+lpBuffer], rcx
0x18000ab76  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000ab7d  mov     rcx, rax; this
0x18000ab80  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ab85  jmp     short loc_18000ABA9
0x18000ab87  mov     rcx, rax; this
0x18000ab8a  test    r9, r9
0x18000ab8d  jz      short loc_18000AB9D
0x18000ab8f  lea     r8, aHs; "[%hs]\n"
0x18000ab96  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ab9b  jmp     short loc_18000ABA9
0x18000ab9d  lea     r8, asc_180027C08; "\n"
0x18000aba4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000aba9  xor     eax, eax
0x18000abab  mov     rcx, [rsp+278h+var_38]
0x18000abb3  xor     rcx, rsp; StackCookie
0x18000abb6  call    __security_check_cookie
0x18000abbb  mov     rbx, [rsp+278h+arg_18]
0x18000abc3  add     rsp, 250h
0x18000abca  pop     r15
0x18000abcc  pop     r14
0x18000abce  pop     rdi
0x18000abcf  pop     rsi
0x18000abd0  pop     rbp
0x18000abd1  retn
```
