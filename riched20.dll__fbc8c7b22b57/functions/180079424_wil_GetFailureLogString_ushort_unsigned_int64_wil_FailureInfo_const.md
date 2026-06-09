# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180079424`
- end: `0x1800796e7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18007742c`
- `0x1800776a4`
- `0x18007a290`

## callees

- `0x180079424`
- `0x18007a5a4`
- `0x180093bca`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800795dd`
- `KERNEL32!GetCurrentThreadId` at `0x1800795dd`
- `KERNEL32!FormatMessageW` at `0x180079556`
- `KERNEL32!FormatMessageW` at `0x180079556`

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
          v8 = (const char *)&word_18009C816;
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
0x180079424  mov     [rsp+arg_18], rbx
0x180079429  push    rbp
0x18007942a  push    rsi
0x18007942b  push    rdi
0x18007942c  push    r14
0x18007942e  push    r15
0x180079430  sub     rsp, 250h
0x180079437  mov     rax, cs:__security_cookie
0x18007943e  xor     rax, rsp
0x180079441  mov     [rsp+278h+var_38], rax
0x180079449  xor     r15d, r15d
0x18007944c  mov     rbx, r8
0x18007944f  mov     rsi, rdx
0x180079452  mov     r14, rcx
0x180079455  test    rdx, rdx
0x180079458  jz      loc_1800796BD
0x18007945e  test    rcx, rcx
0x180079461  jz      loc_1800796BD
0x180079467  mov     rax, cs:g_pfnResultLoggingCallback
0x18007946e  mov     [rcx], r15w
0x180079472  test    rax, rax
0x180079475  jz      short loc_180079498
0x180079477  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18007947e  jz      short loc_180079498
0x180079480  mov     r8, rdx
0x180079483  mov     rdx, rcx
0x180079486  mov     rcx, rbx
0x180079489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007948e  cmp     [r14], r15w
0x180079492  jnz     loc_1800796BD
0x180079498  mov     ecx, [rbx]
0x18007949a  mov     bpl, 8
0x18007949d  test    ecx, ecx
0x18007949f  jz      short loc_1800794EA
0x1800794a1  sub     ecx, 1
0x1800794a4  jz      short loc_1800794D2
0x1800794a6  sub     ecx, 1
0x1800794a9  jz      short loc_1800794C2
0x1800794ab  cmp     ecx, 1
0x1800794ae  jz      short loc_1800794B9
0x1800794b0  lea     rdi, word_18009C816
0x1800794b7  jmp     short loc_1800794F1
0x1800794b9  lea     rdi, aFailfast; "FailFast"
0x1800794c0  jmp     short loc_1800794F1
0x1800794c2  lea     rax, aLoghr; "LogHr"
0x1800794c9  lea     rdi, aLognt; "LogNt"
0x1800794d0  jmp     short loc_1800794E0
0x1800794d2  lea     rax, aReturnhr; "ReturnHr"
0x1800794d9  lea     rdi, aReturnnt; "ReturnNt"
0x1800794e0  test    [rbx+4], bpl
0x1800794e4  cmovz   rdi, rax
0x1800794e8  jmp     short loc_1800794F1
0x1800794ea  lea     rdi, aException; "Exception"
0x1800794f1  xor     edx, edx; Val
0x1800794f3  lea     rcx, [rsp+278h+Buffer]; void *
0x1800794f8  mov     r8d, 200h; Size
0x1800794fe  call    memset_0
0x180079503  test    [rbx+4], bpl
0x180079507  jz      short loc_18007952C
0x180079509  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180079510  mov     ebp, [rbx+0Ch]
0x180079513  test    rax, rax
0x180079516  jz      short loc_180079562
0x180079518  mov     r8d, 100h
0x18007951e  lea     rdx, [rsp+278h+Buffer]
0x180079523  mov     ecx, ebp
0x180079525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007952a  jmp     short loc_180079562
0x18007952c  mov     ebp, [rbx+8]
0x18007952f  lea     rax, [rsp+278h+Buffer]
0x180079534  mov     [rsp+278h+Arguments], r15; Arguments
0x180079539  mov     r8d, ebp; dwMessageId
0x18007953c  mov     [rsp+278h+nSize], 100h; nSize
0x180079544  mov     r9d, 400h; dwLanguageId
0x18007954a  xor     edx, edx; lpSource
0x18007954c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180079551  mov     ecx, 1200h; dwFlags
0x180079556  call    cs:__imp_FormatMessageW
0x18007955d  nop     dword ptr [rax+rax+00h]
0x180079562  mov     r9, [rbx+38h]; unsigned __int16 *
0x180079566  lea     rsi, [r14+rsi*2]
0x18007956a  mov     rax, [rbx+88h]
0x180079571  mov     rdx, rsi; unsigned __int16 *
0x180079574  mov     rcx, [rbx+80h]
0x18007957b  test    r9, r9
0x18007957e  jz      short loc_1800795A2
0x180079580  mov     [rsp+278h+Arguments], rax
0x180079585  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18007958c  mov     eax, [rbx+40h]
0x18007958f  mov     qword ptr [rsp+278h+nSize], rcx
0x180079594  mov     rcx, r14; this
0x180079597  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18007959b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800795a0  jmp     short loc_1800795B9
0x1800795a2  mov     r9, rcx; unsigned __int16 *
0x1800795a5  mov     [rsp+278h+lpBuffer], rax
0x1800795aa  mov     rcx, r14; this
0x1800795ad  lea     r8, aHsP; "%hs!%p: "
0x1800795b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800795b9  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800795c0  mov     r14, rax
0x1800795c3  test    r9, r9
0x1800795c6  jz      short loc_1800795DD
0x1800795c8  lea     r8, aCallerP; "(caller: %p) "
0x1800795cf  mov     rdx, rsi; unsigned __int16 *
0x1800795d2  mov     rcx, rax; this
0x1800795d5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800795da  mov     r14, rax
0x1800795dd  call    cs:__imp_GetCurrentThreadId
0x1800795e4  nop     dword ptr [rax+rax+00h]
0x1800795e9  lea     rcx, [rsp+278h+Buffer]
0x1800795ee  mov     r9, rdi; unsigned __int16 *
0x1800795f1  mov     [rsp+278h+var_240], rcx
0x1800795f6  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800795fd  mov     dword ptr [rsp+278h+Arguments], ebp
0x180079601  mov     rdx, rsi; unsigned __int16 *
0x180079604  mov     [rsp+278h+nSize], eax
0x180079608  mov     rcx, r14; this
0x18007960b  mov     eax, [rbx+44h]
0x18007960e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180079612  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180079617  cmp     [rbx+18h], r15
0x18007961b  jnz     short loc_18007962D
0x18007961d  cmp     [rbx+48h], r15
0x180079621  jnz     short loc_18007962D
0x180079623  cmp     [rbx+30h], r15
0x180079627  jz      loc_1800796BD
0x18007962d  lea     r8, asc_18009C900; "    "
0x180079634  mov     rdx, rsi; unsigned __int16 *
0x180079637  mov     rcx, rax; this
0x18007963a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18007963f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180079643  test    r9, r9
0x180079646  jz      short loc_18007965A
0x180079648  lea     r8, aMsgWs; "Msg:[%ws] "
0x18007964f  mov     rdx, rsi; unsigned __int16 *
0x180079652  mov     rcx, rax; this
0x180079655  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18007965a  mov     r9, [rbx+48h]; unsigned __int16 *
0x18007965e  test    r9, r9
0x180079661  jz      short loc_180079675
0x180079663  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18007966a  mov     rdx, rsi; unsigned __int16 *
0x18007966d  mov     rcx, rax; this
0x180079670  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180079675  mov     rcx, [rbx+28h]
0x180079679  mov     rdx, rsi; unsigned __int16 *
0x18007967c  mov     r9, [rbx+30h]; unsigned __int16 *
0x180079680  test    rcx, rcx
0x180079683  jz      short loc_18007969B
0x180079685  mov     [rsp+278h+lpBuffer], rcx
0x18007968a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180079691  mov     rcx, rax; this
0x180079694  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180079699  jmp     short loc_1800796BD
0x18007969b  mov     rcx, rax; this
0x18007969e  test    r9, r9
0x1800796a1  jz      short loc_1800796B1
0x1800796a3  lea     r8, aHs; "[%hs]\n"
0x1800796aa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800796af  jmp     short loc_1800796BD
0x1800796b1  lea     r8, asc_18009C978; "\n"
0x1800796b8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800796bd  xor     eax, eax
0x1800796bf  mov     rcx, [rsp+278h+var_38]
0x1800796c7  xor     rcx, rsp; StackCookie
0x1800796ca  call    __security_check_cookie
0x1800796cf  mov     rbx, [rsp+278h+arg_18]
0x1800796d7  add     rsp, 250h
0x1800796de  pop     r15
0x1800796e0  pop     r14
0x1800796e2  pop     rdi
0x1800796e3  pop     rsi
0x1800796e4  pop     rbp
0x1800796e5  retn
```
