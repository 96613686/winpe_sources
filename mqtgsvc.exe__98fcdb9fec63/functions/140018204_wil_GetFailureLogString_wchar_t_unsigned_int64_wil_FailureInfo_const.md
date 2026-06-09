# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140018204`
- end: `0x1400184ba`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wchar_t *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140018c9c`
- `0x14001bec0`

## callees

- `0x140018204`
- `0x140018f98`
- `0x14001ceda`
- `0x14001cf00`
- `0x140020010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x140018336`
- `KERNEL32!FormatMessageW` at `0x140018336`
- `KERNEL32!GetCurrentThreadId` at `0x1400183b7`
- `KERNEL32!GetCurrentThreadId` at `0x1400183b7`

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
      g_pfnResultLoggingCallback(a3, this, a2, a4);
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
          v7 = (const char *)&qword_140022DF8;
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
0x140018204  mov     [rsp+arg_18], rbx
0x140018209  push    rbp
0x14001820a  push    rsi
0x14001820b  push    rdi
0x14001820c  push    r14
0x14001820e  push    r15
0x140018210  sub     rsp, 250h
0x140018217  mov     rax, cs:__security_cookie
0x14001821e  xor     rax, rsp
0x140018221  mov     [rsp+278h+var_38], rax
0x140018229  mov     rbx, r8
0x14001822c  mov     rsi, rdx
0x14001822f  mov     r14, rcx
0x140018232  xor     r15d, r15d
0x140018235  test    rdx, rdx
0x140018238  jz      loc_140018491
0x14001823e  test    rcx, rcx
0x140018241  jz      loc_140018491
0x140018247  mov     [rcx], r15w
0x14001824b  mov     rax, cs:g_pfnResultLoggingCallback
0x140018252  test    rax, rax
0x140018255  jz      short loc_140018278
0x140018257  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14001825e  jz      short loc_140018278
0x140018260  mov     r8, rdx
0x140018263  mov     rdx, rcx
0x140018266  mov     rcx, rbx
0x140018269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001826e  cmp     [r14], r15w
0x140018272  jnz     loc_140018491
0x140018278  mov     ecx, [rbx]
0x14001827a  mov     bpl, 8
0x14001827d  test    ecx, ecx
0x14001827f  jz      short loc_1400182CA
0x140018281  sub     ecx, 1
0x140018284  jz      short loc_1400182B2
0x140018286  sub     ecx, 1
0x140018289  jz      short loc_1400182A2
0x14001828b  cmp     ecx, 1
0x14001828e  jz      short loc_140018299
0x140018290  lea     rdi, qword_140022DF8
0x140018297  jmp     short loc_1400182D1
0x140018299  lea     rdi, aFailfast; "FailFast"
0x1400182a0  jmp     short loc_1400182D1
0x1400182a2  lea     rax, aLoghr; "LogHr"
0x1400182a9  lea     rdi, aLognt; "LogNt"
0x1400182b0  jmp     short loc_1400182C0
0x1400182b2  lea     rax, aReturnhr; "ReturnHr"
0x1400182b9  lea     rdi, aReturnnt; "ReturnNt"
0x1400182c0  test    [rbx+4], bpl
0x1400182c4  cmovz   rdi, rax
0x1400182c8  jmp     short loc_1400182D1
0x1400182ca  lea     rdi, aException; "Exception"
0x1400182d1  xor     edx, edx; Val
0x1400182d3  mov     r8d, 200h; Size
0x1400182d9  lea     rcx, [rsp+278h+Buffer]; void *
0x1400182de  call    memset_0
0x1400182e3  test    [rbx+4], bpl
0x1400182e7  jz      short loc_14001830C
0x1400182e9  mov     ebp, [rbx+0Ch]
0x1400182ec  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x1400182f3  test    rax, rax
0x1400182f6  jz      short loc_14001833C
0x1400182f8  mov     r8d, 100h
0x1400182fe  lea     rdx, [rsp+278h+Buffer]
0x140018303  mov     ecx, ebp
0x140018305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001830a  jmp     short loc_14001833C
0x14001830c  mov     ebp, [rbx+8]
0x14001830f  mov     [rsp+278h+Arguments], r15; Arguments
0x140018314  mov     [rsp+278h+nSize], 100h; nSize
0x14001831c  lea     rax, [rsp+278h+Buffer]
0x140018321  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140018326  mov     r9d, 400h; dwLanguageId
0x14001832c  mov     r8d, ebp; dwMessageId
0x14001832f  xor     edx, edx; lpSource
0x140018331  mov     ecx, 1200h; dwFlags
0x140018336  call    cs:__imp_FormatMessageW
0x14001833c  lea     rsi, [r14+rsi*2]
0x140018340  mov     r9, [rbx+38h]; wchar_t *
0x140018344  mov     rax, [rbx+88h]
0x14001834b  mov     rcx, [rbx+80h]
0x140018352  mov     rdx, rsi; wchar_t *
0x140018355  test    r9, r9
0x140018358  jz      short loc_14001837C
0x14001835a  mov     [rsp+278h+Arguments], rax
0x14001835f  mov     qword ptr [rsp+278h+nSize], rcx
0x140018364  mov     eax, [rbx+40h]
0x140018367  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14001836b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140018372  mov     rcx, r14; this
0x140018375  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14001837a  jmp     short loc_140018393
0x14001837c  mov     [rsp+278h+lpBuffer], rax
0x140018381  mov     r9, rcx; wchar_t *
0x140018384  lea     r8, aHsP; "%hs!%p: "
0x14001838b  mov     rcx, r14; this
0x14001838e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140018393  mov     r14, rax
0x140018396  mov     r9, [rbx+90h]; wchar_t *
0x14001839d  test    r9, r9
0x1400183a0  jz      short loc_1400183B7
0x1400183a2  lea     r8, aCallerP; "(caller: %p) "
0x1400183a9  mov     rdx, rsi; wchar_t *
0x1400183ac  mov     rcx, rax; this
0x1400183af  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400183b4  mov     r14, rax
0x1400183b7  call    cs:__imp_GetCurrentThreadId
0x1400183bd  lea     rcx, [rsp+278h+Buffer]
0x1400183c2  mov     [rsp+278h+var_240], rcx
0x1400183c7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1400183cb  mov     [rsp+278h+nSize], eax
0x1400183cf  mov     eax, [rbx+44h]
0x1400183d2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400183d6  mov     r9, rdi; wchar_t *
0x1400183d9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1400183e0  mov     rdx, rsi; wchar_t *
0x1400183e3  mov     rcx, r14; this
0x1400183e6  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400183eb  cmp     [rbx+18h], r15
0x1400183ef  jnz     short loc_140018401
0x1400183f1  cmp     [rbx+48h], r15
0x1400183f5  jnz     short loc_140018401
0x1400183f7  cmp     [rbx+30h], r15
0x1400183fb  jz      loc_140018491
0x140018401  lea     r8, asc_140022EE8; "    "
0x140018408  mov     rdx, rsi; wchar_t *
0x14001840b  mov     rcx, rax; this
0x14001840e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140018413  mov     r9, [rbx+18h]; wchar_t *
0x140018417  test    r9, r9
0x14001841a  jz      short loc_14001842E
0x14001841c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140018423  mov     rdx, rsi; wchar_t *
0x140018426  mov     rcx, rax; this
0x140018429  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14001842e  mov     r9, [rbx+48h]; wchar_t *
0x140018432  test    r9, r9
0x140018435  jz      short loc_140018449
0x140018437  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14001843e  mov     rdx, rsi; wchar_t *
0x140018441  mov     rcx, rax; this
0x140018444  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140018449  mov     rcx, [rbx+28h]
0x14001844d  mov     r9, [rbx+30h]; wchar_t *
0x140018451  mov     rdx, rsi; wchar_t *
0x140018454  test    rcx, rcx
0x140018457  jz      short loc_14001846F
0x140018459  mov     [rsp+278h+lpBuffer], rcx
0x14001845e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140018465  mov     rcx, rax; this
0x140018468  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14001846d  jmp     short loc_140018491
0x14001846f  mov     rcx, rax; this
0x140018472  test    r9, r9
0x140018475  jz      short loc_140018485
0x140018477  lea     r8, aHs; "[%hs]\n"
0x14001847e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140018483  jmp     short loc_140018491
0x140018485  lea     r8, asc_140022F60; "\n"
0x14001848c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140018491  xor     eax, eax
0x140018493  mov     rcx, [rsp+278h+var_38]
0x14001849b  xor     rcx, rsp; StackCookie
0x14001849e  call    __security_check_cookie
0x1400184a3  mov     rbx, [rsp+278h+arg_18]
0x1400184ab  add     rsp, 250h
0x1400184b2  pop     r15
0x1400184b4  pop     r14
0x1400184b6  pop     rdi
0x1400184b7  pop     rsi
0x1400184b8  pop     rbp
0x1400184b9  retn
```
