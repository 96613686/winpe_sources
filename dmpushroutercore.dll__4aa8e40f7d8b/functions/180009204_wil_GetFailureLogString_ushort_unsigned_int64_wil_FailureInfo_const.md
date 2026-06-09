# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180009204`
- end: `0x1800094ba`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180006be8`
- `0x180006e68`
- `0x180009cfc`
- `0x18000d670`
- `0x180025724`
- `0x180038b57`
- `0x180038c8b`

## callees

- `0x1800039f0`
- `0x1800043a8`
- `0x180009204`
- `0x180009ffc`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009336`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009336`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800093b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800093b7`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
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
  unsigned __int16 *v14; // rax
  wil::details *v15; // r14
  const unsigned __int16 *v16; // r9
  wil::details *v17; // rax
  const unsigned __int16 *v18; // r9
  unsigned __int16 *v19; // rax
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
  if ( !this )
    return 0;
  *(_WORD *)this = 0;
  if ( g_pfnResultLoggingCallback )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      g_pfnResultLoggingCallback(a3, this, a2, a4);
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
          v7 = (const char *)&qword_18003EDF8;
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
  v10 = (unsigned __int16 *)((char *)this + 2 * (_QWORD)a2);
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const unsigned __int16 **)(a3 + 128);
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
  v16 = *(const unsigned __int16 **)(a3 + 144);
  if ( v16 )
    v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
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
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
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
0x180009204  mov     [rsp+arg_18], rbx
0x180009209  push    rbp
0x18000920a  push    rsi
0x18000920b  push    rdi
0x18000920c  push    r14
0x18000920e  push    r15
0x180009210  sub     rsp, 250h
0x180009217  mov     rax, cs:__security_cookie
0x18000921e  xor     rax, rsp
0x180009221  mov     [rsp+278h+var_38], rax
0x180009229  mov     rbx, r8
0x18000922c  mov     rsi, rdx
0x18000922f  mov     r14, rcx
0x180009232  xor     r15d, r15d
0x180009235  test    rdx, rdx
0x180009238  jz      loc_180009491
0x18000923e  test    rcx, rcx
0x180009241  jz      loc_180009491
0x180009247  mov     [rcx], r15w
0x18000924b  mov     rax, cs:g_pfnResultLoggingCallback
0x180009252  test    rax, rax
0x180009255  jz      short loc_180009278
0x180009257  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000925e  jz      short loc_180009278
0x180009260  mov     r8, rdx
0x180009263  mov     rdx, rcx
0x180009266  mov     rcx, rbx
0x180009269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000926e  cmp     [r14], r15w
0x180009272  jnz     loc_180009491
0x180009278  mov     ecx, [rbx]
0x18000927a  mov     bpl, 8
0x18000927d  test    ecx, ecx
0x18000927f  jz      short loc_1800092CA
0x180009281  sub     ecx, 1
0x180009284  jz      short loc_1800092B2
0x180009286  sub     ecx, 1
0x180009289  jz      short loc_1800092A2
0x18000928b  cmp     ecx, 1
0x18000928e  jz      short loc_180009299
0x180009290  lea     rdi, qword_18003EDF8
0x180009297  jmp     short loc_1800092D1
0x180009299  lea     rdi, aFailfast; "FailFast"
0x1800092a0  jmp     short loc_1800092D1
0x1800092a2  lea     rax, aLoghr; "LogHr"
0x1800092a9  lea     rdi, aLognt; "LogNt"
0x1800092b0  jmp     short loc_1800092C0
0x1800092b2  lea     rax, aReturnhr; "ReturnHr"
0x1800092b9  lea     rdi, aReturnnt; "ReturnNt"
0x1800092c0  test    [rbx+4], bpl
0x1800092c4  cmovz   rdi, rax
0x1800092c8  jmp     short loc_1800092D1
0x1800092ca  lea     rdi, aException; "Exception"
0x1800092d1  xor     edx, edx; Val
0x1800092d3  mov     r8d, 200h; Size
0x1800092d9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800092de  call    memset_0
0x1800092e3  test    [rbx+4], bpl
0x1800092e7  jz      short loc_18000930C
0x1800092e9  mov     ebp, [rbx+0Ch]
0x1800092ec  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800092f3  test    rax, rax
0x1800092f6  jz      short loc_18000933C
0x1800092f8  mov     r8d, 100h
0x1800092fe  lea     rdx, [rsp+278h+Buffer]
0x180009303  mov     ecx, ebp
0x180009305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000930a  jmp     short loc_18000933C
0x18000930c  mov     ebp, [rbx+8]
0x18000930f  mov     [rsp+278h+Arguments], r15; Arguments
0x180009314  mov     [rsp+278h+nSize], 100h; nSize
0x18000931c  lea     rax, [rsp+278h+Buffer]
0x180009321  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180009326  mov     r9d, 400h; dwLanguageId
0x18000932c  mov     r8d, ebp; dwMessageId
0x18000932f  xor     edx, edx; lpSource
0x180009331  mov     ecx, 1200h; dwFlags
0x180009336  call    cs:__imp_FormatMessageW
0x18000933c  lea     rsi, [r14+rsi*2]
0x180009340  mov     r9, [rbx+38h]; unsigned __int16 *
0x180009344  mov     rax, [rbx+88h]
0x18000934b  mov     rcx, [rbx+80h]
0x180009352  mov     rdx, rsi; unsigned __int16 *
0x180009355  test    r9, r9
0x180009358  jz      short loc_18000937C
0x18000935a  mov     [rsp+278h+Arguments], rax
0x18000935f  mov     qword ptr [rsp+278h+nSize], rcx
0x180009364  mov     eax, [rbx+40h]
0x180009367  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000936b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180009372  mov     rcx, r14; this
0x180009375  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000937a  jmp     short loc_180009393
0x18000937c  mov     [rsp+278h+lpBuffer], rax
0x180009381  mov     r9, rcx; unsigned __int16 *
0x180009384  lea     r8, aHsP; "%hs!%p: "
0x18000938b  mov     rcx, r14; this
0x18000938e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009393  mov     r14, rax
0x180009396  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000939d  test    r9, r9
0x1800093a0  jz      short loc_1800093B7
0x1800093a2  lea     r8, aCallerP; "(caller: %p) "
0x1800093a9  mov     rdx, rsi; unsigned __int16 *
0x1800093ac  mov     rcx, rax; this
0x1800093af  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800093b4  mov     r14, rax
0x1800093b7  call    cs:__imp_GetCurrentThreadId
0x1800093bd  lea     rcx, [rsp+278h+Buffer]
0x1800093c2  mov     [rsp+278h+var_240], rcx
0x1800093c7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800093cb  mov     [rsp+278h+nSize], eax
0x1800093cf  mov     eax, [rbx+44h]
0x1800093d2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800093d6  mov     r9, rdi; unsigned __int16 *
0x1800093d9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800093e0  mov     rdx, rsi; unsigned __int16 *
0x1800093e3  mov     rcx, r14; this
0x1800093e6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800093eb  cmp     [rbx+18h], r15
0x1800093ef  jnz     short loc_180009401
0x1800093f1  cmp     [rbx+48h], r15
0x1800093f5  jnz     short loc_180009401
0x1800093f7  cmp     [rbx+30h], r15
0x1800093fb  jz      loc_180009491
0x180009401  lea     r8, asc_18003E470; "    "
0x180009408  mov     rdx, rsi; unsigned __int16 *
0x18000940b  mov     rcx, rax; this
0x18000940e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009413  mov     r9, [rbx+18h]; unsigned __int16 *
0x180009417  test    r9, r9
0x18000941a  jz      short loc_18000942E
0x18000941c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180009423  mov     rdx, rsi; unsigned __int16 *
0x180009426  mov     rcx, rax; this
0x180009429  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000942e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180009432  test    r9, r9
0x180009435  jz      short loc_180009449
0x180009437  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000943e  mov     rdx, rsi; unsigned __int16 *
0x180009441  mov     rcx, rax; this
0x180009444  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009449  mov     rcx, [rbx+28h]
0x18000944d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180009451  mov     rdx, rsi; unsigned __int16 *
0x180009454  test    rcx, rcx
0x180009457  jz      short loc_18000946F
0x180009459  mov     [rsp+278h+lpBuffer], rcx
0x18000945e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180009465  mov     rcx, rax; this
0x180009468  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000946d  jmp     short loc_180009491
0x18000946f  mov     rcx, rax; this
0x180009472  test    r9, r9
0x180009475  jz      short loc_180009485
0x180009477  lea     r8, aHs; "[%hs]\n"
0x18000947e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009483  jmp     short loc_180009491
0x180009485  lea     r8, asc_18003E4E8; "\n"
0x18000948c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009491  xor     eax, eax
0x180009493  mov     rcx, [rsp+278h+var_38]
0x18000949b  xor     rcx, rsp; StackCookie
0x18000949e  call    __security_check_cookie
0x1800094a3  mov     rbx, [rsp+278h+arg_18]
0x1800094ab  add     rsp, 250h
0x1800094b2  pop     r15
0x1800094b4  pop     r14
0x1800094b6  pop     rdi
0x1800094b7  pop     rsi
0x1800094b8  pop     rbp
0x1800094b9  retn
```
