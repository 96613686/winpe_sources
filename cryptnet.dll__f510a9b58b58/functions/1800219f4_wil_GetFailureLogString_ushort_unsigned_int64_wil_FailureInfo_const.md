# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800219f4`
- end: `0x180021caa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180020794`
- `0x18002251c`

## callees

- `0x1800219f4`
- `0x18002281c`
- `0x18002656a`
- `0x1800265b0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021ba7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021ba7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180021b26`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180021b26`

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
          v8 = (const char *)&byte_18002A955;
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
0x1800219f4  mov     [rsp+arg_18], rbx
0x1800219f9  push    rbp
0x1800219fa  push    rsi
0x1800219fb  push    rdi
0x1800219fc  push    r14
0x1800219fe  push    r15
0x180021a00  sub     rsp, 250h
0x180021a07  mov     rax, cs:__security_cookie
0x180021a0e  xor     rax, rsp
0x180021a11  mov     [rsp+278h+var_38], rax
0x180021a19  xor     r15d, r15d
0x180021a1c  mov     rbx, r8
0x180021a1f  mov     rsi, rdx
0x180021a22  mov     r14, rcx
0x180021a25  test    rdx, rdx
0x180021a28  jz      loc_180021C81
0x180021a2e  test    rcx, rcx
0x180021a31  jz      loc_180021C81
0x180021a37  mov     rax, cs:g_pfnResultLoggingCallback
0x180021a3e  mov     [rcx], r15w
0x180021a42  test    rax, rax
0x180021a45  jz      short loc_180021A68
0x180021a47  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180021a4e  jz      short loc_180021A68
0x180021a50  mov     r8, rdx
0x180021a53  mov     rdx, rcx
0x180021a56  mov     rcx, rbx
0x180021a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a5e  cmp     [r14], r15w
0x180021a62  jnz     loc_180021C81
0x180021a68  mov     ecx, [rbx]
0x180021a6a  mov     bpl, 8
0x180021a6d  test    ecx, ecx
0x180021a6f  jz      short loc_180021ABA
0x180021a71  sub     ecx, 1
0x180021a74  jz      short loc_180021AA2
0x180021a76  sub     ecx, 1
0x180021a79  jz      short loc_180021A92
0x180021a7b  cmp     ecx, 1
0x180021a7e  jz      short loc_180021A89
0x180021a80  lea     rdi, byte_18002A955
0x180021a87  jmp     short loc_180021AC1
0x180021a89  lea     rdi, aFailfast; "FailFast"
0x180021a90  jmp     short loc_180021AC1
0x180021a92  lea     rax, aLoghr; "LogHr"
0x180021a99  lea     rdi, aLognt; "LogNt"
0x180021aa0  jmp     short loc_180021AB0
0x180021aa2  lea     rax, aReturnhr; "ReturnHr"
0x180021aa9  lea     rdi, aReturnnt; "ReturnNt"
0x180021ab0  test    [rbx+4], bpl
0x180021ab4  cmovz   rdi, rax
0x180021ab8  jmp     short loc_180021AC1
0x180021aba  lea     rdi, aException; "Exception"
0x180021ac1  xor     edx, edx; Val
0x180021ac3  lea     rcx, [rsp+278h+Buffer]; void *
0x180021ac8  mov     r8d, 200h; Size
0x180021ace  call    memset_0
0x180021ad3  test    [rbx+4], bpl
0x180021ad7  jz      short loc_180021AFC
0x180021ad9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180021ae0  mov     ebp, [rbx+0Ch]
0x180021ae3  test    rax, rax
0x180021ae6  jz      short loc_180021B2C
0x180021ae8  mov     r8d, 100h
0x180021aee  lea     rdx, [rsp+278h+Buffer]
0x180021af3  mov     ecx, ebp
0x180021af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021afa  jmp     short loc_180021B2C
0x180021afc  mov     ebp, [rbx+8]
0x180021aff  lea     rax, [rsp+278h+Buffer]
0x180021b04  mov     [rsp+278h+Arguments], r15; Arguments
0x180021b09  mov     r8d, ebp; dwMessageId
0x180021b0c  mov     [rsp+278h+nSize], 100h; nSize
0x180021b14  mov     r9d, 400h; dwLanguageId
0x180021b1a  xor     edx, edx; lpSource
0x180021b1c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180021b21  mov     ecx, 1200h; dwFlags
0x180021b26  call    cs:__imp_FormatMessageW
0x180021b2c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180021b30  lea     rsi, [r14+rsi*2]
0x180021b34  mov     rax, [rbx+88h]
0x180021b3b  mov     rdx, rsi; unsigned __int16 *
0x180021b3e  mov     rcx, [rbx+80h]
0x180021b45  test    r9, r9
0x180021b48  jz      short loc_180021B6C
0x180021b4a  mov     [rsp+278h+Arguments], rax
0x180021b4f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180021b56  mov     eax, [rbx+40h]
0x180021b59  mov     qword ptr [rsp+278h+nSize], rcx
0x180021b5e  mov     rcx, r14; this
0x180021b61  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180021b65  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180021b6a  jmp     short loc_180021B83
0x180021b6c  mov     r9, rcx; unsigned __int16 *
0x180021b6f  mov     [rsp+278h+lpBuffer], rax
0x180021b74  mov     rcx, r14; this
0x180021b77  lea     r8, aHsP; "%hs!%p: "
0x180021b7e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180021b83  mov     r9, [rbx+90h]; unsigned __int16 *
0x180021b8a  mov     r14, rax
0x180021b8d  test    r9, r9
0x180021b90  jz      short loc_180021BA7
0x180021b92  lea     r8, aCallerP; "(caller: %p) "
0x180021b99  mov     rdx, rsi; unsigned __int16 *
0x180021b9c  mov     rcx, rax; this
0x180021b9f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180021ba4  mov     r14, rax
0x180021ba7  call    cs:__imp_GetCurrentThreadId
0x180021bad  lea     rcx, [rsp+278h+Buffer]
0x180021bb2  mov     r9, rdi; unsigned __int16 *
0x180021bb5  mov     [rsp+278h+var_240], rcx
0x180021bba  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180021bc1  mov     dword ptr [rsp+278h+Arguments], ebp
0x180021bc5  mov     rdx, rsi; unsigned __int16 *
0x180021bc8  mov     [rsp+278h+nSize], eax
0x180021bcc  mov     rcx, r14; this
0x180021bcf  mov     eax, [rbx+44h]
0x180021bd2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180021bd6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180021bdb  cmp     [rbx+18h], r15
0x180021bdf  jnz     short loc_180021BF1
0x180021be1  cmp     [rbx+48h], r15
0x180021be5  jnz     short loc_180021BF1
0x180021be7  cmp     [rbx+30h], r15
0x180021beb  jz      loc_180021C81
0x180021bf1  lea     r8, asc_18002AA40; "    "
0x180021bf8  mov     rdx, rsi; unsigned __int16 *
0x180021bfb  mov     rcx, rax; this
0x180021bfe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180021c03  mov     r9, [rbx+18h]; unsigned __int16 *
0x180021c07  test    r9, r9
0x180021c0a  jz      short loc_180021C1E
0x180021c0c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180021c13  mov     rdx, rsi; unsigned __int16 *
0x180021c16  mov     rcx, rax; this
0x180021c19  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180021c1e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180021c22  test    r9, r9
0x180021c25  jz      short loc_180021C39
0x180021c27  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180021c2e  mov     rdx, rsi; unsigned __int16 *
0x180021c31  mov     rcx, rax; this
0x180021c34  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180021c39  mov     rcx, [rbx+28h]
0x180021c3d  mov     rdx, rsi; unsigned __int16 *
0x180021c40  mov     r9, [rbx+30h]; unsigned __int16 *
0x180021c44  test    rcx, rcx
0x180021c47  jz      short loc_180021C5F
0x180021c49  mov     [rsp+278h+lpBuffer], rcx
0x180021c4e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180021c55  mov     rcx, rax; this
0x180021c58  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180021c5d  jmp     short loc_180021C81
0x180021c5f  mov     rcx, rax; this
0x180021c62  test    r9, r9
0x180021c65  jz      short loc_180021C75
0x180021c67  lea     r8, aHs; "[%hs]\n"
0x180021c6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180021c73  jmp     short loc_180021C81
0x180021c75  lea     r8, asc_18002AAB8; "\n"
0x180021c7c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180021c81  xor     eax, eax
0x180021c83  mov     rcx, [rsp+278h+var_38]
0x180021c8b  xor     rcx, rsp; StackCookie
0x180021c8e  call    __security_check_cookie
0x180021c93  mov     rbx, [rsp+278h+arg_18]
0x180021c9b  add     rsp, 250h
0x180021ca2  pop     r15
0x180021ca4  pop     r14
0x180021ca6  pop     rdi
0x180021ca7  pop     rsi
0x180021ca8  pop     rbp
0x180021ca9  retn
```
