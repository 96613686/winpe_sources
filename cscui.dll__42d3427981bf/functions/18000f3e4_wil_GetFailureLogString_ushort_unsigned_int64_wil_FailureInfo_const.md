# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000f3e4`
- end: `0x18000f69a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000e7d4`
- `0x18000fad8`
- `0x18004ba30`

## callees

- `0x18000f3e4`
- `0x18000fdd8`
- `0x18004c636`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f597`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f597`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000f516`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000f516`

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
          v8 = qword_180055348;
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
0x18000f3e4  mov     [rsp+arg_18], rbx
0x18000f3e9  push    rbp
0x18000f3ea  push    rsi
0x18000f3eb  push    rdi
0x18000f3ec  push    r14
0x18000f3ee  push    r15
0x18000f3f0  sub     rsp, 250h
0x18000f3f7  mov     rax, cs:__security_cookie
0x18000f3fe  xor     rax, rsp
0x18000f401  mov     [rsp+278h+var_38], rax
0x18000f409  xor     r15d, r15d
0x18000f40c  mov     rbx, r8
0x18000f40f  mov     rsi, rdx
0x18000f412  mov     r14, rcx
0x18000f415  test    rdx, rdx
0x18000f418  jz      loc_18000F671
0x18000f41e  test    rcx, rcx
0x18000f421  jz      loc_18000F671
0x18000f427  mov     rax, cs:g_pfnResultLoggingCallback
0x18000f42e  mov     [rcx], r15w
0x18000f432  test    rax, rax
0x18000f435  jz      short loc_18000F458
0x18000f437  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000f43e  jz      short loc_18000F458
0x18000f440  mov     r8, rdx
0x18000f443  mov     rdx, rcx
0x18000f446  mov     rcx, rbx
0x18000f449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f44e  cmp     [r14], r15w
0x18000f452  jnz     loc_18000F671
0x18000f458  mov     ecx, [rbx]
0x18000f45a  mov     bpl, 8
0x18000f45d  test    ecx, ecx
0x18000f45f  jz      short loc_18000F4AA
0x18000f461  sub     ecx, 1
0x18000f464  jz      short loc_18000F492
0x18000f466  sub     ecx, 1
0x18000f469  jz      short loc_18000F482
0x18000f46b  cmp     ecx, 1
0x18000f46e  jz      short loc_18000F479
0x18000f470  lea     rdi, qword_180055348
0x18000f477  jmp     short loc_18000F4B1
0x18000f479  lea     rdi, aFailfast; "FailFast"
0x18000f480  jmp     short loc_18000F4B1
0x18000f482  lea     rax, aLoghr; "LogHr"
0x18000f489  lea     rdi, aLognt; "LogNt"
0x18000f490  jmp     short loc_18000F4A0
0x18000f492  lea     rax, aReturnhr; "ReturnHr"
0x18000f499  lea     rdi, aReturnnt; "ReturnNt"
0x18000f4a0  test    [rbx+4], bpl
0x18000f4a4  cmovz   rdi, rax
0x18000f4a8  jmp     short loc_18000F4B1
0x18000f4aa  lea     rdi, aException; "Exception"
0x18000f4b1  xor     edx, edx; Val
0x18000f4b3  lea     rcx, [rsp+278h+Buffer]; void *
0x18000f4b8  mov     r8d, 200h; Size
0x18000f4be  call    memset_0
0x18000f4c3  test    [rbx+4], bpl
0x18000f4c7  jz      short loc_18000F4EC
0x18000f4c9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000f4d0  mov     ebp, [rbx+0Ch]
0x18000f4d3  test    rax, rax
0x18000f4d6  jz      short loc_18000F51C
0x18000f4d8  mov     r8d, 100h
0x18000f4de  lea     rdx, [rsp+278h+Buffer]
0x18000f4e3  mov     ecx, ebp
0x18000f4e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4ea  jmp     short loc_18000F51C
0x18000f4ec  mov     ebp, [rbx+8]
0x18000f4ef  lea     rax, [rsp+278h+Buffer]
0x18000f4f4  mov     [rsp+278h+Arguments], r15; Arguments
0x18000f4f9  mov     r8d, ebp; dwMessageId
0x18000f4fc  mov     [rsp+278h+nSize], 100h; nSize
0x18000f504  mov     r9d, 400h; dwLanguageId
0x18000f50a  xor     edx, edx; lpSource
0x18000f50c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000f511  mov     ecx, 1200h; dwFlags
0x18000f516  call    cs:__imp_FormatMessageW
0x18000f51c  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000f520  lea     rsi, [r14+rsi*2]
0x18000f524  mov     rax, [rbx+88h]
0x18000f52b  mov     rdx, rsi; unsigned __int16 *
0x18000f52e  mov     rcx, [rbx+80h]
0x18000f535  test    r9, r9
0x18000f538  jz      short loc_18000F55C
0x18000f53a  mov     [rsp+278h+Arguments], rax
0x18000f53f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000f546  mov     eax, [rbx+40h]
0x18000f549  mov     qword ptr [rsp+278h+nSize], rcx
0x18000f54e  mov     rcx, r14; this
0x18000f551  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000f555  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f55a  jmp     short loc_18000F573
0x18000f55c  mov     r9, rcx; unsigned __int16 *
0x18000f55f  mov     [rsp+278h+lpBuffer], rax
0x18000f564  mov     rcx, r14; this
0x18000f567  lea     r8, aHsP; "%hs!%p: "
0x18000f56e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f573  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000f57a  mov     r14, rax
0x18000f57d  test    r9, r9
0x18000f580  jz      short loc_18000F597
0x18000f582  lea     r8, aCallerP; "(caller: %p) "
0x18000f589  mov     rdx, rsi; unsigned __int16 *
0x18000f58c  mov     rcx, rax; this
0x18000f58f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f594  mov     r14, rax
0x18000f597  call    cs:__imp_GetCurrentThreadId
0x18000f59d  lea     rcx, [rsp+278h+Buffer]
0x18000f5a2  mov     r9, rdi; unsigned __int16 *
0x18000f5a5  mov     [rsp+278h+var_240], rcx
0x18000f5aa  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000f5b1  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000f5b5  mov     rdx, rsi; unsigned __int16 *
0x18000f5b8  mov     [rsp+278h+nSize], eax
0x18000f5bc  mov     rcx, r14; this
0x18000f5bf  mov     eax, [rbx+44h]
0x18000f5c2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000f5c6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f5cb  cmp     [rbx+18h], r15
0x18000f5cf  jnz     short loc_18000F5E1
0x18000f5d1  cmp     [rbx+48h], r15
0x18000f5d5  jnz     short loc_18000F5E1
0x18000f5d7  cmp     [rbx+30h], r15
0x18000f5db  jz      loc_18000F671
0x18000f5e1  lea     r8, asc_180055438; "    "
0x18000f5e8  mov     rdx, rsi; unsigned __int16 *
0x18000f5eb  mov     rcx, rax; this
0x18000f5ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f5f3  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000f5f7  test    r9, r9
0x18000f5fa  jz      short loc_18000F60E
0x18000f5fc  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000f603  mov     rdx, rsi; unsigned __int16 *
0x18000f606  mov     rcx, rax; this
0x18000f609  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f60e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000f612  test    r9, r9
0x18000f615  jz      short loc_18000F629
0x18000f617  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000f61e  mov     rdx, rsi; unsigned __int16 *
0x18000f621  mov     rcx, rax; this
0x18000f624  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f629  mov     rcx, [rbx+28h]
0x18000f62d  mov     rdx, rsi; unsigned __int16 *
0x18000f630  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000f634  test    rcx, rcx
0x18000f637  jz      short loc_18000F64F
0x18000f639  mov     [rsp+278h+lpBuffer], rcx
0x18000f63e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000f645  mov     rcx, rax; this
0x18000f648  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f64d  jmp     short loc_18000F671
0x18000f64f  mov     rcx, rax; this
0x18000f652  test    r9, r9
0x18000f655  jz      short loc_18000F665
0x18000f657  lea     r8, aHs; "[%hs]\n"
0x18000f65e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f663  jmp     short loc_18000F671
0x18000f665  lea     r8, asc_1800554B0; "\n"
0x18000f66c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f671  xor     eax, eax
0x18000f673  mov     rcx, [rsp+278h+var_38]
0x18000f67b  xor     rcx, rsp; StackCookie
0x18000f67e  call    __security_check_cookie
0x18000f683  mov     rbx, [rsp+278h+arg_18]
0x18000f68b  add     rsp, 250h
0x18000f692  pop     r15
0x18000f694  pop     r14
0x18000f696  pop     rdi
0x18000f697  pop     rsi
0x18000f698  pop     rbp
0x18000f699  retn
```
