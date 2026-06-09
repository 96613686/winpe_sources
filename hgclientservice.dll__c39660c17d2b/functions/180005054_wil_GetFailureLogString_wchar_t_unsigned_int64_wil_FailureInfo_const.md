# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005054`
- end: `0x18000530a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x180002e70`
- `0x1800036b8`
- `0x180003938`
- `0x180005a08`
- `0x1800074d0`
- `0x180007de4`
- `0x180015411`
- `0x180015545`

## callees

- `0x180001770`
- `0x1800021f0`
- `0x180005054`
- `0x180005d08`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005207`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005207`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005186`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005186`

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
          v7 = (const char *)&qword_180019A78;
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
0x180005054  mov     [rsp+arg_18], rbx
0x180005059  push    rbp
0x18000505a  push    rsi
0x18000505b  push    rdi
0x18000505c  push    r14
0x18000505e  push    r15
0x180005060  sub     rsp, 250h
0x180005067  mov     rax, cs:__security_cookie
0x18000506e  xor     rax, rsp
0x180005071  mov     [rsp+278h+var_38], rax
0x180005079  mov     rbx, r8
0x18000507c  mov     rsi, rdx
0x18000507f  mov     r14, rcx
0x180005082  xor     r15d, r15d
0x180005085  test    rdx, rdx
0x180005088  jz      loc_1800052E1
0x18000508e  test    rcx, rcx
0x180005091  jz      loc_1800052E1
0x180005097  mov     [rcx], r15w
0x18000509b  mov     rax, cs:g_pfnResultLoggingCallback
0x1800050a2  test    rax, rax
0x1800050a5  jz      short loc_1800050C8
0x1800050a7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800050ae  jz      short loc_1800050C8
0x1800050b0  mov     r8, rdx
0x1800050b3  mov     rdx, rcx
0x1800050b6  mov     rcx, rbx
0x1800050b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050be  cmp     [r14], r15w
0x1800050c2  jnz     loc_1800052E1
0x1800050c8  mov     ecx, [rbx]
0x1800050ca  mov     bpl, 8
0x1800050cd  test    ecx, ecx
0x1800050cf  jz      short loc_18000511A
0x1800050d1  sub     ecx, 1
0x1800050d4  jz      short loc_180005102
0x1800050d6  sub     ecx, 1
0x1800050d9  jz      short loc_1800050F2
0x1800050db  cmp     ecx, 1
0x1800050de  jz      short loc_1800050E9
0x1800050e0  lea     rdi, qword_180019A78
0x1800050e7  jmp     short loc_180005121
0x1800050e9  lea     rdi, aFailfast; "FailFast"
0x1800050f0  jmp     short loc_180005121
0x1800050f2  lea     rax, aLoghr; "LogHr"
0x1800050f9  lea     rdi, aLognt; "LogNt"
0x180005100  jmp     short loc_180005110
0x180005102  lea     rax, aReturnhr; "ReturnHr"
0x180005109  lea     rdi, aReturnnt; "ReturnNt"
0x180005110  test    [rbx+4], bpl
0x180005114  cmovz   rdi, rax
0x180005118  jmp     short loc_180005121
0x18000511a  lea     rdi, aException; "Exception"
0x180005121  xor     edx, edx; Val
0x180005123  mov     r8d, 200h; Size
0x180005129  lea     rcx, [rsp+278h+Buffer]; void *
0x18000512e  call    memset_0
0x180005133  test    [rbx+4], bpl
0x180005137  jz      short loc_18000515C
0x180005139  mov     ebp, [rbx+0Ch]
0x18000513c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180005143  test    rax, rax
0x180005146  jz      short loc_18000518C
0x180005148  mov     r8d, 100h
0x18000514e  lea     rdx, [rsp+278h+Buffer]
0x180005153  mov     ecx, ebp
0x180005155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000515a  jmp     short loc_18000518C
0x18000515c  mov     ebp, [rbx+8]
0x18000515f  mov     [rsp+278h+Arguments], r15; Arguments
0x180005164  mov     [rsp+278h+nSize], 100h; nSize
0x18000516c  lea     rax, [rsp+278h+Buffer]
0x180005171  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005176  mov     r9d, 400h; dwLanguageId
0x18000517c  mov     r8d, ebp; dwMessageId
0x18000517f  xor     edx, edx; lpSource
0x180005181  mov     ecx, 1200h; dwFlags
0x180005186  call    cs:__imp_FormatMessageW
0x18000518c  lea     rsi, [r14+rsi*2]
0x180005190  mov     r9, [rbx+38h]; wchar_t *
0x180005194  mov     rax, [rbx+88h]
0x18000519b  mov     rcx, [rbx+80h]
0x1800051a2  mov     rdx, rsi; wchar_t *
0x1800051a5  test    r9, r9
0x1800051a8  jz      short loc_1800051CC
0x1800051aa  mov     [rsp+278h+Arguments], rax
0x1800051af  mov     qword ptr [rsp+278h+nSize], rcx
0x1800051b4  mov     eax, [rbx+40h]
0x1800051b7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800051bb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800051c2  mov     rcx, r14; this
0x1800051c5  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800051ca  jmp     short loc_1800051E3
0x1800051cc  mov     [rsp+278h+lpBuffer], rax
0x1800051d1  mov     r9, rcx; wchar_t *
0x1800051d4  lea     r8, aHsP; "%hs!%p: "
0x1800051db  mov     rcx, r14; this
0x1800051de  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800051e3  mov     r14, rax
0x1800051e6  mov     r9, [rbx+90h]; wchar_t *
0x1800051ed  test    r9, r9
0x1800051f0  jz      short loc_180005207
0x1800051f2  lea     r8, aCallerP; "(caller: %p) "
0x1800051f9  mov     rdx, rsi; wchar_t *
0x1800051fc  mov     rcx, rax; this
0x1800051ff  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005204  mov     r14, rax
0x180005207  call    cs:__imp_GetCurrentThreadId
0x18000520d  lea     rcx, [rsp+278h+Buffer]
0x180005212  mov     [rsp+278h+var_240], rcx
0x180005217  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000521b  mov     [rsp+278h+nSize], eax
0x18000521f  mov     eax, [rbx+44h]
0x180005222  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005226  mov     r9, rdi; wchar_t *
0x180005229  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005230  mov     rdx, rsi; wchar_t *
0x180005233  mov     rcx, r14; this
0x180005236  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000523b  cmp     [rbx+18h], r15
0x18000523f  jnz     short loc_180005251
0x180005241  cmp     [rbx+48h], r15
0x180005245  jnz     short loc_180005251
0x180005247  cmp     [rbx+30h], r15
0x18000524b  jz      loc_1800052E1
0x180005251  lea     r8, asc_180019B68; "    "
0x180005258  mov     rdx, rsi; wchar_t *
0x18000525b  mov     rcx, rax; this
0x18000525e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005263  mov     r9, [rbx+18h]; wchar_t *
0x180005267  test    r9, r9
0x18000526a  jz      short loc_18000527E
0x18000526c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005273  mov     rdx, rsi; wchar_t *
0x180005276  mov     rcx, rax; this
0x180005279  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000527e  mov     r9, [rbx+48h]; wchar_t *
0x180005282  test    r9, r9
0x180005285  jz      short loc_180005299
0x180005287  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000528e  mov     rdx, rsi; wchar_t *
0x180005291  mov     rcx, rax; this
0x180005294  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005299  mov     rcx, [rbx+28h]
0x18000529d  mov     r9, [rbx+30h]; wchar_t *
0x1800052a1  mov     rdx, rsi; wchar_t *
0x1800052a4  test    rcx, rcx
0x1800052a7  jz      short loc_1800052BF
0x1800052a9  mov     [rsp+278h+lpBuffer], rcx
0x1800052ae  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800052b5  mov     rcx, rax; this
0x1800052b8  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800052bd  jmp     short loc_1800052E1
0x1800052bf  mov     rcx, rax; this
0x1800052c2  test    r9, r9
0x1800052c5  jz      short loc_1800052D5
0x1800052c7  lea     r8, aHs; "[%hs]\n"
0x1800052ce  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800052d3  jmp     short loc_1800052E1
0x1800052d5  lea     r8, asc_180019BE0; "\n"
0x1800052dc  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800052e1  xor     eax, eax
0x1800052e3  mov     rcx, [rsp+278h+var_38]
0x1800052eb  xor     rcx, rsp; StackCookie
0x1800052ee  call    __security_check_cookie
0x1800052f3  mov     rbx, [rsp+278h+arg_18]
0x1800052fb  add     rsp, 250h
0x180005302  pop     r15
0x180005304  pop     r14
0x180005306  pop     rdi
0x180005307  pop     rsi
0x180005308  pop     rbp
0x180005309  retn
```
