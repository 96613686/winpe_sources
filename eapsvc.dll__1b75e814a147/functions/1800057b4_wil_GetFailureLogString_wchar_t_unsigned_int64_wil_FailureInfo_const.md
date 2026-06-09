# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800057b4`
- end: `0x180005a6a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180003024`
- `0x18000328c`
- `0x180006214`
- `0x180009c80`
- `0x18000a380`
- `0x180015075`
- `0x1800151a9`

## callees

- `0x180001f60`
- `0x1800028dc`
- `0x1800057b4`
- `0x180006514`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005967`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005967`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800058e6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800058e6`

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
          v7 = (const char *)&word_180018CBE;
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
0x1800057b4  mov     [rsp+arg_18], rbx
0x1800057b9  push    rbp
0x1800057ba  push    rsi
0x1800057bb  push    rdi
0x1800057bc  push    r14
0x1800057be  push    r15
0x1800057c0  sub     rsp, 250h
0x1800057c7  mov     rax, cs:__security_cookie
0x1800057ce  xor     rax, rsp
0x1800057d1  mov     [rsp+278h+var_38], rax
0x1800057d9  mov     rbx, r8
0x1800057dc  mov     rsi, rdx
0x1800057df  mov     r14, rcx
0x1800057e2  xor     r15d, r15d
0x1800057e5  test    rdx, rdx
0x1800057e8  jz      loc_180005A41
0x1800057ee  test    rcx, rcx
0x1800057f1  jz      loc_180005A41
0x1800057f7  mov     [rcx], r15w
0x1800057fb  mov     rax, cs:g_pfnResultLoggingCallback
0x180005802  test    rax, rax
0x180005805  jz      short loc_180005828
0x180005807  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000580e  jz      short loc_180005828
0x180005810  mov     r8, rdx
0x180005813  mov     rdx, rcx
0x180005816  mov     rcx, rbx
0x180005819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000581e  cmp     [r14], r15w
0x180005822  jnz     loc_180005A41
0x180005828  mov     ecx, [rbx]
0x18000582a  mov     bpl, 8
0x18000582d  test    ecx, ecx
0x18000582f  jz      short loc_18000587A
0x180005831  sub     ecx, 1
0x180005834  jz      short loc_180005862
0x180005836  sub     ecx, 1
0x180005839  jz      short loc_180005852
0x18000583b  cmp     ecx, 1
0x18000583e  jz      short loc_180005849
0x180005840  lea     rdi, word_180018CBE
0x180005847  jmp     short loc_180005881
0x180005849  lea     rdi, aFailfast; "FailFast"
0x180005850  jmp     short loc_180005881
0x180005852  lea     rax, aLoghr; "LogHr"
0x180005859  lea     rdi, aLognt; "LogNt"
0x180005860  jmp     short loc_180005870
0x180005862  lea     rax, aReturnhr; "ReturnHr"
0x180005869  lea     rdi, aReturnnt; "ReturnNt"
0x180005870  test    [rbx+4], bpl
0x180005874  cmovz   rdi, rax
0x180005878  jmp     short loc_180005881
0x18000587a  lea     rdi, aException; "Exception"
0x180005881  xor     edx, edx; Val
0x180005883  mov     r8d, 200h; Size
0x180005889  lea     rcx, [rsp+278h+Buffer]; void *
0x18000588e  call    memset_0
0x180005893  test    [rbx+4], bpl
0x180005897  jz      short loc_1800058BC
0x180005899  mov     ebp, [rbx+0Ch]
0x18000589c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x1800058a3  test    rax, rax
0x1800058a6  jz      short loc_1800058EC
0x1800058a8  mov     r8d, 100h
0x1800058ae  lea     rdx, [rsp+278h+Buffer]
0x1800058b3  mov     ecx, ebp
0x1800058b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058ba  jmp     short loc_1800058EC
0x1800058bc  mov     ebp, [rbx+8]
0x1800058bf  mov     [rsp+278h+Arguments], r15; Arguments
0x1800058c4  mov     [rsp+278h+nSize], 100h; nSize
0x1800058cc  lea     rax, [rsp+278h+Buffer]
0x1800058d1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800058d6  mov     r9d, 400h; dwLanguageId
0x1800058dc  mov     r8d, ebp; dwMessageId
0x1800058df  xor     edx, edx; lpSource
0x1800058e1  mov     ecx, 1200h; dwFlags
0x1800058e6  call    cs:__imp_FormatMessageW
0x1800058ec  lea     rsi, [r14+rsi*2]
0x1800058f0  mov     r9, [rbx+38h]; wchar_t *
0x1800058f4  mov     rax, [rbx+88h]
0x1800058fb  mov     rcx, [rbx+80h]
0x180005902  mov     rdx, rsi; wchar_t *
0x180005905  test    r9, r9
0x180005908  jz      short loc_18000592C
0x18000590a  mov     [rsp+278h+Arguments], rax
0x18000590f  mov     qword ptr [rsp+278h+nSize], rcx
0x180005914  mov     eax, [rbx+40h]
0x180005917  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000591b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005922  mov     rcx, r14; this
0x180005925  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000592a  jmp     short loc_180005943
0x18000592c  mov     [rsp+278h+lpBuffer], rax
0x180005931  mov     r9, rcx; wchar_t *
0x180005934  lea     r8, aHsP; "%hs!%p: "
0x18000593b  mov     rcx, r14; this
0x18000593e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005943  mov     r14, rax
0x180005946  mov     r9, [rbx+90h]; wchar_t *
0x18000594d  test    r9, r9
0x180005950  jz      short loc_180005967
0x180005952  lea     r8, aCallerP; "(caller: %p) "
0x180005959  mov     rdx, rsi; wchar_t *
0x18000595c  mov     rcx, rax; this
0x18000595f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005964  mov     r14, rax
0x180005967  call    cs:__imp_GetCurrentThreadId
0x18000596d  lea     rcx, [rsp+278h+Buffer]
0x180005972  mov     [rsp+278h+var_240], rcx
0x180005977  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000597b  mov     [rsp+278h+nSize], eax
0x18000597f  mov     eax, [rbx+44h]
0x180005982  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005986  mov     r9, rdi; wchar_t *
0x180005989  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005990  mov     rdx, rsi; wchar_t *
0x180005993  mov     rcx, r14; this
0x180005996  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000599b  cmp     [rbx+18h], r15
0x18000599f  jnz     short loc_1800059B1
0x1800059a1  cmp     [rbx+48h], r15
0x1800059a5  jnz     short loc_1800059B1
0x1800059a7  cmp     [rbx+30h], r15
0x1800059ab  jz      loc_180005A41
0x1800059b1  lea     r8, asc_180018DA8; "    "
0x1800059b8  mov     rdx, rsi; wchar_t *
0x1800059bb  mov     rcx, rax; this
0x1800059be  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800059c3  mov     r9, [rbx+18h]; wchar_t *
0x1800059c7  test    r9, r9
0x1800059ca  jz      short loc_1800059DE
0x1800059cc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800059d3  mov     rdx, rsi; wchar_t *
0x1800059d6  mov     rcx, rax; this
0x1800059d9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800059de  mov     r9, [rbx+48h]; wchar_t *
0x1800059e2  test    r9, r9
0x1800059e5  jz      short loc_1800059F9
0x1800059e7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800059ee  mov     rdx, rsi; wchar_t *
0x1800059f1  mov     rcx, rax; this
0x1800059f4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800059f9  mov     rcx, [rbx+28h]
0x1800059fd  mov     r9, [rbx+30h]; wchar_t *
0x180005a01  mov     rdx, rsi; wchar_t *
0x180005a04  test    rcx, rcx
0x180005a07  jz      short loc_180005A1F
0x180005a09  mov     [rsp+278h+lpBuffer], rcx
0x180005a0e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005a15  mov     rcx, rax; this
0x180005a18  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005a1d  jmp     short loc_180005A41
0x180005a1f  mov     rcx, rax; this
0x180005a22  test    r9, r9
0x180005a25  jz      short loc_180005A35
0x180005a27  lea     r8, aHs; "[%hs]\n"
0x180005a2e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005a33  jmp     short loc_180005A41
0x180005a35  lea     r8, asc_180018E20; "\n"
0x180005a3c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005a41  xor     eax, eax
0x180005a43  mov     rcx, [rsp+278h+var_38]
0x180005a4b  xor     rcx, rsp; StackCookie
0x180005a4e  call    __security_check_cookie
0x180005a53  mov     rbx, [rsp+278h+arg_18]
0x180005a5b  add     rsp, 250h
0x180005a62  pop     r15
0x180005a64  pop     r14
0x180005a66  pop     rdi
0x180005a67  pop     rsi
0x180005a68  pop     rbp
0x180005a69  retn
```
