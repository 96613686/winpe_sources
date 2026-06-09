# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004934`
- end: `0x180004bf7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002b54`
- `0x180002dcc`
- `0x180005300`

## callees

- `0x180004934`
- `0x180005614`
- `0x180014dce`
- `0x180014e00`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004aed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004aed`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004a66`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004a66`

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
          v8 = (const char *)&dword_180018E34;
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
0x180004934  mov     [rsp+arg_18], rbx
0x180004939  push    rbp
0x18000493a  push    rsi
0x18000493b  push    rdi
0x18000493c  push    r14
0x18000493e  push    r15
0x180004940  sub     rsp, 250h
0x180004947  mov     rax, cs:__security_cookie
0x18000494e  xor     rax, rsp
0x180004951  mov     [rsp+278h+var_38], rax
0x180004959  xor     r15d, r15d
0x18000495c  mov     rbx, r8
0x18000495f  mov     rsi, rdx
0x180004962  mov     r14, rcx
0x180004965  test    rdx, rdx
0x180004968  jz      loc_180004BCD
0x18000496e  test    rcx, rcx
0x180004971  jz      loc_180004BCD
0x180004977  mov     rax, cs:g_pfnResultLoggingCallback
0x18000497e  mov     [rcx], r15w
0x180004982  test    rax, rax
0x180004985  jz      short loc_1800049A8
0x180004987  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000498e  jz      short loc_1800049A8
0x180004990  mov     r8, rdx
0x180004993  mov     rdx, rcx
0x180004996  mov     rcx, rbx
0x180004999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000499e  cmp     [r14], r15w
0x1800049a2  jnz     loc_180004BCD
0x1800049a8  mov     ecx, [rbx]
0x1800049aa  mov     bpl, 8
0x1800049ad  test    ecx, ecx
0x1800049af  jz      short loc_1800049FA
0x1800049b1  sub     ecx, 1
0x1800049b4  jz      short loc_1800049E2
0x1800049b6  sub     ecx, 1
0x1800049b9  jz      short loc_1800049D2
0x1800049bb  cmp     ecx, 1
0x1800049be  jz      short loc_1800049C9
0x1800049c0  lea     rdi, dword_180018E34
0x1800049c7  jmp     short loc_180004A01
0x1800049c9  lea     rdi, aFailfast; "FailFast"
0x1800049d0  jmp     short loc_180004A01
0x1800049d2  lea     rax, aLoghr; "LogHr"
0x1800049d9  lea     rdi, aLognt; "LogNt"
0x1800049e0  jmp     short loc_1800049F0
0x1800049e2  lea     rax, aReturnhr; "ReturnHr"
0x1800049e9  lea     rdi, aReturnnt; "ReturnNt"
0x1800049f0  test    [rbx+4], bpl
0x1800049f4  cmovz   rdi, rax
0x1800049f8  jmp     short loc_180004A01
0x1800049fa  lea     rdi, aException; "Exception"
0x180004a01  xor     edx, edx; Val
0x180004a03  lea     rcx, [rsp+278h+Buffer]; void *
0x180004a08  mov     r8d, 200h; Size
0x180004a0e  call    memset_0
0x180004a13  test    [rbx+4], bpl
0x180004a17  jz      short loc_180004A3C
0x180004a19  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004a20  mov     ebp, [rbx+0Ch]
0x180004a23  test    rax, rax
0x180004a26  jz      short loc_180004A72
0x180004a28  mov     r8d, 100h
0x180004a2e  lea     rdx, [rsp+278h+Buffer]
0x180004a33  mov     ecx, ebp
0x180004a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a3a  jmp     short loc_180004A72
0x180004a3c  mov     ebp, [rbx+8]
0x180004a3f  lea     rax, [rsp+278h+Buffer]
0x180004a44  mov     [rsp+278h+Arguments], r15; Arguments
0x180004a49  mov     r8d, ebp; dwMessageId
0x180004a4c  mov     [rsp+278h+nSize], 100h; nSize
0x180004a54  mov     r9d, 400h; dwLanguageId
0x180004a5a  xor     edx, edx; lpSource
0x180004a5c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004a61  mov     ecx, 1200h; dwFlags
0x180004a66  call    cs:__imp_FormatMessageW
0x180004a6d  nop     dword ptr [rax+rax+00h]
0x180004a72  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004a76  lea     rsi, [r14+rsi*2]
0x180004a7a  mov     rax, [rbx+88h]
0x180004a81  mov     rdx, rsi; unsigned __int16 *
0x180004a84  mov     rcx, [rbx+80h]
0x180004a8b  test    r9, r9
0x180004a8e  jz      short loc_180004AB2
0x180004a90  mov     [rsp+278h+Arguments], rax
0x180004a95  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004a9c  mov     eax, [rbx+40h]
0x180004a9f  mov     qword ptr [rsp+278h+nSize], rcx
0x180004aa4  mov     rcx, r14; this
0x180004aa7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004aab  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004ab0  jmp     short loc_180004AC9
0x180004ab2  mov     r9, rcx; unsigned __int16 *
0x180004ab5  mov     [rsp+278h+lpBuffer], rax
0x180004aba  mov     rcx, r14; this
0x180004abd  lea     r8, aHsP; "%hs!%p: "
0x180004ac4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004ac9  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004ad0  mov     r14, rax
0x180004ad3  test    r9, r9
0x180004ad6  jz      short loc_180004AED
0x180004ad8  lea     r8, aCallerP; "(caller: %p) "
0x180004adf  mov     rdx, rsi; unsigned __int16 *
0x180004ae2  mov     rcx, rax; this
0x180004ae5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004aea  mov     r14, rax
0x180004aed  call    cs:__imp_GetCurrentThreadId
0x180004af4  nop     dword ptr [rax+rax+00h]
0x180004af9  lea     rcx, [rsp+278h+Buffer]
0x180004afe  mov     r9, rdi; unsigned __int16 *
0x180004b01  mov     [rsp+278h+var_240], rcx
0x180004b06  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004b0d  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004b11  mov     rdx, rsi; unsigned __int16 *
0x180004b14  mov     [rsp+278h+nSize], eax
0x180004b18  mov     rcx, r14; this
0x180004b1b  mov     eax, [rbx+44h]
0x180004b1e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004b22  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b27  cmp     [rbx+18h], r15
0x180004b2b  jnz     short loc_180004B3D
0x180004b2d  cmp     [rbx+48h], r15
0x180004b31  jnz     short loc_180004B3D
0x180004b33  cmp     [rbx+30h], r15
0x180004b37  jz      loc_180004BCD
0x180004b3d  lea     r8, asc_180018FA0; "    "
0x180004b44  mov     rdx, rsi; unsigned __int16 *
0x180004b47  mov     rcx, rax; this
0x180004b4a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b4f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004b53  test    r9, r9
0x180004b56  jz      short loc_180004B6A
0x180004b58  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004b5f  mov     rdx, rsi; unsigned __int16 *
0x180004b62  mov     rcx, rax; this
0x180004b65  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b6a  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004b6e  test    r9, r9
0x180004b71  jz      short loc_180004B85
0x180004b73  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180004b7a  mov     rdx, rsi; unsigned __int16 *
0x180004b7d  mov     rcx, rax; this
0x180004b80  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b85  mov     rcx, [rbx+28h]
0x180004b89  mov     rdx, rsi; unsigned __int16 *
0x180004b8c  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004b90  test    rcx, rcx
0x180004b93  jz      short loc_180004BAB
0x180004b95  mov     [rsp+278h+lpBuffer], rcx
0x180004b9a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004ba1  mov     rcx, rax; this
0x180004ba4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004ba9  jmp     short loc_180004BCD
0x180004bab  mov     rcx, rax; this
0x180004bae  test    r9, r9
0x180004bb1  jz      short loc_180004BC1
0x180004bb3  lea     r8, aHs; "[%hs]\n"
0x180004bba  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004bbf  jmp     short loc_180004BCD
0x180004bc1  lea     r8, asc_180019018; "\n"
0x180004bc8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004bcd  xor     eax, eax
0x180004bcf  mov     rcx, [rsp+278h+var_38]
0x180004bd7  xor     rcx, rsp; StackCookie
0x180004bda  call    __security_check_cookie
0x180004bdf  mov     rbx, [rsp+278h+arg_18]
0x180004be7  add     rsp, 250h
0x180004bee  pop     r15
0x180004bf0  pop     r14
0x180004bf2  pop     rdi
0x180004bf3  pop     rsi
0x180004bf4  pop     rbp
0x180004bf5  retn
```
