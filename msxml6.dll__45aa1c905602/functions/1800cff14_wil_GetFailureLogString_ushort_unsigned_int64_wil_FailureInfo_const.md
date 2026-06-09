# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800cff14`
- end: `0x1800d01d7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `HRESULT __fastcall(wchar_t *pszDest, unsigned __int64 cchDest, const wil::FailureInfo *failure)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800cebec`
- `0x1800d08f8`

## callees

- `0x1800cc580`
- `0x1800cc6c0`
- `0x1800cd3e4`
- `0x1800cff14`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d00cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d00cd`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800d0046`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800d0046`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wchar_t *pszDest, unsigned __int64 cchDest, wil::FailureInfo *failure)
{
  void (__fastcall *v6)(wil::FailureInfo *, wchar_t *, unsigned __int64); // rax
  const char *v7; // rdi
  const char *v8; // rax
  int status; // ebp
  const wchar_t *v10; // rsi
  wchar_t *v11; // rax
  wchar_t *v12; // r14
  wchar_t *v13; // rax
  wchar_t *v14; // rax
  const char *pszFunction; // r9
  LPWSTR lpBuffer; // [rsp+20h] [rbp-258h]
  DWORD nSize[2]; // [rsp+28h] [rbp-250h]
  va_list *Arguments; // [rsp+30h] [rbp-248h]
  wchar_t szErrorText[256]; // [rsp+40h] [rbp-238h] BYREF

  if ( !cchDest )
    return 0;
  if ( !pszDest )
    return 0;
  v6 = g_pfnResultLoggingCallback;
  *pszDest = 0;
  if ( v6 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      v6(failure, pszDest, cchDest);
      if ( *pszDest )
        return 0;
    }
  }
  if ( *(_DWORD *)failure->type )
  {
    if ( *(_DWORD *)failure->type == 1 )
    {
      v8 = "ReturnHr";
      v7 = "ReturnNt";
    }
    else
    {
      if ( *(_DWORD *)failure->type != 2 )
      {
        if ( *(_DWORD *)failure->type == 3 )
          v7 = "FailFast";
        else
          v7 = (const char *)&dword_1801C88A4;
        goto LABEL_18;
      }
      v8 = "LogHr";
      v7 = "LogNt";
    }
    if ( (failure->flags[0] & 8) == 0 )
      v7 = v8;
    goto LABEL_18;
  }
  v7 = "Exception";
LABEL_18:
  memset_0(szErrorText, 0, sizeof(szErrorText));
  if ( (failure->flags[0] & 8) != 0 )
  {
    status = failure->status;
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(status, szErrorText, 0x100u);
  }
  else
  {
    status = failure->hr;
    FormatMessageW(0x1200u, 0, status, 0x400u, szErrorText, 0x100u, 0);
  }
  v10 = &pszDest[cchDest];
  if ( failure->pszFile )
  {
    HIDWORD(Arguments) = HIDWORD(failure->returnAddress);
    nSize[1] = HIDWORD(failure->pszModule);
    v11 = wil::details::LogStringPrintf(pszDest, v10, L"%hs(%u)\\%hs!%p: ");
  }
  else
  {
    v11 = wil::details::LogStringPrintf(pszDest, v10, L"%hs!%p: ", failure->pszModule, failure->returnAddress);
  }
  v12 = v11;
  if ( failure->callerReturnAddress )
    v12 = wil::details::LogStringPrintf(v11, v10, L"(caller: %p) ");
  LODWORD(Arguments) = status;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffer) = failure->cFailureCount;
  v13 = wil::details::LogStringPrintf(
          v12,
          v10,
          L"%hs(%d) tid(%x) %08X %ws",
          v7,
          lpBuffer,
          *(_QWORD *)nSize,
          Arguments,
          szErrorText);
  if ( failure->pszMessage || failure->pszCallContext || failure->pszFunction )
  {
    v14 = wil::details::LogStringPrintf(v13, v10, L"    ");
    if ( failure->pszMessage )
      v14 = wil::details::LogStringPrintf(v14, v10, L"Msg:[%ws] ");
    if ( failure->pszCallContext )
      v14 = wil::details::LogStringPrintf(v14, v10, L"CallContext:[%hs] ");
    pszFunction = failure->pszFunction;
    if ( failure->pszCode )
    {
      wil::details::LogStringPrintf(v14, v10, L"[%hs(%hs)]\n", pszFunction, failure->pszCode);
    }
    else if ( pszFunction )
    {
      wil::details::LogStringPrintf(v14, v10, L"[%hs]\n");
    }
    else
    {
      wil::details::LogStringPrintf(v14, v10, L"\n");
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800cff14  mov     [rsp+arg_18], rbx
0x1800cff19  push    rbp
0x1800cff1a  push    rsi
0x1800cff1b  push    rdi
0x1800cff1c  push    r14
0x1800cff1e  push    r15
0x1800cff20  sub     rsp, 250h
0x1800cff27  mov     rax, cs:__security_cookie
0x1800cff2e  xor     rax, rsp
0x1800cff31  mov     [rsp+278h+var_38], rax
0x1800cff39  xor     r15d, r15d
0x1800cff3c  mov     rbx, failure
0x1800cff3f  mov     rsi, cchDest
0x1800cff42  mov     r14, pszDest
0x1800cff45  test    cchDest, cchDest
0x1800cff48  jz      loc_1800D01AD
0x1800cff4e  test    pszDest, pszDest
0x1800cff51  jz      loc_1800D01AD
0x1800cff57  mov     rax, cs:g_pfnResultLoggingCallback
0x1800cff5e  mov     [pszDest], r15w
0x1800cff62  test    rax, rax
0x1800cff65  jz      short loc_1800CFF88
0x1800cff67  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800cff6e  jz      short loc_1800CFF88
0x1800cff70  mov     failure, cchDest
0x1800cff73  mov     cchDest, pszDest
0x1800cff76  mov     pszDest, rbx
0x1800cff79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cff7e  cmp     [r14], r15w
0x1800cff82  jnz     loc_1800D01AD
0x1800cff88  mov     ecx, [rbx]
0x1800cff8a  mov     bpl, 8
0x1800cff8d  test    ecx, ecx
0x1800cff8f  jz      short loc_1800CFFDA
0x1800cff91  sub     ecx, 1
0x1800cff94  jz      short loc_1800CFFC2
0x1800cff96  sub     ecx, 1
0x1800cff99  jz      short loc_1800CFFB2
0x1800cff9b  cmp     ecx, 1
0x1800cff9e  jz      short loc_1800CFFA9
0x1800cffa0  lea     rdi, dword_1801C88A4
0x1800cffa7  jmp     short loc_1800CFFE1
0x1800cffa9  lea     rdi, aFailfast; "FailFast"
0x1800cffb0  jmp     short loc_1800CFFE1
0x1800cffb2  lea     rax, aLoghr; "LogHr"
0x1800cffb9  lea     rdi, aLognt; "LogNt"
0x1800cffc0  jmp     short loc_1800CFFD0
0x1800cffc2  lea     rax, aReturnhr; "ReturnHr"
0x1800cffc9  lea     rdi, aReturnnt; "ReturnNt"
0x1800cffd0  test    [rbx+4], bpl
0x1800cffd4  cmovz   rdi, rax
0x1800cffd8  jmp     short loc_1800CFFE1
0x1800cffda  lea     rdi, aException; "Exception"
0x1800cffe1  xor     edx, edx; Val
0x1800cffe3  lea     pszDest, [rsp+278h+szErrorText]; void *
0x1800cffe8  mov     r8d, 200h; Size
0x1800cffee  call    memset_0
0x1800cfff3  test    [rbx+4], bpl
0x1800cfff7  jz      short loc_1800D001C
0x1800cfff9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800d0000  mov     ebp, [rbx+0Ch]
0x1800d0003  test    rax, rax
0x1800d0006  jz      short loc_1800D0052
0x1800d0008  mov     r8d, 100h
0x1800d000e  lea     cchDest, [rsp+278h+szErrorText]
0x1800d0013  mov     ecx, ebp
0x1800d0015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d001a  jmp     short loc_1800D0052
0x1800d001c  mov     ebp, [rbx+8]
0x1800d001f  lea     rax, [rsp+278h+szErrorText]
0x1800d0024  mov     [rsp+278h+Arguments], r15; Arguments
0x1800d0029  mov     r8d, ebp; dwMessageId
0x1800d002c  mov     [rsp+278h+nSize], 100h; nSize
0x1800d0034  mov     r9d, 400h; dwLanguageId
0x1800d003a  xor     edx, edx; lpSource
0x1800d003c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800d0041  mov     ecx, 1200h; dwFlags
0x1800d0046  call    cs:__imp_FormatMessageW
0x1800d004d  nop     dword ptr [rax+rax+00h]
0x1800d0052  mov     r9, [rbx+38h]
0x1800d0056  lea     rsi, [r14+rsi*2]
0x1800d005a  mov     rax, [rbx+88h]
0x1800d0061  mov     cchDest, rsi; destEnd
0x1800d0064  mov     pszDest, [rbx+80h]
0x1800d006b  test    r9, r9
0x1800d006e  jz      short loc_1800D0092
0x1800d0070  mov     [rsp+278h+Arguments], rax
0x1800d0075  lea     failure, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800d007c  mov     eax, [rbx+40h]
0x1800d007f  mov     qword ptr [rsp+278h+nSize], pszDest
0x1800d0084  mov     pszDest, r14; dest
0x1800d0087  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800d008b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800d0090  jmp     short loc_1800D00A9
0x1800d0092  mov     r9, pszDest
0x1800d0095  mov     [rsp+278h+lpBuffer], rax
0x1800d009a  mov     pszDest, r14; dest
0x1800d009d  lea     failure, aHsP; "%hs!%p: "
0x1800d00a4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800d00a9  mov     r9, [rbx+90h]
0x1800d00b0  mov     r14, rax
0x1800d00b3  test    r9, r9
0x1800d00b6  jz      short loc_1800D00CD
0x1800d00b8  lea     failure, aCallerP; "(caller: %p) "
0x1800d00bf  mov     cchDest, rsi; destEnd
0x1800d00c2  mov     pszDest, rax; dest
0x1800d00c5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800d00ca  mov     r14, rax
0x1800d00cd  call    cs:__imp_GetCurrentThreadId
0x1800d00d4  nop     dword ptr [rax+rax+00h]
0x1800d00d9  lea     pszDest, [rsp+278h+szErrorText]
0x1800d00de  mov     r9, rdi
0x1800d00e1  mov     [rsp+278h+var_240], pszDest
0x1800d00e6  lea     failure, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800d00ed  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800d00f1  mov     cchDest, rsi; destEnd
0x1800d00f4  mov     [rsp+278h+nSize], eax
0x1800d00f8  mov     pszDest, r14; dest
0x1800d00fb  mov     eax, [rbx+44h]
0x1800d00fe  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800d0102  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800d0107  cmp     [rbx+18h], r15
0x1800d010b  jnz     short loc_1800D011D
0x1800d010d  cmp     [rbx+48h], r15
0x1800d0111  jnz     short loc_1800D011D
0x1800d0113  cmp     [rbx+30h], r15
0x1800d0117  jz      loc_1800D01AD
0x1800d011d  lea     failure, asc_1801C8990; "    "
0x1800d0124  mov     cchDest, rsi; destEnd
0x1800d0127  mov     pszDest, rax; dest
0x1800d012a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800d012f  mov     r9, [rbx+18h]
0x1800d0133  test    r9, r9
0x1800d0136  jz      short loc_1800D014A
0x1800d0138  lea     failure, aMsgWs; "Msg:[%ws] "
0x1800d013f  mov     cchDest, rsi; destEnd
0x1800d0142  mov     pszDest, rax; dest
0x1800d0145  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800d014a  mov     r9, [rbx+48h]
0x1800d014e  test    r9, r9
0x1800d0151  jz      short loc_1800D0165
0x1800d0153  lea     failure, aCallcontextHs; "CallContext:[%hs] "
0x1800d015a  mov     cchDest, rsi; destEnd
0x1800d015d  mov     pszDest, rax; dest
0x1800d0160  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800d0165  mov     pszDest, [rbx+28h]
0x1800d0169  mov     cchDest, rsi; destEnd
0x1800d016c  mov     r9, [rbx+30h]
0x1800d0170  test    pszDest, pszDest
0x1800d0173  jz      short loc_1800D018B
0x1800d0175  mov     [rsp+278h+lpBuffer], pszDest
0x1800d017a  lea     failure, aHsHs; "[%hs(%hs)]\n"
0x1800d0181  mov     pszDest, rax; dest
0x1800d0184  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800d0189  jmp     short loc_1800D01AD
0x1800d018b  mov     pszDest, rax; dest
0x1800d018e  test    r9, r9
0x1800d0191  jz      short loc_1800D01A1
0x1800d0193  lea     failure, aHs; "[%hs]\n"
0x1800d019a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800d019f  jmp     short loc_1800D01AD
0x1800d01a1  lea     failure, asc_1801C8A08; "\n"
0x1800d01a8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800d01ad  xor     eax, eax
0x1800d01af  mov     pszDest, [rsp+278h+var_38]
0x1800d01b7  xor     pszDest, rsp; StackCookie
0x1800d01ba  call    __security_check_cookie
0x1800d01bf  mov     rbx, [rsp+278h+arg_18]
0x1800d01c7  add     rsp, 250h
0x1800d01ce  pop     r15
0x1800d01d0  pop     r14
0x1800d01d2  pop     rdi
0x1800d01d3  pop     rsi
0x1800d01d4  pop     rbp
0x1800d01d5  retn
```
