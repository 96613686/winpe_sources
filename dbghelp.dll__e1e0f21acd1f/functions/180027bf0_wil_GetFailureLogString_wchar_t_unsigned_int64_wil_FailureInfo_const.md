# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180027bf0`
- end: `0x180027e55`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `613`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180029950`
- `0x1801dca50`
- `0x1801dcb1d`

## callees

- `0x180027bf0`
- `0x180027fb0`
- `0x1801d6350`
- `0x1801d63b0`

## import_xrefs

- `api-ms-win-core-misc-l1-1-0!FormatMessageW` at `0x180027cd7`
- `api-ms-win-core-misc-l1-1-0!FormatMessageW` at `0x180027cd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027d58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027d58`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v7; // rbp
  wchar_t *v8; // rsi
  const wchar_t *v9; // rcx
  __int64 v10; // rax
  const wchar_t *v11; // r9
  wchar_t *v12; // rax
  wil::details *v13; // r14
  const wchar_t *v14; // r9
  wil::details *v15; // rax
  const wchar_t *v16; // r9
  wchar_t *v17; // rax
  const wchar_t *v18; // r9
  const wchar_t *v19; // r9
  const wchar_t *v20; // r9
  LPWSTR lpBuffer; // [rsp+20h] [rbp-268h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-268h]
  DWORD nSize[2]; // [rsp+28h] [rbp-260h]
  va_list *Arguments; // [rsp+30h] [rbp-258h]
  WCHAR Buffer[256]; // [rsp+50h] [rbp-238h] BYREF

  if ( a2 )
  {
    if ( this )
    {
      *(_WORD *)this = 0;
      if ( !g_pfnResultLoggingCallback
        || !wil::details::g_resultMessageCallbackSet
        || (g_pfnResultLoggingCallback(a3, this, a2, a4), !*(_WORD *)this) )
      {
        if ( *(_DWORD *)a3 )
        {
          switch ( *(_DWORD *)a3 )
          {
            case 1:
              v7 = "ReturnHr";
              break;
            case 2:
              v7 = "LogHr";
              break;
            case 3:
              v7 = "FailFast";
              break;
            default:
              v7 = (const char *)&MultiByteStr;
              break;
          }
        }
        else
        {
          v7 = "Exception";
        }
        Buffer[0] = 0;
        FormatMessageW(0x1200u, 0, *(_DWORD *)(a3 + 4), 0x400u, Buffer, 0x100u, 0);
        v8 = (wchar_t *)((char *)this + 2 * (_QWORD)a2);
        v9 = *(const wchar_t **)(a3 + 48);
        v10 = *(_QWORD *)(a3 + 128);
        v11 = *(const wchar_t **)(a3 + 120);
        if ( v9 )
        {
          LODWORD(lpBuffer) = *(_DWORD *)(a3 + 56);
          v12 = wil::details::LogStringPrintf(this, v8, L"%hs(%u)\\%hs!%p: ", v9, lpBuffer, v11, v10);
        }
        else
        {
          v12 = wil::details::LogStringPrintf(this, v8, L"%hs!%p: ", v11, v10);
        }
        v13 = (wil::details *)v12;
        v14 = *(const wchar_t **)(a3 + 136);
        if ( v14 )
          v13 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v12, v8, L"(caller: %p) ", v14);
        LODWORD(Arguments) = *(_DWORD *)(a3 + 4);
        nSize[0] = GetCurrentThreadId();
        LODWORD(lpBuffera) = *(_DWORD *)(a3 + 60);
        v15 = (wil::details *)wil::details::LogStringPrintf(
                                v13,
                                v8,
                                L"%hs(%d) tid(%x) %08X %ws",
                                (const wchar_t *)v7,
                                lpBuffera,
                                *(_QWORD *)nSize,
                                Arguments,
                                Buffer,
                                -2);
        if ( *(_QWORD *)(a3 + 16) || *(_QWORD *)(a3 + 64) || *(_QWORD *)(a3 + 40) )
        {
          v17 = wil::details::LogStringPrintf(v15, v8, L"    ", v16);
          v18 = *(const wchar_t **)(a3 + 16);
          if ( v18 )
            v17 = wil::details::LogStringPrintf((wil::details *)v17, v8, L"Msg:[%ws] ", v18);
          v19 = *(const wchar_t **)(a3 + 64);
          if ( v19 )
            v17 = wil::details::LogStringPrintf((wil::details *)v17, v8, L"CallContext:[%hs] ", v19);
          v20 = *(const wchar_t **)(a3 + 40);
          if ( *(_QWORD *)(a3 + 32) )
          {
            wil::details::LogStringPrintf((wil::details *)v17, v8, L"[%hs(%hs)]\n", v20, *(_QWORD *)(a3 + 32));
          }
          else if ( v20 )
          {
            wil::details::LogStringPrintf((wil::details *)v17, v8, L"[%hs]\n", v20);
          }
          else
          {
            wil::details::LogStringPrintf((wil::details *)v17, v8, L"\n", 0);
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180027bf0  push    rbx
0x180027bf2  push    rbp
0x180027bf3  push    rsi
0x180027bf4  push    rdi
0x180027bf5  push    r14
0x180027bf7  sub     rsp, 260h
0x180027bfe  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x180027c07  mov     rax, cs:__security_cookie
0x180027c0e  xor     rax, rsp
0x180027c11  mov     [rsp+288h+var_38], rax
0x180027c19  mov     rdi, r8
0x180027c1c  mov     rsi, rdx
0x180027c1f  mov     rbx, rcx
0x180027c22  test    rdx, rdx
0x180027c25  jz      loc_180027E35
0x180027c2b  test    rcx, rcx
0x180027c2e  jz      loc_180027E35
0x180027c34  xor     r14d, r14d
0x180027c37  mov     [rcx], r14w
0x180027c3b  mov     rax, cs:g_pfnResultLoggingCallback
0x180027c42  test    rax, rax
0x180027c45  jz      short loc_180027C69
0x180027c47  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r14b; bool wil::details::g_resultMessageCallbackSet
0x180027c4e  jz      short loc_180027C69
0x180027c50  mov     r8, rdx
0x180027c53  mov     rdx, rcx
0x180027c56  mov     rcx, rdi
0x180027c59  call    cs:__guard_dispatch_icall_fptr
0x180027c5f  cmp     [rbx], r14w
0x180027c63  jnz     loc_180027E35
0x180027c69  mov     ecx, [rdi]
0x180027c6b  test    ecx, ecx
0x180027c6d  jz      short loc_180027CA2
0x180027c6f  sub     ecx, 1
0x180027c72  jz      short loc_180027C99
0x180027c74  sub     ecx, 1
0x180027c77  jz      short loc_180027C90
0x180027c79  cmp     ecx, 1
0x180027c7c  jz      short loc_180027C87
0x180027c7e  lea     rbp, MultiByteStr
0x180027c85  jmp     short loc_180027CA9
0x180027c87  lea     rbp, aFailfast; "FailFast"
0x180027c8e  jmp     short loc_180027CA9
0x180027c90  lea     rbp, aLoghr; "LogHr"
0x180027c97  jmp     short loc_180027CA9
0x180027c99  lea     rbp, aReturnhr; "ReturnHr"
0x180027ca0  jmp     short loc_180027CA9
0x180027ca2  lea     rbp, aException; "Exception"
0x180027ca9  mov     [rsp+288h+Buffer], r14w
0x180027caf  mov     [rsp+288h+Arguments], r14; Arguments
0x180027cb4  mov     [rsp+288h+nSize], 100h; nSize
0x180027cbc  lea     rax, [rsp+288h+Buffer]
0x180027cc1  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x180027cc6  mov     r9d, 400h; dwLanguageId
0x180027ccc  mov     r8d, [rdi+4]; dwMessageId
0x180027cd0  xor     edx, edx; lpSource
0x180027cd2  mov     ecx, 1200h; dwFlags
0x180027cd7  call    cs:__imp_FormatMessageW
0x180027cdd  lea     rsi, [rbx+rsi*2]
0x180027ce1  mov     rcx, [rdi+30h]
0x180027ce5  mov     rax, [rdi+80h]
0x180027cec  mov     r9, [rdi+78h]; wchar_t *
0x180027cf0  mov     rdx, rsi; wchar_t *
0x180027cf3  test    rcx, rcx
0x180027cf6  jz      short loc_180027D1D
0x180027cf8  mov     [rsp+288h+Arguments], rax
0x180027cfd  mov     qword ptr [rsp+288h+nSize], r9
0x180027d02  mov     eax, [rdi+38h]
0x180027d05  mov     dword ptr [rsp+288h+lpBuffer], eax
0x180027d09  mov     r9, rcx; wchar_t *
0x180027d0c  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180027d13  mov     rcx, rbx; this
0x180027d16  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180027d1b  jmp     short loc_180027D31
0x180027d1d  mov     [rsp+288h+lpBuffer], rax
0x180027d22  lea     r8, aHsP; "%hs!%p: "
0x180027d29  mov     rcx, rbx; this
0x180027d2c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180027d31  mov     r14, rax
0x180027d34  mov     r9, [rdi+88h]; wchar_t *
0x180027d3b  test    r9, r9
0x180027d3e  jz      short loc_180027D55
0x180027d40  lea     r8, aCallerP; "(caller: %p) "
0x180027d47  mov     rdx, rsi; wchar_t *
0x180027d4a  mov     rcx, rax; this
0x180027d4d  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180027d52  mov     r14, rax
0x180027d55  mov     ebx, [rdi+4]
0x180027d58  call    cs:__imp_GetCurrentThreadId
0x180027d5e  lea     rcx, [rsp+288h+Buffer]
0x180027d63  mov     [rsp+288h+var_250], rcx
0x180027d68  mov     dword ptr [rsp+288h+Arguments], ebx
0x180027d6c  mov     [rsp+288h+nSize], eax
0x180027d70  mov     eax, [rdi+3Ch]
0x180027d73  mov     dword ptr [rsp+288h+lpBuffer], eax
0x180027d77  mov     r9, rbp; wchar_t *
0x180027d7a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180027d81  mov     rdx, rsi; wchar_t *
0x180027d84  mov     rcx, r14; this
0x180027d87  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180027d8c  cmp     qword ptr [rdi+10h], 0
0x180027d91  jnz     short loc_180027DA5
0x180027d93  cmp     qword ptr [rdi+40h], 0
0x180027d98  jnz     short loc_180027DA5
0x180027d9a  cmp     qword ptr [rdi+28h], 0
0x180027d9f  jz      loc_180027E35
0x180027da5  lea     r8, asc_180256800; "    "
0x180027dac  mov     rdx, rsi; wchar_t *
0x180027daf  mov     rcx, rax; this
0x180027db2  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180027db7  mov     r9, [rdi+10h]; wchar_t *
0x180027dbb  test    r9, r9
0x180027dbe  jz      short loc_180027DD2
0x180027dc0  lea     r8, aMsgWs; "Msg:[%ws] "
0x180027dc7  mov     rdx, rsi; wchar_t *
0x180027dca  mov     rcx, rax; this
0x180027dcd  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180027dd2  mov     r9, [rdi+40h]; wchar_t *
0x180027dd6  test    r9, r9
0x180027dd9  jz      short loc_180027DED
0x180027ddb  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180027de2  mov     rdx, rsi; wchar_t *
0x180027de5  mov     rcx, rax; this
0x180027de8  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180027ded  mov     rcx, [rdi+20h]
0x180027df1  mov     r9, [rdi+28h]; wchar_t *
0x180027df5  mov     rdx, rsi; wchar_t *
0x180027df8  test    rcx, rcx
0x180027dfb  jz      short loc_180027E13
0x180027dfd  mov     [rsp+288h+lpBuffer], rcx
0x180027e02  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180027e09  mov     rcx, rax; this
0x180027e0c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180027e11  jmp     short loc_180027E35
0x180027e13  mov     rcx, rax; this
0x180027e16  test    r9, r9
0x180027e19  jz      short loc_180027E29
0x180027e1b  lea     r8, aHs_0; "[%hs]\n"
0x180027e22  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180027e27  jmp     short loc_180027E35
0x180027e29  lea     r8, asc_1802499F4; "\n"
0x180027e30  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180027e35  xor     eax, eax
0x180027e37  mov     rcx, [rsp+288h+var_38]
0x180027e3f  xor     rcx, rsp; StackCookie
0x180027e42  call    __security_check_cookie
0x180027e47  add     rsp, 260h
0x180027e4e  pop     r14
0x180027e50  pop     rdi
0x180027e51  pop     rsi
0x180027e52  pop     rbp
0x180027e53  pop     rbx
0x180027e54  retn
```
