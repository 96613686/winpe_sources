# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800b3314`
- end: `0x1800b35ca`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wchar_t *String, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800b2280`
- `0x1800b3c70`
- `0x1800b5800`

## callees

- `0x1800a9d20`
- `0x1800aa9a8`
- `0x1800b3314`
- `0x1800b3f70`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b34c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b34c7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800b3446`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800b3446`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wchar_t *String,
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
  wchar_t *v14; // rax
  wchar_t *v15; // r14
  const unsigned __int16 *v16; // r9
  wchar_t *v17; // rax
  const unsigned __int16 *v18; // r9
  wchar_t *v19; // rax
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
  if ( !String )
    return 0;
  *String = 0;
  if ( g_pfnResultLoggingCallback )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      g_pfnResultLoggingCallback(a3, String, a2);
      if ( *String )
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
          v7 = (const char *)&qword_1801F9D78;
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
  v10 = &String[(_QWORD)a2];
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const unsigned __int16 **)(a3 + 128);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(String, v10, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, v13, v12);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(String, v10, L"%hs!%p: ", v13, v12);
  }
  v15 = v14;
  v16 = *(const unsigned __int16 **)(a3 + 144);
  if ( v16 )
    v15 = wil::details::LogStringPrintf(v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = wil::details::LogStringPrintf(
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
      v19 = wil::details::LogStringPrintf(v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf(v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
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
0x1800b3314  mov     [rsp+arg_18], rbx
0x1800b3319  push    rbp
0x1800b331a  push    rsi
0x1800b331b  push    rdi
0x1800b331c  push    r14
0x1800b331e  push    r15
0x1800b3320  sub     rsp, 250h
0x1800b3327  mov     rax, cs:__security_cookie
0x1800b332e  xor     rax, rsp
0x1800b3331  mov     [rsp+278h+var_38], rax
0x1800b3339  mov     rbx, r8
0x1800b333c  mov     rsi, rdx
0x1800b333f  mov     r14, rcx
0x1800b3342  xor     r15d, r15d
0x1800b3345  test    rdx, rdx
0x1800b3348  jz      loc_1800B35A1
0x1800b334e  test    rcx, rcx
0x1800b3351  jz      loc_1800B35A1
0x1800b3357  mov     [rcx], r15w
0x1800b335b  mov     rax, cs:g_pfnResultLoggingCallback
0x1800b3362  test    rax, rax
0x1800b3365  jz      short loc_1800B3388
0x1800b3367  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800b336e  jz      short loc_1800B3388
0x1800b3370  mov     r8, rdx
0x1800b3373  mov     rdx, rcx
0x1800b3376  mov     rcx, rbx
0x1800b3379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b337e  cmp     [r14], r15w
0x1800b3382  jnz     loc_1800B35A1
0x1800b3388  mov     ecx, [rbx]
0x1800b338a  mov     bpl, 8
0x1800b338d  test    ecx, ecx
0x1800b338f  jz      short loc_1800B33DA
0x1800b3391  sub     ecx, 1
0x1800b3394  jz      short loc_1800B33C2
0x1800b3396  sub     ecx, 1
0x1800b3399  jz      short loc_1800B33B2
0x1800b339b  cmp     ecx, 1
0x1800b339e  jz      short loc_1800B33A9
0x1800b33a0  lea     rdi, qword_1801F9D78
0x1800b33a7  jmp     short loc_1800B33E1
0x1800b33a9  lea     rdi, aFailfast; "FailFast"
0x1800b33b0  jmp     short loc_1800B33E1
0x1800b33b2  lea     rax, aLoghr; "LogHr"
0x1800b33b9  lea     rdi, aLognt; "LogNt"
0x1800b33c0  jmp     short loc_1800B33D0
0x1800b33c2  lea     rax, aReturnhr; "ReturnHr"
0x1800b33c9  lea     rdi, aReturnnt; "ReturnNt"
0x1800b33d0  test    [rbx+4], bpl
0x1800b33d4  cmovz   rdi, rax
0x1800b33d8  jmp     short loc_1800B33E1
0x1800b33da  lea     rdi, aException; "Exception"
0x1800b33e1  xor     edx, edx; Val
0x1800b33e3  mov     r8d, 200h; Size
0x1800b33e9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800b33ee  call    memset_0
0x1800b33f3  test    [rbx+4], bpl
0x1800b33f7  jz      short loc_1800B341C
0x1800b33f9  mov     ebp, [rbx+0Ch]
0x1800b33fc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800b3403  test    rax, rax
0x1800b3406  jz      short loc_1800B344C
0x1800b3408  mov     r8d, 100h
0x1800b340e  lea     rdx, [rsp+278h+Buffer]
0x1800b3413  mov     ecx, ebp
0x1800b3415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b341a  jmp     short loc_1800B344C
0x1800b341c  mov     ebp, [rbx+8]
0x1800b341f  mov     [rsp+278h+Arguments], r15; Arguments
0x1800b3424  mov     [rsp+278h+nSize], 100h; nSize
0x1800b342c  lea     rax, [rsp+278h+Buffer]
0x1800b3431  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800b3436  mov     r9d, 400h; dwLanguageId
0x1800b343c  mov     r8d, ebp; dwMessageId
0x1800b343f  xor     edx, edx; lpSource
0x1800b3441  mov     ecx, 1200h; dwFlags
0x1800b3446  call    cs:__imp_FormatMessageW
0x1800b344c  lea     rsi, [r14+rsi*2]
0x1800b3450  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800b3454  mov     rax, [rbx+88h]
0x1800b345b  mov     rcx, [rbx+80h]
0x1800b3462  mov     rdx, rsi; unsigned __int16 *
0x1800b3465  test    r9, r9
0x1800b3468  jz      short loc_1800B348C
0x1800b346a  mov     [rsp+278h+Arguments], rax
0x1800b346f  mov     qword ptr [rsp+278h+nSize], rcx
0x1800b3474  mov     eax, [rbx+40h]
0x1800b3477  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800b347b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800b3482  mov     rcx, r14; String
0x1800b3485  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800b348a  jmp     short loc_1800B34A3
0x1800b348c  mov     [rsp+278h+lpBuffer], rax
0x1800b3491  mov     r9, rcx; unsigned __int16 *
0x1800b3494  lea     r8, aHsP; "%hs!%p: "
0x1800b349b  mov     rcx, r14; String
0x1800b349e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800b34a3  mov     r14, rax
0x1800b34a6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800b34ad  test    r9, r9
0x1800b34b0  jz      short loc_1800B34C7
0x1800b34b2  lea     r8, aCallerP; "(caller: %p) "
0x1800b34b9  mov     rdx, rsi; unsigned __int16 *
0x1800b34bc  mov     rcx, rax; String
0x1800b34bf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800b34c4  mov     r14, rax
0x1800b34c7  call    cs:__imp_GetCurrentThreadId
0x1800b34cd  lea     rcx, [rsp+278h+Buffer]
0x1800b34d2  mov     [rsp+278h+var_240], rcx
0x1800b34d7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800b34db  mov     [rsp+278h+nSize], eax
0x1800b34df  mov     eax, [rbx+44h]
0x1800b34e2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800b34e6  mov     r9, rdi; unsigned __int16 *
0x1800b34e9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800b34f0  mov     rdx, rsi; unsigned __int16 *
0x1800b34f3  mov     rcx, r14; String
0x1800b34f6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800b34fb  cmp     [rbx+18h], r15
0x1800b34ff  jnz     short loc_1800B3511
0x1800b3501  cmp     [rbx+48h], r15
0x1800b3505  jnz     short loc_1800B3511
0x1800b3507  cmp     [rbx+30h], r15
0x1800b350b  jz      loc_1800B35A1
0x1800b3511  lea     r8, asc_1801F9E68; "    "
0x1800b3518  mov     rdx, rsi; unsigned __int16 *
0x1800b351b  mov     rcx, rax; String
0x1800b351e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800b3523  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800b3527  test    r9, r9
0x1800b352a  jz      short loc_1800B353E
0x1800b352c  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800b3533  mov     rdx, rsi; unsigned __int16 *
0x1800b3536  mov     rcx, rax; String
0x1800b3539  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800b353e  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800b3542  test    r9, r9
0x1800b3545  jz      short loc_1800B3559
0x1800b3547  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800b354e  mov     rdx, rsi; unsigned __int16 *
0x1800b3551  mov     rcx, rax; String
0x1800b3554  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800b3559  mov     rcx, [rbx+28h]
0x1800b355d  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800b3561  mov     rdx, rsi; unsigned __int16 *
0x1800b3564  test    rcx, rcx
0x1800b3567  jz      short loc_1800B357F
0x1800b3569  mov     [rsp+278h+lpBuffer], rcx
0x1800b356e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800b3575  mov     rcx, rax; String
0x1800b3578  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800b357d  jmp     short loc_1800B35A1
0x1800b357f  mov     rcx, rax; String
0x1800b3582  test    r9, r9
0x1800b3585  jz      short loc_1800B3595
0x1800b3587  lea     r8, aHs; "[%hs]\n"
0x1800b358e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800b3593  jmp     short loc_1800B35A1
0x1800b3595  lea     r8, asc_1801F94D0; "\n"
0x1800b359c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800b35a1  xor     eax, eax
0x1800b35a3  mov     rcx, [rsp+278h+var_38]
0x1800b35ab  xor     rcx, rsp; StackCookie
0x1800b35ae  call    __security_check_cookie
0x1800b35b3  mov     rbx, [rsp+278h+arg_18]
0x1800b35bb  add     rsp, 250h
0x1800b35c2  pop     r15
0x1800b35c4  pop     r14
0x1800b35c6  pop     rdi
0x1800b35c7  pop     rsi
0x1800b35c8  pop     rbp
0x1800b35c9  retn
```
