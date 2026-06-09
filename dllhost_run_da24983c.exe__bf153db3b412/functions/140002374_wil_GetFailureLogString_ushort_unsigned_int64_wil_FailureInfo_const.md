# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140002374`
- end: `0x14000262a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140001ed8`
- `0x140002920`

## callees

- `0x140001380`
- `0x140001d16`
- `0x140002374`
- `0x140002c08`
- `0x140004010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002527`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002527`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400024a6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400024a6`

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
          v8 = (const char *)&word_140005470;
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
0x140002374  mov     [rsp+arg_18], rbx
0x140002379  push    rbp
0x14000237a  push    rsi
0x14000237b  push    rdi
0x14000237c  push    r14
0x14000237e  push    r15
0x140002380  sub     rsp, 250h
0x140002387  mov     rax, cs:__security_cookie
0x14000238e  xor     rax, rsp
0x140002391  mov     [rsp+278h+var_38], rax
0x140002399  xor     r15d, r15d
0x14000239c  mov     rbx, r8
0x14000239f  mov     rsi, rdx
0x1400023a2  mov     r14, rcx
0x1400023a5  test    rdx, rdx
0x1400023a8  jz      loc_140002601
0x1400023ae  test    rcx, rcx
0x1400023b1  jz      loc_140002601
0x1400023b7  mov     rax, cs:g_pfnResultLoggingCallback
0x1400023be  mov     [rcx], r15w
0x1400023c2  test    rax, rax
0x1400023c5  jz      short loc_1400023E8
0x1400023c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400023ce  jz      short loc_1400023E8
0x1400023d0  mov     r8, rdx
0x1400023d3  mov     rdx, rcx
0x1400023d6  mov     rcx, rbx
0x1400023d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400023de  cmp     [r14], r15w
0x1400023e2  jnz     loc_140002601
0x1400023e8  mov     ecx, [rbx]
0x1400023ea  mov     bpl, 8
0x1400023ed  test    ecx, ecx
0x1400023ef  jz      short loc_14000243A
0x1400023f1  sub     ecx, 1
0x1400023f4  jz      short loc_140002422
0x1400023f6  sub     ecx, 1
0x1400023f9  jz      short loc_140002412
0x1400023fb  cmp     ecx, 1
0x1400023fe  jz      short loc_140002409
0x140002400  lea     rdi, word_140005470
0x140002407  jmp     short loc_140002441
0x140002409  lea     rdi, aFailfast; "FailFast"
0x140002410  jmp     short loc_140002441
0x140002412  lea     rax, aLoghr; "LogHr"
0x140002419  lea     rdi, aLognt; "LogNt"
0x140002420  jmp     short loc_140002430
0x140002422  lea     rax, aReturnhr; "ReturnHr"
0x140002429  lea     rdi, aReturnnt; "ReturnNt"
0x140002430  test    [rbx+4], bpl
0x140002434  cmovz   rdi, rax
0x140002438  jmp     short loc_140002441
0x14000243a  lea     rdi, aException; "Exception"
0x140002441  xor     edx, edx; Val
0x140002443  lea     rcx, [rsp+278h+Buffer]; void *
0x140002448  mov     r8d, 200h; Size
0x14000244e  call    memset_0
0x140002453  test    [rbx+4], bpl
0x140002457  jz      short loc_14000247C
0x140002459  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140002460  mov     ebp, [rbx+0Ch]
0x140002463  test    rax, rax
0x140002466  jz      short loc_1400024AC
0x140002468  mov     r8d, 100h
0x14000246e  lea     rdx, [rsp+278h+Buffer]
0x140002473  mov     ecx, ebp
0x140002475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000247a  jmp     short loc_1400024AC
0x14000247c  mov     ebp, [rbx+8]
0x14000247f  lea     rax, [rsp+278h+Buffer]
0x140002484  mov     [rsp+278h+Arguments], r15; Arguments
0x140002489  mov     r8d, ebp; dwMessageId
0x14000248c  mov     [rsp+278h+nSize], 100h; nSize
0x140002494  mov     r9d, 400h; dwLanguageId
0x14000249a  xor     edx, edx; lpSource
0x14000249c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1400024a1  mov     ecx, 1200h; dwFlags
0x1400024a6  call    cs:__imp_FormatMessageW
0x1400024ac  mov     r9, [rbx+38h]; unsigned __int16 *
0x1400024b0  lea     rsi, [r14+rsi*2]
0x1400024b4  mov     rax, [rbx+88h]
0x1400024bb  mov     rdx, rsi; unsigned __int16 *
0x1400024be  mov     rcx, [rbx+80h]
0x1400024c5  test    r9, r9
0x1400024c8  jz      short loc_1400024EC
0x1400024ca  mov     [rsp+278h+Arguments], rax
0x1400024cf  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1400024d6  mov     eax, [rbx+40h]
0x1400024d9  mov     qword ptr [rsp+278h+nSize], rcx
0x1400024de  mov     rcx, r14; this
0x1400024e1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400024e5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400024ea  jmp     short loc_140002503
0x1400024ec  mov     r9, rcx; unsigned __int16 *
0x1400024ef  mov     [rsp+278h+lpBuffer], rax
0x1400024f4  mov     rcx, r14; this
0x1400024f7  lea     r8, aHsP; "%hs!%p: "
0x1400024fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140002503  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000250a  mov     r14, rax
0x14000250d  test    r9, r9
0x140002510  jz      short loc_140002527
0x140002512  lea     r8, aCallerP; "(caller: %p) "
0x140002519  mov     rdx, rsi; unsigned __int16 *
0x14000251c  mov     rcx, rax; this
0x14000251f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140002524  mov     r14, rax
0x140002527  call    cs:__imp_GetCurrentThreadId
0x14000252d  lea     rcx, [rsp+278h+Buffer]
0x140002532  mov     r9, rdi; unsigned __int16 *
0x140002535  mov     [rsp+278h+var_240], rcx
0x14000253a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140002541  mov     dword ptr [rsp+278h+Arguments], ebp
0x140002545  mov     rdx, rsi; unsigned __int16 *
0x140002548  mov     [rsp+278h+nSize], eax
0x14000254c  mov     rcx, r14; this
0x14000254f  mov     eax, [rbx+44h]
0x140002552  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140002556  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000255b  cmp     [rbx+18h], r15
0x14000255f  jnz     short loc_140002571
0x140002561  cmp     [rbx+48h], r15
0x140002565  jnz     short loc_140002571
0x140002567  cmp     [rbx+30h], r15
0x14000256b  jz      loc_140002601
0x140002571  lea     r8, asc_140005560; "    "
0x140002578  mov     rdx, rsi; unsigned __int16 *
0x14000257b  mov     rcx, rax; this
0x14000257e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140002583  mov     r9, [rbx+18h]; unsigned __int16 *
0x140002587  test    r9, r9
0x14000258a  jz      short loc_14000259E
0x14000258c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140002593  mov     rdx, rsi; unsigned __int16 *
0x140002596  mov     rcx, rax; this
0x140002599  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000259e  mov     r9, [rbx+48h]; unsigned __int16 *
0x1400025a2  test    r9, r9
0x1400025a5  jz      short loc_1400025B9
0x1400025a7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1400025ae  mov     rdx, rsi; unsigned __int16 *
0x1400025b1  mov     rcx, rax; this
0x1400025b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400025b9  mov     rcx, [rbx+28h]
0x1400025bd  mov     rdx, rsi; unsigned __int16 *
0x1400025c0  mov     r9, [rbx+30h]; unsigned __int16 *
0x1400025c4  test    rcx, rcx
0x1400025c7  jz      short loc_1400025DF
0x1400025c9  mov     [rsp+278h+lpBuffer], rcx
0x1400025ce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1400025d5  mov     rcx, rax; this
0x1400025d8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400025dd  jmp     short loc_140002601
0x1400025df  mov     rcx, rax; this
0x1400025e2  test    r9, r9
0x1400025e5  jz      short loc_1400025F5
0x1400025e7  lea     r8, aHs; "[%hs]\n"
0x1400025ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400025f3  jmp     short loc_140002601
0x1400025f5  lea     r8, asc_1400055D8; "\n"
0x1400025fc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140002601  xor     eax, eax
0x140002603  mov     rcx, [rsp+278h+var_38]
0x14000260b  xor     rcx, rsp; StackCookie
0x14000260e  call    __security_check_cookie
0x140002613  mov     rbx, [rsp+278h+arg_18]
0x14000261b  add     rsp, 250h
0x140002622  pop     r15
0x140002624  pop     r14
0x140002626  pop     rdi
0x140002627  pop     rsi
0x140002628  pop     rbp
0x140002629  retn
```
