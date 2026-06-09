# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x14000b49c`
- end: `0x14000b752`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x14000a734`
- `0x14000a99c`
- `0x14000bb90`

## callees

- `0x14000b49c`
- `0x14000be90`
- `0x14001619a`
- `0x1400161d0`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000b64f`
- `KERNEL32!GetCurrentThreadId` at `0x14000b64f`
- `KERNEL32!FormatMessageW` at `0x14000b5ce`
- `KERNEL32!FormatMessageW` at `0x14000b5ce`

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
          v8 = (const char *)&qword_140019E70;
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
0x14000b49c  mov     [rsp+arg_18], rbx
0x14000b4a1  push    rbp
0x14000b4a2  push    rsi
0x14000b4a3  push    rdi
0x14000b4a4  push    r14
0x14000b4a6  push    r15
0x14000b4a8  sub     rsp, 250h
0x14000b4af  mov     rax, cs:__security_cookie
0x14000b4b6  xor     rax, rsp
0x14000b4b9  mov     [rsp+278h+var_38], rax
0x14000b4c1  xor     r15d, r15d
0x14000b4c4  mov     rbx, r8
0x14000b4c7  mov     rsi, rdx
0x14000b4ca  mov     r14, rcx
0x14000b4cd  test    rdx, rdx
0x14000b4d0  jz      loc_14000B729
0x14000b4d6  test    rcx, rcx
0x14000b4d9  jz      loc_14000B729
0x14000b4df  mov     rax, cs:g_pfnResultLoggingCallback
0x14000b4e6  mov     [rcx], r15w
0x14000b4ea  test    rax, rax
0x14000b4ed  jz      short loc_14000B510
0x14000b4ef  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000b4f6  jz      short loc_14000B510
0x14000b4f8  mov     r8, rdx
0x14000b4fb  mov     rdx, rcx
0x14000b4fe  mov     rcx, rbx
0x14000b501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b506  cmp     [r14], r15w
0x14000b50a  jnz     loc_14000B729
0x14000b510  mov     ecx, [rbx]
0x14000b512  mov     bpl, 8
0x14000b515  test    ecx, ecx
0x14000b517  jz      short loc_14000B562
0x14000b519  sub     ecx, 1
0x14000b51c  jz      short loc_14000B54A
0x14000b51e  sub     ecx, 1
0x14000b521  jz      short loc_14000B53A
0x14000b523  cmp     ecx, 1
0x14000b526  jz      short loc_14000B531
0x14000b528  lea     rdi, qword_140019E70
0x14000b52f  jmp     short loc_14000B569
0x14000b531  lea     rdi, aFailfast; "FailFast"
0x14000b538  jmp     short loc_14000B569
0x14000b53a  lea     rax, aLoghr; "LogHr"
0x14000b541  lea     rdi, aLognt; "LogNt"
0x14000b548  jmp     short loc_14000B558
0x14000b54a  lea     rax, aReturnhr; "ReturnHr"
0x14000b551  lea     rdi, aReturnnt; "ReturnNt"
0x14000b558  test    [rbx+4], bpl
0x14000b55c  cmovz   rdi, rax
0x14000b560  jmp     short loc_14000B569
0x14000b562  lea     rdi, aException; "Exception"
0x14000b569  xor     edx, edx; Val
0x14000b56b  lea     rcx, [rsp+278h+Buffer]; void *
0x14000b570  mov     r8d, 200h; Size
0x14000b576  call    memset_0
0x14000b57b  test    [rbx+4], bpl
0x14000b57f  jz      short loc_14000B5A4
0x14000b581  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x14000b588  mov     ebp, [rbx+0Ch]
0x14000b58b  test    rax, rax
0x14000b58e  jz      short loc_14000B5D4
0x14000b590  mov     r8d, 100h
0x14000b596  lea     rdx, [rsp+278h+Buffer]
0x14000b59b  mov     ecx, ebp
0x14000b59d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b5a2  jmp     short loc_14000B5D4
0x14000b5a4  mov     ebp, [rbx+8]
0x14000b5a7  lea     rax, [rsp+278h+Buffer]
0x14000b5ac  mov     [rsp+278h+Arguments], r15; Arguments
0x14000b5b1  mov     r8d, ebp; dwMessageId
0x14000b5b4  mov     [rsp+278h+nSize], 100h; nSize
0x14000b5bc  mov     r9d, 400h; dwLanguageId
0x14000b5c2  xor     edx, edx; lpSource
0x14000b5c4  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x14000b5c9  mov     ecx, 1200h; dwFlags
0x14000b5ce  call    cs:__imp_FormatMessageW
0x14000b5d4  mov     r9, [rbx+38h]; unsigned __int16 *
0x14000b5d8  lea     rsi, [r14+rsi*2]
0x14000b5dc  mov     rax, [rbx+88h]
0x14000b5e3  mov     rdx, rsi; unsigned __int16 *
0x14000b5e6  mov     rcx, [rbx+80h]
0x14000b5ed  test    r9, r9
0x14000b5f0  jz      short loc_14000B614
0x14000b5f2  mov     [rsp+278h+Arguments], rax
0x14000b5f7  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x14000b5fe  mov     eax, [rbx+40h]
0x14000b601  mov     qword ptr [rsp+278h+nSize], rcx
0x14000b606  mov     rcx, r14; this
0x14000b609  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000b60d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b612  jmp     short loc_14000B62B
0x14000b614  mov     r9, rcx; unsigned __int16 *
0x14000b617  mov     [rsp+278h+lpBuffer], rax
0x14000b61c  mov     rcx, r14; this
0x14000b61f  lea     r8, aHsP; "%hs!%p: "
0x14000b626  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b62b  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000b632  mov     r14, rax
0x14000b635  test    r9, r9
0x14000b638  jz      short loc_14000B64F
0x14000b63a  lea     r8, aCallerP; "(caller: %p) "
0x14000b641  mov     rdx, rsi; unsigned __int16 *
0x14000b644  mov     rcx, rax; this
0x14000b647  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b64c  mov     r14, rax
0x14000b64f  call    cs:__imp_GetCurrentThreadId
0x14000b655  lea     rcx, [rsp+278h+Buffer]
0x14000b65a  mov     r9, rdi; unsigned __int16 *
0x14000b65d  mov     [rsp+278h+var_240], rcx
0x14000b662  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x14000b669  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000b66d  mov     rdx, rsi; unsigned __int16 *
0x14000b670  mov     [rsp+278h+nSize], eax
0x14000b674  mov     rcx, r14; this
0x14000b677  mov     eax, [rbx+44h]
0x14000b67a  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000b67e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b683  cmp     [rbx+18h], r15
0x14000b687  jnz     short loc_14000B699
0x14000b689  cmp     [rbx+48h], r15
0x14000b68d  jnz     short loc_14000B699
0x14000b68f  cmp     [rbx+30h], r15
0x14000b693  jz      loc_14000B729
0x14000b699  lea     r8, asc_140019F60; "    "
0x14000b6a0  mov     rdx, rsi; unsigned __int16 *
0x14000b6a3  mov     rcx, rax; this
0x14000b6a6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b6ab  mov     r9, [rbx+18h]; unsigned __int16 *
0x14000b6af  test    r9, r9
0x14000b6b2  jz      short loc_14000B6C6
0x14000b6b4  lea     r8, aMsgWs; "Msg:[%ws] "
0x14000b6bb  mov     rdx, rsi; unsigned __int16 *
0x14000b6be  mov     rcx, rax; this
0x14000b6c1  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b6c6  mov     r9, [rbx+48h]; unsigned __int16 *
0x14000b6ca  test    r9, r9
0x14000b6cd  jz      short loc_14000B6E1
0x14000b6cf  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000b6d6  mov     rdx, rsi; unsigned __int16 *
0x14000b6d9  mov     rcx, rax; this
0x14000b6dc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b6e1  mov     rcx, [rbx+28h]
0x14000b6e5  mov     rdx, rsi; unsigned __int16 *
0x14000b6e8  mov     r9, [rbx+30h]; unsigned __int16 *
0x14000b6ec  test    rcx, rcx
0x14000b6ef  jz      short loc_14000B707
0x14000b6f1  mov     [rsp+278h+lpBuffer], rcx
0x14000b6f6  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x14000b6fd  mov     rcx, rax; this
0x14000b700  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b705  jmp     short loc_14000B729
0x14000b707  mov     rcx, rax; this
0x14000b70a  test    r9, r9
0x14000b70d  jz      short loc_14000B71D
0x14000b70f  lea     r8, aHs; "[%hs]\n"
0x14000b716  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b71b  jmp     short loc_14000B729
0x14000b71d  lea     r8, asc_140019FD8; "\n"
0x14000b724  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b729  xor     eax, eax
0x14000b72b  mov     rcx, [rsp+278h+var_38]
0x14000b733  xor     rcx, rsp; StackCookie
0x14000b736  call    __security_check_cookie
0x14000b73b  mov     rbx, [rsp+278h+arg_18]
0x14000b743  add     rsp, 250h
0x14000b74a  pop     r15
0x14000b74c  pop     r14
0x14000b74e  pop     rdi
0x14000b74f  pop     rsi
0x14000b750  pop     rbp
0x14000b751  retn
```
