# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000a3b8`
- end: `0x18000a66e`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180007b54`
- `0x18000b484`
- `0x18000b9f4`
- `0x18000f8c0`
- `0x180010a84`

## callees

- `0x180006330`
- `0x180006e9c`
- `0x18000a3b8`
- `0x18000b784`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a56b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a56b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a4ea`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a4ea`

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
          v7 = (const char *)&dword_18002483C;
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
0x18000a3b8  mov     [rsp+arg_18], rbx
0x18000a3bd  push    rbp
0x18000a3be  push    rsi
0x18000a3bf  push    rdi
0x18000a3c0  push    r14
0x18000a3c2  push    r15
0x18000a3c4  sub     rsp, 250h
0x18000a3cb  mov     rax, cs:__security_cookie
0x18000a3d2  xor     rax, rsp
0x18000a3d5  mov     [rsp+278h+var_38], rax
0x18000a3dd  mov     rbx, r8
0x18000a3e0  mov     rsi, rdx
0x18000a3e3  mov     r14, rcx
0x18000a3e6  xor     r15d, r15d
0x18000a3e9  test    rdx, rdx
0x18000a3ec  jz      loc_18000A645
0x18000a3f2  test    rcx, rcx
0x18000a3f5  jz      loc_18000A645
0x18000a3fb  mov     [rcx], r15w
0x18000a3ff  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a406  test    rax, rax
0x18000a409  jz      short loc_18000A42C
0x18000a40b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000a412  jz      short loc_18000A42C
0x18000a414  mov     r8, rdx
0x18000a417  mov     rdx, rcx
0x18000a41a  mov     rcx, rbx
0x18000a41d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a422  cmp     [r14], r15w
0x18000a426  jnz     loc_18000A645
0x18000a42c  mov     ecx, [rbx]
0x18000a42e  mov     bpl, 8
0x18000a431  test    ecx, ecx
0x18000a433  jz      short loc_18000A47E
0x18000a435  sub     ecx, 1
0x18000a438  jz      short loc_18000A466
0x18000a43a  sub     ecx, 1
0x18000a43d  jz      short loc_18000A456
0x18000a43f  cmp     ecx, 1
0x18000a442  jz      short loc_18000A44D
0x18000a444  lea     rdi, dword_18002483C
0x18000a44b  jmp     short loc_18000A485
0x18000a44d  lea     rdi, aFailfast; "FailFast"
0x18000a454  jmp     short loc_18000A485
0x18000a456  lea     rax, aLoghr; "LogHr"
0x18000a45d  lea     rdi, aLognt; "LogNt"
0x18000a464  jmp     short loc_18000A474
0x18000a466  lea     rax, aReturnhr; "ReturnHr"
0x18000a46d  lea     rdi, aReturnnt; "ReturnNt"
0x18000a474  test    [rbx+4], bpl
0x18000a478  cmovz   rdi, rax
0x18000a47c  jmp     short loc_18000A485
0x18000a47e  lea     rdi, aException; "Exception"
0x18000a485  xor     edx, edx; Val
0x18000a487  mov     r8d, 200h; Size
0x18000a48d  lea     rcx, [rsp+278h+Buffer]; void *
0x18000a492  call    memset_0
0x18000a497  test    [rbx+4], bpl
0x18000a49b  jz      short loc_18000A4C0
0x18000a49d  mov     ebp, [rbx+0Ch]
0x18000a4a0  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000a4a7  test    rax, rax
0x18000a4aa  jz      short loc_18000A4F0
0x18000a4ac  mov     r8d, 100h
0x18000a4b2  lea     rdx, [rsp+278h+Buffer]
0x18000a4b7  mov     ecx, ebp
0x18000a4b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4be  jmp     short loc_18000A4F0
0x18000a4c0  mov     ebp, [rbx+8]
0x18000a4c3  mov     [rsp+278h+Arguments], r15; Arguments
0x18000a4c8  mov     [rsp+278h+nSize], 100h; nSize
0x18000a4d0  lea     rax, [rsp+278h+Buffer]
0x18000a4d5  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000a4da  mov     r9d, 400h; dwLanguageId
0x18000a4e0  mov     r8d, ebp; dwMessageId
0x18000a4e3  xor     edx, edx; lpSource
0x18000a4e5  mov     ecx, 1200h; dwFlags
0x18000a4ea  call    cs:__imp_FormatMessageW
0x18000a4f0  lea     rsi, [r14+rsi*2]
0x18000a4f4  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000a4f8  mov     rax, [rbx+88h]
0x18000a4ff  mov     rcx, [rbx+80h]
0x18000a506  mov     rdx, rsi; unsigned __int16 *
0x18000a509  test    r9, r9
0x18000a50c  jz      short loc_18000A530
0x18000a50e  mov     [rsp+278h+Arguments], rax
0x18000a513  mov     qword ptr [rsp+278h+nSize], rcx
0x18000a518  mov     eax, [rbx+40h]
0x18000a51b  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000a51f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000a526  mov     rcx, r14; this
0x18000a529  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a52e  jmp     short loc_18000A547
0x18000a530  mov     [rsp+278h+lpBuffer], rax
0x18000a535  mov     r9, rcx; unsigned __int16 *
0x18000a538  lea     r8, aHsP; "%hs!%p: "
0x18000a53f  mov     rcx, r14; this
0x18000a542  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a547  mov     r14, rax
0x18000a54a  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000a551  test    r9, r9
0x18000a554  jz      short loc_18000A56B
0x18000a556  lea     r8, aCallerP; "(caller: %p) "
0x18000a55d  mov     rdx, rsi; unsigned __int16 *
0x18000a560  mov     rcx, rax; this
0x18000a563  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a568  mov     r14, rax
0x18000a56b  call    cs:__imp_GetCurrentThreadId
0x18000a571  lea     rcx, [rsp+278h+Buffer]
0x18000a576  mov     [rsp+278h+var_240], rcx
0x18000a57b  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000a57f  mov     [rsp+278h+nSize], eax
0x18000a583  mov     eax, [rbx+44h]
0x18000a586  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000a58a  mov     r9, rdi; unsigned __int16 *
0x18000a58d  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000a594  mov     rdx, rsi; unsigned __int16 *
0x18000a597  mov     rcx, r14; this
0x18000a59a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a59f  cmp     [rbx+18h], r15
0x18000a5a3  jnz     short loc_18000A5B5
0x18000a5a5  cmp     [rbx+48h], r15
0x18000a5a9  jnz     short loc_18000A5B5
0x18000a5ab  cmp     [rbx+30h], r15
0x18000a5af  jz      loc_18000A645
0x18000a5b5  lea     r8, asc_180024948; "    "
0x18000a5bc  mov     rdx, rsi; unsigned __int16 *
0x18000a5bf  mov     rcx, rax; this
0x18000a5c2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a5c7  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000a5cb  test    r9, r9
0x18000a5ce  jz      short loc_18000A5E2
0x18000a5d0  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000a5d7  mov     rdx, rsi; unsigned __int16 *
0x18000a5da  mov     rcx, rax; this
0x18000a5dd  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a5e2  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000a5e6  test    r9, r9
0x18000a5e9  jz      short loc_18000A5FD
0x18000a5eb  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000a5f2  mov     rdx, rsi; unsigned __int16 *
0x18000a5f5  mov     rcx, rax; this
0x18000a5f8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a5fd  mov     rcx, [rbx+28h]
0x18000a601  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000a605  mov     rdx, rsi; unsigned __int16 *
0x18000a608  test    rcx, rcx
0x18000a60b  jz      short loc_18000A623
0x18000a60d  mov     [rsp+278h+lpBuffer], rcx
0x18000a612  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000a619  mov     rcx, rax; this
0x18000a61c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a621  jmp     short loc_18000A645
0x18000a623  mov     rcx, rax; this
0x18000a626  test    r9, r9
0x18000a629  jz      short loc_18000A639
0x18000a62b  lea     r8, aHs; "[%hs]\n"
0x18000a632  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a637  jmp     short loc_18000A645
0x18000a639  lea     r8, asc_1800249C0; "\n"
0x18000a640  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a645  xor     eax, eax
0x18000a647  mov     rcx, [rsp+278h+var_38]
0x18000a64f  xor     rcx, rsp; StackCookie
0x18000a652  call    __security_check_cookie
0x18000a657  mov     rbx, [rsp+278h+arg_18]
0x18000a65f  add     rsp, 250h
0x18000a666  pop     r15
0x18000a668  pop     r14
0x18000a66a  pop     rdi
0x18000a66b  pop     rsi
0x18000a66c  pop     rbp
0x18000a66d  retn
```
