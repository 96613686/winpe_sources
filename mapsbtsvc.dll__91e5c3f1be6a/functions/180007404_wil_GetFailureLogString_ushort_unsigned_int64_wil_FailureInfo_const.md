# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180007404`
- end: `0x1800076ba`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180006648`
- `0x180007d9c`
- `0x180008258`
- `0x1800093f0`

## callees

- `0x180001e70`
- `0x1800028e8`
- `0x180007404`
- `0x18000809c`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800075b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800075b7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007536`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007536`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  unsigned __int16 *v10; // rsi
  const unsigned __int16 *v11; // r9
  __int64 v12; // rax
  const unsigned __int16 *v13; // rcx
  unsigned __int16 *v14; // rax
  wil::details *v15; // r14
  const unsigned __int16 *v16; // r9
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
          v7 = (const char *)&dword_180017404;
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
  v10 = (unsigned __int16 *)((char *)this + 2 * (_QWORD)a2);
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const unsigned __int16 **)(a3 + 128);
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
  v16 = *(const unsigned __int16 **)(a3 + 144);
  if ( v16 )
    v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v15,
                          v10,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const unsigned __int16 *)v7,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v10, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
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
0x180007404  mov     [rsp+arg_18], rbx
0x180007409  push    rbp
0x18000740a  push    rsi
0x18000740b  push    rdi
0x18000740c  push    r14
0x18000740e  push    r15
0x180007410  sub     rsp, 250h
0x180007417  mov     rax, cs:__security_cookie
0x18000741e  xor     rax, rsp
0x180007421  mov     [rsp+278h+var_38], rax
0x180007429  mov     rbx, r8
0x18000742c  mov     rsi, rdx
0x18000742f  mov     r14, rcx
0x180007432  xor     r15d, r15d
0x180007435  test    rdx, rdx
0x180007438  jz      loc_180007691
0x18000743e  test    rcx, rcx
0x180007441  jz      loc_180007691
0x180007447  mov     [rcx], r15w
0x18000744b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007452  test    rax, rax
0x180007455  jz      short loc_180007478
0x180007457  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000745e  jz      short loc_180007478
0x180007460  mov     r8, rdx
0x180007463  mov     rdx, rcx
0x180007466  mov     rcx, rbx
0x180007469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000746e  cmp     [r14], r15w
0x180007472  jnz     loc_180007691
0x180007478  mov     ecx, [rbx]
0x18000747a  mov     bpl, 8
0x18000747d  test    ecx, ecx
0x18000747f  jz      short loc_1800074CA
0x180007481  sub     ecx, 1
0x180007484  jz      short loc_1800074B2
0x180007486  sub     ecx, 1
0x180007489  jz      short loc_1800074A2
0x18000748b  cmp     ecx, 1
0x18000748e  jz      short loc_180007499
0x180007490  lea     rdi, dword_180017404
0x180007497  jmp     short loc_1800074D1
0x180007499  lea     rdi, aFailfast; "FailFast"
0x1800074a0  jmp     short loc_1800074D1
0x1800074a2  lea     rax, aLoghr; "LogHr"
0x1800074a9  lea     rdi, aLognt; "LogNt"
0x1800074b0  jmp     short loc_1800074C0
0x1800074b2  lea     rax, aReturnhr; "ReturnHr"
0x1800074b9  lea     rdi, aReturnnt; "ReturnNt"
0x1800074c0  test    [rbx+4], bpl
0x1800074c4  cmovz   rdi, rax
0x1800074c8  jmp     short loc_1800074D1
0x1800074ca  lea     rdi, aException; "Exception"
0x1800074d1  xor     edx, edx; Val
0x1800074d3  mov     r8d, 200h; Size
0x1800074d9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800074de  call    memset_0
0x1800074e3  test    [rbx+4], bpl
0x1800074e7  jz      short loc_18000750C
0x1800074e9  mov     ebp, [rbx+0Ch]
0x1800074ec  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800074f3  test    rax, rax
0x1800074f6  jz      short loc_18000753C
0x1800074f8  mov     r8d, 100h
0x1800074fe  lea     rdx, [rsp+278h+Buffer]
0x180007503  mov     ecx, ebp
0x180007505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000750a  jmp     short loc_18000753C
0x18000750c  mov     ebp, [rbx+8]
0x18000750f  mov     [rsp+278h+Arguments], r15; Arguments
0x180007514  mov     [rsp+278h+nSize], 100h; nSize
0x18000751c  lea     rax, [rsp+278h+Buffer]
0x180007521  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180007526  mov     r9d, 400h; dwLanguageId
0x18000752c  mov     r8d, ebp; dwMessageId
0x18000752f  xor     edx, edx; lpSource
0x180007531  mov     ecx, 1200h; dwFlags
0x180007536  call    cs:__imp_FormatMessageW
0x18000753c  lea     rsi, [r14+rsi*2]
0x180007540  mov     r9, [rbx+38h]; unsigned __int16 *
0x180007544  mov     rax, [rbx+88h]
0x18000754b  mov     rcx, [rbx+80h]
0x180007552  mov     rdx, rsi; unsigned __int16 *
0x180007555  test    r9, r9
0x180007558  jz      short loc_18000757C
0x18000755a  mov     [rsp+278h+Arguments], rax
0x18000755f  mov     qword ptr [rsp+278h+nSize], rcx
0x180007564  mov     eax, [rbx+40h]
0x180007567  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000756b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180007572  mov     rcx, r14; this
0x180007575  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000757a  jmp     short loc_180007593
0x18000757c  mov     [rsp+278h+lpBuffer], rax
0x180007581  mov     r9, rcx; unsigned __int16 *
0x180007584  lea     r8, aHsP; "%hs!%p: "
0x18000758b  mov     rcx, r14; this
0x18000758e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007593  mov     r14, rax
0x180007596  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000759d  test    r9, r9
0x1800075a0  jz      short loc_1800075B7
0x1800075a2  lea     r8, aCallerP; "(caller: %p) "
0x1800075a9  mov     rdx, rsi; unsigned __int16 *
0x1800075ac  mov     rcx, rax; this
0x1800075af  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800075b4  mov     r14, rax
0x1800075b7  call    cs:__imp_GetCurrentThreadId
0x1800075bd  lea     rcx, [rsp+278h+Buffer]
0x1800075c2  mov     [rsp+278h+var_240], rcx
0x1800075c7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800075cb  mov     [rsp+278h+nSize], eax
0x1800075cf  mov     eax, [rbx+44h]
0x1800075d2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800075d6  mov     r9, rdi; unsigned __int16 *
0x1800075d9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800075e0  mov     rdx, rsi; unsigned __int16 *
0x1800075e3  mov     rcx, r14; this
0x1800075e6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800075eb  cmp     [rbx+18h], r15
0x1800075ef  jnz     short loc_180007601
0x1800075f1  cmp     [rbx+48h], r15
0x1800075f5  jnz     short loc_180007601
0x1800075f7  cmp     [rbx+30h], r15
0x1800075fb  jz      loc_180007691
0x180007601  lea     r8, asc_1800174F0; "    "
0x180007608  mov     rdx, rsi; unsigned __int16 *
0x18000760b  mov     rcx, rax; this
0x18000760e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007613  mov     r9, [rbx+18h]; unsigned __int16 *
0x180007617  test    r9, r9
0x18000761a  jz      short loc_18000762E
0x18000761c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180007623  mov     rdx, rsi; unsigned __int16 *
0x180007626  mov     rcx, rax; this
0x180007629  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000762e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180007632  test    r9, r9
0x180007635  jz      short loc_180007649
0x180007637  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000763e  mov     rdx, rsi; unsigned __int16 *
0x180007641  mov     rcx, rax; this
0x180007644  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007649  mov     rcx, [rbx+28h]
0x18000764d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180007651  mov     rdx, rsi; unsigned __int16 *
0x180007654  test    rcx, rcx
0x180007657  jz      short loc_18000766F
0x180007659  mov     [rsp+278h+lpBuffer], rcx
0x18000765e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180007665  mov     rcx, rax; this
0x180007668  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000766d  jmp     short loc_180007691
0x18000766f  mov     rcx, rax; this
0x180007672  test    r9, r9
0x180007675  jz      short loc_180007685
0x180007677  lea     r8, aHs; "[%hs]\n"
0x18000767e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007683  jmp     short loc_180007691
0x180007685  lea     r8, asc_180017568; "\n"
0x18000768c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007691  xor     eax, eax
0x180007693  mov     rcx, [rsp+278h+var_38]
0x18000769b  xor     rcx, rsp; StackCookie
0x18000769e  call    __security_check_cookie
0x1800076a3  mov     rbx, [rsp+278h+arg_18]
0x1800076ab  add     rsp, 250h
0x1800076b2  pop     r15
0x1800076b4  pop     r14
0x1800076b6  pop     rdi
0x1800076b7  pop     rsi
0x1800076b8  pop     rbp
0x1800076b9  retn
```
