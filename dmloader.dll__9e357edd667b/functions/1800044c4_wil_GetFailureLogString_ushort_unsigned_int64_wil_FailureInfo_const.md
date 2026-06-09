# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800044c4`
- end: `0x18000477a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002390`
- `0x1800025f8`
- `0x180004e40`

## callees

- `0x1800015d0`
- `0x180001ef0`
- `0x1800044c4`
- `0x180005140`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004677`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004677`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800045f6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800045f6`

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
          v8 = (const char *)&qword_180011C80;
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
0x1800044c4  mov     [rsp+arg_18], rbx
0x1800044c9  push    rbp
0x1800044ca  push    rsi
0x1800044cb  push    rdi
0x1800044cc  push    r14
0x1800044ce  push    r15
0x1800044d0  sub     rsp, 250h
0x1800044d7  mov     rax, cs:__security_cookie
0x1800044de  xor     rax, rsp
0x1800044e1  mov     [rsp+278h+var_38], rax
0x1800044e9  xor     r15d, r15d
0x1800044ec  mov     rbx, r8
0x1800044ef  mov     rsi, rdx
0x1800044f2  mov     r14, rcx
0x1800044f5  test    rdx, rdx
0x1800044f8  jz      loc_180004751
0x1800044fe  test    rcx, rcx
0x180004501  jz      loc_180004751
0x180004507  mov     rax, cs:g_pfnResultLoggingCallback
0x18000450e  mov     [rcx], r15w
0x180004512  test    rax, rax
0x180004515  jz      short loc_180004538
0x180004517  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000451e  jz      short loc_180004538
0x180004520  mov     r8, rdx
0x180004523  mov     rdx, rcx
0x180004526  mov     rcx, rbx
0x180004529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000452e  cmp     [r14], r15w
0x180004532  jnz     loc_180004751
0x180004538  mov     ecx, [rbx]
0x18000453a  mov     bpl, 8
0x18000453d  test    ecx, ecx
0x18000453f  jz      short loc_18000458A
0x180004541  sub     ecx, 1
0x180004544  jz      short loc_180004572
0x180004546  sub     ecx, 1
0x180004549  jz      short loc_180004562
0x18000454b  cmp     ecx, 1
0x18000454e  jz      short loc_180004559
0x180004550  lea     rdi, qword_180011C80
0x180004557  jmp     short loc_180004591
0x180004559  lea     rdi, aFailfast; "FailFast"
0x180004560  jmp     short loc_180004591
0x180004562  lea     rax, aLoghr; "LogHr"
0x180004569  lea     rdi, aLognt; "LogNt"
0x180004570  jmp     short loc_180004580
0x180004572  lea     rax, aReturnhr; "ReturnHr"
0x180004579  lea     rdi, aReturnnt; "ReturnNt"
0x180004580  test    [rbx+4], bpl
0x180004584  cmovz   rdi, rax
0x180004588  jmp     short loc_180004591
0x18000458a  lea     rdi, aException; "Exception"
0x180004591  xor     edx, edx; Val
0x180004593  lea     rcx, [rsp+278h+Buffer]; void *
0x180004598  mov     r8d, 200h; Size
0x18000459e  call    memset_0
0x1800045a3  test    [rbx+4], bpl
0x1800045a7  jz      short loc_1800045CC
0x1800045a9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800045b0  mov     ebp, [rbx+0Ch]
0x1800045b3  test    rax, rax
0x1800045b6  jz      short loc_1800045FC
0x1800045b8  mov     r8d, 100h
0x1800045be  lea     rdx, [rsp+278h+Buffer]
0x1800045c3  mov     ecx, ebp
0x1800045c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045ca  jmp     short loc_1800045FC
0x1800045cc  mov     ebp, [rbx+8]
0x1800045cf  lea     rax, [rsp+278h+Buffer]
0x1800045d4  mov     [rsp+278h+Arguments], r15; Arguments
0x1800045d9  mov     r8d, ebp; dwMessageId
0x1800045dc  mov     [rsp+278h+nSize], 100h; nSize
0x1800045e4  mov     r9d, 400h; dwLanguageId
0x1800045ea  xor     edx, edx; lpSource
0x1800045ec  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800045f1  mov     ecx, 1200h; dwFlags
0x1800045f6  call    cs:__imp_FormatMessageW
0x1800045fc  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004600  lea     rsi, [r14+rsi*2]
0x180004604  mov     rax, [rbx+88h]
0x18000460b  mov     rdx, rsi; unsigned __int16 *
0x18000460e  mov     rcx, [rbx+80h]
0x180004615  test    r9, r9
0x180004618  jz      short loc_18000463C
0x18000461a  mov     [rsp+278h+Arguments], rax
0x18000461f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004626  mov     eax, [rbx+40h]
0x180004629  mov     qword ptr [rsp+278h+nSize], rcx
0x18000462e  mov     rcx, r14; this
0x180004631  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004635  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000463a  jmp     short loc_180004653
0x18000463c  mov     r9, rcx; unsigned __int16 *
0x18000463f  mov     [rsp+278h+lpBuffer], rax
0x180004644  mov     rcx, r14; this
0x180004647  lea     r8, aHsP; "%hs!%p: "
0x18000464e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004653  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000465a  mov     r14, rax
0x18000465d  test    r9, r9
0x180004660  jz      short loc_180004677
0x180004662  lea     r8, aCallerP; "(caller: %p) "
0x180004669  mov     rdx, rsi; unsigned __int16 *
0x18000466c  mov     rcx, rax; this
0x18000466f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004674  mov     r14, rax
0x180004677  call    cs:__imp_GetCurrentThreadId
0x18000467d  lea     rcx, [rsp+278h+Buffer]
0x180004682  mov     r9, rdi; unsigned __int16 *
0x180004685  mov     [rsp+278h+var_240], rcx
0x18000468a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004691  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004695  mov     rdx, rsi; unsigned __int16 *
0x180004698  mov     [rsp+278h+nSize], eax
0x18000469c  mov     rcx, r14; this
0x18000469f  mov     eax, [rbx+44h]
0x1800046a2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800046a6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800046ab  cmp     [rbx+18h], r15
0x1800046af  jnz     short loc_1800046C1
0x1800046b1  cmp     [rbx+48h], r15
0x1800046b5  jnz     short loc_1800046C1
0x1800046b7  cmp     [rbx+30h], r15
0x1800046bb  jz      loc_180004751
0x1800046c1  lea     r8, asc_180011D70; "    "
0x1800046c8  mov     rdx, rsi; unsigned __int16 *
0x1800046cb  mov     rcx, rax; this
0x1800046ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800046d3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800046d7  test    r9, r9
0x1800046da  jz      short loc_1800046EE
0x1800046dc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800046e3  mov     rdx, rsi; unsigned __int16 *
0x1800046e6  mov     rcx, rax; this
0x1800046e9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800046ee  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800046f2  test    r9, r9
0x1800046f5  jz      short loc_180004709
0x1800046f7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800046fe  mov     rdx, rsi; unsigned __int16 *
0x180004701  mov     rcx, rax; this
0x180004704  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004709  mov     rcx, [rbx+28h]
0x18000470d  mov     rdx, rsi; unsigned __int16 *
0x180004710  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004714  test    rcx, rcx
0x180004717  jz      short loc_18000472F
0x180004719  mov     [rsp+278h+lpBuffer], rcx
0x18000471e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004725  mov     rcx, rax; this
0x180004728  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000472d  jmp     short loc_180004751
0x18000472f  mov     rcx, rax; this
0x180004732  test    r9, r9
0x180004735  jz      short loc_180004745
0x180004737  lea     r8, aHs; "[%hs]\n"
0x18000473e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004743  jmp     short loc_180004751
0x180004745  lea     r8, asc_180011DE8; "\n"
0x18000474c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004751  xor     eax, eax
0x180004753  mov     rcx, [rsp+278h+var_38]
0x18000475b  xor     rcx, rsp; StackCookie
0x18000475e  call    __security_check_cookie
0x180004763  mov     rbx, [rsp+278h+arg_18]
0x18000476b  add     rsp, 250h
0x180004772  pop     r15
0x180004774  pop     r14
0x180004776  pop     rdi
0x180004777  pop     rsi
0x180004778  pop     rbp
0x180004779  retn
```
