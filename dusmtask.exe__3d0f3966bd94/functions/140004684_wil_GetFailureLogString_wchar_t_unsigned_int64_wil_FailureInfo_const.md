# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140004684`
- end: `0x14000493a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x1400027b4`
- `0x140002a34`
- `0x140002d48`
- `0x140005000`
- `0x140006e60`
- `0x140007a27`
- `0x140007b5b`

## callees

- `0x140001470`
- `0x140001f0e`
- `0x140004684`
- `0x140005300`
- `0x140008010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004837`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004837`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400047b6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400047b6`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rsi
  const wchar_t *v11; // r9
  __int64 v12; // rax
  const wchar_t *v13; // rcx
  wchar_t *v14; // rax
  wil::details *v15; // r14
  const wchar_t *v16; // r9
  wil::details *v17; // rax
  const wchar_t *v18; // r9
  wchar_t *v19; // rax
  const wchar_t *v20; // r9
  const wchar_t *v21; // r9
  const wchar_t *v22; // r9
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
          v7 = (const char *)&qword_140009888;
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
  v10 = (wchar_t *)((char *)this + 2 * (_QWORD)a2);
  v11 = *(const wchar_t **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const wchar_t **)(a3 + 128);
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
  v16 = *(const wchar_t **)(a3 + 144);
  if ( v16 )
    v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v15,
                          v10,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const wchar_t *)v7,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v10, L"    ", v18);
    v20 = *(const wchar_t **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const wchar_t **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const wchar_t **)(a3 + 48);
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
0x140004684  mov     [rsp+arg_18], rbx
0x140004689  push    rbp
0x14000468a  push    rsi
0x14000468b  push    rdi
0x14000468c  push    r14
0x14000468e  push    r15
0x140004690  sub     rsp, 250h
0x140004697  mov     rax, cs:__security_cookie
0x14000469e  xor     rax, rsp
0x1400046a1  mov     [rsp+278h+var_38], rax
0x1400046a9  mov     rbx, r8
0x1400046ac  mov     rsi, rdx
0x1400046af  mov     r14, rcx
0x1400046b2  xor     r15d, r15d
0x1400046b5  test    rdx, rdx
0x1400046b8  jz      loc_140004911
0x1400046be  test    rcx, rcx
0x1400046c1  jz      loc_140004911
0x1400046c7  mov     [rcx], r15w
0x1400046cb  mov     rax, cs:g_pfnResultLoggingCallback
0x1400046d2  test    rax, rax
0x1400046d5  jz      short loc_1400046F8
0x1400046d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400046de  jz      short loc_1400046F8
0x1400046e0  mov     r8, rdx
0x1400046e3  mov     rdx, rcx
0x1400046e6  mov     rcx, rbx
0x1400046e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400046ee  cmp     [r14], r15w
0x1400046f2  jnz     loc_140004911
0x1400046f8  mov     ecx, [rbx]
0x1400046fa  mov     bpl, 8
0x1400046fd  test    ecx, ecx
0x1400046ff  jz      short loc_14000474A
0x140004701  sub     ecx, 1
0x140004704  jz      short loc_140004732
0x140004706  sub     ecx, 1
0x140004709  jz      short loc_140004722
0x14000470b  cmp     ecx, 1
0x14000470e  jz      short loc_140004719
0x140004710  lea     rdi, qword_140009888
0x140004717  jmp     short loc_140004751
0x140004719  lea     rdi, aFailfast; "FailFast"
0x140004720  jmp     short loc_140004751
0x140004722  lea     rax, aLoghr; "LogHr"
0x140004729  lea     rdi, aLognt; "LogNt"
0x140004730  jmp     short loc_140004740
0x140004732  lea     rax, aReturnhr; "ReturnHr"
0x140004739  lea     rdi, aReturnnt; "ReturnNt"
0x140004740  test    [rbx+4], bpl
0x140004744  cmovz   rdi, rax
0x140004748  jmp     short loc_140004751
0x14000474a  lea     rdi, aException; "Exception"
0x140004751  xor     edx, edx; Val
0x140004753  mov     r8d, 200h; Size
0x140004759  lea     rcx, [rsp+278h+Buffer]; void *
0x14000475e  call    memset_0
0x140004763  test    [rbx+4], bpl
0x140004767  jz      short loc_14000478C
0x140004769  mov     ebp, [rbx+0Ch]
0x14000476c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x140004773  test    rax, rax
0x140004776  jz      short loc_1400047BC
0x140004778  mov     r8d, 100h
0x14000477e  lea     rdx, [rsp+278h+Buffer]
0x140004783  mov     ecx, ebp
0x140004785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000478a  jmp     short loc_1400047BC
0x14000478c  mov     ebp, [rbx+8]
0x14000478f  mov     [rsp+278h+Arguments], r15; Arguments
0x140004794  mov     [rsp+278h+nSize], 100h; nSize
0x14000479c  lea     rax, [rsp+278h+Buffer]
0x1400047a1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1400047a6  mov     r9d, 400h; dwLanguageId
0x1400047ac  mov     r8d, ebp; dwMessageId
0x1400047af  xor     edx, edx; lpSource
0x1400047b1  mov     ecx, 1200h; dwFlags
0x1400047b6  call    cs:__imp_FormatMessageW
0x1400047bc  lea     rsi, [r14+rsi*2]
0x1400047c0  mov     r9, [rbx+38h]; wchar_t *
0x1400047c4  mov     rax, [rbx+88h]
0x1400047cb  mov     rcx, [rbx+80h]
0x1400047d2  mov     rdx, rsi; wchar_t *
0x1400047d5  test    r9, r9
0x1400047d8  jz      short loc_1400047FC
0x1400047da  mov     [rsp+278h+Arguments], rax
0x1400047df  mov     qword ptr [rsp+278h+nSize], rcx
0x1400047e4  mov     eax, [rbx+40h]
0x1400047e7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400047eb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1400047f2  mov     rcx, r14; this
0x1400047f5  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400047fa  jmp     short loc_140004813
0x1400047fc  mov     [rsp+278h+lpBuffer], rax
0x140004801  mov     r9, rcx; wchar_t *
0x140004804  lea     r8, aHsP; "%hs!%p: "
0x14000480b  mov     rcx, r14; this
0x14000480e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140004813  mov     r14, rax
0x140004816  mov     r9, [rbx+90h]; wchar_t *
0x14000481d  test    r9, r9
0x140004820  jz      short loc_140004837
0x140004822  lea     r8, aCallerP; "(caller: %p) "
0x140004829  mov     rdx, rsi; wchar_t *
0x14000482c  mov     rcx, rax; this
0x14000482f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140004834  mov     r14, rax
0x140004837  call    cs:__imp_GetCurrentThreadId
0x14000483d  lea     rcx, [rsp+278h+Buffer]
0x140004842  mov     [rsp+278h+var_240], rcx
0x140004847  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000484b  mov     [rsp+278h+nSize], eax
0x14000484f  mov     eax, [rbx+44h]
0x140004852  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140004856  mov     r9, rdi; wchar_t *
0x140004859  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140004860  mov     rdx, rsi; wchar_t *
0x140004863  mov     rcx, r14; this
0x140004866  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14000486b  cmp     [rbx+18h], r15
0x14000486f  jnz     short loc_140004881
0x140004871  cmp     [rbx+48h], r15
0x140004875  jnz     short loc_140004881
0x140004877  cmp     [rbx+30h], r15
0x14000487b  jz      loc_140004911
0x140004881  lea     r8, asc_140009978; "    "
0x140004888  mov     rdx, rsi; wchar_t *
0x14000488b  mov     rcx, rax; this
0x14000488e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140004893  mov     r9, [rbx+18h]; wchar_t *
0x140004897  test    r9, r9
0x14000489a  jz      short loc_1400048AE
0x14000489c  lea     r8, aMsgWs; "Msg:[%ws] "
0x1400048a3  mov     rdx, rsi; wchar_t *
0x1400048a6  mov     rcx, rax; this
0x1400048a9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400048ae  mov     r9, [rbx+48h]; wchar_t *
0x1400048b2  test    r9, r9
0x1400048b5  jz      short loc_1400048C9
0x1400048b7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1400048be  mov     rdx, rsi; wchar_t *
0x1400048c1  mov     rcx, rax; this
0x1400048c4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400048c9  mov     rcx, [rbx+28h]
0x1400048cd  mov     r9, [rbx+30h]; wchar_t *
0x1400048d1  mov     rdx, rsi; wchar_t *
0x1400048d4  test    rcx, rcx
0x1400048d7  jz      short loc_1400048EF
0x1400048d9  mov     [rsp+278h+lpBuffer], rcx
0x1400048de  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1400048e5  mov     rcx, rax; this
0x1400048e8  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400048ed  jmp     short loc_140004911
0x1400048ef  mov     rcx, rax; this
0x1400048f2  test    r9, r9
0x1400048f5  jz      short loc_140004905
0x1400048f7  lea     r8, aHs; "[%hs]\n"
0x1400048fe  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140004903  jmp     short loc_140004911
0x140004905  lea     r8, asc_1400099F0; "\n"
0x14000490c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140004911  xor     eax, eax
0x140004913  mov     rcx, [rsp+278h+var_38]
0x14000491b  xor     rcx, rsp; StackCookie
0x14000491e  call    __security_check_cookie
0x140004923  mov     rbx, [rsp+278h+arg_18]
0x14000492b  add     rsp, 250h
0x140004932  pop     r15
0x140004934  pop     r14
0x140004936  pop     rdi
0x140004937  pop     rsi
0x140004938  pop     rbp
0x140004939  retn
```
