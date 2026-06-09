# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800199f4`
- end: `0x180019cb7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180017014`
- `0x18001a3dc`
- `0x18001aaf4`
- `0x18001dc60`

## callees

- `0x180014330`
- `0x180015174`
- `0x1800199f4`
- `0x18001a6f0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019bad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019bad`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180019b26`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180019b26`

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
          v7 = (const char *)&byte_180033E35;
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
0x1800199f4  mov     [rsp+arg_18], rbx
0x1800199f9  push    rbp
0x1800199fa  push    rsi
0x1800199fb  push    rdi
0x1800199fc  push    r14
0x1800199fe  push    r15
0x180019a00  sub     rsp, 250h
0x180019a07  mov     rax, cs:__security_cookie
0x180019a0e  xor     rax, rsp
0x180019a11  mov     [rsp+278h+var_38], rax
0x180019a19  mov     rbx, r8
0x180019a1c  mov     rsi, rdx
0x180019a1f  mov     r14, rcx
0x180019a22  xor     r15d, r15d
0x180019a25  test    rdx, rdx
0x180019a28  jz      loc_180019C8D
0x180019a2e  test    rcx, rcx
0x180019a31  jz      loc_180019C8D
0x180019a37  mov     [rcx], r15w
0x180019a3b  mov     rax, cs:g_pfnResultLoggingCallback
0x180019a42  test    rax, rax
0x180019a45  jz      short loc_180019A68
0x180019a47  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180019a4e  jz      short loc_180019A68
0x180019a50  mov     r8, rdx
0x180019a53  mov     rdx, rcx
0x180019a56  mov     rcx, rbx
0x180019a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a5e  cmp     [r14], r15w
0x180019a62  jnz     loc_180019C8D
0x180019a68  mov     ecx, [rbx]
0x180019a6a  mov     bpl, 8
0x180019a6d  test    ecx, ecx
0x180019a6f  jz      short loc_180019ABA
0x180019a71  sub     ecx, 1
0x180019a74  jz      short loc_180019AA2
0x180019a76  sub     ecx, 1
0x180019a79  jz      short loc_180019A92
0x180019a7b  cmp     ecx, 1
0x180019a7e  jz      short loc_180019A89
0x180019a80  lea     rdi, byte_180033E35
0x180019a87  jmp     short loc_180019AC1
0x180019a89  lea     rdi, aFailfast; "FailFast"
0x180019a90  jmp     short loc_180019AC1
0x180019a92  lea     rax, aLoghr; "LogHr"
0x180019a99  lea     rdi, aLognt; "LogNt"
0x180019aa0  jmp     short loc_180019AB0
0x180019aa2  lea     rax, aReturnhr; "ReturnHr"
0x180019aa9  lea     rdi, aReturnnt; "ReturnNt"
0x180019ab0  test    [rbx+4], bpl
0x180019ab4  cmovz   rdi, rax
0x180019ab8  jmp     short loc_180019AC1
0x180019aba  lea     rdi, aException; "Exception"
0x180019ac1  xor     edx, edx; Val
0x180019ac3  mov     r8d, 200h; Size
0x180019ac9  lea     rcx, [rsp+278h+Buffer]; void *
0x180019ace  call    memset_0
0x180019ad3  test    [rbx+4], bpl
0x180019ad7  jz      short loc_180019AFC
0x180019ad9  mov     ebp, [rbx+0Ch]
0x180019adc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180019ae3  test    rax, rax
0x180019ae6  jz      short loc_180019B32
0x180019ae8  mov     r8d, 100h
0x180019aee  lea     rdx, [rsp+278h+Buffer]
0x180019af3  mov     ecx, ebp
0x180019af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019afa  jmp     short loc_180019B32
0x180019afc  mov     ebp, [rbx+8]
0x180019aff  mov     [rsp+278h+Arguments], r15; Arguments
0x180019b04  mov     [rsp+278h+nSize], 100h; nSize
0x180019b0c  lea     rax, [rsp+278h+Buffer]
0x180019b11  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180019b16  mov     r9d, 400h; dwLanguageId
0x180019b1c  mov     r8d, ebp; dwMessageId
0x180019b1f  xor     edx, edx; lpSource
0x180019b21  mov     ecx, 1200h; dwFlags
0x180019b26  call    cs:__imp_FormatMessageW
0x180019b2d  nop     dword ptr [rax+rax+00h]
0x180019b32  lea     rsi, [r14+rsi*2]
0x180019b36  mov     r9, [rbx+38h]; unsigned __int16 *
0x180019b3a  mov     rax, [rbx+88h]
0x180019b41  mov     rcx, [rbx+80h]
0x180019b48  mov     rdx, rsi; unsigned __int16 *
0x180019b4b  test    r9, r9
0x180019b4e  jz      short loc_180019B72
0x180019b50  mov     [rsp+278h+Arguments], rax
0x180019b55  mov     qword ptr [rsp+278h+nSize], rcx
0x180019b5a  mov     eax, [rbx+40h]
0x180019b5d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180019b61  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180019b68  mov     rcx, r14; this
0x180019b6b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180019b70  jmp     short loc_180019B89
0x180019b72  mov     [rsp+278h+lpBuffer], rax
0x180019b77  mov     r9, rcx; unsigned __int16 *
0x180019b7a  lea     r8, aHsP; "%hs!%p: "
0x180019b81  mov     rcx, r14; this
0x180019b84  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180019b89  mov     r14, rax
0x180019b8c  mov     r9, [rbx+90h]; unsigned __int16 *
0x180019b93  test    r9, r9
0x180019b96  jz      short loc_180019BAD
0x180019b98  lea     r8, aCallerP; "(caller: %p) "
0x180019b9f  mov     rdx, rsi; unsigned __int16 *
0x180019ba2  mov     rcx, rax; this
0x180019ba5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180019baa  mov     r14, rax
0x180019bad  call    cs:__imp_GetCurrentThreadId
0x180019bb4  nop     dword ptr [rax+rax+00h]
0x180019bb9  lea     rcx, [rsp+278h+Buffer]
0x180019bbe  mov     [rsp+278h+var_240], rcx
0x180019bc3  mov     dword ptr [rsp+278h+Arguments], ebp
0x180019bc7  mov     [rsp+278h+nSize], eax
0x180019bcb  mov     eax, [rbx+44h]
0x180019bce  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180019bd2  mov     r9, rdi; unsigned __int16 *
0x180019bd5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180019bdc  mov     rdx, rsi; unsigned __int16 *
0x180019bdf  mov     rcx, r14; this
0x180019be2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180019be7  cmp     [rbx+18h], r15
0x180019beb  jnz     short loc_180019BFD
0x180019bed  cmp     [rbx+48h], r15
0x180019bf1  jnz     short loc_180019BFD
0x180019bf3  cmp     [rbx+30h], r15
0x180019bf7  jz      loc_180019C8D
0x180019bfd  lea     r8, asc_180033F38; "    "
0x180019c04  mov     rdx, rsi; unsigned __int16 *
0x180019c07  mov     rcx, rax; this
0x180019c0a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180019c0f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180019c13  test    r9, r9
0x180019c16  jz      short loc_180019C2A
0x180019c18  lea     r8, aMsgWs; "Msg:[%ws] "
0x180019c1f  mov     rdx, rsi; unsigned __int16 *
0x180019c22  mov     rcx, rax; this
0x180019c25  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180019c2a  mov     r9, [rbx+48h]; unsigned __int16 *
0x180019c2e  test    r9, r9
0x180019c31  jz      short loc_180019C45
0x180019c33  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180019c3a  mov     rdx, rsi; unsigned __int16 *
0x180019c3d  mov     rcx, rax; this
0x180019c40  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180019c45  mov     rcx, [rbx+28h]
0x180019c49  mov     r9, [rbx+30h]; unsigned __int16 *
0x180019c4d  mov     rdx, rsi; unsigned __int16 *
0x180019c50  test    rcx, rcx
0x180019c53  jz      short loc_180019C6B
0x180019c55  mov     [rsp+278h+lpBuffer], rcx
0x180019c5a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180019c61  mov     rcx, rax; this
0x180019c64  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180019c69  jmp     short loc_180019C8D
0x180019c6b  mov     rcx, rax; this
0x180019c6e  test    r9, r9
0x180019c71  jz      short loc_180019C81
0x180019c73  lea     r8, aHs; "[%hs]\n"
0x180019c7a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180019c7f  jmp     short loc_180019C8D
0x180019c81  lea     r8, asc_180033E48; "\n"
0x180019c88  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180019c8d  xor     eax, eax
0x180019c8f  mov     rcx, [rsp+278h+var_38]
0x180019c97  xor     rcx, rsp; StackCookie
0x180019c9a  call    __security_check_cookie
0x180019c9f  mov     rbx, [rsp+278h+arg_18]
0x180019ca7  add     rsp, 250h
0x180019cae  pop     r15
0x180019cb0  pop     r14
0x180019cb2  pop     rdi
0x180019cb3  pop     rsi
0x180019cb4  pop     rbp
0x180019cb5  retn
```
