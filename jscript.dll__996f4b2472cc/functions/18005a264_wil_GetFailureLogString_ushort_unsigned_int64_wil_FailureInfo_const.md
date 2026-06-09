# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18005a264`
- end: `0x18005a527`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800596fc`
- `0x18005a884`

## callees

- `0x18005a264`
- `0x18005ab98`
- `0x1800966aa`
- `0x1800966e0`
- `0x180098010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18005a41d`
- `KERNEL32!GetCurrentThreadId` at `0x18005a41d`
- `KERNEL32!FormatMessageW` at `0x18005a396`
- `KERNEL32!FormatMessageW` at `0x18005a396`

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
          v8 = (const char *)&qword_1800A4330;
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
0x18005a264  mov     [rsp+arg_18], rbx
0x18005a269  push    rbp
0x18005a26a  push    rsi
0x18005a26b  push    rdi
0x18005a26c  push    r14
0x18005a26e  push    r15
0x18005a270  sub     rsp, 250h
0x18005a277  mov     rax, cs:__security_cookie
0x18005a27e  xor     rax, rsp
0x18005a281  mov     [rsp+278h+var_38], rax
0x18005a289  xor     r15d, r15d
0x18005a28c  mov     rbx, r8
0x18005a28f  mov     rsi, rdx
0x18005a292  mov     r14, rcx
0x18005a295  test    rdx, rdx
0x18005a298  jz      loc_18005A4FD
0x18005a29e  test    rcx, rcx
0x18005a2a1  jz      loc_18005A4FD
0x18005a2a7  mov     rax, cs:g_pfnResultLoggingCallback
0x18005a2ae  mov     [rcx], r15w
0x18005a2b2  test    rax, rax
0x18005a2b5  jz      short loc_18005A2D8
0x18005a2b7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18005a2be  jz      short loc_18005A2D8
0x18005a2c0  mov     r8, rdx
0x18005a2c3  mov     rdx, rcx
0x18005a2c6  mov     rcx, rbx
0x18005a2c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a2ce  cmp     [r14], r15w
0x18005a2d2  jnz     loc_18005A4FD
0x18005a2d8  mov     ecx, [rbx]
0x18005a2da  mov     bpl, 8
0x18005a2dd  test    ecx, ecx
0x18005a2df  jz      short loc_18005A32A
0x18005a2e1  sub     ecx, 1
0x18005a2e4  jz      short loc_18005A312
0x18005a2e6  sub     ecx, 1
0x18005a2e9  jz      short loc_18005A302
0x18005a2eb  cmp     ecx, 1
0x18005a2ee  jz      short loc_18005A2F9
0x18005a2f0  lea     rdi, qword_1800A4330
0x18005a2f7  jmp     short loc_18005A331
0x18005a2f9  lea     rdi, aFailfast; "FailFast"
0x18005a300  jmp     short loc_18005A331
0x18005a302  lea     rax, aLoghr; "LogHr"
0x18005a309  lea     rdi, aLognt; "LogNt"
0x18005a310  jmp     short loc_18005A320
0x18005a312  lea     rax, aReturnhr; "ReturnHr"
0x18005a319  lea     rdi, aReturnnt; "ReturnNt"
0x18005a320  test    [rbx+4], bpl
0x18005a324  cmovz   rdi, rax
0x18005a328  jmp     short loc_18005A331
0x18005a32a  lea     rdi, aException; "Exception"
0x18005a331  xor     edx, edx; Val
0x18005a333  lea     rcx, [rsp+278h+Buffer]; void *
0x18005a338  mov     r8d, 200h; Size
0x18005a33e  call    memset_0
0x18005a343  test    [rbx+4], bpl
0x18005a347  jz      short loc_18005A36C
0x18005a349  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18005a350  mov     ebp, [rbx+0Ch]
0x18005a353  test    rax, rax
0x18005a356  jz      short loc_18005A3A2
0x18005a358  mov     r8d, 100h
0x18005a35e  lea     rdx, [rsp+278h+Buffer]
0x18005a363  mov     ecx, ebp
0x18005a365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a36a  jmp     short loc_18005A3A2
0x18005a36c  mov     ebp, [rbx+8]
0x18005a36f  lea     rax, [rsp+278h+Buffer]
0x18005a374  mov     [rsp+278h+Arguments], r15; Arguments
0x18005a379  mov     r8d, ebp; dwMessageId
0x18005a37c  mov     [rsp+278h+nSize], 100h; nSize
0x18005a384  mov     r9d, 400h; dwLanguageId
0x18005a38a  xor     edx, edx; lpSource
0x18005a38c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18005a391  mov     ecx, 1200h; dwFlags
0x18005a396  call    cs:__imp_FormatMessageW
0x18005a39d  nop     dword ptr [rax+rax+00h]
0x18005a3a2  mov     r9, [rbx+38h]; unsigned __int16 *
0x18005a3a6  lea     rsi, [r14+rsi*2]
0x18005a3aa  mov     rax, [rbx+88h]
0x18005a3b1  mov     rdx, rsi; unsigned __int16 *
0x18005a3b4  mov     rcx, [rbx+80h]
0x18005a3bb  test    r9, r9
0x18005a3be  jz      short loc_18005A3E2
0x18005a3c0  mov     [rsp+278h+Arguments], rax
0x18005a3c5  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18005a3cc  mov     eax, [rbx+40h]
0x18005a3cf  mov     qword ptr [rsp+278h+nSize], rcx
0x18005a3d4  mov     rcx, r14; this
0x18005a3d7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18005a3db  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005a3e0  jmp     short loc_18005A3F9
0x18005a3e2  mov     r9, rcx; unsigned __int16 *
0x18005a3e5  mov     [rsp+278h+lpBuffer], rax
0x18005a3ea  mov     rcx, r14; this
0x18005a3ed  lea     r8, aHsP; "%hs!%p: "
0x18005a3f4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005a3f9  mov     r9, [rbx+90h]; unsigned __int16 *
0x18005a400  mov     r14, rax
0x18005a403  test    r9, r9
0x18005a406  jz      short loc_18005A41D
0x18005a408  lea     r8, aCallerP; "(caller: %p) "
0x18005a40f  mov     rdx, rsi; unsigned __int16 *
0x18005a412  mov     rcx, rax; this
0x18005a415  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005a41a  mov     r14, rax
0x18005a41d  call    cs:__imp_GetCurrentThreadId
0x18005a424  nop     dword ptr [rax+rax+00h]
0x18005a429  lea     rcx, [rsp+278h+Buffer]
0x18005a42e  mov     r9, rdi; unsigned __int16 *
0x18005a431  mov     [rsp+278h+var_240], rcx
0x18005a436  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18005a43d  mov     dword ptr [rsp+278h+Arguments], ebp
0x18005a441  mov     rdx, rsi; unsigned __int16 *
0x18005a444  mov     [rsp+278h+nSize], eax
0x18005a448  mov     rcx, r14; this
0x18005a44b  mov     eax, [rbx+44h]
0x18005a44e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18005a452  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005a457  cmp     [rbx+18h], r15
0x18005a45b  jnz     short loc_18005A46D
0x18005a45d  cmp     [rbx+48h], r15
0x18005a461  jnz     short loc_18005A46D
0x18005a463  cmp     [rbx+30h], r15
0x18005a467  jz      loc_18005A4FD
0x18005a46d  lea     r8, asc_1800A4980; "    "
0x18005a474  mov     rdx, rsi; unsigned __int16 *
0x18005a477  mov     rcx, rax; this
0x18005a47a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005a47f  mov     r9, [rbx+18h]; unsigned __int16 *
0x18005a483  test    r9, r9
0x18005a486  jz      short loc_18005A49A
0x18005a488  lea     r8, aMsgWs; "Msg:[%ws] "
0x18005a48f  mov     rdx, rsi; unsigned __int16 *
0x18005a492  mov     rcx, rax; this
0x18005a495  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005a49a  mov     r9, [rbx+48h]; unsigned __int16 *
0x18005a49e  test    r9, r9
0x18005a4a1  jz      short loc_18005A4B5
0x18005a4a3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18005a4aa  mov     rdx, rsi; unsigned __int16 *
0x18005a4ad  mov     rcx, rax; this
0x18005a4b0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005a4b5  mov     rcx, [rbx+28h]
0x18005a4b9  mov     rdx, rsi; unsigned __int16 *
0x18005a4bc  mov     r9, [rbx+30h]; unsigned __int16 *
0x18005a4c0  test    rcx, rcx
0x18005a4c3  jz      short loc_18005A4DB
0x18005a4c5  mov     [rsp+278h+lpBuffer], rcx
0x18005a4ca  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18005a4d1  mov     rcx, rax; this
0x18005a4d4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005a4d9  jmp     short loc_18005A4FD
0x18005a4db  mov     rcx, rax; this
0x18005a4de  test    r9, r9
0x18005a4e1  jz      short loc_18005A4F1
0x18005a4e3  lea     r8, aHs; "[%hs]\n"
0x18005a4ea  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005a4ef  jmp     short loc_18005A4FD
0x18005a4f1  lea     r8, asc_1800A49F8; "\n"
0x18005a4f8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005a4fd  xor     eax, eax
0x18005a4ff  mov     rcx, [rsp+278h+var_38]
0x18005a507  xor     rcx, rsp; StackCookie
0x18005a50a  call    __security_check_cookie
0x18005a50f  mov     rbx, [rsp+278h+arg_18]
0x18005a517  add     rsp, 250h
0x18005a51e  pop     r15
0x18005a520  pop     r14
0x18005a522  pop     rdi
0x18005a523  pop     rsi
0x18005a524  pop     rbp
0x18005a525  retn
```
