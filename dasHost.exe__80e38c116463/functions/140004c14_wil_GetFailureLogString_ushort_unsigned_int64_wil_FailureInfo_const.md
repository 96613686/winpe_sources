# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140004c14`
- end: `0x140004eca`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x14000268c`
- `0x14000290c`
- `0x140002bb8`
- `0x1400085e0`
- `0x14001aaa3`
- `0x14001abd7`

## callees

- `0x140001570`
- `0x1400020d0`
- `0x140004c14`
- `0x140005580`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004dc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004dc7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140004d46`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140004d46`

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
          v7 = (const char *)&dword_140021104;
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
0x140004c14  mov     [rsp+arg_18], rbx
0x140004c19  push    rbp
0x140004c1a  push    rsi
0x140004c1b  push    rdi
0x140004c1c  push    r14
0x140004c1e  push    r15
0x140004c20  sub     rsp, 250h
0x140004c27  mov     rax, cs:__security_cookie
0x140004c2e  xor     rax, rsp
0x140004c31  mov     [rsp+278h+var_38], rax
0x140004c39  mov     rbx, r8
0x140004c3c  mov     rsi, rdx
0x140004c3f  mov     r14, rcx
0x140004c42  xor     r15d, r15d
0x140004c45  test    rdx, rdx
0x140004c48  jz      loc_140004EA1
0x140004c4e  test    rcx, rcx
0x140004c51  jz      loc_140004EA1
0x140004c57  mov     [rcx], r15w
0x140004c5b  mov     rax, cs:g_pfnResultLoggingCallback
0x140004c62  test    rax, rax
0x140004c65  jz      short loc_140004C88
0x140004c67  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140004c6e  jz      short loc_140004C88
0x140004c70  mov     r8, rdx
0x140004c73  mov     rdx, rcx
0x140004c76  mov     rcx, rbx
0x140004c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004c7e  cmp     [r14], r15w
0x140004c82  jnz     loc_140004EA1
0x140004c88  mov     ecx, [rbx]
0x140004c8a  mov     bpl, 8
0x140004c8d  test    ecx, ecx
0x140004c8f  jz      short loc_140004CDA
0x140004c91  sub     ecx, 1
0x140004c94  jz      short loc_140004CC2
0x140004c96  sub     ecx, 1
0x140004c99  jz      short loc_140004CB2
0x140004c9b  cmp     ecx, 1
0x140004c9e  jz      short loc_140004CA9
0x140004ca0  lea     rdi, dword_140021104
0x140004ca7  jmp     short loc_140004CE1
0x140004ca9  lea     rdi, aFailfast; "FailFast"
0x140004cb0  jmp     short loc_140004CE1
0x140004cb2  lea     rax, aLoghr; "LogHr"
0x140004cb9  lea     rdi, aLognt; "LogNt"
0x140004cc0  jmp     short loc_140004CD0
0x140004cc2  lea     rax, aReturnhr; "ReturnHr"
0x140004cc9  lea     rdi, aReturnnt; "ReturnNt"
0x140004cd0  test    [rbx+4], bpl
0x140004cd4  cmovz   rdi, rax
0x140004cd8  jmp     short loc_140004CE1
0x140004cda  lea     rdi, aException; "Exception"
0x140004ce1  xor     edx, edx; Val
0x140004ce3  mov     r8d, 200h; Size
0x140004ce9  lea     rcx, [rsp+278h+Buffer]; void *
0x140004cee  call    memset_0
0x140004cf3  test    [rbx+4], bpl
0x140004cf7  jz      short loc_140004D1C
0x140004cf9  mov     ebp, [rbx+0Ch]
0x140004cfc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140004d03  test    rax, rax
0x140004d06  jz      short loc_140004D4C
0x140004d08  mov     r8d, 100h
0x140004d0e  lea     rdx, [rsp+278h+Buffer]
0x140004d13  mov     ecx, ebp
0x140004d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004d1a  jmp     short loc_140004D4C
0x140004d1c  mov     ebp, [rbx+8]
0x140004d1f  mov     [rsp+278h+Arguments], r15; Arguments
0x140004d24  mov     [rsp+278h+nSize], 100h; nSize
0x140004d2c  lea     rax, [rsp+278h+Buffer]
0x140004d31  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140004d36  mov     r9d, 400h; dwLanguageId
0x140004d3c  mov     r8d, ebp; dwMessageId
0x140004d3f  xor     edx, edx; lpSource
0x140004d41  mov     ecx, 1200h; dwFlags
0x140004d46  call    cs:__imp_FormatMessageW
0x140004d4c  lea     rsi, [r14+rsi*2]
0x140004d50  mov     r9, [rbx+38h]; unsigned __int16 *
0x140004d54  mov     rax, [rbx+88h]
0x140004d5b  mov     rcx, [rbx+80h]
0x140004d62  mov     rdx, rsi; unsigned __int16 *
0x140004d65  test    r9, r9
0x140004d68  jz      short loc_140004D8C
0x140004d6a  mov     [rsp+278h+Arguments], rax
0x140004d6f  mov     qword ptr [rsp+278h+nSize], rcx
0x140004d74  mov     eax, [rbx+40h]
0x140004d77  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140004d7b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140004d82  mov     rcx, r14; this
0x140004d85  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004d8a  jmp     short loc_140004DA3
0x140004d8c  mov     [rsp+278h+lpBuffer], rax
0x140004d91  mov     r9, rcx; unsigned __int16 *
0x140004d94  lea     r8, aHsP; "%hs!%p: "
0x140004d9b  mov     rcx, r14; this
0x140004d9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004da3  mov     r14, rax
0x140004da6  mov     r9, [rbx+90h]; unsigned __int16 *
0x140004dad  test    r9, r9
0x140004db0  jz      short loc_140004DC7
0x140004db2  lea     r8, aCallerP; "(caller: %p) "
0x140004db9  mov     rdx, rsi; unsigned __int16 *
0x140004dbc  mov     rcx, rax; this
0x140004dbf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004dc4  mov     r14, rax
0x140004dc7  call    cs:__imp_GetCurrentThreadId
0x140004dcd  lea     rcx, [rsp+278h+Buffer]
0x140004dd2  mov     [rsp+278h+var_240], rcx
0x140004dd7  mov     dword ptr [rsp+278h+Arguments], ebp
0x140004ddb  mov     [rsp+278h+nSize], eax
0x140004ddf  mov     eax, [rbx+44h]
0x140004de2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140004de6  mov     r9, rdi; unsigned __int16 *
0x140004de9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140004df0  mov     rdx, rsi; unsigned __int16 *
0x140004df3  mov     rcx, r14; this
0x140004df6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004dfb  cmp     [rbx+18h], r15
0x140004dff  jnz     short loc_140004E11
0x140004e01  cmp     [rbx+48h], r15
0x140004e05  jnz     short loc_140004E11
0x140004e07  cmp     [rbx+30h], r15
0x140004e0b  jz      loc_140004EA1
0x140004e11  lea     r8, asc_140021208; "    "
0x140004e18  mov     rdx, rsi; unsigned __int16 *
0x140004e1b  mov     rcx, rax; this
0x140004e1e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004e23  mov     r9, [rbx+18h]; unsigned __int16 *
0x140004e27  test    r9, r9
0x140004e2a  jz      short loc_140004E3E
0x140004e2c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140004e33  mov     rdx, rsi; unsigned __int16 *
0x140004e36  mov     rcx, rax; this
0x140004e39  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004e3e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140004e42  test    r9, r9
0x140004e45  jz      short loc_140004E59
0x140004e47  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140004e4e  mov     rdx, rsi; unsigned __int16 *
0x140004e51  mov     rcx, rax; this
0x140004e54  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004e59  mov     rcx, [rbx+28h]
0x140004e5d  mov     r9, [rbx+30h]; unsigned __int16 *
0x140004e61  mov     rdx, rsi; unsigned __int16 *
0x140004e64  test    rcx, rcx
0x140004e67  jz      short loc_140004E7F
0x140004e69  mov     [rsp+278h+lpBuffer], rcx
0x140004e6e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140004e75  mov     rcx, rax; this
0x140004e78  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004e7d  jmp     short loc_140004EA1
0x140004e7f  mov     rcx, rax; this
0x140004e82  test    r9, r9
0x140004e85  jz      short loc_140004E95
0x140004e87  lea     r8, aHs; "[%hs]\n"
0x140004e8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004e93  jmp     short loc_140004EA1
0x140004e95  lea     r8, asc_140021280; "\n"
0x140004e9c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004ea1  xor     eax, eax
0x140004ea3  mov     rcx, [rsp+278h+var_38]
0x140004eab  xor     rcx, rsp; StackCookie
0x140004eae  call    __security_check_cookie
0x140004eb3  mov     rbx, [rsp+278h+arg_18]
0x140004ebb  add     rsp, 250h
0x140004ec2  pop     r15
0x140004ec4  pop     r14
0x140004ec6  pop     rdi
0x140004ec7  pop     rsi
0x140004ec8  pop     rbp
0x140004ec9  retn
```
