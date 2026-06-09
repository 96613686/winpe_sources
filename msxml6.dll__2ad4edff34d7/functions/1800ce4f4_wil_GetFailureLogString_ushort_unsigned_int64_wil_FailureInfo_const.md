# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800ce4f4`
- end: `0x1800ce7aa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `HRESULT __fastcall(wchar_t *pszDest, unsigned __int64 cchDest, const wil::FailureInfo *failure)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800cd268`
- `0x1800cee74`

## callees

- `0x1800cac64`
- `0x1800cada0`
- `0x1800cba94`
- `0x1800ce4f4`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ce6a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ce6a7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800ce626`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800ce626`

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
          v7 = (const char *)&dword_1801C48A4;
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
0x1800ce4f4  mov     [rsp+arg_18], rbx
0x1800ce4f9  push    rbp
0x1800ce4fa  push    rsi
0x1800ce4fb  push    rdi
0x1800ce4fc  push    r14
0x1800ce4fe  push    r15
0x1800ce500  sub     rsp, 250h
0x1800ce507  mov     rax, cs:__security_cookie
0x1800ce50e  xor     rax, rsp
0x1800ce511  mov     [rsp+278h+var_38], rax
0x1800ce519  xor     r15d, r15d
0x1800ce51c  mov     rbx, failure
0x1800ce51f  mov     rsi, cchDest
0x1800ce522  mov     r14, pszDest
0x1800ce525  test    cchDest, cchDest
0x1800ce528  jz      loc_1800CE781
0x1800ce52e  test    pszDest, pszDest
0x1800ce531  jz      loc_1800CE781
0x1800ce537  mov     rax, cs:g_pfnResultLoggingCallback
0x1800ce53e  mov     [pszDest], r15w
0x1800ce542  test    rax, rax
0x1800ce545  jz      short loc_1800CE568
0x1800ce547  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800ce54e  jz      short loc_1800CE568
0x1800ce550  mov     failure, cchDest
0x1800ce553  mov     cchDest, pszDest
0x1800ce556  mov     pszDest, rbx
0x1800ce559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce55e  cmp     [r14], r15w
0x1800ce562  jnz     loc_1800CE781
0x1800ce568  mov     ecx, [rbx]
0x1800ce56a  mov     bpl, 8
0x1800ce56d  test    ecx, ecx
0x1800ce56f  jz      short loc_1800CE5BA
0x1800ce571  sub     ecx, 1
0x1800ce574  jz      short loc_1800CE5A2
0x1800ce576  sub     ecx, 1
0x1800ce579  jz      short loc_1800CE592
0x1800ce57b  cmp     ecx, 1
0x1800ce57e  jz      short loc_1800CE589
0x1800ce580  lea     rdi, dword_1801C48A4
0x1800ce587  jmp     short loc_1800CE5C1
0x1800ce589  lea     rdi, aFailfast; "FailFast"
0x1800ce590  jmp     short loc_1800CE5C1
0x1800ce592  lea     rax, aLoghr; "LogHr"
0x1800ce599  lea     rdi, aLognt; "LogNt"
0x1800ce5a0  jmp     short loc_1800CE5B0
0x1800ce5a2  lea     rax, aReturnhr; "ReturnHr"
0x1800ce5a9  lea     rdi, aReturnnt; "ReturnNt"
0x1800ce5b0  test    [rbx+4], bpl
0x1800ce5b4  cmovz   rdi, rax
0x1800ce5b8  jmp     short loc_1800CE5C1
0x1800ce5ba  lea     rdi, aException; "Exception"
0x1800ce5c1  xor     edx, edx; Val
0x1800ce5c3  lea     pszDest, [rsp+278h+szErrorText]; void *
0x1800ce5c8  mov     r8d, 200h; Size
0x1800ce5ce  call    memset_0
0x1800ce5d3  test    [rbx+4], bpl
0x1800ce5d7  jz      short loc_1800CE5FC
0x1800ce5d9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800ce5e0  mov     ebp, [rbx+0Ch]
0x1800ce5e3  test    rax, rax
0x1800ce5e6  jz      short loc_1800CE62C
0x1800ce5e8  mov     r8d, 100h
0x1800ce5ee  lea     cchDest, [rsp+278h+szErrorText]
0x1800ce5f3  mov     ecx, ebp
0x1800ce5f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce5fa  jmp     short loc_1800CE62C
0x1800ce5fc  mov     ebp, [rbx+8]
0x1800ce5ff  lea     rax, [rsp+278h+szErrorText]
0x1800ce604  mov     [rsp+278h+Arguments], r15; Arguments
0x1800ce609  mov     r8d, ebp; dwMessageId
0x1800ce60c  mov     [rsp+278h+nSize], 100h; nSize
0x1800ce614  mov     r9d, 400h; dwLanguageId
0x1800ce61a  xor     edx, edx; lpSource
0x1800ce61c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800ce621  mov     ecx, 1200h; dwFlags
0x1800ce626  call    cs:__imp_FormatMessageW
0x1800ce62c  mov     r9, [rbx+38h]
0x1800ce630  lea     rsi, [r14+rsi*2]
0x1800ce634  mov     rax, [rbx+88h]
0x1800ce63b  mov     cchDest, rsi; destEnd
0x1800ce63e  mov     pszDest, [rbx+80h]
0x1800ce645  test    r9, r9
0x1800ce648  jz      short loc_1800CE66C
0x1800ce64a  mov     [rsp+278h+Arguments], rax
0x1800ce64f  lea     failure, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800ce656  mov     eax, [rbx+40h]
0x1800ce659  mov     qword ptr [rsp+278h+nSize], pszDest
0x1800ce65e  mov     pszDest, r14; dest
0x1800ce661  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800ce665  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ce66a  jmp     short loc_1800CE683
0x1800ce66c  mov     r9, pszDest
0x1800ce66f  mov     [rsp+278h+lpBuffer], rax
0x1800ce674  mov     pszDest, r14; dest
0x1800ce677  lea     failure, aHsP; "%hs!%p: "
0x1800ce67e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ce683  mov     r9, [rbx+90h]
0x1800ce68a  mov     r14, rax
0x1800ce68d  test    r9, r9
0x1800ce690  jz      short loc_1800CE6A7
0x1800ce692  lea     failure, aCallerP; "(caller: %p) "
0x1800ce699  mov     cchDest, rsi; destEnd
0x1800ce69c  mov     pszDest, rax; dest
0x1800ce69f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ce6a4  mov     r14, rax
0x1800ce6a7  call    cs:__imp_GetCurrentThreadId
0x1800ce6ad  lea     pszDest, [rsp+278h+szErrorText]
0x1800ce6b2  mov     r9, rdi
0x1800ce6b5  mov     [rsp+278h+var_240], pszDest
0x1800ce6ba  lea     failure, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800ce6c1  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800ce6c5  mov     cchDest, rsi; destEnd
0x1800ce6c8  mov     [rsp+278h+nSize], eax
0x1800ce6cc  mov     pszDest, r14; dest
0x1800ce6cf  mov     eax, [rbx+44h]
0x1800ce6d2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800ce6d6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ce6db  cmp     [rbx+18h], r15
0x1800ce6df  jnz     short loc_1800CE6F1
0x1800ce6e1  cmp     [rbx+48h], r15
0x1800ce6e5  jnz     short loc_1800CE6F1
0x1800ce6e7  cmp     [rbx+30h], r15
0x1800ce6eb  jz      loc_1800CE781
0x1800ce6f1  lea     failure, asc_1801C4990; "    "
0x1800ce6f8  mov     cchDest, rsi; destEnd
0x1800ce6fb  mov     pszDest, rax; dest
0x1800ce6fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ce703  mov     r9, [rbx+18h]
0x1800ce707  test    r9, r9
0x1800ce70a  jz      short loc_1800CE71E
0x1800ce70c  lea     failure, aMsgWs; "Msg:[%ws] "
0x1800ce713  mov     cchDest, rsi; destEnd
0x1800ce716  mov     pszDest, rax; dest
0x1800ce719  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ce71e  mov     r9, [rbx+48h]
0x1800ce722  test    r9, r9
0x1800ce725  jz      short loc_1800CE739
0x1800ce727  lea     failure, aCallcontextHs; "CallContext:[%hs] "
0x1800ce72e  mov     cchDest, rsi; destEnd
0x1800ce731  mov     pszDest, rax; dest
0x1800ce734  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ce739  mov     pszDest, [rbx+28h]
0x1800ce73d  mov     cchDest, rsi; destEnd
0x1800ce740  mov     r9, [rbx+30h]
0x1800ce744  test    pszDest, pszDest
0x1800ce747  jz      short loc_1800CE75F
0x1800ce749  mov     [rsp+278h+lpBuffer], pszDest
0x1800ce74e  lea     failure, aHsHs; "[%hs(%hs)]\n"
0x1800ce755  mov     pszDest, rax; dest
0x1800ce758  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ce75d  jmp     short loc_1800CE781
0x1800ce75f  mov     pszDest, rax; dest
0x1800ce762  test    r9, r9
0x1800ce765  jz      short loc_1800CE775
0x1800ce767  lea     failure, aHs; "[%hs]\n"
0x1800ce76e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ce773  jmp     short loc_1800CE781
0x1800ce775  lea     failure, asc_1801C4A08; "\n"
0x1800ce77c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800ce781  xor     eax, eax
0x1800ce783  mov     pszDest, [rsp+278h+var_38]
0x1800ce78b  xor     pszDest, rsp; StackCookie
0x1800ce78e  call    __security_check_cookie
0x1800ce793  mov     rbx, [rsp+278h+arg_18]
0x1800ce79b  add     rsp, 250h
0x1800ce7a2  pop     r15
0x1800ce7a4  pop     r14
0x1800ce7a6  pop     rdi
0x1800ce7a7  pop     rsi
0x1800ce7a8  pop     rbp
0x1800ce7a9  retn
```
