# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006684`
- end: `0x18000693a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180007180`
- `0x180009f80`

## callees

- `0x180006684`
- `0x18000747c`
- `0x18000ac8e`
- `0x18000ad30`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800067b6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800067b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006837`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006837`

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
      g_pfnResultLoggingCallback(a3, this, a2, a4);
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
          v7 = (const char *)&qword_18000DDE8;
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
0x180006684  mov     [rsp+arg_18], rbx
0x180006689  push    rbp
0x18000668a  push    rsi
0x18000668b  push    rdi
0x18000668c  push    r14
0x18000668e  push    r15
0x180006690  sub     rsp, 250h
0x180006697  mov     rax, cs:__security_cookie
0x18000669e  xor     rax, rsp
0x1800066a1  mov     [rsp+278h+var_38], rax
0x1800066a9  mov     rbx, r8
0x1800066ac  mov     rsi, rdx
0x1800066af  mov     r14, rcx
0x1800066b2  xor     r15d, r15d
0x1800066b5  test    rdx, rdx
0x1800066b8  jz      loc_180006911
0x1800066be  test    rcx, rcx
0x1800066c1  jz      loc_180006911
0x1800066c7  mov     [rcx], r15w
0x1800066cb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800066d2  test    rax, rax
0x1800066d5  jz      short loc_1800066F8
0x1800066d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800066de  jz      short loc_1800066F8
0x1800066e0  mov     r8, rdx
0x1800066e3  mov     rdx, rcx
0x1800066e6  mov     rcx, rbx
0x1800066e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066ee  cmp     [r14], r15w
0x1800066f2  jnz     loc_180006911
0x1800066f8  mov     ecx, [rbx]
0x1800066fa  mov     bpl, 8
0x1800066fd  test    ecx, ecx
0x1800066ff  jz      short loc_18000674A
0x180006701  sub     ecx, 1
0x180006704  jz      short loc_180006732
0x180006706  sub     ecx, 1
0x180006709  jz      short loc_180006722
0x18000670b  cmp     ecx, 1
0x18000670e  jz      short loc_180006719
0x180006710  lea     rdi, qword_18000DDE8
0x180006717  jmp     short loc_180006751
0x180006719  lea     rdi, aFailfast; "FailFast"
0x180006720  jmp     short loc_180006751
0x180006722  lea     rax, aLoghr; "LogHr"
0x180006729  lea     rdi, aLognt; "LogNt"
0x180006730  jmp     short loc_180006740
0x180006732  lea     rax, aReturnhr; "ReturnHr"
0x180006739  lea     rdi, aReturnnt; "ReturnNt"
0x180006740  test    [rbx+4], bpl
0x180006744  cmovz   rdi, rax
0x180006748  jmp     short loc_180006751
0x18000674a  lea     rdi, aException; "Exception"
0x180006751  xor     edx, edx; Val
0x180006753  mov     r8d, 200h; Size
0x180006759  lea     rcx, [rsp+278h+Buffer]; void *
0x18000675e  call    memset_0
0x180006763  test    [rbx+4], bpl
0x180006767  jz      short loc_18000678C
0x180006769  mov     ebp, [rbx+0Ch]
0x18000676c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180006773  test    rax, rax
0x180006776  jz      short loc_1800067BC
0x180006778  mov     r8d, 100h
0x18000677e  lea     rdx, [rsp+278h+Buffer]
0x180006783  mov     ecx, ebp
0x180006785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000678a  jmp     short loc_1800067BC
0x18000678c  mov     ebp, [rbx+8]
0x18000678f  mov     [rsp+278h+Arguments], r15; Arguments
0x180006794  mov     [rsp+278h+nSize], 100h; nSize
0x18000679c  lea     rax, [rsp+278h+Buffer]
0x1800067a1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800067a6  mov     r9d, 400h; dwLanguageId
0x1800067ac  mov     r8d, ebp; dwMessageId
0x1800067af  xor     edx, edx; lpSource
0x1800067b1  mov     ecx, 1200h; dwFlags
0x1800067b6  call    cs:__imp_FormatMessageW
0x1800067bc  lea     rsi, [r14+rsi*2]
0x1800067c0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800067c4  mov     rax, [rbx+88h]
0x1800067cb  mov     rcx, [rbx+80h]
0x1800067d2  mov     rdx, rsi; unsigned __int16 *
0x1800067d5  test    r9, r9
0x1800067d8  jz      short loc_1800067FC
0x1800067da  mov     [rsp+278h+Arguments], rax
0x1800067df  mov     qword ptr [rsp+278h+nSize], rcx
0x1800067e4  mov     eax, [rbx+40h]
0x1800067e7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800067eb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800067f2  mov     rcx, r14; this
0x1800067f5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800067fa  jmp     short loc_180006813
0x1800067fc  mov     [rsp+278h+lpBuffer], rax
0x180006801  mov     r9, rcx; unsigned __int16 *
0x180006804  lea     r8, aHsP; "%hs!%p: "
0x18000680b  mov     rcx, r14; this
0x18000680e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006813  mov     r14, rax
0x180006816  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000681d  test    r9, r9
0x180006820  jz      short loc_180006837
0x180006822  lea     r8, aCallerP; "(caller: %p) "
0x180006829  mov     rdx, rsi; unsigned __int16 *
0x18000682c  mov     rcx, rax; this
0x18000682f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006834  mov     r14, rax
0x180006837  call    cs:__imp_GetCurrentThreadId
0x18000683d  lea     rcx, [rsp+278h+Buffer]
0x180006842  mov     [rsp+278h+var_240], rcx
0x180006847  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000684b  mov     [rsp+278h+nSize], eax
0x18000684f  mov     eax, [rbx+44h]
0x180006852  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006856  mov     r9, rdi; unsigned __int16 *
0x180006859  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006860  mov     rdx, rsi; unsigned __int16 *
0x180006863  mov     rcx, r14; this
0x180006866  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000686b  cmp     [rbx+18h], r15
0x18000686f  jnz     short loc_180006881
0x180006871  cmp     [rbx+48h], r15
0x180006875  jnz     short loc_180006881
0x180006877  cmp     [rbx+30h], r15
0x18000687b  jz      loc_180006911
0x180006881  lea     r8, asc_18000DED8; "    "
0x180006888  mov     rdx, rsi; unsigned __int16 *
0x18000688b  mov     rcx, rax; this
0x18000688e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006893  mov     r9, [rbx+18h]; unsigned __int16 *
0x180006897  test    r9, r9
0x18000689a  jz      short loc_1800068AE
0x18000689c  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800068a3  mov     rdx, rsi; unsigned __int16 *
0x1800068a6  mov     rcx, rax; this
0x1800068a9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800068ae  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800068b2  test    r9, r9
0x1800068b5  jz      short loc_1800068C9
0x1800068b7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800068be  mov     rdx, rsi; unsigned __int16 *
0x1800068c1  mov     rcx, rax; this
0x1800068c4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800068c9  mov     rcx, [rbx+28h]
0x1800068cd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800068d1  mov     rdx, rsi; unsigned __int16 *
0x1800068d4  test    rcx, rcx
0x1800068d7  jz      short loc_1800068EF
0x1800068d9  mov     [rsp+278h+lpBuffer], rcx
0x1800068de  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800068e5  mov     rcx, rax; this
0x1800068e8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800068ed  jmp     short loc_180006911
0x1800068ef  mov     rcx, rax; this
0x1800068f2  test    r9, r9
0x1800068f5  jz      short loc_180006905
0x1800068f7  lea     r8, aHs; "[%hs]\n"
0x1800068fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006903  jmp     short loc_180006911
0x180006905  lea     r8, asc_18000DF50; "\n"
0x18000690c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006911  xor     eax, eax
0x180006913  mov     rcx, [rsp+278h+var_38]
0x18000691b  xor     rcx, rsp; StackCookie
0x18000691e  call    __security_check_cookie
0x180006923  mov     rbx, [rsp+278h+arg_18]
0x18000692b  add     rsp, 250h
0x180006932  pop     r15
0x180006934  pop     r14
0x180006936  pop     rdi
0x180006937  pop     rsi
0x180006938  pop     rbp
0x180006939  retn
```
