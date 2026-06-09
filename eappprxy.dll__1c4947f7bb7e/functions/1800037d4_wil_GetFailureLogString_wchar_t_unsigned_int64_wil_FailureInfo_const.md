# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800037d4`
- end: `0x180003a97`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000259c`
- `0x180002820`
- `0x18000420c`
- `0x180005f40`

## callees

- `0x180001780`
- `0x180002106`
- `0x1800037d4`
- `0x180004520`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003906`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003906`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000398d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000398d`

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
          v7 = (const char *)&qword_1800108E0;
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
0x1800037d4  mov     [rsp+arg_18], rbx
0x1800037d9  push    rbp
0x1800037da  push    rsi
0x1800037db  push    rdi
0x1800037dc  push    r14
0x1800037de  push    r15
0x1800037e0  sub     rsp, 250h
0x1800037e7  mov     rax, cs:__security_cookie
0x1800037ee  xor     rax, rsp
0x1800037f1  mov     [rsp+278h+var_38], rax
0x1800037f9  mov     rbx, r8
0x1800037fc  mov     rsi, rdx
0x1800037ff  mov     r14, rcx
0x180003802  xor     r15d, r15d
0x180003805  test    rdx, rdx
0x180003808  jz      loc_180003A6D
0x18000380e  test    rcx, rcx
0x180003811  jz      loc_180003A6D
0x180003817  mov     [rcx], r15w
0x18000381b  mov     rax, cs:g_pfnResultLoggingCallback
0x180003822  test    rax, rax
0x180003825  jz      short loc_180003848
0x180003827  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000382e  jz      short loc_180003848
0x180003830  mov     r8, rdx
0x180003833  mov     rdx, rcx
0x180003836  mov     rcx, rbx
0x180003839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000383e  cmp     [r14], r15w
0x180003842  jnz     loc_180003A6D
0x180003848  mov     ecx, [rbx]
0x18000384a  mov     bpl, 8
0x18000384d  test    ecx, ecx
0x18000384f  jz      short loc_18000389A
0x180003851  sub     ecx, 1
0x180003854  jz      short loc_180003882
0x180003856  sub     ecx, 1
0x180003859  jz      short loc_180003872
0x18000385b  cmp     ecx, 1
0x18000385e  jz      short loc_180003869
0x180003860  lea     rdi, qword_1800108E0
0x180003867  jmp     short loc_1800038A1
0x180003869  lea     rdi, aFailfast; "FailFast"
0x180003870  jmp     short loc_1800038A1
0x180003872  lea     rax, aLoghr; "LogHr"
0x180003879  lea     rdi, aLognt; "LogNt"
0x180003880  jmp     short loc_180003890
0x180003882  lea     rax, aReturnhr; "ReturnHr"
0x180003889  lea     rdi, aReturnnt; "ReturnNt"
0x180003890  test    [rbx+4], bpl
0x180003894  cmovz   rdi, rax
0x180003898  jmp     short loc_1800038A1
0x18000389a  lea     rdi, aException; "Exception"
0x1800038a1  xor     edx, edx; Val
0x1800038a3  mov     r8d, 200h; Size
0x1800038a9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800038ae  call    memset_0
0x1800038b3  test    [rbx+4], bpl
0x1800038b7  jz      short loc_1800038DC
0x1800038b9  mov     ebp, [rbx+0Ch]
0x1800038bc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x1800038c3  test    rax, rax
0x1800038c6  jz      short loc_180003912
0x1800038c8  mov     r8d, 100h
0x1800038ce  lea     rdx, [rsp+278h+Buffer]
0x1800038d3  mov     ecx, ebp
0x1800038d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038da  jmp     short loc_180003912
0x1800038dc  mov     ebp, [rbx+8]
0x1800038df  mov     [rsp+278h+Arguments], r15; Arguments
0x1800038e4  mov     [rsp+278h+nSize], 100h; nSize
0x1800038ec  lea     rax, [rsp+278h+Buffer]
0x1800038f1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800038f6  mov     r9d, 400h; dwLanguageId
0x1800038fc  mov     r8d, ebp; dwMessageId
0x1800038ff  xor     edx, edx; lpSource
0x180003901  mov     ecx, 1200h; dwFlags
0x180003906  call    cs:__imp_FormatMessageW
0x18000390d  nop     dword ptr [rax+rax+00h]
0x180003912  lea     rsi, [r14+rsi*2]
0x180003916  mov     r9, [rbx+38h]; wchar_t *
0x18000391a  mov     rax, [rbx+88h]
0x180003921  mov     rcx, [rbx+80h]
0x180003928  mov     rdx, rsi; wchar_t *
0x18000392b  test    r9, r9
0x18000392e  jz      short loc_180003952
0x180003930  mov     [rsp+278h+Arguments], rax
0x180003935  mov     qword ptr [rsp+278h+nSize], rcx
0x18000393a  mov     eax, [rbx+40h]
0x18000393d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003941  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180003948  mov     rcx, r14; this
0x18000394b  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180003950  jmp     short loc_180003969
0x180003952  mov     [rsp+278h+lpBuffer], rax
0x180003957  mov     r9, rcx; wchar_t *
0x18000395a  lea     r8, aHsP; "%hs!%p: "
0x180003961  mov     rcx, r14; this
0x180003964  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180003969  mov     r14, rax
0x18000396c  mov     r9, [rbx+90h]; wchar_t *
0x180003973  test    r9, r9
0x180003976  jz      short loc_18000398D
0x180003978  lea     r8, aCallerP; "(caller: %p) "
0x18000397f  mov     rdx, rsi; wchar_t *
0x180003982  mov     rcx, rax; this
0x180003985  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000398a  mov     r14, rax
0x18000398d  call    cs:__imp_GetCurrentThreadId
0x180003994  nop     dword ptr [rax+rax+00h]
0x180003999  lea     rcx, [rsp+278h+Buffer]
0x18000399e  mov     [rsp+278h+var_240], rcx
0x1800039a3  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800039a7  mov     [rsp+278h+nSize], eax
0x1800039ab  mov     eax, [rbx+44h]
0x1800039ae  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800039b2  mov     r9, rdi; wchar_t *
0x1800039b5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800039bc  mov     rdx, rsi; wchar_t *
0x1800039bf  mov     rcx, r14; this
0x1800039c2  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800039c7  cmp     [rbx+18h], r15
0x1800039cb  jnz     short loc_1800039DD
0x1800039cd  cmp     [rbx+48h], r15
0x1800039d1  jnz     short loc_1800039DD
0x1800039d3  cmp     [rbx+30h], r15
0x1800039d7  jz      loc_180003A6D
0x1800039dd  lea     r8, asc_1800109D0; "    "
0x1800039e4  mov     rdx, rsi; wchar_t *
0x1800039e7  mov     rcx, rax; this
0x1800039ea  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800039ef  mov     r9, [rbx+18h]; wchar_t *
0x1800039f3  test    r9, r9
0x1800039f6  jz      short loc_180003A0A
0x1800039f8  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800039ff  mov     rdx, rsi; wchar_t *
0x180003a02  mov     rcx, rax; this
0x180003a05  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180003a0a  mov     r9, [rbx+48h]; wchar_t *
0x180003a0e  test    r9, r9
0x180003a11  jz      short loc_180003A25
0x180003a13  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180003a1a  mov     rdx, rsi; wchar_t *
0x180003a1d  mov     rcx, rax; this
0x180003a20  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180003a25  mov     rcx, [rbx+28h]
0x180003a29  mov     r9, [rbx+30h]; wchar_t *
0x180003a2d  mov     rdx, rsi; wchar_t *
0x180003a30  test    rcx, rcx
0x180003a33  jz      short loc_180003A4B
0x180003a35  mov     [rsp+278h+lpBuffer], rcx
0x180003a3a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180003a41  mov     rcx, rax; this
0x180003a44  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180003a49  jmp     short loc_180003A6D
0x180003a4b  mov     rcx, rax; this
0x180003a4e  test    r9, r9
0x180003a51  jz      short loc_180003A61
0x180003a53  lea     r8, aHs; "[%hs]\n"
0x180003a5a  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180003a5f  jmp     short loc_180003A6D
0x180003a61  lea     r8, asc_180010A48; "\n"
0x180003a68  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180003a6d  xor     eax, eax
0x180003a6f  mov     rcx, [rsp+278h+var_38]
0x180003a77  xor     rcx, rsp; StackCookie
0x180003a7a  call    __security_check_cookie
0x180003a7f  mov     rbx, [rsp+278h+arg_18]
0x180003a87  add     rsp, 250h
0x180003a8e  pop     r15
0x180003a90  pop     r14
0x180003a92  pop     rdi
0x180003a93  pop     rsi
0x180003a94  pop     rbp
0x180003a95  retn
```
