# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180012da4`
- end: `0x18001305a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18001180c`
- `0x180013700`
- `0x180013d48`
- `0x180015cf0`

## callees

- `0x18000fcd0`
- `0x180010b2c`
- `0x180012da4`
- `0x180013a04`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012f57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012f57`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180012ed6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180012ed6`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rsi
  const wchar_t *v11; // r9
  __int64 v12; // rax
  const wchar_t *v13; // rcx
  wchar_t *v14; // rax
  wil::details *v15; // r14
  const wchar_t *v16; // r9
  wil::details *v17; // rax
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
          v7 = (const char *)&qword_18002B508;
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
  v10 = (wchar_t *)((char *)this + 2 * (_QWORD)a2);
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
  v15 = (wil::details *)v14;
  v16 = *(const wchar_t **)(a3 + 144);
  if ( v16 )
    v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
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
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const wchar_t **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const wchar_t **)(a3 + 48);
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
0x180012da4  mov     [rsp+arg_18], rbx
0x180012da9  push    rbp
0x180012daa  push    rsi
0x180012dab  push    rdi
0x180012dac  push    r14
0x180012dae  push    r15
0x180012db0  sub     rsp, 250h
0x180012db7  mov     rax, cs:__security_cookie
0x180012dbe  xor     rax, rsp
0x180012dc1  mov     [rsp+278h+var_38], rax
0x180012dc9  mov     rbx, r8
0x180012dcc  mov     rsi, rdx
0x180012dcf  mov     r14, rcx
0x180012dd2  xor     r15d, r15d
0x180012dd5  test    rdx, rdx
0x180012dd8  jz      loc_180013031
0x180012dde  test    rcx, rcx
0x180012de1  jz      loc_180013031
0x180012de7  mov     [rcx], r15w
0x180012deb  mov     rax, cs:g_pfnResultLoggingCallback
0x180012df2  test    rax, rax
0x180012df5  jz      short loc_180012E18
0x180012df7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180012dfe  jz      short loc_180012E18
0x180012e00  mov     r8, rdx
0x180012e03  mov     rdx, rcx
0x180012e06  mov     rcx, rbx
0x180012e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e0e  cmp     [r14], r15w
0x180012e12  jnz     loc_180013031
0x180012e18  mov     ecx, [rbx]
0x180012e1a  mov     bpl, 8
0x180012e1d  test    ecx, ecx
0x180012e1f  jz      short loc_180012E6A
0x180012e21  sub     ecx, 1
0x180012e24  jz      short loc_180012E52
0x180012e26  sub     ecx, 1
0x180012e29  jz      short loc_180012E42
0x180012e2b  cmp     ecx, 1
0x180012e2e  jz      short loc_180012E39
0x180012e30  lea     rdi, qword_18002B508
0x180012e37  jmp     short loc_180012E71
0x180012e39  lea     rdi, aFailfast; "FailFast"
0x180012e40  jmp     short loc_180012E71
0x180012e42  lea     rax, aLoghr; "LogHr"
0x180012e49  lea     rdi, aLognt; "LogNt"
0x180012e50  jmp     short loc_180012E60
0x180012e52  lea     rax, aReturnhr; "ReturnHr"
0x180012e59  lea     rdi, aReturnnt; "ReturnNt"
0x180012e60  test    [rbx+4], bpl
0x180012e64  cmovz   rdi, rax
0x180012e68  jmp     short loc_180012E71
0x180012e6a  lea     rdi, aException; "Exception"
0x180012e71  xor     edx, edx; Val
0x180012e73  mov     r8d, 200h; Size
0x180012e79  lea     rcx, [rsp+278h+Buffer]; void *
0x180012e7e  call    memset_0
0x180012e83  test    [rbx+4], bpl
0x180012e87  jz      short loc_180012EAC
0x180012e89  mov     ebp, [rbx+0Ch]
0x180012e8c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180012e93  test    rax, rax
0x180012e96  jz      short loc_180012EDC
0x180012e98  mov     r8d, 100h
0x180012e9e  lea     rdx, [rsp+278h+Buffer]
0x180012ea3  mov     ecx, ebp
0x180012ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012eaa  jmp     short loc_180012EDC
0x180012eac  mov     ebp, [rbx+8]
0x180012eaf  mov     [rsp+278h+Arguments], r15; Arguments
0x180012eb4  mov     [rsp+278h+nSize], 100h; nSize
0x180012ebc  lea     rax, [rsp+278h+Buffer]
0x180012ec1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180012ec6  mov     r9d, 400h; dwLanguageId
0x180012ecc  mov     r8d, ebp; dwMessageId
0x180012ecf  xor     edx, edx; lpSource
0x180012ed1  mov     ecx, 1200h; dwFlags
0x180012ed6  call    cs:__imp_FormatMessageW
0x180012edc  lea     rsi, [r14+rsi*2]
0x180012ee0  mov     r9, [rbx+38h]; wchar_t *
0x180012ee4  mov     rax, [rbx+88h]
0x180012eeb  mov     rcx, [rbx+80h]
0x180012ef2  mov     rdx, rsi; wchar_t *
0x180012ef5  test    r9, r9
0x180012ef8  jz      short loc_180012F1C
0x180012efa  mov     [rsp+278h+Arguments], rax
0x180012eff  mov     qword ptr [rsp+278h+nSize], rcx
0x180012f04  mov     eax, [rbx+40h]
0x180012f07  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180012f0b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180012f12  mov     rcx, r14; this
0x180012f15  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180012f1a  jmp     short loc_180012F33
0x180012f1c  mov     [rsp+278h+lpBuffer], rax
0x180012f21  mov     r9, rcx; wchar_t *
0x180012f24  lea     r8, aHsP; "%hs!%p: "
0x180012f2b  mov     rcx, r14; this
0x180012f2e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180012f33  mov     r14, rax
0x180012f36  mov     r9, [rbx+90h]; wchar_t *
0x180012f3d  test    r9, r9
0x180012f40  jz      short loc_180012F57
0x180012f42  lea     r8, aCallerP; "(caller: %p) "
0x180012f49  mov     rdx, rsi; wchar_t *
0x180012f4c  mov     rcx, rax; this
0x180012f4f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180012f54  mov     r14, rax
0x180012f57  call    cs:__imp_GetCurrentThreadId
0x180012f5d  lea     rcx, [rsp+278h+Buffer]
0x180012f62  mov     [rsp+278h+var_240], rcx
0x180012f67  mov     dword ptr [rsp+278h+Arguments], ebp
0x180012f6b  mov     [rsp+278h+nSize], eax
0x180012f6f  mov     eax, [rbx+44h]
0x180012f72  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180012f76  mov     r9, rdi; wchar_t *
0x180012f79  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180012f80  mov     rdx, rsi; wchar_t *
0x180012f83  mov     rcx, r14; this
0x180012f86  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180012f8b  cmp     [rbx+18h], r15
0x180012f8f  jnz     short loc_180012FA1
0x180012f91  cmp     [rbx+48h], r15
0x180012f95  jnz     short loc_180012FA1
0x180012f97  cmp     [rbx+30h], r15
0x180012f9b  jz      loc_180013031
0x180012fa1  lea     r8, asc_18002B638; "    "
0x180012fa8  mov     rdx, rsi; wchar_t *
0x180012fab  mov     rcx, rax; this
0x180012fae  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180012fb3  mov     r9, [rbx+18h]; wchar_t *
0x180012fb7  test    r9, r9
0x180012fba  jz      short loc_180012FCE
0x180012fbc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180012fc3  mov     rdx, rsi; wchar_t *
0x180012fc6  mov     rcx, rax; this
0x180012fc9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180012fce  mov     r9, [rbx+48h]; wchar_t *
0x180012fd2  test    r9, r9
0x180012fd5  jz      short loc_180012FE9
0x180012fd7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180012fde  mov     rdx, rsi; wchar_t *
0x180012fe1  mov     rcx, rax; this
0x180012fe4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180012fe9  mov     rcx, [rbx+28h]
0x180012fed  mov     r9, [rbx+30h]; wchar_t *
0x180012ff1  mov     rdx, rsi; wchar_t *
0x180012ff4  test    rcx, rcx
0x180012ff7  jz      short loc_18001300F
0x180012ff9  mov     [rsp+278h+lpBuffer], rcx
0x180012ffe  lea     r8, aHsHs_0; "[%hs(%hs)]\n"
0x180013005  mov     rcx, rax; this
0x180013008  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18001300d  jmp     short loc_180013031
0x18001300f  mov     rcx, rax; this
0x180013012  test    r9, r9
0x180013015  jz      short loc_180013025
0x180013017  lea     r8, aHs; "[%hs]\n"
0x18001301e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180013023  jmp     short loc_180013031
0x180013025  lea     r8, asc_18002B6B0; "\n"
0x18001302c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180013031  xor     eax, eax
0x180013033  mov     rcx, [rsp+278h+var_38]
0x18001303b  xor     rcx, rsp; StackCookie
0x18001303e  call    __security_check_cookie
0x180013043  mov     rbx, [rsp+278h+arg_18]
0x18001304b  add     rsp, 250h
0x180013052  pop     r15
0x180013054  pop     r14
0x180013056  pop     rdi
0x180013057  pop     rsi
0x180013058  pop     rbp
0x180013059  retn
```
