# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180003af4`
- end: `0x180003daa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800029d0`
- `0x180002c38`
- `0x180004450`

## callees

- `0x180003af4`
- `0x180004750`
- `0x180012dce`
- `0x180012e00`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180003ca7`
- `KERNEL32!GetCurrentThreadId` at `0x180003ca7`
- `KERNEL32!FormatMessageW` at `0x180003c26`
- `KERNEL32!FormatMessageW` at `0x180003c26`

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
          v8 = (const char *)&word_180016326;
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
0x180003af4  mov     [rsp+arg_18], rbx
0x180003af9  push    rbp
0x180003afa  push    rsi
0x180003afb  push    rdi
0x180003afc  push    r14
0x180003afe  push    r15
0x180003b00  sub     rsp, 250h
0x180003b07  mov     rax, cs:__security_cookie
0x180003b0e  xor     rax, rsp
0x180003b11  mov     [rsp+278h+var_38], rax
0x180003b19  xor     r15d, r15d
0x180003b1c  mov     rbx, r8
0x180003b1f  mov     rsi, rdx
0x180003b22  mov     r14, rcx
0x180003b25  test    rdx, rdx
0x180003b28  jz      loc_180003D81
0x180003b2e  test    rcx, rcx
0x180003b31  jz      loc_180003D81
0x180003b37  mov     rax, cs:g_pfnResultLoggingCallback
0x180003b3e  mov     [rcx], r15w
0x180003b42  test    rax, rax
0x180003b45  jz      short loc_180003B68
0x180003b47  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003b4e  jz      short loc_180003B68
0x180003b50  mov     r8, rdx
0x180003b53  mov     rdx, rcx
0x180003b56  mov     rcx, rbx
0x180003b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b5e  cmp     [r14], r15w
0x180003b62  jnz     loc_180003D81
0x180003b68  mov     ecx, [rbx]
0x180003b6a  mov     bpl, 8
0x180003b6d  test    ecx, ecx
0x180003b6f  jz      short loc_180003BBA
0x180003b71  sub     ecx, 1
0x180003b74  jz      short loc_180003BA2
0x180003b76  sub     ecx, 1
0x180003b79  jz      short loc_180003B92
0x180003b7b  cmp     ecx, 1
0x180003b7e  jz      short loc_180003B89
0x180003b80  lea     rdi, word_180016326
0x180003b87  jmp     short loc_180003BC1
0x180003b89  lea     rdi, aFailfast; "FailFast"
0x180003b90  jmp     short loc_180003BC1
0x180003b92  lea     rax, aLoghr; "LogHr"
0x180003b99  lea     rdi, aLognt; "LogNt"
0x180003ba0  jmp     short loc_180003BB0
0x180003ba2  lea     rax, aReturnhr; "ReturnHr"
0x180003ba9  lea     rdi, aReturnnt; "ReturnNt"
0x180003bb0  test    [rbx+4], bpl
0x180003bb4  cmovz   rdi, rax
0x180003bb8  jmp     short loc_180003BC1
0x180003bba  lea     rdi, aException; "Exception"
0x180003bc1  xor     edx, edx; Val
0x180003bc3  lea     rcx, [rsp+278h+Buffer]; void *
0x180003bc8  mov     r8d, 200h; Size
0x180003bce  call    memset_0
0x180003bd3  test    [rbx+4], bpl
0x180003bd7  jz      short loc_180003BFC
0x180003bd9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180003be0  mov     ebp, [rbx+0Ch]
0x180003be3  test    rax, rax
0x180003be6  jz      short loc_180003C2C
0x180003be8  mov     r8d, 100h
0x180003bee  lea     rdx, [rsp+278h+Buffer]
0x180003bf3  mov     ecx, ebp
0x180003bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bfa  jmp     short loc_180003C2C
0x180003bfc  mov     ebp, [rbx+8]
0x180003bff  lea     rax, [rsp+278h+Buffer]
0x180003c04  mov     [rsp+278h+Arguments], r15; Arguments
0x180003c09  mov     r8d, ebp; dwMessageId
0x180003c0c  mov     [rsp+278h+nSize], 100h; nSize
0x180003c14  mov     r9d, 400h; dwLanguageId
0x180003c1a  xor     edx, edx; lpSource
0x180003c1c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180003c21  mov     ecx, 1200h; dwFlags
0x180003c26  call    cs:__imp_FormatMessageW
0x180003c2c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180003c30  lea     rsi, [r14+rsi*2]
0x180003c34  mov     rax, [rbx+88h]
0x180003c3b  mov     rdx, rsi; unsigned __int16 *
0x180003c3e  mov     rcx, [rbx+80h]
0x180003c45  test    r9, r9
0x180003c48  jz      short loc_180003C6C
0x180003c4a  mov     [rsp+278h+Arguments], rax
0x180003c4f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180003c56  mov     eax, [rbx+40h]
0x180003c59  mov     qword ptr [rsp+278h+nSize], rcx
0x180003c5e  mov     rcx, r14; this
0x180003c61  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003c65  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003c6a  jmp     short loc_180003C83
0x180003c6c  mov     r9, rcx; unsigned __int16 *
0x180003c6f  mov     [rsp+278h+lpBuffer], rax
0x180003c74  mov     rcx, r14; this
0x180003c77  lea     r8, aHsP; "%hs!%p: "
0x180003c7e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003c83  mov     r9, [rbx+90h]; unsigned __int16 *
0x180003c8a  mov     r14, rax
0x180003c8d  test    r9, r9
0x180003c90  jz      short loc_180003CA7
0x180003c92  lea     r8, aCallerP; "(caller: %p) "
0x180003c99  mov     rdx, rsi; unsigned __int16 *
0x180003c9c  mov     rcx, rax; this
0x180003c9f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003ca4  mov     r14, rax
0x180003ca7  call    cs:__imp_GetCurrentThreadId
0x180003cad  lea     rcx, [rsp+278h+Buffer]
0x180003cb2  mov     r9, rdi; unsigned __int16 *
0x180003cb5  mov     [rsp+278h+var_240], rcx
0x180003cba  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180003cc1  mov     dword ptr [rsp+278h+Arguments], ebp
0x180003cc5  mov     rdx, rsi; unsigned __int16 *
0x180003cc8  mov     [rsp+278h+nSize], eax
0x180003ccc  mov     rcx, r14; this
0x180003ccf  mov     eax, [rbx+44h]
0x180003cd2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003cd6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003cdb  cmp     [rbx+18h], r15
0x180003cdf  jnz     short loc_180003CF1
0x180003ce1  cmp     [rbx+48h], r15
0x180003ce5  jnz     short loc_180003CF1
0x180003ce7  cmp     [rbx+30h], r15
0x180003ceb  jz      loc_180003D81
0x180003cf1  lea     r8, asc_180016410; "    "
0x180003cf8  mov     rdx, rsi; unsigned __int16 *
0x180003cfb  mov     rcx, rax; this
0x180003cfe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003d03  mov     r9, [rbx+18h]; unsigned __int16 *
0x180003d07  test    r9, r9
0x180003d0a  jz      short loc_180003D1E
0x180003d0c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180003d13  mov     rdx, rsi; unsigned __int16 *
0x180003d16  mov     rcx, rax; this
0x180003d19  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003d1e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180003d22  test    r9, r9
0x180003d25  jz      short loc_180003D39
0x180003d27  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180003d2e  mov     rdx, rsi; unsigned __int16 *
0x180003d31  mov     rcx, rax; this
0x180003d34  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003d39  mov     rcx, [rbx+28h]
0x180003d3d  mov     rdx, rsi; unsigned __int16 *
0x180003d40  mov     r9, [rbx+30h]; unsigned __int16 *
0x180003d44  test    rcx, rcx
0x180003d47  jz      short loc_180003D5F
0x180003d49  mov     [rsp+278h+lpBuffer], rcx
0x180003d4e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180003d55  mov     rcx, rax; this
0x180003d58  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003d5d  jmp     short loc_180003D81
0x180003d5f  mov     rcx, rax; this
0x180003d62  test    r9, r9
0x180003d65  jz      short loc_180003D75
0x180003d67  lea     r8, aHs; "[%hs]\n"
0x180003d6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003d73  jmp     short loc_180003D81
0x180003d75  lea     r8, asc_180016488; "\n"
0x180003d7c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003d81  xor     eax, eax
0x180003d83  mov     rcx, [rsp+278h+var_38]
0x180003d8b  xor     rcx, rsp; StackCookie
0x180003d8e  call    __security_check_cookie
0x180003d93  mov     rbx, [rsp+278h+arg_18]
0x180003d9b  add     rsp, 250h
0x180003da2  pop     r15
0x180003da4  pop     r14
0x180003da6  pop     rdi
0x180003da7  pop     rsi
0x180003da8  pop     rbp
0x180003da9  retn
```
