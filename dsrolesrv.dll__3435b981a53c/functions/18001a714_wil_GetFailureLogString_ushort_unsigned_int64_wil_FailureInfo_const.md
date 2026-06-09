# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18001a714`
- end: `0x18001a9ca`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180018950`
- `0x18001b270`

## callees

- `0x18001a714`
- `0x18001b570`
- `0x18002c01e`
- `0x18002c050`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a8c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a8c7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001a846`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001a846`

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
          v8 = (const char *)&dword_180040DA4;
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
0x18001a714  mov     [rsp+arg_18], rbx
0x18001a719  push    rbp
0x18001a71a  push    rsi
0x18001a71b  push    rdi
0x18001a71c  push    r14
0x18001a71e  push    r15
0x18001a720  sub     rsp, 250h
0x18001a727  mov     rax, cs:__security_cookie
0x18001a72e  xor     rax, rsp
0x18001a731  mov     [rsp+278h+var_38], rax
0x18001a739  xor     r15d, r15d
0x18001a73c  mov     rbx, r8
0x18001a73f  mov     rsi, rdx
0x18001a742  mov     r14, rcx
0x18001a745  test    rdx, rdx
0x18001a748  jz      loc_18001A9A1
0x18001a74e  test    rcx, rcx
0x18001a751  jz      loc_18001A9A1
0x18001a757  mov     rax, cs:g_pfnResultLoggingCallback
0x18001a75e  mov     [rcx], r15w
0x18001a762  test    rax, rax
0x18001a765  jz      short loc_18001A788
0x18001a767  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001a76e  jz      short loc_18001A788
0x18001a770  mov     r8, rdx
0x18001a773  mov     rdx, rcx
0x18001a776  mov     rcx, rbx
0x18001a779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a77e  cmp     [r14], r15w
0x18001a782  jnz     loc_18001A9A1
0x18001a788  mov     ecx, [rbx]
0x18001a78a  mov     bpl, 8
0x18001a78d  test    ecx, ecx
0x18001a78f  jz      short loc_18001A7DA
0x18001a791  sub     ecx, 1
0x18001a794  jz      short loc_18001A7C2
0x18001a796  sub     ecx, 1
0x18001a799  jz      short loc_18001A7B2
0x18001a79b  cmp     ecx, 1
0x18001a79e  jz      short loc_18001A7A9
0x18001a7a0  lea     rdi, dword_180040DA4
0x18001a7a7  jmp     short loc_18001A7E1
0x18001a7a9  lea     rdi, aFailfast; "FailFast"
0x18001a7b0  jmp     short loc_18001A7E1
0x18001a7b2  lea     rax, aLoghr; "LogHr"
0x18001a7b9  lea     rdi, aLognt; "LogNt"
0x18001a7c0  jmp     short loc_18001A7D0
0x18001a7c2  lea     rax, aReturnhr; "ReturnHr"
0x18001a7c9  lea     rdi, aReturnnt; "ReturnNt"
0x18001a7d0  test    [rbx+4], bpl
0x18001a7d4  cmovz   rdi, rax
0x18001a7d8  jmp     short loc_18001A7E1
0x18001a7da  lea     rdi, aException; "Exception"
0x18001a7e1  xor     edx, edx; Val
0x18001a7e3  lea     rcx, [rsp+278h+Buffer]; void *
0x18001a7e8  mov     r8d, 200h; Size
0x18001a7ee  call    memset_0
0x18001a7f3  test    [rbx+4], bpl
0x18001a7f7  jz      short loc_18001A81C
0x18001a7f9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18001a800  mov     ebp, [rbx+0Ch]
0x18001a803  test    rax, rax
0x18001a806  jz      short loc_18001A84C
0x18001a808  mov     r8d, 100h
0x18001a80e  lea     rdx, [rsp+278h+Buffer]
0x18001a813  mov     ecx, ebp
0x18001a815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a81a  jmp     short loc_18001A84C
0x18001a81c  mov     ebp, [rbx+8]
0x18001a81f  lea     rax, [rsp+278h+Buffer]
0x18001a824  mov     [rsp+278h+Arguments], r15; Arguments
0x18001a829  mov     r8d, ebp; dwMessageId
0x18001a82c  mov     [rsp+278h+nSize], 100h; nSize
0x18001a834  mov     r9d, 400h; dwLanguageId
0x18001a83a  xor     edx, edx; lpSource
0x18001a83c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18001a841  mov     ecx, 1200h; dwFlags
0x18001a846  call    cs:__imp_FormatMessageW
0x18001a84c  mov     r9, [rbx+38h]; unsigned __int16 *
0x18001a850  lea     rsi, [r14+rsi*2]
0x18001a854  mov     rax, [rbx+88h]
0x18001a85b  mov     rdx, rsi; unsigned __int16 *
0x18001a85e  mov     rcx, [rbx+80h]
0x18001a865  test    r9, r9
0x18001a868  jz      short loc_18001A88C
0x18001a86a  mov     [rsp+278h+Arguments], rax
0x18001a86f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18001a876  mov     eax, [rbx+40h]
0x18001a879  mov     qword ptr [rsp+278h+nSize], rcx
0x18001a87e  mov     rcx, r14; this
0x18001a881  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001a885  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a88a  jmp     short loc_18001A8A3
0x18001a88c  mov     r9, rcx; unsigned __int16 *
0x18001a88f  mov     [rsp+278h+lpBuffer], rax
0x18001a894  mov     rcx, r14; this
0x18001a897  lea     r8, aHsP; "%hs!%p: "
0x18001a89e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a8a3  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001a8aa  mov     r14, rax
0x18001a8ad  test    r9, r9
0x18001a8b0  jz      short loc_18001A8C7
0x18001a8b2  lea     r8, aCallerP; "(caller: %p) "
0x18001a8b9  mov     rdx, rsi; unsigned __int16 *
0x18001a8bc  mov     rcx, rax; this
0x18001a8bf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a8c4  mov     r14, rax
0x18001a8c7  call    cs:__imp_GetCurrentThreadId
0x18001a8cd  lea     rcx, [rsp+278h+Buffer]
0x18001a8d2  mov     r9, rdi; unsigned __int16 *
0x18001a8d5  mov     [rsp+278h+var_240], rcx
0x18001a8da  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18001a8e1  mov     dword ptr [rsp+278h+Arguments], ebp
0x18001a8e5  mov     rdx, rsi; unsigned __int16 *
0x18001a8e8  mov     [rsp+278h+nSize], eax
0x18001a8ec  mov     rcx, r14; this
0x18001a8ef  mov     eax, [rbx+44h]
0x18001a8f2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001a8f6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a8fb  cmp     [rbx+18h], r15
0x18001a8ff  jnz     short loc_18001A911
0x18001a901  cmp     [rbx+48h], r15
0x18001a905  jnz     short loc_18001A911
0x18001a907  cmp     [rbx+30h], r15
0x18001a90b  jz      loc_18001A9A1
0x18001a911  lea     r8, asc_180040E90; "    "
0x18001a918  mov     rdx, rsi; unsigned __int16 *
0x18001a91b  mov     rcx, rax; this
0x18001a91e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a923  mov     r9, [rbx+18h]; unsigned __int16 *
0x18001a927  test    r9, r9
0x18001a92a  jz      short loc_18001A93E
0x18001a92c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18001a933  mov     rdx, rsi; unsigned __int16 *
0x18001a936  mov     rcx, rax; this
0x18001a939  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a93e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18001a942  test    r9, r9
0x18001a945  jz      short loc_18001A959
0x18001a947  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001a94e  mov     rdx, rsi; unsigned __int16 *
0x18001a951  mov     rcx, rax; this
0x18001a954  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a959  mov     rcx, [rbx+28h]
0x18001a95d  mov     rdx, rsi; unsigned __int16 *
0x18001a960  mov     r9, [rbx+30h]; unsigned __int16 *
0x18001a964  test    rcx, rcx
0x18001a967  jz      short loc_18001A97F
0x18001a969  mov     [rsp+278h+lpBuffer], rcx
0x18001a96e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18001a975  mov     rcx, rax; this
0x18001a978  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a97d  jmp     short loc_18001A9A1
0x18001a97f  mov     rcx, rax; this
0x18001a982  test    r9, r9
0x18001a985  jz      short loc_18001A995
0x18001a987  lea     r8, aHs; "[%hs]\n"
0x18001a98e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a993  jmp     short loc_18001A9A1
0x18001a995  lea     r8, asc_18003C80C; "\n"
0x18001a99c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a9a1  xor     eax, eax
0x18001a9a3  mov     rcx, [rsp+278h+var_38]
0x18001a9ab  xor     rcx, rsp; StackCookie
0x18001a9ae  call    __security_check_cookie
0x18001a9b3  mov     rbx, [rsp+278h+arg_18]
0x18001a9bb  add     rsp, 250h
0x18001a9c2  pop     r15
0x18001a9c4  pop     r14
0x18001a9c6  pop     rdi
0x18001a9c7  pop     rsi
0x18001a9c8  pop     rbp
0x18001a9c9  retn
```
