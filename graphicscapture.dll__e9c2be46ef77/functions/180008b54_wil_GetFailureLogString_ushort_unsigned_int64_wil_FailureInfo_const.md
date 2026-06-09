# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180008b54`
- end: `0x180008e0a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180007134`
- `0x1800097a0`
- `0x180009f00`
- `0x18000cbf0`

## callees

- `0x180001640`
- `0x180001f78`
- `0x180008b54`
- `0x180009aa4`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008d07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008d07`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008c86`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008c86`

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
          v7 = (const char *)&qword_18002CC80;
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
0x180008b54  mov     [rsp+arg_18], rbx
0x180008b59  push    rbp
0x180008b5a  push    rsi
0x180008b5b  push    rdi
0x180008b5c  push    r14
0x180008b5e  push    r15
0x180008b60  sub     rsp, 250h
0x180008b67  mov     rax, cs:__security_cookie
0x180008b6e  xor     rax, rsp
0x180008b71  mov     [rsp+278h+var_38], rax
0x180008b79  mov     rbx, r8
0x180008b7c  mov     rsi, rdx
0x180008b7f  mov     r14, rcx
0x180008b82  xor     r15d, r15d
0x180008b85  test    rdx, rdx
0x180008b88  jz      loc_180008DE1
0x180008b8e  test    rcx, rcx
0x180008b91  jz      loc_180008DE1
0x180008b97  mov     [rcx], r15w
0x180008b9b  mov     rax, cs:g_pfnResultLoggingCallback
0x180008ba2  test    rax, rax
0x180008ba5  jz      short loc_180008BC8
0x180008ba7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180008bae  jz      short loc_180008BC8
0x180008bb0  mov     r8, rdx
0x180008bb3  mov     rdx, rcx
0x180008bb6  mov     rcx, rbx
0x180008bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bbe  cmp     [r14], r15w
0x180008bc2  jnz     loc_180008DE1
0x180008bc8  mov     ecx, [rbx]
0x180008bca  mov     bpl, 8
0x180008bcd  test    ecx, ecx
0x180008bcf  jz      short loc_180008C1A
0x180008bd1  sub     ecx, 1
0x180008bd4  jz      short loc_180008C02
0x180008bd6  sub     ecx, 1
0x180008bd9  jz      short loc_180008BF2
0x180008bdb  cmp     ecx, 1
0x180008bde  jz      short loc_180008BE9
0x180008be0  lea     rdi, qword_18002CC80
0x180008be7  jmp     short loc_180008C21
0x180008be9  lea     rdi, aFailfast; "FailFast"
0x180008bf0  jmp     short loc_180008C21
0x180008bf2  lea     rax, aLoghr; "LogHr"
0x180008bf9  lea     rdi, aLognt; "LogNt"
0x180008c00  jmp     short loc_180008C10
0x180008c02  lea     rax, aReturnhr; "ReturnHr"
0x180008c09  lea     rdi, aReturnnt; "ReturnNt"
0x180008c10  test    [rbx+4], bpl
0x180008c14  cmovz   rdi, rax
0x180008c18  jmp     short loc_180008C21
0x180008c1a  lea     rdi, aException; "Exception"
0x180008c21  xor     edx, edx; Val
0x180008c23  mov     r8d, 200h; Size
0x180008c29  lea     rcx, [rsp+278h+Buffer]; void *
0x180008c2e  call    memset_0
0x180008c33  test    [rbx+4], bpl
0x180008c37  jz      short loc_180008C5C
0x180008c39  mov     ebp, [rbx+0Ch]
0x180008c3c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180008c43  test    rax, rax
0x180008c46  jz      short loc_180008C8C
0x180008c48  mov     r8d, 100h
0x180008c4e  lea     rdx, [rsp+278h+Buffer]
0x180008c53  mov     ecx, ebp
0x180008c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c5a  jmp     short loc_180008C8C
0x180008c5c  mov     ebp, [rbx+8]
0x180008c5f  mov     [rsp+278h+Arguments], r15; Arguments
0x180008c64  mov     [rsp+278h+nSize], 100h; nSize
0x180008c6c  lea     rax, [rsp+278h+Buffer]
0x180008c71  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180008c76  mov     r9d, 400h; dwLanguageId
0x180008c7c  mov     r8d, ebp; dwMessageId
0x180008c7f  xor     edx, edx; lpSource
0x180008c81  mov     ecx, 1200h; dwFlags
0x180008c86  call    cs:__imp_FormatMessageW
0x180008c8c  lea     rsi, [r14+rsi*2]
0x180008c90  mov     r9, [rbx+38h]; unsigned __int16 *
0x180008c94  mov     rax, [rbx+88h]
0x180008c9b  mov     rcx, [rbx+80h]
0x180008ca2  mov     rdx, rsi; unsigned __int16 *
0x180008ca5  test    r9, r9
0x180008ca8  jz      short loc_180008CCC
0x180008caa  mov     [rsp+278h+Arguments], rax
0x180008caf  mov     qword ptr [rsp+278h+nSize], rcx
0x180008cb4  mov     eax, [rbx+40h]
0x180008cb7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180008cbb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180008cc2  mov     rcx, r14; this
0x180008cc5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008cca  jmp     short loc_180008CE3
0x180008ccc  mov     [rsp+278h+lpBuffer], rax
0x180008cd1  mov     r9, rcx; unsigned __int16 *
0x180008cd4  lea     r8, aHsP; "%hs!%p: "
0x180008cdb  mov     rcx, r14; this
0x180008cde  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008ce3  mov     r14, rax
0x180008ce6  mov     r9, [rbx+90h]; unsigned __int16 *
0x180008ced  test    r9, r9
0x180008cf0  jz      short loc_180008D07
0x180008cf2  lea     r8, aCallerP; "(caller: %p) "
0x180008cf9  mov     rdx, rsi; unsigned __int16 *
0x180008cfc  mov     rcx, rax; this
0x180008cff  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008d04  mov     r14, rax
0x180008d07  call    cs:__imp_GetCurrentThreadId
0x180008d0d  lea     rcx, [rsp+278h+Buffer]
0x180008d12  mov     [rsp+278h+var_240], rcx
0x180008d17  mov     dword ptr [rsp+278h+Arguments], ebp
0x180008d1b  mov     [rsp+278h+nSize], eax
0x180008d1f  mov     eax, [rbx+44h]
0x180008d22  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180008d26  mov     r9, rdi; unsigned __int16 *
0x180008d29  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180008d30  mov     rdx, rsi; unsigned __int16 *
0x180008d33  mov     rcx, r14; this
0x180008d36  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008d3b  cmp     [rbx+18h], r15
0x180008d3f  jnz     short loc_180008D51
0x180008d41  cmp     [rbx+48h], r15
0x180008d45  jnz     short loc_180008D51
0x180008d47  cmp     [rbx+30h], r15
0x180008d4b  jz      loc_180008DE1
0x180008d51  lea     r8, asc_18002CD70; "    "
0x180008d58  mov     rdx, rsi; unsigned __int16 *
0x180008d5b  mov     rcx, rax; this
0x180008d5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008d63  mov     r9, [rbx+18h]; unsigned __int16 *
0x180008d67  test    r9, r9
0x180008d6a  jz      short loc_180008D7E
0x180008d6c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180008d73  mov     rdx, rsi; unsigned __int16 *
0x180008d76  mov     rcx, rax; this
0x180008d79  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008d7e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180008d82  test    r9, r9
0x180008d85  jz      short loc_180008D99
0x180008d87  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180008d8e  mov     rdx, rsi; unsigned __int16 *
0x180008d91  mov     rcx, rax; this
0x180008d94  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008d99  mov     rcx, [rbx+28h]
0x180008d9d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180008da1  mov     rdx, rsi; unsigned __int16 *
0x180008da4  test    rcx, rcx
0x180008da7  jz      short loc_180008DBF
0x180008da9  mov     [rsp+278h+lpBuffer], rcx
0x180008dae  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180008db5  mov     rcx, rax; this
0x180008db8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008dbd  jmp     short loc_180008DE1
0x180008dbf  mov     rcx, rax; this
0x180008dc2  test    r9, r9
0x180008dc5  jz      short loc_180008DD5
0x180008dc7  lea     r8, aHs; "[%hs]\n"
0x180008dce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008dd3  jmp     short loc_180008DE1
0x180008dd5  lea     r8, asc_18002CDE8; "\n"
0x180008ddc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008de1  xor     eax, eax
0x180008de3  mov     rcx, [rsp+278h+var_38]
0x180008deb  xor     rcx, rsp; StackCookie
0x180008dee  call    __security_check_cookie
0x180008df3  mov     rbx, [rsp+278h+arg_18]
0x180008dfb  add     rsp, 250h
0x180008e02  pop     r15
0x180008e04  pop     r14
0x180008e06  pop     rdi
0x180008e07  pop     rsi
0x180008e08  pop     rbp
0x180008e09  retn
```
