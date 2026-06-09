# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1400033a4`
- end: `0x14000365a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140002334`
- `0x1400025a4`
- `0x140003d00`

## callees

- `0x1400017bf`
- `0x1400033a4`
- `0x140004000`
- `0x140004cd0`
- `0x140005010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140003557`
- `KERNEL32!GetCurrentThreadId` at `0x140003557`
- `KERNEL32!FormatMessageW` at `0x1400034d6`
- `KERNEL32!FormatMessageW` at `0x1400034d6`

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
          v8 = (const char *)&qword_140006628;
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
0x1400033a4  mov     [rsp+arg_18], rbx
0x1400033a9  push    rbp
0x1400033aa  push    rsi
0x1400033ab  push    rdi
0x1400033ac  push    r14
0x1400033ae  push    r15
0x1400033b0  sub     rsp, 250h
0x1400033b7  mov     rax, cs:__security_cookie
0x1400033be  xor     rax, rsp
0x1400033c1  mov     [rsp+278h+var_38], rax
0x1400033c9  xor     r15d, r15d
0x1400033cc  mov     rbx, r8
0x1400033cf  mov     rsi, rdx
0x1400033d2  mov     r14, rcx
0x1400033d5  test    rdx, rdx
0x1400033d8  jz      loc_140003631
0x1400033de  test    rcx, rcx
0x1400033e1  jz      loc_140003631
0x1400033e7  mov     rax, cs:g_pfnResultLoggingCallback
0x1400033ee  mov     [rcx], r15w
0x1400033f2  test    rax, rax
0x1400033f5  jz      short loc_140003418
0x1400033f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400033fe  jz      short loc_140003418
0x140003400  mov     r8, rdx
0x140003403  mov     rdx, rcx
0x140003406  mov     rcx, rbx
0x140003409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000340e  cmp     [r14], r15w
0x140003412  jnz     loc_140003631
0x140003418  mov     ecx, [rbx]
0x14000341a  mov     bpl, 8
0x14000341d  test    ecx, ecx
0x14000341f  jz      short loc_14000346A
0x140003421  sub     ecx, 1
0x140003424  jz      short loc_140003452
0x140003426  sub     ecx, 1
0x140003429  jz      short loc_140003442
0x14000342b  cmp     ecx, 1
0x14000342e  jz      short loc_140003439
0x140003430  lea     rdi, qword_140006628
0x140003437  jmp     short loc_140003471
0x140003439  lea     rdi, aFailfast; "FailFast"
0x140003440  jmp     short loc_140003471
0x140003442  lea     rax, aLoghr; "LogHr"
0x140003449  lea     rdi, aLognt; "LogNt"
0x140003450  jmp     short loc_140003460
0x140003452  lea     rax, aReturnhr; "ReturnHr"
0x140003459  lea     rdi, aReturnnt; "ReturnNt"
0x140003460  test    [rbx+4], bpl
0x140003464  cmovz   rdi, rax
0x140003468  jmp     short loc_140003471
0x14000346a  lea     rdi, aException; "Exception"
0x140003471  xor     edx, edx; Val
0x140003473  lea     rcx, [rsp+278h+Buffer]; void *
0x140003478  mov     r8d, 200h; Size
0x14000347e  call    memset_0
0x140003483  test    [rbx+4], bpl
0x140003487  jz      short loc_1400034AC
0x140003489  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140003490  mov     ebp, [rbx+0Ch]
0x140003493  test    rax, rax
0x140003496  jz      short loc_1400034DC
0x140003498  mov     r8d, 100h
0x14000349e  lea     rdx, [rsp+278h+Buffer]
0x1400034a3  mov     ecx, ebp
0x1400034a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400034aa  jmp     short loc_1400034DC
0x1400034ac  mov     ebp, [rbx+8]
0x1400034af  lea     rax, [rsp+278h+Buffer]
0x1400034b4  mov     [rsp+278h+Arguments], r15; Arguments
0x1400034b9  mov     r8d, ebp; dwMessageId
0x1400034bc  mov     [rsp+278h+nSize], 100h; nSize
0x1400034c4  mov     r9d, 400h; dwLanguageId
0x1400034ca  xor     edx, edx; lpSource
0x1400034cc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1400034d1  mov     ecx, 1200h; dwFlags
0x1400034d6  call    cs:__imp_FormatMessageW
0x1400034dc  mov     r9, [rbx+38h]; unsigned __int16 *
0x1400034e0  lea     rsi, [r14+rsi*2]
0x1400034e4  mov     rax, [rbx+88h]
0x1400034eb  mov     rdx, rsi; unsigned __int16 *
0x1400034ee  mov     rcx, [rbx+80h]
0x1400034f5  test    r9, r9
0x1400034f8  jz      short loc_14000351C
0x1400034fa  mov     [rsp+278h+Arguments], rax
0x1400034ff  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140003506  mov     eax, [rbx+40h]
0x140003509  mov     qword ptr [rsp+278h+nSize], rcx
0x14000350e  mov     rcx, r14; this
0x140003511  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140003515  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000351a  jmp     short loc_140003533
0x14000351c  mov     r9, rcx; unsigned __int16 *
0x14000351f  mov     [rsp+278h+lpBuffer], rax
0x140003524  mov     rcx, r14; this
0x140003527  lea     r8, aHsP; "%hs!%p: "
0x14000352e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003533  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000353a  mov     r14, rax
0x14000353d  test    r9, r9
0x140003540  jz      short loc_140003557
0x140003542  lea     r8, aCallerP; "(caller: %p) "
0x140003549  mov     rdx, rsi; unsigned __int16 *
0x14000354c  mov     rcx, rax; this
0x14000354f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003554  mov     r14, rax
0x140003557  call    cs:__imp_GetCurrentThreadId
0x14000355d  lea     rcx, [rsp+278h+Buffer]
0x140003562  mov     r9, rdi; unsigned __int16 *
0x140003565  mov     [rsp+278h+var_240], rcx
0x14000356a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140003571  mov     dword ptr [rsp+278h+Arguments], ebp
0x140003575  mov     rdx, rsi; unsigned __int16 *
0x140003578  mov     [rsp+278h+nSize], eax
0x14000357c  mov     rcx, r14; this
0x14000357f  mov     eax, [rbx+44h]
0x140003582  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140003586  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000358b  cmp     [rbx+18h], r15
0x14000358f  jnz     short loc_1400035A1
0x140003591  cmp     [rbx+48h], r15
0x140003595  jnz     short loc_1400035A1
0x140003597  cmp     [rbx+30h], r15
0x14000359b  jz      loc_140003631
0x1400035a1  lea     r8, asc_140006718; "    "
0x1400035a8  mov     rdx, rsi; unsigned __int16 *
0x1400035ab  mov     rcx, rax; this
0x1400035ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400035b3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1400035b7  test    r9, r9
0x1400035ba  jz      short loc_1400035CE
0x1400035bc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1400035c3  mov     rdx, rsi; unsigned __int16 *
0x1400035c6  mov     rcx, rax; this
0x1400035c9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400035ce  mov     r9, [rbx+48h]; unsigned __int16 *
0x1400035d2  test    r9, r9
0x1400035d5  jz      short loc_1400035E9
0x1400035d7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1400035de  mov     rdx, rsi; unsigned __int16 *
0x1400035e1  mov     rcx, rax; this
0x1400035e4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400035e9  mov     rcx, [rbx+28h]
0x1400035ed  mov     rdx, rsi; unsigned __int16 *
0x1400035f0  mov     r9, [rbx+30h]; unsigned __int16 *
0x1400035f4  test    rcx, rcx
0x1400035f7  jz      short loc_14000360F
0x1400035f9  mov     [rsp+278h+lpBuffer], rcx
0x1400035fe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140003605  mov     rcx, rax; this
0x140003608  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000360d  jmp     short loc_140003631
0x14000360f  mov     rcx, rax; this
0x140003612  test    r9, r9
0x140003615  jz      short loc_140003625
0x140003617  lea     r8, aHs; "[%hs]\n"
0x14000361e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003623  jmp     short loc_140003631
0x140003625  lea     r8, asc_140006790; "\n"
0x14000362c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003631  xor     eax, eax
0x140003633  mov     rcx, [rsp+278h+var_38]
0x14000363b  xor     rcx, rsp; StackCookie
0x14000363e  call    __security_check_cookie
0x140003643  mov     rbx, [rsp+278h+arg_18]
0x14000364b  add     rsp, 250h
0x140003652  pop     r15
0x140003654  pop     r14
0x140003656  pop     rdi
0x140003657  pop     rsi
0x140003658  pop     rbp
0x140003659  retn
```
