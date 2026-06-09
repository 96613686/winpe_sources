# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004684`
- end: `0x18000493a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wchar_t *this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002d98`
- `0x180005188`
- `0x1800080c0`

## callees

- `0x180004684`
- `0x1800054a8`
- `0x180023c5a`
- `0x180023ca0`
- `0x180026010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x1800047b6`
- `KERNEL32!FormatMessageW` at `0x1800047b6`
- `KERNEL32!GetCurrentThreadId` at `0x180004837`
- `KERNEL32!GetCurrentThreadId` at `0x180004837`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wchar_t *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rsi
  const wchar_t *v11; // r9
  __int64 v12; // rax
  const wchar_t *v13; // rcx
  wchar_t *v14; // rax
  wchar_t *v15; // r14
  const wchar_t *v16; // r9
  wchar_t *v17; // rax
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
  *this = 0;
  if ( g_pfnResultLoggingCallback )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      g_pfnResultLoggingCallback(a3, this, a2);
      if ( *this )
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
          v7 = (const char *)&qword_180031340;
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
  v10 = &this[(_QWORD)a2];
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
  v15 = v14;
  v16 = *(const wchar_t **)(a3 + 144);
  if ( v16 )
    v15 = wil::details::LogStringPrintf(v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = wil::details::LogStringPrintf(
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
      v19 = wil::details::LogStringPrintf(v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const wchar_t **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf(v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const wchar_t **)(a3 + 48);
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
0x180004684  mov     [rsp+arg_18], rbx
0x180004689  push    rbp
0x18000468a  push    rsi
0x18000468b  push    rdi
0x18000468c  push    r14
0x18000468e  push    r15
0x180004690  sub     rsp, 250h
0x180004697  mov     rax, cs:__security_cookie
0x18000469e  xor     rax, rsp
0x1800046a1  mov     [rsp+278h+var_38], rax
0x1800046a9  mov     rbx, r8
0x1800046ac  mov     rsi, rdx
0x1800046af  mov     r14, rcx
0x1800046b2  xor     r15d, r15d
0x1800046b5  test    rdx, rdx
0x1800046b8  jz      loc_180004911
0x1800046be  test    rcx, rcx
0x1800046c1  jz      loc_180004911
0x1800046c7  mov     [rcx], r15w
0x1800046cb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800046d2  test    rax, rax
0x1800046d5  jz      short loc_1800046F8
0x1800046d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800046de  jz      short loc_1800046F8
0x1800046e0  mov     r8, rdx
0x1800046e3  mov     rdx, rcx
0x1800046e6  mov     rcx, rbx
0x1800046e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046ee  cmp     [r14], r15w
0x1800046f2  jnz     loc_180004911
0x1800046f8  mov     ecx, [rbx]
0x1800046fa  mov     bpl, 8
0x1800046fd  test    ecx, ecx
0x1800046ff  jz      short loc_18000474A
0x180004701  sub     ecx, 1
0x180004704  jz      short loc_180004732
0x180004706  sub     ecx, 1
0x180004709  jz      short loc_180004722
0x18000470b  cmp     ecx, 1
0x18000470e  jz      short loc_180004719
0x180004710  lea     rdi, qword_180031340
0x180004717  jmp     short loc_180004751
0x180004719  lea     rdi, aFailfast; "FailFast"
0x180004720  jmp     short loc_180004751
0x180004722  lea     rax, aLoghr; "LogHr"
0x180004729  lea     rdi, aLognt; "LogNt"
0x180004730  jmp     short loc_180004740
0x180004732  lea     rax, aReturnhr; "ReturnHr"
0x180004739  lea     rdi, aReturnnt; "ReturnNt"
0x180004740  test    [rbx+4], bpl
0x180004744  cmovz   rdi, rax
0x180004748  jmp     short loc_180004751
0x18000474a  lea     rdi, aException; "Exception"
0x180004751  xor     edx, edx; Val
0x180004753  mov     r8d, 200h; Size
0x180004759  lea     rcx, [rsp+278h+Buffer]; void *
0x18000475e  call    memset_0
0x180004763  test    [rbx+4], bpl
0x180004767  jz      short loc_18000478C
0x180004769  mov     ebp, [rbx+0Ch]
0x18000476c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180004773  test    rax, rax
0x180004776  jz      short loc_1800047BC
0x180004778  mov     r8d, 100h
0x18000477e  lea     rdx, [rsp+278h+Buffer]
0x180004783  mov     ecx, ebp
0x180004785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000478a  jmp     short loc_1800047BC
0x18000478c  mov     ebp, [rbx+8]
0x18000478f  mov     [rsp+278h+Arguments], r15; Arguments
0x180004794  mov     [rsp+278h+nSize], 100h; nSize
0x18000479c  lea     rax, [rsp+278h+Buffer]
0x1800047a1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800047a6  mov     r9d, 400h; dwLanguageId
0x1800047ac  mov     r8d, ebp; dwMessageId
0x1800047af  xor     edx, edx; lpSource
0x1800047b1  mov     ecx, 1200h; dwFlags
0x1800047b6  call    cs:__imp_FormatMessageW
0x1800047bc  lea     rsi, [r14+rsi*2]
0x1800047c0  mov     r9, [rbx+38h]; wchar_t *
0x1800047c4  mov     rax, [rbx+88h]
0x1800047cb  mov     rcx, [rbx+80h]
0x1800047d2  mov     rdx, rsi; wchar_t *
0x1800047d5  test    r9, r9
0x1800047d8  jz      short loc_1800047FC
0x1800047da  mov     [rsp+278h+Arguments], rax
0x1800047df  mov     qword ptr [rsp+278h+nSize], rcx
0x1800047e4  mov     eax, [rbx+40h]
0x1800047e7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800047eb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800047f2  mov     rcx, r14; this
0x1800047f5  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800047fa  jmp     short loc_180004813
0x1800047fc  mov     [rsp+278h+lpBuffer], rax
0x180004801  mov     r9, rcx; wchar_t *
0x180004804  lea     r8, aHsP; "%hs!%p: "
0x18000480b  mov     rcx, r14; this
0x18000480e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004813  mov     r14, rax
0x180004816  mov     r9, [rbx+90h]; wchar_t *
0x18000481d  test    r9, r9
0x180004820  jz      short loc_180004837
0x180004822  lea     r8, aCallerP; "(caller: %p) "
0x180004829  mov     rdx, rsi; wchar_t *
0x18000482c  mov     rcx, rax; this
0x18000482f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004834  mov     r14, rax
0x180004837  call    cs:__imp_GetCurrentThreadId
0x18000483d  lea     rcx, [rsp+278h+Buffer]
0x180004842  mov     [rsp+278h+var_240], rcx
0x180004847  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000484b  mov     [rsp+278h+nSize], eax
0x18000484f  mov     eax, [rbx+44h]
0x180004852  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004856  mov     r9, rdi; wchar_t *
0x180004859  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004860  mov     rdx, rsi; wchar_t *
0x180004863  mov     rcx, r14; this
0x180004866  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000486b  cmp     [rbx+18h], r15
0x18000486f  jnz     short loc_180004881
0x180004871  cmp     [rbx+48h], r15
0x180004875  jnz     short loc_180004881
0x180004877  cmp     [rbx+30h], r15
0x18000487b  jz      loc_180004911
0x180004881  lea     r8, asc_180031430; "    "
0x180004888  mov     rdx, rsi; wchar_t *
0x18000488b  mov     rcx, rax; this
0x18000488e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004893  mov     r9, [rbx+18h]; wchar_t *
0x180004897  test    r9, r9
0x18000489a  jz      short loc_1800048AE
0x18000489c  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800048a3  mov     rdx, rsi; wchar_t *
0x1800048a6  mov     rcx, rax; this
0x1800048a9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800048ae  mov     r9, [rbx+48h]; wchar_t *
0x1800048b2  test    r9, r9
0x1800048b5  jz      short loc_1800048C9
0x1800048b7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800048be  mov     rdx, rsi; wchar_t *
0x1800048c1  mov     rcx, rax; this
0x1800048c4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800048c9  mov     rcx, [rbx+28h]
0x1800048cd  mov     r9, [rbx+30h]; wchar_t *
0x1800048d1  mov     rdx, rsi; wchar_t *
0x1800048d4  test    rcx, rcx
0x1800048d7  jz      short loc_1800048EF
0x1800048d9  mov     [rsp+278h+lpBuffer], rcx
0x1800048de  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800048e5  mov     rcx, rax; this
0x1800048e8  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800048ed  jmp     short loc_180004911
0x1800048ef  mov     rcx, rax; this
0x1800048f2  test    r9, r9
0x1800048f5  jz      short loc_180004905
0x1800048f7  lea     r8, aHs; "[%hs]\n"
0x1800048fe  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004903  jmp     short loc_180004911
0x180004905  lea     r8, asc_1800314A8; "\n"
0x18000490c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004911  xor     eax, eax
0x180004913  mov     rcx, [rsp+278h+var_38]
0x18000491b  xor     rcx, rsp; StackCookie
0x18000491e  call    __security_check_cookie
0x180004923  mov     rbx, [rsp+278h+arg_18]
0x18000492b  add     rsp, 250h
0x180004932  pop     r15
0x180004934  pop     r14
0x180004936  pop     rdi
0x180004937  pop     rsi
0x180004938  pop     rbp
0x180004939  retn
```
