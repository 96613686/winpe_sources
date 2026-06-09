# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180051fb4`
- end: `0x18005226a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180052c70`
- `0x1800557f0`

## callees

- `0x18004ca90`
- `0x18004d8fc`
- `0x180051fb4`
- `0x180052f6c`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052167`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052167`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800520e6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800520e6`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        STRSAFE_LPWSTR pszDest,
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
  wchar_t *v14; // rax
  wchar_t *v15; // r14
  const unsigned __int16 *v16; // r9
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
          v7 = (const char *)&word_1800A040E;
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
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const unsigned __int16 **)(a3 + 128);
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
  v16 = *(const unsigned __int16 **)(a3 + 144);
  if ( v16 )
    v15 = wil::details::LogStringPrintf(v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = wil::details::LogStringPrintf(
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
      v19 = wil::details::LogStringPrintf(v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf(v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
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
0x180051fb4  mov     [rsp+arg_18], rbx
0x180051fb9  push    rbp
0x180051fba  push    rsi
0x180051fbb  push    rdi
0x180051fbc  push    r14
0x180051fbe  push    r15
0x180051fc0  sub     rsp, 250h
0x180051fc7  mov     rax, cs:__security_cookie
0x180051fce  xor     rax, rsp
0x180051fd1  mov     [rsp+278h+var_38], rax
0x180051fd9  mov     rbx, r8
0x180051fdc  mov     rsi, rdx
0x180051fdf  mov     r14, rcx
0x180051fe2  xor     r15d, r15d
0x180051fe5  test    rdx, rdx
0x180051fe8  jz      loc_180052241
0x180051fee  test    rcx, rcx
0x180051ff1  jz      loc_180052241
0x180051ff7  mov     [rcx], r15w
0x180051ffb  mov     rax, cs:g_pfnResultLoggingCallback
0x180052002  test    rax, rax
0x180052005  jz      short loc_180052028
0x180052007  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18005200e  jz      short loc_180052028
0x180052010  mov     r8, rdx
0x180052013  mov     rdx, rcx
0x180052016  mov     rcx, rbx
0x180052019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005201e  cmp     [r14], r15w
0x180052022  jnz     loc_180052241
0x180052028  mov     ecx, [rbx]
0x18005202a  mov     bpl, 8
0x18005202d  test    ecx, ecx
0x18005202f  jz      short loc_18005207A
0x180052031  sub     ecx, 1
0x180052034  jz      short loc_180052062
0x180052036  sub     ecx, 1
0x180052039  jz      short loc_180052052
0x18005203b  cmp     ecx, 1
0x18005203e  jz      short loc_180052049
0x180052040  lea     rdi, word_1800A040E
0x180052047  jmp     short loc_180052081
0x180052049  lea     rdi, aFailfast; "FailFast"
0x180052050  jmp     short loc_180052081
0x180052052  lea     rax, aLoghr; "LogHr"
0x180052059  lea     rdi, aLognt; "LogNt"
0x180052060  jmp     short loc_180052070
0x180052062  lea     rax, aReturnhr; "ReturnHr"
0x180052069  lea     rdi, aReturnnt; "ReturnNt"
0x180052070  test    [rbx+4], bpl
0x180052074  cmovz   rdi, rax
0x180052078  jmp     short loc_180052081
0x18005207a  lea     rdi, aException; "Exception"
0x180052081  xor     edx, edx; Val
0x180052083  mov     r8d, 200h; Size
0x180052089  lea     rcx, [rsp+278h+Buffer]; void *
0x18005208e  call    memset_0
0x180052093  test    [rbx+4], bpl
0x180052097  jz      short loc_1800520BC
0x180052099  mov     ebp, [rbx+0Ch]
0x18005209c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800520a3  test    rax, rax
0x1800520a6  jz      short loc_1800520EC
0x1800520a8  mov     r8d, 100h
0x1800520ae  lea     rdx, [rsp+278h+Buffer]
0x1800520b3  mov     ecx, ebp
0x1800520b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800520ba  jmp     short loc_1800520EC
0x1800520bc  mov     ebp, [rbx+8]
0x1800520bf  mov     [rsp+278h+Arguments], r15; Arguments
0x1800520c4  mov     [rsp+278h+nSize], 100h; nSize
0x1800520cc  lea     rax, [rsp+278h+Buffer]
0x1800520d1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800520d6  mov     r9d, 400h; dwLanguageId
0x1800520dc  mov     r8d, ebp; dwMessageId
0x1800520df  xor     edx, edx; lpSource
0x1800520e1  mov     ecx, 1200h; dwFlags
0x1800520e6  call    cs:__imp_FormatMessageW
0x1800520ec  lea     rsi, [r14+rsi*2]
0x1800520f0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800520f4  mov     rax, [rbx+88h]
0x1800520fb  mov     rcx, [rbx+80h]
0x180052102  mov     rdx, rsi; unsigned __int16 *
0x180052105  test    r9, r9
0x180052108  jz      short loc_18005212C
0x18005210a  mov     [rsp+278h+Arguments], rax
0x18005210f  mov     qword ptr [rsp+278h+nSize], rcx
0x180052114  mov     eax, [rbx+40h]
0x180052117  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18005211b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180052122  mov     rcx, r14; pszDest
0x180052125  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005212a  jmp     short loc_180052143
0x18005212c  mov     [rsp+278h+lpBuffer], rax
0x180052131  mov     r9, rcx; unsigned __int16 *
0x180052134  lea     r8, aHsP; "%hs!%p: "
0x18005213b  mov     rcx, r14; pszDest
0x18005213e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180052143  mov     r14, rax
0x180052146  mov     r9, [rbx+90h]; unsigned __int16 *
0x18005214d  test    r9, r9
0x180052150  jz      short loc_180052167
0x180052152  lea     r8, aCallerP; "(caller: %p) "
0x180052159  mov     rdx, rsi; unsigned __int16 *
0x18005215c  mov     rcx, rax; pszDest
0x18005215f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180052164  mov     r14, rax
0x180052167  call    cs:__imp_GetCurrentThreadId
0x18005216d  lea     rcx, [rsp+278h+Buffer]
0x180052172  mov     [rsp+278h+var_240], rcx
0x180052177  mov     dword ptr [rsp+278h+Arguments], ebp
0x18005217b  mov     [rsp+278h+nSize], eax
0x18005217f  mov     eax, [rbx+44h]
0x180052182  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180052186  mov     r9, rdi; unsigned __int16 *
0x180052189  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180052190  mov     rdx, rsi; unsigned __int16 *
0x180052193  mov     rcx, r14; pszDest
0x180052196  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005219b  cmp     [rbx+18h], r15
0x18005219f  jnz     short loc_1800521B1
0x1800521a1  cmp     [rbx+48h], r15
0x1800521a5  jnz     short loc_1800521B1
0x1800521a7  cmp     [rbx+30h], r15
0x1800521ab  jz      loc_180052241
0x1800521b1  lea     r8, asc_1800A04F8; "    "
0x1800521b8  mov     rdx, rsi; unsigned __int16 *
0x1800521bb  mov     rcx, rax; pszDest
0x1800521be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800521c3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800521c7  test    r9, r9
0x1800521ca  jz      short loc_1800521DE
0x1800521cc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800521d3  mov     rdx, rsi; unsigned __int16 *
0x1800521d6  mov     rcx, rax; pszDest
0x1800521d9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800521de  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800521e2  test    r9, r9
0x1800521e5  jz      short loc_1800521F9
0x1800521e7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800521ee  mov     rdx, rsi; unsigned __int16 *
0x1800521f1  mov     rcx, rax; pszDest
0x1800521f4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800521f9  mov     rcx, [rbx+28h]
0x1800521fd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180052201  mov     rdx, rsi; unsigned __int16 *
0x180052204  test    rcx, rcx
0x180052207  jz      short loc_18005221F
0x180052209  mov     [rsp+278h+lpBuffer], rcx
0x18005220e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180052215  mov     rcx, rax; pszDest
0x180052218  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005221d  jmp     short loc_180052241
0x18005221f  mov     rcx, rax; pszDest
0x180052222  test    r9, r9
0x180052225  jz      short loc_180052235
0x180052227  lea     r8, aHs; "[%hs]\n"
0x18005222e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180052233  jmp     short loc_180052241
0x180052235  lea     r8, asc_18009E340; "\n"
0x18005223c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180052241  xor     eax, eax
0x180052243  mov     rcx, [rsp+278h+var_38]
0x18005224b  xor     rcx, rsp; StackCookie
0x18005224e  call    __security_check_cookie
0x180052253  mov     rbx, [rsp+278h+arg_18]
0x18005225b  add     rsp, 250h
0x180052262  pop     r15
0x180052264  pop     r14
0x180052266  pop     rdi
0x180052267  pop     rsi
0x180052268  pop     rbp
0x180052269  retn
```
