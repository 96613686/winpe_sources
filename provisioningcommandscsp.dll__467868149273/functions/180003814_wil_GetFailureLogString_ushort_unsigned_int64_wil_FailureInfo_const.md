# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180003814`
- end: `0x180003ad7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x1800025b0`
- `0x180002844`
- `0x180004210`
- `0x180006100`
- `0x1800067ac`
- `0x18000d20a`
- `0x18000d33e`

## callees

- `0x180003814`
- `0x180004524`
- `0x18000cc8e`
- `0x18000ccc0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800039cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800039cd`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003946`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003946`

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
      g_pfnResultLoggingCallback(a3, this, a2, a4);
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
          v7 = (const char *)&qword_18000FC10;
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
0x180003814  mov     [rsp+arg_18], rbx
0x180003819  push    rbp
0x18000381a  push    rsi
0x18000381b  push    rdi
0x18000381c  push    r14
0x18000381e  push    r15
0x180003820  sub     rsp, 250h
0x180003827  mov     rax, cs:__security_cookie
0x18000382e  xor     rax, rsp
0x180003831  mov     [rsp+278h+var_38], rax
0x180003839  mov     rbx, r8
0x18000383c  mov     rsi, rdx
0x18000383f  mov     r14, rcx
0x180003842  xor     r15d, r15d
0x180003845  test    rdx, rdx
0x180003848  jz      loc_180003AAD
0x18000384e  test    rcx, rcx
0x180003851  jz      loc_180003AAD
0x180003857  mov     [rcx], r15w
0x18000385b  mov     rax, cs:g_pfnResultLoggingCallback
0x180003862  test    rax, rax
0x180003865  jz      short loc_180003888
0x180003867  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000386e  jz      short loc_180003888
0x180003870  mov     r8, rdx
0x180003873  mov     rdx, rcx
0x180003876  mov     rcx, rbx
0x180003879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000387e  cmp     [r14], r15w
0x180003882  jnz     loc_180003AAD
0x180003888  mov     ecx, [rbx]
0x18000388a  mov     bpl, 8
0x18000388d  test    ecx, ecx
0x18000388f  jz      short loc_1800038DA
0x180003891  sub     ecx, 1
0x180003894  jz      short loc_1800038C2
0x180003896  sub     ecx, 1
0x180003899  jz      short loc_1800038B2
0x18000389b  cmp     ecx, 1
0x18000389e  jz      short loc_1800038A9
0x1800038a0  lea     rdi, qword_18000FC10
0x1800038a7  jmp     short loc_1800038E1
0x1800038a9  lea     rdi, aFailfast; "FailFast"
0x1800038b0  jmp     short loc_1800038E1
0x1800038b2  lea     rax, aLoghr; "LogHr"
0x1800038b9  lea     rdi, aLognt; "LogNt"
0x1800038c0  jmp     short loc_1800038D0
0x1800038c2  lea     rax, aReturnhr; "ReturnHr"
0x1800038c9  lea     rdi, aReturnnt; "ReturnNt"
0x1800038d0  test    [rbx+4], bpl
0x1800038d4  cmovz   rdi, rax
0x1800038d8  jmp     short loc_1800038E1
0x1800038da  lea     rdi, aException; "Exception"
0x1800038e1  xor     edx, edx; Val
0x1800038e3  mov     r8d, 200h; Size
0x1800038e9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800038ee  call    memset_0
0x1800038f3  test    [rbx+4], bpl
0x1800038f7  jz      short loc_18000391C
0x1800038f9  mov     ebp, [rbx+0Ch]
0x1800038fc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180003903  test    rax, rax
0x180003906  jz      short loc_180003952
0x180003908  mov     r8d, 100h
0x18000390e  lea     rdx, [rsp+278h+Buffer]
0x180003913  mov     ecx, ebp
0x180003915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000391a  jmp     short loc_180003952
0x18000391c  mov     ebp, [rbx+8]
0x18000391f  mov     [rsp+278h+Arguments], r15; Arguments
0x180003924  mov     [rsp+278h+nSize], 100h; nSize
0x18000392c  lea     rax, [rsp+278h+Buffer]
0x180003931  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180003936  mov     r9d, 400h; dwLanguageId
0x18000393c  mov     r8d, ebp; dwMessageId
0x18000393f  xor     edx, edx; lpSource
0x180003941  mov     ecx, 1200h; dwFlags
0x180003946  call    cs:__imp_FormatMessageW
0x18000394d  nop     dword ptr [rax+rax+00h]
0x180003952  lea     rsi, [r14+rsi*2]
0x180003956  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000395a  mov     rax, [rbx+88h]
0x180003961  mov     rcx, [rbx+80h]
0x180003968  mov     rdx, rsi; unsigned __int16 *
0x18000396b  test    r9, r9
0x18000396e  jz      short loc_180003992
0x180003970  mov     [rsp+278h+Arguments], rax
0x180003975  mov     qword ptr [rsp+278h+nSize], rcx
0x18000397a  mov     eax, [rbx+40h]
0x18000397d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003981  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180003988  mov     rcx, r14; this
0x18000398b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003990  jmp     short loc_1800039A9
0x180003992  mov     [rsp+278h+lpBuffer], rax
0x180003997  mov     r9, rcx; unsigned __int16 *
0x18000399a  lea     r8, aHsP; "%hs!%p: "
0x1800039a1  mov     rcx, r14; this
0x1800039a4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800039a9  mov     r14, rax
0x1800039ac  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800039b3  test    r9, r9
0x1800039b6  jz      short loc_1800039CD
0x1800039b8  lea     r8, aCallerP; "(caller: %p) "
0x1800039bf  mov     rdx, rsi; unsigned __int16 *
0x1800039c2  mov     rcx, rax; this
0x1800039c5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800039ca  mov     r14, rax
0x1800039cd  call    cs:__imp_GetCurrentThreadId
0x1800039d4  nop     dword ptr [rax+rax+00h]
0x1800039d9  lea     rcx, [rsp+278h+Buffer]
0x1800039de  mov     [rsp+278h+var_240], rcx
0x1800039e3  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800039e7  mov     [rsp+278h+nSize], eax
0x1800039eb  mov     eax, [rbx+44h]
0x1800039ee  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800039f2  mov     r9, rdi; unsigned __int16 *
0x1800039f5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800039fc  mov     rdx, rsi; unsigned __int16 *
0x1800039ff  mov     rcx, r14; this
0x180003a02  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a07  cmp     [rbx+18h], r15
0x180003a0b  jnz     short loc_180003A1D
0x180003a0d  cmp     [rbx+48h], r15
0x180003a11  jnz     short loc_180003A1D
0x180003a13  cmp     [rbx+30h], r15
0x180003a17  jz      loc_180003AAD
0x180003a1d  lea     r8, asc_18000FD48; "    "
0x180003a24  mov     rdx, rsi; unsigned __int16 *
0x180003a27  mov     rcx, rax; this
0x180003a2a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a2f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180003a33  test    r9, r9
0x180003a36  jz      short loc_180003A4A
0x180003a38  lea     r8, aMsgWs; "Msg:[%ws] "
0x180003a3f  mov     rdx, rsi; unsigned __int16 *
0x180003a42  mov     rcx, rax; this
0x180003a45  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a4a  mov     r9, [rbx+48h]; unsigned __int16 *
0x180003a4e  test    r9, r9
0x180003a51  jz      short loc_180003A65
0x180003a53  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180003a5a  mov     rdx, rsi; unsigned __int16 *
0x180003a5d  mov     rcx, rax; this
0x180003a60  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a65  mov     rcx, [rbx+28h]
0x180003a69  mov     r9, [rbx+30h]; unsigned __int16 *
0x180003a6d  mov     rdx, rsi; unsigned __int16 *
0x180003a70  test    rcx, rcx
0x180003a73  jz      short loc_180003A8B
0x180003a75  mov     [rsp+278h+lpBuffer], rcx
0x180003a7a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180003a81  mov     rcx, rax; this
0x180003a84  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a89  jmp     short loc_180003AAD
0x180003a8b  mov     rcx, rax; this
0x180003a8e  test    r9, r9
0x180003a91  jz      short loc_180003AA1
0x180003a93  lea     r8, aHs; "[%hs]\n"
0x180003a9a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a9f  jmp     short loc_180003AAD
0x180003aa1  lea     r8, asc_18000FDC0; "\n"
0x180003aa8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003aad  xor     eax, eax
0x180003aaf  mov     rcx, [rsp+278h+var_38]
0x180003ab7  xor     rcx, rsp; StackCookie
0x180003aba  call    __security_check_cookie
0x180003abf  mov     rbx, [rsp+278h+arg_18]
0x180003ac7  add     rsp, 250h
0x180003ace  pop     r15
0x180003ad0  pop     r14
0x180003ad2  pop     rdi
0x180003ad3  pop     rsi
0x180003ad4  pop     rbp
0x180003ad5  retn
```
