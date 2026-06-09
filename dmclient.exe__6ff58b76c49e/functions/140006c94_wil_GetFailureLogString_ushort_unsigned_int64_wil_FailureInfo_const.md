# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140006c94`
- end: `0x140006f4a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x1400035c0`
- `0x140003828`
- `0x140003adc`
- `0x140007b00`
- `0x14000c360`

## callees

- `0x140006c94`
- `0x140007e00`
- `0x1400187b2`
- `0x1400187e0`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006e47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006e47`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140006dc6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140006dc6`

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
          v7 = (const char *)&word_14001C5D2;
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
0x140006c94  mov     [rsp+arg_18], rbx
0x140006c99  push    rbp
0x140006c9a  push    rsi
0x140006c9b  push    rdi
0x140006c9c  push    r14
0x140006c9e  push    r15
0x140006ca0  sub     rsp, 250h
0x140006ca7  mov     rax, cs:__security_cookie
0x140006cae  xor     rax, rsp
0x140006cb1  mov     [rsp+278h+var_38], rax
0x140006cb9  mov     rbx, r8
0x140006cbc  mov     rsi, rdx
0x140006cbf  mov     r14, rcx
0x140006cc2  xor     r15d, r15d
0x140006cc5  test    rdx, rdx
0x140006cc8  jz      loc_140006F21
0x140006cce  test    rcx, rcx
0x140006cd1  jz      loc_140006F21
0x140006cd7  mov     [rcx], r15w
0x140006cdb  mov     rax, cs:g_pfnResultLoggingCallback
0x140006ce2  test    rax, rax
0x140006ce5  jz      short loc_140006D08
0x140006ce7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140006cee  jz      short loc_140006D08
0x140006cf0  mov     r8, rdx
0x140006cf3  mov     rdx, rcx
0x140006cf6  mov     rcx, rbx
0x140006cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006cfe  cmp     [r14], r15w
0x140006d02  jnz     loc_140006F21
0x140006d08  mov     ecx, [rbx]
0x140006d0a  mov     bpl, 8
0x140006d0d  test    ecx, ecx
0x140006d0f  jz      short loc_140006D5A
0x140006d11  sub     ecx, 1
0x140006d14  jz      short loc_140006D42
0x140006d16  sub     ecx, 1
0x140006d19  jz      short loc_140006D32
0x140006d1b  cmp     ecx, 1
0x140006d1e  jz      short loc_140006D29
0x140006d20  lea     rdi, word_14001C5D2
0x140006d27  jmp     short loc_140006D61
0x140006d29  lea     rdi, aFailfast; "FailFast"
0x140006d30  jmp     short loc_140006D61
0x140006d32  lea     rax, aLoghr; "LogHr"
0x140006d39  lea     rdi, aLognt; "LogNt"
0x140006d40  jmp     short loc_140006D50
0x140006d42  lea     rax, aReturnhr; "ReturnHr"
0x140006d49  lea     rdi, aReturnnt; "ReturnNt"
0x140006d50  test    [rbx+4], bpl
0x140006d54  cmovz   rdi, rax
0x140006d58  jmp     short loc_140006D61
0x140006d5a  lea     rdi, aException; "Exception"
0x140006d61  xor     edx, edx; Val
0x140006d63  mov     r8d, 200h; Size
0x140006d69  lea     rcx, [rsp+278h+Buffer]; void *
0x140006d6e  call    memset_0
0x140006d73  test    [rbx+4], bpl
0x140006d77  jz      short loc_140006D9C
0x140006d79  mov     ebp, [rbx+0Ch]
0x140006d7c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140006d83  test    rax, rax
0x140006d86  jz      short loc_140006DCC
0x140006d88  mov     r8d, 100h
0x140006d8e  lea     rdx, [rsp+278h+Buffer]
0x140006d93  mov     ecx, ebp
0x140006d95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d9a  jmp     short loc_140006DCC
0x140006d9c  mov     ebp, [rbx+8]
0x140006d9f  mov     [rsp+278h+Arguments], r15; Arguments
0x140006da4  mov     [rsp+278h+nSize], 100h; nSize
0x140006dac  lea     rax, [rsp+278h+Buffer]
0x140006db1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140006db6  mov     r9d, 400h; dwLanguageId
0x140006dbc  mov     r8d, ebp; dwMessageId
0x140006dbf  xor     edx, edx; lpSource
0x140006dc1  mov     ecx, 1200h; dwFlags
0x140006dc6  call    cs:__imp_FormatMessageW
0x140006dcc  lea     rsi, [r14+rsi*2]
0x140006dd0  mov     r9, [rbx+38h]; unsigned __int16 *
0x140006dd4  mov     rax, [rbx+88h]
0x140006ddb  mov     rcx, [rbx+80h]
0x140006de2  mov     rdx, rsi; unsigned __int16 *
0x140006de5  test    r9, r9
0x140006de8  jz      short loc_140006E0C
0x140006dea  mov     [rsp+278h+Arguments], rax
0x140006def  mov     qword ptr [rsp+278h+nSize], rcx
0x140006df4  mov     eax, [rbx+40h]
0x140006df7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140006dfb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140006e02  mov     rcx, r14; this
0x140006e05  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006e0a  jmp     short loc_140006E23
0x140006e0c  mov     [rsp+278h+lpBuffer], rax
0x140006e11  mov     r9, rcx; unsigned __int16 *
0x140006e14  lea     r8, aHsP; "%hs!%p: "
0x140006e1b  mov     rcx, r14; this
0x140006e1e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006e23  mov     r14, rax
0x140006e26  mov     r9, [rbx+90h]; unsigned __int16 *
0x140006e2d  test    r9, r9
0x140006e30  jz      short loc_140006E47
0x140006e32  lea     r8, aCallerP; "(caller: %p) "
0x140006e39  mov     rdx, rsi; unsigned __int16 *
0x140006e3c  mov     rcx, rax; this
0x140006e3f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006e44  mov     r14, rax
0x140006e47  call    cs:__imp_GetCurrentThreadId
0x140006e4d  lea     rcx, [rsp+278h+Buffer]
0x140006e52  mov     [rsp+278h+var_240], rcx
0x140006e57  mov     dword ptr [rsp+278h+Arguments], ebp
0x140006e5b  mov     [rsp+278h+nSize], eax
0x140006e5f  mov     eax, [rbx+44h]
0x140006e62  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140006e66  mov     r9, rdi; unsigned __int16 *
0x140006e69  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140006e70  mov     rdx, rsi; unsigned __int16 *
0x140006e73  mov     rcx, r14; this
0x140006e76  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006e7b  cmp     [rbx+18h], r15
0x140006e7f  jnz     short loc_140006E91
0x140006e81  cmp     [rbx+48h], r15
0x140006e85  jnz     short loc_140006E91
0x140006e87  cmp     [rbx+30h], r15
0x140006e8b  jz      loc_140006F21
0x140006e91  lea     r8, asc_14001C6C0; "    "
0x140006e98  mov     rdx, rsi; unsigned __int16 *
0x140006e9b  mov     rcx, rax; this
0x140006e9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006ea3  mov     r9, [rbx+18h]; unsigned __int16 *
0x140006ea7  test    r9, r9
0x140006eaa  jz      short loc_140006EBE
0x140006eac  lea     r8, aMsgWs; "Msg:[%ws] "
0x140006eb3  mov     rdx, rsi; unsigned __int16 *
0x140006eb6  mov     rcx, rax; this
0x140006eb9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006ebe  mov     r9, [rbx+48h]; unsigned __int16 *
0x140006ec2  test    r9, r9
0x140006ec5  jz      short loc_140006ED9
0x140006ec7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140006ece  mov     rdx, rsi; unsigned __int16 *
0x140006ed1  mov     rcx, rax; this
0x140006ed4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006ed9  mov     rcx, [rbx+28h]
0x140006edd  mov     r9, [rbx+30h]; unsigned __int16 *
0x140006ee1  mov     rdx, rsi; unsigned __int16 *
0x140006ee4  test    rcx, rcx
0x140006ee7  jz      short loc_140006EFF
0x140006ee9  mov     [rsp+278h+lpBuffer], rcx
0x140006eee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140006ef5  mov     rcx, rax; this
0x140006ef8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006efd  jmp     short loc_140006F21
0x140006eff  mov     rcx, rax; this
0x140006f02  test    r9, r9
0x140006f05  jz      short loc_140006F15
0x140006f07  lea     r8, aHs; "[%hs]\n"
0x140006f0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006f13  jmp     short loc_140006F21
0x140006f15  lea     r8, asc_14001C738; "\n"
0x140006f1c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006f21  xor     eax, eax
0x140006f23  mov     rcx, [rsp+278h+var_38]
0x140006f2b  xor     rcx, rsp; StackCookie
0x140006f2e  call    __security_check_cookie
0x140006f33  mov     rbx, [rsp+278h+arg_18]
0x140006f3b  add     rsp, 250h
0x140006f42  pop     r15
0x140006f44  pop     r14
0x140006f46  pop     rdi
0x140006f47  pop     rsi
0x140006f48  pop     rbp
0x140006f49  retn
```
