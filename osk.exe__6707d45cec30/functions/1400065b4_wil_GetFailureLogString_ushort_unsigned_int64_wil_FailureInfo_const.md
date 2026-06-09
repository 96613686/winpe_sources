# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1400065b4`
- end: `0x14000686a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140003c6c`
- `0x1400073c8`
- `0x14000d650`

## callees

- `0x140002de3`
- `0x1400065b4`
- `0x1400076c8`
- `0x140025d70`
- `0x140027010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140006767`
- `KERNEL32!GetCurrentThreadId` at `0x140006767`
- `KERNEL32!FormatMessageW` at `0x1400066e6`
- `KERNEL32!FormatMessageW` at `0x1400066e6`

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
          v7 = MultiByteStr;
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
0x1400065b4  mov     [rsp+arg_18], rbx
0x1400065b9  push    rbp
0x1400065ba  push    rsi
0x1400065bb  push    rdi
0x1400065bc  push    r14
0x1400065be  push    r15
0x1400065c0  sub     rsp, 250h
0x1400065c7  mov     rax, cs:__security_cookie
0x1400065ce  xor     rax, rsp
0x1400065d1  mov     [rsp+278h+var_38], rax
0x1400065d9  mov     rbx, r8
0x1400065dc  mov     rsi, rdx
0x1400065df  mov     r14, rcx
0x1400065e2  xor     r15d, r15d
0x1400065e5  test    rdx, rdx
0x1400065e8  jz      loc_140006841
0x1400065ee  test    rcx, rcx
0x1400065f1  jz      loc_140006841
0x1400065f7  mov     [rcx], r15w
0x1400065fb  mov     rax, cs:g_pfnResultLoggingCallback
0x140006602  test    rax, rax
0x140006605  jz      short loc_140006628
0x140006607  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000660e  jz      short loc_140006628
0x140006610  mov     r8, rdx
0x140006613  mov     rdx, rcx
0x140006616  mov     rcx, rbx
0x140006619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000661e  cmp     [r14], r15w
0x140006622  jnz     loc_140006841
0x140006628  mov     ecx, [rbx]
0x14000662a  mov     bpl, 8
0x14000662d  test    ecx, ecx
0x14000662f  jz      short loc_14000667A
0x140006631  sub     ecx, 1
0x140006634  jz      short loc_140006662
0x140006636  sub     ecx, 1
0x140006639  jz      short loc_140006652
0x14000663b  cmp     ecx, 1
0x14000663e  jz      short loc_140006649
0x140006640  lea     rdi, MultiByteStr
0x140006647  jmp     short loc_140006681
0x140006649  lea     rdi, aFailfast; "FailFast"
0x140006650  jmp     short loc_140006681
0x140006652  lea     rax, aLoghr; "LogHr"
0x140006659  lea     rdi, aLognt; "LogNt"
0x140006660  jmp     short loc_140006670
0x140006662  lea     rax, aReturnhr; "ReturnHr"
0x140006669  lea     rdi, aReturnnt; "ReturnNt"
0x140006670  test    [rbx+4], bpl
0x140006674  cmovz   rdi, rax
0x140006678  jmp     short loc_140006681
0x14000667a  lea     rdi, aException; "Exception"
0x140006681  xor     edx, edx; Val
0x140006683  mov     r8d, 200h; Size
0x140006689  lea     rcx, [rsp+278h+Buffer]; void *
0x14000668e  call    memset_0
0x140006693  test    [rbx+4], bpl
0x140006697  jz      short loc_1400066BC
0x140006699  mov     ebp, [rbx+0Ch]
0x14000669c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1400066a3  test    rax, rax
0x1400066a6  jz      short loc_1400066EC
0x1400066a8  mov     r8d, 100h
0x1400066ae  lea     rdx, [rsp+278h+Buffer]
0x1400066b3  mov     ecx, ebp
0x1400066b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400066ba  jmp     short loc_1400066EC
0x1400066bc  mov     ebp, [rbx+8]
0x1400066bf  mov     [rsp+278h+Arguments], r15; Arguments
0x1400066c4  mov     [rsp+278h+nSize], 100h; nSize
0x1400066cc  lea     rax, [rsp+278h+Buffer]
0x1400066d1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1400066d6  mov     r9d, 400h; dwLanguageId
0x1400066dc  mov     r8d, ebp; dwMessageId
0x1400066df  xor     edx, edx; lpSource
0x1400066e1  mov     ecx, 1200h; dwFlags
0x1400066e6  call    cs:__imp_FormatMessageW
0x1400066ec  lea     rsi, [r14+rsi*2]
0x1400066f0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1400066f4  mov     rax, [rbx+88h]
0x1400066fb  mov     rcx, [rbx+80h]
0x140006702  mov     rdx, rsi; unsigned __int16 *
0x140006705  test    r9, r9
0x140006708  jz      short loc_14000672C
0x14000670a  mov     [rsp+278h+Arguments], rax
0x14000670f  mov     qword ptr [rsp+278h+nSize], rcx
0x140006714  mov     eax, [rbx+40h]
0x140006717  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000671b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140006722  mov     rcx, r14; pszDest
0x140006725  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000672a  jmp     short loc_140006743
0x14000672c  mov     [rsp+278h+lpBuffer], rax
0x140006731  mov     r9, rcx; unsigned __int16 *
0x140006734  lea     r8, aHsP; "%hs!%p: "
0x14000673b  mov     rcx, r14; pszDest
0x14000673e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006743  mov     r14, rax
0x140006746  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000674d  test    r9, r9
0x140006750  jz      short loc_140006767
0x140006752  lea     r8, aCallerP; "(caller: %p) "
0x140006759  mov     rdx, rsi; unsigned __int16 *
0x14000675c  mov     rcx, rax; pszDest
0x14000675f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006764  mov     r14, rax
0x140006767  call    cs:__imp_GetCurrentThreadId
0x14000676d  lea     rcx, [rsp+278h+Buffer]
0x140006772  mov     [rsp+278h+var_240], rcx
0x140006777  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000677b  mov     [rsp+278h+nSize], eax
0x14000677f  mov     eax, [rbx+44h]
0x140006782  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140006786  mov     r9, rdi; unsigned __int16 *
0x140006789  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140006790  mov     rdx, rsi; unsigned __int16 *
0x140006793  mov     rcx, r14; pszDest
0x140006796  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000679b  cmp     [rbx+18h], r15
0x14000679f  jnz     short loc_1400067B1
0x1400067a1  cmp     [rbx+48h], r15
0x1400067a5  jnz     short loc_1400067B1
0x1400067a7  cmp     [rbx+30h], r15
0x1400067ab  jz      loc_140006841
0x1400067b1  lea     r8, asc_14002ABD0; "    "
0x1400067b8  mov     rdx, rsi; unsigned __int16 *
0x1400067bb  mov     rcx, rax; pszDest
0x1400067be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400067c3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1400067c7  test    r9, r9
0x1400067ca  jz      short loc_1400067DE
0x1400067cc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1400067d3  mov     rdx, rsi; unsigned __int16 *
0x1400067d6  mov     rcx, rax; pszDest
0x1400067d9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400067de  mov     r9, [rbx+48h]; unsigned __int16 *
0x1400067e2  test    r9, r9
0x1400067e5  jz      short loc_1400067F9
0x1400067e7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1400067ee  mov     rdx, rsi; unsigned __int16 *
0x1400067f1  mov     rcx, rax; pszDest
0x1400067f4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400067f9  mov     rcx, [rbx+28h]
0x1400067fd  mov     r9, [rbx+30h]; unsigned __int16 *
0x140006801  mov     rdx, rsi; unsigned __int16 *
0x140006804  test    rcx, rcx
0x140006807  jz      short loc_14000681F
0x140006809  mov     [rsp+278h+lpBuffer], rcx
0x14000680e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140006815  mov     rcx, rax; pszDest
0x140006818  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000681d  jmp     short loc_140006841
0x14000681f  mov     rcx, rax; pszDest
0x140006822  test    r9, r9
0x140006825  jz      short loc_140006835
0x140006827  lea     r8, aHs; "[%hs]\n"
0x14000682e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006833  jmp     short loc_140006841
0x140006835  lea     r8, asc_14002AC48; "\n"
0x14000683c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006841  xor     eax, eax
0x140006843  mov     rcx, [rsp+278h+var_38]
0x14000684b  xor     rcx, rsp; StackCookie
0x14000684e  call    __security_check_cookie
0x140006853  mov     rbx, [rsp+278h+arg_18]
0x14000685b  add     rsp, 250h
0x140006862  pop     r15
0x140006864  pop     r14
0x140006866  pop     rdi
0x140006867  pop     rsi
0x140006868  pop     rbp
0x140006869  retn
```
