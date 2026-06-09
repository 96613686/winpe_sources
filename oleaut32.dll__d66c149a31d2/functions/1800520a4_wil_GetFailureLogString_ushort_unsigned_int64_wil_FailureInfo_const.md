# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800520a4`
- end: `0x18005235a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18004f5f4`
- `0x180052f34`

## callees

- `0x18004d900`
- `0x18004e530`
- `0x1800520a4`
- `0x180053234`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800521d6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800521d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052257`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052257`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        STRSAFE_LPWSTR pszDest,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, STRSAFE_LPWSTR, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rdi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rsi
  __int64 v13; // rax
  wchar_t *v14; // rax
  const unsigned __int16 *v15; // r9
  wchar_t *v16; // r14
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
  if ( !pszDest )
    return 0;
  v7 = (void (__fastcall *)(__int64, STRSAFE_LPWSTR, unsigned __int16 *, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
  *pszDest = 0;
  if ( v7 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      v7(a3, pszDest, a2, a4);
      if ( *pszDest )
        return 0;
    }
  }
  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      v9 = "ReturnHr";
      v8 = "ReturnNt";
    }
    else
    {
      if ( *(_DWORD *)a3 != 2 )
      {
        if ( *(_DWORD *)a3 == 3 )
          v8 = "FailFast";
        else
          v8 = qword_1800AD360;
        goto LABEL_18;
      }
      v9 = "LogHr";
      v8 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v8 = v9;
    goto LABEL_18;
  }
  v8 = "Exception";
LABEL_18:
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
  {
    v10 = *(_DWORD *)(a3 + 12);
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(v10, Buffer, 0x100u);
  }
  else
  {
    v10 = *(_DWORD *)(a3 + 8);
    FormatMessageW(0x1200u, 0, v10, 0x400u, Buffer, 0x100u, 0);
  }
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = &pszDest[(_QWORD)a2];
  v13 = *(_QWORD *)(a3 + 136);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(pszDest, v12, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, *(_QWORD *)(a3 + 128), v13);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(pszDest, v12, L"%hs!%p: ", *(const unsigned __int16 **)(a3 + 128), v13);
  }
  v15 = *(const unsigned __int16 **)(a3 + 144);
  v16 = v14;
  if ( v15 )
    v16 = wil::details::LogStringPrintf(v14, v12, L"(caller: %p) ", v15);
  LODWORD(Arguments) = v10;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = wil::details::LogStringPrintf(
          v16,
          v12,
          L"%hs(%d) tid(%x) %08X %ws",
          (const unsigned __int16 *)v8,
          lpBuffera,
          *(_QWORD *)nSize,
          Arguments,
          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v12, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf(v19, v12, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf(v19, v12, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf(v19, v12, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf(v19, v12, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf(v19, v12, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800520a4  mov     [rsp+arg_18], rbx
0x1800520a9  push    rbp
0x1800520aa  push    rsi
0x1800520ab  push    rdi
0x1800520ac  push    r14
0x1800520ae  push    r15
0x1800520b0  sub     rsp, 250h
0x1800520b7  mov     rax, cs:__security_cookie
0x1800520be  xor     rax, rsp
0x1800520c1  mov     [rsp+278h+var_38], rax
0x1800520c9  xor     r15d, r15d
0x1800520cc  mov     rbx, r8
0x1800520cf  mov     rsi, rdx
0x1800520d2  mov     r14, rcx
0x1800520d5  test    rdx, rdx
0x1800520d8  jz      loc_180052331
0x1800520de  test    rcx, rcx
0x1800520e1  jz      loc_180052331
0x1800520e7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800520ee  mov     [rcx], r15w
0x1800520f2  test    rax, rax
0x1800520f5  jz      short loc_180052118
0x1800520f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800520fe  jz      short loc_180052118
0x180052100  mov     r8, rdx
0x180052103  mov     rdx, rcx
0x180052106  mov     rcx, rbx
0x180052109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005210e  cmp     [r14], r15w
0x180052112  jnz     loc_180052331
0x180052118  mov     ecx, [rbx]
0x18005211a  mov     bpl, 8
0x18005211d  test    ecx, ecx
0x18005211f  jz      short loc_18005216A
0x180052121  sub     ecx, 1
0x180052124  jz      short loc_180052152
0x180052126  sub     ecx, 1
0x180052129  jz      short loc_180052142
0x18005212b  cmp     ecx, 1
0x18005212e  jz      short loc_180052139
0x180052130  lea     rdi, qword_1800AD360
0x180052137  jmp     short loc_180052171
0x180052139  lea     rdi, aFailfast; "FailFast"
0x180052140  jmp     short loc_180052171
0x180052142  lea     rax, aLoghr; "LogHr"
0x180052149  lea     rdi, aLognt; "LogNt"
0x180052150  jmp     short loc_180052160
0x180052152  lea     rax, aReturnhr; "ReturnHr"
0x180052159  lea     rdi, aReturnnt; "ReturnNt"
0x180052160  test    [rbx+4], bpl
0x180052164  cmovz   rdi, rax
0x180052168  jmp     short loc_180052171
0x18005216a  lea     rdi, aException; "Exception"
0x180052171  xor     edx, edx; Val
0x180052173  lea     rcx, [rsp+278h+Buffer]; void *
0x180052178  mov     r8d, 200h; Size
0x18005217e  call    memset_0
0x180052183  test    [rbx+4], bpl
0x180052187  jz      short loc_1800521AC
0x180052189  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180052190  mov     ebp, [rbx+0Ch]
0x180052193  test    rax, rax
0x180052196  jz      short loc_1800521DC
0x180052198  mov     r8d, 100h
0x18005219e  lea     rdx, [rsp+278h+Buffer]
0x1800521a3  mov     ecx, ebp
0x1800521a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800521aa  jmp     short loc_1800521DC
0x1800521ac  mov     ebp, [rbx+8]
0x1800521af  lea     rax, [rsp+278h+Buffer]
0x1800521b4  mov     [rsp+278h+Arguments], r15; Arguments
0x1800521b9  mov     r8d, ebp; dwMessageId
0x1800521bc  mov     [rsp+278h+nSize], 100h; nSize
0x1800521c4  mov     r9d, 400h; dwLanguageId
0x1800521ca  xor     edx, edx; lpSource
0x1800521cc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800521d1  mov     ecx, 1200h; dwFlags
0x1800521d6  call    cs:__imp_FormatMessageW
0x1800521dc  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800521e0  lea     rsi, [r14+rsi*2]
0x1800521e4  mov     rax, [rbx+88h]
0x1800521eb  mov     rdx, rsi; unsigned __int16 *
0x1800521ee  mov     rcx, [rbx+80h]
0x1800521f5  test    r9, r9
0x1800521f8  jz      short loc_18005221C
0x1800521fa  mov     [rsp+278h+Arguments], rax
0x1800521ff  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180052206  mov     eax, [rbx+40h]
0x180052209  mov     qword ptr [rsp+278h+nSize], rcx
0x18005220e  mov     rcx, r14; pszDest
0x180052211  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180052215  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005221a  jmp     short loc_180052233
0x18005221c  mov     r9, rcx; unsigned __int16 *
0x18005221f  mov     [rsp+278h+lpBuffer], rax
0x180052224  mov     rcx, r14; pszDest
0x180052227  lea     r8, aHsP; "%hs!%p: "
0x18005222e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180052233  mov     r9, [rbx+90h]; unsigned __int16 *
0x18005223a  mov     r14, rax
0x18005223d  test    r9, r9
0x180052240  jz      short loc_180052257
0x180052242  lea     r8, aCallerP; "(caller: %p) "
0x180052249  mov     rdx, rsi; unsigned __int16 *
0x18005224c  mov     rcx, rax; pszDest
0x18005224f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180052254  mov     r14, rax
0x180052257  call    cs:__imp_GetCurrentThreadId
0x18005225d  lea     rcx, [rsp+278h+Buffer]
0x180052262  mov     r9, rdi; unsigned __int16 *
0x180052265  mov     [rsp+278h+var_240], rcx
0x18005226a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180052271  mov     dword ptr [rsp+278h+Arguments], ebp
0x180052275  mov     rdx, rsi; unsigned __int16 *
0x180052278  mov     [rsp+278h+nSize], eax
0x18005227c  mov     rcx, r14; pszDest
0x18005227f  mov     eax, [rbx+44h]
0x180052282  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180052286  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005228b  cmp     [rbx+18h], r15
0x18005228f  jnz     short loc_1800522A1
0x180052291  cmp     [rbx+48h], r15
0x180052295  jnz     short loc_1800522A1
0x180052297  cmp     [rbx+30h], r15
0x18005229b  jz      loc_180052331
0x1800522a1  lea     r8, asc_1800B0F50; "    "
0x1800522a8  mov     rdx, rsi; unsigned __int16 *
0x1800522ab  mov     rcx, rax; pszDest
0x1800522ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800522b3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800522b7  test    r9, r9
0x1800522ba  jz      short loc_1800522CE
0x1800522bc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800522c3  mov     rdx, rsi; unsigned __int16 *
0x1800522c6  mov     rcx, rax; pszDest
0x1800522c9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800522ce  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800522d2  test    r9, r9
0x1800522d5  jz      short loc_1800522E9
0x1800522d7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800522de  mov     rdx, rsi; unsigned __int16 *
0x1800522e1  mov     rcx, rax; pszDest
0x1800522e4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800522e9  mov     rcx, [rbx+28h]
0x1800522ed  mov     rdx, rsi; unsigned __int16 *
0x1800522f0  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800522f4  test    rcx, rcx
0x1800522f7  jz      short loc_18005230F
0x1800522f9  mov     [rsp+278h+lpBuffer], rcx
0x1800522fe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180052305  mov     rcx, rax; pszDest
0x180052308  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005230d  jmp     short loc_180052331
0x18005230f  mov     rcx, rax; pszDest
0x180052312  test    r9, r9
0x180052315  jz      short loc_180052325
0x180052317  lea     r8, aHs; "[%hs]\n"
0x18005231e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180052323  jmp     short loc_180052331
0x180052325  lea     r8, asc_1800B0FC8; "\n"
0x18005232c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180052331  xor     eax, eax
0x180052333  mov     rcx, [rsp+278h+var_38]
0x18005233b  xor     rcx, rsp; StackCookie
0x18005233e  call    __security_check_cookie
0x180052343  mov     rbx, [rsp+278h+arg_18]
0x18005234b  add     rsp, 250h
0x180052352  pop     r15
0x180052354  pop     r14
0x180052356  pop     rdi
0x180052357  pop     rsi
0x180052358  pop     rbp
0x180052359  retn
```
