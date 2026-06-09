# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18007d3dc`
- end: `0x18007d692`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18005e854`
- `0x18007dc44`
- `0x18007eec0`

## callees

- `0x180075fa0`
- `0x180076f20`
- `0x18007d3dc`
- `0x18007d928`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007d58f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007d58f`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18007d50e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18007d50e`

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
          v7 = dword_1800DA58C;
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
0x18007d3dc  mov     [rsp+arg_18], rbx
0x18007d3e1  push    rbp
0x18007d3e2  push    rsi
0x18007d3e3  push    rdi
0x18007d3e4  push    r14
0x18007d3e6  push    r15
0x18007d3e8  sub     rsp, 250h
0x18007d3ef  mov     rax, cs:__security_cookie
0x18007d3f6  xor     rax, rsp
0x18007d3f9  mov     [rsp+278h+var_38], rax
0x18007d401  mov     rbx, r8
0x18007d404  mov     rsi, rdx
0x18007d407  mov     r14, rcx
0x18007d40a  xor     r15d, r15d
0x18007d40d  test    rdx, rdx
0x18007d410  jz      loc_18007D669
0x18007d416  test    rcx, rcx
0x18007d419  jz      loc_18007D669
0x18007d41f  mov     [rcx], r15w
0x18007d423  mov     rax, cs:g_pfnResultLoggingCallback
0x18007d42a  test    rax, rax
0x18007d42d  jz      short loc_18007D450
0x18007d42f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18007d436  jz      short loc_18007D450
0x18007d438  mov     r8, rdx
0x18007d43b  mov     rdx, rcx
0x18007d43e  mov     rcx, rbx
0x18007d441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d446  cmp     [r14], r15w
0x18007d44a  jnz     loc_18007D669
0x18007d450  mov     ecx, [rbx]
0x18007d452  mov     bpl, 8
0x18007d455  test    ecx, ecx
0x18007d457  jz      short loc_18007D4A2
0x18007d459  sub     ecx, 1
0x18007d45c  jz      short loc_18007D48A
0x18007d45e  sub     ecx, 1
0x18007d461  jz      short loc_18007D47A
0x18007d463  cmp     ecx, 1
0x18007d466  jz      short loc_18007D471
0x18007d468  lea     rdi, dword_1800DA58C
0x18007d46f  jmp     short loc_18007D4A9
0x18007d471  lea     rdi, aFailfast; "FailFast"
0x18007d478  jmp     short loc_18007D4A9
0x18007d47a  lea     rax, aLoghr; "LogHr"
0x18007d481  lea     rdi, aLognt; "LogNt"
0x18007d488  jmp     short loc_18007D498
0x18007d48a  lea     rax, aReturnhr; "ReturnHr"
0x18007d491  lea     rdi, aReturnnt; "ReturnNt"
0x18007d498  test    [rbx+4], bpl
0x18007d49c  cmovz   rdi, rax
0x18007d4a0  jmp     short loc_18007D4A9
0x18007d4a2  lea     rdi, aException; "Exception"
0x18007d4a9  xor     edx, edx; Val
0x18007d4ab  mov     r8d, 200h; Size
0x18007d4b1  lea     rcx, [rsp+278h+Buffer]; void *
0x18007d4b6  call    memset_0
0x18007d4bb  test    [rbx+4], bpl
0x18007d4bf  jz      short loc_18007D4E4
0x18007d4c1  mov     ebp, [rbx+0Ch]
0x18007d4c4  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18007d4cb  test    rax, rax
0x18007d4ce  jz      short loc_18007D514
0x18007d4d0  mov     r8d, 100h
0x18007d4d6  lea     rdx, [rsp+278h+Buffer]
0x18007d4db  mov     ecx, ebp
0x18007d4dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d4e2  jmp     short loc_18007D514
0x18007d4e4  mov     ebp, [rbx+8]
0x18007d4e7  mov     [rsp+278h+Arguments], r15; Arguments
0x18007d4ec  mov     [rsp+278h+nSize], 100h; nSize
0x18007d4f4  lea     rax, [rsp+278h+Buffer]
0x18007d4f9  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18007d4fe  mov     r9d, 400h; dwLanguageId
0x18007d504  mov     r8d, ebp; dwMessageId
0x18007d507  xor     edx, edx; lpSource
0x18007d509  mov     ecx, 1200h; dwFlags
0x18007d50e  call    cs:__imp_FormatMessageW
0x18007d514  lea     rsi, [r14+rsi*2]
0x18007d518  mov     r9, [rbx+38h]; unsigned __int16 *
0x18007d51c  mov     rax, [rbx+88h]
0x18007d523  mov     rcx, [rbx+80h]
0x18007d52a  mov     rdx, rsi; unsigned __int16 *
0x18007d52d  test    r9, r9
0x18007d530  jz      short loc_18007D554
0x18007d532  mov     [rsp+278h+Arguments], rax
0x18007d537  mov     qword ptr [rsp+278h+nSize], rcx
0x18007d53c  mov     eax, [rbx+40h]
0x18007d53f  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18007d543  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18007d54a  mov     rcx, r14; this
0x18007d54d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18007d552  jmp     short loc_18007D56B
0x18007d554  mov     [rsp+278h+lpBuffer], rax
0x18007d559  mov     r9, rcx; unsigned __int16 *
0x18007d55c  lea     r8, aHsP; "%hs!%p: "
0x18007d563  mov     rcx, r14; this
0x18007d566  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18007d56b  mov     r14, rax
0x18007d56e  mov     r9, [rbx+90h]; unsigned __int16 *
0x18007d575  test    r9, r9
0x18007d578  jz      short loc_18007D58F
0x18007d57a  lea     r8, aCallerP; "(caller: %p) "
0x18007d581  mov     rdx, rsi; unsigned __int16 *
0x18007d584  mov     rcx, rax; this
0x18007d587  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18007d58c  mov     r14, rax
0x18007d58f  call    cs:__imp_GetCurrentThreadId
0x18007d595  lea     rcx, [rsp+278h+Buffer]
0x18007d59a  mov     [rsp+278h+var_240], rcx
0x18007d59f  mov     dword ptr [rsp+278h+Arguments], ebp
0x18007d5a3  mov     [rsp+278h+nSize], eax
0x18007d5a7  mov     eax, [rbx+44h]
0x18007d5aa  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18007d5ae  mov     r9, rdi; unsigned __int16 *
0x18007d5b1  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18007d5b8  mov     rdx, rsi; unsigned __int16 *
0x18007d5bb  mov     rcx, r14; this
0x18007d5be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18007d5c3  cmp     [rbx+18h], r15
0x18007d5c7  jnz     short loc_18007D5D9
0x18007d5c9  cmp     [rbx+48h], r15
0x18007d5cd  jnz     short loc_18007D5D9
0x18007d5cf  cmp     [rbx+30h], r15
0x18007d5d3  jz      loc_18007D669
0x18007d5d9  lea     r8, asc_1800DC018; "    "
0x18007d5e0  mov     rdx, rsi; unsigned __int16 *
0x18007d5e3  mov     rcx, rax; this
0x18007d5e6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18007d5eb  mov     r9, [rbx+18h]; unsigned __int16 *
0x18007d5ef  test    r9, r9
0x18007d5f2  jz      short loc_18007D606
0x18007d5f4  lea     r8, aMsgWs; "Msg:[%ws] "
0x18007d5fb  mov     rdx, rsi; unsigned __int16 *
0x18007d5fe  mov     rcx, rax; this
0x18007d601  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18007d606  mov     r9, [rbx+48h]; unsigned __int16 *
0x18007d60a  test    r9, r9
0x18007d60d  jz      short loc_18007D621
0x18007d60f  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18007d616  mov     rdx, rsi; unsigned __int16 *
0x18007d619  mov     rcx, rax; this
0x18007d61c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18007d621  mov     rcx, [rbx+28h]
0x18007d625  mov     r9, [rbx+30h]; unsigned __int16 *
0x18007d629  mov     rdx, rsi; unsigned __int16 *
0x18007d62c  test    rcx, rcx
0x18007d62f  jz      short loc_18007D647
0x18007d631  mov     [rsp+278h+lpBuffer], rcx
0x18007d636  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18007d63d  mov     rcx, rax; this
0x18007d640  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18007d645  jmp     short loc_18007D669
0x18007d647  mov     rcx, rax; this
0x18007d64a  test    r9, r9
0x18007d64d  jz      short loc_18007D65D
0x18007d64f  lea     r8, aHs; "[%hs]\n"
0x18007d656  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18007d65b  jmp     short loc_18007D669
0x18007d65d  lea     r8, asc_1800DC090; "\n"
0x18007d664  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18007d669  xor     eax, eax
0x18007d66b  mov     rcx, [rsp+278h+var_38]
0x18007d673  xor     rcx, rsp; StackCookie
0x18007d676  call    __security_check_cookie
0x18007d67b  mov     rbx, [rsp+278h+arg_18]
0x18007d683  add     rsp, 250h
0x18007d68a  pop     r15
0x18007d68c  pop     r14
0x18007d68e  pop     rdi
0x18007d68f  pop     rsi
0x18007d690  pop     rbp
0x18007d691  retn
```
