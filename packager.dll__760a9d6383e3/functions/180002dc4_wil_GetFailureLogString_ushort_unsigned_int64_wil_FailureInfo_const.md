# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180002dc4`
- end: `0x18000307a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180001d50`
- `0x180001fc0`
- `0x180003720`

## callees

- `0x180002dc4`
- `0x180003a20`
- `0x18000cbbe`
- `0x18000cbf0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002f77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002f77`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180002ef6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180002ef6`

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
          v8 = (const char *)&qword_180010080;
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
0x180002dc4  mov     [rsp+arg_18], rbx
0x180002dc9  push    rbp
0x180002dca  push    rsi
0x180002dcb  push    rdi
0x180002dcc  push    r14
0x180002dce  push    r15
0x180002dd0  sub     rsp, 250h
0x180002dd7  mov     rax, cs:__security_cookie
0x180002dde  xor     rax, rsp
0x180002de1  mov     [rsp+278h+var_38], rax
0x180002de9  xor     r15d, r15d
0x180002dec  mov     rbx, r8
0x180002def  mov     rsi, rdx
0x180002df2  mov     r14, rcx
0x180002df5  test    rdx, rdx
0x180002df8  jz      loc_180003051
0x180002dfe  test    rcx, rcx
0x180002e01  jz      loc_180003051
0x180002e07  mov     rax, cs:g_pfnResultLoggingCallback
0x180002e0e  mov     [rcx], r15w
0x180002e12  test    rax, rax
0x180002e15  jz      short loc_180002E38
0x180002e17  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002e1e  jz      short loc_180002E38
0x180002e20  mov     r8, rdx
0x180002e23  mov     rdx, rcx
0x180002e26  mov     rcx, rbx
0x180002e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e2e  cmp     [r14], r15w
0x180002e32  jnz     loc_180003051
0x180002e38  mov     ecx, [rbx]
0x180002e3a  mov     bpl, 8
0x180002e3d  test    ecx, ecx
0x180002e3f  jz      short loc_180002E8A
0x180002e41  sub     ecx, 1
0x180002e44  jz      short loc_180002E72
0x180002e46  sub     ecx, 1
0x180002e49  jz      short loc_180002E62
0x180002e4b  cmp     ecx, 1
0x180002e4e  jz      short loc_180002E59
0x180002e50  lea     rdi, qword_180010080
0x180002e57  jmp     short loc_180002E91
0x180002e59  lea     rdi, aFailfast; "FailFast"
0x180002e60  jmp     short loc_180002E91
0x180002e62  lea     rax, aLoghr; "LogHr"
0x180002e69  lea     rdi, aLognt; "LogNt"
0x180002e70  jmp     short loc_180002E80
0x180002e72  lea     rax, aReturnhr; "ReturnHr"
0x180002e79  lea     rdi, aReturnnt; "ReturnNt"
0x180002e80  test    [rbx+4], bpl
0x180002e84  cmovz   rdi, rax
0x180002e88  jmp     short loc_180002E91
0x180002e8a  lea     rdi, aException; "Exception"
0x180002e91  xor     edx, edx; Val
0x180002e93  lea     rcx, [rsp+278h+Buffer]; void *
0x180002e98  mov     r8d, 200h; Size
0x180002e9e  call    memset_0
0x180002ea3  test    [rbx+4], bpl
0x180002ea7  jz      short loc_180002ECC
0x180002ea9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180002eb0  mov     ebp, [rbx+0Ch]
0x180002eb3  test    rax, rax
0x180002eb6  jz      short loc_180002EFC
0x180002eb8  mov     r8d, 100h
0x180002ebe  lea     rdx, [rsp+278h+Buffer]
0x180002ec3  mov     ecx, ebp
0x180002ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002eca  jmp     short loc_180002EFC
0x180002ecc  mov     ebp, [rbx+8]
0x180002ecf  lea     rax, [rsp+278h+Buffer]
0x180002ed4  mov     [rsp+278h+Arguments], r15; Arguments
0x180002ed9  mov     r8d, ebp; dwMessageId
0x180002edc  mov     [rsp+278h+nSize], 100h; nSize
0x180002ee4  mov     r9d, 400h; dwLanguageId
0x180002eea  xor     edx, edx; lpSource
0x180002eec  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180002ef1  mov     ecx, 1200h; dwFlags
0x180002ef6  call    cs:__imp_FormatMessageW
0x180002efc  mov     r9, [rbx+38h]; unsigned __int16 *
0x180002f00  lea     rsi, [r14+rsi*2]
0x180002f04  mov     rax, [rbx+88h]
0x180002f0b  mov     rdx, rsi; unsigned __int16 *
0x180002f0e  mov     rcx, [rbx+80h]
0x180002f15  test    r9, r9
0x180002f18  jz      short loc_180002F3C
0x180002f1a  mov     [rsp+278h+Arguments], rax
0x180002f1f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180002f26  mov     eax, [rbx+40h]
0x180002f29  mov     qword ptr [rsp+278h+nSize], rcx
0x180002f2e  mov     rcx, r14; this
0x180002f31  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180002f35  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002f3a  jmp     short loc_180002F53
0x180002f3c  mov     r9, rcx; unsigned __int16 *
0x180002f3f  mov     [rsp+278h+lpBuffer], rax
0x180002f44  mov     rcx, r14; this
0x180002f47  lea     r8, aHsP; "%hs!%p: "
0x180002f4e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002f53  mov     r9, [rbx+90h]; unsigned __int16 *
0x180002f5a  mov     r14, rax
0x180002f5d  test    r9, r9
0x180002f60  jz      short loc_180002F77
0x180002f62  lea     r8, aCallerP; "(caller: %p) "
0x180002f69  mov     rdx, rsi; unsigned __int16 *
0x180002f6c  mov     rcx, rax; this
0x180002f6f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002f74  mov     r14, rax
0x180002f77  call    cs:__imp_GetCurrentThreadId
0x180002f7d  lea     rcx, [rsp+278h+Buffer]
0x180002f82  mov     r9, rdi; unsigned __int16 *
0x180002f85  mov     [rsp+278h+var_240], rcx
0x180002f8a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180002f91  mov     dword ptr [rsp+278h+Arguments], ebp
0x180002f95  mov     rdx, rsi; unsigned __int16 *
0x180002f98  mov     [rsp+278h+nSize], eax
0x180002f9c  mov     rcx, r14; this
0x180002f9f  mov     eax, [rbx+44h]
0x180002fa2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180002fa6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002fab  cmp     [rbx+18h], r15
0x180002faf  jnz     short loc_180002FC1
0x180002fb1  cmp     [rbx+48h], r15
0x180002fb5  jnz     short loc_180002FC1
0x180002fb7  cmp     [rbx+30h], r15
0x180002fbb  jz      loc_180003051
0x180002fc1  lea     r8, asc_180010170; "    "
0x180002fc8  mov     rdx, rsi; unsigned __int16 *
0x180002fcb  mov     rcx, rax; this
0x180002fce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002fd3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180002fd7  test    r9, r9
0x180002fda  jz      short loc_180002FEE
0x180002fdc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180002fe3  mov     rdx, rsi; unsigned __int16 *
0x180002fe6  mov     rcx, rax; this
0x180002fe9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002fee  mov     r9, [rbx+48h]; unsigned __int16 *
0x180002ff2  test    r9, r9
0x180002ff5  jz      short loc_180003009
0x180002ff7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180002ffe  mov     rdx, rsi; unsigned __int16 *
0x180003001  mov     rcx, rax; this
0x180003004  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003009  mov     rcx, [rbx+28h]
0x18000300d  mov     rdx, rsi; unsigned __int16 *
0x180003010  mov     r9, [rbx+30h]; unsigned __int16 *
0x180003014  test    rcx, rcx
0x180003017  jz      short loc_18000302F
0x180003019  mov     [rsp+278h+lpBuffer], rcx
0x18000301e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180003025  mov     rcx, rax; this
0x180003028  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000302d  jmp     short loc_180003051
0x18000302f  mov     rcx, rax; this
0x180003032  test    r9, r9
0x180003035  jz      short loc_180003045
0x180003037  lea     r8, aHs; "[%hs]\n"
0x18000303e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003043  jmp     short loc_180003051
0x180003045  lea     r8, asc_1800101E8; "\n"
0x18000304c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003051  xor     eax, eax
0x180003053  mov     rcx, [rsp+278h+var_38]
0x18000305b  xor     rcx, rsp; StackCookie
0x18000305e  call    __security_check_cookie
0x180003063  mov     rbx, [rsp+278h+arg_18]
0x18000306b  add     rsp, 250h
0x180003072  pop     r15
0x180003074  pop     r14
0x180003076  pop     rdi
0x180003077  pop     rsi
0x180003078  pop     rbp
0x180003079  retn
```
