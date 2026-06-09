# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180003784`
- end: `0x180003a3a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x180002374`
- `0x1800025f4`
- `0x1800040e8`
- `0x180005920`
- `0x180006e90`
- `0x1800072f0`
- `0x18000aa5f`
- `0x18000ab93`

## callees

- `0x180001520`
- `0x180001f9e`
- `0x180003784`
- `0x1800043e8`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003937`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003937`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800038b6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800038b6`

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
          v7 = (const char *)&byte_18000D6EF;
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
0x180003784  mov     [rsp+arg_18], rbx
0x180003789  push    rbp
0x18000378a  push    rsi
0x18000378b  push    rdi
0x18000378c  push    r14
0x18000378e  push    r15
0x180003790  sub     rsp, 250h
0x180003797  mov     rax, cs:__security_cookie
0x18000379e  xor     rax, rsp
0x1800037a1  mov     [rsp+278h+var_38], rax
0x1800037a9  mov     rbx, r8
0x1800037ac  mov     rsi, rdx
0x1800037af  mov     r14, rcx
0x1800037b2  xor     r15d, r15d
0x1800037b5  test    rdx, rdx
0x1800037b8  jz      loc_180003A11
0x1800037be  test    rcx, rcx
0x1800037c1  jz      loc_180003A11
0x1800037c7  mov     [rcx], r15w
0x1800037cb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800037d2  test    rax, rax
0x1800037d5  jz      short loc_1800037F8
0x1800037d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800037de  jz      short loc_1800037F8
0x1800037e0  mov     r8, rdx
0x1800037e3  mov     rdx, rcx
0x1800037e6  mov     rcx, rbx
0x1800037e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037ee  cmp     [r14], r15w
0x1800037f2  jnz     loc_180003A11
0x1800037f8  mov     ecx, [rbx]
0x1800037fa  mov     bpl, 8
0x1800037fd  test    ecx, ecx
0x1800037ff  jz      short loc_18000384A
0x180003801  sub     ecx, 1
0x180003804  jz      short loc_180003832
0x180003806  sub     ecx, 1
0x180003809  jz      short loc_180003822
0x18000380b  cmp     ecx, 1
0x18000380e  jz      short loc_180003819
0x180003810  lea     rdi, byte_18000D6EF
0x180003817  jmp     short loc_180003851
0x180003819  lea     rdi, aFailfast; "FailFast"
0x180003820  jmp     short loc_180003851
0x180003822  lea     rax, aLoghr; "LogHr"
0x180003829  lea     rdi, aLognt; "LogNt"
0x180003830  jmp     short loc_180003840
0x180003832  lea     rax, aReturnhr; "ReturnHr"
0x180003839  lea     rdi, aReturnnt; "ReturnNt"
0x180003840  test    [rbx+4], bpl
0x180003844  cmovz   rdi, rax
0x180003848  jmp     short loc_180003851
0x18000384a  lea     rdi, aException; "Exception"
0x180003851  xor     edx, edx; Val
0x180003853  mov     r8d, 200h; Size
0x180003859  lea     rcx, [rsp+278h+Buffer]; void *
0x18000385e  call    memset_0
0x180003863  test    [rbx+4], bpl
0x180003867  jz      short loc_18000388C
0x180003869  mov     ebp, [rbx+0Ch]
0x18000386c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180003873  test    rax, rax
0x180003876  jz      short loc_1800038BC
0x180003878  mov     r8d, 100h
0x18000387e  lea     rdx, [rsp+278h+Buffer]
0x180003883  mov     ecx, ebp
0x180003885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000388a  jmp     short loc_1800038BC
0x18000388c  mov     ebp, [rbx+8]
0x18000388f  mov     [rsp+278h+Arguments], r15; Arguments
0x180003894  mov     [rsp+278h+nSize], 100h; nSize
0x18000389c  lea     rax, [rsp+278h+Buffer]
0x1800038a1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800038a6  mov     r9d, 400h; dwLanguageId
0x1800038ac  mov     r8d, ebp; dwMessageId
0x1800038af  xor     edx, edx; lpSource
0x1800038b1  mov     ecx, 1200h; dwFlags
0x1800038b6  call    cs:__imp_FormatMessageW
0x1800038bc  lea     rsi, [r14+rsi*2]
0x1800038c0  mov     r9, [rbx+38h]; wchar_t *
0x1800038c4  mov     rax, [rbx+88h]
0x1800038cb  mov     rcx, [rbx+80h]
0x1800038d2  mov     rdx, rsi; wchar_t *
0x1800038d5  test    r9, r9
0x1800038d8  jz      short loc_1800038FC
0x1800038da  mov     [rsp+278h+Arguments], rax
0x1800038df  mov     qword ptr [rsp+278h+nSize], rcx
0x1800038e4  mov     eax, [rbx+40h]
0x1800038e7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800038eb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800038f2  mov     rcx, r14; this
0x1800038f5  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800038fa  jmp     short loc_180003913
0x1800038fc  mov     [rsp+278h+lpBuffer], rax
0x180003901  mov     r9, rcx; wchar_t *
0x180003904  lea     r8, aHsP; "%hs!%p: "
0x18000390b  mov     rcx, r14; this
0x18000390e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180003913  mov     r14, rax
0x180003916  mov     r9, [rbx+90h]; wchar_t *
0x18000391d  test    r9, r9
0x180003920  jz      short loc_180003937
0x180003922  lea     r8, aCallerP; "(caller: %p) "
0x180003929  mov     rdx, rsi; wchar_t *
0x18000392c  mov     rcx, rax; this
0x18000392f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180003934  mov     r14, rax
0x180003937  call    cs:__imp_GetCurrentThreadId
0x18000393d  lea     rcx, [rsp+278h+Buffer]
0x180003942  mov     [rsp+278h+var_240], rcx
0x180003947  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000394b  mov     [rsp+278h+nSize], eax
0x18000394f  mov     eax, [rbx+44h]
0x180003952  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003956  mov     r9, rdi; wchar_t *
0x180003959  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180003960  mov     rdx, rsi; wchar_t *
0x180003963  mov     rcx, r14; this
0x180003966  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000396b  cmp     [rbx+18h], r15
0x18000396f  jnz     short loc_180003981
0x180003971  cmp     [rbx+48h], r15
0x180003975  jnz     short loc_180003981
0x180003977  cmp     [rbx+30h], r15
0x18000397b  jz      loc_180003A11
0x180003981  lea     r8, asc_18000D7F0; "    "
0x180003988  mov     rdx, rsi; wchar_t *
0x18000398b  mov     rcx, rax; this
0x18000398e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180003993  mov     r9, [rbx+18h]; wchar_t *
0x180003997  test    r9, r9
0x18000399a  jz      short loc_1800039AE
0x18000399c  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800039a3  mov     rdx, rsi; wchar_t *
0x1800039a6  mov     rcx, rax; this
0x1800039a9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800039ae  mov     r9, [rbx+48h]; wchar_t *
0x1800039b2  test    r9, r9
0x1800039b5  jz      short loc_1800039C9
0x1800039b7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800039be  mov     rdx, rsi; wchar_t *
0x1800039c1  mov     rcx, rax; this
0x1800039c4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800039c9  mov     rcx, [rbx+28h]
0x1800039cd  mov     r9, [rbx+30h]; wchar_t *
0x1800039d1  mov     rdx, rsi; wchar_t *
0x1800039d4  test    rcx, rcx
0x1800039d7  jz      short loc_1800039EF
0x1800039d9  mov     [rsp+278h+lpBuffer], rcx
0x1800039de  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800039e5  mov     rcx, rax; this
0x1800039e8  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800039ed  jmp     short loc_180003A11
0x1800039ef  mov     rcx, rax; this
0x1800039f2  test    r9, r9
0x1800039f5  jz      short loc_180003A05
0x1800039f7  lea     r8, aHs; "[%hs]\n"
0x1800039fe  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180003a03  jmp     short loc_180003A11
0x180003a05  lea     r8, asc_18000D868; "\n"
0x180003a0c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180003a11  xor     eax, eax
0x180003a13  mov     rcx, [rsp+278h+var_38]
0x180003a1b  xor     rcx, rsp; StackCookie
0x180003a1e  call    __security_check_cookie
0x180003a23  mov     rbx, [rsp+278h+arg_18]
0x180003a2b  add     rsp, 250h
0x180003a32  pop     r15
0x180003a34  pop     r14
0x180003a36  pop     rdi
0x180003a37  pop     rsi
0x180003a38  pop     rbp
0x180003a39  retn
```
