# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000d474`
- end: `0x18000d735`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180005058`
- `0x1800052ec`
- `0x1800055b0`
- `0x180005870`
- `0x180019e40`
- `0x180022783`
- `0x1800228b7`
- `0x180023209`
- `0x180023466`

## callees

- `0x1800026b0`
- `0x180003374`
- `0x18000d474`
- `0x18000ea4c`
- `0x180024010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x18000d5a4`
- `KERNEL32!FormatMessageW` at `0x18000d5a4`
- `KERNEL32!GetCurrentThreadId` at `0x18000d62b`
- `KERNEL32!GetCurrentThreadId` at `0x18000d62b`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  const char *v7; // rsi
  const char *v8; // rax
  DWORD v9; // ebp
  unsigned __int16 *v10; // rdi
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
  v7 = (const char *)&word_1800261C0;
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
        goto LABEL_17;
      }
      v8 = "LogHr";
      v7 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v7 = v8;
    goto LABEL_17;
  }
  v7 = "Exception";
LABEL_17:
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
0x18000d474  mov     [rsp+arg_18], rbx
0x18000d479  push    rbp
0x18000d47a  push    rsi
0x18000d47b  push    rdi
0x18000d47c  push    r14
0x18000d47e  push    r15
0x18000d480  sub     rsp, 250h
0x18000d487  mov     rax, cs:__security_cookie
0x18000d48e  xor     rax, rsp
0x18000d491  mov     [rsp+278h+var_38], rax
0x18000d499  mov     rbx, r8
0x18000d49c  mov     rdi, rdx
0x18000d49f  mov     r14, rcx
0x18000d4a2  xor     r15d, r15d
0x18000d4a5  test    rdx, rdx
0x18000d4a8  jz      loc_18000D70B
0x18000d4ae  test    rcx, rcx
0x18000d4b1  jz      loc_18000D70B
0x18000d4b7  mov     [rcx], r15w
0x18000d4bb  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d4c2  test    rax, rax
0x18000d4c5  jz      short loc_18000D4E8
0x18000d4c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000d4ce  jz      short loc_18000D4E8
0x18000d4d0  mov     r8, rdx
0x18000d4d3  mov     rdx, rcx
0x18000d4d6  mov     rcx, rbx
0x18000d4d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4de  cmp     [r14], r15w
0x18000d4e2  jnz     loc_18000D70B
0x18000d4e8  lea     rsi, word_1800261C0
0x18000d4ef  mov     ecx, [rbx]
0x18000d4f1  mov     bpl, 8
0x18000d4f4  test    ecx, ecx
0x18000d4f6  jz      short loc_18000D538
0x18000d4f8  sub     ecx, 1
0x18000d4fb  jz      short loc_18000D520
0x18000d4fd  sub     ecx, 1
0x18000d500  jz      short loc_18000D510
0x18000d502  cmp     ecx, 1
0x18000d505  jnz     short loc_18000D53F
0x18000d507  lea     rsi, aFailfast; "FailFast"
0x18000d50e  jmp     short loc_18000D53F
0x18000d510  lea     rax, aLoghr; "LogHr"
0x18000d517  lea     rsi, aLognt; "LogNt"
0x18000d51e  jmp     short loc_18000D52E
0x18000d520  lea     rax, aReturnhr; "ReturnHr"
0x18000d527  lea     rsi, aReturnnt; "ReturnNt"
0x18000d52e  test    [rbx+4], bpl
0x18000d532  cmovz   rsi, rax
0x18000d536  jmp     short loc_18000D53F
0x18000d538  lea     rsi, aException; "Exception"
0x18000d53f  xor     edx, edx; Val
0x18000d541  mov     r8d, 200h; Size
0x18000d547  lea     rcx, [rsp+278h+Buffer]; void *
0x18000d54c  call    memset_0
0x18000d551  test    [rbx+4], bpl
0x18000d555  jz      short loc_18000D57A
0x18000d557  mov     ebp, [rbx+0Ch]
0x18000d55a  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000d561  test    rax, rax
0x18000d564  jz      short loc_18000D5B0
0x18000d566  mov     r8d, 100h
0x18000d56c  lea     rdx, [rsp+278h+Buffer]
0x18000d571  mov     ecx, ebp
0x18000d573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d578  jmp     short loc_18000D5B0
0x18000d57a  mov     ebp, [rbx+8]
0x18000d57d  mov     [rsp+278h+Arguments], r15; Arguments
0x18000d582  mov     [rsp+278h+nSize], 100h; nSize
0x18000d58a  lea     rax, [rsp+278h+Buffer]
0x18000d58f  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000d594  mov     r9d, 400h; dwLanguageId
0x18000d59a  mov     r8d, ebp; dwMessageId
0x18000d59d  xor     edx, edx; lpSource
0x18000d59f  mov     ecx, 1200h; dwFlags
0x18000d5a4  call    cs:__imp_FormatMessageW
0x18000d5ab  nop     dword ptr [rax+rax+00h]
0x18000d5b0  lea     rdi, [r14+rdi*2]
0x18000d5b4  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000d5b8  mov     rax, [rbx+88h]
0x18000d5bf  mov     rcx, [rbx+80h]
0x18000d5c6  mov     rdx, rdi; unsigned __int16 *
0x18000d5c9  test    r9, r9
0x18000d5cc  jz      short loc_18000D5F0
0x18000d5ce  mov     [rsp+278h+Arguments], rax
0x18000d5d3  mov     qword ptr [rsp+278h+nSize], rcx
0x18000d5d8  mov     eax, [rbx+40h]
0x18000d5db  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000d5df  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000d5e6  mov     rcx, r14; this
0x18000d5e9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d5ee  jmp     short loc_18000D607
0x18000d5f0  mov     [rsp+278h+lpBuffer], rax
0x18000d5f5  mov     r9, rcx; unsigned __int16 *
0x18000d5f8  lea     r8, aHsP; "%hs!%p: "
0x18000d5ff  mov     rcx, r14; this
0x18000d602  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d607  mov     r14, rax
0x18000d60a  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000d611  test    r9, r9
0x18000d614  jz      short loc_18000D62B
0x18000d616  lea     r8, aCallerP; "(caller: %p) "
0x18000d61d  mov     rdx, rdi; unsigned __int16 *
0x18000d620  mov     rcx, rax; this
0x18000d623  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d628  mov     r14, rax
0x18000d62b  call    cs:__imp_GetCurrentThreadId
0x18000d632  nop     dword ptr [rax+rax+00h]
0x18000d637  mov     ecx, [rbx+44h]
0x18000d63a  lea     rdx, [rsp+278h+Buffer]
0x18000d63f  mov     [rsp+278h+var_240], rdx
0x18000d644  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000d648  mov     [rsp+278h+nSize], eax
0x18000d64c  mov     dword ptr [rsp+278h+lpBuffer], ecx
0x18000d650  mov     r9, rsi; unsigned __int16 *
0x18000d653  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000d65a  mov     rdx, rdi; unsigned __int16 *
0x18000d65d  mov     rcx, r14; this
0x18000d660  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d665  cmp     [rbx+18h], r15
0x18000d669  jnz     short loc_18000D67B
0x18000d66b  cmp     [rbx+48h], r15
0x18000d66f  jnz     short loc_18000D67B
0x18000d671  cmp     [rbx+30h], r15
0x18000d675  jz      loc_18000D70B
0x18000d67b  lea     r8, asc_1800262E0; "    "
0x18000d682  mov     rdx, rdi; unsigned __int16 *
0x18000d685  mov     rcx, rax; this
0x18000d688  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d68d  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000d691  test    r9, r9
0x18000d694  jz      short loc_18000D6A8
0x18000d696  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000d69d  mov     rdx, rdi; unsigned __int16 *
0x18000d6a0  mov     rcx, rax; this
0x18000d6a3  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d6a8  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000d6ac  test    r9, r9
0x18000d6af  jz      short loc_18000D6C3
0x18000d6b1  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000d6b8  mov     rdx, rdi; unsigned __int16 *
0x18000d6bb  mov     rcx, rax; this
0x18000d6be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d6c3  mov     rcx, [rbx+28h]
0x18000d6c7  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000d6cb  mov     rdx, rdi; unsigned __int16 *
0x18000d6ce  test    rcx, rcx
0x18000d6d1  jz      short loc_18000D6E9
0x18000d6d3  mov     [rsp+278h+lpBuffer], rcx
0x18000d6d8  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000d6df  mov     rcx, rax; this
0x18000d6e2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d6e7  jmp     short loc_18000D70B
0x18000d6e9  mov     rcx, rax; this
0x18000d6ec  test    r9, r9
0x18000d6ef  jz      short loc_18000D6FF
0x18000d6f1  lea     r8, aHs; "[%hs]\n"
0x18000d6f8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d6fd  jmp     short loc_18000D70B
0x18000d6ff  lea     r8, asc_180026358; "\n"
0x18000d706  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d70b  xor     eax, eax
0x18000d70d  mov     rcx, [rsp+278h+var_38]
0x18000d715  xor     rcx, rsp; StackCookie
0x18000d718  call    __security_check_cookie
0x18000d71d  mov     rbx, [rsp+278h+arg_18]
0x18000d725  add     rsp, 250h
0x18000d72c  pop     r15
0x18000d72e  pop     r14
0x18000d730  pop     rdi
0x18000d731  pop     rsi
0x18000d732  pop     rbp
0x18000d733  retn
```
