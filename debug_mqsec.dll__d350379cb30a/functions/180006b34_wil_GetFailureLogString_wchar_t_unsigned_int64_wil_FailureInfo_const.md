# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006b34`
- end: `0x180006dea`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wchar_t *this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180004edc`
- `0x180005144`
- `0x180007ae8`
- `0x18000b0d0`

## callees

- `0x180006b34`
- `0x180007de8`
- `0x18002f0ba`
- `0x18002f0e0`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180006ce7`
- `KERNEL32!GetCurrentThreadId` at `0x180006ce7`
- `KERNEL32!FormatMessageW` at `0x180006c66`
- `KERNEL32!FormatMessageW` at `0x180006c66`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wchar_t *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rsi
  const wchar_t *v11; // r9
  __int64 v12; // rax
  const wchar_t *v13; // rcx
  wchar_t *v14; // rax
  wchar_t *v15; // r14
  const wchar_t *v16; // r9
  wchar_t *v17; // rax
  const wchar_t *v18; // r9
  wchar_t *v19; // rax
  const wchar_t *v20; // r9
  const wchar_t *v21; // r9
  const wchar_t *v22; // r9
  LPWSTR lpBuffer; // [rsp+20h] [rbp-258h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-258h]
  DWORD nSize[2]; // [rsp+28h] [rbp-250h]
  va_list *Arguments; // [rsp+30h] [rbp-248h]
  WCHAR Buffer[256]; // [rsp+40h] [rbp-238h] BYREF

  if ( !a2 )
    return 0;
  if ( !this )
    return 0;
  *this = 0;
  if ( g_pfnResultLoggingCallback )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      g_pfnResultLoggingCallback(a3, this, a2);
      if ( *this )
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
          v7 = (const char *)&byte_180034A70;
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
  v10 = &this[(_QWORD)a2];
  v11 = *(const wchar_t **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const wchar_t **)(a3 + 128);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v10, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, v13, v12);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v10, L"%hs!%p: ", v13, v12);
  }
  v15 = v14;
  v16 = *(const wchar_t **)(a3 + 144);
  if ( v16 )
    v15 = wil::details::LogStringPrintf(v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = wil::details::LogStringPrintf(
          v15,
          v10,
          L"%hs(%d) tid(%x) %08X %ws",
          (const wchar_t *)v7,
          lpBuffera,
          *(_QWORD *)nSize,
          Arguments,
          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v10, L"    ", v18);
    v20 = *(const wchar_t **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf(v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const wchar_t **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf(v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const wchar_t **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf(v19, v10, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf(v19, v10, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf(v19, v10, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180006b34  mov     [rsp+arg_18], rbx
0x180006b39  push    rbp
0x180006b3a  push    rsi
0x180006b3b  push    rdi
0x180006b3c  push    r14
0x180006b3e  push    r15
0x180006b40  sub     rsp, 250h
0x180006b47  mov     rax, cs:__security_cookie
0x180006b4e  xor     rax, rsp
0x180006b51  mov     [rsp+278h+var_38], rax
0x180006b59  mov     rbx, r8
0x180006b5c  mov     rsi, rdx
0x180006b5f  mov     r14, rcx
0x180006b62  xor     r15d, r15d
0x180006b65  test    rdx, rdx
0x180006b68  jz      loc_180006DC1
0x180006b6e  test    rcx, rcx
0x180006b71  jz      loc_180006DC1
0x180006b77  mov     [rcx], r15w
0x180006b7b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006b82  test    rax, rax
0x180006b85  jz      short loc_180006BA8
0x180006b87  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006b8e  jz      short loc_180006BA8
0x180006b90  mov     r8, rdx
0x180006b93  mov     rdx, rcx
0x180006b96  mov     rcx, rbx
0x180006b99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b9e  cmp     [r14], r15w
0x180006ba2  jnz     loc_180006DC1
0x180006ba8  mov     ecx, [rbx]
0x180006baa  mov     bpl, 8
0x180006bad  test    ecx, ecx
0x180006baf  jz      short loc_180006BFA
0x180006bb1  sub     ecx, 1
0x180006bb4  jz      short loc_180006BE2
0x180006bb6  sub     ecx, 1
0x180006bb9  jz      short loc_180006BD2
0x180006bbb  cmp     ecx, 1
0x180006bbe  jz      short loc_180006BC9
0x180006bc0  lea     rdi, byte_180034A70
0x180006bc7  jmp     short loc_180006C01
0x180006bc9  lea     rdi, aFailfast; "FailFast"
0x180006bd0  jmp     short loc_180006C01
0x180006bd2  lea     rax, aLoghr; "LogHr"
0x180006bd9  lea     rdi, aLognt; "LogNt"
0x180006be0  jmp     short loc_180006BF0
0x180006be2  lea     rax, aReturnhr; "ReturnHr"
0x180006be9  lea     rdi, aReturnnt; "ReturnNt"
0x180006bf0  test    [rbx+4], bpl
0x180006bf4  cmovz   rdi, rax
0x180006bf8  jmp     short loc_180006C01
0x180006bfa  lea     rdi, aException; "Exception"
0x180006c01  xor     edx, edx; Val
0x180006c03  mov     r8d, 200h; Size
0x180006c09  lea     rcx, [rsp+278h+Buffer]; void *
0x180006c0e  call    memset_0
0x180006c13  test    [rbx+4], bpl
0x180006c17  jz      short loc_180006C3C
0x180006c19  mov     ebp, [rbx+0Ch]
0x180006c1c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180006c23  test    rax, rax
0x180006c26  jz      short loc_180006C6C
0x180006c28  mov     r8d, 100h
0x180006c2e  lea     rdx, [rsp+278h+Buffer]
0x180006c33  mov     ecx, ebp
0x180006c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c3a  jmp     short loc_180006C6C
0x180006c3c  mov     ebp, [rbx+8]
0x180006c3f  mov     [rsp+278h+Arguments], r15; Arguments
0x180006c44  mov     [rsp+278h+nSize], 100h; nSize
0x180006c4c  lea     rax, [rsp+278h+Buffer]
0x180006c51  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006c56  mov     r9d, 400h; dwLanguageId
0x180006c5c  mov     r8d, ebp; dwMessageId
0x180006c5f  xor     edx, edx; lpSource
0x180006c61  mov     ecx, 1200h; dwFlags
0x180006c66  call    cs:__imp_FormatMessageW
0x180006c6c  lea     rsi, [r14+rsi*2]
0x180006c70  mov     r9, [rbx+38h]; wchar_t *
0x180006c74  mov     rax, [rbx+88h]
0x180006c7b  mov     rcx, [rbx+80h]
0x180006c82  mov     rdx, rsi; wchar_t *
0x180006c85  test    r9, r9
0x180006c88  jz      short loc_180006CAC
0x180006c8a  mov     [rsp+278h+Arguments], rax
0x180006c8f  mov     qword ptr [rsp+278h+nSize], rcx
0x180006c94  mov     eax, [rbx+40h]
0x180006c97  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006c9b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006ca2  mov     rcx, r14; this
0x180006ca5  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006caa  jmp     short loc_180006CC3
0x180006cac  mov     [rsp+278h+lpBuffer], rax
0x180006cb1  mov     r9, rcx; wchar_t *
0x180006cb4  lea     r8, aHsP; "%hs!%p: "
0x180006cbb  mov     rcx, r14; this
0x180006cbe  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006cc3  mov     r14, rax
0x180006cc6  mov     r9, [rbx+90h]; wchar_t *
0x180006ccd  test    r9, r9
0x180006cd0  jz      short loc_180006CE7
0x180006cd2  lea     r8, aCallerP; "(caller: %p) "
0x180006cd9  mov     rdx, rsi; wchar_t *
0x180006cdc  mov     rcx, rax; this
0x180006cdf  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006ce4  mov     r14, rax
0x180006ce7  call    cs:__imp_GetCurrentThreadId
0x180006ced  lea     rcx, [rsp+278h+Buffer]
0x180006cf2  mov     [rsp+278h+var_240], rcx
0x180006cf7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180006cfb  mov     [rsp+278h+nSize], eax
0x180006cff  mov     eax, [rbx+44h]
0x180006d02  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006d06  mov     r9, rdi; wchar_t *
0x180006d09  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006d10  mov     rdx, rsi; wchar_t *
0x180006d13  mov     rcx, r14; this
0x180006d16  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006d1b  cmp     [rbx+18h], r15
0x180006d1f  jnz     short loc_180006D31
0x180006d21  cmp     [rbx+48h], r15
0x180006d25  jnz     short loc_180006D31
0x180006d27  cmp     [rbx+30h], r15
0x180006d2b  jz      loc_180006DC1
0x180006d31  lea     r8, asc_1800346B8; "    "
0x180006d38  mov     rdx, rsi; wchar_t *
0x180006d3b  mov     rcx, rax; this
0x180006d3e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006d43  mov     r9, [rbx+18h]; wchar_t *
0x180006d47  test    r9, r9
0x180006d4a  jz      short loc_180006D5E
0x180006d4c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006d53  mov     rdx, rsi; wchar_t *
0x180006d56  mov     rcx, rax; this
0x180006d59  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006d5e  mov     r9, [rbx+48h]; wchar_t *
0x180006d62  test    r9, r9
0x180006d65  jz      short loc_180006D79
0x180006d67  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180006d6e  mov     rdx, rsi; wchar_t *
0x180006d71  mov     rcx, rax; this
0x180006d74  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006d79  mov     rcx, [rbx+28h]
0x180006d7d  mov     r9, [rbx+30h]; wchar_t *
0x180006d81  mov     rdx, rsi; wchar_t *
0x180006d84  test    rcx, rcx
0x180006d87  jz      short loc_180006D9F
0x180006d89  mov     [rsp+278h+lpBuffer], rcx
0x180006d8e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006d95  mov     rcx, rax; this
0x180006d98  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006d9d  jmp     short loc_180006DC1
0x180006d9f  mov     rcx, rax; this
0x180006da2  test    r9, r9
0x180006da5  jz      short loc_180006DB5
0x180006da7  lea     r8, aHs; "[%hs]\n"
0x180006dae  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006db3  jmp     short loc_180006DC1
0x180006db5  lea     r8, asc_180034730; "\n"
0x180006dbc  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006dc1  xor     eax, eax
0x180006dc3  mov     rcx, [rsp+278h+var_38]
0x180006dcb  xor     rcx, rsp; StackCookie
0x180006dce  call    __security_check_cookie
0x180006dd3  mov     rbx, [rsp+278h+arg_18]
0x180006ddb  add     rsp, 250h
0x180006de2  pop     r15
0x180006de4  pop     r14
0x180006de6  pop     rdi
0x180006de7  pop     rsi
0x180006de8  pop     rbp
0x180006de9  retn
```
