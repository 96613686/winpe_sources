# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180002bf4`
- end: `0x180002eaa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180003f00`
- `0x180006860`
- `0x18001702c`

## callees

- `0x180002bf4`
- `0x180003170`
- `0x18002c802`
- `0x18002c840`
- `0x18002f010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180002da7`
- `KERNEL32!GetCurrentThreadId` at `0x180002da7`
- `KERNEL32!FormatMessageW` at `0x180002d26`
- `KERNEL32!FormatMessageW` at `0x180002d26`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        STRSAFE_LPWSTR pszDest,
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
  wchar_t *v14; // rax
  wchar_t *v15; // r14
  const unsigned __int16 *v16; // r9
  wchar_t *v17; // rax
  const unsigned __int16 *v18; // r9
  wchar_t *v19; // rax
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
  if ( !pszDest )
    return 0;
  *pszDest = 0;
  if ( g_pfnResultLoggingCallback )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      g_pfnResultLoggingCallback(a3, pszDest, a2);
      if ( *pszDest )
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
          v7 = (const char *)&qword_180033960;
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
  v10 = &pszDest[(_QWORD)a2];
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const unsigned __int16 **)(a3 + 128);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(pszDest, v10, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, v13, v12);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(pszDest, v10, L"%hs!%p: ", v13, v12);
  }
  v15 = v14;
  v16 = *(const unsigned __int16 **)(a3 + 144);
  if ( v16 )
    v15 = wil::details::LogStringPrintf(v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = wil::details::LogStringPrintf(
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
      v19 = wil::details::LogStringPrintf(v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf(v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf(v19, v10, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf(v19, v10, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf(v19, v10, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180002bf4  mov     [rsp+arg_18], rbx
0x180002bf9  push    rbp
0x180002bfa  push    rsi
0x180002bfb  push    rdi
0x180002bfc  push    r14
0x180002bfe  push    r15
0x180002c00  sub     rsp, 250h
0x180002c07  mov     rax, cs:__security_cookie
0x180002c0e  xor     rax, rsp
0x180002c11  mov     [rsp+278h+var_38], rax
0x180002c19  mov     rbx, r8
0x180002c1c  mov     rsi, rdx
0x180002c1f  mov     r14, rcx
0x180002c22  xor     r15d, r15d
0x180002c25  test    rdx, rdx
0x180002c28  jz      loc_180002E81
0x180002c2e  test    rcx, rcx
0x180002c31  jz      loc_180002E81
0x180002c37  mov     [rcx], r15w
0x180002c3b  mov     rax, cs:g_pfnResultLoggingCallback
0x180002c42  test    rax, rax
0x180002c45  jz      short loc_180002C68
0x180002c47  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002c4e  jz      short loc_180002C68
0x180002c50  mov     r8, rdx
0x180002c53  mov     rdx, rcx
0x180002c56  mov     rcx, rbx
0x180002c59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c5e  cmp     [r14], r15w
0x180002c62  jnz     loc_180002E81
0x180002c68  mov     ecx, [rbx]
0x180002c6a  mov     bpl, 8
0x180002c6d  test    ecx, ecx
0x180002c6f  jz      short loc_180002CBA
0x180002c71  sub     ecx, 1
0x180002c74  jz      short loc_180002CA2
0x180002c76  sub     ecx, 1
0x180002c79  jz      short loc_180002C92
0x180002c7b  cmp     ecx, 1
0x180002c7e  jz      short loc_180002C89
0x180002c80  lea     rdi, qword_180033960
0x180002c87  jmp     short loc_180002CC1
0x180002c89  lea     rdi, aFailfast; "FailFast"
0x180002c90  jmp     short loc_180002CC1
0x180002c92  lea     rax, aLoghr; "LogHr"
0x180002c99  lea     rdi, aLognt; "LogNt"
0x180002ca0  jmp     short loc_180002CB0
0x180002ca2  lea     rax, aReturnhr; "ReturnHr"
0x180002ca9  lea     rdi, aReturnnt; "ReturnNt"
0x180002cb0  test    [rbx+4], bpl
0x180002cb4  cmovz   rdi, rax
0x180002cb8  jmp     short loc_180002CC1
0x180002cba  lea     rdi, aException; "Exception"
0x180002cc1  xor     edx, edx; Val
0x180002cc3  mov     r8d, 200h; Size
0x180002cc9  lea     rcx, [rsp+278h+Buffer]; void *
0x180002cce  call    memset_0
0x180002cd3  test    [rbx+4], bpl
0x180002cd7  jz      short loc_180002CFC
0x180002cd9  mov     ebp, [rbx+0Ch]
0x180002cdc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180002ce3  test    rax, rax
0x180002ce6  jz      short loc_180002D2C
0x180002ce8  mov     r8d, 100h
0x180002cee  lea     rdx, [rsp+278h+Buffer]
0x180002cf3  mov     ecx, ebp
0x180002cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cfa  jmp     short loc_180002D2C
0x180002cfc  mov     ebp, [rbx+8]
0x180002cff  mov     [rsp+278h+Arguments], r15; Arguments
0x180002d04  mov     [rsp+278h+nSize], 100h; nSize
0x180002d0c  lea     rax, [rsp+278h+Buffer]
0x180002d11  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180002d16  mov     r9d, 400h; dwLanguageId
0x180002d1c  mov     r8d, ebp; dwMessageId
0x180002d1f  xor     edx, edx; lpSource
0x180002d21  mov     ecx, 1200h; dwFlags
0x180002d26  call    cs:__imp_FormatMessageW
0x180002d2c  lea     rsi, [r14+rsi*2]
0x180002d30  mov     r9, [rbx+38h]; unsigned __int16 *
0x180002d34  mov     rax, [rbx+88h]
0x180002d3b  mov     rcx, [rbx+80h]
0x180002d42  mov     rdx, rsi; unsigned __int16 *
0x180002d45  test    r9, r9
0x180002d48  jz      short loc_180002D6C
0x180002d4a  mov     [rsp+278h+Arguments], rax
0x180002d4f  mov     qword ptr [rsp+278h+nSize], rcx
0x180002d54  mov     eax, [rbx+40h]
0x180002d57  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180002d5b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180002d62  mov     rcx, r14; pszDest
0x180002d65  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002d6a  jmp     short loc_180002D83
0x180002d6c  mov     [rsp+278h+lpBuffer], rax
0x180002d71  mov     r9, rcx; unsigned __int16 *
0x180002d74  lea     r8, aHsP; "%hs!%p: "
0x180002d7b  mov     rcx, r14; pszDest
0x180002d7e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002d83  mov     r14, rax
0x180002d86  mov     r9, [rbx+90h]; unsigned __int16 *
0x180002d8d  test    r9, r9
0x180002d90  jz      short loc_180002DA7
0x180002d92  lea     r8, aCallerP; "(caller: %p) "
0x180002d99  mov     rdx, rsi; unsigned __int16 *
0x180002d9c  mov     rcx, rax; pszDest
0x180002d9f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002da4  mov     r14, rax
0x180002da7  call    cs:__imp_GetCurrentThreadId
0x180002dad  lea     rcx, [rsp+278h+Buffer]
0x180002db2  mov     [rsp+278h+var_240], rcx
0x180002db7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180002dbb  mov     [rsp+278h+nSize], eax
0x180002dbf  mov     eax, [rbx+44h]
0x180002dc2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180002dc6  mov     r9, rdi; unsigned __int16 *
0x180002dc9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180002dd0  mov     rdx, rsi; unsigned __int16 *
0x180002dd3  mov     rcx, r14; pszDest
0x180002dd6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002ddb  cmp     [rbx+18h], r15
0x180002ddf  jnz     short loc_180002DF1
0x180002de1  cmp     [rbx+48h], r15
0x180002de5  jnz     short loc_180002DF1
0x180002de7  cmp     [rbx+30h], r15
0x180002deb  jz      loc_180002E81
0x180002df1  lea     r8, asc_180033A98; "    "
0x180002df8  mov     rdx, rsi; unsigned __int16 *
0x180002dfb  mov     rcx, rax; pszDest
0x180002dfe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002e03  mov     r9, [rbx+18h]; unsigned __int16 *
0x180002e07  test    r9, r9
0x180002e0a  jz      short loc_180002E1E
0x180002e0c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180002e13  mov     rdx, rsi; unsigned __int16 *
0x180002e16  mov     rcx, rax; pszDest
0x180002e19  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002e1e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180002e22  test    r9, r9
0x180002e25  jz      short loc_180002E39
0x180002e27  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180002e2e  mov     rdx, rsi; unsigned __int16 *
0x180002e31  mov     rcx, rax; pszDest
0x180002e34  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002e39  mov     rcx, [rbx+28h]
0x180002e3d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180002e41  mov     rdx, rsi; unsigned __int16 *
0x180002e44  test    rcx, rcx
0x180002e47  jz      short loc_180002E5F
0x180002e49  mov     [rsp+278h+lpBuffer], rcx
0x180002e4e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180002e55  mov     rcx, rax; pszDest
0x180002e58  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002e5d  jmp     short loc_180002E81
0x180002e5f  mov     rcx, rax; pszDest
0x180002e62  test    r9, r9
0x180002e65  jz      short loc_180002E75
0x180002e67  lea     r8, aHs; "[%hs]\n"
0x180002e6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002e73  jmp     short loc_180002E81
0x180002e75  lea     r8, SubStr; "\n"
0x180002e7c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002e81  xor     eax, eax
0x180002e83  mov     rcx, [rsp+278h+var_38]
0x180002e8b  xor     rcx, rsp; StackCookie
0x180002e8e  call    __security_check_cookie
0x180002e93  mov     rbx, [rsp+278h+arg_18]
0x180002e9b  add     rsp, 250h
0x180002ea2  pop     r15
0x180002ea4  pop     r14
0x180002ea6  pop     rdi
0x180002ea7  pop     rsi
0x180002ea8  pop     rbp
0x180002ea9  retn
```
