# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800061e4`
- end: `0x18000649a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800034a4`
- `0x18000370c`
- `0x180006e40`

## callees

- `0x180002240`
- `0x180002b60`
- `0x1800061e4`
- `0x180007140`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006397`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006397`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006316`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006316`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rdi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rsi
  __int64 v13; // rax
  unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // r9
  wil::details *v16; // r14
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
  v7 = (void (__fastcall *)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
  *(_WORD *)this = 0;
  if ( v7 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      v7(a3, this, a2, a4);
      if ( *(_WORD *)this )
        return 0;
    }
  }
  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      v9 = "ReturnHr";
      v8 = "ReturnNt";
    }
    else
    {
      if ( *(_DWORD *)a3 != 2 )
      {
        if ( *(_DWORD *)a3 == 3 )
          v8 = "FailFast";
        else
          v8 = byte_18002AE78;
        goto LABEL_18;
      }
      v9 = "LogHr";
      v8 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v8 = v9;
    goto LABEL_18;
  }
  v8 = "Exception";
LABEL_18:
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
  {
    v10 = *(_DWORD *)(a3 + 12);
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(v10, Buffer, 0x100u);
  }
  else
  {
    v10 = *(_DWORD *)(a3 + 8);
    FormatMessageW(0x1200u, 0, v10, 0x400u, Buffer, 0x100u, 0);
  }
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = (unsigned __int16 *)((char *)this + 2 * (_QWORD)a2);
  v13 = *(_QWORD *)(a3 + 136);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, *(_QWORD *)(a3 + 128), v13);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs!%p: ", *(const unsigned __int16 **)(a3 + 128), v13);
  }
  v15 = *(const unsigned __int16 **)(a3 + 144);
  v16 = (wil::details *)v14;
  if ( v15 )
    v16 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v12, L"(caller: %p) ", v15);
  LODWORD(Arguments) = v10;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v16,
                          v12,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const unsigned __int16 *)v8,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v12, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800061e4  mov     [rsp+arg_18], rbx
0x1800061e9  push    rbp
0x1800061ea  push    rsi
0x1800061eb  push    rdi
0x1800061ec  push    r14
0x1800061ee  push    r15
0x1800061f0  sub     rsp, 250h
0x1800061f7  mov     rax, cs:__security_cookie
0x1800061fe  xor     rax, rsp
0x180006201  mov     [rsp+278h+var_38], rax
0x180006209  xor     r15d, r15d
0x18000620c  mov     rbx, r8
0x18000620f  mov     rsi, rdx
0x180006212  mov     r14, rcx
0x180006215  test    rdx, rdx
0x180006218  jz      loc_180006471
0x18000621e  test    rcx, rcx
0x180006221  jz      loc_180006471
0x180006227  mov     rax, cs:g_pfnResultLoggingCallback
0x18000622e  mov     [rcx], r15w
0x180006232  test    rax, rax
0x180006235  jz      short loc_180006258
0x180006237  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000623e  jz      short loc_180006258
0x180006240  mov     r8, rdx
0x180006243  mov     rdx, rcx
0x180006246  mov     rcx, rbx
0x180006249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000624e  cmp     [r14], r15w
0x180006252  jnz     loc_180006471
0x180006258  mov     ecx, [rbx]
0x18000625a  mov     bpl, 8
0x18000625d  test    ecx, ecx
0x18000625f  jz      short loc_1800062AA
0x180006261  sub     ecx, 1
0x180006264  jz      short loc_180006292
0x180006266  sub     ecx, 1
0x180006269  jz      short loc_180006282
0x18000626b  cmp     ecx, 1
0x18000626e  jz      short loc_180006279
0x180006270  lea     rdi, byte_18002AE78
0x180006277  jmp     short loc_1800062B1
0x180006279  lea     rdi, aFailfast; "FailFast"
0x180006280  jmp     short loc_1800062B1
0x180006282  lea     rax, aLoghr; "LogHr"
0x180006289  lea     rdi, aLognt; "LogNt"
0x180006290  jmp     short loc_1800062A0
0x180006292  lea     rax, aReturnhr; "ReturnHr"
0x180006299  lea     rdi, aReturnnt; "ReturnNt"
0x1800062a0  test    [rbx+4], bpl
0x1800062a4  cmovz   rdi, rax
0x1800062a8  jmp     short loc_1800062B1
0x1800062aa  lea     rdi, aException; "Exception"
0x1800062b1  xor     edx, edx; Val
0x1800062b3  lea     rcx, [rsp+278h+Buffer]; void *
0x1800062b8  mov     r8d, 200h; Size
0x1800062be  call    memset_0
0x1800062c3  test    [rbx+4], bpl
0x1800062c7  jz      short loc_1800062EC
0x1800062c9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800062d0  mov     ebp, [rbx+0Ch]
0x1800062d3  test    rax, rax
0x1800062d6  jz      short loc_18000631C
0x1800062d8  mov     r8d, 100h
0x1800062de  lea     rdx, [rsp+278h+Buffer]
0x1800062e3  mov     ecx, ebp
0x1800062e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062ea  jmp     short loc_18000631C
0x1800062ec  mov     ebp, [rbx+8]
0x1800062ef  lea     rax, [rsp+278h+Buffer]
0x1800062f4  mov     [rsp+278h+Arguments], r15; Arguments
0x1800062f9  mov     r8d, ebp; dwMessageId
0x1800062fc  mov     [rsp+278h+nSize], 100h; nSize
0x180006304  mov     r9d, 400h; dwLanguageId
0x18000630a  xor     edx, edx; lpSource
0x18000630c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006311  mov     ecx, 1200h; dwFlags
0x180006316  call    cs:__imp_FormatMessageW
0x18000631c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180006320  lea     rsi, [r14+rsi*2]
0x180006324  mov     rax, [rbx+88h]
0x18000632b  mov     rdx, rsi; unsigned __int16 *
0x18000632e  mov     rcx, [rbx+80h]
0x180006335  test    r9, r9
0x180006338  jz      short loc_18000635C
0x18000633a  mov     [rsp+278h+Arguments], rax
0x18000633f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006346  mov     eax, [rbx+40h]
0x180006349  mov     qword ptr [rsp+278h+nSize], rcx
0x18000634e  mov     rcx, r14; this
0x180006351  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006355  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000635a  jmp     short loc_180006373
0x18000635c  mov     r9, rcx; unsigned __int16 *
0x18000635f  mov     [rsp+278h+lpBuffer], rax
0x180006364  mov     rcx, r14; this
0x180006367  lea     r8, aHsP; "%hs!%p: "
0x18000636e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006373  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000637a  mov     r14, rax
0x18000637d  test    r9, r9
0x180006380  jz      short loc_180006397
0x180006382  lea     r8, aCallerP; "(caller: %p) "
0x180006389  mov     rdx, rsi; unsigned __int16 *
0x18000638c  mov     rcx, rax; this
0x18000638f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006394  mov     r14, rax
0x180006397  call    cs:__imp_GetCurrentThreadId
0x18000639d  lea     rcx, [rsp+278h+Buffer]
0x1800063a2  mov     r9, rdi; unsigned __int16 *
0x1800063a5  mov     [rsp+278h+var_240], rcx
0x1800063aa  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800063b1  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800063b5  mov     rdx, rsi; unsigned __int16 *
0x1800063b8  mov     [rsp+278h+nSize], eax
0x1800063bc  mov     rcx, r14; this
0x1800063bf  mov     eax, [rbx+44h]
0x1800063c2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800063c6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800063cb  cmp     [rbx+18h], r15
0x1800063cf  jnz     short loc_1800063E1
0x1800063d1  cmp     [rbx+48h], r15
0x1800063d5  jnz     short loc_1800063E1
0x1800063d7  cmp     [rbx+30h], r15
0x1800063db  jz      loc_180006471
0x1800063e1  lea     r8, asc_18002AF68; "    "
0x1800063e8  mov     rdx, rsi; unsigned __int16 *
0x1800063eb  mov     rcx, rax; this
0x1800063ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800063f3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800063f7  test    r9, r9
0x1800063fa  jz      short loc_18000640E
0x1800063fc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006403  mov     rdx, rsi; unsigned __int16 *
0x180006406  mov     rcx, rax; this
0x180006409  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000640e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180006412  test    r9, r9
0x180006415  jz      short loc_180006429
0x180006417  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000641e  mov     rdx, rsi; unsigned __int16 *
0x180006421  mov     rcx, rax; this
0x180006424  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006429  mov     rcx, [rbx+28h]
0x18000642d  mov     rdx, rsi; unsigned __int16 *
0x180006430  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006434  test    rcx, rcx
0x180006437  jz      short loc_18000644F
0x180006439  mov     [rsp+278h+lpBuffer], rcx
0x18000643e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006445  mov     rcx, rax; this
0x180006448  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000644d  jmp     short loc_180006471
0x18000644f  mov     rcx, rax; this
0x180006452  test    r9, r9
0x180006455  jz      short loc_180006465
0x180006457  lea     r8, aHs; "[%hs]\n"
0x18000645e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006463  jmp     short loc_180006471
0x180006465  lea     r8, asc_18002AFE0; "\n"
0x18000646c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006471  xor     eax, eax
0x180006473  mov     rcx, [rsp+278h+var_38]
0x18000647b  xor     rcx, rsp; StackCookie
0x18000647e  call    __security_check_cookie
0x180006483  mov     rbx, [rsp+278h+arg_18]
0x18000648b  add     rsp, 250h
0x180006492  pop     r15
0x180006494  pop     r14
0x180006496  pop     rdi
0x180006497  pop     rsi
0x180006498  pop     rbp
0x180006499  retn
```
