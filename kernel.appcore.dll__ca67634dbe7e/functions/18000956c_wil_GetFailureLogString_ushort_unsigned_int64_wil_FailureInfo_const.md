# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000956c`
- end: `0x180009822`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180005a4c`

## callees

- `0x18000956c`
- `0x180009828`
- `0x180009d9e`
- `0x180009dd0`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000971f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000971f`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000969e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000969e`

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
          v8 = (const char *)&word_18000D0DE;
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
0x18000956c  mov     [rsp+arg_18], rbx
0x180009571  push    rbp
0x180009572  push    rsi
0x180009573  push    rdi
0x180009574  push    r14
0x180009576  push    r15
0x180009578  sub     rsp, 250h
0x18000957f  mov     rax, cs:__security_cookie
0x180009586  xor     rax, rsp
0x180009589  mov     [rsp+278h+var_38], rax
0x180009591  xor     r15d, r15d
0x180009594  mov     rbx, r8
0x180009597  mov     rsi, rdx
0x18000959a  mov     r14, rcx
0x18000959d  test    rdx, rdx
0x1800095a0  jz      loc_1800097F9
0x1800095a6  test    rcx, rcx
0x1800095a9  jz      loc_1800097F9
0x1800095af  mov     rax, cs:g_pfnResultLoggingCallback
0x1800095b6  mov     [rcx], r15w
0x1800095ba  test    rax, rax
0x1800095bd  jz      short loc_1800095E0
0x1800095bf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800095c6  jz      short loc_1800095E0
0x1800095c8  mov     r8, rdx
0x1800095cb  mov     rdx, rcx
0x1800095ce  mov     rcx, rbx
0x1800095d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095d6  cmp     [r14], r15w
0x1800095da  jnz     loc_1800097F9
0x1800095e0  mov     ecx, [rbx]
0x1800095e2  mov     bpl, 8
0x1800095e5  test    ecx, ecx
0x1800095e7  jz      short loc_180009632
0x1800095e9  sub     ecx, 1
0x1800095ec  jz      short loc_18000961A
0x1800095ee  sub     ecx, 1
0x1800095f1  jz      short loc_18000960A
0x1800095f3  cmp     ecx, 1
0x1800095f6  jz      short loc_180009601
0x1800095f8  lea     rdi, word_18000D0DE
0x1800095ff  jmp     short loc_180009639
0x180009601  lea     rdi, aFailfast; "FailFast"
0x180009608  jmp     short loc_180009639
0x18000960a  lea     rax, aLoghr; "LogHr"
0x180009611  lea     rdi, aLognt; "LogNt"
0x180009618  jmp     short loc_180009628
0x18000961a  lea     rax, aReturnhr; "ReturnHr"
0x180009621  lea     rdi, aReturnnt; "ReturnNt"
0x180009628  test    [rbx+4], bpl
0x18000962c  cmovz   rdi, rax
0x180009630  jmp     short loc_180009639
0x180009632  lea     rdi, aException; "Exception"
0x180009639  xor     edx, edx; Val
0x18000963b  lea     rcx, [rsp+278h+Buffer]; void *
0x180009640  mov     r8d, 200h; Size
0x180009646  call    memset_0
0x18000964b  test    [rbx+4], bpl
0x18000964f  jz      short loc_180009674
0x180009651  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180009658  mov     ebp, [rbx+0Ch]
0x18000965b  test    rax, rax
0x18000965e  jz      short loc_1800096A4
0x180009660  mov     r8d, 100h
0x180009666  lea     rdx, [rsp+278h+Buffer]
0x18000966b  mov     ecx, ebp
0x18000966d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009672  jmp     short loc_1800096A4
0x180009674  mov     ebp, [rbx+8]
0x180009677  lea     rax, [rsp+278h+Buffer]
0x18000967c  mov     [rsp+278h+Arguments], r15; Arguments
0x180009681  mov     r8d, ebp; dwMessageId
0x180009684  mov     [rsp+278h+nSize], 100h; nSize
0x18000968c  mov     r9d, 400h; dwLanguageId
0x180009692  xor     edx, edx; lpSource
0x180009694  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180009699  mov     ecx, 1200h; dwFlags
0x18000969e  call    cs:__imp_FormatMessageW
0x1800096a4  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800096a8  lea     rsi, [r14+rsi*2]
0x1800096ac  mov     rax, [rbx+88h]
0x1800096b3  mov     rdx, rsi; unsigned __int16 *
0x1800096b6  mov     rcx, [rbx+80h]
0x1800096bd  test    r9, r9
0x1800096c0  jz      short loc_1800096E4
0x1800096c2  mov     [rsp+278h+Arguments], rax
0x1800096c7  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800096ce  mov     eax, [rbx+40h]
0x1800096d1  mov     qword ptr [rsp+278h+nSize], rcx
0x1800096d6  mov     rcx, r14; this
0x1800096d9  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800096dd  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800096e2  jmp     short loc_1800096FB
0x1800096e4  mov     r9, rcx; unsigned __int16 *
0x1800096e7  mov     [rsp+278h+lpBuffer], rax
0x1800096ec  mov     rcx, r14; this
0x1800096ef  lea     r8, aHsP; "%hs!%p: "
0x1800096f6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800096fb  mov     r9, [rbx+90h]; unsigned __int16 *
0x180009702  mov     r14, rax
0x180009705  test    r9, r9
0x180009708  jz      short loc_18000971F
0x18000970a  lea     r8, aCallerP; "(caller: %p) "
0x180009711  mov     rdx, rsi; unsigned __int16 *
0x180009714  mov     rcx, rax; this
0x180009717  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000971c  mov     r14, rax
0x18000971f  call    cs:__imp_GetCurrentThreadId
0x180009725  lea     rcx, [rsp+278h+Buffer]
0x18000972a  mov     r9, rdi; unsigned __int16 *
0x18000972d  mov     [rsp+278h+var_240], rcx
0x180009732  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180009739  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000973d  mov     rdx, rsi; unsigned __int16 *
0x180009740  mov     [rsp+278h+nSize], eax
0x180009744  mov     rcx, r14; this
0x180009747  mov     eax, [rbx+44h]
0x18000974a  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000974e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009753  cmp     [rbx+18h], r15
0x180009757  jnz     short loc_180009769
0x180009759  cmp     [rbx+48h], r15
0x18000975d  jnz     short loc_180009769
0x18000975f  cmp     [rbx+30h], r15
0x180009763  jz      loc_1800097F9
0x180009769  lea     r8, asc_18000D1C8; "    "
0x180009770  mov     rdx, rsi; unsigned __int16 *
0x180009773  mov     rcx, rax; this
0x180009776  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000977b  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000977f  test    r9, r9
0x180009782  jz      short loc_180009796
0x180009784  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000978b  mov     rdx, rsi; unsigned __int16 *
0x18000978e  mov     rcx, rax; this
0x180009791  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009796  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000979a  test    r9, r9
0x18000979d  jz      short loc_1800097B1
0x18000979f  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800097a6  mov     rdx, rsi; unsigned __int16 *
0x1800097a9  mov     rcx, rax; this
0x1800097ac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800097b1  mov     rcx, [rbx+28h]
0x1800097b5  mov     rdx, rsi; unsigned __int16 *
0x1800097b8  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800097bc  test    rcx, rcx
0x1800097bf  jz      short loc_1800097D7
0x1800097c1  mov     [rsp+278h+lpBuffer], rcx
0x1800097c6  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800097cd  mov     rcx, rax; this
0x1800097d0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800097d5  jmp     short loc_1800097F9
0x1800097d7  mov     rcx, rax; this
0x1800097da  test    r9, r9
0x1800097dd  jz      short loc_1800097ED
0x1800097df  lea     r8, aHs; "[%hs]\n"
0x1800097e6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800097eb  jmp     short loc_1800097F9
0x1800097ed  lea     r8, asc_18000D240; "\n"
0x1800097f4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800097f9  xor     eax, eax
0x1800097fb  mov     rcx, [rsp+278h+var_38]
0x180009803  xor     rcx, rsp; StackCookie
0x180009806  call    __security_check_cookie
0x18000980b  mov     rbx, [rsp+278h+arg_18]
0x180009813  add     rsp, 250h
0x18000981a  pop     r15
0x18000981c  pop     r14
0x18000981e  pop     rdi
0x18000981f  pop     rsi
0x180009820  pop     rbp
0x180009821  retn
```
