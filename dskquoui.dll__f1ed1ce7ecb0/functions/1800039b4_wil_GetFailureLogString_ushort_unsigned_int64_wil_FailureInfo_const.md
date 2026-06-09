# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800039b4`
- end: `0x180003c6a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000261c`
- `0x18000288c`
- `0x180004314`
- `0x1800059f0`

## callees

- `0x180001510`
- `0x1800022b4`
- `0x1800039b4`
- `0x180004614`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003b67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003b67`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003ae6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003ae6`

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
          v7 = (const char *)&dword_18002179C;
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
0x1800039b4  mov     [rsp+arg_18], rbx
0x1800039b9  push    rbp
0x1800039ba  push    rsi
0x1800039bb  push    rdi
0x1800039bc  push    r14
0x1800039be  push    r15
0x1800039c0  sub     rsp, 250h
0x1800039c7  mov     rax, cs:__security_cookie
0x1800039ce  xor     rax, rsp
0x1800039d1  mov     [rsp+278h+var_38], rax
0x1800039d9  mov     rbx, r8
0x1800039dc  mov     rsi, rdx
0x1800039df  mov     r14, rcx
0x1800039e2  xor     r15d, r15d
0x1800039e5  test    rdx, rdx
0x1800039e8  jz      loc_180003C41
0x1800039ee  test    rcx, rcx
0x1800039f1  jz      loc_180003C41
0x1800039f7  mov     [rcx], r15w
0x1800039fb  mov     rax, cs:g_pfnResultLoggingCallback
0x180003a02  test    rax, rax
0x180003a05  jz      short loc_180003A28
0x180003a07  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003a0e  jz      short loc_180003A28
0x180003a10  mov     r8, rdx
0x180003a13  mov     rdx, rcx
0x180003a16  mov     rcx, rbx
0x180003a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a1e  cmp     [r14], r15w
0x180003a22  jnz     loc_180003C41
0x180003a28  mov     ecx, [rbx]
0x180003a2a  mov     bpl, 8
0x180003a2d  test    ecx, ecx
0x180003a2f  jz      short loc_180003A7A
0x180003a31  sub     ecx, 1
0x180003a34  jz      short loc_180003A62
0x180003a36  sub     ecx, 1
0x180003a39  jz      short loc_180003A52
0x180003a3b  cmp     ecx, 1
0x180003a3e  jz      short loc_180003A49
0x180003a40  lea     rdi, dword_18002179C
0x180003a47  jmp     short loc_180003A81
0x180003a49  lea     rdi, aFailfast; "FailFast"
0x180003a50  jmp     short loc_180003A81
0x180003a52  lea     rax, aLoghr; "LogHr"
0x180003a59  lea     rdi, aLognt; "LogNt"
0x180003a60  jmp     short loc_180003A70
0x180003a62  lea     rax, aReturnhr; "ReturnHr"
0x180003a69  lea     rdi, aReturnnt; "ReturnNt"
0x180003a70  test    [rbx+4], bpl
0x180003a74  cmovz   rdi, rax
0x180003a78  jmp     short loc_180003A81
0x180003a7a  lea     rdi, aException; "Exception"
0x180003a81  xor     edx, edx; Val
0x180003a83  mov     r8d, 200h; Size
0x180003a89  lea     rcx, [rsp+278h+Buffer]; void *
0x180003a8e  call    memset_0
0x180003a93  test    [rbx+4], bpl
0x180003a97  jz      short loc_180003ABC
0x180003a99  mov     ebp, [rbx+0Ch]
0x180003a9c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180003aa3  test    rax, rax
0x180003aa6  jz      short loc_180003AEC
0x180003aa8  mov     r8d, 100h
0x180003aae  lea     rdx, [rsp+278h+Buffer]
0x180003ab3  mov     ecx, ebp
0x180003ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003aba  jmp     short loc_180003AEC
0x180003abc  mov     ebp, [rbx+8]
0x180003abf  mov     [rsp+278h+Arguments], r15; Arguments
0x180003ac4  mov     [rsp+278h+nSize], 100h; nSize
0x180003acc  lea     rax, [rsp+278h+Buffer]
0x180003ad1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180003ad6  mov     r9d, 400h; dwLanguageId
0x180003adc  mov     r8d, ebp; dwMessageId
0x180003adf  xor     edx, edx; lpSource
0x180003ae1  mov     ecx, 1200h; dwFlags
0x180003ae6  call    cs:__imp_FormatMessageW
0x180003aec  lea     rsi, [r14+rsi*2]
0x180003af0  mov     r9, [rbx+38h]; unsigned __int16 *
0x180003af4  mov     rax, [rbx+88h]
0x180003afb  mov     rcx, [rbx+80h]
0x180003b02  mov     rdx, rsi; unsigned __int16 *
0x180003b05  test    r9, r9
0x180003b08  jz      short loc_180003B2C
0x180003b0a  mov     [rsp+278h+Arguments], rax
0x180003b0f  mov     qword ptr [rsp+278h+nSize], rcx
0x180003b14  mov     eax, [rbx+40h]
0x180003b17  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003b1b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180003b22  mov     rcx, r14; this
0x180003b25  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003b2a  jmp     short loc_180003B43
0x180003b2c  mov     [rsp+278h+lpBuffer], rax
0x180003b31  mov     r9, rcx; unsigned __int16 *
0x180003b34  lea     r8, aHsP; "%hs!%p: "
0x180003b3b  mov     rcx, r14; this
0x180003b3e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003b43  mov     r14, rax
0x180003b46  mov     r9, [rbx+90h]; unsigned __int16 *
0x180003b4d  test    r9, r9
0x180003b50  jz      short loc_180003B67
0x180003b52  lea     r8, aCallerP; "(caller: %p) "
0x180003b59  mov     rdx, rsi; unsigned __int16 *
0x180003b5c  mov     rcx, rax; this
0x180003b5f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003b64  mov     r14, rax
0x180003b67  call    cs:__imp_GetCurrentThreadId
0x180003b6d  lea     rcx, [rsp+278h+Buffer]
0x180003b72  mov     [rsp+278h+var_240], rcx
0x180003b77  mov     dword ptr [rsp+278h+Arguments], ebp
0x180003b7b  mov     [rsp+278h+nSize], eax
0x180003b7f  mov     eax, [rbx+44h]
0x180003b82  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003b86  mov     r9, rdi; unsigned __int16 *
0x180003b89  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180003b90  mov     rdx, rsi; unsigned __int16 *
0x180003b93  mov     rcx, r14; this
0x180003b96  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003b9b  cmp     [rbx+18h], r15
0x180003b9f  jnz     short loc_180003BB1
0x180003ba1  cmp     [rbx+48h], r15
0x180003ba5  jnz     short loc_180003BB1
0x180003ba7  cmp     [rbx+30h], r15
0x180003bab  jz      loc_180003C41
0x180003bb1  lea     r8, asc_1800218A0; "    "
0x180003bb8  mov     rdx, rsi; unsigned __int16 *
0x180003bbb  mov     rcx, rax; this
0x180003bbe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003bc3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180003bc7  test    r9, r9
0x180003bca  jz      short loc_180003BDE
0x180003bcc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180003bd3  mov     rdx, rsi; unsigned __int16 *
0x180003bd6  mov     rcx, rax; this
0x180003bd9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003bde  mov     r9, [rbx+48h]; unsigned __int16 *
0x180003be2  test    r9, r9
0x180003be5  jz      short loc_180003BF9
0x180003be7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180003bee  mov     rdx, rsi; unsigned __int16 *
0x180003bf1  mov     rcx, rax; this
0x180003bf4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003bf9  mov     rcx, [rbx+28h]
0x180003bfd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180003c01  mov     rdx, rsi; unsigned __int16 *
0x180003c04  test    rcx, rcx
0x180003c07  jz      short loc_180003C1F
0x180003c09  mov     [rsp+278h+lpBuffer], rcx
0x180003c0e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180003c15  mov     rcx, rax; this
0x180003c18  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003c1d  jmp     short loc_180003C41
0x180003c1f  mov     rcx, rax; this
0x180003c22  test    r9, r9
0x180003c25  jz      short loc_180003C35
0x180003c27  lea     r8, aHs; "[%hs]\n"
0x180003c2e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003c33  jmp     short loc_180003C41
0x180003c35  lea     r8, asc_180021918; "\n"
0x180003c3c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003c41  xor     eax, eax
0x180003c43  mov     rcx, [rsp+278h+var_38]
0x180003c4b  xor     rcx, rsp; StackCookie
0x180003c4e  call    __security_check_cookie
0x180003c53  mov     rbx, [rsp+278h+arg_18]
0x180003c5b  add     rsp, 250h
0x180003c62  pop     r15
0x180003c64  pop     r14
0x180003c66  pop     rdi
0x180003c67  pop     rsi
0x180003c68  pop     rbp
0x180003c69  retn
```
