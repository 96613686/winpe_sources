# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18002a094`
- end: `0x18002a34a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180026cfc`
- `0x180026f64`
- `0x18002ae84`
- `0x18002e7f0`

## callees

- `0x18002a094`
- `0x18002b184`
- `0x180031642`
- `0x180031680`
- `0x180034010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x18002a1c6`
- `KERNEL32!FormatMessageW` at `0x18002a1c6`
- `KERNEL32!GetCurrentThreadId` at `0x18002a247`
- `KERNEL32!GetCurrentThreadId` at `0x18002a247`

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
          v7 = (const char *)&byte_1800391A8;
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
0x18002a094  mov     [rsp+arg_18], rbx
0x18002a099  push    rbp
0x18002a09a  push    rsi
0x18002a09b  push    rdi
0x18002a09c  push    r14
0x18002a09e  push    r15
0x18002a0a0  sub     rsp, 250h
0x18002a0a7  mov     rax, cs:__security_cookie
0x18002a0ae  xor     rax, rsp
0x18002a0b1  mov     [rsp+278h+var_38], rax
0x18002a0b9  mov     rbx, r8
0x18002a0bc  mov     rsi, rdx
0x18002a0bf  mov     r14, rcx
0x18002a0c2  xor     r15d, r15d
0x18002a0c5  test    rdx, rdx
0x18002a0c8  jz      loc_18002A321
0x18002a0ce  test    rcx, rcx
0x18002a0d1  jz      loc_18002A321
0x18002a0d7  mov     [rcx], r15w
0x18002a0db  mov     rax, cs:g_pfnResultLoggingCallback
0x18002a0e2  test    rax, rax
0x18002a0e5  jz      short loc_18002A108
0x18002a0e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002a0ee  jz      short loc_18002A108
0x18002a0f0  mov     r8, rdx
0x18002a0f3  mov     rdx, rcx
0x18002a0f6  mov     rcx, rbx
0x18002a0f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0fe  cmp     [r14], r15w
0x18002a102  jnz     loc_18002A321
0x18002a108  mov     ecx, [rbx]
0x18002a10a  mov     bpl, 8
0x18002a10d  test    ecx, ecx
0x18002a10f  jz      short loc_18002A15A
0x18002a111  sub     ecx, 1
0x18002a114  jz      short loc_18002A142
0x18002a116  sub     ecx, 1
0x18002a119  jz      short loc_18002A132
0x18002a11b  cmp     ecx, 1
0x18002a11e  jz      short loc_18002A129
0x18002a120  lea     rdi, byte_1800391A8
0x18002a127  jmp     short loc_18002A161
0x18002a129  lea     rdi, aFailfast; "FailFast"
0x18002a130  jmp     short loc_18002A161
0x18002a132  lea     rax, aLoghr; "LogHr"
0x18002a139  lea     rdi, aLognt; "LogNt"
0x18002a140  jmp     short loc_18002A150
0x18002a142  lea     rax, aReturnhr; "ReturnHr"
0x18002a149  lea     rdi, aReturnnt; "ReturnNt"
0x18002a150  test    [rbx+4], bpl
0x18002a154  cmovz   rdi, rax
0x18002a158  jmp     short loc_18002A161
0x18002a15a  lea     rdi, aException; "Exception"
0x18002a161  xor     edx, edx; Val
0x18002a163  mov     r8d, 200h; Size
0x18002a169  lea     rcx, [rsp+278h+Buffer]; void *
0x18002a16e  call    memset_0
0x18002a173  test    [rbx+4], bpl
0x18002a177  jz      short loc_18002A19C
0x18002a179  mov     ebp, [rbx+0Ch]
0x18002a17c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18002a183  test    rax, rax
0x18002a186  jz      short loc_18002A1CC
0x18002a188  mov     r8d, 100h
0x18002a18e  lea     rdx, [rsp+278h+Buffer]
0x18002a193  mov     ecx, ebp
0x18002a195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a19a  jmp     short loc_18002A1CC
0x18002a19c  mov     ebp, [rbx+8]
0x18002a19f  mov     [rsp+278h+Arguments], r15; Arguments
0x18002a1a4  mov     [rsp+278h+nSize], 100h; nSize
0x18002a1ac  lea     rax, [rsp+278h+Buffer]
0x18002a1b1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18002a1b6  mov     r9d, 400h; dwLanguageId
0x18002a1bc  mov     r8d, ebp; dwMessageId
0x18002a1bf  xor     edx, edx; lpSource
0x18002a1c1  mov     ecx, 1200h; dwFlags
0x18002a1c6  call    cs:__imp_FormatMessageW
0x18002a1cc  lea     rsi, [r14+rsi*2]
0x18002a1d0  mov     r9, [rbx+38h]; unsigned __int16 *
0x18002a1d4  mov     rax, [rbx+88h]
0x18002a1db  mov     rcx, [rbx+80h]
0x18002a1e2  mov     rdx, rsi; unsigned __int16 *
0x18002a1e5  test    r9, r9
0x18002a1e8  jz      short loc_18002A20C
0x18002a1ea  mov     [rsp+278h+Arguments], rax
0x18002a1ef  mov     qword ptr [rsp+278h+nSize], rcx
0x18002a1f4  mov     eax, [rbx+40h]
0x18002a1f7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18002a1fb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18002a202  mov     rcx, r14; this
0x18002a205  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002a20a  jmp     short loc_18002A223
0x18002a20c  mov     [rsp+278h+lpBuffer], rax
0x18002a211  mov     r9, rcx; unsigned __int16 *
0x18002a214  lea     r8, aHsP; "%hs!%p: "
0x18002a21b  mov     rcx, r14; this
0x18002a21e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002a223  mov     r14, rax
0x18002a226  mov     r9, [rbx+90h]; unsigned __int16 *
0x18002a22d  test    r9, r9
0x18002a230  jz      short loc_18002A247
0x18002a232  lea     r8, aCallerP; "(caller: %p) "
0x18002a239  mov     rdx, rsi; unsigned __int16 *
0x18002a23c  mov     rcx, rax; this
0x18002a23f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002a244  mov     r14, rax
0x18002a247  call    cs:__imp_GetCurrentThreadId
0x18002a24d  lea     rcx, [rsp+278h+Buffer]
0x18002a252  mov     [rsp+278h+var_240], rcx
0x18002a257  mov     dword ptr [rsp+278h+Arguments], ebp
0x18002a25b  mov     [rsp+278h+nSize], eax
0x18002a25f  mov     eax, [rbx+44h]
0x18002a262  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18002a266  mov     r9, rdi; unsigned __int16 *
0x18002a269  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18002a270  mov     rdx, rsi; unsigned __int16 *
0x18002a273  mov     rcx, r14; this
0x18002a276  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002a27b  cmp     [rbx+18h], r15
0x18002a27f  jnz     short loc_18002A291
0x18002a281  cmp     [rbx+48h], r15
0x18002a285  jnz     short loc_18002A291
0x18002a287  cmp     [rbx+30h], r15
0x18002a28b  jz      loc_18002A321
0x18002a291  lea     r8, asc_180038DD0; "    "
0x18002a298  mov     rdx, rsi; unsigned __int16 *
0x18002a29b  mov     rcx, rax; this
0x18002a29e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002a2a3  mov     r9, [rbx+18h]; unsigned __int16 *
0x18002a2a7  test    r9, r9
0x18002a2aa  jz      short loc_18002A2BE
0x18002a2ac  lea     r8, aMsgWs; "Msg:[%ws] "
0x18002a2b3  mov     rdx, rsi; unsigned __int16 *
0x18002a2b6  mov     rcx, rax; this
0x18002a2b9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002a2be  mov     r9, [rbx+48h]; unsigned __int16 *
0x18002a2c2  test    r9, r9
0x18002a2c5  jz      short loc_18002A2D9
0x18002a2c7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18002a2ce  mov     rdx, rsi; unsigned __int16 *
0x18002a2d1  mov     rcx, rax; this
0x18002a2d4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002a2d9  mov     rcx, [rbx+28h]
0x18002a2dd  mov     r9, [rbx+30h]; unsigned __int16 *
0x18002a2e1  mov     rdx, rsi; unsigned __int16 *
0x18002a2e4  test    rcx, rcx
0x18002a2e7  jz      short loc_18002A2FF
0x18002a2e9  mov     [rsp+278h+lpBuffer], rcx
0x18002a2ee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18002a2f5  mov     rcx, rax; this
0x18002a2f8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002a2fd  jmp     short loc_18002A321
0x18002a2ff  mov     rcx, rax; this
0x18002a302  test    r9, r9
0x18002a305  jz      short loc_18002A315
0x18002a307  lea     r8, aHs; "[%hs]\n"
0x18002a30e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002a313  jmp     short loc_18002A321
0x18002a315  lea     r8, asc_180038E48; "\n"
0x18002a31c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002a321  xor     eax, eax
0x18002a323  mov     rcx, [rsp+278h+var_38]
0x18002a32b  xor     rcx, rsp; StackCookie
0x18002a32e  call    __security_check_cookie
0x18002a333  mov     rbx, [rsp+278h+arg_18]
0x18002a33b  add     rsp, 250h
0x18002a342  pop     r15
0x18002a344  pop     r14
0x18002a346  pop     rdi
0x18002a347  pop     rsi
0x18002a348  pop     rbp
0x18002a349  retn
```
