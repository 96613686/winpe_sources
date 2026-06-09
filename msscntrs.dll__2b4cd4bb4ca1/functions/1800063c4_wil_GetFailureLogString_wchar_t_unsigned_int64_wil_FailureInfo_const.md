# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800063c4`
- end: `0x18000667a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180003a68`
- `0x180003ce8`
- `0x180006e10`
- `0x18000a8a0`
- `0x180011b6c`
- `0x18001597a`
- `0x180015aae`
- `0x180015c17`
- `0x180015ee7`

## callees

- `0x1800024a0`
- `0x180003320`
- `0x1800063c4`
- `0x180007110`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006577`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006577`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800064f6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800064f6`

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
          v7 = (const char *)&dword_18001A14C;
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
0x1800063c4  mov     [rsp+arg_18], rbx
0x1800063c9  push    rbp
0x1800063ca  push    rsi
0x1800063cb  push    rdi
0x1800063cc  push    r14
0x1800063ce  push    r15
0x1800063d0  sub     rsp, 250h
0x1800063d7  mov     rax, cs:__security_cookie
0x1800063de  xor     rax, rsp
0x1800063e1  mov     [rsp+278h+var_38], rax
0x1800063e9  mov     rbx, r8
0x1800063ec  mov     rsi, rdx
0x1800063ef  mov     r14, rcx
0x1800063f2  xor     r15d, r15d
0x1800063f5  test    rdx, rdx
0x1800063f8  jz      loc_180006651
0x1800063fe  test    rcx, rcx
0x180006401  jz      loc_180006651
0x180006407  mov     [rcx], r15w
0x18000640b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006412  test    rax, rax
0x180006415  jz      short loc_180006438
0x180006417  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000641e  jz      short loc_180006438
0x180006420  mov     r8, rdx
0x180006423  mov     rdx, rcx
0x180006426  mov     rcx, rbx
0x180006429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000642e  cmp     [r14], r15w
0x180006432  jnz     loc_180006651
0x180006438  mov     ecx, [rbx]
0x18000643a  mov     bpl, 8
0x18000643d  test    ecx, ecx
0x18000643f  jz      short loc_18000648A
0x180006441  sub     ecx, 1
0x180006444  jz      short loc_180006472
0x180006446  sub     ecx, 1
0x180006449  jz      short loc_180006462
0x18000644b  cmp     ecx, 1
0x18000644e  jz      short loc_180006459
0x180006450  lea     rdi, dword_18001A14C
0x180006457  jmp     short loc_180006491
0x180006459  lea     rdi, aFailfast; "FailFast"
0x180006460  jmp     short loc_180006491
0x180006462  lea     rax, aLoghr; "LogHr"
0x180006469  lea     rdi, aLognt; "LogNt"
0x180006470  jmp     short loc_180006480
0x180006472  lea     rax, aReturnhr; "ReturnHr"
0x180006479  lea     rdi, aReturnnt; "ReturnNt"
0x180006480  test    [rbx+4], bpl
0x180006484  cmovz   rdi, rax
0x180006488  jmp     short loc_180006491
0x18000648a  lea     rdi, aException; "Exception"
0x180006491  xor     edx, edx; Val
0x180006493  mov     r8d, 200h; Size
0x180006499  lea     rcx, [rsp+278h+Buffer]; void *
0x18000649e  call    memset_0
0x1800064a3  test    [rbx+4], bpl
0x1800064a7  jz      short loc_1800064CC
0x1800064a9  mov     ebp, [rbx+0Ch]
0x1800064ac  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x1800064b3  test    rax, rax
0x1800064b6  jz      short loc_1800064FC
0x1800064b8  mov     r8d, 100h
0x1800064be  lea     rdx, [rsp+278h+Buffer]
0x1800064c3  mov     ecx, ebp
0x1800064c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064ca  jmp     short loc_1800064FC
0x1800064cc  mov     ebp, [rbx+8]
0x1800064cf  mov     [rsp+278h+Arguments], r15; Arguments
0x1800064d4  mov     [rsp+278h+nSize], 100h; nSize
0x1800064dc  lea     rax, [rsp+278h+Buffer]
0x1800064e1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800064e6  mov     r9d, 400h; dwLanguageId
0x1800064ec  mov     r8d, ebp; dwMessageId
0x1800064ef  xor     edx, edx; lpSource
0x1800064f1  mov     ecx, 1200h; dwFlags
0x1800064f6  call    cs:__imp_FormatMessageW
0x1800064fc  lea     rsi, [r14+rsi*2]
0x180006500  mov     r9, [rbx+38h]; wchar_t *
0x180006504  mov     rax, [rbx+88h]
0x18000650b  mov     rcx, [rbx+80h]
0x180006512  mov     rdx, rsi; wchar_t *
0x180006515  test    r9, r9
0x180006518  jz      short loc_18000653C
0x18000651a  mov     [rsp+278h+Arguments], rax
0x18000651f  mov     qword ptr [rsp+278h+nSize], rcx
0x180006524  mov     eax, [rbx+40h]
0x180006527  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000652b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006532  mov     rcx, r14; this
0x180006535  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000653a  jmp     short loc_180006553
0x18000653c  mov     [rsp+278h+lpBuffer], rax
0x180006541  mov     r9, rcx; wchar_t *
0x180006544  lea     r8, aHsP; "%hs!%p: "
0x18000654b  mov     rcx, r14; this
0x18000654e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006553  mov     r14, rax
0x180006556  mov     r9, [rbx+90h]; wchar_t *
0x18000655d  test    r9, r9
0x180006560  jz      short loc_180006577
0x180006562  lea     r8, aCallerP; "(caller: %p) "
0x180006569  mov     rdx, rsi; wchar_t *
0x18000656c  mov     rcx, rax; this
0x18000656f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006574  mov     r14, rax
0x180006577  call    cs:__imp_GetCurrentThreadId
0x18000657d  lea     rcx, [rsp+278h+Buffer]
0x180006582  mov     [rsp+278h+var_240], rcx
0x180006587  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000658b  mov     [rsp+278h+nSize], eax
0x18000658f  mov     eax, [rbx+44h]
0x180006592  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006596  mov     r9, rdi; wchar_t *
0x180006599  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800065a0  mov     rdx, rsi; wchar_t *
0x1800065a3  mov     rcx, r14; this
0x1800065a6  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800065ab  cmp     [rbx+18h], r15
0x1800065af  jnz     short loc_1800065C1
0x1800065b1  cmp     [rbx+48h], r15
0x1800065b5  jnz     short loc_1800065C1
0x1800065b7  cmp     [rbx+30h], r15
0x1800065bb  jz      loc_180006651
0x1800065c1  lea     r8, asc_18001A280; "    "
0x1800065c8  mov     rdx, rsi; wchar_t *
0x1800065cb  mov     rcx, rax; this
0x1800065ce  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800065d3  mov     r9, [rbx+18h]; wchar_t *
0x1800065d7  test    r9, r9
0x1800065da  jz      short loc_1800065EE
0x1800065dc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800065e3  mov     rdx, rsi; wchar_t *
0x1800065e6  mov     rcx, rax; this
0x1800065e9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800065ee  mov     r9, [rbx+48h]; wchar_t *
0x1800065f2  test    r9, r9
0x1800065f5  jz      short loc_180006609
0x1800065f7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800065fe  mov     rdx, rsi; wchar_t *
0x180006601  mov     rcx, rax; this
0x180006604  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006609  mov     rcx, [rbx+28h]
0x18000660d  mov     r9, [rbx+30h]; wchar_t *
0x180006611  mov     rdx, rsi; wchar_t *
0x180006614  test    rcx, rcx
0x180006617  jz      short loc_18000662F
0x180006619  mov     [rsp+278h+lpBuffer], rcx
0x18000661e  lea     r8, aHsHs_0; "[%hs(%hs)]\n"
0x180006625  mov     rcx, rax; this
0x180006628  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000662d  jmp     short loc_180006651
0x18000662f  mov     rcx, rax; this
0x180006632  test    r9, r9
0x180006635  jz      short loc_180006645
0x180006637  lea     r8, aHs; "[%hs]\n"
0x18000663e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006643  jmp     short loc_180006651
0x180006645  lea     r8, asc_18001A2F8; "\n"
0x18000664c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006651  xor     eax, eax
0x180006653  mov     rcx, [rsp+278h+var_38]
0x18000665b  xor     rcx, rsp; StackCookie
0x18000665e  call    __security_check_cookie
0x180006663  mov     rbx, [rsp+278h+arg_18]
0x18000666b  add     rsp, 250h
0x180006672  pop     r15
0x180006674  pop     r14
0x180006676  pop     rdi
0x180006677  pop     rsi
0x180006678  pop     rbp
0x180006679  retn
```
