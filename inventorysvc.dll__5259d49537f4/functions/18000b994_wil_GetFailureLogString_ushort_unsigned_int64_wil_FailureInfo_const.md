# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000b994`
- end: `0x18000bc4a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x18000604c`
- `0x1800062b4`
- `0x180006568`
- `0x18000cb14`
- `0x1800113b0`

## callees

- `0x180002bf0`
- `0x1800038b8`
- `0x18000b994`
- `0x18000ce14`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bb47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bb47`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000bac6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000bac6`

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
          v7 = (const char *)&word_1800D7582;
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
0x18000b994  mov     [rsp+arg_18], rbx
0x18000b999  push    rbp
0x18000b99a  push    rsi
0x18000b99b  push    rdi
0x18000b99c  push    r14
0x18000b99e  push    r15
0x18000b9a0  sub     rsp, 250h
0x18000b9a7  mov     rax, cs:__security_cookie
0x18000b9ae  xor     rax, rsp
0x18000b9b1  mov     [rsp+278h+var_38], rax
0x18000b9b9  mov     rbx, r8
0x18000b9bc  mov     rsi, rdx
0x18000b9bf  mov     r14, rcx
0x18000b9c2  xor     r15d, r15d
0x18000b9c5  test    rdx, rdx
0x18000b9c8  jz      loc_18000BC21
0x18000b9ce  test    rcx, rcx
0x18000b9d1  jz      loc_18000BC21
0x18000b9d7  mov     [rcx], r15w
0x18000b9db  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b9e2  test    rax, rax
0x18000b9e5  jz      short loc_18000BA08
0x18000b9e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000b9ee  jz      short loc_18000BA08
0x18000b9f0  mov     r8, rdx
0x18000b9f3  mov     rdx, rcx
0x18000b9f6  mov     rcx, rbx
0x18000b9f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9fe  cmp     [r14], r15w
0x18000ba02  jnz     loc_18000BC21
0x18000ba08  mov     ecx, [rbx]
0x18000ba0a  mov     bpl, 8
0x18000ba0d  test    ecx, ecx
0x18000ba0f  jz      short loc_18000BA5A
0x18000ba11  sub     ecx, 1
0x18000ba14  jz      short loc_18000BA42
0x18000ba16  sub     ecx, 1
0x18000ba19  jz      short loc_18000BA32
0x18000ba1b  cmp     ecx, 1
0x18000ba1e  jz      short loc_18000BA29
0x18000ba20  lea     rdi, word_1800D7582
0x18000ba27  jmp     short loc_18000BA61
0x18000ba29  lea     rdi, aFailfast; "FailFast"
0x18000ba30  jmp     short loc_18000BA61
0x18000ba32  lea     rax, aLoghr; "LogHr"
0x18000ba39  lea     rdi, aLognt; "LogNt"
0x18000ba40  jmp     short loc_18000BA50
0x18000ba42  lea     rax, aReturnhr; "ReturnHr"
0x18000ba49  lea     rdi, aReturnnt; "ReturnNt"
0x18000ba50  test    [rbx+4], bpl
0x18000ba54  cmovz   rdi, rax
0x18000ba58  jmp     short loc_18000BA61
0x18000ba5a  lea     rdi, aException; "Exception"
0x18000ba61  xor     edx, edx; Val
0x18000ba63  mov     r8d, 200h; Size
0x18000ba69  lea     rcx, [rsp+278h+Buffer]; void *
0x18000ba6e  call    memset_0
0x18000ba73  test    [rbx+4], bpl
0x18000ba77  jz      short loc_18000BA9C
0x18000ba79  mov     ebp, [rbx+0Ch]
0x18000ba7c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000ba83  test    rax, rax
0x18000ba86  jz      short loc_18000BACC
0x18000ba88  mov     r8d, 100h
0x18000ba8e  lea     rdx, [rsp+278h+Buffer]
0x18000ba93  mov     ecx, ebp
0x18000ba95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba9a  jmp     short loc_18000BACC
0x18000ba9c  mov     ebp, [rbx+8]
0x18000ba9f  mov     [rsp+278h+Arguments], r15; Arguments
0x18000baa4  mov     [rsp+278h+nSize], 100h; nSize
0x18000baac  lea     rax, [rsp+278h+Buffer]
0x18000bab1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000bab6  mov     r9d, 400h; dwLanguageId
0x18000babc  mov     r8d, ebp; dwMessageId
0x18000babf  xor     edx, edx; lpSource
0x18000bac1  mov     ecx, 1200h; dwFlags
0x18000bac6  call    cs:__imp_FormatMessageW
0x18000bacc  lea     rsi, [r14+rsi*2]
0x18000bad0  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000bad4  mov     rax, [rbx+88h]
0x18000badb  mov     rcx, [rbx+80h]
0x18000bae2  mov     rdx, rsi; unsigned __int16 *
0x18000bae5  test    r9, r9
0x18000bae8  jz      short loc_18000BB0C
0x18000baea  mov     [rsp+278h+Arguments], rax
0x18000baef  mov     qword ptr [rsp+278h+nSize], rcx
0x18000baf4  mov     eax, [rbx+40h]
0x18000baf7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000bafb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000bb02  mov     rcx, r14; this
0x18000bb05  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bb0a  jmp     short loc_18000BB23
0x18000bb0c  mov     [rsp+278h+lpBuffer], rax
0x18000bb11  mov     r9, rcx; unsigned __int16 *
0x18000bb14  lea     r8, aHsP; "%hs!%p: "
0x18000bb1b  mov     rcx, r14; this
0x18000bb1e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bb23  mov     r14, rax
0x18000bb26  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000bb2d  test    r9, r9
0x18000bb30  jz      short loc_18000BB47
0x18000bb32  lea     r8, aCallerP; "(caller: %p) "
0x18000bb39  mov     rdx, rsi; unsigned __int16 *
0x18000bb3c  mov     rcx, rax; this
0x18000bb3f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bb44  mov     r14, rax
0x18000bb47  call    cs:__imp_GetCurrentThreadId
0x18000bb4d  lea     rcx, [rsp+278h+Buffer]
0x18000bb52  mov     [rsp+278h+var_240], rcx
0x18000bb57  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000bb5b  mov     [rsp+278h+nSize], eax
0x18000bb5f  mov     eax, [rbx+44h]
0x18000bb62  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000bb66  mov     r9, rdi; unsigned __int16 *
0x18000bb69  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000bb70  mov     rdx, rsi; unsigned __int16 *
0x18000bb73  mov     rcx, r14; this
0x18000bb76  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bb7b  cmp     [rbx+18h], r15
0x18000bb7f  jnz     short loc_18000BB91
0x18000bb81  cmp     [rbx+48h], r15
0x18000bb85  jnz     short loc_18000BB91
0x18000bb87  cmp     [rbx+30h], r15
0x18000bb8b  jz      loc_18000BC21
0x18000bb91  lea     r8, asc_1800D76A0; "    "
0x18000bb98  mov     rdx, rsi; unsigned __int16 *
0x18000bb9b  mov     rcx, rax; this
0x18000bb9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bba3  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000bba7  test    r9, r9
0x18000bbaa  jz      short loc_18000BBBE
0x18000bbac  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000bbb3  mov     rdx, rsi; unsigned __int16 *
0x18000bbb6  mov     rcx, rax; this
0x18000bbb9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bbbe  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000bbc2  test    r9, r9
0x18000bbc5  jz      short loc_18000BBD9
0x18000bbc7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000bbce  mov     rdx, rsi; unsigned __int16 *
0x18000bbd1  mov     rcx, rax; this
0x18000bbd4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bbd9  mov     rcx, [rbx+28h]
0x18000bbdd  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000bbe1  mov     rdx, rsi; unsigned __int16 *
0x18000bbe4  test    rcx, rcx
0x18000bbe7  jz      short loc_18000BBFF
0x18000bbe9  mov     [rsp+278h+lpBuffer], rcx
0x18000bbee  lea     r8, aHsHs_0; "[%hs(%hs)]\n"
0x18000bbf5  mov     rcx, rax; this
0x18000bbf8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bbfd  jmp     short loc_18000BC21
0x18000bbff  mov     rcx, rax; this
0x18000bc02  test    r9, r9
0x18000bc05  jz      short loc_18000BC15
0x18000bc07  lea     r8, aHs_0; "[%hs]\n"
0x18000bc0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bc13  jmp     short loc_18000BC21
0x18000bc15  lea     r8, asc_1800D7718; "\n"
0x18000bc1c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bc21  xor     eax, eax
0x18000bc23  mov     rcx, [rsp+278h+var_38]
0x18000bc2b  xor     rcx, rsp; StackCookie
0x18000bc2e  call    __security_check_cookie
0x18000bc33  mov     rbx, [rsp+278h+arg_18]
0x18000bc3b  add     rsp, 250h
0x18000bc42  pop     r15
0x18000bc44  pop     r14
0x18000bc46  pop     rdi
0x18000bc47  pop     rsi
0x18000bc48  pop     rbp
0x18000bc49  retn
```
