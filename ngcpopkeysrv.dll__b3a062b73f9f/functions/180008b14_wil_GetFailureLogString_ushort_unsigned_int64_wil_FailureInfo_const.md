# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180008b14`
- end: `0x180008dca`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180006bfc`
- `0x180007e34`
- `0x180009768`
- `0x180009f10`
- `0x18000ca70`

## callees

- `0x180004de0`
- `0x180005858`
- `0x180008b14`
- `0x180009a68`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008cc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008cc7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008c46`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008c46`

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
          v7 = (const char *)&dword_18002A2BC;
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
0x180008b14  mov     [rsp+arg_18], rbx
0x180008b19  push    rbp
0x180008b1a  push    rsi
0x180008b1b  push    rdi
0x180008b1c  push    r14
0x180008b1e  push    r15
0x180008b20  sub     rsp, 250h
0x180008b27  mov     rax, cs:__security_cookie
0x180008b2e  xor     rax, rsp
0x180008b31  mov     [rsp+278h+var_38], rax
0x180008b39  mov     rbx, r8
0x180008b3c  mov     rsi, rdx
0x180008b3f  mov     r14, rcx
0x180008b42  xor     r15d, r15d
0x180008b45  test    rdx, rdx
0x180008b48  jz      loc_180008DA1
0x180008b4e  test    rcx, rcx
0x180008b51  jz      loc_180008DA1
0x180008b57  mov     [rcx], r15w
0x180008b5b  mov     rax, cs:g_pfnResultLoggingCallback
0x180008b62  test    rax, rax
0x180008b65  jz      short loc_180008B88
0x180008b67  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180008b6e  jz      short loc_180008B88
0x180008b70  mov     r8, rdx
0x180008b73  mov     rdx, rcx
0x180008b76  mov     rcx, rbx
0x180008b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b7e  cmp     [r14], r15w
0x180008b82  jnz     loc_180008DA1
0x180008b88  mov     ecx, [rbx]
0x180008b8a  mov     bpl, 8
0x180008b8d  test    ecx, ecx
0x180008b8f  jz      short loc_180008BDA
0x180008b91  sub     ecx, 1
0x180008b94  jz      short loc_180008BC2
0x180008b96  sub     ecx, 1
0x180008b99  jz      short loc_180008BB2
0x180008b9b  cmp     ecx, 1
0x180008b9e  jz      short loc_180008BA9
0x180008ba0  lea     rdi, dword_18002A2BC
0x180008ba7  jmp     short loc_180008BE1
0x180008ba9  lea     rdi, aFailfast; "FailFast"
0x180008bb0  jmp     short loc_180008BE1
0x180008bb2  lea     rax, aLoghr; "LogHr"
0x180008bb9  lea     rdi, aLognt; "LogNt"
0x180008bc0  jmp     short loc_180008BD0
0x180008bc2  lea     rax, aReturnhr; "ReturnHr"
0x180008bc9  lea     rdi, aReturnnt; "ReturnNt"
0x180008bd0  test    [rbx+4], bpl
0x180008bd4  cmovz   rdi, rax
0x180008bd8  jmp     short loc_180008BE1
0x180008bda  lea     rdi, aException; "Exception"
0x180008be1  xor     edx, edx; Val
0x180008be3  mov     r8d, 200h; Size
0x180008be9  lea     rcx, [rsp+278h+Buffer]; void *
0x180008bee  call    memset_0
0x180008bf3  test    [rbx+4], bpl
0x180008bf7  jz      short loc_180008C1C
0x180008bf9  mov     ebp, [rbx+0Ch]
0x180008bfc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180008c03  test    rax, rax
0x180008c06  jz      short loc_180008C4C
0x180008c08  mov     r8d, 100h
0x180008c0e  lea     rdx, [rsp+278h+Buffer]
0x180008c13  mov     ecx, ebp
0x180008c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c1a  jmp     short loc_180008C4C
0x180008c1c  mov     ebp, [rbx+8]
0x180008c1f  mov     [rsp+278h+Arguments], r15; Arguments
0x180008c24  mov     [rsp+278h+nSize], 100h; nSize
0x180008c2c  lea     rax, [rsp+278h+Buffer]
0x180008c31  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180008c36  mov     r9d, 400h; dwLanguageId
0x180008c3c  mov     r8d, ebp; dwMessageId
0x180008c3f  xor     edx, edx; lpSource
0x180008c41  mov     ecx, 1200h; dwFlags
0x180008c46  call    cs:__imp_FormatMessageW
0x180008c4c  lea     rsi, [r14+rsi*2]
0x180008c50  mov     r9, [rbx+38h]; unsigned __int16 *
0x180008c54  mov     rax, [rbx+88h]
0x180008c5b  mov     rcx, [rbx+80h]
0x180008c62  mov     rdx, rsi; unsigned __int16 *
0x180008c65  test    r9, r9
0x180008c68  jz      short loc_180008C8C
0x180008c6a  mov     [rsp+278h+Arguments], rax
0x180008c6f  mov     qword ptr [rsp+278h+nSize], rcx
0x180008c74  mov     eax, [rbx+40h]
0x180008c77  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180008c7b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180008c82  mov     rcx, r14; this
0x180008c85  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008c8a  jmp     short loc_180008CA3
0x180008c8c  mov     [rsp+278h+lpBuffer], rax
0x180008c91  mov     r9, rcx; unsigned __int16 *
0x180008c94  lea     r8, aHsP; "%hs!%p: "
0x180008c9b  mov     rcx, r14; this
0x180008c9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008ca3  mov     r14, rax
0x180008ca6  mov     r9, [rbx+90h]; unsigned __int16 *
0x180008cad  test    r9, r9
0x180008cb0  jz      short loc_180008CC7
0x180008cb2  lea     r8, aCallerP; "(caller: %p) "
0x180008cb9  mov     rdx, rsi; unsigned __int16 *
0x180008cbc  mov     rcx, rax; this
0x180008cbf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008cc4  mov     r14, rax
0x180008cc7  call    cs:__imp_GetCurrentThreadId
0x180008ccd  lea     rcx, [rsp+278h+Buffer]
0x180008cd2  mov     [rsp+278h+var_240], rcx
0x180008cd7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180008cdb  mov     [rsp+278h+nSize], eax
0x180008cdf  mov     eax, [rbx+44h]
0x180008ce2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180008ce6  mov     r9, rdi; unsigned __int16 *
0x180008ce9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180008cf0  mov     rdx, rsi; unsigned __int16 *
0x180008cf3  mov     rcx, r14; this
0x180008cf6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008cfb  cmp     [rbx+18h], r15
0x180008cff  jnz     short loc_180008D11
0x180008d01  cmp     [rbx+48h], r15
0x180008d05  jnz     short loc_180008D11
0x180008d07  cmp     [rbx+30h], r15
0x180008d0b  jz      loc_180008DA1
0x180008d11  lea     r8, asc_18002A3C8; "    "
0x180008d18  mov     rdx, rsi; unsigned __int16 *
0x180008d1b  mov     rcx, rax; this
0x180008d1e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008d23  mov     r9, [rbx+18h]; unsigned __int16 *
0x180008d27  test    r9, r9
0x180008d2a  jz      short loc_180008D3E
0x180008d2c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180008d33  mov     rdx, rsi; unsigned __int16 *
0x180008d36  mov     rcx, rax; this
0x180008d39  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008d3e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180008d42  test    r9, r9
0x180008d45  jz      short loc_180008D59
0x180008d47  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180008d4e  mov     rdx, rsi; unsigned __int16 *
0x180008d51  mov     rcx, rax; this
0x180008d54  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008d59  mov     rcx, [rbx+28h]
0x180008d5d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180008d61  mov     rdx, rsi; unsigned __int16 *
0x180008d64  test    rcx, rcx
0x180008d67  jz      short loc_180008D7F
0x180008d69  mov     [rsp+278h+lpBuffer], rcx
0x180008d6e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180008d75  mov     rcx, rax; this
0x180008d78  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008d7d  jmp     short loc_180008DA1
0x180008d7f  mov     rcx, rax; this
0x180008d82  test    r9, r9
0x180008d85  jz      short loc_180008D95
0x180008d87  lea     r8, aHs; "[%hs]\n"
0x180008d8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008d93  jmp     short loc_180008DA1
0x180008d95  lea     r8, asc_18002A440; "\n"
0x180008d9c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008da1  xor     eax, eax
0x180008da3  mov     rcx, [rsp+278h+var_38]
0x180008dab  xor     rcx, rsp; StackCookie
0x180008dae  call    __security_check_cookie
0x180008db3  mov     rbx, [rsp+278h+arg_18]
0x180008dbb  add     rsp, 250h
0x180008dc2  pop     r15
0x180008dc4  pop     r14
0x180008dc6  pop     rdi
0x180008dc7  pop     rsi
0x180008dc8  pop     rbp
0x180008dc9  retn
```
