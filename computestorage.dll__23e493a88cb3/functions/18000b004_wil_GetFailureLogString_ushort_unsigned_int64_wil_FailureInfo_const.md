# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000b004`
- end: `0x18000b2c7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x180005958`
- `0x180005bec`
- `0x180005ecc`
- `0x18000bcb8`
- `0x180012e10`
- `0x180013d50`
- `0x18004367c`
- `0x1800437b0`

## callees

- `0x180002690`
- `0x1800032b8`
- `0x18000b004`
- `0x18000bfcc`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b1bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b1bd`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b136`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b136`

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
          v7 = (const char *)&byte_18004C4CD;
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
0x18000b004  mov     [rsp+arg_18], rbx
0x18000b009  push    rbp
0x18000b00a  push    rsi
0x18000b00b  push    rdi
0x18000b00c  push    r14
0x18000b00e  push    r15
0x18000b010  sub     rsp, 250h
0x18000b017  mov     rax, cs:__security_cookie
0x18000b01e  xor     rax, rsp
0x18000b021  mov     [rsp+278h+var_38], rax
0x18000b029  mov     rbx, r8
0x18000b02c  mov     rsi, rdx
0x18000b02f  mov     r14, rcx
0x18000b032  xor     r15d, r15d
0x18000b035  test    rdx, rdx
0x18000b038  jz      loc_18000B29D
0x18000b03e  test    rcx, rcx
0x18000b041  jz      loc_18000B29D
0x18000b047  mov     [rcx], r15w
0x18000b04b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b052  test    rax, rax
0x18000b055  jz      short loc_18000B078
0x18000b057  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000b05e  jz      short loc_18000B078
0x18000b060  mov     r8, rdx
0x18000b063  mov     rdx, rcx
0x18000b066  mov     rcx, rbx
0x18000b069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b06e  cmp     [r14], r15w
0x18000b072  jnz     loc_18000B29D
0x18000b078  mov     ecx, [rbx]
0x18000b07a  mov     bpl, 8
0x18000b07d  test    ecx, ecx
0x18000b07f  jz      short loc_18000B0CA
0x18000b081  sub     ecx, 1
0x18000b084  jz      short loc_18000B0B2
0x18000b086  sub     ecx, 1
0x18000b089  jz      short loc_18000B0A2
0x18000b08b  cmp     ecx, 1
0x18000b08e  jz      short loc_18000B099
0x18000b090  lea     rdi, byte_18004C4CD
0x18000b097  jmp     short loc_18000B0D1
0x18000b099  lea     rdi, aFailfast; "FailFast"
0x18000b0a0  jmp     short loc_18000B0D1
0x18000b0a2  lea     rax, aLoghr; "LogHr"
0x18000b0a9  lea     rdi, aLognt; "LogNt"
0x18000b0b0  jmp     short loc_18000B0C0
0x18000b0b2  lea     rax, aReturnhr; "ReturnHr"
0x18000b0b9  lea     rdi, aReturnnt; "ReturnNt"
0x18000b0c0  test    [rbx+4], bpl
0x18000b0c4  cmovz   rdi, rax
0x18000b0c8  jmp     short loc_18000B0D1
0x18000b0ca  lea     rdi, aException; "Exception"
0x18000b0d1  xor     edx, edx; Val
0x18000b0d3  mov     r8d, 200h; Size
0x18000b0d9  lea     rcx, [rsp+278h+Buffer]; void *
0x18000b0de  call    memset_0
0x18000b0e3  test    [rbx+4], bpl
0x18000b0e7  jz      short loc_18000B10C
0x18000b0e9  mov     ebp, [rbx+0Ch]
0x18000b0ec  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000b0f3  test    rax, rax
0x18000b0f6  jz      short loc_18000B142
0x18000b0f8  mov     r8d, 100h
0x18000b0fe  lea     rdx, [rsp+278h+Buffer]
0x18000b103  mov     ecx, ebp
0x18000b105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b10a  jmp     short loc_18000B142
0x18000b10c  mov     ebp, [rbx+8]
0x18000b10f  mov     [rsp+278h+Arguments], r15; Arguments
0x18000b114  mov     [rsp+278h+nSize], 100h; nSize
0x18000b11c  lea     rax, [rsp+278h+Buffer]
0x18000b121  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000b126  mov     r9d, 400h; dwLanguageId
0x18000b12c  mov     r8d, ebp; dwMessageId
0x18000b12f  xor     edx, edx; lpSource
0x18000b131  mov     ecx, 1200h; dwFlags
0x18000b136  call    cs:__imp_FormatMessageW
0x18000b13d  nop     dword ptr [rax+rax+00h]
0x18000b142  lea     rsi, [r14+rsi*2]
0x18000b146  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000b14a  mov     rax, [rbx+88h]
0x18000b151  mov     rcx, [rbx+80h]
0x18000b158  mov     rdx, rsi; unsigned __int16 *
0x18000b15b  test    r9, r9
0x18000b15e  jz      short loc_18000B182
0x18000b160  mov     [rsp+278h+Arguments], rax
0x18000b165  mov     qword ptr [rsp+278h+nSize], rcx
0x18000b16a  mov     eax, [rbx+40h]
0x18000b16d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000b171  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000b178  mov     rcx, r14; this
0x18000b17b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b180  jmp     short loc_18000B199
0x18000b182  mov     [rsp+278h+lpBuffer], rax
0x18000b187  mov     r9, rcx; unsigned __int16 *
0x18000b18a  lea     r8, aHsP; "%hs!%p: "
0x18000b191  mov     rcx, r14; this
0x18000b194  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b199  mov     r14, rax
0x18000b19c  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000b1a3  test    r9, r9
0x18000b1a6  jz      short loc_18000B1BD
0x18000b1a8  lea     r8, aCallerP; "(caller: %p) "
0x18000b1af  mov     rdx, rsi; unsigned __int16 *
0x18000b1b2  mov     rcx, rax; this
0x18000b1b5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b1ba  mov     r14, rax
0x18000b1bd  call    cs:__imp_GetCurrentThreadId
0x18000b1c4  nop     dword ptr [rax+rax+00h]
0x18000b1c9  lea     rcx, [rsp+278h+Buffer]
0x18000b1ce  mov     [rsp+278h+var_240], rcx
0x18000b1d3  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000b1d7  mov     [rsp+278h+nSize], eax
0x18000b1db  mov     eax, [rbx+44h]
0x18000b1de  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000b1e2  mov     r9, rdi; unsigned __int16 *
0x18000b1e5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000b1ec  mov     rdx, rsi; unsigned __int16 *
0x18000b1ef  mov     rcx, r14; this
0x18000b1f2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b1f7  cmp     [rbx+18h], r15
0x18000b1fb  jnz     short loc_18000B20D
0x18000b1fd  cmp     [rbx+48h], r15
0x18000b201  jnz     short loc_18000B20D
0x18000b203  cmp     [rbx+30h], r15
0x18000b207  jz      loc_18000B29D
0x18000b20d  lea     r8, asc_18004C608; "    "
0x18000b214  mov     rdx, rsi; unsigned __int16 *
0x18000b217  mov     rcx, rax; this
0x18000b21a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b21f  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000b223  test    r9, r9
0x18000b226  jz      short loc_18000B23A
0x18000b228  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000b22f  mov     rdx, rsi; unsigned __int16 *
0x18000b232  mov     rcx, rax; this
0x18000b235  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b23a  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000b23e  test    r9, r9
0x18000b241  jz      short loc_18000B255
0x18000b243  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000b24a  mov     rdx, rsi; unsigned __int16 *
0x18000b24d  mov     rcx, rax; this
0x18000b250  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b255  mov     rcx, [rbx+28h]
0x18000b259  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000b25d  mov     rdx, rsi; unsigned __int16 *
0x18000b260  test    rcx, rcx
0x18000b263  jz      short loc_18000B27B
0x18000b265  mov     [rsp+278h+lpBuffer], rcx
0x18000b26a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000b271  mov     rcx, rax; this
0x18000b274  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b279  jmp     short loc_18000B29D
0x18000b27b  mov     rcx, rax; this
0x18000b27e  test    r9, r9
0x18000b281  jz      short loc_18000B291
0x18000b283  lea     r8, aHs; "[%hs]\n"
0x18000b28a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b28f  jmp     short loc_18000B29D
0x18000b291  lea     r8, asc_18004C680; "\n"
0x18000b298  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b29d  xor     eax, eax
0x18000b29f  mov     rcx, [rsp+278h+var_38]
0x18000b2a7  xor     rcx, rsp; StackCookie
0x18000b2aa  call    __security_check_cookie
0x18000b2af  mov     rbx, [rsp+278h+arg_18]
0x18000b2b7  add     rsp, 250h
0x18000b2be  pop     r15
0x18000b2c0  pop     r14
0x18000b2c2  pop     rdi
0x18000b2c3  pop     rsi
0x18000b2c4  pop     rbp
0x18000b2c5  retn
```
