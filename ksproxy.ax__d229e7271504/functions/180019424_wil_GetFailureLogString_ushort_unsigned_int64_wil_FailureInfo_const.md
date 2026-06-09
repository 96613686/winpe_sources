# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180019424`
- end: `0x1800196e7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180020428`
- `0x1800237f8`

## callees

- `0x180017174`
- `0x180019424`
- `0x18001f620`
- `0x18001ffb0`
- `0x180045010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180019556`
- `KERNEL32!FormatMessageW` at `0x180019556`
- `KERNEL32!GetCurrentThreadId` at `0x1800195dd`
- `KERNEL32!GetCurrentThreadId` at `0x1800195dd`

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
  char *v12; // rsi
  __int64 v13; // rax
  unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // r9
  unsigned __int16 *v16; // r14
  unsigned __int16 *v17; // rax
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
          v8 = (const char *)&byte_18004A39B;
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
  v12 = (char *)this + 2 * (_QWORD)a2;
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
  v16 = v14;
  if ( v15 )
    v16 = wil::details::LogStringPrintf((wil::details *)v14, v12, L"(caller: %p) ", v15);
  LODWORD(Arguments) = v10;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = wil::details::LogStringPrintf(
          (wil::details *)v16,
          v12,
          L"%hs(%d) tid(%x) %08X %ws",
          (const unsigned __int16 *)v8,
          lpBuffera,
          *(_QWORD *)nSize,
          Arguments,
          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf((wil::details *)v17, v12, L"    ", v18);
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
0x180019424  mov     [rsp+arg_18], rbx
0x180019429  push    rbp
0x18001942a  push    rsi
0x18001942b  push    rdi
0x18001942c  push    r14
0x18001942e  push    r15
0x180019430  sub     rsp, 250h
0x180019437  mov     rax, cs:__security_cookie
0x18001943e  xor     rax, rsp
0x180019441  mov     [rsp+278h+var_38], rax
0x180019449  xor     r15d, r15d
0x18001944c  mov     rbx, r8
0x18001944f  mov     rsi, rdx
0x180019452  mov     r14, rcx
0x180019455  test    rdx, rdx
0x180019458  jz      loc_1800196BD
0x18001945e  test    rcx, rcx
0x180019461  jz      loc_1800196BD
0x180019467  mov     rax, cs:g_pfnResultLoggingCallback
0x18001946e  mov     [rcx], r15w
0x180019472  test    rax, rax
0x180019475  jz      short loc_180019498
0x180019477  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001947e  jz      short loc_180019498
0x180019480  mov     r8, rdx
0x180019483  mov     rdx, rcx
0x180019486  mov     rcx, rbx
0x180019489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001948e  cmp     [r14], r15w
0x180019492  jnz     loc_1800196BD
0x180019498  mov     ecx, [rbx]
0x18001949a  mov     bpl, 8
0x18001949d  test    ecx, ecx
0x18001949f  jz      short loc_1800194EA
0x1800194a1  sub     ecx, 1
0x1800194a4  jz      short loc_1800194D2
0x1800194a6  sub     ecx, 1
0x1800194a9  jz      short loc_1800194C2
0x1800194ab  cmp     ecx, 1
0x1800194ae  jz      short loc_1800194B9
0x1800194b0  lea     rdi, byte_18004A39B
0x1800194b7  jmp     short loc_1800194F1
0x1800194b9  lea     rdi, aFailfast; "FailFast"
0x1800194c0  jmp     short loc_1800194F1
0x1800194c2  lea     rax, aLoghr; "LogHr"
0x1800194c9  lea     rdi, aLognt; "LogNt"
0x1800194d0  jmp     short loc_1800194E0
0x1800194d2  lea     rax, aReturnhr; "ReturnHr"
0x1800194d9  lea     rdi, aReturnnt; "ReturnNt"
0x1800194e0  test    [rbx+4], bpl
0x1800194e4  cmovz   rdi, rax
0x1800194e8  jmp     short loc_1800194F1
0x1800194ea  lea     rdi, aException; "Exception"
0x1800194f1  xor     edx, edx; Val
0x1800194f3  lea     rcx, [rsp+278h+Buffer]; void *
0x1800194f8  mov     r8d, 200h; Size
0x1800194fe  call    memset_0
0x180019503  test    [rbx+4], bpl
0x180019507  jz      short loc_18001952C
0x180019509  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180019510  mov     ebp, [rbx+0Ch]
0x180019513  test    rax, rax
0x180019516  jz      short loc_180019562
0x180019518  mov     r8d, 100h
0x18001951e  lea     rdx, [rsp+278h+Buffer]
0x180019523  mov     ecx, ebp
0x180019525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001952a  jmp     short loc_180019562
0x18001952c  mov     ebp, [rbx+8]
0x18001952f  lea     rax, [rsp+278h+Buffer]
0x180019534  mov     [rsp+278h+Arguments], r15; Arguments
0x180019539  mov     r8d, ebp; dwMessageId
0x18001953c  mov     [rsp+278h+nSize], 100h; nSize
0x180019544  mov     r9d, 400h; dwLanguageId
0x18001954a  xor     edx, edx; lpSource
0x18001954c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180019551  mov     ecx, 1200h; dwFlags
0x180019556  call    cs:__imp_FormatMessageW
0x18001955d  nop     dword ptr [rax+rax+00h]
0x180019562  mov     r9, [rbx+38h]; unsigned __int16 *
0x180019566  lea     rsi, [r14+rsi*2]
0x18001956a  mov     rax, [rbx+88h]
0x180019571  mov     rdx, rsi; unsigned __int16 *
0x180019574  mov     rcx, [rbx+80h]
0x18001957b  test    r9, r9
0x18001957e  jz      short loc_1800195A2
0x180019580  mov     [rsp+278h+Arguments], rax
0x180019585  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18001958c  mov     eax, [rbx+40h]
0x18001958f  mov     qword ptr [rsp+278h+nSize], rcx
0x180019594  mov     rcx, r14; this
0x180019597  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001959b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800195a0  jmp     short loc_1800195B9
0x1800195a2  mov     r9, rcx; unsigned __int16 *
0x1800195a5  mov     [rsp+278h+lpBuffer], rax
0x1800195aa  mov     rcx, r14; this
0x1800195ad  lea     r8, aHsP; "%hs!%p: "
0x1800195b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800195b9  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800195c0  mov     r14, rax
0x1800195c3  test    r9, r9
0x1800195c6  jz      short loc_1800195DD
0x1800195c8  lea     r8, aCallerP; "(caller: %p) "
0x1800195cf  mov     rdx, rsi; unsigned __int16 *
0x1800195d2  mov     rcx, rax; this
0x1800195d5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800195da  mov     r14, rax
0x1800195dd  call    cs:__imp_GetCurrentThreadId
0x1800195e4  nop     dword ptr [rax+rax+00h]
0x1800195e9  lea     rcx, [rsp+278h+Buffer]
0x1800195ee  mov     r9, rdi; unsigned __int16 *
0x1800195f1  mov     [rsp+278h+var_240], rcx
0x1800195f6  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800195fd  mov     dword ptr [rsp+278h+Arguments], ebp
0x180019601  mov     rdx, rsi; unsigned __int16 *
0x180019604  mov     [rsp+278h+nSize], eax
0x180019608  mov     rcx, r14; this
0x18001960b  mov     eax, [rbx+44h]
0x18001960e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180019612  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180019617  cmp     [rbx+18h], r15
0x18001961b  jnz     short loc_18001962D
0x18001961d  cmp     [rbx+48h], r15
0x180019621  jnz     short loc_18001962D
0x180019623  cmp     [rbx+30h], r15
0x180019627  jz      loc_1800196BD
0x18001962d  lea     r8, asc_18004A488; "    "
0x180019634  mov     rdx, rsi; unsigned __int16 *
0x180019637  mov     rcx, rax; this
0x18001963a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001963f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180019643  test    r9, r9
0x180019646  jz      short loc_18001965A
0x180019648  lea     r8, aMsgWs; "Msg:[%ws] "
0x18001964f  mov     rdx, rsi; unsigned __int16 *
0x180019652  mov     rcx, rax; this
0x180019655  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001965a  mov     r9, [rbx+48h]; unsigned __int16 *
0x18001965e  test    r9, r9
0x180019661  jz      short loc_180019675
0x180019663  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001966a  mov     rdx, rsi; unsigned __int16 *
0x18001966d  mov     rcx, rax; this
0x180019670  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180019675  mov     rcx, [rbx+28h]
0x180019679  mov     rdx, rsi; unsigned __int16 *
0x18001967c  mov     r9, [rbx+30h]; unsigned __int16 *
0x180019680  test    rcx, rcx
0x180019683  jz      short loc_18001969B
0x180019685  mov     [rsp+278h+lpBuffer], rcx
0x18001968a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180019691  mov     rcx, rax; this
0x180019694  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180019699  jmp     short loc_1800196BD
0x18001969b  mov     rcx, rax; this
0x18001969e  test    r9, r9
0x1800196a1  jz      short loc_1800196B1
0x1800196a3  lea     r8, aHs; "[%hs]\n"
0x1800196aa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800196af  jmp     short loc_1800196BD
0x1800196b1  lea     r8, asc_18004A500; "\n"
0x1800196b8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800196bd  xor     eax, eax
0x1800196bf  mov     rcx, [rsp+278h+var_38]
0x1800196c7  xor     rcx, rsp; StackCookie
0x1800196ca  call    __security_check_cookie
0x1800196cf  mov     rbx, [rsp+278h+arg_18]
0x1800196d7  add     rsp, 250h
0x1800196de  pop     r15
0x1800196e0  pop     r14
0x1800196e2  pop     rdi
0x1800196e3  pop     rsi
0x1800196e4  pop     rbp
0x1800196e5  retn
```
