# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140004b34`
- end: `0x140004df7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x140003148`
- `0x1400033dc`
- `0x1400056f8`
- `0x140009260`
- `0x140011b78`
- `0x14002eaec`
- `0x14002ec20`

## callees

- `0x1400020b0`
- `0x140002b2c`
- `0x140004b34`
- `0x140005a0c`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004ced`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004ced`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140004c66`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140004c66`

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
          v7 = (const char *)&word_140036642;
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
0x140004b34  mov     [rsp+arg_18], rbx
0x140004b39  push    rbp
0x140004b3a  push    rsi
0x140004b3b  push    rdi
0x140004b3c  push    r14
0x140004b3e  push    r15
0x140004b40  sub     rsp, 250h
0x140004b47  mov     rax, cs:__security_cookie
0x140004b4e  xor     rax, rsp
0x140004b51  mov     [rsp+278h+var_38], rax
0x140004b59  mov     rbx, r8
0x140004b5c  mov     rsi, rdx
0x140004b5f  mov     r14, rcx
0x140004b62  xor     r15d, r15d
0x140004b65  test    rdx, rdx
0x140004b68  jz      loc_140004DCD
0x140004b6e  test    rcx, rcx
0x140004b71  jz      loc_140004DCD
0x140004b77  mov     [rcx], r15w
0x140004b7b  mov     rax, cs:g_pfnResultLoggingCallback
0x140004b82  test    rax, rax
0x140004b85  jz      short loc_140004BA8
0x140004b87  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140004b8e  jz      short loc_140004BA8
0x140004b90  mov     r8, rdx
0x140004b93  mov     rdx, rcx
0x140004b96  mov     rcx, rbx
0x140004b99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004b9e  cmp     [r14], r15w
0x140004ba2  jnz     loc_140004DCD
0x140004ba8  mov     ecx, [rbx]
0x140004baa  mov     bpl, 8
0x140004bad  test    ecx, ecx
0x140004baf  jz      short loc_140004BFA
0x140004bb1  sub     ecx, 1
0x140004bb4  jz      short loc_140004BE2
0x140004bb6  sub     ecx, 1
0x140004bb9  jz      short loc_140004BD2
0x140004bbb  cmp     ecx, 1
0x140004bbe  jz      short loc_140004BC9
0x140004bc0  lea     rdi, word_140036642
0x140004bc7  jmp     short loc_140004C01
0x140004bc9  lea     rdi, aFailfast; "FailFast"
0x140004bd0  jmp     short loc_140004C01
0x140004bd2  lea     rax, aLoghr; "LogHr"
0x140004bd9  lea     rdi, aLognt; "LogNt"
0x140004be0  jmp     short loc_140004BF0
0x140004be2  lea     rax, aReturnhr; "ReturnHr"
0x140004be9  lea     rdi, aReturnnt; "ReturnNt"
0x140004bf0  test    [rbx+4], bpl
0x140004bf4  cmovz   rdi, rax
0x140004bf8  jmp     short loc_140004C01
0x140004bfa  lea     rdi, aException; "Exception"
0x140004c01  xor     edx, edx; Val
0x140004c03  mov     r8d, 200h; Size
0x140004c09  lea     rcx, [rsp+278h+Buffer]; void *
0x140004c0e  call    memset_0
0x140004c13  test    [rbx+4], bpl
0x140004c17  jz      short loc_140004C3C
0x140004c19  mov     ebp, [rbx+0Ch]
0x140004c1c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140004c23  test    rax, rax
0x140004c26  jz      short loc_140004C72
0x140004c28  mov     r8d, 100h
0x140004c2e  lea     rdx, [rsp+278h+Buffer]
0x140004c33  mov     ecx, ebp
0x140004c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004c3a  jmp     short loc_140004C72
0x140004c3c  mov     ebp, [rbx+8]
0x140004c3f  mov     [rsp+278h+Arguments], r15; Arguments
0x140004c44  mov     [rsp+278h+nSize], 100h; nSize
0x140004c4c  lea     rax, [rsp+278h+Buffer]
0x140004c51  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140004c56  mov     r9d, 400h; dwLanguageId
0x140004c5c  mov     r8d, ebp; dwMessageId
0x140004c5f  xor     edx, edx; lpSource
0x140004c61  mov     ecx, 1200h; dwFlags
0x140004c66  call    cs:__imp_FormatMessageW
0x140004c6d  nop     dword ptr [rax+rax+00h]
0x140004c72  lea     rsi, [r14+rsi*2]
0x140004c76  mov     r9, [rbx+38h]; unsigned __int16 *
0x140004c7a  mov     rax, [rbx+88h]
0x140004c81  mov     rcx, [rbx+80h]
0x140004c88  mov     rdx, rsi; unsigned __int16 *
0x140004c8b  test    r9, r9
0x140004c8e  jz      short loc_140004CB2
0x140004c90  mov     [rsp+278h+Arguments], rax
0x140004c95  mov     qword ptr [rsp+278h+nSize], rcx
0x140004c9a  mov     eax, [rbx+40h]
0x140004c9d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140004ca1  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140004ca8  mov     rcx, r14; this
0x140004cab  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004cb0  jmp     short loc_140004CC9
0x140004cb2  mov     [rsp+278h+lpBuffer], rax
0x140004cb7  mov     r9, rcx; unsigned __int16 *
0x140004cba  lea     r8, aHsP; "%hs!%p: "
0x140004cc1  mov     rcx, r14; this
0x140004cc4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004cc9  mov     r14, rax
0x140004ccc  mov     r9, [rbx+90h]; unsigned __int16 *
0x140004cd3  test    r9, r9
0x140004cd6  jz      short loc_140004CED
0x140004cd8  lea     r8, aCallerP; "(caller: %p) "
0x140004cdf  mov     rdx, rsi; unsigned __int16 *
0x140004ce2  mov     rcx, rax; this
0x140004ce5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004cea  mov     r14, rax
0x140004ced  call    cs:__imp_GetCurrentThreadId
0x140004cf4  nop     dword ptr [rax+rax+00h]
0x140004cf9  lea     rcx, [rsp+278h+Buffer]
0x140004cfe  mov     [rsp+278h+var_240], rcx
0x140004d03  mov     dword ptr [rsp+278h+Arguments], ebp
0x140004d07  mov     [rsp+278h+nSize], eax
0x140004d0b  mov     eax, [rbx+44h]
0x140004d0e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140004d12  mov     r9, rdi; unsigned __int16 *
0x140004d15  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140004d1c  mov     rdx, rsi; unsigned __int16 *
0x140004d1f  mov     rcx, r14; this
0x140004d22  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004d27  cmp     [rbx+18h], r15
0x140004d2b  jnz     short loc_140004D3D
0x140004d2d  cmp     [rbx+48h], r15
0x140004d31  jnz     short loc_140004D3D
0x140004d33  cmp     [rbx+30h], r15
0x140004d37  jz      loc_140004DCD
0x140004d3d  lea     r8, asc_140036730; "    "
0x140004d44  mov     rdx, rsi; unsigned __int16 *
0x140004d47  mov     rcx, rax; this
0x140004d4a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004d4f  mov     r9, [rbx+18h]; unsigned __int16 *
0x140004d53  test    r9, r9
0x140004d56  jz      short loc_140004D6A
0x140004d58  lea     r8, aMsgWs; "Msg:[%ws] "
0x140004d5f  mov     rdx, rsi; unsigned __int16 *
0x140004d62  mov     rcx, rax; this
0x140004d65  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004d6a  mov     r9, [rbx+48h]; unsigned __int16 *
0x140004d6e  test    r9, r9
0x140004d71  jz      short loc_140004D85
0x140004d73  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140004d7a  mov     rdx, rsi; unsigned __int16 *
0x140004d7d  mov     rcx, rax; this
0x140004d80  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004d85  mov     rcx, [rbx+28h]
0x140004d89  mov     r9, [rbx+30h]; unsigned __int16 *
0x140004d8d  mov     rdx, rsi; unsigned __int16 *
0x140004d90  test    rcx, rcx
0x140004d93  jz      short loc_140004DAB
0x140004d95  mov     [rsp+278h+lpBuffer], rcx
0x140004d9a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140004da1  mov     rcx, rax; this
0x140004da4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004da9  jmp     short loc_140004DCD
0x140004dab  mov     rcx, rax; this
0x140004dae  test    r9, r9
0x140004db1  jz      short loc_140004DC1
0x140004db3  lea     r8, aHs; "[%hs]\n"
0x140004dba  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004dbf  jmp     short loc_140004DCD
0x140004dc1  lea     r8, asc_1400367A8; "\n"
0x140004dc8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004dcd  xor     eax, eax
0x140004dcf  mov     rcx, [rsp+278h+var_38]
0x140004dd7  xor     rcx, rsp; StackCookie
0x140004dda  call    __security_check_cookie
0x140004ddf  mov     rbx, [rsp+278h+arg_18]
0x140004de7  add     rsp, 250h
0x140004dee  pop     r15
0x140004df0  pop     r14
0x140004df2  pop     rdi
0x140004df3  pop     rsi
0x140004df4  pop     rbp
0x140004df5  retn
```
