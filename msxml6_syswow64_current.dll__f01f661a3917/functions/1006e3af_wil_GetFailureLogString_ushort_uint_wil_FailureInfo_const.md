# wil::GetFailureLogString(ushort *,uint,wil::FailureInfo const &)

- ea: `0x1006e3af`
- end: `0x1006e619`
- name: `?GetFailureLogString@wil@@YGJPAGIABUFailureInfo@1@@Z`
- size: `618`
- prototype: `HRESULT __userpurge@<eax>(wchar_t *pszDest@<ecx>, unsigned int cchDest@<edx>, const wil::FailureInfo *failure)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1006edb4`

## callees

- `0x10067bc0`
- `0x1006b510`
- `0x1006c354`
- `0x1006e3af`
- `0x1006f045`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1006e540`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1006e540`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1006e4d1`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1006e4d1`

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
0x1006e3af  mov     edi, edi
0x1006e3b1  push    ebp
0x1006e3b2  mov     ebp, esp
0x1006e3b4  sub     esp, 214h
0x1006e3ba  mov     eax, ___security_cookie
0x1006e3bf  xor     eax, ebp
0x1006e3c1  mov     [ebp+var_4], eax
0x1006e3c4  push    esi
0x1006e3c5  mov     esi, [ebp+failure]
0x1006e3c8  mov     eax, cchDest
0x1006e3ca  mov     [ebp+var_214], eax
0x1006e3d0  push    edi
0x1006e3d1  mov     edi, pszDest
0x1006e3d3  mov     [ebp+dest], edi
0x1006e3d9  test    eax, eax
0x1006e3db  jz      loc_1006E607
0x1006e3e1  test    edi, edi
0x1006e3e3  jz      loc_1006E607
0x1006e3e9  push    ebx
0x1006e3ea  mov     ebx, _g_pfnResultLoggingCallback
0x1006e3f0  xor     pszDest, pszDest
0x1006e3f2  mov     [edi], cx
0x1006e3f5  test    ebx, ebx
0x1006e3f7  jz      short loc_1006E419
0x1006e3f9  cmp     ?g_resultMessageCallbackSet@details@wil@@3_NA, cl; bool wil::details::g_resultMessageCallbackSet
0x1006e3ff  jz      short loc_1006E419
0x1006e401  push    eax
0x1006e402  push    edi
0x1006e403  push    esi
0x1006e404  mov     pszDest, ebx; this
0x1006e406  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1006e40c  call    ebx ; _g_pfnResultLoggingCallback
0x1006e40e  xor     pszDest, pszDest
0x1006e410  cmp     [edi], cx
0x1006e413  jnz     loc_1006E606
0x1006e419  mov     eax, [esi]
0x1006e41b  mov     ebx, offset dword_1001E7D4
0x1006e420  sub     eax, pszDest
0x1006e422  jz      short loc_1006E459
0x1006e424  sub     eax, 1
0x1006e427  jz      short loc_1006E446
0x1006e429  sub     eax, 1
0x1006e42c  jz      short loc_1006E43A
0x1006e42e  sub     eax, 1
0x1006e431  jnz     short loc_1006E45E
0x1006e433  mov     ebx, offset aFailfast; "FailFast"
0x1006e438  jmp     short loc_1006E45E
0x1006e43a  mov     ebx, offset aLoghr; "LogHr"
0x1006e43f  mov     eax, offset aLognt; "LogNt"
0x1006e444  jmp     short loc_1006E450
0x1006e446  mov     ebx, offset aReturnhr; "ReturnHr"
0x1006e44b  mov     eax, offset aReturnnt; "ReturnNt"
0x1006e450  test    byte ptr [esi+4], 8
0x1006e454  cmovnz  ebx, eax
0x1006e457  jmp     short loc_1006E45E
0x1006e459  mov     ebx, offset aException; "Exception"
0x1006e45e  push    200h; Size
0x1006e463  push    pszDest; Val
0x1006e464  lea     eax, [ebp+szErrorText]
0x1006e46a  push    eax; void *
0x1006e46b  call    _memset
0x1006e470  add     esp, 0Ch
0x1006e473  test    byte ptr [esi+4], 8
0x1006e477  jz      short loc_1006E4AD
0x1006e479  mov     pszDest, ?g_pfnFormatNtStatusMsg@details@wil@@3P6GXJPAGK@ZA; this
0x1006e47f  mov     eax, [esi+0Ch]
0x1006e482  mov     [ebp+var_20C], eax
0x1006e488  mov     [ebp+var_210], pszDest
0x1006e48e  test    pszDest, pszDest
0x1006e490  jz      short loc_1006E4D7
0x1006e492  push    100h
0x1006e497  lea     cchDest, [ebp+szErrorText]
0x1006e49d  push    cchDest
0x1006e49e  push    eax
0x1006e49f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1006e4a5  call    [ebp+var_210]
0x1006e4ab  jmp     short loc_1006E4D7
0x1006e4ad  mov     eax, [esi+8]
0x1006e4b0  lea     pszDest, [ebp+szErrorText]
0x1006e4b6  push    0; Arguments
0x1006e4b8  push    100h; nSize
0x1006e4bd  push    pszDest; lpBuffer
0x1006e4be  push    400h; dwLanguageId
0x1006e4c3  push    eax; dwMessageId
0x1006e4c4  push    0; lpSource
0x1006e4c6  push    1200h; dwFlags
0x1006e4cb  mov     [ebp+var_20C], eax
0x1006e4d1  call    ds:__imp__FormatMessageW@28; FormatMessageW(x,x,x,x,x,x,x)
0x1006e4d7  cmp     dword ptr [esi+24h], 0
0x1006e4db  mov     eax, [ebp+var_214]
0x1006e4e1  push    dword ptr [esi+50h]
0x1006e4e4  push    dword ptr [esi+4Ch]
0x1006e4e7  lea     edi, [edi+eax*2]
0x1006e4ea  jz      short loc_1006E508
0x1006e4ec  push    dword ptr [esi+28h]
0x1006e4ef  push    dword ptr [esi+24h]
0x1006e4f2  push    offset aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1006e4f7  push    edi; destEnd
0x1006e4f8  push    [ebp+dest]; dest
0x1006e4fe  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1006e503  add     esp, 1Ch
0x1006e506  jmp     short loc_1006E51C
0x1006e508  push    offset aHsP; "%hs!%p: "
0x1006e50d  push    edi; destEnd
0x1006e50e  push    [ebp+dest]; dest
0x1006e514  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1006e519  add     esp, 14h
0x1006e51c  cmp     dword ptr [esi+54h], 0
0x1006e520  mov     [ebp+dest], eax
0x1006e526  jz      short loc_1006E540
0x1006e528  push    dword ptr [esi+54h]
0x1006e52b  push    offset aCallerP; "(caller: %p) "
0x1006e530  push    edi; destEnd
0x1006e531  push    eax; dest
0x1006e532  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1006e537  add     esp, 10h
0x1006e53a  mov     [ebp+dest], eax
0x1006e540  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1006e546  lea     pszDest, [ebp+szErrorText]
0x1006e54c  push    pszDest
0x1006e54d  push    [ebp+var_20C]
0x1006e553  push    eax
0x1006e554  push    dword ptr [esi+2Ch]
0x1006e557  push    ebx
0x1006e558  push    offset aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1006e55d  push    edi; destEnd
0x1006e55e  push    [ebp+dest]; dest
0x1006e564  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1006e569  xor     pszDest, pszDest
0x1006e56b  add     esp, 20h
0x1006e56e  cmp     [esi+14h], pszDest
0x1006e571  jnz     short loc_1006E581
0x1006e573  cmp     [esi+30h], pszDest
0x1006e576  jnz     short loc_1006E581
0x1006e578  cmp     [esi+20h], pszDest
0x1006e57b  jz      loc_1006E606
0x1006e581  push    offset asc_1001E8A0; "    "
0x1006e586  push    edi; destEnd
0x1006e587  push    eax; dest
0x1006e588  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1006e58d  add     esp, 0Ch
0x1006e590  cmp     dword ptr [esi+14h], 0
0x1006e594  jz      short loc_1006E5A8
0x1006e596  push    dword ptr [esi+14h]
0x1006e599  push    offset aMsgWs; "Msg:[%ws] "
0x1006e59e  push    edi; destEnd
0x1006e59f  push    eax; dest
0x1006e5a0  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1006e5a5  add     esp, 10h
0x1006e5a8  cmp     dword ptr [esi+30h], 0
0x1006e5ac  jz      short loc_1006E5C0
0x1006e5ae  push    dword ptr [esi+30h]
0x1006e5b1  push    offset aCallcontextHs; "CallContext:[%hs] "
0x1006e5b6  push    edi; destEnd
0x1006e5b7  push    eax; dest
0x1006e5b8  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1006e5bd  add     esp, 10h
0x1006e5c0  cmp     dword ptr [esi+1Ch], 0
0x1006e5c4  jz      short loc_1006E5DD
0x1006e5c6  push    dword ptr [esi+1Ch]
0x1006e5c9  push    dword ptr [esi+20h]
0x1006e5cc  push    offset aHsHs; "[%hs(%hs)]\n"
0x1006e5d1  push    edi; destEnd
0x1006e5d2  push    eax; dest
0x1006e5d3  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1006e5d8  add     esp, 14h
0x1006e5db  jmp     short loc_1006E606
0x1006e5dd  cmp     dword ptr [esi+20h], 0
0x1006e5e1  jz      short loc_1006E5F7
0x1006e5e3  push    dword ptr [esi+20h]
0x1006e5e6  push    offset aHs; "[%hs]\n"
0x1006e5eb  push    edi; destEnd
0x1006e5ec  push    eax; dest
0x1006e5ed  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1006e5f2  add     esp, 10h
0x1006e5f5  jmp     short loc_1006E606
0x1006e5f7  push    offset asc_1001E914; "\n"
0x1006e5fc  push    edi; destEnd
0x1006e5fd  push    eax; dest
0x1006e5fe  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1006e603  add     esp, 0Ch
0x1006e606  pop     ebx
0x1006e607  mov     pszDest, [ebp+var_4]
0x1006e60a  xor     eax, eax
0x1006e60c  pop     edi
0x1006e60d  xor     pszDest, ebp; cookie
0x1006e60f  pop     esi
0x1006e610  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1006e615  leave
0x1006e616  retn    4
```
