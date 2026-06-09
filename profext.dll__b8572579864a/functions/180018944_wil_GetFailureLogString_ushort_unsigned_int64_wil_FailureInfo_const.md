# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180018944`
- end: `0x180018c07`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180012c80`
- `0x180018fa0`
- `0x1800194ac`
- `0x18001c280`
- `0x18001eb50`

## callees

- `0x180018944`
- `0x1800192b4`
- `0x1800227f2`
- `0x180022830`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018afd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018afd`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180018a76`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180018a76`

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
          v7 = (const char *)&qword_180027080;
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
0x180018944  mov     [rsp+arg_18], rbx
0x180018949  push    rbp
0x18001894a  push    rsi
0x18001894b  push    rdi
0x18001894c  push    r14
0x18001894e  push    r15
0x180018950  sub     rsp, 250h
0x180018957  mov     rax, cs:__security_cookie
0x18001895e  xor     rax, rsp
0x180018961  mov     [rsp+278h+var_38], rax
0x180018969  mov     rbx, r8
0x18001896c  mov     rsi, rdx
0x18001896f  mov     r14, rcx
0x180018972  xor     r15d, r15d
0x180018975  test    rdx, rdx
0x180018978  jz      loc_180018BDD
0x18001897e  test    rcx, rcx
0x180018981  jz      loc_180018BDD
0x180018987  mov     [rcx], r15w
0x18001898b  mov     rax, cs:g_pfnResultLoggingCallback
0x180018992  test    rax, rax
0x180018995  jz      short loc_1800189B8
0x180018997  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001899e  jz      short loc_1800189B8
0x1800189a0  mov     r8, rdx
0x1800189a3  mov     rdx, rcx
0x1800189a6  mov     rcx, rbx
0x1800189a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189ae  cmp     [r14], r15w
0x1800189b2  jnz     loc_180018BDD
0x1800189b8  mov     ecx, [rbx]
0x1800189ba  mov     bpl, 8
0x1800189bd  test    ecx, ecx
0x1800189bf  jz      short loc_180018A0A
0x1800189c1  sub     ecx, 1
0x1800189c4  jz      short loc_1800189F2
0x1800189c6  sub     ecx, 1
0x1800189c9  jz      short loc_1800189E2
0x1800189cb  cmp     ecx, 1
0x1800189ce  jz      short loc_1800189D9
0x1800189d0  lea     rdi, qword_180027080
0x1800189d7  jmp     short loc_180018A11
0x1800189d9  lea     rdi, aFailfast; "FailFast"
0x1800189e0  jmp     short loc_180018A11
0x1800189e2  lea     rax, aLoghr; "LogHr"
0x1800189e9  lea     rdi, aLognt; "LogNt"
0x1800189f0  jmp     short loc_180018A00
0x1800189f2  lea     rax, aReturnhr; "ReturnHr"
0x1800189f9  lea     rdi, aReturnnt; "ReturnNt"
0x180018a00  test    [rbx+4], bpl
0x180018a04  cmovz   rdi, rax
0x180018a08  jmp     short loc_180018A11
0x180018a0a  lea     rdi, aException; "Exception"
0x180018a11  xor     edx, edx; Val
0x180018a13  mov     r8d, 200h; Size
0x180018a19  lea     rcx, [rsp+278h+Buffer]; void *
0x180018a1e  call    memset_0
0x180018a23  test    [rbx+4], bpl
0x180018a27  jz      short loc_180018A4C
0x180018a29  mov     ebp, [rbx+0Ch]
0x180018a2c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180018a33  test    rax, rax
0x180018a36  jz      short loc_180018A82
0x180018a38  mov     r8d, 100h
0x180018a3e  lea     rdx, [rsp+278h+Buffer]
0x180018a43  mov     ecx, ebp
0x180018a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a4a  jmp     short loc_180018A82
0x180018a4c  mov     ebp, [rbx+8]
0x180018a4f  mov     [rsp+278h+Arguments], r15; Arguments
0x180018a54  mov     [rsp+278h+nSize], 100h; nSize
0x180018a5c  lea     rax, [rsp+278h+Buffer]
0x180018a61  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180018a66  mov     r9d, 400h; dwLanguageId
0x180018a6c  mov     r8d, ebp; dwMessageId
0x180018a6f  xor     edx, edx; lpSource
0x180018a71  mov     ecx, 1200h; dwFlags
0x180018a76  call    cs:__imp_FormatMessageW
0x180018a7d  nop     dword ptr [rax+rax+00h]
0x180018a82  lea     rsi, [r14+rsi*2]
0x180018a86  mov     r9, [rbx+38h]; unsigned __int16 *
0x180018a8a  mov     rax, [rbx+88h]
0x180018a91  mov     rcx, [rbx+80h]
0x180018a98  mov     rdx, rsi; unsigned __int16 *
0x180018a9b  test    r9, r9
0x180018a9e  jz      short loc_180018AC2
0x180018aa0  mov     [rsp+278h+Arguments], rax
0x180018aa5  mov     qword ptr [rsp+278h+nSize], rcx
0x180018aaa  mov     eax, [rbx+40h]
0x180018aad  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180018ab1  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180018ab8  mov     rcx, r14; this
0x180018abb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180018ac0  jmp     short loc_180018AD9
0x180018ac2  mov     [rsp+278h+lpBuffer], rax
0x180018ac7  mov     r9, rcx; unsigned __int16 *
0x180018aca  lea     r8, aHsP; "%hs!%p: "
0x180018ad1  mov     rcx, r14; this
0x180018ad4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180018ad9  mov     r14, rax
0x180018adc  mov     r9, [rbx+90h]; unsigned __int16 *
0x180018ae3  test    r9, r9
0x180018ae6  jz      short loc_180018AFD
0x180018ae8  lea     r8, aCallerP; "(caller: %p) "
0x180018aef  mov     rdx, rsi; unsigned __int16 *
0x180018af2  mov     rcx, rax; this
0x180018af5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180018afa  mov     r14, rax
0x180018afd  call    cs:__imp_GetCurrentThreadId
0x180018b04  nop     dword ptr [rax+rax+00h]
0x180018b09  lea     rcx, [rsp+278h+Buffer]
0x180018b0e  mov     [rsp+278h+var_240], rcx
0x180018b13  mov     dword ptr [rsp+278h+Arguments], ebp
0x180018b17  mov     [rsp+278h+nSize], eax
0x180018b1b  mov     eax, [rbx+44h]
0x180018b1e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180018b22  mov     r9, rdi; unsigned __int16 *
0x180018b25  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180018b2c  mov     rdx, rsi; unsigned __int16 *
0x180018b2f  mov     rcx, r14; this
0x180018b32  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180018b37  cmp     [rbx+18h], r15
0x180018b3b  jnz     short loc_180018B4D
0x180018b3d  cmp     [rbx+48h], r15
0x180018b41  jnz     short loc_180018B4D
0x180018b43  cmp     [rbx+30h], r15
0x180018b47  jz      loc_180018BDD
0x180018b4d  lea     r8, asc_1800280B0; "    "
0x180018b54  mov     rdx, rsi; unsigned __int16 *
0x180018b57  mov     rcx, rax; this
0x180018b5a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180018b5f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180018b63  test    r9, r9
0x180018b66  jz      short loc_180018B7A
0x180018b68  lea     r8, aMsgWs; "Msg:[%ws] "
0x180018b6f  mov     rdx, rsi; unsigned __int16 *
0x180018b72  mov     rcx, rax; this
0x180018b75  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180018b7a  mov     r9, [rbx+48h]; unsigned __int16 *
0x180018b7e  test    r9, r9
0x180018b81  jz      short loc_180018B95
0x180018b83  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180018b8a  mov     rdx, rsi; unsigned __int16 *
0x180018b8d  mov     rcx, rax; this
0x180018b90  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180018b95  mov     rcx, [rbx+28h]
0x180018b99  mov     r9, [rbx+30h]; unsigned __int16 *
0x180018b9d  mov     rdx, rsi; unsigned __int16 *
0x180018ba0  test    rcx, rcx
0x180018ba3  jz      short loc_180018BBB
0x180018ba5  mov     [rsp+278h+lpBuffer], rcx
0x180018baa  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180018bb1  mov     rcx, rax; this
0x180018bb4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180018bb9  jmp     short loc_180018BDD
0x180018bbb  mov     rcx, rax; this
0x180018bbe  test    r9, r9
0x180018bc1  jz      short loc_180018BD1
0x180018bc3  lea     r8, aHs; "[%hs]\n"
0x180018bca  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180018bcf  jmp     short loc_180018BDD
0x180018bd1  lea     r8, asc_180028128; "\n"
0x180018bd8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180018bdd  xor     eax, eax
0x180018bdf  mov     rcx, [rsp+278h+var_38]
0x180018be7  xor     rcx, rsp; StackCookie
0x180018bea  call    __security_check_cookie
0x180018bef  mov     rbx, [rsp+278h+arg_18]
0x180018bf7  add     rsp, 250h
0x180018bfe  pop     r15
0x180018c00  pop     r14
0x180018c02  pop     rdi
0x180018c03  pop     rsi
0x180018c04  pop     rbp
0x180018c05  retn
```
