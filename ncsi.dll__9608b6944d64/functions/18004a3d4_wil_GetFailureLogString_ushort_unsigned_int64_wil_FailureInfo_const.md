# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18004a3d4`
- end: `0x18004a68a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18004a7e4`
- `0x18004b080`
- `0x18004bca8`
- `0x18004d60c`

## callees

- `0x180047240`
- `0x180047f78`
- `0x18004a3d4`
- `0x18004a778`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004a587`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004a587`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18004a506`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18004a506`

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
          v7 = (const char *)&qword_18007F760;
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
0x18004a3d4  mov     [rsp+arg_18], rbx
0x18004a3d9  push    rbp
0x18004a3da  push    rsi
0x18004a3db  push    rdi
0x18004a3dc  push    r14
0x18004a3de  push    r15
0x18004a3e0  sub     rsp, 250h
0x18004a3e7  mov     rax, cs:__security_cookie
0x18004a3ee  xor     rax, rsp
0x18004a3f1  mov     [rsp+278h+var_38], rax
0x18004a3f9  mov     rbx, r8
0x18004a3fc  mov     rsi, rdx
0x18004a3ff  mov     r14, rcx
0x18004a402  xor     r15d, r15d
0x18004a405  test    rdx, rdx
0x18004a408  jz      loc_18004A661
0x18004a40e  test    rcx, rcx
0x18004a411  jz      loc_18004A661
0x18004a417  mov     [rcx], r15w
0x18004a41b  mov     rax, cs:g_pfnResultLoggingCallback
0x18004a422  test    rax, rax
0x18004a425  jz      short loc_18004A448
0x18004a427  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18004a42e  jz      short loc_18004A448
0x18004a430  mov     r8, rdx
0x18004a433  mov     rdx, rcx
0x18004a436  mov     rcx, rbx
0x18004a439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a43e  cmp     [r14], r15w
0x18004a442  jnz     loc_18004A661
0x18004a448  mov     ecx, [rbx]
0x18004a44a  mov     bpl, 8
0x18004a44d  test    ecx, ecx
0x18004a44f  jz      short loc_18004A49A
0x18004a451  sub     ecx, 1
0x18004a454  jz      short loc_18004A482
0x18004a456  sub     ecx, 1
0x18004a459  jz      short loc_18004A472
0x18004a45b  cmp     ecx, 1
0x18004a45e  jz      short loc_18004A469
0x18004a460  lea     rdi, qword_18007F760
0x18004a467  jmp     short loc_18004A4A1
0x18004a469  lea     rdi, aFailfast; "FailFast"
0x18004a470  jmp     short loc_18004A4A1
0x18004a472  lea     rax, aLoghr; "LogHr"
0x18004a479  lea     rdi, aLognt; "LogNt"
0x18004a480  jmp     short loc_18004A490
0x18004a482  lea     rax, aReturnhr; "ReturnHr"
0x18004a489  lea     rdi, aReturnnt; "ReturnNt"
0x18004a490  test    [rbx+4], bpl
0x18004a494  cmovz   rdi, rax
0x18004a498  jmp     short loc_18004A4A1
0x18004a49a  lea     rdi, aException; "Exception"
0x18004a4a1  xor     edx, edx; Val
0x18004a4a3  mov     r8d, 200h; Size
0x18004a4a9  lea     rcx, [rsp+278h+Buffer]; void *
0x18004a4ae  call    memset_0
0x18004a4b3  test    [rbx+4], bpl
0x18004a4b7  jz      short loc_18004A4DC
0x18004a4b9  mov     ebp, [rbx+0Ch]
0x18004a4bc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18004a4c3  test    rax, rax
0x18004a4c6  jz      short loc_18004A50C
0x18004a4c8  mov     r8d, 100h
0x18004a4ce  lea     rdx, [rsp+278h+Buffer]
0x18004a4d3  mov     ecx, ebp
0x18004a4d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a4da  jmp     short loc_18004A50C
0x18004a4dc  mov     ebp, [rbx+8]
0x18004a4df  mov     [rsp+278h+Arguments], r15; Arguments
0x18004a4e4  mov     [rsp+278h+nSize], 100h; nSize
0x18004a4ec  lea     rax, [rsp+278h+Buffer]
0x18004a4f1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18004a4f6  mov     r9d, 400h; dwLanguageId
0x18004a4fc  mov     r8d, ebp; dwMessageId
0x18004a4ff  xor     edx, edx; lpSource
0x18004a501  mov     ecx, 1200h; dwFlags
0x18004a506  call    cs:__imp_FormatMessageW
0x18004a50c  lea     rsi, [r14+rsi*2]
0x18004a510  mov     r9, [rbx+38h]; unsigned __int16 *
0x18004a514  mov     rax, [rbx+88h]
0x18004a51b  mov     rcx, [rbx+80h]
0x18004a522  mov     rdx, rsi; unsigned __int16 *
0x18004a525  test    r9, r9
0x18004a528  jz      short loc_18004A54C
0x18004a52a  mov     [rsp+278h+Arguments], rax
0x18004a52f  mov     qword ptr [rsp+278h+nSize], rcx
0x18004a534  mov     eax, [rbx+40h]
0x18004a537  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18004a53b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18004a542  mov     rcx, r14; this
0x18004a545  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004a54a  jmp     short loc_18004A563
0x18004a54c  mov     [rsp+278h+lpBuffer], rax
0x18004a551  mov     r9, rcx; unsigned __int16 *
0x18004a554  lea     r8, aHsP; "%hs!%p: "
0x18004a55b  mov     rcx, r14; this
0x18004a55e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004a563  mov     r14, rax
0x18004a566  mov     r9, [rbx+90h]; unsigned __int16 *
0x18004a56d  test    r9, r9
0x18004a570  jz      short loc_18004A587
0x18004a572  lea     r8, aCallerP; "(caller: %p) "
0x18004a579  mov     rdx, rsi; unsigned __int16 *
0x18004a57c  mov     rcx, rax; this
0x18004a57f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004a584  mov     r14, rax
0x18004a587  call    cs:__imp_GetCurrentThreadId
0x18004a58d  lea     rcx, [rsp+278h+Buffer]
0x18004a592  mov     [rsp+278h+var_240], rcx
0x18004a597  mov     dword ptr [rsp+278h+Arguments], ebp
0x18004a59b  mov     [rsp+278h+nSize], eax
0x18004a59f  mov     eax, [rbx+44h]
0x18004a5a2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18004a5a6  mov     r9, rdi; unsigned __int16 *
0x18004a5a9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18004a5b0  mov     rdx, rsi; unsigned __int16 *
0x18004a5b3  mov     rcx, r14; this
0x18004a5b6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004a5bb  cmp     [rbx+18h], r15
0x18004a5bf  jnz     short loc_18004A5D1
0x18004a5c1  cmp     [rbx+48h], r15
0x18004a5c5  jnz     short loc_18004A5D1
0x18004a5c7  cmp     [rbx+30h], r15
0x18004a5cb  jz      loc_18004A661
0x18004a5d1  lea     r8, asc_180080BF0; "    "
0x18004a5d8  mov     rdx, rsi; unsigned __int16 *
0x18004a5db  mov     rcx, rax; this
0x18004a5de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004a5e3  mov     r9, [rbx+18h]; unsigned __int16 *
0x18004a5e7  test    r9, r9
0x18004a5ea  jz      short loc_18004A5FE
0x18004a5ec  lea     r8, aMsgWs; "Msg:[%ws] "
0x18004a5f3  mov     rdx, rsi; unsigned __int16 *
0x18004a5f6  mov     rcx, rax; this
0x18004a5f9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004a5fe  mov     r9, [rbx+48h]; unsigned __int16 *
0x18004a602  test    r9, r9
0x18004a605  jz      short loc_18004A619
0x18004a607  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18004a60e  mov     rdx, rsi; unsigned __int16 *
0x18004a611  mov     rcx, rax; this
0x18004a614  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004a619  mov     rcx, [rbx+28h]
0x18004a61d  mov     r9, [rbx+30h]; unsigned __int16 *
0x18004a621  mov     rdx, rsi; unsigned __int16 *
0x18004a624  test    rcx, rcx
0x18004a627  jz      short loc_18004A63F
0x18004a629  mov     [rsp+278h+lpBuffer], rcx
0x18004a62e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18004a635  mov     rcx, rax; this
0x18004a638  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004a63d  jmp     short loc_18004A661
0x18004a63f  mov     rcx, rax; this
0x18004a642  test    r9, r9
0x18004a645  jz      short loc_18004A655
0x18004a647  lea     r8, aHs; "[%hs]\n"
0x18004a64e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004a653  jmp     short loc_18004A661
0x18004a655  lea     r8, asc_180080C68; "\n"
0x18004a65c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004a661  xor     eax, eax
0x18004a663  mov     rcx, [rsp+278h+var_38]
0x18004a66b  xor     rcx, rsp; StackCookie
0x18004a66e  call    __security_check_cookie
0x18004a673  mov     rbx, [rsp+278h+arg_18]
0x18004a67b  add     rsp, 250h
0x18004a682  pop     r15
0x18004a684  pop     r14
0x18004a686  pop     rdi
0x18004a687  pop     rsi
0x18004a688  pop     rbp
0x18004a689  retn
```
