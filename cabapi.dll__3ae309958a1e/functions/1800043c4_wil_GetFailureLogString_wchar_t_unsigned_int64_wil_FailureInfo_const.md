# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800043c4`
- end: `0x180004685`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800027a4`
- `0x180002a18`
- `0x180004d6c`
- `0x180006890`

## callees

- `0x180001540`
- `0x180001fd6`
- `0x1800043c4`
- `0x180005074`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004582`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004582`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004501`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004501`

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
  LPWSTR lpBuffer; // [rsp+20h] [rbp-268h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-268h]
  DWORD nSize[2]; // [rsp+28h] [rbp-260h]
  va_list *Arguments; // [rsp+30h] [rbp-258h]
  WCHAR Buffer[256]; // [rsp+50h] [rbp-238h] BYREF

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
          v7 = (const char *)&pszCabPath;
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
                          Buffer,
                          -2);
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
0x1800043c4  mov     rax, rsp
0x1800043c7  push    rbp
0x1800043c8  push    rsi
0x1800043c9  push    rdi
0x1800043ca  push    r14
0x1800043cc  push    r15
0x1800043ce  sub     rsp, 260h
0x1800043d5  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x1800043de  mov     [rax+20h], rbx
0x1800043e2  mov     rax, cs:__security_cookie
0x1800043e9  xor     rax, rsp
0x1800043ec  mov     [rsp+288h+var_38], rax
0x1800043f4  mov     rbx, r8
0x1800043f7  mov     rsi, rdx
0x1800043fa  mov     r14, rcx
0x1800043fd  xor     r15d, r15d
0x180004400  test    rdx, rdx
0x180004403  jz      loc_18000465C
0x180004409  test    rcx, rcx
0x18000440c  jz      loc_18000465C
0x180004412  mov     [rcx], r15w
0x180004416  mov     rax, cs:g_pfnResultLoggingCallback
0x18000441d  test    rax, rax
0x180004420  jz      short loc_180004443
0x180004422  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004429  jz      short loc_180004443
0x18000442b  mov     r8, rdx
0x18000442e  mov     rdx, rcx
0x180004431  mov     rcx, rbx
0x180004434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004439  cmp     [r14], r15w
0x18000443d  jnz     loc_18000465C
0x180004443  mov     ecx, [rbx]
0x180004445  mov     bpl, 8
0x180004448  test    ecx, ecx
0x18000444a  jz      short loc_180004495
0x18000444c  sub     ecx, 1
0x18000444f  jz      short loc_18000447D
0x180004451  sub     ecx, 1
0x180004454  jz      short loc_18000446D
0x180004456  cmp     ecx, 1
0x180004459  jz      short loc_180004464
0x18000445b  lea     rdi, pszCabPath
0x180004462  jmp     short loc_18000449C
0x180004464  lea     rdi, aFailfast; "FailFast"
0x18000446b  jmp     short loc_18000449C
0x18000446d  lea     rax, aLoghr; "LogHr"
0x180004474  lea     rdi, aLognt; "LogNt"
0x18000447b  jmp     short loc_18000448B
0x18000447d  lea     rax, aReturnhr; "ReturnHr"
0x180004484  lea     rdi, aReturnnt; "ReturnNt"
0x18000448b  test    [rbx+4], bpl
0x18000448f  cmovz   rdi, rax
0x180004493  jmp     short loc_18000449C
0x180004495  lea     rdi, aException; "Exception"
0x18000449c  xor     edx, edx; Val
0x18000449e  mov     r8d, 200h; Size
0x1800044a4  lea     rcx, [rsp+288h+Buffer]; void *
0x1800044a9  call    memset_0
0x1800044ae  test    [rbx+4], bpl
0x1800044b2  jz      short loc_1800044D7
0x1800044b4  mov     ebp, [rbx+0Ch]
0x1800044b7  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x1800044be  test    rax, rax
0x1800044c1  jz      short loc_180004507
0x1800044c3  mov     r8d, 100h
0x1800044c9  lea     rdx, [rsp+288h+Buffer]
0x1800044ce  mov     ecx, ebp
0x1800044d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044d5  jmp     short loc_180004507
0x1800044d7  mov     ebp, [rbx+8]
0x1800044da  mov     [rsp+288h+Arguments], r15; Arguments
0x1800044df  mov     [rsp+288h+nSize], 100h; nSize
0x1800044e7  lea     rax, [rsp+288h+Buffer]
0x1800044ec  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x1800044f1  mov     r9d, 400h; dwLanguageId
0x1800044f7  mov     r8d, ebp; dwMessageId
0x1800044fa  xor     edx, edx; lpSource
0x1800044fc  mov     ecx, 1200h; dwFlags
0x180004501  call    cs:__imp_FormatMessageW
0x180004507  lea     rsi, [r14+rsi*2]
0x18000450b  mov     r9, [rbx+38h]; wchar_t *
0x18000450f  mov     rax, [rbx+88h]
0x180004516  mov     rcx, [rbx+80h]
0x18000451d  mov     rdx, rsi; wchar_t *
0x180004520  test    r9, r9
0x180004523  jz      short loc_180004547
0x180004525  mov     [rsp+288h+Arguments], rax
0x18000452a  mov     qword ptr [rsp+288h+nSize], rcx
0x18000452f  mov     eax, [rbx+40h]
0x180004532  mov     dword ptr [rsp+288h+lpBuffer], eax
0x180004536  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000453d  mov     rcx, r14; this
0x180004540  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004545  jmp     short loc_18000455E
0x180004547  mov     [rsp+288h+lpBuffer], rax
0x18000454c  mov     r9, rcx; wchar_t *
0x18000454f  lea     r8, aHsP; "%hs!%p: "
0x180004556  mov     rcx, r14; this
0x180004559  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000455e  mov     r14, rax
0x180004561  mov     r9, [rbx+90h]; wchar_t *
0x180004568  test    r9, r9
0x18000456b  jz      short loc_180004582
0x18000456d  lea     r8, aCallerP; "(caller: %p) "
0x180004574  mov     rdx, rsi; wchar_t *
0x180004577  mov     rcx, rax; this
0x18000457a  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000457f  mov     r14, rax
0x180004582  call    cs:__imp_GetCurrentThreadId
0x180004588  lea     rcx, [rsp+288h+Buffer]
0x18000458d  mov     [rsp+288h+var_250], rcx
0x180004592  mov     dword ptr [rsp+288h+Arguments], ebp
0x180004596  mov     [rsp+288h+nSize], eax
0x18000459a  mov     eax, [rbx+44h]
0x18000459d  mov     dword ptr [rsp+288h+lpBuffer], eax
0x1800045a1  mov     r9, rdi; wchar_t *
0x1800045a4  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800045ab  mov     rdx, rsi; wchar_t *
0x1800045ae  mov     rcx, r14; this
0x1800045b1  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800045b6  cmp     [rbx+18h], r15
0x1800045ba  jnz     short loc_1800045CC
0x1800045bc  cmp     [rbx+48h], r15
0x1800045c0  jnz     short loc_1800045CC
0x1800045c2  cmp     [rbx+30h], r15
0x1800045c6  jz      loc_18000465C
0x1800045cc  lea     r8, asc_180017E28; "    "
0x1800045d3  mov     rdx, rsi; wchar_t *
0x1800045d6  mov     rcx, rax; this
0x1800045d9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800045de  mov     r9, [rbx+18h]; wchar_t *
0x1800045e2  test    r9, r9
0x1800045e5  jz      short loc_1800045F9
0x1800045e7  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800045ee  mov     rdx, rsi; wchar_t *
0x1800045f1  mov     rcx, rax; this
0x1800045f4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800045f9  mov     r9, [rbx+48h]; wchar_t *
0x1800045fd  test    r9, r9
0x180004600  jz      short loc_180004614
0x180004602  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180004609  mov     rdx, rsi; wchar_t *
0x18000460c  mov     rcx, rax; this
0x18000460f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004614  mov     rcx, [rbx+28h]
0x180004618  mov     r9, [rbx+30h]; wchar_t *
0x18000461c  mov     rdx, rsi; wchar_t *
0x18000461f  test    rcx, rcx
0x180004622  jz      short loc_18000463A
0x180004624  mov     [rsp+288h+lpBuffer], rcx
0x180004629  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004630  mov     rcx, rax; this
0x180004633  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004638  jmp     short loc_18000465C
0x18000463a  mov     rcx, rax; this
0x18000463d  test    r9, r9
0x180004640  jz      short loc_180004650
0x180004642  lea     r8, aHs; "[%hs]\n"
0x180004649  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000464e  jmp     short loc_18000465C
0x180004650  lea     r8, asc_180017EA0; "\n"
0x180004657  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000465c  xor     eax, eax
0x18000465e  mov     rcx, [rsp+288h+var_38]
0x180004666  xor     rcx, rsp; StackCookie
0x180004669  call    __security_check_cookie
0x18000466e  mov     rbx, [rsp+288h+arg_18]
0x180004676  add     rsp, 260h
0x18000467d  pop     r15
0x18000467f  pop     r14
0x180004681  pop     rdi
0x180004682  pop     rsi
0x180004683  pop     rbp
0x180004684  retn
```
