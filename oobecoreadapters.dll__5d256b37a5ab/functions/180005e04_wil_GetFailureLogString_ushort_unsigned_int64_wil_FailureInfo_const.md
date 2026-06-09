# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005e04`
- end: `0x1800060ba`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180004a1c`
- `0x1800068d4`
- `0x180006df0`
- `0x180008b10`

## callees

- `0x180002b60`
- `0x1800036e4`
- `0x180005e04`
- `0x180006bd8`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005fb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005fb7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005f36`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005f36`

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
          v7 = (const char *)&byte_18008A1C0;
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
0x180005e04  mov     [rsp+arg_18], rbx
0x180005e09  push    rbp
0x180005e0a  push    rsi
0x180005e0b  push    rdi
0x180005e0c  push    r14
0x180005e0e  push    r15
0x180005e10  sub     rsp, 250h
0x180005e17  mov     rax, cs:__security_cookie
0x180005e1e  xor     rax, rsp
0x180005e21  mov     [rsp+278h+var_38], rax
0x180005e29  mov     rbx, r8
0x180005e2c  mov     rsi, rdx
0x180005e2f  mov     r14, rcx
0x180005e32  xor     r15d, r15d
0x180005e35  test    rdx, rdx
0x180005e38  jz      loc_180006091
0x180005e3e  test    rcx, rcx
0x180005e41  jz      loc_180006091
0x180005e47  mov     [rcx], r15w
0x180005e4b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005e52  test    rax, rax
0x180005e55  jz      short loc_180005E78
0x180005e57  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005e5e  jz      short loc_180005E78
0x180005e60  mov     r8, rdx
0x180005e63  mov     rdx, rcx
0x180005e66  mov     rcx, rbx
0x180005e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e6e  cmp     [r14], r15w
0x180005e72  jnz     loc_180006091
0x180005e78  mov     ecx, [rbx]
0x180005e7a  mov     bpl, 8
0x180005e7d  test    ecx, ecx
0x180005e7f  jz      short loc_180005ECA
0x180005e81  sub     ecx, 1
0x180005e84  jz      short loc_180005EB2
0x180005e86  sub     ecx, 1
0x180005e89  jz      short loc_180005EA2
0x180005e8b  cmp     ecx, 1
0x180005e8e  jz      short loc_180005E99
0x180005e90  lea     rdi, byte_18008A1C0
0x180005e97  jmp     short loc_180005ED1
0x180005e99  lea     rdi, aFailfast; "FailFast"
0x180005ea0  jmp     short loc_180005ED1
0x180005ea2  lea     rax, aLoghr; "LogHr"
0x180005ea9  lea     rdi, aLognt; "LogNt"
0x180005eb0  jmp     short loc_180005EC0
0x180005eb2  lea     rax, aReturnhr; "ReturnHr"
0x180005eb9  lea     rdi, aReturnnt; "ReturnNt"
0x180005ec0  test    [rbx+4], bpl
0x180005ec4  cmovz   rdi, rax
0x180005ec8  jmp     short loc_180005ED1
0x180005eca  lea     rdi, aException; "Exception"
0x180005ed1  xor     edx, edx; Val
0x180005ed3  mov     r8d, 200h; Size
0x180005ed9  lea     rcx, [rsp+278h+Buffer]; void *
0x180005ede  call    memset_0
0x180005ee3  test    [rbx+4], bpl
0x180005ee7  jz      short loc_180005F0C
0x180005ee9  mov     ebp, [rbx+0Ch]
0x180005eec  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005ef3  test    rax, rax
0x180005ef6  jz      short loc_180005F3C
0x180005ef8  mov     r8d, 100h
0x180005efe  lea     rdx, [rsp+278h+Buffer]
0x180005f03  mov     ecx, ebp
0x180005f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f0a  jmp     short loc_180005F3C
0x180005f0c  mov     ebp, [rbx+8]
0x180005f0f  mov     [rsp+278h+Arguments], r15; Arguments
0x180005f14  mov     [rsp+278h+nSize], 100h; nSize
0x180005f1c  lea     rax, [rsp+278h+Buffer]
0x180005f21  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005f26  mov     r9d, 400h; dwLanguageId
0x180005f2c  mov     r8d, ebp; dwMessageId
0x180005f2f  xor     edx, edx; lpSource
0x180005f31  mov     ecx, 1200h; dwFlags
0x180005f36  call    cs:__imp_FormatMessageW
0x180005f3c  lea     rsi, [r14+rsi*2]
0x180005f40  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005f44  mov     rax, [rbx+88h]
0x180005f4b  mov     rcx, [rbx+80h]
0x180005f52  mov     rdx, rsi; unsigned __int16 *
0x180005f55  test    r9, r9
0x180005f58  jz      short loc_180005F7C
0x180005f5a  mov     [rsp+278h+Arguments], rax
0x180005f5f  mov     qword ptr [rsp+278h+nSize], rcx
0x180005f64  mov     eax, [rbx+40h]
0x180005f67  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005f6b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005f72  mov     rcx, r14; this
0x180005f75  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f7a  jmp     short loc_180005F93
0x180005f7c  mov     [rsp+278h+lpBuffer], rax
0x180005f81  mov     r9, rcx; unsigned __int16 *
0x180005f84  lea     r8, aHsP; "%hs!%p: "
0x180005f8b  mov     rcx, r14; this
0x180005f8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f93  mov     r14, rax
0x180005f96  mov     r9, [rbx+90h]; unsigned __int16 *
0x180005f9d  test    r9, r9
0x180005fa0  jz      short loc_180005FB7
0x180005fa2  lea     r8, aCallerP; "(caller: %p) "
0x180005fa9  mov     rdx, rsi; unsigned __int16 *
0x180005fac  mov     rcx, rax; this
0x180005faf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005fb4  mov     r14, rax
0x180005fb7  call    cs:__imp_GetCurrentThreadId
0x180005fbd  lea     rcx, [rsp+278h+Buffer]
0x180005fc2  mov     [rsp+278h+var_240], rcx
0x180005fc7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180005fcb  mov     [rsp+278h+nSize], eax
0x180005fcf  mov     eax, [rbx+44h]
0x180005fd2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005fd6  mov     r9, rdi; unsigned __int16 *
0x180005fd9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005fe0  mov     rdx, rsi; unsigned __int16 *
0x180005fe3  mov     rcx, r14; this
0x180005fe6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005feb  cmp     [rbx+18h], r15
0x180005fef  jnz     short loc_180006001
0x180005ff1  cmp     [rbx+48h], r15
0x180005ff5  jnz     short loc_180006001
0x180005ff7  cmp     [rbx+30h], r15
0x180005ffb  jz      loc_180006091
0x180006001  lea     r8, asc_18008A2D8; "    "
0x180006008  mov     rdx, rsi; unsigned __int16 *
0x18000600b  mov     rcx, rax; this
0x18000600e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006013  mov     r9, [rbx+18h]; unsigned __int16 *
0x180006017  test    r9, r9
0x18000601a  jz      short loc_18000602E
0x18000601c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006023  mov     rdx, rsi; unsigned __int16 *
0x180006026  mov     rcx, rax; this
0x180006029  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000602e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180006032  test    r9, r9
0x180006035  jz      short loc_180006049
0x180006037  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000603e  mov     rdx, rsi; unsigned __int16 *
0x180006041  mov     rcx, rax; this
0x180006044  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006049  mov     rcx, [rbx+28h]
0x18000604d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006051  mov     rdx, rsi; unsigned __int16 *
0x180006054  test    rcx, rcx
0x180006057  jz      short loc_18000606F
0x180006059  mov     [rsp+278h+lpBuffer], rcx
0x18000605e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006065  mov     rcx, rax; this
0x180006068  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000606d  jmp     short loc_180006091
0x18000606f  mov     rcx, rax; this
0x180006072  test    r9, r9
0x180006075  jz      short loc_180006085
0x180006077  lea     r8, aHs; "[%hs]\n"
0x18000607e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006083  jmp     short loc_180006091
0x180006085  lea     r8, asc_18008A350; "\n"
0x18000608c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006091  xor     eax, eax
0x180006093  mov     rcx, [rsp+278h+var_38]
0x18000609b  xor     rcx, rsp; StackCookie
0x18000609e  call    __security_check_cookie
0x1800060a3  mov     rbx, [rsp+278h+arg_18]
0x1800060ab  add     rsp, 250h
0x1800060b2  pop     r15
0x1800060b4  pop     r14
0x1800060b6  pop     rdi
0x1800060b7  pop     rsi
0x1800060b8  pop     rbp
0x1800060b9  retn
```
