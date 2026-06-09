# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800052e4`
- end: `0x18000559a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800033d0`
- `0x180003638`
- `0x180005c40`

## callees

- `0x1800052e4`
- `0x180005f40`
- `0x18000bbc2`
- `0x18000bbf0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005416`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005416`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005497`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005497`

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
          v8 = (const char *)&qword_1800109C8;
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
0x1800052e4  mov     [rsp+arg_18], rbx
0x1800052e9  push    rbp
0x1800052ea  push    rsi
0x1800052eb  push    rdi
0x1800052ec  push    r14
0x1800052ee  push    r15
0x1800052f0  sub     rsp, 250h
0x1800052f7  mov     rax, cs:__security_cookie
0x1800052fe  xor     rax, rsp
0x180005301  mov     [rsp+278h+var_38], rax
0x180005309  xor     r15d, r15d
0x18000530c  mov     rbx, r8
0x18000530f  mov     rsi, rdx
0x180005312  mov     r14, rcx
0x180005315  test    rdx, rdx
0x180005318  jz      loc_180005571
0x18000531e  test    rcx, rcx
0x180005321  jz      loc_180005571
0x180005327  mov     rax, cs:g_pfnResultLoggingCallback
0x18000532e  mov     [rcx], r15w
0x180005332  test    rax, rax
0x180005335  jz      short loc_180005358
0x180005337  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000533e  jz      short loc_180005358
0x180005340  mov     r8, rdx
0x180005343  mov     rdx, rcx
0x180005346  mov     rcx, rbx
0x180005349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000534e  cmp     [r14], r15w
0x180005352  jnz     loc_180005571
0x180005358  mov     ecx, [rbx]
0x18000535a  mov     bpl, 8
0x18000535d  test    ecx, ecx
0x18000535f  jz      short loc_1800053AA
0x180005361  sub     ecx, 1
0x180005364  jz      short loc_180005392
0x180005366  sub     ecx, 1
0x180005369  jz      short loc_180005382
0x18000536b  cmp     ecx, 1
0x18000536e  jz      short loc_180005379
0x180005370  lea     rdi, qword_1800109C8
0x180005377  jmp     short loc_1800053B1
0x180005379  lea     rdi, aFailfast; "FailFast"
0x180005380  jmp     short loc_1800053B1
0x180005382  lea     rax, aLoghr; "LogHr"
0x180005389  lea     rdi, aLognt; "LogNt"
0x180005390  jmp     short loc_1800053A0
0x180005392  lea     rax, aReturnhr; "ReturnHr"
0x180005399  lea     rdi, aReturnnt; "ReturnNt"
0x1800053a0  test    [rbx+4], bpl
0x1800053a4  cmovz   rdi, rax
0x1800053a8  jmp     short loc_1800053B1
0x1800053aa  lea     rdi, aException; "Exception"
0x1800053b1  xor     edx, edx; Val
0x1800053b3  lea     rcx, [rsp+278h+Buffer]; void *
0x1800053b8  mov     r8d, 200h; Size
0x1800053be  call    memset_0
0x1800053c3  test    [rbx+4], bpl
0x1800053c7  jz      short loc_1800053EC
0x1800053c9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800053d0  mov     ebp, [rbx+0Ch]
0x1800053d3  test    rax, rax
0x1800053d6  jz      short loc_18000541C
0x1800053d8  mov     r8d, 100h
0x1800053de  lea     rdx, [rsp+278h+Buffer]
0x1800053e3  mov     ecx, ebp
0x1800053e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053ea  jmp     short loc_18000541C
0x1800053ec  mov     ebp, [rbx+8]
0x1800053ef  lea     rax, [rsp+278h+Buffer]
0x1800053f4  mov     [rsp+278h+Arguments], r15; Arguments
0x1800053f9  mov     r8d, ebp; dwMessageId
0x1800053fc  mov     [rsp+278h+nSize], 100h; nSize
0x180005404  mov     r9d, 400h; dwLanguageId
0x18000540a  xor     edx, edx; lpSource
0x18000540c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005411  mov     ecx, 1200h; dwFlags
0x180005416  call    cs:__imp_FormatMessageW
0x18000541c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005420  lea     rsi, [r14+rsi*2]
0x180005424  mov     rax, [rbx+88h]
0x18000542b  mov     rdx, rsi; unsigned __int16 *
0x18000542e  mov     rcx, [rbx+80h]
0x180005435  test    r9, r9
0x180005438  jz      short loc_18000545C
0x18000543a  mov     [rsp+278h+Arguments], rax
0x18000543f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005446  mov     eax, [rbx+40h]
0x180005449  mov     qword ptr [rsp+278h+nSize], rcx
0x18000544e  mov     rcx, r14; this
0x180005451  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005455  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000545a  jmp     short loc_180005473
0x18000545c  mov     r9, rcx; unsigned __int16 *
0x18000545f  mov     [rsp+278h+lpBuffer], rax
0x180005464  mov     rcx, r14; this
0x180005467  lea     r8, aHsP; "%hs!%p: "
0x18000546e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005473  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000547a  mov     r14, rax
0x18000547d  test    r9, r9
0x180005480  jz      short loc_180005497
0x180005482  lea     r8, aCallerP; "(caller: %p) "
0x180005489  mov     rdx, rsi; unsigned __int16 *
0x18000548c  mov     rcx, rax; this
0x18000548f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005494  mov     r14, rax
0x180005497  call    cs:__imp_GetCurrentThreadId
0x18000549d  lea     rcx, [rsp+278h+Buffer]
0x1800054a2  mov     r9, rdi; unsigned __int16 *
0x1800054a5  mov     [rsp+278h+var_240], rcx
0x1800054aa  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800054b1  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800054b5  mov     rdx, rsi; unsigned __int16 *
0x1800054b8  mov     [rsp+278h+nSize], eax
0x1800054bc  mov     rcx, r14; this
0x1800054bf  mov     eax, [rbx+44h]
0x1800054c2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800054c6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800054cb  cmp     [rbx+18h], r15
0x1800054cf  jnz     short loc_1800054E1
0x1800054d1  cmp     [rbx+48h], r15
0x1800054d5  jnz     short loc_1800054E1
0x1800054d7  cmp     [rbx+30h], r15
0x1800054db  jz      loc_180005571
0x1800054e1  lea     r8, asc_180010690; "    "
0x1800054e8  mov     rdx, rsi; unsigned __int16 *
0x1800054eb  mov     rcx, rax; this
0x1800054ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800054f3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800054f7  test    r9, r9
0x1800054fa  jz      short loc_18000550E
0x1800054fc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005503  mov     rdx, rsi; unsigned __int16 *
0x180005506  mov     rcx, rax; this
0x180005509  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000550e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005512  test    r9, r9
0x180005515  jz      short loc_180005529
0x180005517  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000551e  mov     rdx, rsi; unsigned __int16 *
0x180005521  mov     rcx, rax; this
0x180005524  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005529  mov     rcx, [rbx+28h]
0x18000552d  mov     rdx, rsi; unsigned __int16 *
0x180005530  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005534  test    rcx, rcx
0x180005537  jz      short loc_18000554F
0x180005539  mov     [rsp+278h+lpBuffer], rcx
0x18000553e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005545  mov     rcx, rax; this
0x180005548  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000554d  jmp     short loc_180005571
0x18000554f  mov     rcx, rax; this
0x180005552  test    r9, r9
0x180005555  jz      short loc_180005565
0x180005557  lea     r8, aHs; "[%hs]\n"
0x18000555e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005563  jmp     short loc_180005571
0x180005565  lea     r8, asc_180010708; "\n"
0x18000556c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005571  xor     eax, eax
0x180005573  mov     rcx, [rsp+278h+var_38]
0x18000557b  xor     rcx, rsp; StackCookie
0x18000557e  call    __security_check_cookie
0x180005583  mov     rbx, [rsp+278h+arg_18]
0x18000558b  add     rsp, 250h
0x180005592  pop     r15
0x180005594  pop     r14
0x180005596  pop     rdi
0x180005597  pop     rsi
0x180005598  pop     rbp
0x180005599  retn
```
