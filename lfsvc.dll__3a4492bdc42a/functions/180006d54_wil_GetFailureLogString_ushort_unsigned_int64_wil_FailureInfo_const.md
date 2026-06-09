# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006d54`
- end: `0x18000700a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800053b4`
- `0x180007688`
- `0x18000a1a0`

## callees

- `0x180004310`
- `0x180004d48`
- `0x180006d54`
- `0x180007b60`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f07`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006e86`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006e86`

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
          v7 = (const char *)&word_18000DA02;
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
0x180006d54  mov     [rsp+arg_18], rbx
0x180006d59  push    rbp
0x180006d5a  push    rsi
0x180006d5b  push    rdi
0x180006d5c  push    r14
0x180006d5e  push    r15
0x180006d60  sub     rsp, 250h
0x180006d67  mov     rax, cs:__security_cookie
0x180006d6e  xor     rax, rsp
0x180006d71  mov     [rsp+278h+var_38], rax
0x180006d79  mov     rbx, r8
0x180006d7c  mov     rsi, rdx
0x180006d7f  mov     r14, rcx
0x180006d82  xor     r15d, r15d
0x180006d85  test    rdx, rdx
0x180006d88  jz      loc_180006FE1
0x180006d8e  test    rcx, rcx
0x180006d91  jz      loc_180006FE1
0x180006d97  mov     [rcx], r15w
0x180006d9b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006da2  test    rax, rax
0x180006da5  jz      short loc_180006DC8
0x180006da7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006dae  jz      short loc_180006DC8
0x180006db0  mov     r8, rdx
0x180006db3  mov     rdx, rcx
0x180006db6  mov     rcx, rbx
0x180006db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dbe  cmp     [r14], r15w
0x180006dc2  jnz     loc_180006FE1
0x180006dc8  mov     ecx, [rbx]
0x180006dca  mov     bpl, 8
0x180006dcd  test    ecx, ecx
0x180006dcf  jz      short loc_180006E1A
0x180006dd1  sub     ecx, 1
0x180006dd4  jz      short loc_180006E02
0x180006dd6  sub     ecx, 1
0x180006dd9  jz      short loc_180006DF2
0x180006ddb  cmp     ecx, 1
0x180006dde  jz      short loc_180006DE9
0x180006de0  lea     rdi, word_18000DA02
0x180006de7  jmp     short loc_180006E21
0x180006de9  lea     rdi, aFailfast; "FailFast"
0x180006df0  jmp     short loc_180006E21
0x180006df2  lea     rax, aLoghr; "LogHr"
0x180006df9  lea     rdi, aLognt; "LogNt"
0x180006e00  jmp     short loc_180006E10
0x180006e02  lea     rax, aReturnhr; "ReturnHr"
0x180006e09  lea     rdi, aReturnnt; "ReturnNt"
0x180006e10  test    [rbx+4], bpl
0x180006e14  cmovz   rdi, rax
0x180006e18  jmp     short loc_180006E21
0x180006e1a  lea     rdi, aException; "Exception"
0x180006e21  xor     edx, edx; Val
0x180006e23  mov     r8d, 200h; Size
0x180006e29  lea     rcx, [rsp+278h+Buffer]; void *
0x180006e2e  call    memset_0
0x180006e33  test    [rbx+4], bpl
0x180006e37  jz      short loc_180006E5C
0x180006e39  mov     ebp, [rbx+0Ch]
0x180006e3c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180006e43  test    rax, rax
0x180006e46  jz      short loc_180006E8C
0x180006e48  mov     r8d, 100h
0x180006e4e  lea     rdx, [rsp+278h+Buffer]
0x180006e53  mov     ecx, ebp
0x180006e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e5a  jmp     short loc_180006E8C
0x180006e5c  mov     ebp, [rbx+8]
0x180006e5f  mov     [rsp+278h+Arguments], r15; Arguments
0x180006e64  mov     [rsp+278h+nSize], 100h; nSize
0x180006e6c  lea     rax, [rsp+278h+Buffer]
0x180006e71  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006e76  mov     r9d, 400h; dwLanguageId
0x180006e7c  mov     r8d, ebp; dwMessageId
0x180006e7f  xor     edx, edx; lpSource
0x180006e81  mov     ecx, 1200h; dwFlags
0x180006e86  call    cs:__imp_FormatMessageW
0x180006e8c  lea     rsi, [r14+rsi*2]
0x180006e90  mov     r9, [rbx+38h]; unsigned __int16 *
0x180006e94  mov     rax, [rbx+88h]
0x180006e9b  mov     rcx, [rbx+80h]
0x180006ea2  mov     rdx, rsi; unsigned __int16 *
0x180006ea5  test    r9, r9
0x180006ea8  jz      short loc_180006ECC
0x180006eaa  mov     [rsp+278h+Arguments], rax
0x180006eaf  mov     qword ptr [rsp+278h+nSize], rcx
0x180006eb4  mov     eax, [rbx+40h]
0x180006eb7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006ebb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006ec2  mov     rcx, r14; this
0x180006ec5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006eca  jmp     short loc_180006EE3
0x180006ecc  mov     [rsp+278h+lpBuffer], rax
0x180006ed1  mov     r9, rcx; unsigned __int16 *
0x180006ed4  lea     r8, aHsP; "%hs!%p: "
0x180006edb  mov     rcx, r14; this
0x180006ede  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006ee3  mov     r14, rax
0x180006ee6  mov     r9, [rbx+90h]; unsigned __int16 *
0x180006eed  test    r9, r9
0x180006ef0  jz      short loc_180006F07
0x180006ef2  lea     r8, aCallerP; "(caller: %p) "
0x180006ef9  mov     rdx, rsi; unsigned __int16 *
0x180006efc  mov     rcx, rax; this
0x180006eff  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006f04  mov     r14, rax
0x180006f07  call    cs:__imp_GetCurrentThreadId
0x180006f0d  lea     rcx, [rsp+278h+Buffer]
0x180006f12  mov     [rsp+278h+var_240], rcx
0x180006f17  mov     dword ptr [rsp+278h+Arguments], ebp
0x180006f1b  mov     [rsp+278h+nSize], eax
0x180006f1f  mov     eax, [rbx+44h]
0x180006f22  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006f26  mov     r9, rdi; unsigned __int16 *
0x180006f29  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006f30  mov     rdx, rsi; unsigned __int16 *
0x180006f33  mov     rcx, r14; this
0x180006f36  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006f3b  cmp     [rbx+18h], r15
0x180006f3f  jnz     short loc_180006F51
0x180006f41  cmp     [rbx+48h], r15
0x180006f45  jnz     short loc_180006F51
0x180006f47  cmp     [rbx+30h], r15
0x180006f4b  jz      loc_180006FE1
0x180006f51  lea     r8, asc_18000DAF0; "    "
0x180006f58  mov     rdx, rsi; unsigned __int16 *
0x180006f5b  mov     rcx, rax; this
0x180006f5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006f63  mov     r9, [rbx+18h]; unsigned __int16 *
0x180006f67  test    r9, r9
0x180006f6a  jz      short loc_180006F7E
0x180006f6c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006f73  mov     rdx, rsi; unsigned __int16 *
0x180006f76  mov     rcx, rax; this
0x180006f79  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006f7e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180006f82  test    r9, r9
0x180006f85  jz      short loc_180006F99
0x180006f87  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180006f8e  mov     rdx, rsi; unsigned __int16 *
0x180006f91  mov     rcx, rax; this
0x180006f94  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006f99  mov     rcx, [rbx+28h]
0x180006f9d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006fa1  mov     rdx, rsi; unsigned __int16 *
0x180006fa4  test    rcx, rcx
0x180006fa7  jz      short loc_180006FBF
0x180006fa9  mov     [rsp+278h+lpBuffer], rcx
0x180006fae  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006fb5  mov     rcx, rax; this
0x180006fb8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006fbd  jmp     short loc_180006FE1
0x180006fbf  mov     rcx, rax; this
0x180006fc2  test    r9, r9
0x180006fc5  jz      short loc_180006FD5
0x180006fc7  lea     r8, aHs; "[%hs]\n"
0x180006fce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006fd3  jmp     short loc_180006FE1
0x180006fd5  lea     r8, asc_18000DB68; "\n"
0x180006fdc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006fe1  xor     eax, eax
0x180006fe3  mov     rcx, [rsp+278h+var_38]
0x180006feb  xor     rcx, rsp; StackCookie
0x180006fee  call    __security_check_cookie
0x180006ff3  mov     rbx, [rsp+278h+arg_18]
0x180006ffb  add     rsp, 250h
0x180007002  pop     r15
0x180007004  pop     r14
0x180007006  pop     rdi
0x180007007  pop     rsi
0x180007008  pop     rbp
0x180007009  retn
```
