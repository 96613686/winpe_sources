# wil::GetFailureLogString(ushort *,uint,wil::FailureInfo const &)

- ea: `0x1006e31f`
- end: `0x1006e589`
- name: `?GetFailureLogString@wil@@YGJPAGIABUFailureInfo@1@@Z`
- size: `618`
- prototype: `HRESULT __userpurge@<eax>(wchar_t *pszDest@<ecx>, unsigned int cchDest@<edx>, const wil::FailureInfo *failure)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1006ed24`

## callees

- `0x10067b20`
- `0x1006b470`
- `0x1006c2c4`
- `0x1006e31f`
- `0x1006efb5`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1006e4b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1006e4b0`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1006e441`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1006e441`

## pseudocode

```c
HRESULT __fastcall wil::GetFailureLogString(wchar_t *pszDest, unsigned int cchDest, const wil::FailureInfo *failure)
{
  _array<NodeSet *> *v4; // ebx
  const char *v5; // ebx
  const char *v6; // eax
  const wchar_t *v7; // edi
  wchar_t *v8; // eax
  DWORD CurrentThreadId; // eax
  wchar_t *v10; // eax
  wchar_t *v11; // eax
  const char *pszModule; // [esp-Ch] [ebp-228h]
  void *returnAddress; // [esp-8h] [ebp-224h]
  DWORD status; // [esp+10h] [ebp-20Ch]
  wchar_t *desta; // [esp+14h] [ebp-208h]
  wchar_t szErrorText[256]; // [esp+18h] [ebp-204h] BYREF

  if ( !cchDest )
    return 0;
  if ( !pszDest )
    return 0;
  v4 = g_pfnResultLoggingCallback;
  *pszDest = 0;
  if ( v4 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      ((void (__thiscall *)(_array<NodeSet *> *, const wil::FailureInfo *, wchar_t *, unsigned int))v4)(
        v4,
        failure,
        pszDest,
        cchDest);
      if ( *pszDest )
        return 0;
    }
  }
  v5 = (const char *)&dword_1001E7D4;
  if ( *(_DWORD *)failure->type )
  {
    if ( *(_DWORD *)failure->type == 1 )
    {
      v5 = "ReturnHr";
      v6 = "ReturnNt";
    }
    else
    {
      if ( *(_DWORD *)failure->type != 2 )
      {
        if ( *(_DWORD *)failure->type == 3 )
          v5 = "FailFast";
        goto LABEL_17;
      }
      v5 = "LogHr";
      v6 = "LogNt";
    }
    if ( (failure->flags[0] & 8) != 0 )
      v5 = v6;
    goto LABEL_17;
  }
  v5 = "Exception";
LABEL_17:
  memset(szErrorText, 0, sizeof(szErrorText));
  if ( (failure->flags[0] & 8) != 0 )
  {
    status = failure->status;
    if ( wil::details::g_pfnFormatNtStatusMsg )
      ((void (__stdcall *)(int, wchar_t *, int))wil::details::g_pfnFormatNtStatusMsg)(failure->status, szErrorText, 256);
  }
  else
  {
    status = failure->hr;
    FormatMessageW(0x1200u, 0, status, 0x400u, szErrorText, 0x100u, 0);
  }
  returnAddress = failure->returnAddress;
  pszModule = failure->pszModule;
  v7 = &pszDest[cchDest];
  if ( failure->pszFile )
    v8 = wil::details::LogStringPrintf(
           pszDest,
           v7,
           L"%hs(%u)\\%hs!%p: ",
           failure->pszFile,
           failure->uLineNumber,
           pszModule,
           returnAddress);
  else
    v8 = wil::details::LogStringPrintf(pszDest, v7, L"%hs!%p: ", pszModule, returnAddress);
  desta = v8;
  if ( failure->callerReturnAddress )
    desta = wil::details::LogStringPrintf(v8, v7, L"(caller: %p) ", failure->callerReturnAddress);
  CurrentThreadId = GetCurrentThreadId();
  v10 = wil::details::LogStringPrintf(
          desta,
          v7,
          L"%hs(%d) tid(%x) %08X %ws",
          v5,
          failure->cFailureCount,
          CurrentThreadId,
          status,
          szErrorText);
  if ( failure->pszMessage || failure->pszCallContext || failure->pszFunction )
  {
    v11 = wil::details::LogStringPrintf(v10, v7, L"    ");
    if ( failure->pszMessage )
      v11 = wil::details::LogStringPrintf(v11, v7, L"Msg:[%ws] ", failure->pszMessage);
    if ( failure->pszCallContext )
      v11 = wil::details::LogStringPrintf(v11, v7, L"CallContext:[%hs] ", failure->pszCallContext);
    if ( failure->pszCode )
    {
      wil::details::LogStringPrintf(v11, v7, L"[%hs(%hs)]\n", failure->pszFunction, failure->pszCode);
    }
    else if ( failure->pszFunction )
    {
      wil::details::LogStringPrintf(v11, v7, L"[%hs]\n", failure->pszFunction);
    }
    else
    {
      wil::details::LogStringPrintf(v11, v7, L"\n");
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1006e31f  mov     edi, edi
0x1006e321  push    ebp
0x1006e322  mov     ebp, esp
0x1006e324  sub     esp, 214h
0x1006e32a  mov     eax, ___security_cookie
0x1006e32f  xor     eax, ebp
0x1006e331  mov     [ebp+var_4], eax
0x1006e334  push    esi
0x1006e335  mov     esi, [ebp+failure]
0x1006e338  mov     eax, cchDest
0x1006e33a  mov     [ebp+var_214], eax
0x1006e340  push    edi
0x1006e341  mov     edi, pszDest
0x1006e343  mov     [ebp+dest], edi
0x1006e349  test    eax, eax
0x1006e34b  jz      loc_1006E577
0x1006e351  test    edi, edi
0x1006e353  jz      loc_1006E577
0x1006e359  push    ebx
0x1006e35a  mov     ebx, _g_pfnResultLoggingCallback
0x1006e360  xor     pszDest, pszDest
0x1006e362  mov     [edi], cx
0x1006e365  test    ebx, ebx
0x1006e367  jz      short loc_1006E389
0x1006e369  cmp     ?g_resultMessageCallbackSet@details@wil@@3_NA, cl; bool wil::details::g_resultMessageCallbackSet
0x1006e36f  jz      short loc_1006E389
0x1006e371  push    eax
0x1006e372  push    edi
0x1006e373  push    esi
0x1006e374  mov     pszDest, ebx; this
0x1006e376  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1006e37c  call    ebx ; _g_pfnResultLoggingCallback
0x1006e37e  xor     pszDest, pszDest
0x1006e380  cmp     [edi], cx
0x1006e383  jnz     loc_1006E576
0x1006e389  mov     eax, [esi]
0x1006e38b  mov     ebx, offset dword_1001E7D4
0x1006e390  sub     eax, pszDest
0x1006e392  jz      short loc_1006E3C9
0x1006e394  sub     eax, 1
0x1006e397  jz      short loc_1006E3B6
0x1006e399  sub     eax, 1
0x1006e39c  jz      short loc_1006E3AA
0x1006e39e  sub     eax, 1
0x1006e3a1  jnz     short loc_1006E3CE
0x1006e3a3  mov     ebx, offset aFailfast; "FailFast"
0x1006e3a8  jmp     short loc_1006E3CE
0x1006e3aa  mov     ebx, offset aLoghr; "LogHr"
0x1006e3af  mov     eax, offset aLognt; "LogNt"
0x1006e3b4  jmp     short loc_1006E3C0
0x1006e3b6  mov     ebx, offset aReturnhr; "ReturnHr"
0x1006e3bb  mov     eax, offset aReturnnt; "ReturnNt"
0x1006e3c0  test    byte ptr [esi+4], 8
0x1006e3c4  cmovnz  ebx, eax
0x1006e3c7  jmp     short loc_1006E3CE
0x1006e3c9  mov     ebx, offset aException; "Exception"
0x1006e3ce  push    200h; Size
0x1006e3d3  push    pszDest; Val
0x1006e3d4  lea     eax, [ebp+szErrorText]
0x1006e3da  push    eax; void *
0x1006e3db  call    _memset
0x1006e3e0  add     esp, 0Ch
0x1006e3e3  test    byte ptr [esi+4], 8
0x1006e3e7  jz      short loc_1006E41D
0x1006e3e9  mov     pszDest, ?g_pfnFormatNtStatusMsg@details@wil@@3P6GXJPAGK@ZA; this
0x1006e3ef  mov     eax, [esi+0Ch]
0x1006e3f2  mov     [ebp+var_20C], eax
0x1006e3f8  mov     [ebp+var_210], pszDest
0x1006e3fe  test    pszDest, pszDest
0x1006e400  jz      short loc_1006E447
0x1006e402  push    100h
0x1006e407  lea     cchDest, [ebp+szErrorText]
0x1006e40d  push    cchDest
0x1006e40e  push    eax
0x1006e40f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1006e415  call    [ebp+var_210]
0x1006e41b  jmp     short loc_1006E447
0x1006e41d  mov     eax, [esi+8]
0x1006e420  lea     pszDest, [ebp+szErrorText]
0x1006e426  push    0; Arguments
0x1006e428  push    100h; nSize
0x1006e42d  push    pszDest; lpBuffer
0x1006e42e  push    400h; dwLanguageId
0x1006e433  push    eax; dwMessageId
0x1006e434  push    0; lpSource
0x1006e436  push    1200h; dwFlags
0x1006e43b  mov     [ebp+var_20C], eax
0x1006e441  call    ds:__imp__FormatMessageW@28; FormatMessageW(x,x,x,x,x,x,x)
0x1006e447  cmp     dword ptr [esi+24h], 0
0x1006e44b  mov     eax, [ebp+var_214]
0x1006e451  push    dword ptr [esi+50h]
0x1006e454  push    dword ptr [esi+4Ch]
0x1006e457  lea     edi, [edi+eax*2]
0x1006e45a  jz      short loc_1006E478
0x1006e45c  push    dword ptr [esi+28h]
0x1006e45f  push    dword ptr [esi+24h]
0x1006e462  push    offset aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1006e467  push    edi; destEnd
0x1006e468  push    [ebp+dest]; dest
0x1006e46e  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1006e473  add     esp, 1Ch
0x1006e476  jmp     short loc_1006E48C
0x1006e478  push    offset aHsP; "%hs!%p: "
0x1006e47d  push    edi; destEnd
0x1006e47e  push    [ebp+dest]; dest
0x1006e484  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1006e489  add     esp, 14h
0x1006e48c  cmp     dword ptr [esi+54h], 0
0x1006e490  mov     [ebp+dest], eax
0x1006e496  jz      short loc_1006E4B0
0x1006e498  push    dword ptr [esi+54h]
0x1006e49b  push    offset aCallerP; "(caller: %p) "
0x1006e4a0  push    edi; destEnd
0x1006e4a1  push    eax; dest
0x1006e4a2  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1006e4a7  add     esp, 10h
0x1006e4aa  mov     [ebp+dest], eax
0x1006e4b0  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1006e4b6  lea     pszDest, [ebp+szErrorText]
0x1006e4bc  push    pszDest
0x1006e4bd  push    [ebp+var_20C]
0x1006e4c3  push    eax
0x1006e4c4  push    dword ptr [esi+2Ch]
0x1006e4c7  push    ebx
0x1006e4c8  push    offset aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1006e4cd  push    edi; destEnd
0x1006e4ce  push    [ebp+dest]; dest
0x1006e4d4  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1006e4d9  xor     pszDest, pszDest
0x1006e4db  add     esp, 20h
0x1006e4de  cmp     [esi+14h], pszDest
0x1006e4e1  jnz     short loc_1006E4F1
0x1006e4e3  cmp     [esi+30h], pszDest
0x1006e4e6  jnz     short loc_1006E4F1
0x1006e4e8  cmp     [esi+20h], pszDest
0x1006e4eb  jz      loc_1006E576
0x1006e4f1  push    offset asc_1001E8A0; "    "
0x1006e4f6  push    edi; destEnd
0x1006e4f7  push    eax; dest
0x1006e4f8  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1006e4fd  add     esp, 0Ch
0x1006e500  cmp     dword ptr [esi+14h], 0
0x1006e504  jz      short loc_1006E518
0x1006e506  push    dword ptr [esi+14h]
0x1006e509  push    offset aMsgWs; "Msg:[%ws] "
0x1006e50e  push    edi; destEnd
0x1006e50f  push    eax; dest
0x1006e510  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1006e515  add     esp, 10h
0x1006e518  cmp     dword ptr [esi+30h], 0
0x1006e51c  jz      short loc_1006E530
0x1006e51e  push    dword ptr [esi+30h]
0x1006e521  push    offset aCallcontextHs; "CallContext:[%hs] "
0x1006e526  push    edi; destEnd
0x1006e527  push    eax; dest
0x1006e528  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1006e52d  add     esp, 10h
0x1006e530  cmp     dword ptr [esi+1Ch], 0
0x1006e534  jz      short loc_1006E54D
0x1006e536  push    dword ptr [esi+1Ch]
0x1006e539  push    dword ptr [esi+20h]
0x1006e53c  push    offset aHsHs; "[%hs(%hs)]\n"
0x1006e541  push    edi; destEnd
0x1006e542  push    eax; dest
0x1006e543  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1006e548  add     esp, 14h
0x1006e54b  jmp     short loc_1006E576
0x1006e54d  cmp     dword ptr [esi+20h], 0
0x1006e551  jz      short loc_1006E567
0x1006e553  push    dword ptr [esi+20h]
0x1006e556  push    offset aHs; "[%hs]\n"
0x1006e55b  push    edi; destEnd
0x1006e55c  push    eax; dest
0x1006e55d  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1006e562  add     esp, 10h
0x1006e565  jmp     short loc_1006E576
0x1006e567  push    offset asc_1001E914; "\n"
0x1006e56c  push    edi; destEnd
0x1006e56d  push    eax; dest
0x1006e56e  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1006e573  add     esp, 0Ch
0x1006e576  pop     ebx
0x1006e577  mov     pszDest, [ebp+var_4]
0x1006e57a  xor     eax, eax
0x1006e57c  pop     edi
0x1006e57d  xor     pszDest, ebp; cookie
0x1006e57f  pop     esi
0x1006e580  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1006e585  leave
0x1006e586  retn    4
```
