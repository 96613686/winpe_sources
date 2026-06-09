# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180007ec4`
- end: `0x18000817a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800082d0`
- `0x180008d50`
- `0x180009660`
- `0x18000e2d0`

## callees

- `0x180006270`
- `0x180006dcc`
- `0x180007ec4`
- `0x180008268`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008077`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008077`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007ff6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007ff6`

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
          v7 = (const char *)&MultiByteStr;
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
0x180007ec4  mov     [rsp+arg_18], rbx
0x180007ec9  push    rbp
0x180007eca  push    rsi
0x180007ecb  push    rdi
0x180007ecc  push    r14
0x180007ece  push    r15
0x180007ed0  sub     rsp, 250h
0x180007ed7  mov     rax, cs:__security_cookie
0x180007ede  xor     rax, rsp
0x180007ee1  mov     [rsp+278h+var_38], rax
0x180007ee9  mov     rbx, r8
0x180007eec  mov     rsi, rdx
0x180007eef  mov     r14, rcx
0x180007ef2  xor     r15d, r15d
0x180007ef5  test    rdx, rdx
0x180007ef8  jz      loc_180008151
0x180007efe  test    rcx, rcx
0x180007f01  jz      loc_180008151
0x180007f07  mov     [rcx], r15w
0x180007f0b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007f12  test    rax, rax
0x180007f15  jz      short loc_180007F38
0x180007f17  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007f1e  jz      short loc_180007F38
0x180007f20  mov     r8, rdx
0x180007f23  mov     rdx, rcx
0x180007f26  mov     rcx, rbx
0x180007f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f2e  cmp     [r14], r15w
0x180007f32  jnz     loc_180008151
0x180007f38  mov     ecx, [rbx]
0x180007f3a  mov     bpl, 8
0x180007f3d  test    ecx, ecx
0x180007f3f  jz      short loc_180007F8A
0x180007f41  sub     ecx, 1
0x180007f44  jz      short loc_180007F72
0x180007f46  sub     ecx, 1
0x180007f49  jz      short loc_180007F62
0x180007f4b  cmp     ecx, 1
0x180007f4e  jz      short loc_180007F59
0x180007f50  lea     rdi, MultiByteStr
0x180007f57  jmp     short loc_180007F91
0x180007f59  lea     rdi, aFailfast; "FailFast"
0x180007f60  jmp     short loc_180007F91
0x180007f62  lea     rax, aLoghr; "LogHr"
0x180007f69  lea     rdi, aLognt; "LogNt"
0x180007f70  jmp     short loc_180007F80
0x180007f72  lea     rax, aReturnhr; "ReturnHr"
0x180007f79  lea     rdi, aReturnnt; "ReturnNt"
0x180007f80  test    [rbx+4], bpl
0x180007f84  cmovz   rdi, rax
0x180007f88  jmp     short loc_180007F91
0x180007f8a  lea     rdi, aException; "Exception"
0x180007f91  xor     edx, edx; Val
0x180007f93  mov     r8d, 200h; Size
0x180007f99  lea     rcx, [rsp+278h+Buffer]; void *
0x180007f9e  call    memset_0
0x180007fa3  test    [rbx+4], bpl
0x180007fa7  jz      short loc_180007FCC
0x180007fa9  mov     ebp, [rbx+0Ch]
0x180007fac  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180007fb3  test    rax, rax
0x180007fb6  jz      short loc_180007FFC
0x180007fb8  mov     r8d, 100h
0x180007fbe  lea     rdx, [rsp+278h+Buffer]
0x180007fc3  mov     ecx, ebp
0x180007fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fca  jmp     short loc_180007FFC
0x180007fcc  mov     ebp, [rbx+8]
0x180007fcf  mov     [rsp+278h+Arguments], r15; Arguments
0x180007fd4  mov     [rsp+278h+nSize], 100h; nSize
0x180007fdc  lea     rax, [rsp+278h+Buffer]
0x180007fe1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180007fe6  mov     r9d, 400h; dwLanguageId
0x180007fec  mov     r8d, ebp; dwMessageId
0x180007fef  xor     edx, edx; lpSource
0x180007ff1  mov     ecx, 1200h; dwFlags
0x180007ff6  call    cs:__imp_FormatMessageW
0x180007ffc  lea     rsi, [r14+rsi*2]
0x180008000  mov     r9, [rbx+38h]; wchar_t *
0x180008004  mov     rax, [rbx+88h]
0x18000800b  mov     rcx, [rbx+80h]
0x180008012  mov     rdx, rsi; wchar_t *
0x180008015  test    r9, r9
0x180008018  jz      short loc_18000803C
0x18000801a  mov     [rsp+278h+Arguments], rax
0x18000801f  mov     qword ptr [rsp+278h+nSize], rcx
0x180008024  mov     eax, [rbx+40h]
0x180008027  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000802b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180008032  mov     rcx, r14; this
0x180008035  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000803a  jmp     short loc_180008053
0x18000803c  mov     [rsp+278h+lpBuffer], rax
0x180008041  mov     r9, rcx; wchar_t *
0x180008044  lea     r8, aHsP; "%hs!%p: "
0x18000804b  mov     rcx, r14; this
0x18000804e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180008053  mov     r14, rax
0x180008056  mov     r9, [rbx+90h]; wchar_t *
0x18000805d  test    r9, r9
0x180008060  jz      short loc_180008077
0x180008062  lea     r8, aCallerP; "(caller: %p) "
0x180008069  mov     rdx, rsi; wchar_t *
0x18000806c  mov     rcx, rax; this
0x18000806f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180008074  mov     r14, rax
0x180008077  call    cs:__imp_GetCurrentThreadId
0x18000807d  lea     rcx, [rsp+278h+Buffer]
0x180008082  mov     [rsp+278h+var_240], rcx
0x180008087  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000808b  mov     [rsp+278h+nSize], eax
0x18000808f  mov     eax, [rbx+44h]
0x180008092  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180008096  mov     r9, rdi; wchar_t *
0x180008099  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800080a0  mov     rdx, rsi; wchar_t *
0x1800080a3  mov     rcx, r14; this
0x1800080a6  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800080ab  cmp     [rbx+18h], r15
0x1800080af  jnz     short loc_1800080C1
0x1800080b1  cmp     [rbx+48h], r15
0x1800080b5  jnz     short loc_1800080C1
0x1800080b7  cmp     [rbx+30h], r15
0x1800080bb  jz      loc_180008151
0x1800080c1  lea     r8, asc_180043920; "    "
0x1800080c8  mov     rdx, rsi; wchar_t *
0x1800080cb  mov     rcx, rax; this
0x1800080ce  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800080d3  mov     r9, [rbx+18h]; wchar_t *
0x1800080d7  test    r9, r9
0x1800080da  jz      short loc_1800080EE
0x1800080dc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800080e3  mov     rdx, rsi; wchar_t *
0x1800080e6  mov     rcx, rax; this
0x1800080e9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800080ee  mov     r9, [rbx+48h]; wchar_t *
0x1800080f2  test    r9, r9
0x1800080f5  jz      short loc_180008109
0x1800080f7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800080fe  mov     rdx, rsi; wchar_t *
0x180008101  mov     rcx, rax; this
0x180008104  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180008109  mov     rcx, [rbx+28h]
0x18000810d  mov     r9, [rbx+30h]; wchar_t *
0x180008111  mov     rdx, rsi; wchar_t *
0x180008114  test    rcx, rcx
0x180008117  jz      short loc_18000812F
0x180008119  mov     [rsp+278h+lpBuffer], rcx
0x18000811e  lea     r8, aHsHs_0; "[%hs(%hs)]\n"
0x180008125  mov     rcx, rax; this
0x180008128  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000812d  jmp     short loc_180008151
0x18000812f  mov     rcx, rax; this
0x180008132  test    r9, r9
0x180008135  jz      short loc_180008145
0x180008137  lea     r8, aHs; "[%hs]\n"
0x18000813e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180008143  jmp     short loc_180008151
0x180008145  lea     r8, asc_180043998; "\n"
0x18000814c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180008151  xor     eax, eax
0x180008153  mov     rcx, [rsp+278h+var_38]
0x18000815b  xor     rcx, rsp; StackCookie
0x18000815e  call    __security_check_cookie
0x180008163  mov     rbx, [rsp+278h+arg_18]
0x18000816b  add     rsp, 250h
0x180008172  pop     r15
0x180008174  pop     r14
0x180008176  pop     rdi
0x180008177  pop     rsi
0x180008178  pop     rbp
0x180008179  retn
```
