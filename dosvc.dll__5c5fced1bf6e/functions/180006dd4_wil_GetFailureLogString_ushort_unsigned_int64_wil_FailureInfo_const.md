# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006dd4`
- end: `0x18000708a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180002780`
- `0x180008610`

## callees

- `0x180005020`
- `0x180005b2c`
- `0x180006dd4`
- `0x1800074e4`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f87`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006f06`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006f06`

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
          v7 = (const char *)&dword_18000D194;
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
0x180006dd4  mov     [rsp+arg_18], rbx
0x180006dd9  push    rbp
0x180006dda  push    rsi
0x180006ddb  push    rdi
0x180006ddc  push    r14
0x180006dde  push    r15
0x180006de0  sub     rsp, 250h
0x180006de7  mov     rax, cs:__security_cookie
0x180006dee  xor     rax, rsp
0x180006df1  mov     [rsp+278h+var_38], rax
0x180006df9  mov     rbx, r8
0x180006dfc  mov     rsi, rdx
0x180006dff  mov     r14, rcx
0x180006e02  xor     r15d, r15d
0x180006e05  test    rdx, rdx
0x180006e08  jz      loc_180007061
0x180006e0e  test    rcx, rcx
0x180006e11  jz      loc_180007061
0x180006e17  mov     [rcx], r15w
0x180006e1b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006e22  test    rax, rax
0x180006e25  jz      short loc_180006E48
0x180006e27  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006e2e  jz      short loc_180006E48
0x180006e30  mov     r8, rdx
0x180006e33  mov     rdx, rcx
0x180006e36  mov     rcx, rbx
0x180006e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e3e  cmp     [r14], r15w
0x180006e42  jnz     loc_180007061
0x180006e48  mov     ecx, [rbx]
0x180006e4a  mov     bpl, 8
0x180006e4d  test    ecx, ecx
0x180006e4f  jz      short loc_180006E9A
0x180006e51  sub     ecx, 1
0x180006e54  jz      short loc_180006E82
0x180006e56  sub     ecx, 1
0x180006e59  jz      short loc_180006E72
0x180006e5b  cmp     ecx, 1
0x180006e5e  jz      short loc_180006E69
0x180006e60  lea     rdi, dword_18000D194
0x180006e67  jmp     short loc_180006EA1
0x180006e69  lea     rdi, aFailfast; "FailFast"
0x180006e70  jmp     short loc_180006EA1
0x180006e72  lea     rax, aLoghr; "LogHr"
0x180006e79  lea     rdi, aLognt; "LogNt"
0x180006e80  jmp     short loc_180006E90
0x180006e82  lea     rax, aReturnhr; "ReturnHr"
0x180006e89  lea     rdi, aReturnnt; "ReturnNt"
0x180006e90  test    [rbx+4], bpl
0x180006e94  cmovz   rdi, rax
0x180006e98  jmp     short loc_180006EA1
0x180006e9a  lea     rdi, aException; "Exception"
0x180006ea1  xor     edx, edx; Val
0x180006ea3  mov     r8d, 200h; Size
0x180006ea9  lea     rcx, [rsp+278h+Buffer]; void *
0x180006eae  call    memset_0
0x180006eb3  test    [rbx+4], bpl
0x180006eb7  jz      short loc_180006EDC
0x180006eb9  mov     ebp, [rbx+0Ch]
0x180006ebc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180006ec3  test    rax, rax
0x180006ec6  jz      short loc_180006F0C
0x180006ec8  mov     r8d, 100h
0x180006ece  lea     rdx, [rsp+278h+Buffer]
0x180006ed3  mov     ecx, ebp
0x180006ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006eda  jmp     short loc_180006F0C
0x180006edc  mov     ebp, [rbx+8]
0x180006edf  mov     [rsp+278h+Arguments], r15; Arguments
0x180006ee4  mov     [rsp+278h+nSize], 100h; nSize
0x180006eec  lea     rax, [rsp+278h+Buffer]
0x180006ef1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006ef6  mov     r9d, 400h; dwLanguageId
0x180006efc  mov     r8d, ebp; dwMessageId
0x180006eff  xor     edx, edx; lpSource
0x180006f01  mov     ecx, 1200h; dwFlags
0x180006f06  call    cs:__imp_FormatMessageW
0x180006f0c  lea     rsi, [r14+rsi*2]
0x180006f10  mov     r9, [rbx+38h]; unsigned __int16 *
0x180006f14  mov     rax, [rbx+88h]
0x180006f1b  mov     rcx, [rbx+80h]
0x180006f22  mov     rdx, rsi; unsigned __int16 *
0x180006f25  test    r9, r9
0x180006f28  jz      short loc_180006F4C
0x180006f2a  mov     [rsp+278h+Arguments], rax
0x180006f2f  mov     qword ptr [rsp+278h+nSize], rcx
0x180006f34  mov     eax, [rbx+40h]
0x180006f37  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006f3b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006f42  mov     rcx, r14; this
0x180006f45  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006f4a  jmp     short loc_180006F63
0x180006f4c  mov     [rsp+278h+lpBuffer], rax
0x180006f51  mov     r9, rcx; unsigned __int16 *
0x180006f54  lea     r8, aHsP; "%hs!%p: "
0x180006f5b  mov     rcx, r14; this
0x180006f5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006f63  mov     r14, rax
0x180006f66  mov     r9, [rbx+90h]; unsigned __int16 *
0x180006f6d  test    r9, r9
0x180006f70  jz      short loc_180006F87
0x180006f72  lea     r8, aCallerP; "(caller: %p) "
0x180006f79  mov     rdx, rsi; unsigned __int16 *
0x180006f7c  mov     rcx, rax; this
0x180006f7f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006f84  mov     r14, rax
0x180006f87  call    cs:__imp_GetCurrentThreadId
0x180006f8d  lea     rcx, [rsp+278h+Buffer]
0x180006f92  mov     [rsp+278h+var_240], rcx
0x180006f97  mov     dword ptr [rsp+278h+Arguments], ebp
0x180006f9b  mov     [rsp+278h+nSize], eax
0x180006f9f  mov     eax, [rbx+44h]
0x180006fa2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006fa6  mov     r9, rdi; unsigned __int16 *
0x180006fa9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006fb0  mov     rdx, rsi; unsigned __int16 *
0x180006fb3  mov     rcx, r14; this
0x180006fb6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006fbb  cmp     [rbx+18h], r15
0x180006fbf  jnz     short loc_180006FD1
0x180006fc1  cmp     [rbx+48h], r15
0x180006fc5  jnz     short loc_180006FD1
0x180006fc7  cmp     [rbx+30h], r15
0x180006fcb  jz      loc_180007061
0x180006fd1  lea     r8, asc_18000D298; "    "
0x180006fd8  mov     rdx, rsi; unsigned __int16 *
0x180006fdb  mov     rcx, rax; this
0x180006fde  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006fe3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180006fe7  test    r9, r9
0x180006fea  jz      short loc_180006FFE
0x180006fec  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006ff3  mov     rdx, rsi; unsigned __int16 *
0x180006ff6  mov     rcx, rax; this
0x180006ff9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006ffe  mov     r9, [rbx+48h]; unsigned __int16 *
0x180007002  test    r9, r9
0x180007005  jz      short loc_180007019
0x180007007  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000700e  mov     rdx, rsi; unsigned __int16 *
0x180007011  mov     rcx, rax; this
0x180007014  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007019  mov     rcx, [rbx+28h]
0x18000701d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180007021  mov     rdx, rsi; unsigned __int16 *
0x180007024  test    rcx, rcx
0x180007027  jz      short loc_18000703F
0x180007029  mov     [rsp+278h+lpBuffer], rcx
0x18000702e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180007035  mov     rcx, rax; this
0x180007038  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000703d  jmp     short loc_180007061
0x18000703f  mov     rcx, rax; this
0x180007042  test    r9, r9
0x180007045  jz      short loc_180007055
0x180007047  lea     r8, aHs; "[%hs]\n"
0x18000704e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007053  jmp     short loc_180007061
0x180007055  lea     r8, asc_18000D310; "\n"
0x18000705c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007061  xor     eax, eax
0x180007063  mov     rcx, [rsp+278h+var_38]
0x18000706b  xor     rcx, rsp; StackCookie
0x18000706e  call    __security_check_cookie
0x180007073  mov     rbx, [rsp+278h+arg_18]
0x18000707b  add     rsp, 250h
0x180007082  pop     r15
0x180007084  pop     r14
0x180007086  pop     rdi
0x180007087  pop     rsi
0x180007088  pop     rbp
0x180007089  retn
```
