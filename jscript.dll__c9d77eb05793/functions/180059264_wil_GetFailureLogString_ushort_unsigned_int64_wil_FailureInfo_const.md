# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180059264`
- end: `0x18005951a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18005879c`
- `0x180059850`

## callees

- `0x180059264`
- `0x180059b50`
- `0x18009429a`
- `0x1800942d0`
- `0x180096010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180059417`
- `KERNEL32!GetCurrentThreadId` at `0x180059417`
- `KERNEL32!FormatMessageW` at `0x180059396`
- `KERNEL32!FormatMessageW` at `0x180059396`

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
          v8 = (const char *)&dword_1800A2364;
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
0x180059264  mov     [rsp+arg_18], rbx
0x180059269  push    rbp
0x18005926a  push    rsi
0x18005926b  push    rdi
0x18005926c  push    r14
0x18005926e  push    r15
0x180059270  sub     rsp, 250h
0x180059277  mov     rax, cs:__security_cookie
0x18005927e  xor     rax, rsp
0x180059281  mov     [rsp+278h+var_38], rax
0x180059289  xor     r15d, r15d
0x18005928c  mov     rbx, r8
0x18005928f  mov     rsi, rdx
0x180059292  mov     r14, rcx
0x180059295  test    rdx, rdx
0x180059298  jz      loc_1800594F1
0x18005929e  test    rcx, rcx
0x1800592a1  jz      loc_1800594F1
0x1800592a7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800592ae  mov     [rcx], r15w
0x1800592b2  test    rax, rax
0x1800592b5  jz      short loc_1800592D8
0x1800592b7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800592be  jz      short loc_1800592D8
0x1800592c0  mov     r8, rdx
0x1800592c3  mov     rdx, rcx
0x1800592c6  mov     rcx, rbx
0x1800592c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800592ce  cmp     [r14], r15w
0x1800592d2  jnz     loc_1800594F1
0x1800592d8  mov     ecx, [rbx]
0x1800592da  mov     bpl, 8
0x1800592dd  test    ecx, ecx
0x1800592df  jz      short loc_18005932A
0x1800592e1  sub     ecx, 1
0x1800592e4  jz      short loc_180059312
0x1800592e6  sub     ecx, 1
0x1800592e9  jz      short loc_180059302
0x1800592eb  cmp     ecx, 1
0x1800592ee  jz      short loc_1800592F9
0x1800592f0  lea     rdi, dword_1800A2364
0x1800592f7  jmp     short loc_180059331
0x1800592f9  lea     rdi, aFailfast; "FailFast"
0x180059300  jmp     short loc_180059331
0x180059302  lea     rax, aLoghr; "LogHr"
0x180059309  lea     rdi, aLognt; "LogNt"
0x180059310  jmp     short loc_180059320
0x180059312  lea     rax, aReturnhr; "ReturnHr"
0x180059319  lea     rdi, aReturnnt; "ReturnNt"
0x180059320  test    [rbx+4], bpl
0x180059324  cmovz   rdi, rax
0x180059328  jmp     short loc_180059331
0x18005932a  lea     rdi, aException; "Exception"
0x180059331  xor     edx, edx; Val
0x180059333  lea     rcx, [rsp+278h+Buffer]; void *
0x180059338  mov     r8d, 200h; Size
0x18005933e  call    memset_0
0x180059343  test    [rbx+4], bpl
0x180059347  jz      short loc_18005936C
0x180059349  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180059350  mov     ebp, [rbx+0Ch]
0x180059353  test    rax, rax
0x180059356  jz      short loc_18005939C
0x180059358  mov     r8d, 100h
0x18005935e  lea     rdx, [rsp+278h+Buffer]
0x180059363  mov     ecx, ebp
0x180059365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005936a  jmp     short loc_18005939C
0x18005936c  mov     ebp, [rbx+8]
0x18005936f  lea     rax, [rsp+278h+Buffer]
0x180059374  mov     [rsp+278h+Arguments], r15; Arguments
0x180059379  mov     r8d, ebp; dwMessageId
0x18005937c  mov     [rsp+278h+nSize], 100h; nSize
0x180059384  mov     r9d, 400h; dwLanguageId
0x18005938a  xor     edx, edx; lpSource
0x18005938c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180059391  mov     ecx, 1200h; dwFlags
0x180059396  call    cs:__imp_FormatMessageW
0x18005939c  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800593a0  lea     rsi, [r14+rsi*2]
0x1800593a4  mov     rax, [rbx+88h]
0x1800593ab  mov     rdx, rsi; unsigned __int16 *
0x1800593ae  mov     rcx, [rbx+80h]
0x1800593b5  test    r9, r9
0x1800593b8  jz      short loc_1800593DC
0x1800593ba  mov     [rsp+278h+Arguments], rax
0x1800593bf  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800593c6  mov     eax, [rbx+40h]
0x1800593c9  mov     qword ptr [rsp+278h+nSize], rcx
0x1800593ce  mov     rcx, r14; this
0x1800593d1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800593d5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800593da  jmp     short loc_1800593F3
0x1800593dc  mov     r9, rcx; unsigned __int16 *
0x1800593df  mov     [rsp+278h+lpBuffer], rax
0x1800593e4  mov     rcx, r14; this
0x1800593e7  lea     r8, aHsP; "%hs!%p: "
0x1800593ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800593f3  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800593fa  mov     r14, rax
0x1800593fd  test    r9, r9
0x180059400  jz      short loc_180059417
0x180059402  lea     r8, aCallerP; "(caller: %p) "
0x180059409  mov     rdx, rsi; unsigned __int16 *
0x18005940c  mov     rcx, rax; this
0x18005940f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180059414  mov     r14, rax
0x180059417  call    cs:__imp_GetCurrentThreadId
0x18005941d  lea     rcx, [rsp+278h+Buffer]
0x180059422  mov     r9, rdi; unsigned __int16 *
0x180059425  mov     [rsp+278h+var_240], rcx
0x18005942a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180059431  mov     dword ptr [rsp+278h+Arguments], ebp
0x180059435  mov     rdx, rsi; unsigned __int16 *
0x180059438  mov     [rsp+278h+nSize], eax
0x18005943c  mov     rcx, r14; this
0x18005943f  mov     eax, [rbx+44h]
0x180059442  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180059446  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005944b  cmp     [rbx+18h], r15
0x18005944f  jnz     short loc_180059461
0x180059451  cmp     [rbx+48h], r15
0x180059455  jnz     short loc_180059461
0x180059457  cmp     [rbx+30h], r15
0x18005945b  jz      loc_1800594F1
0x180059461  lea     r8, asc_1800A2990; "    "
0x180059468  mov     rdx, rsi; unsigned __int16 *
0x18005946b  mov     rcx, rax; this
0x18005946e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180059473  mov     r9, [rbx+18h]; unsigned __int16 *
0x180059477  test    r9, r9
0x18005947a  jz      short loc_18005948E
0x18005947c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180059483  mov     rdx, rsi; unsigned __int16 *
0x180059486  mov     rcx, rax; this
0x180059489  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005948e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180059492  test    r9, r9
0x180059495  jz      short loc_1800594A9
0x180059497  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18005949e  mov     rdx, rsi; unsigned __int16 *
0x1800594a1  mov     rcx, rax; this
0x1800594a4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800594a9  mov     rcx, [rbx+28h]
0x1800594ad  mov     rdx, rsi; unsigned __int16 *
0x1800594b0  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800594b4  test    rcx, rcx
0x1800594b7  jz      short loc_1800594CF
0x1800594b9  mov     [rsp+278h+lpBuffer], rcx
0x1800594be  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800594c5  mov     rcx, rax; this
0x1800594c8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800594cd  jmp     short loc_1800594F1
0x1800594cf  mov     rcx, rax; this
0x1800594d2  test    r9, r9
0x1800594d5  jz      short loc_1800594E5
0x1800594d7  lea     r8, aHs; "[%hs]\n"
0x1800594de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800594e3  jmp     short loc_1800594F1
0x1800594e5  lea     r8, asc_1800A2A08; "\n"
0x1800594ec  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800594f1  xor     eax, eax
0x1800594f3  mov     rcx, [rsp+278h+var_38]
0x1800594fb  xor     rcx, rsp; StackCookie
0x1800594fe  call    __security_check_cookie
0x180059503  mov     rbx, [rsp+278h+arg_18]
0x18005950b  add     rsp, 250h
0x180059512  pop     r15
0x180059514  pop     r14
0x180059516  pop     rdi
0x180059517  pop     rsi
0x180059518  pop     rbp
0x180059519  retn
```
