# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180034b54`
- end: `0x180034e0a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18003264c`
- `0x1800328b4`
- `0x180035ed8`
- `0x18003b190`

## callees

- `0x18001e4c0`
- `0x18001efc4`
- `0x180034b54`
- `0x1800361d8`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034d07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034d07`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180034c86`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180034c86`

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
          v7 = (const char *)&qword_180057410;
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
0x180034b54  mov     [rsp+arg_18], rbx
0x180034b59  push    rbp
0x180034b5a  push    rsi
0x180034b5b  push    rdi
0x180034b5c  push    r14
0x180034b5e  push    r15
0x180034b60  sub     rsp, 250h
0x180034b67  mov     rax, cs:__security_cookie
0x180034b6e  xor     rax, rsp
0x180034b71  mov     [rsp+278h+var_38], rax
0x180034b79  mov     rbx, r8
0x180034b7c  mov     rsi, rdx
0x180034b7f  mov     r14, rcx
0x180034b82  xor     r15d, r15d
0x180034b85  test    rdx, rdx
0x180034b88  jz      loc_180034DE1
0x180034b8e  test    rcx, rcx
0x180034b91  jz      loc_180034DE1
0x180034b97  mov     [rcx], r15w
0x180034b9b  mov     rax, cs:g_pfnResultLoggingCallback
0x180034ba2  test    rax, rax
0x180034ba5  jz      short loc_180034BC8
0x180034ba7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180034bae  jz      short loc_180034BC8
0x180034bb0  mov     r8, rdx
0x180034bb3  mov     rdx, rcx
0x180034bb6  mov     rcx, rbx
0x180034bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034bbe  cmp     [r14], r15w
0x180034bc2  jnz     loc_180034DE1
0x180034bc8  mov     ecx, [rbx]
0x180034bca  mov     bpl, 8
0x180034bcd  test    ecx, ecx
0x180034bcf  jz      short loc_180034C1A
0x180034bd1  sub     ecx, 1
0x180034bd4  jz      short loc_180034C02
0x180034bd6  sub     ecx, 1
0x180034bd9  jz      short loc_180034BF2
0x180034bdb  cmp     ecx, 1
0x180034bde  jz      short loc_180034BE9
0x180034be0  lea     rdi, qword_180057410
0x180034be7  jmp     short loc_180034C21
0x180034be9  lea     rdi, aFailfast; "FailFast"
0x180034bf0  jmp     short loc_180034C21
0x180034bf2  lea     rax, aLoghr; "LogHr"
0x180034bf9  lea     rdi, aLognt; "LogNt"
0x180034c00  jmp     short loc_180034C10
0x180034c02  lea     rax, aReturnhr; "ReturnHr"
0x180034c09  lea     rdi, aReturnnt; "ReturnNt"
0x180034c10  test    [rbx+4], bpl
0x180034c14  cmovz   rdi, rax
0x180034c18  jmp     short loc_180034C21
0x180034c1a  lea     rdi, aException; "Exception"
0x180034c21  xor     edx, edx; Val
0x180034c23  mov     r8d, 200h; Size
0x180034c29  lea     rcx, [rsp+278h+Buffer]; void *
0x180034c2e  call    memset_0
0x180034c33  test    [rbx+4], bpl
0x180034c37  jz      short loc_180034C5C
0x180034c39  mov     ebp, [rbx+0Ch]
0x180034c3c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180034c43  test    rax, rax
0x180034c46  jz      short loc_180034C8C
0x180034c48  mov     r8d, 100h
0x180034c4e  lea     rdx, [rsp+278h+Buffer]
0x180034c53  mov     ecx, ebp
0x180034c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c5a  jmp     short loc_180034C8C
0x180034c5c  mov     ebp, [rbx+8]
0x180034c5f  mov     [rsp+278h+Arguments], r15; Arguments
0x180034c64  mov     [rsp+278h+nSize], 100h; nSize
0x180034c6c  lea     rax, [rsp+278h+Buffer]
0x180034c71  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180034c76  mov     r9d, 400h; dwLanguageId
0x180034c7c  mov     r8d, ebp; dwMessageId
0x180034c7f  xor     edx, edx; lpSource
0x180034c81  mov     ecx, 1200h; dwFlags
0x180034c86  call    cs:__imp_FormatMessageW
0x180034c8c  lea     rsi, [r14+rsi*2]
0x180034c90  mov     r9, [rbx+38h]; unsigned __int16 *
0x180034c94  mov     rax, [rbx+88h]
0x180034c9b  mov     rcx, [rbx+80h]
0x180034ca2  mov     rdx, rsi; unsigned __int16 *
0x180034ca5  test    r9, r9
0x180034ca8  jz      short loc_180034CCC
0x180034caa  mov     [rsp+278h+Arguments], rax
0x180034caf  mov     qword ptr [rsp+278h+nSize], rcx
0x180034cb4  mov     eax, [rbx+40h]
0x180034cb7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180034cbb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180034cc2  mov     rcx, r14; this
0x180034cc5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180034cca  jmp     short loc_180034CE3
0x180034ccc  mov     [rsp+278h+lpBuffer], rax
0x180034cd1  mov     r9, rcx; unsigned __int16 *
0x180034cd4  lea     r8, aHsP; "%hs!%p: "
0x180034cdb  mov     rcx, r14; this
0x180034cde  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180034ce3  mov     r14, rax
0x180034ce6  mov     r9, [rbx+90h]; unsigned __int16 *
0x180034ced  test    r9, r9
0x180034cf0  jz      short loc_180034D07
0x180034cf2  lea     r8, aCallerP; "(caller: %p) "
0x180034cf9  mov     rdx, rsi; unsigned __int16 *
0x180034cfc  mov     rcx, rax; this
0x180034cff  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180034d04  mov     r14, rax
0x180034d07  call    cs:__imp_GetCurrentThreadId
0x180034d0d  lea     rcx, [rsp+278h+Buffer]
0x180034d12  mov     [rsp+278h+var_240], rcx
0x180034d17  mov     dword ptr [rsp+278h+Arguments], ebp
0x180034d1b  mov     [rsp+278h+nSize], eax
0x180034d1f  mov     eax, [rbx+44h]
0x180034d22  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180034d26  mov     r9, rdi; unsigned __int16 *
0x180034d29  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180034d30  mov     rdx, rsi; unsigned __int16 *
0x180034d33  mov     rcx, r14; this
0x180034d36  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180034d3b  cmp     [rbx+18h], r15
0x180034d3f  jnz     short loc_180034D51
0x180034d41  cmp     [rbx+48h], r15
0x180034d45  jnz     short loc_180034D51
0x180034d47  cmp     [rbx+30h], r15
0x180034d4b  jz      loc_180034DE1
0x180034d51  lea     r8, asc_180057518; "    "
0x180034d58  mov     rdx, rsi; unsigned __int16 *
0x180034d5b  mov     rcx, rax; this
0x180034d5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180034d63  mov     r9, [rbx+18h]; unsigned __int16 *
0x180034d67  test    r9, r9
0x180034d6a  jz      short loc_180034D7E
0x180034d6c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180034d73  mov     rdx, rsi; unsigned __int16 *
0x180034d76  mov     rcx, rax; this
0x180034d79  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180034d7e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180034d82  test    r9, r9
0x180034d85  jz      short loc_180034D99
0x180034d87  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180034d8e  mov     rdx, rsi; unsigned __int16 *
0x180034d91  mov     rcx, rax; this
0x180034d94  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180034d99  mov     rcx, [rbx+28h]
0x180034d9d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180034da1  mov     rdx, rsi; unsigned __int16 *
0x180034da4  test    rcx, rcx
0x180034da7  jz      short loc_180034DBF
0x180034da9  mov     [rsp+278h+lpBuffer], rcx
0x180034dae  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180034db5  mov     rcx, rax; this
0x180034db8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180034dbd  jmp     short loc_180034DE1
0x180034dbf  mov     rcx, rax; this
0x180034dc2  test    r9, r9
0x180034dc5  jz      short loc_180034DD5
0x180034dc7  lea     r8, aHs; "[%hs]\n"
0x180034dce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180034dd3  jmp     short loc_180034DE1
0x180034dd5  lea     r8, asc_180057590; "\n"
0x180034ddc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180034de1  xor     eax, eax
0x180034de3  mov     rcx, [rsp+278h+var_38]
0x180034deb  xor     rcx, rsp; StackCookie
0x180034dee  call    __security_check_cookie
0x180034df3  mov     rbx, [rsp+278h+arg_18]
0x180034dfb  add     rsp, 250h
0x180034e02  pop     r15
0x180034e04  pop     r14
0x180034e06  pop     rdi
0x180034e07  pop     rsi
0x180034e08  pop     rbp
0x180034e09  retn
```
