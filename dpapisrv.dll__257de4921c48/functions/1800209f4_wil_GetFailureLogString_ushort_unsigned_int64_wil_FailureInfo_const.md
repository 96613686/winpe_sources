# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800209f4`
- end: `0x180020cb7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18001f04c`
- `0x1800218ec`
- `0x180021d38`
- `0x1800240a0`

## callees

- `0x18001d810`
- `0x18001e1b4`
- `0x1800209f4`
- `0x180021c00`
- `0x18003e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020bad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020bad`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180020b26`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180020b26`

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
          v7 = (const char *)&word_1800423FA;
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
0x1800209f4  mov     [rsp+arg_18], rbx
0x1800209f9  push    rbp
0x1800209fa  push    rsi
0x1800209fb  push    rdi
0x1800209fc  push    r14
0x1800209fe  push    r15
0x180020a00  sub     rsp, 250h
0x180020a07  mov     rax, cs:__security_cookie
0x180020a0e  xor     rax, rsp
0x180020a11  mov     [rsp+278h+var_38], rax
0x180020a19  mov     rbx, r8
0x180020a1c  mov     rsi, rdx
0x180020a1f  mov     r14, rcx
0x180020a22  xor     r15d, r15d
0x180020a25  test    rdx, rdx
0x180020a28  jz      loc_180020C8D
0x180020a2e  test    rcx, rcx
0x180020a31  jz      loc_180020C8D
0x180020a37  mov     [rcx], r15w
0x180020a3b  mov     rax, cs:g_pfnResultLoggingCallback
0x180020a42  test    rax, rax
0x180020a45  jz      short loc_180020A68
0x180020a47  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180020a4e  jz      short loc_180020A68
0x180020a50  mov     r8, rdx
0x180020a53  mov     rdx, rcx
0x180020a56  mov     rcx, rbx
0x180020a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a5e  cmp     [r14], r15w
0x180020a62  jnz     loc_180020C8D
0x180020a68  mov     ecx, [rbx]
0x180020a6a  mov     bpl, 8
0x180020a6d  test    ecx, ecx
0x180020a6f  jz      short loc_180020ABA
0x180020a71  sub     ecx, 1
0x180020a74  jz      short loc_180020AA2
0x180020a76  sub     ecx, 1
0x180020a79  jz      short loc_180020A92
0x180020a7b  cmp     ecx, 1
0x180020a7e  jz      short loc_180020A89
0x180020a80  lea     rdi, word_1800423FA
0x180020a87  jmp     short loc_180020AC1
0x180020a89  lea     rdi, aFailfast; "FailFast"
0x180020a90  jmp     short loc_180020AC1
0x180020a92  lea     rax, aLoghr; "LogHr"
0x180020a99  lea     rdi, aLognt; "LogNt"
0x180020aa0  jmp     short loc_180020AB0
0x180020aa2  lea     rax, aReturnhr; "ReturnHr"
0x180020aa9  lea     rdi, aReturnnt; "ReturnNt"
0x180020ab0  test    [rbx+4], bpl
0x180020ab4  cmovz   rdi, rax
0x180020ab8  jmp     short loc_180020AC1
0x180020aba  lea     rdi, aException; "Exception"
0x180020ac1  xor     edx, edx; Val
0x180020ac3  mov     r8d, 200h; Size
0x180020ac9  lea     rcx, [rsp+278h+Buffer]; void *
0x180020ace  call    memset_0
0x180020ad3  test    [rbx+4], bpl
0x180020ad7  jz      short loc_180020AFC
0x180020ad9  mov     ebp, [rbx+0Ch]
0x180020adc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180020ae3  test    rax, rax
0x180020ae6  jz      short loc_180020B32
0x180020ae8  mov     r8d, 100h
0x180020aee  lea     rdx, [rsp+278h+Buffer]
0x180020af3  mov     ecx, ebp
0x180020af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020afa  jmp     short loc_180020B32
0x180020afc  mov     ebp, [rbx+8]
0x180020aff  mov     [rsp+278h+Arguments], r15; Arguments
0x180020b04  mov     [rsp+278h+nSize], 100h; nSize
0x180020b0c  lea     rax, [rsp+278h+Buffer]
0x180020b11  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180020b16  mov     r9d, 400h; dwLanguageId
0x180020b1c  mov     r8d, ebp; dwMessageId
0x180020b1f  xor     edx, edx; lpSource
0x180020b21  mov     ecx, 1200h; dwFlags
0x180020b26  call    cs:__imp_FormatMessageW
0x180020b2d  nop     dword ptr [rax+rax+00h]
0x180020b32  lea     rsi, [r14+rsi*2]
0x180020b36  mov     r9, [rbx+38h]; unsigned __int16 *
0x180020b3a  mov     rax, [rbx+88h]
0x180020b41  mov     rcx, [rbx+80h]
0x180020b48  mov     rdx, rsi; unsigned __int16 *
0x180020b4b  test    r9, r9
0x180020b4e  jz      short loc_180020B72
0x180020b50  mov     [rsp+278h+Arguments], rax
0x180020b55  mov     qword ptr [rsp+278h+nSize], rcx
0x180020b5a  mov     eax, [rbx+40h]
0x180020b5d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180020b61  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180020b68  mov     rcx, r14; this
0x180020b6b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180020b70  jmp     short loc_180020B89
0x180020b72  mov     [rsp+278h+lpBuffer], rax
0x180020b77  mov     r9, rcx; unsigned __int16 *
0x180020b7a  lea     r8, aHsP; "%hs!%p: "
0x180020b81  mov     rcx, r14; this
0x180020b84  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180020b89  mov     r14, rax
0x180020b8c  mov     r9, [rbx+90h]; unsigned __int16 *
0x180020b93  test    r9, r9
0x180020b96  jz      short loc_180020BAD
0x180020b98  lea     r8, aCallerP; "(caller: %p) "
0x180020b9f  mov     rdx, rsi; unsigned __int16 *
0x180020ba2  mov     rcx, rax; this
0x180020ba5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180020baa  mov     r14, rax
0x180020bad  call    cs:__imp_GetCurrentThreadId
0x180020bb4  nop     dword ptr [rax+rax+00h]
0x180020bb9  lea     rcx, [rsp+278h+Buffer]
0x180020bbe  mov     [rsp+278h+var_240], rcx
0x180020bc3  mov     dword ptr [rsp+278h+Arguments], ebp
0x180020bc7  mov     [rsp+278h+nSize], eax
0x180020bcb  mov     eax, [rbx+44h]
0x180020bce  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180020bd2  mov     r9, rdi; unsigned __int16 *
0x180020bd5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180020bdc  mov     rdx, rsi; unsigned __int16 *
0x180020bdf  mov     rcx, r14; this
0x180020be2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180020be7  cmp     [rbx+18h], r15
0x180020beb  jnz     short loc_180020BFD
0x180020bed  cmp     [rbx+48h], r15
0x180020bf1  jnz     short loc_180020BFD
0x180020bf3  cmp     [rbx+30h], r15
0x180020bf7  jz      loc_180020C8D
0x180020bfd  lea     r8, asc_1800424E8; "    "
0x180020c04  mov     rdx, rsi; unsigned __int16 *
0x180020c07  mov     rcx, rax; this
0x180020c0a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180020c0f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180020c13  test    r9, r9
0x180020c16  jz      short loc_180020C2A
0x180020c18  lea     r8, aMsgWs; "Msg:[%ws] "
0x180020c1f  mov     rdx, rsi; unsigned __int16 *
0x180020c22  mov     rcx, rax; this
0x180020c25  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180020c2a  mov     r9, [rbx+48h]; unsigned __int16 *
0x180020c2e  test    r9, r9
0x180020c31  jz      short loc_180020C45
0x180020c33  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180020c3a  mov     rdx, rsi; unsigned __int16 *
0x180020c3d  mov     rcx, rax; this
0x180020c40  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180020c45  mov     rcx, [rbx+28h]
0x180020c49  mov     r9, [rbx+30h]; unsigned __int16 *
0x180020c4d  mov     rdx, rsi; unsigned __int16 *
0x180020c50  test    rcx, rcx
0x180020c53  jz      short loc_180020C6B
0x180020c55  mov     [rsp+278h+lpBuffer], rcx
0x180020c5a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180020c61  mov     rcx, rax; this
0x180020c64  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180020c69  jmp     short loc_180020C8D
0x180020c6b  mov     rcx, rax; this
0x180020c6e  test    r9, r9
0x180020c71  jz      short loc_180020C81
0x180020c73  lea     r8, aHs; "[%hs]\n"
0x180020c7a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180020c7f  jmp     short loc_180020C8D
0x180020c81  lea     r8, asc_180042560; "\n"
0x180020c88  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180020c8d  xor     eax, eax
0x180020c8f  mov     rcx, [rsp+278h+var_38]
0x180020c97  xor     rcx, rsp; StackCookie
0x180020c9a  call    __security_check_cookie
0x180020c9f  mov     rbx, [rsp+278h+arg_18]
0x180020ca7  add     rsp, 250h
0x180020cae  pop     r15
0x180020cb0  pop     r14
0x180020cb2  pop     rdi
0x180020cb3  pop     rsi
0x180020cb4  pop     rbp
0x180020cb5  retn
```
