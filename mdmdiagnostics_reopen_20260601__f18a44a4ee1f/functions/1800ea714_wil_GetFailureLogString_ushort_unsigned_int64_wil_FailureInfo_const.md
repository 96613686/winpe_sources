# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800ea714`
- end: `0x1800ea9d7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800e4d6c`
- `0x1800eb4ac`
- `0x1800ebbf4`
- `0x1800f5500`

## callees

- `0x180019080`
- `0x18001a054`
- `0x1800ea714`
- `0x1800eb7c0`
- `0x180193010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ea8cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ea8cd`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800ea846`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800ea846`

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
          v7 = (const char *)&word_1801BBB0E;
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
0x1800ea714  mov     [rsp+arg_18], rbx
0x1800ea719  push    rbp
0x1800ea71a  push    rsi
0x1800ea71b  push    rdi
0x1800ea71c  push    r14
0x1800ea71e  push    r15
0x1800ea720  sub     rsp, 250h
0x1800ea727  mov     rax, cs:__security_cookie
0x1800ea72e  xor     rax, rsp
0x1800ea731  mov     [rsp+278h+var_38], rax
0x1800ea739  mov     rbx, r8
0x1800ea73c  mov     rsi, rdx
0x1800ea73f  mov     r14, rcx
0x1800ea742  xor     r15d, r15d
0x1800ea745  test    rdx, rdx
0x1800ea748  jz      loc_1800EA9AD
0x1800ea74e  test    rcx, rcx
0x1800ea751  jz      loc_1800EA9AD
0x1800ea757  mov     [rcx], r15w
0x1800ea75b  mov     rax, cs:g_pfnResultLoggingCallback
0x1800ea762  test    rax, rax
0x1800ea765  jz      short loc_1800EA788
0x1800ea767  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800ea76e  jz      short loc_1800EA788
0x1800ea770  mov     r8, rdx
0x1800ea773  mov     rdx, rcx
0x1800ea776  mov     rcx, rbx
0x1800ea779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea77e  cmp     [r14], r15w
0x1800ea782  jnz     loc_1800EA9AD
0x1800ea788  mov     ecx, [rbx]
0x1800ea78a  mov     bpl, 8
0x1800ea78d  test    ecx, ecx
0x1800ea78f  jz      short loc_1800EA7DA
0x1800ea791  sub     ecx, 1
0x1800ea794  jz      short loc_1800EA7C2
0x1800ea796  sub     ecx, 1
0x1800ea799  jz      short loc_1800EA7B2
0x1800ea79b  cmp     ecx, 1
0x1800ea79e  jz      short loc_1800EA7A9
0x1800ea7a0  lea     rdi, word_1801BBB0E
0x1800ea7a7  jmp     short loc_1800EA7E1
0x1800ea7a9  lea     rdi, aFailfast; "FailFast"
0x1800ea7b0  jmp     short loc_1800EA7E1
0x1800ea7b2  lea     rax, aLoghr; "LogHr"
0x1800ea7b9  lea     rdi, aLognt; "LogNt"
0x1800ea7c0  jmp     short loc_1800EA7D0
0x1800ea7c2  lea     rax, aReturnhr; "ReturnHr"
0x1800ea7c9  lea     rdi, aReturnnt; "ReturnNt"
0x1800ea7d0  test    [rbx+4], bpl
0x1800ea7d4  cmovz   rdi, rax
0x1800ea7d8  jmp     short loc_1800EA7E1
0x1800ea7da  lea     rdi, aException; "Exception"
0x1800ea7e1  xor     edx, edx; Val
0x1800ea7e3  mov     r8d, 200h; Size
0x1800ea7e9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800ea7ee  call    memset_0
0x1800ea7f3  test    [rbx+4], bpl
0x1800ea7f7  jz      short loc_1800EA81C
0x1800ea7f9  mov     ebp, [rbx+0Ch]
0x1800ea7fc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800ea803  test    rax, rax
0x1800ea806  jz      short loc_1800EA852
0x1800ea808  mov     r8d, 100h
0x1800ea80e  lea     rdx, [rsp+278h+Buffer]
0x1800ea813  mov     ecx, ebp
0x1800ea815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea81a  jmp     short loc_1800EA852
0x1800ea81c  mov     ebp, [rbx+8]
0x1800ea81f  mov     [rsp+278h+Arguments], r15; Arguments
0x1800ea824  mov     [rsp+278h+nSize], 100h; nSize
0x1800ea82c  lea     rax, [rsp+278h+Buffer]
0x1800ea831  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800ea836  mov     r9d, 400h; dwLanguageId
0x1800ea83c  mov     r8d, ebp; dwMessageId
0x1800ea83f  xor     edx, edx; lpSource
0x1800ea841  mov     ecx, 1200h; dwFlags
0x1800ea846  call    cs:__imp_FormatMessageW
0x1800ea84d  nop     dword ptr [rax+rax+00h]
0x1800ea852  lea     rsi, [r14+rsi*2]
0x1800ea856  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800ea85a  mov     rax, [rbx+88h]
0x1800ea861  mov     rcx, [rbx+80h]
0x1800ea868  mov     rdx, rsi; unsigned __int16 *
0x1800ea86b  test    r9, r9
0x1800ea86e  jz      short loc_1800EA892
0x1800ea870  mov     [rsp+278h+Arguments], rax
0x1800ea875  mov     qword ptr [rsp+278h+nSize], rcx
0x1800ea87a  mov     eax, [rbx+40h]
0x1800ea87d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800ea881  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800ea888  mov     rcx, r14; this
0x1800ea88b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ea890  jmp     short loc_1800EA8A9
0x1800ea892  mov     [rsp+278h+lpBuffer], rax
0x1800ea897  mov     r9, rcx; unsigned __int16 *
0x1800ea89a  lea     r8, aHsP; "%hs!%p: "
0x1800ea8a1  mov     rcx, r14; this
0x1800ea8a4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ea8a9  mov     r14, rax
0x1800ea8ac  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800ea8b3  test    r9, r9
0x1800ea8b6  jz      short loc_1800EA8CD
0x1800ea8b8  lea     r8, aCallerP; "(caller: %p) "
0x1800ea8bf  mov     rdx, rsi; unsigned __int16 *
0x1800ea8c2  mov     rcx, rax; this
0x1800ea8c5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ea8ca  mov     r14, rax
0x1800ea8cd  call    cs:__imp_GetCurrentThreadId
0x1800ea8d4  nop     dword ptr [rax+rax+00h]
0x1800ea8d9  lea     rcx, [rsp+278h+Buffer]
0x1800ea8de  mov     [rsp+278h+var_240], rcx
0x1800ea8e3  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800ea8e7  mov     [rsp+278h+nSize], eax
0x1800ea8eb  mov     eax, [rbx+44h]
0x1800ea8ee  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800ea8f2  mov     r9, rdi; unsigned __int16 *
0x1800ea8f5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800ea8fc  mov     rdx, rsi; unsigned __int16 *
0x1800ea8ff  mov     rcx, r14; this
0x1800ea902  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ea907  cmp     [rbx+18h], r15
0x1800ea90b  jnz     short loc_1800EA91D
0x1800ea90d  cmp     [rbx+48h], r15
0x1800ea911  jnz     short loc_1800EA91D
0x1800ea913  cmp     [rbx+30h], r15
0x1800ea917  jz      loc_1800EA9AD
0x1800ea91d  lea     r8, asc_1801BBC80; "    "
0x1800ea924  mov     rdx, rsi; unsigned __int16 *
0x1800ea927  mov     rcx, rax; this
0x1800ea92a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ea92f  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800ea933  test    r9, r9
0x1800ea936  jz      short loc_1800EA94A
0x1800ea938  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800ea93f  mov     rdx, rsi; unsigned __int16 *
0x1800ea942  mov     rcx, rax; this
0x1800ea945  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ea94a  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800ea94e  test    r9, r9
0x1800ea951  jz      short loc_1800EA965
0x1800ea953  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800ea95a  mov     rdx, rsi; unsigned __int16 *
0x1800ea95d  mov     rcx, rax; this
0x1800ea960  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ea965  mov     rcx, [rbx+28h]
0x1800ea969  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800ea96d  mov     rdx, rsi; unsigned __int16 *
0x1800ea970  test    rcx, rcx
0x1800ea973  jz      short loc_1800EA98B
0x1800ea975  mov     [rsp+278h+lpBuffer], rcx
0x1800ea97a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800ea981  mov     rcx, rax; this
0x1800ea984  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ea989  jmp     short loc_1800EA9AD
0x1800ea98b  mov     rcx, rax; this
0x1800ea98e  test    r9, r9
0x1800ea991  jz      short loc_1800EA9A1
0x1800ea993  lea     r8, aHs; "[%hs]\n"
0x1800ea99a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ea99f  jmp     short loc_1800EA9AD
0x1800ea9a1  lea     r8, asc_1801BBCF8; "\n"
0x1800ea9a8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ea9ad  xor     eax, eax
0x1800ea9af  mov     rcx, [rsp+278h+var_38]
0x1800ea9b7  xor     rcx, rsp; StackCookie
0x1800ea9ba  call    __security_check_cookie
0x1800ea9bf  mov     rbx, [rsp+278h+arg_18]
0x1800ea9c7  add     rsp, 250h
0x1800ea9ce  pop     r15
0x1800ea9d0  pop     r14
0x1800ea9d2  pop     rdi
0x1800ea9d3  pop     rsi
0x1800ea9d4  pop     rbp
0x1800ea9d5  retn
```
