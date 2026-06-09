# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006a04`
- end: `0x180006cba`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wchar_t *Buffer, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000562c`
- `0x18000589c`
- `0x180007368`
- `0x180008a40`

## callees

- `0x180001500`
- `0x180006a04`
- `0x180007668`
- `0x18000b8b0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006bb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006bb7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006b36`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006b36`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wchar_t *Buffer,
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
  WCHAR Buffera[256]; // [rsp+40h] [rbp-238h] BYREF

  if ( !a2 )
    return 0;
  if ( !Buffer )
    return 0;
  *Buffer = 0;
  if ( g_pfnResultLoggingCallback )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      g_pfnResultLoggingCallback(a3, Buffer, a2);
      if ( *Buffer )
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
          v7 = (const char *)&word_180010306;
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
  memset(Buffera, 0, sizeof(Buffera));
  if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
  {
    v9 = *(_DWORD *)(a3 + 12);
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(v9, Buffera, 0x100u);
  }
  else
  {
    v9 = *(_DWORD *)(a3 + 8);
    FormatMessageW(0x1200u, 0, v9, 0x400u, Buffera, 0x100u, 0);
  }
  v10 = &Buffer[(_QWORD)a2];
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const unsigned __int16 **)(a3 + 128);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(Buffer, v10, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, v13, v12);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(Buffer, v10, L"%hs!%p: ", v13, v12);
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
          Buffera);
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
0x180006a04  mov     [rsp+arg_18], rbx
0x180006a09  push    rbp
0x180006a0a  push    rsi
0x180006a0b  push    rdi
0x180006a0c  push    r14
0x180006a0e  push    r15
0x180006a10  sub     rsp, 250h
0x180006a17  mov     rax, cs:__security_cookie
0x180006a1e  xor     rax, rsp
0x180006a21  mov     [rsp+278h+var_38], rax
0x180006a29  mov     rbx, r8
0x180006a2c  mov     rsi, rdx
0x180006a2f  mov     r14, rcx
0x180006a32  xor     r15d, r15d
0x180006a35  test    rdx, rdx
0x180006a38  jz      loc_180006C91
0x180006a3e  test    rcx, rcx
0x180006a41  jz      loc_180006C91
0x180006a47  mov     [rcx], r15w
0x180006a4b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006a52  test    rax, rax
0x180006a55  jz      short loc_180006A78
0x180006a57  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006a5e  jz      short loc_180006A78
0x180006a60  mov     r8, rdx
0x180006a63  mov     rdx, rcx
0x180006a66  mov     rcx, rbx
0x180006a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a6e  cmp     [r14], r15w
0x180006a72  jnz     loc_180006C91
0x180006a78  mov     ecx, [rbx]
0x180006a7a  mov     bpl, 8
0x180006a7d  test    ecx, ecx
0x180006a7f  jz      short loc_180006ACA
0x180006a81  sub     ecx, 1
0x180006a84  jz      short loc_180006AB2
0x180006a86  sub     ecx, 1
0x180006a89  jz      short loc_180006AA2
0x180006a8b  cmp     ecx, 1
0x180006a8e  jz      short loc_180006A99
0x180006a90  lea     rdi, word_180010306
0x180006a97  jmp     short loc_180006AD1
0x180006a99  lea     rdi, aFailfast; "FailFast"
0x180006aa0  jmp     short loc_180006AD1
0x180006aa2  lea     rax, aLoghr; "LogHr"
0x180006aa9  lea     rdi, aLognt; "LogNt"
0x180006ab0  jmp     short loc_180006AC0
0x180006ab2  lea     rax, aReturnhr; "ReturnHr"
0x180006ab9  lea     rdi, aReturnnt; "ReturnNt"
0x180006ac0  test    [rbx+4], bpl
0x180006ac4  cmovz   rdi, rax
0x180006ac8  jmp     short loc_180006AD1
0x180006aca  lea     rdi, aException; "Exception"
0x180006ad1  xor     edx, edx; Val
0x180006ad3  mov     r8d, 200h; Size
0x180006ad9  lea     rcx, [rsp+278h+Buffer]; void *
0x180006ade  call    memset
0x180006ae3  test    [rbx+4], bpl
0x180006ae7  jz      short loc_180006B0C
0x180006ae9  mov     ebp, [rbx+0Ch]
0x180006aec  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180006af3  test    rax, rax
0x180006af6  jz      short loc_180006B3C
0x180006af8  mov     r8d, 100h
0x180006afe  lea     rdx, [rsp+278h+Buffer]
0x180006b03  mov     ecx, ebp
0x180006b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b0a  jmp     short loc_180006B3C
0x180006b0c  mov     ebp, [rbx+8]
0x180006b0f  mov     [rsp+278h+Arguments], r15; Arguments
0x180006b14  mov     [rsp+278h+nSize], 100h; nSize
0x180006b1c  lea     rax, [rsp+278h+Buffer]
0x180006b21  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006b26  mov     r9d, 400h; dwLanguageId
0x180006b2c  mov     r8d, ebp; dwMessageId
0x180006b2f  xor     edx, edx; lpSource
0x180006b31  mov     ecx, 1200h; dwFlags
0x180006b36  call    cs:__imp_FormatMessageW
0x180006b3c  lea     rsi, [r14+rsi*2]
0x180006b40  mov     r9, [rbx+38h]; unsigned __int16 *
0x180006b44  mov     rax, [rbx+88h]
0x180006b4b  mov     rcx, [rbx+80h]
0x180006b52  mov     rdx, rsi; unsigned __int16 *
0x180006b55  test    r9, r9
0x180006b58  jz      short loc_180006B7C
0x180006b5a  mov     [rsp+278h+Arguments], rax
0x180006b5f  mov     qword ptr [rsp+278h+nSize], rcx
0x180006b64  mov     eax, [rbx+40h]
0x180006b67  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006b6b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006b72  mov     rcx, r14; Buffer
0x180006b75  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006b7a  jmp     short loc_180006B93
0x180006b7c  mov     [rsp+278h+lpBuffer], rax
0x180006b81  mov     r9, rcx; unsigned __int16 *
0x180006b84  lea     r8, aHsP; "%hs!%p: "
0x180006b8b  mov     rcx, r14; Buffer
0x180006b8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006b93  mov     r14, rax
0x180006b96  mov     r9, [rbx+90h]; unsigned __int16 *
0x180006b9d  test    r9, r9
0x180006ba0  jz      short loc_180006BB7
0x180006ba2  lea     r8, aCallerP; "(caller: %p) "
0x180006ba9  mov     rdx, rsi; unsigned __int16 *
0x180006bac  mov     rcx, rax; Buffer
0x180006baf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006bb4  mov     r14, rax
0x180006bb7  call    cs:__imp_GetCurrentThreadId
0x180006bbd  lea     rcx, [rsp+278h+Buffer]
0x180006bc2  mov     [rsp+278h+var_240], rcx
0x180006bc7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180006bcb  mov     [rsp+278h+nSize], eax
0x180006bcf  mov     eax, [rbx+44h]
0x180006bd2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006bd6  mov     r9, rdi; unsigned __int16 *
0x180006bd9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006be0  mov     rdx, rsi; unsigned __int16 *
0x180006be3  mov     rcx, r14; Buffer
0x180006be6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006beb  cmp     [rbx+18h], r15
0x180006bef  jnz     short loc_180006C01
0x180006bf1  cmp     [rbx+48h], r15
0x180006bf5  jnz     short loc_180006C01
0x180006bf7  cmp     [rbx+30h], r15
0x180006bfb  jz      loc_180006C91
0x180006c01  lea     r8, asc_180010408; "    "
0x180006c08  mov     rdx, rsi; unsigned __int16 *
0x180006c0b  mov     rcx, rax; Buffer
0x180006c0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006c13  mov     r9, [rbx+18h]; unsigned __int16 *
0x180006c17  test    r9, r9
0x180006c1a  jz      short loc_180006C2E
0x180006c1c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006c23  mov     rdx, rsi; unsigned __int16 *
0x180006c26  mov     rcx, rax; Buffer
0x180006c29  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006c2e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180006c32  test    r9, r9
0x180006c35  jz      short loc_180006C49
0x180006c37  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180006c3e  mov     rdx, rsi; unsigned __int16 *
0x180006c41  mov     rcx, rax; Buffer
0x180006c44  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006c49  mov     rcx, [rbx+28h]
0x180006c4d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006c51  mov     rdx, rsi; unsigned __int16 *
0x180006c54  test    rcx, rcx
0x180006c57  jz      short loc_180006C6F
0x180006c59  mov     [rsp+278h+lpBuffer], rcx
0x180006c5e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006c65  mov     rcx, rax; Buffer
0x180006c68  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006c6d  jmp     short loc_180006C91
0x180006c6f  mov     rcx, rax; Buffer
0x180006c72  test    r9, r9
0x180006c75  jz      short loc_180006C85
0x180006c77  lea     r8, aHs; "[%hs]\n"
0x180006c7e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006c83  jmp     short loc_180006C91
0x180006c85  lea     r8, asc_180010480; "\n"
0x180006c8c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006c91  xor     eax, eax
0x180006c93  mov     rcx, [rsp+278h+var_38]
0x180006c9b  xor     rcx, rsp; StackCookie
0x180006c9e  call    __security_check_cookie
0x180006ca3  mov     rbx, [rsp+278h+arg_18]
0x180006cab  add     rsp, 250h
0x180006cb2  pop     r15
0x180006cb4  pop     r14
0x180006cb6  pop     rdi
0x180006cb7  pop     rsi
0x180006cb8  pop     rbp
0x180006cb9  retn
```
