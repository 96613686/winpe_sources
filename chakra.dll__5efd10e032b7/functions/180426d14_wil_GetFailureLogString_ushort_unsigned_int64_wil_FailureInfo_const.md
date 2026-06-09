# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180426d14`
- end: `0x180426fee`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `730`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180425180`
- `0x180428050`
- `0x18042b740`

## callees

- `0x180426d14`
- `0x180428384`
- `0x1805a9c5a`
- `0x1805a9e80`
- `0x1805cd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180426ee4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180426ee4`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180426e5d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180426e5d`

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
  LPWSTR lpBuffer; // [rsp+20h] [rbp-268h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-268h]
  DWORD nSize[2]; // [rsp+28h] [rbp-260h]
  va_list *Arguments; // [rsp+30h] [rbp-258h]
  WCHAR Buffer[256]; // [rsp+50h] [rbp-238h] BYREF

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
          v7 = (const char *)&word_180629442;
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
                          Buffer,
                          -2);
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
0x180426d14  mov     r11, rsp
0x180426d17  mov     [r11+18h], r8
0x180426d1b  mov     [r11+10h], rdx
0x180426d1f  mov     [r11+8], rcx
0x180426d23  push    rbp
0x180426d24  push    rsi
0x180426d25  push    rdi
0x180426d26  push    r14
0x180426d28  push    r15
0x180426d2a  sub     rsp, 260h
0x180426d31  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x180426d3a  mov     [r11+20h], rbx
0x180426d3e  mov     rax, cs:__security_cookie
0x180426d45  xor     rax, rsp
0x180426d48  mov     [rsp+288h+var_38], rax
0x180426d50  mov     rbx, r8
0x180426d53  mov     r14, rcx
0x180426d56  mov     rsi, rdx
0x180426d59  xor     r15d, r15d
0x180426d5c  test    rdx, rdx
0x180426d5f  jz      loc_180426FC4
0x180426d65  test    rcx, rcx
0x180426d68  jz      loc_180426FC4
0x180426d6e  mov     [rcx], r15w
0x180426d72  mov     rax, cs:g_pfnResultLoggingCallback
0x180426d79  test    rax, rax
0x180426d7c  jz      short loc_180426D9F
0x180426d7e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180426d85  jz      short loc_180426D9F
0x180426d87  mov     r8, rdx
0x180426d8a  mov     rdx, rcx
0x180426d8d  mov     rcx, rbx
0x180426d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180426d95  cmp     [r14], r15w
0x180426d99  jnz     loc_180426FC4
0x180426d9f  mov     ecx, [rbx]
0x180426da1  mov     bpl, 8
0x180426da4  test    ecx, ecx
0x180426da6  jz      short loc_180426DF1
0x180426da8  sub     ecx, 1
0x180426dab  jz      short loc_180426DD9
0x180426dad  sub     ecx, 1
0x180426db0  jz      short loc_180426DC9
0x180426db2  cmp     ecx, 1
0x180426db5  jz      short loc_180426DC0
0x180426db7  lea     rdi, word_180629442
0x180426dbe  jmp     short loc_180426DF8
0x180426dc0  lea     rdi, aFailfast; "FailFast"
0x180426dc7  jmp     short loc_180426DF8
0x180426dc9  lea     rax, aLoghr; "LogHr"
0x180426dd0  lea     rdi, aLognt; "LogNt"
0x180426dd7  jmp     short loc_180426DE7
0x180426dd9  lea     rax, aReturnhr; "ReturnHr"
0x180426de0  lea     rdi, aReturnnt; "ReturnNt"
0x180426de7  test    [rbx+4], bpl
0x180426deb  cmovz   rdi, rax
0x180426def  jmp     short loc_180426DF8
0x180426df1  lea     rdi, aException_0; "Exception"
0x180426df8  xor     edx, edx; Val
0x180426dfa  mov     r8d, 200h; Size
0x180426e00  lea     rcx, [rsp+288h+Buffer]; void *
0x180426e05  call    memset_0
0x180426e0a  test    [rbx+4], bpl
0x180426e0e  jz      short loc_180426E33
0x180426e10  mov     ebp, [rbx+0Ch]
0x180426e13  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180426e1a  test    rax, rax
0x180426e1d  jz      short loc_180426E69
0x180426e1f  mov     r8d, 100h
0x180426e25  lea     rdx, [rsp+288h+Buffer]
0x180426e2a  mov     ecx, ebp
0x180426e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180426e31  jmp     short loc_180426E69
0x180426e33  mov     ebp, [rbx+8]
0x180426e36  mov     [rsp+288h+Arguments], r15; Arguments
0x180426e3b  mov     [rsp+288h+nSize], 100h; nSize
0x180426e43  lea     rax, [rsp+288h+Buffer]
0x180426e48  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x180426e4d  mov     r9d, 400h; dwLanguageId
0x180426e53  mov     r8d, ebp; dwMessageId
0x180426e56  xor     edx, edx; lpSource
0x180426e58  mov     ecx, 1200h; dwFlags
0x180426e5d  call    cs:__imp_FormatMessageW
0x180426e64  nop     dword ptr [rax+rax+00h]
0x180426e69  lea     rsi, [r14+rsi*2]
0x180426e6d  mov     r9, [rbx+38h]; unsigned __int16 *
0x180426e71  mov     rax, [rbx+88h]
0x180426e78  mov     rcx, [rbx+80h]
0x180426e7f  mov     rdx, rsi; unsigned __int16 *
0x180426e82  test    r9, r9
0x180426e85  jz      short loc_180426EA9
0x180426e87  mov     [rsp+288h+Arguments], rax
0x180426e8c  mov     qword ptr [rsp+288h+nSize], rcx
0x180426e91  mov     eax, [rbx+40h]
0x180426e94  mov     dword ptr [rsp+288h+lpBuffer], eax
0x180426e98  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180426e9f  mov     rcx, r14; this
0x180426ea2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180426ea7  jmp     short loc_180426EC0
0x180426ea9  mov     [rsp+288h+lpBuffer], rax
0x180426eae  mov     r9, rcx; unsigned __int16 *
0x180426eb1  lea     r8, aHsP; "%hs!%p: "
0x180426eb8  mov     rcx, r14; this
0x180426ebb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180426ec0  mov     r14, rax
0x180426ec3  mov     r9, [rbx+90h]; unsigned __int16 *
0x180426eca  test    r9, r9
0x180426ecd  jz      short loc_180426EE4
0x180426ecf  lea     r8, aCallerP; "(caller: %p) "
0x180426ed6  mov     rdx, rsi; unsigned __int16 *
0x180426ed9  mov     rcx, rax; this
0x180426edc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180426ee1  mov     r14, rax
0x180426ee4  call    cs:__imp_GetCurrentThreadId
0x180426eeb  nop     dword ptr [rax+rax+00h]
0x180426ef0  lea     rcx, [rsp+288h+Buffer]
0x180426ef5  mov     [rsp+288h+var_250], rcx
0x180426efa  mov     dword ptr [rsp+288h+Arguments], ebp
0x180426efe  mov     [rsp+288h+nSize], eax
0x180426f02  mov     eax, [rbx+44h]
0x180426f05  mov     dword ptr [rsp+288h+lpBuffer], eax
0x180426f09  mov     r9, rdi; unsigned __int16 *
0x180426f0c  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180426f13  mov     rdx, rsi; unsigned __int16 *
0x180426f16  mov     rcx, r14; this
0x180426f19  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180426f1e  cmp     [rbx+18h], r15
0x180426f22  jnz     short loc_180426F34
0x180426f24  cmp     [rbx+48h], r15
0x180426f28  jnz     short loc_180426F34
0x180426f2a  cmp     [rbx+30h], r15
0x180426f2e  jz      loc_180426FC4
0x180426f34  lea     r8, asc_1806844F8; "    "
0x180426f3b  mov     rdx, rsi; unsigned __int16 *
0x180426f3e  mov     rcx, rax; this
0x180426f41  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180426f46  mov     r9, [rbx+18h]; unsigned __int16 *
0x180426f4a  test    r9, r9
0x180426f4d  jz      short loc_180426F61
0x180426f4f  lea     r8, aMsgWs; "Msg:[%ws] "
0x180426f56  mov     rdx, rsi; unsigned __int16 *
0x180426f59  mov     rcx, rax; this
0x180426f5c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180426f61  mov     r9, [rbx+48h]; unsigned __int16 *
0x180426f65  test    r9, r9
0x180426f68  jz      short loc_180426F7C
0x180426f6a  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180426f71  mov     rdx, rsi; unsigned __int16 *
0x180426f74  mov     rcx, rax; this
0x180426f77  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180426f7c  mov     rcx, [rbx+28h]
0x180426f80  mov     r9, [rbx+30h]; unsigned __int16 *
0x180426f84  mov     rdx, rsi; unsigned __int16 *
0x180426f87  test    rcx, rcx
0x180426f8a  jz      short loc_180426FA2
0x180426f8c  mov     [rsp+288h+lpBuffer], rcx
0x180426f91  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180426f98  mov     rcx, rax; this
0x180426f9b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180426fa0  jmp     short loc_180426FC4
0x180426fa2  mov     rcx, rax; this
0x180426fa5  test    r9, r9
0x180426fa8  jz      short loc_180426FB8
0x180426faa  lea     r8, aHs; "[%hs]\n"
0x180426fb1  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180426fb6  jmp     short loc_180426FC4
0x180426fb8  lea     r8, asc_180684570; "\n"
0x180426fbf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180426fc4  xor     eax, eax
0x180426fc6  mov     rcx, [rsp+288h+var_38]
0x180426fce  xor     rcx, rsp; StackCookie
0x180426fd1  call    __security_check_cookie
0x180426fd6  mov     rbx, [rsp+288h+arg_18]
0x180426fde  add     rsp, 260h
0x180426fe5  pop     r15
0x180426fe7  pop     r14
0x180426fe9  pop     rdi
0x180426fea  pop     rsi
0x180426feb  pop     rbp
0x180426fec  retn
```
