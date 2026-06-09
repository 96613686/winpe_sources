# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005e84`
- end: `0x18000613a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `HRESULT __fastcall(wchar_t *pszDest, unsigned __int64 cchDest, const wil::FailureInfo *failure)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180004f84`
- `0x180006844`
- `0x180006d34`
- `0x180007f20`

## callees

- `0x180002790`
- `0x1800032dc`
- `0x180005e84`
- `0x180006b44`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006037`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006037`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005fb6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005fb6`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wchar_t *pszDest, unsigned __int64 cchDest, wil::FailureInfo *failure)
{
  const char *v6; // rdi
  const char *v7; // rax
  int status; // ebp
  const wchar_t *v9; // rsi
  wchar_t *v10; // rax
  wchar_t *v11; // r14
  wchar_t *v12; // rax
  wchar_t *v13; // rax
  const char *pszFunction; // r9
  LPWSTR lpBuffer; // [rsp+20h] [rbp-258h]
  DWORD nSize[2]; // [rsp+28h] [rbp-250h]
  va_list *Arguments; // [rsp+30h] [rbp-248h]
  wchar_t szErrorText[256]; // [rsp+40h] [rbp-238h] BYREF

  if ( !cchDest )
    return 0;
  if ( !pszDest )
    return 0;
  *pszDest = 0;
  if ( g_pfnResultLoggingCallback )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      g_pfnResultLoggingCallback(failure, pszDest, cchDest);
      if ( *pszDest )
        return 0;
    }
  }
  if ( failure->type )
  {
    if ( failure->type == Return )
    {
      v7 = "ReturnHr";
      v6 = "ReturnNt";
    }
    else
    {
      if ( failure->type != Log )
      {
        if ( failure->type == FailFast )
          v6 = "FailFast";
        else
          v6 = (const char *)&dword_1800742F4;
        goto LABEL_18;
      }
      v7 = "LogHr";
      v6 = "LogNt";
    }
    if ( (failure->flags & 8) == 0 )
      v6 = v7;
    goto LABEL_18;
  }
  v6 = "Exception";
LABEL_18:
  memset_0(szErrorText, 0, sizeof(szErrorText));
  if ( (failure->flags & 8) != 0 )
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
  v9 = &pszDest[cchDest];
  if ( failure->pszFile )
  {
    HIDWORD(Arguments) = HIDWORD(failure->returnAddress);
    nSize[1] = HIDWORD(failure->pszModule);
    v10 = wil::details::LogStringPrintf(pszDest, v9, L"%hs(%u)\\%hs!%p: ");
  }
  else
  {
    v10 = wil::details::LogStringPrintf(pszDest, v9, L"%hs!%p: ", failure->pszModule, failure->returnAddress);
  }
  v11 = v10;
  if ( failure->callerReturnAddress )
    v11 = wil::details::LogStringPrintf(v10, v9, L"(caller: %p) ");
  LODWORD(Arguments) = status;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffer) = failure->cFailureCount;
  v12 = wil::details::LogStringPrintf(
          v11,
          v9,
          L"%hs(%d) tid(%x) %08X %ws",
          v6,
          lpBuffer,
          *(_QWORD *)nSize,
          Arguments,
          szErrorText);
  if ( failure->pszMessage || failure->pszCallContext || failure->pszFunction )
  {
    v13 = wil::details::LogStringPrintf(v12, v9, L"    ");
    if ( failure->pszMessage )
      v13 = wil::details::LogStringPrintf(v13, v9, L"Msg:[%ws] ");
    if ( failure->pszCallContext )
      v13 = wil::details::LogStringPrintf(v13, v9, L"CallContext:[%hs] ");
    pszFunction = failure->pszFunction;
    if ( failure->pszCode )
    {
      wil::details::LogStringPrintf(v13, v9, L"[%hs(%hs)]\n", pszFunction, failure->pszCode);
    }
    else if ( pszFunction )
    {
      wil::details::LogStringPrintf(v13, v9, L"[%hs]\n");
    }
    else
    {
      wil::details::LogStringPrintf(v13, v9, L"\n");
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180005e84  mov     [rsp+arg_18], rbx
0x180005e89  push    rbp
0x180005e8a  push    rsi
0x180005e8b  push    rdi
0x180005e8c  push    r14
0x180005e8e  push    r15
0x180005e90  sub     rsp, 250h
0x180005e97  mov     rax, cs:__security_cookie
0x180005e9e  xor     rax, rsp
0x180005ea1  mov     [rsp+278h+var_38], rax
0x180005ea9  mov     rbx, failure
0x180005eac  mov     rsi, cchDest
0x180005eaf  mov     r14, pszDest
0x180005eb2  xor     r15d, r15d
0x180005eb5  test    cchDest, cchDest
0x180005eb8  jz      loc_180006111
0x180005ebe  test    pszDest, pszDest
0x180005ec1  jz      loc_180006111
0x180005ec7  mov     [pszDest], r15w
0x180005ecb  mov     rax, cs:g_pfnResultLoggingCallback
0x180005ed2  test    rax, rax
0x180005ed5  jz      short loc_180005EF8
0x180005ed7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005ede  jz      short loc_180005EF8
0x180005ee0  mov     failure, cchDest
0x180005ee3  mov     cchDest, pszDest
0x180005ee6  mov     pszDest, rbx
0x180005ee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eee  cmp     [r14], r15w
0x180005ef2  jnz     loc_180006111
0x180005ef8  mov     ecx, [rbx]
0x180005efa  mov     bpl, 8
0x180005efd  test    ecx, ecx
0x180005eff  jz      short loc_180005F4A
0x180005f01  sub     ecx, 1
0x180005f04  jz      short loc_180005F32
0x180005f06  sub     ecx, 1
0x180005f09  jz      short loc_180005F22
0x180005f0b  cmp     ecx, 1
0x180005f0e  jz      short loc_180005F19
0x180005f10  lea     rdi, dword_1800742F4
0x180005f17  jmp     short loc_180005F51
0x180005f19  lea     rdi, aFailfast; "FailFast"
0x180005f20  jmp     short loc_180005F51
0x180005f22  lea     rax, aLoghr; "LogHr"
0x180005f29  lea     rdi, aLognt; "LogNt"
0x180005f30  jmp     short loc_180005F40
0x180005f32  lea     rax, aReturnhr; "ReturnHr"
0x180005f39  lea     rdi, aReturnnt; "ReturnNt"
0x180005f40  test    [rbx+4], bpl
0x180005f44  cmovz   rdi, rax
0x180005f48  jmp     short loc_180005F51
0x180005f4a  lea     rdi, aException; "Exception"
0x180005f51  xor     edx, edx; Val
0x180005f53  mov     r8d, 200h; Size
0x180005f59  lea     pszDest, [rsp+278h+szErrorText]; void *
0x180005f5e  call    memset_0
0x180005f63  test    [rbx+4], bpl
0x180005f67  jz      short loc_180005F8C
0x180005f69  mov     ebp, [rbx+0Ch]
0x180005f6c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005f73  test    rax, rax
0x180005f76  jz      short loc_180005FBC
0x180005f78  mov     r8d, 100h
0x180005f7e  lea     cchDest, [rsp+278h+szErrorText]
0x180005f83  mov     ecx, ebp
0x180005f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f8a  jmp     short loc_180005FBC
0x180005f8c  mov     ebp, [rbx+8]
0x180005f8f  mov     [rsp+278h+Arguments], r15; Arguments
0x180005f94  mov     [rsp+278h+nSize], 100h; nSize
0x180005f9c  lea     rax, [rsp+278h+szErrorText]
0x180005fa1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005fa6  mov     r9d, 400h; dwLanguageId
0x180005fac  mov     r8d, ebp; dwMessageId
0x180005faf  xor     edx, edx; lpSource
0x180005fb1  mov     ecx, 1200h; dwFlags
0x180005fb6  call    cs:__imp_FormatMessageW
0x180005fbc  lea     rsi, [r14+rsi*2]
0x180005fc0  mov     r9, [rbx+38h]
0x180005fc4  mov     rax, [rbx+88h]
0x180005fcb  mov     pszDest, [rbx+80h]
0x180005fd2  mov     cchDest, rsi; destEnd
0x180005fd5  test    r9, r9
0x180005fd8  jz      short loc_180005FFC
0x180005fda  mov     [rsp+278h+Arguments], rax
0x180005fdf  mov     qword ptr [rsp+278h+nSize], pszDest
0x180005fe4  mov     eax, [rbx+40h]
0x180005fe7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005feb  lea     failure, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005ff2  mov     pszDest, r14; dest
0x180005ff5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005ffa  jmp     short loc_180006013
0x180005ffc  mov     [rsp+278h+lpBuffer], rax
0x180006001  mov     r9, pszDest
0x180006004  lea     failure, aHsP; "%hs!%p: "
0x18000600b  mov     pszDest, r14; dest
0x18000600e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006013  mov     r14, rax
0x180006016  mov     r9, [rbx+90h]
0x18000601d  test    r9, r9
0x180006020  jz      short loc_180006037
0x180006022  lea     failure, aCallerP; "(caller: %p) "
0x180006029  mov     cchDest, rsi; destEnd
0x18000602c  mov     pszDest, rax; dest
0x18000602f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006034  mov     r14, rax
0x180006037  call    cs:__imp_GetCurrentThreadId
0x18000603d  lea     pszDest, [rsp+278h+szErrorText]
0x180006042  mov     [rsp+278h+var_240], pszDest
0x180006047  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000604b  mov     [rsp+278h+nSize], eax
0x18000604f  mov     eax, [rbx+44h]
0x180006052  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006056  mov     r9, rdi
0x180006059  lea     failure, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006060  mov     cchDest, rsi; destEnd
0x180006063  mov     pszDest, r14; dest
0x180006066  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000606b  cmp     [rbx+18h], r15
0x18000606f  jnz     short loc_180006081
0x180006071  cmp     [rbx+48h], r15
0x180006075  jnz     short loc_180006081
0x180006077  cmp     [rbx+30h], r15
0x18000607b  jz      loc_180006111
0x180006081  lea     failure, asc_1800743F8; "    "
0x180006088  mov     cchDest, rsi; destEnd
0x18000608b  mov     pszDest, rax; dest
0x18000608e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006093  mov     r9, [rbx+18h]
0x180006097  test    r9, r9
0x18000609a  jz      short loc_1800060AE
0x18000609c  lea     failure, aMsgWs; "Msg:[%ws] "
0x1800060a3  mov     cchDest, rsi; destEnd
0x1800060a6  mov     pszDest, rax; dest
0x1800060a9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800060ae  mov     r9, [rbx+48h]
0x1800060b2  test    r9, r9
0x1800060b5  jz      short loc_1800060C9
0x1800060b7  lea     failure, aCallcontextHs; "CallContext:[%hs] "
0x1800060be  mov     cchDest, rsi; destEnd
0x1800060c1  mov     pszDest, rax; dest
0x1800060c4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800060c9  mov     pszDest, [rbx+28h]
0x1800060cd  mov     r9, [rbx+30h]
0x1800060d1  mov     cchDest, rsi; destEnd
0x1800060d4  test    pszDest, pszDest
0x1800060d7  jz      short loc_1800060EF
0x1800060d9  mov     [rsp+278h+lpBuffer], pszDest
0x1800060de  lea     failure, aHsHs; "[%hs(%hs)]\n"
0x1800060e5  mov     pszDest, rax; dest
0x1800060e8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800060ed  jmp     short loc_180006111
0x1800060ef  mov     pszDest, rax; dest
0x1800060f2  test    r9, r9
0x1800060f5  jz      short loc_180006105
0x1800060f7  lea     failure, aHs; "[%hs]\n"
0x1800060fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006103  jmp     short loc_180006111
0x180006105  lea     failure, asc_180074470; "\n"
0x18000610c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006111  xor     eax, eax
0x180006113  mov     pszDest, [rsp+278h+var_38]
0x18000611b  xor     pszDest, rsp; StackCookie
0x18000611e  call    __security_check_cookie
0x180006123  mov     rbx, [rsp+278h+arg_18]
0x18000612b  add     rsp, 250h
0x180006132  pop     r15
0x180006134  pop     r14
0x180006136  pop     rdi
0x180006137  pop     rsi
0x180006138  pop     rbp
0x180006139  retn
```
