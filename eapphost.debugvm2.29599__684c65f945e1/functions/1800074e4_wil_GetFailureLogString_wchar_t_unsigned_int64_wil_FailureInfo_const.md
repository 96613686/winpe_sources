# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800074e4`
- end: `0x18000779a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800044dc`
- `0x1800080f8`
- `0x18000859c`
- `0x180009990`

## callees

- `0x180002a90`
- `0x18000343c`
- `0x1800074e4`
- `0x1800083f8`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007616`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007616`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007697`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007697`

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
          v7 = (const char *)&qword_18003BB78;
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
0x1800074e4  mov     [rsp+arg_18], rbx
0x1800074e9  push    rbp
0x1800074ea  push    rsi
0x1800074eb  push    rdi
0x1800074ec  push    r14
0x1800074ee  push    r15
0x1800074f0  sub     rsp, 250h
0x1800074f7  mov     rax, cs:__security_cookie
0x1800074fe  xor     rax, rsp
0x180007501  mov     [rsp+278h+var_38], rax
0x180007509  mov     rbx, r8
0x18000750c  mov     rsi, rdx
0x18000750f  mov     r14, rcx
0x180007512  xor     r15d, r15d
0x180007515  test    rdx, rdx
0x180007518  jz      loc_180007771
0x18000751e  test    rcx, rcx
0x180007521  jz      loc_180007771
0x180007527  mov     [rcx], r15w
0x18000752b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007532  test    rax, rax
0x180007535  jz      short loc_180007558
0x180007537  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000753e  jz      short loc_180007558
0x180007540  mov     r8, rdx
0x180007543  mov     rdx, rcx
0x180007546  mov     rcx, rbx
0x180007549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000754e  cmp     [r14], r15w
0x180007552  jnz     loc_180007771
0x180007558  mov     ecx, [rbx]
0x18000755a  mov     bpl, 8
0x18000755d  test    ecx, ecx
0x18000755f  jz      short loc_1800075AA
0x180007561  sub     ecx, 1
0x180007564  jz      short loc_180007592
0x180007566  sub     ecx, 1
0x180007569  jz      short loc_180007582
0x18000756b  cmp     ecx, 1
0x18000756e  jz      short loc_180007579
0x180007570  lea     rdi, qword_18003BB78
0x180007577  jmp     short loc_1800075B1
0x180007579  lea     rdi, aFailfast; "FailFast"
0x180007580  jmp     short loc_1800075B1
0x180007582  lea     rax, aLoghr; "LogHr"
0x180007589  lea     rdi, aLognt; "LogNt"
0x180007590  jmp     short loc_1800075A0
0x180007592  lea     rax, aReturnhr; "ReturnHr"
0x180007599  lea     rdi, aReturnnt; "ReturnNt"
0x1800075a0  test    [rbx+4], bpl
0x1800075a4  cmovz   rdi, rax
0x1800075a8  jmp     short loc_1800075B1
0x1800075aa  lea     rdi, aException; "Exception"
0x1800075b1  xor     edx, edx; Val
0x1800075b3  mov     r8d, 200h; Size
0x1800075b9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800075be  call    memset_0
0x1800075c3  test    [rbx+4], bpl
0x1800075c7  jz      short loc_1800075EC
0x1800075c9  mov     ebp, [rbx+0Ch]
0x1800075cc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x1800075d3  test    rax, rax
0x1800075d6  jz      short loc_18000761C
0x1800075d8  mov     r8d, 100h
0x1800075de  lea     rdx, [rsp+278h+Buffer]
0x1800075e3  mov     ecx, ebp
0x1800075e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075ea  jmp     short loc_18000761C
0x1800075ec  mov     ebp, [rbx+8]
0x1800075ef  mov     [rsp+278h+Arguments], r15; Arguments
0x1800075f4  mov     [rsp+278h+nSize], 100h; nSize
0x1800075fc  lea     rax, [rsp+278h+Buffer]
0x180007601  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180007606  mov     r9d, 400h; dwLanguageId
0x18000760c  mov     r8d, ebp; dwMessageId
0x18000760f  xor     edx, edx; lpSource
0x180007611  mov     ecx, 1200h; dwFlags
0x180007616  call    cs:__imp_FormatMessageW
0x18000761c  lea     rsi, [r14+rsi*2]
0x180007620  mov     r9, [rbx+38h]; wchar_t *
0x180007624  mov     rax, [rbx+88h]
0x18000762b  mov     rcx, [rbx+80h]
0x180007632  mov     rdx, rsi; wchar_t *
0x180007635  test    r9, r9
0x180007638  jz      short loc_18000765C
0x18000763a  mov     [rsp+278h+Arguments], rax
0x18000763f  mov     qword ptr [rsp+278h+nSize], rcx
0x180007644  mov     eax, [rbx+40h]
0x180007647  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000764b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180007652  mov     rcx, r14; this
0x180007655  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000765a  jmp     short loc_180007673
0x18000765c  mov     [rsp+278h+lpBuffer], rax
0x180007661  mov     r9, rcx; wchar_t *
0x180007664  lea     r8, aHsP; "%hs!%p: "
0x18000766b  mov     rcx, r14; this
0x18000766e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007673  mov     r14, rax
0x180007676  mov     r9, [rbx+90h]; wchar_t *
0x18000767d  test    r9, r9
0x180007680  jz      short loc_180007697
0x180007682  lea     r8, aCallerP; "(caller: %p) "
0x180007689  mov     rdx, rsi; wchar_t *
0x18000768c  mov     rcx, rax; this
0x18000768f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007694  mov     r14, rax
0x180007697  call    cs:__imp_GetCurrentThreadId
0x18000769d  lea     rcx, [rsp+278h+Buffer]
0x1800076a2  mov     [rsp+278h+var_240], rcx
0x1800076a7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800076ab  mov     [rsp+278h+nSize], eax
0x1800076af  mov     eax, [rbx+44h]
0x1800076b2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800076b6  mov     r9, rdi; wchar_t *
0x1800076b9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800076c0  mov     rdx, rsi; wchar_t *
0x1800076c3  mov     rcx, r14; this
0x1800076c6  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800076cb  cmp     [rbx+18h], r15
0x1800076cf  jnz     short loc_1800076E1
0x1800076d1  cmp     [rbx+48h], r15
0x1800076d5  jnz     short loc_1800076E1
0x1800076d7  cmp     [rbx+30h], r15
0x1800076db  jz      loc_180007771
0x1800076e1  lea     r8, asc_18003BC68; "    "
0x1800076e8  mov     rdx, rsi; wchar_t *
0x1800076eb  mov     rcx, rax; this
0x1800076ee  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800076f3  mov     r9, [rbx+18h]; wchar_t *
0x1800076f7  test    r9, r9
0x1800076fa  jz      short loc_18000770E
0x1800076fc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180007703  mov     rdx, rsi; wchar_t *
0x180007706  mov     rcx, rax; this
0x180007709  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000770e  mov     r9, [rbx+48h]; wchar_t *
0x180007712  test    r9, r9
0x180007715  jz      short loc_180007729
0x180007717  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000771e  mov     rdx, rsi; wchar_t *
0x180007721  mov     rcx, rax; this
0x180007724  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007729  mov     rcx, [rbx+28h]
0x18000772d  mov     r9, [rbx+30h]; wchar_t *
0x180007731  mov     rdx, rsi; wchar_t *
0x180007734  test    rcx, rcx
0x180007737  jz      short loc_18000774F
0x180007739  mov     [rsp+278h+lpBuffer], rcx
0x18000773e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180007745  mov     rcx, rax; this
0x180007748  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000774d  jmp     short loc_180007771
0x18000774f  mov     rcx, rax; this
0x180007752  test    r9, r9
0x180007755  jz      short loc_180007765
0x180007757  lea     r8, aHs; "[%hs]\n"
0x18000775e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007763  jmp     short loc_180007771
0x180007765  lea     r8, asc_18003BCE0; "\n"
0x18000776c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007771  xor     eax, eax
0x180007773  mov     rcx, [rsp+278h+var_38]
0x18000777b  xor     rcx, rsp; StackCookie
0x18000777e  call    __security_check_cookie
0x180007783  mov     rbx, [rsp+278h+arg_18]
0x18000778b  add     rsp, 250h
0x180007792  pop     r15
0x180007794  pop     r14
0x180007796  pop     rdi
0x180007797  pop     rsi
0x180007798  pop     rbp
0x180007799  retn
```
