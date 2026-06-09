# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004774`
- end: `0x180004a2a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002c14`
- `0x180005450`
- `0x180008bf0`

## callees

- `0x180004774`
- `0x180005750`
- `0x18002737e`
- `0x1800273b0`
- `0x180029010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x1800048a6`
- `KERNEL32!FormatMessageW` at `0x1800048a6`
- `KERNEL32!GetCurrentThreadId` at `0x180004927`
- `KERNEL32!GetCurrentThreadId` at `0x180004927`

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
          v7 = (const char *)&byte_18002EDF7;
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
0x180004774  mov     [rsp+arg_18], rbx
0x180004779  push    rbp
0x18000477a  push    rsi
0x18000477b  push    rdi
0x18000477c  push    r14
0x18000477e  push    r15
0x180004780  sub     rsp, 250h
0x180004787  mov     rax, cs:__security_cookie
0x18000478e  xor     rax, rsp
0x180004791  mov     [rsp+278h+var_38], rax
0x180004799  mov     rbx, r8
0x18000479c  mov     rsi, rdx
0x18000479f  mov     r14, rcx
0x1800047a2  xor     r15d, r15d
0x1800047a5  test    rdx, rdx
0x1800047a8  jz      loc_180004A01
0x1800047ae  test    rcx, rcx
0x1800047b1  jz      loc_180004A01
0x1800047b7  mov     [rcx], r15w
0x1800047bb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800047c2  test    rax, rax
0x1800047c5  jz      short loc_1800047E8
0x1800047c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800047ce  jz      short loc_1800047E8
0x1800047d0  mov     r8, rdx
0x1800047d3  mov     rdx, rcx
0x1800047d6  mov     rcx, rbx
0x1800047d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047de  cmp     [r14], r15w
0x1800047e2  jnz     loc_180004A01
0x1800047e8  mov     ecx, [rbx]
0x1800047ea  mov     bpl, 8
0x1800047ed  test    ecx, ecx
0x1800047ef  jz      short loc_18000483A
0x1800047f1  sub     ecx, 1
0x1800047f4  jz      short loc_180004822
0x1800047f6  sub     ecx, 1
0x1800047f9  jz      short loc_180004812
0x1800047fb  cmp     ecx, 1
0x1800047fe  jz      short loc_180004809
0x180004800  lea     rdi, byte_18002EDF7
0x180004807  jmp     short loc_180004841
0x180004809  lea     rdi, aFailfast; "FailFast"
0x180004810  jmp     short loc_180004841
0x180004812  lea     rax, aLoghr; "LogHr"
0x180004819  lea     rdi, aLognt; "LogNt"
0x180004820  jmp     short loc_180004830
0x180004822  lea     rax, aReturnhr; "ReturnHr"
0x180004829  lea     rdi, aReturnnt; "ReturnNt"
0x180004830  test    [rbx+4], bpl
0x180004834  cmovz   rdi, rax
0x180004838  jmp     short loc_180004841
0x18000483a  lea     rdi, aException; "Exception"
0x180004841  xor     edx, edx; Val
0x180004843  mov     r8d, 200h; Size
0x180004849  lea     rcx, [rsp+278h+Buffer]; void *
0x18000484e  call    memset_0
0x180004853  test    [rbx+4], bpl
0x180004857  jz      short loc_18000487C
0x180004859  mov     ebp, [rbx+0Ch]
0x18000485c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180004863  test    rax, rax
0x180004866  jz      short loc_1800048AC
0x180004868  mov     r8d, 100h
0x18000486e  lea     rdx, [rsp+278h+Buffer]
0x180004873  mov     ecx, ebp
0x180004875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000487a  jmp     short loc_1800048AC
0x18000487c  mov     ebp, [rbx+8]
0x18000487f  mov     [rsp+278h+Arguments], r15; Arguments
0x180004884  mov     [rsp+278h+nSize], 100h; nSize
0x18000488c  lea     rax, [rsp+278h+Buffer]
0x180004891  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004896  mov     r9d, 400h; dwLanguageId
0x18000489c  mov     r8d, ebp; dwMessageId
0x18000489f  xor     edx, edx; lpSource
0x1800048a1  mov     ecx, 1200h; dwFlags
0x1800048a6  call    cs:__imp_FormatMessageW
0x1800048ac  lea     rsi, [r14+rsi*2]
0x1800048b0  mov     r9, [rbx+38h]; wchar_t *
0x1800048b4  mov     rax, [rbx+88h]
0x1800048bb  mov     rcx, [rbx+80h]
0x1800048c2  mov     rdx, rsi; wchar_t *
0x1800048c5  test    r9, r9
0x1800048c8  jz      short loc_1800048EC
0x1800048ca  mov     [rsp+278h+Arguments], rax
0x1800048cf  mov     qword ptr [rsp+278h+nSize], rcx
0x1800048d4  mov     eax, [rbx+40h]
0x1800048d7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800048db  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800048e2  mov     rcx, r14; this
0x1800048e5  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800048ea  jmp     short loc_180004903
0x1800048ec  mov     [rsp+278h+lpBuffer], rax
0x1800048f1  mov     r9, rcx; wchar_t *
0x1800048f4  lea     r8, aHsP; "%hs!%p: "
0x1800048fb  mov     rcx, r14; this
0x1800048fe  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004903  mov     r14, rax
0x180004906  mov     r9, [rbx+90h]; wchar_t *
0x18000490d  test    r9, r9
0x180004910  jz      short loc_180004927
0x180004912  lea     r8, aCallerP; "(caller: %p) "
0x180004919  mov     rdx, rsi; wchar_t *
0x18000491c  mov     rcx, rax; this
0x18000491f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004924  mov     r14, rax
0x180004927  call    cs:__imp_GetCurrentThreadId
0x18000492d  lea     rcx, [rsp+278h+Buffer]
0x180004932  mov     [rsp+278h+var_240], rcx
0x180004937  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000493b  mov     [rsp+278h+nSize], eax
0x18000493f  mov     eax, [rbx+44h]
0x180004942  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004946  mov     r9, rdi; wchar_t *
0x180004949  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004950  mov     rdx, rsi; wchar_t *
0x180004953  mov     rcx, r14; this
0x180004956  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000495b  cmp     [rbx+18h], r15
0x18000495f  jnz     short loc_180004971
0x180004961  cmp     [rbx+48h], r15
0x180004965  jnz     short loc_180004971
0x180004967  cmp     [rbx+30h], r15
0x18000496b  jz      loc_180004A01
0x180004971  lea     r8, asc_18002EEE0; "    "
0x180004978  mov     rdx, rsi; wchar_t *
0x18000497b  mov     rcx, rax; this
0x18000497e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004983  mov     r9, [rbx+18h]; wchar_t *
0x180004987  test    r9, r9
0x18000498a  jz      short loc_18000499E
0x18000498c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004993  mov     rdx, rsi; wchar_t *
0x180004996  mov     rcx, rax; this
0x180004999  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000499e  mov     r9, [rbx+48h]; wchar_t *
0x1800049a2  test    r9, r9
0x1800049a5  jz      short loc_1800049B9
0x1800049a7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800049ae  mov     rdx, rsi; wchar_t *
0x1800049b1  mov     rcx, rax; this
0x1800049b4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800049b9  mov     rcx, [rbx+28h]
0x1800049bd  mov     r9, [rbx+30h]; wchar_t *
0x1800049c1  mov     rdx, rsi; wchar_t *
0x1800049c4  test    rcx, rcx
0x1800049c7  jz      short loc_1800049DF
0x1800049c9  mov     [rsp+278h+lpBuffer], rcx
0x1800049ce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800049d5  mov     rcx, rax; this
0x1800049d8  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800049dd  jmp     short loc_180004A01
0x1800049df  mov     rcx, rax; this
0x1800049e2  test    r9, r9
0x1800049e5  jz      short loc_1800049F5
0x1800049e7  lea     r8, aHs; "[%hs]\n"
0x1800049ee  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800049f3  jmp     short loc_180004A01
0x1800049f5  lea     r8, asc_18002F2C0; "\n"
0x1800049fc  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004a01  xor     eax, eax
0x180004a03  mov     rcx, [rsp+278h+var_38]
0x180004a0b  xor     rcx, rsp; StackCookie
0x180004a0e  call    __security_check_cookie
0x180004a13  mov     rbx, [rsp+278h+arg_18]
0x180004a1b  add     rsp, 250h
0x180004a22  pop     r15
0x180004a24  pop     r14
0x180004a26  pop     rdi
0x180004a27  pop     rsi
0x180004a28  pop     rbp
0x180004a29  retn
```
