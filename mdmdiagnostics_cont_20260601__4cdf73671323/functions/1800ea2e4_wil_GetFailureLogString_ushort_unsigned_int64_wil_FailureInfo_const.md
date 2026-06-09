# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800ea2e4`
- end: `0x1800ea59a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800e4be4`
- `0x1800eb00c`
- `0x1800eb738`
- `0x1800f4910`

## callees

- `0x180019000`
- `0x180019fc4`
- `0x1800ea2e4`
- `0x1800eb30c`
- `0x180191010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ea497`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ea497`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800ea416`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800ea416`

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
          v7 = (const char *)&word_1801B9B0E;
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
0x1800ea2e4  mov     [rsp+arg_18], rbx
0x1800ea2e9  push    rbp
0x1800ea2ea  push    rsi
0x1800ea2eb  push    rdi
0x1800ea2ec  push    r14
0x1800ea2ee  push    r15
0x1800ea2f0  sub     rsp, 250h
0x1800ea2f7  mov     rax, cs:__security_cookie
0x1800ea2fe  xor     rax, rsp
0x1800ea301  mov     [rsp+278h+var_38], rax
0x1800ea309  mov     rbx, r8
0x1800ea30c  mov     rsi, rdx
0x1800ea30f  mov     r14, rcx
0x1800ea312  xor     r15d, r15d
0x1800ea315  test    rdx, rdx
0x1800ea318  jz      loc_1800EA571
0x1800ea31e  test    rcx, rcx
0x1800ea321  jz      loc_1800EA571
0x1800ea327  mov     [rcx], r15w
0x1800ea32b  mov     rax, cs:g_pfnResultLoggingCallback
0x1800ea332  test    rax, rax
0x1800ea335  jz      short loc_1800EA358
0x1800ea337  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800ea33e  jz      short loc_1800EA358
0x1800ea340  mov     r8, rdx
0x1800ea343  mov     rdx, rcx
0x1800ea346  mov     rcx, rbx
0x1800ea349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea34e  cmp     [r14], r15w
0x1800ea352  jnz     loc_1800EA571
0x1800ea358  mov     ecx, [rbx]
0x1800ea35a  mov     bpl, 8
0x1800ea35d  test    ecx, ecx
0x1800ea35f  jz      short loc_1800EA3AA
0x1800ea361  sub     ecx, 1
0x1800ea364  jz      short loc_1800EA392
0x1800ea366  sub     ecx, 1
0x1800ea369  jz      short loc_1800EA382
0x1800ea36b  cmp     ecx, 1
0x1800ea36e  jz      short loc_1800EA379
0x1800ea370  lea     rdi, word_1801B9B0E
0x1800ea377  jmp     short loc_1800EA3B1
0x1800ea379  lea     rdi, aFailfast; "FailFast"
0x1800ea380  jmp     short loc_1800EA3B1
0x1800ea382  lea     rax, aLoghr; "LogHr"
0x1800ea389  lea     rdi, aLognt; "LogNt"
0x1800ea390  jmp     short loc_1800EA3A0
0x1800ea392  lea     rax, aReturnhr; "ReturnHr"
0x1800ea399  lea     rdi, aReturnnt; "ReturnNt"
0x1800ea3a0  test    [rbx+4], bpl
0x1800ea3a4  cmovz   rdi, rax
0x1800ea3a8  jmp     short loc_1800EA3B1
0x1800ea3aa  lea     rdi, aException; "Exception"
0x1800ea3b1  xor     edx, edx; Val
0x1800ea3b3  mov     r8d, 200h; Size
0x1800ea3b9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800ea3be  call    memset_0
0x1800ea3c3  test    [rbx+4], bpl
0x1800ea3c7  jz      short loc_1800EA3EC
0x1800ea3c9  mov     ebp, [rbx+0Ch]
0x1800ea3cc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800ea3d3  test    rax, rax
0x1800ea3d6  jz      short loc_1800EA41C
0x1800ea3d8  mov     r8d, 100h
0x1800ea3de  lea     rdx, [rsp+278h+Buffer]
0x1800ea3e3  mov     ecx, ebp
0x1800ea3e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea3ea  jmp     short loc_1800EA41C
0x1800ea3ec  mov     ebp, [rbx+8]
0x1800ea3ef  mov     [rsp+278h+Arguments], r15; Arguments
0x1800ea3f4  mov     [rsp+278h+nSize], 100h; nSize
0x1800ea3fc  lea     rax, [rsp+278h+Buffer]
0x1800ea401  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800ea406  mov     r9d, 400h; dwLanguageId
0x1800ea40c  mov     r8d, ebp; dwMessageId
0x1800ea40f  xor     edx, edx; lpSource
0x1800ea411  mov     ecx, 1200h; dwFlags
0x1800ea416  call    cs:__imp_FormatMessageW
0x1800ea41c  lea     rsi, [r14+rsi*2]
0x1800ea420  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800ea424  mov     rax, [rbx+88h]
0x1800ea42b  mov     rcx, [rbx+80h]
0x1800ea432  mov     rdx, rsi; unsigned __int16 *
0x1800ea435  test    r9, r9
0x1800ea438  jz      short loc_1800EA45C
0x1800ea43a  mov     [rsp+278h+Arguments], rax
0x1800ea43f  mov     qword ptr [rsp+278h+nSize], rcx
0x1800ea444  mov     eax, [rbx+40h]
0x1800ea447  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800ea44b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800ea452  mov     rcx, r14; this
0x1800ea455  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ea45a  jmp     short loc_1800EA473
0x1800ea45c  mov     [rsp+278h+lpBuffer], rax
0x1800ea461  mov     r9, rcx; unsigned __int16 *
0x1800ea464  lea     r8, aHsP; "%hs!%p: "
0x1800ea46b  mov     rcx, r14; this
0x1800ea46e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ea473  mov     r14, rax
0x1800ea476  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800ea47d  test    r9, r9
0x1800ea480  jz      short loc_1800EA497
0x1800ea482  lea     r8, aCallerP; "(caller: %p) "
0x1800ea489  mov     rdx, rsi; unsigned __int16 *
0x1800ea48c  mov     rcx, rax; this
0x1800ea48f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ea494  mov     r14, rax
0x1800ea497  call    cs:__imp_GetCurrentThreadId
0x1800ea49d  lea     rcx, [rsp+278h+Buffer]
0x1800ea4a2  mov     [rsp+278h+var_240], rcx
0x1800ea4a7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800ea4ab  mov     [rsp+278h+nSize], eax
0x1800ea4af  mov     eax, [rbx+44h]
0x1800ea4b2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800ea4b6  mov     r9, rdi; unsigned __int16 *
0x1800ea4b9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800ea4c0  mov     rdx, rsi; unsigned __int16 *
0x1800ea4c3  mov     rcx, r14; this
0x1800ea4c6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ea4cb  cmp     [rbx+18h], r15
0x1800ea4cf  jnz     short loc_1800EA4E1
0x1800ea4d1  cmp     [rbx+48h], r15
0x1800ea4d5  jnz     short loc_1800EA4E1
0x1800ea4d7  cmp     [rbx+30h], r15
0x1800ea4db  jz      loc_1800EA571
0x1800ea4e1  lea     r8, asc_1801B9C80; "    "
0x1800ea4e8  mov     rdx, rsi; unsigned __int16 *
0x1800ea4eb  mov     rcx, rax; this
0x1800ea4ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ea4f3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800ea4f7  test    r9, r9
0x1800ea4fa  jz      short loc_1800EA50E
0x1800ea4fc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800ea503  mov     rdx, rsi; unsigned __int16 *
0x1800ea506  mov     rcx, rax; this
0x1800ea509  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ea50e  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800ea512  test    r9, r9
0x1800ea515  jz      short loc_1800EA529
0x1800ea517  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800ea51e  mov     rdx, rsi; unsigned __int16 *
0x1800ea521  mov     rcx, rax; this
0x1800ea524  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ea529  mov     rcx, [rbx+28h]
0x1800ea52d  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800ea531  mov     rdx, rsi; unsigned __int16 *
0x1800ea534  test    rcx, rcx
0x1800ea537  jz      short loc_1800EA54F
0x1800ea539  mov     [rsp+278h+lpBuffer], rcx
0x1800ea53e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800ea545  mov     rcx, rax; this
0x1800ea548  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ea54d  jmp     short loc_1800EA571
0x1800ea54f  mov     rcx, rax; this
0x1800ea552  test    r9, r9
0x1800ea555  jz      short loc_1800EA565
0x1800ea557  lea     r8, aHs; "[%hs]\n"
0x1800ea55e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ea563  jmp     short loc_1800EA571
0x1800ea565  lea     r8, asc_1801B9CF8; "\n"
0x1800ea56c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ea571  xor     eax, eax
0x1800ea573  mov     rcx, [rsp+278h+var_38]
0x1800ea57b  xor     rcx, rsp; StackCookie
0x1800ea57e  call    __security_check_cookie
0x1800ea583  mov     rbx, [rsp+278h+arg_18]
0x1800ea58b  add     rsp, 250h
0x1800ea592  pop     r15
0x1800ea594  pop     r14
0x1800ea596  pop     rdi
0x1800ea597  pop     rsi
0x1800ea598  pop     rbp
0x1800ea599  retn
```
