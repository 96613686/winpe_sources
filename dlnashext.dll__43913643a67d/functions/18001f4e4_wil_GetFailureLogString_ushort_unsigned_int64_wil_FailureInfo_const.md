# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18001f4e4`
- end: `0x18001f79a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800206d0`
- `0x180030f74`
- `0x180031df8`

## callees

- `0x180011930`
- `0x1800125c4`
- `0x18001f4e4`
- `0x18001f8fc`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f697`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f697`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001f616`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001f616`

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
      g_pfnResultLoggingCallback(a3, this, a2, a4);
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
          v7 = (const char *)&word_18003C16A;
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
0x18001f4e4  mov     [rsp+arg_18], rbx
0x18001f4e9  push    rbp
0x18001f4ea  push    rsi
0x18001f4eb  push    rdi
0x18001f4ec  push    r14
0x18001f4ee  push    r15
0x18001f4f0  sub     rsp, 250h
0x18001f4f7  mov     rax, cs:__security_cookie
0x18001f4fe  xor     rax, rsp
0x18001f501  mov     [rsp+278h+var_38], rax
0x18001f509  mov     rbx, r8
0x18001f50c  mov     rsi, rdx
0x18001f50f  mov     r14, rcx
0x18001f512  xor     r15d, r15d
0x18001f515  test    rdx, rdx
0x18001f518  jz      loc_18001F771
0x18001f51e  test    rcx, rcx
0x18001f521  jz      loc_18001F771
0x18001f527  mov     [rcx], r15w
0x18001f52b  mov     rax, cs:g_pfnResultLoggingCallback
0x18001f532  test    rax, rax
0x18001f535  jz      short loc_18001F558
0x18001f537  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001f53e  jz      short loc_18001F558
0x18001f540  mov     r8, rdx
0x18001f543  mov     rdx, rcx
0x18001f546  mov     rcx, rbx
0x18001f549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f54e  cmp     [r14], r15w
0x18001f552  jnz     loc_18001F771
0x18001f558  mov     ecx, [rbx]
0x18001f55a  mov     bpl, 8
0x18001f55d  test    ecx, ecx
0x18001f55f  jz      short loc_18001F5AA
0x18001f561  sub     ecx, 1
0x18001f564  jz      short loc_18001F592
0x18001f566  sub     ecx, 1
0x18001f569  jz      short loc_18001F582
0x18001f56b  cmp     ecx, 1
0x18001f56e  jz      short loc_18001F579
0x18001f570  lea     rdi, word_18003C16A
0x18001f577  jmp     short loc_18001F5B1
0x18001f579  lea     rdi, aFailfast; "FailFast"
0x18001f580  jmp     short loc_18001F5B1
0x18001f582  lea     rax, aLoghr; "LogHr"
0x18001f589  lea     rdi, aLognt; "LogNt"
0x18001f590  jmp     short loc_18001F5A0
0x18001f592  lea     rax, aReturnhr; "ReturnHr"
0x18001f599  lea     rdi, aReturnnt; "ReturnNt"
0x18001f5a0  test    [rbx+4], bpl
0x18001f5a4  cmovz   rdi, rax
0x18001f5a8  jmp     short loc_18001F5B1
0x18001f5aa  lea     rdi, aException; "Exception"
0x18001f5b1  xor     edx, edx; Val
0x18001f5b3  mov     r8d, 200h; Size
0x18001f5b9  lea     rcx, [rsp+278h+Buffer]; void *
0x18001f5be  call    memset_0
0x18001f5c3  test    [rbx+4], bpl
0x18001f5c7  jz      short loc_18001F5EC
0x18001f5c9  mov     ebp, [rbx+0Ch]
0x18001f5cc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18001f5d3  test    rax, rax
0x18001f5d6  jz      short loc_18001F61C
0x18001f5d8  mov     r8d, 100h
0x18001f5de  lea     rdx, [rsp+278h+Buffer]
0x18001f5e3  mov     ecx, ebp
0x18001f5e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5ea  jmp     short loc_18001F61C
0x18001f5ec  mov     ebp, [rbx+8]
0x18001f5ef  mov     [rsp+278h+Arguments], r15; Arguments
0x18001f5f4  mov     [rsp+278h+nSize], 100h; nSize
0x18001f5fc  lea     rax, [rsp+278h+Buffer]
0x18001f601  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18001f606  mov     r9d, 400h; dwLanguageId
0x18001f60c  mov     r8d, ebp; dwMessageId
0x18001f60f  xor     edx, edx; lpSource
0x18001f611  mov     ecx, 1200h; dwFlags
0x18001f616  call    cs:__imp_FormatMessageW
0x18001f61c  lea     rsi, [r14+rsi*2]
0x18001f620  mov     r9, [rbx+38h]; unsigned __int16 *
0x18001f624  mov     rax, [rbx+88h]
0x18001f62b  mov     rcx, [rbx+80h]
0x18001f632  mov     rdx, rsi; unsigned __int16 *
0x18001f635  test    r9, r9
0x18001f638  jz      short loc_18001F65C
0x18001f63a  mov     [rsp+278h+Arguments], rax
0x18001f63f  mov     qword ptr [rsp+278h+nSize], rcx
0x18001f644  mov     eax, [rbx+40h]
0x18001f647  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001f64b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18001f652  mov     rcx, r14; this
0x18001f655  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001f65a  jmp     short loc_18001F673
0x18001f65c  mov     [rsp+278h+lpBuffer], rax
0x18001f661  mov     r9, rcx; unsigned __int16 *
0x18001f664  lea     r8, aHsP; "%hs!%p: "
0x18001f66b  mov     rcx, r14; this
0x18001f66e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001f673  mov     r14, rax
0x18001f676  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001f67d  test    r9, r9
0x18001f680  jz      short loc_18001F697
0x18001f682  lea     r8, aCallerP; "(caller: %p) "
0x18001f689  mov     rdx, rsi; unsigned __int16 *
0x18001f68c  mov     rcx, rax; this
0x18001f68f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001f694  mov     r14, rax
0x18001f697  call    cs:__imp_GetCurrentThreadId
0x18001f69d  lea     rcx, [rsp+278h+Buffer]
0x18001f6a2  mov     [rsp+278h+var_240], rcx
0x18001f6a7  mov     dword ptr [rsp+278h+Arguments], ebp
0x18001f6ab  mov     [rsp+278h+nSize], eax
0x18001f6af  mov     eax, [rbx+44h]
0x18001f6b2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001f6b6  mov     r9, rdi; unsigned __int16 *
0x18001f6b9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18001f6c0  mov     rdx, rsi; unsigned __int16 *
0x18001f6c3  mov     rcx, r14; this
0x18001f6c6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001f6cb  cmp     [rbx+18h], r15
0x18001f6cf  jnz     short loc_18001F6E1
0x18001f6d1  cmp     [rbx+48h], r15
0x18001f6d5  jnz     short loc_18001F6E1
0x18001f6d7  cmp     [rbx+30h], r15
0x18001f6db  jz      loc_18001F771
0x18001f6e1  lea     r8, asc_18003C258; "    "
0x18001f6e8  mov     rdx, rsi; unsigned __int16 *
0x18001f6eb  mov     rcx, rax; this
0x18001f6ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001f6f3  mov     r9, [rbx+18h]; unsigned __int16 *
0x18001f6f7  test    r9, r9
0x18001f6fa  jz      short loc_18001F70E
0x18001f6fc  lea     r8, aMsgWs; "Msg:[%ws] "
0x18001f703  mov     rdx, rsi; unsigned __int16 *
0x18001f706  mov     rcx, rax; this
0x18001f709  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001f70e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18001f712  test    r9, r9
0x18001f715  jz      short loc_18001F729
0x18001f717  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001f71e  mov     rdx, rsi; unsigned __int16 *
0x18001f721  mov     rcx, rax; this
0x18001f724  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001f729  mov     rcx, [rbx+28h]
0x18001f72d  mov     r9, [rbx+30h]; unsigned __int16 *
0x18001f731  mov     rdx, rsi; unsigned __int16 *
0x18001f734  test    rcx, rcx
0x18001f737  jz      short loc_18001F74F
0x18001f739  mov     [rsp+278h+lpBuffer], rcx
0x18001f73e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18001f745  mov     rcx, rax; this
0x18001f748  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001f74d  jmp     short loc_18001F771
0x18001f74f  mov     rcx, rax; this
0x18001f752  test    r9, r9
0x18001f755  jz      short loc_18001F765
0x18001f757  lea     r8, aHs; "[%hs]\n"
0x18001f75e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001f763  jmp     short loc_18001F771
0x18001f765  lea     r8, asc_18003C2D0; "\n"
0x18001f76c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001f771  xor     eax, eax
0x18001f773  mov     rcx, [rsp+278h+var_38]
0x18001f77b  xor     rcx, rsp; StackCookie
0x18001f77e  call    __security_check_cookie
0x18001f783  mov     rbx, [rsp+278h+arg_18]
0x18001f78b  add     rsp, 250h
0x18001f792  pop     r15
0x18001f794  pop     r14
0x18001f796  pop     rdi
0x18001f797  pop     rsi
0x18001f798  pop     rbp
0x18001f799  retn
```
