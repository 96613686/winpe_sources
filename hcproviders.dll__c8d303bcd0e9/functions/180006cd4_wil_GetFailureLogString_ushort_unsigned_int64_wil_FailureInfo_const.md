# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006cd4`
- end: `0x180006f97`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180005f74`
- `0x180007474`

## callees

- `0x180006cd4`
- `0x180007788`
- `0x180009e16`
- `0x180009e40`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006e8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006e8d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006e06`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006e06`

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
          v8 = (const char *)&qword_18000D7E0;
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
0x180006cd4  mov     [rsp+arg_18], rbx
0x180006cd9  push    rbp
0x180006cda  push    rsi
0x180006cdb  push    rdi
0x180006cdc  push    r14
0x180006cde  push    r15
0x180006ce0  sub     rsp, 250h
0x180006ce7  mov     rax, cs:__security_cookie
0x180006cee  xor     rax, rsp
0x180006cf1  mov     [rsp+278h+var_38], rax
0x180006cf9  xor     r15d, r15d
0x180006cfc  mov     rbx, r8
0x180006cff  mov     rsi, rdx
0x180006d02  mov     r14, rcx
0x180006d05  test    rdx, rdx
0x180006d08  jz      loc_180006F6D
0x180006d0e  test    rcx, rcx
0x180006d11  jz      loc_180006F6D
0x180006d17  mov     rax, cs:g_pfnResultLoggingCallback
0x180006d1e  mov     [rcx], r15w
0x180006d22  test    rax, rax
0x180006d25  jz      short loc_180006D48
0x180006d27  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006d2e  jz      short loc_180006D48
0x180006d30  mov     r8, rdx
0x180006d33  mov     rdx, rcx
0x180006d36  mov     rcx, rbx
0x180006d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d3e  cmp     [r14], r15w
0x180006d42  jnz     loc_180006F6D
0x180006d48  mov     ecx, [rbx]
0x180006d4a  mov     bpl, 8
0x180006d4d  test    ecx, ecx
0x180006d4f  jz      short loc_180006D9A
0x180006d51  sub     ecx, 1
0x180006d54  jz      short loc_180006D82
0x180006d56  sub     ecx, 1
0x180006d59  jz      short loc_180006D72
0x180006d5b  cmp     ecx, 1
0x180006d5e  jz      short loc_180006D69
0x180006d60  lea     rdi, qword_18000D7E0
0x180006d67  jmp     short loc_180006DA1
0x180006d69  lea     rdi, aFailfast; "FailFast"
0x180006d70  jmp     short loc_180006DA1
0x180006d72  lea     rax, aLoghr; "LogHr"
0x180006d79  lea     rdi, aLognt; "LogNt"
0x180006d80  jmp     short loc_180006D90
0x180006d82  lea     rax, aReturnhr; "ReturnHr"
0x180006d89  lea     rdi, aReturnnt; "ReturnNt"
0x180006d90  test    [rbx+4], bpl
0x180006d94  cmovz   rdi, rax
0x180006d98  jmp     short loc_180006DA1
0x180006d9a  lea     rdi, aException; "Exception"
0x180006da1  xor     edx, edx; Val
0x180006da3  lea     rcx, [rsp+278h+Buffer]; void *
0x180006da8  mov     r8d, 200h; Size
0x180006dae  call    memset_0
0x180006db3  test    [rbx+4], bpl
0x180006db7  jz      short loc_180006DDC
0x180006db9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180006dc0  mov     ebp, [rbx+0Ch]
0x180006dc3  test    rax, rax
0x180006dc6  jz      short loc_180006E12
0x180006dc8  mov     r8d, 100h
0x180006dce  lea     rdx, [rsp+278h+Buffer]
0x180006dd3  mov     ecx, ebp
0x180006dd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dda  jmp     short loc_180006E12
0x180006ddc  mov     ebp, [rbx+8]
0x180006ddf  lea     rax, [rsp+278h+Buffer]
0x180006de4  mov     [rsp+278h+Arguments], r15; Arguments
0x180006de9  mov     r8d, ebp; dwMessageId
0x180006dec  mov     [rsp+278h+nSize], 100h; nSize
0x180006df4  mov     r9d, 400h; dwLanguageId
0x180006dfa  xor     edx, edx; lpSource
0x180006dfc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006e01  mov     ecx, 1200h; dwFlags
0x180006e06  call    cs:__imp_FormatMessageW
0x180006e0d  nop     dword ptr [rax+rax+00h]
0x180006e12  mov     r9, [rbx+38h]; unsigned __int16 *
0x180006e16  lea     rsi, [r14+rsi*2]
0x180006e1a  mov     rax, [rbx+88h]
0x180006e21  mov     rdx, rsi; unsigned __int16 *
0x180006e24  mov     rcx, [rbx+80h]
0x180006e2b  test    r9, r9
0x180006e2e  jz      short loc_180006E52
0x180006e30  mov     [rsp+278h+Arguments], rax
0x180006e35  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006e3c  mov     eax, [rbx+40h]
0x180006e3f  mov     qword ptr [rsp+278h+nSize], rcx
0x180006e44  mov     rcx, r14; this
0x180006e47  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006e4b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006e50  jmp     short loc_180006E69
0x180006e52  mov     r9, rcx; unsigned __int16 *
0x180006e55  mov     [rsp+278h+lpBuffer], rax
0x180006e5a  mov     rcx, r14; this
0x180006e5d  lea     r8, aHsP; "%hs!%p: "
0x180006e64  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006e69  mov     r9, [rbx+90h]; unsigned __int16 *
0x180006e70  mov     r14, rax
0x180006e73  test    r9, r9
0x180006e76  jz      short loc_180006E8D
0x180006e78  lea     r8, aCallerP; "(caller: %p) "
0x180006e7f  mov     rdx, rsi; unsigned __int16 *
0x180006e82  mov     rcx, rax; this
0x180006e85  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006e8a  mov     r14, rax
0x180006e8d  call    cs:__imp_GetCurrentThreadId
0x180006e94  nop     dword ptr [rax+rax+00h]
0x180006e99  lea     rcx, [rsp+278h+Buffer]
0x180006e9e  mov     r9, rdi; unsigned __int16 *
0x180006ea1  mov     [rsp+278h+var_240], rcx
0x180006ea6  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006ead  mov     dword ptr [rsp+278h+Arguments], ebp
0x180006eb1  mov     rdx, rsi; unsigned __int16 *
0x180006eb4  mov     [rsp+278h+nSize], eax
0x180006eb8  mov     rcx, r14; this
0x180006ebb  mov     eax, [rbx+44h]
0x180006ebe  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006ec2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006ec7  cmp     [rbx+18h], r15
0x180006ecb  jnz     short loc_180006EDD
0x180006ecd  cmp     [rbx+48h], r15
0x180006ed1  jnz     short loc_180006EDD
0x180006ed3  cmp     [rbx+30h], r15
0x180006ed7  jz      loc_180006F6D
0x180006edd  lea     r8, asc_18000D8D0; "    "
0x180006ee4  mov     rdx, rsi; unsigned __int16 *
0x180006ee7  mov     rcx, rax; this
0x180006eea  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006eef  mov     r9, [rbx+18h]; unsigned __int16 *
0x180006ef3  test    r9, r9
0x180006ef6  jz      short loc_180006F0A
0x180006ef8  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006eff  mov     rdx, rsi; unsigned __int16 *
0x180006f02  mov     rcx, rax; this
0x180006f05  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006f0a  mov     r9, [rbx+48h]; unsigned __int16 *
0x180006f0e  test    r9, r9
0x180006f11  jz      short loc_180006F25
0x180006f13  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180006f1a  mov     rdx, rsi; unsigned __int16 *
0x180006f1d  mov     rcx, rax; this
0x180006f20  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006f25  mov     rcx, [rbx+28h]
0x180006f29  mov     rdx, rsi; unsigned __int16 *
0x180006f2c  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006f30  test    rcx, rcx
0x180006f33  jz      short loc_180006F4B
0x180006f35  mov     [rsp+278h+lpBuffer], rcx
0x180006f3a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006f41  mov     rcx, rax; this
0x180006f44  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006f49  jmp     short loc_180006F6D
0x180006f4b  mov     rcx, rax; this
0x180006f4e  test    r9, r9
0x180006f51  jz      short loc_180006F61
0x180006f53  lea     r8, aHs; "[%hs]\n"
0x180006f5a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006f5f  jmp     short loc_180006F6D
0x180006f61  lea     r8, asc_18000D948; "\n"
0x180006f68  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006f6d  xor     eax, eax
0x180006f6f  mov     rcx, [rsp+278h+var_38]
0x180006f77  xor     rcx, rsp; StackCookie
0x180006f7a  call    __security_check_cookie
0x180006f7f  mov     rbx, [rsp+278h+arg_18]
0x180006f87  add     rsp, 250h
0x180006f8e  pop     r15
0x180006f90  pop     r14
0x180006f92  pop     rdi
0x180006f93  pop     rsi
0x180006f94  pop     rbp
0x180006f95  retn
```
