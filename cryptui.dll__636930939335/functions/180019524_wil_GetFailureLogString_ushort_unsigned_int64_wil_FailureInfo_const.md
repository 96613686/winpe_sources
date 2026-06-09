# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180019524`
- end: `0x1800197da`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180015df8`
- `0x18001a454`
- `0x18001d820`

## callees

- `0x180019524`
- `0x18001a754`
- `0x18003e582`
- `0x18003e5c0`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800196d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800196d7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180019656`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180019656`

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
          v7 = byte_1800451D4;
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
0x180019524  mov     [rsp+arg_18], rbx
0x180019529  push    rbp
0x18001952a  push    rsi
0x18001952b  push    rdi
0x18001952c  push    r14
0x18001952e  push    r15
0x180019530  sub     rsp, 250h
0x180019537  mov     rax, cs:__security_cookie
0x18001953e  xor     rax, rsp
0x180019541  mov     [rsp+278h+var_38], rax
0x180019549  mov     rbx, r8
0x18001954c  mov     rsi, rdx
0x18001954f  mov     r14, rcx
0x180019552  xor     r15d, r15d
0x180019555  test    rdx, rdx
0x180019558  jz      loc_1800197B1
0x18001955e  test    rcx, rcx
0x180019561  jz      loc_1800197B1
0x180019567  mov     [rcx], r15w
0x18001956b  mov     rax, cs:g_pfnResultLoggingCallback
0x180019572  test    rax, rax
0x180019575  jz      short loc_180019598
0x180019577  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001957e  jz      short loc_180019598
0x180019580  mov     r8, rdx
0x180019583  mov     rdx, rcx
0x180019586  mov     rcx, rbx
0x180019589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001958e  cmp     [r14], r15w
0x180019592  jnz     loc_1800197B1
0x180019598  mov     ecx, [rbx]
0x18001959a  mov     bpl, 8
0x18001959d  test    ecx, ecx
0x18001959f  jz      short loc_1800195EA
0x1800195a1  sub     ecx, 1
0x1800195a4  jz      short loc_1800195D2
0x1800195a6  sub     ecx, 1
0x1800195a9  jz      short loc_1800195C2
0x1800195ab  cmp     ecx, 1
0x1800195ae  jz      short loc_1800195B9
0x1800195b0  lea     rdi, byte_1800451D4
0x1800195b7  jmp     short loc_1800195F1
0x1800195b9  lea     rdi, aFailfast; "FailFast"
0x1800195c0  jmp     short loc_1800195F1
0x1800195c2  lea     rax, aLoghr; "LogHr"
0x1800195c9  lea     rdi, aLognt; "LogNt"
0x1800195d0  jmp     short loc_1800195E0
0x1800195d2  lea     rax, aReturnhr; "ReturnHr"
0x1800195d9  lea     rdi, aReturnnt; "ReturnNt"
0x1800195e0  test    [rbx+4], bpl
0x1800195e4  cmovz   rdi, rax
0x1800195e8  jmp     short loc_1800195F1
0x1800195ea  lea     rdi, aException; "Exception"
0x1800195f1  xor     edx, edx; Val
0x1800195f3  mov     r8d, 200h; Size
0x1800195f9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800195fe  call    memset_0
0x180019603  test    [rbx+4], bpl
0x180019607  jz      short loc_18001962C
0x180019609  mov     ebp, [rbx+0Ch]
0x18001960c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180019613  test    rax, rax
0x180019616  jz      short loc_18001965C
0x180019618  mov     r8d, 100h
0x18001961e  lea     rdx, [rsp+278h+Buffer]
0x180019623  mov     ecx, ebp
0x180019625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001962a  jmp     short loc_18001965C
0x18001962c  mov     ebp, [rbx+8]
0x18001962f  mov     [rsp+278h+Arguments], r15; Arguments
0x180019634  mov     [rsp+278h+nSize], 100h; nSize
0x18001963c  lea     rax, [rsp+278h+Buffer]
0x180019641  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180019646  mov     r9d, 400h; dwLanguageId
0x18001964c  mov     r8d, ebp; dwMessageId
0x18001964f  xor     edx, edx; lpSource
0x180019651  mov     ecx, 1200h; dwFlags
0x180019656  call    cs:__imp_FormatMessageW
0x18001965c  lea     rsi, [r14+rsi*2]
0x180019660  mov     r9, [rbx+38h]; unsigned __int16 *
0x180019664  mov     rax, [rbx+88h]
0x18001966b  mov     rcx, [rbx+80h]
0x180019672  mov     rdx, rsi; unsigned __int16 *
0x180019675  test    r9, r9
0x180019678  jz      short loc_18001969C
0x18001967a  mov     [rsp+278h+Arguments], rax
0x18001967f  mov     qword ptr [rsp+278h+nSize], rcx
0x180019684  mov     eax, [rbx+40h]
0x180019687  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001968b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180019692  mov     rcx, r14; this
0x180019695  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001969a  jmp     short loc_1800196B3
0x18001969c  mov     [rsp+278h+lpBuffer], rax
0x1800196a1  mov     r9, rcx; unsigned __int16 *
0x1800196a4  lea     r8, aHsP; "%hs!%p: "
0x1800196ab  mov     rcx, r14; this
0x1800196ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800196b3  mov     r14, rax
0x1800196b6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800196bd  test    r9, r9
0x1800196c0  jz      short loc_1800196D7
0x1800196c2  lea     r8, aCallerP; "(caller: %p) "
0x1800196c9  mov     rdx, rsi; unsigned __int16 *
0x1800196cc  mov     rcx, rax; this
0x1800196cf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800196d4  mov     r14, rax
0x1800196d7  call    cs:__imp_GetCurrentThreadId
0x1800196dd  lea     rcx, [rsp+278h+Buffer]
0x1800196e2  mov     [rsp+278h+var_240], rcx
0x1800196e7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800196eb  mov     [rsp+278h+nSize], eax
0x1800196ef  mov     eax, [rbx+44h]
0x1800196f2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800196f6  mov     r9, rdi; unsigned __int16 *
0x1800196f9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180019700  mov     rdx, rsi; unsigned __int16 *
0x180019703  mov     rcx, r14; this
0x180019706  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001970b  cmp     [rbx+18h], r15
0x18001970f  jnz     short loc_180019721
0x180019711  cmp     [rbx+48h], r15
0x180019715  jnz     short loc_180019721
0x180019717  cmp     [rbx+30h], r15
0x18001971b  jz      loc_1800197B1
0x180019721  lea     r8, asc_1800452C0; "    "
0x180019728  mov     rdx, rsi; unsigned __int16 *
0x18001972b  mov     rcx, rax; this
0x18001972e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180019733  mov     r9, [rbx+18h]; unsigned __int16 *
0x180019737  test    r9, r9
0x18001973a  jz      short loc_18001974E
0x18001973c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180019743  mov     rdx, rsi; unsigned __int16 *
0x180019746  mov     rcx, rax; this
0x180019749  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001974e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180019752  test    r9, r9
0x180019755  jz      short loc_180019769
0x180019757  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001975e  mov     rdx, rsi; unsigned __int16 *
0x180019761  mov     rcx, rax; this
0x180019764  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180019769  mov     rcx, [rbx+28h]
0x18001976d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180019771  mov     rdx, rsi; unsigned __int16 *
0x180019774  test    rcx, rcx
0x180019777  jz      short loc_18001978F
0x180019779  mov     [rsp+278h+lpBuffer], rcx
0x18001977e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180019785  mov     rcx, rax; this
0x180019788  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001978d  jmp     short loc_1800197B1
0x18001978f  mov     rcx, rax; this
0x180019792  test    r9, r9
0x180019795  jz      short loc_1800197A5
0x180019797  lea     r8, aHs; "[%hs]\n"
0x18001979e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800197a3  jmp     short loc_1800197B1
0x1800197a5  lea     r8, asc_180045338; "\n"
0x1800197ac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800197b1  xor     eax, eax
0x1800197b3  mov     rcx, [rsp+278h+var_38]
0x1800197bb  xor     rcx, rsp; StackCookie
0x1800197be  call    __security_check_cookie
0x1800197c3  mov     rbx, [rsp+278h+arg_18]
0x1800197cb  add     rsp, 250h
0x1800197d2  pop     r15
0x1800197d4  pop     r14
0x1800197d6  pop     rdi
0x1800197d7  pop     rsi
0x1800197d8  pop     rbp
0x1800197d9  retn
```
