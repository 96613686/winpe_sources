# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18001b934`
- end: `0x18001bbea`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18001cbb0`
- `0x180021cd0`
- `0x180021f38`
- `0x180023d6c`

## callees

- `0x18001b934`
- `0x18001bef0`
- `0x1800396f2`
- `0x180039740`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001ba66`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001ba66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bae7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bae7`

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
          v7 = (const char *)&qword_180052328;
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
0x18001b934  mov     [rsp+arg_18], rbx
0x18001b939  push    rbp
0x18001b93a  push    rsi
0x18001b93b  push    rdi
0x18001b93c  push    r14
0x18001b93e  push    r15
0x18001b940  sub     rsp, 250h
0x18001b947  mov     rax, cs:__security_cookie
0x18001b94e  xor     rax, rsp
0x18001b951  mov     [rsp+278h+var_38], rax
0x18001b959  mov     rbx, r8
0x18001b95c  mov     rsi, rdx
0x18001b95f  mov     r14, rcx
0x18001b962  xor     r15d, r15d
0x18001b965  test    rdx, rdx
0x18001b968  jz      loc_18001BBC1
0x18001b96e  test    rcx, rcx
0x18001b971  jz      loc_18001BBC1
0x18001b977  mov     [rcx], r15w
0x18001b97b  mov     rax, cs:g_pfnResultLoggingCallback
0x18001b982  test    rax, rax
0x18001b985  jz      short loc_18001B9A8
0x18001b987  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001b98e  jz      short loc_18001B9A8
0x18001b990  mov     r8, rdx
0x18001b993  mov     rdx, rcx
0x18001b996  mov     rcx, rbx
0x18001b999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b99e  cmp     [r14], r15w
0x18001b9a2  jnz     loc_18001BBC1
0x18001b9a8  mov     ecx, [rbx]
0x18001b9aa  mov     bpl, 8
0x18001b9ad  test    ecx, ecx
0x18001b9af  jz      short loc_18001B9FA
0x18001b9b1  sub     ecx, 1
0x18001b9b4  jz      short loc_18001B9E2
0x18001b9b6  sub     ecx, 1
0x18001b9b9  jz      short loc_18001B9D2
0x18001b9bb  cmp     ecx, 1
0x18001b9be  jz      short loc_18001B9C9
0x18001b9c0  lea     rdi, qword_180052328
0x18001b9c7  jmp     short loc_18001BA01
0x18001b9c9  lea     rdi, aFailfast; "FailFast"
0x18001b9d0  jmp     short loc_18001BA01
0x18001b9d2  lea     rax, aLoghr; "LogHr"
0x18001b9d9  lea     rdi, aLognt; "LogNt"
0x18001b9e0  jmp     short loc_18001B9F0
0x18001b9e2  lea     rax, aReturnhr; "ReturnHr"
0x18001b9e9  lea     rdi, aReturnnt; "ReturnNt"
0x18001b9f0  test    [rbx+4], bpl
0x18001b9f4  cmovz   rdi, rax
0x18001b9f8  jmp     short loc_18001BA01
0x18001b9fa  lea     rdi, aException; "Exception"
0x18001ba01  xor     edx, edx; Val
0x18001ba03  mov     r8d, 200h; Size
0x18001ba09  lea     rcx, [rsp+278h+Buffer]; void *
0x18001ba0e  call    memset_0
0x18001ba13  test    [rbx+4], bpl
0x18001ba17  jz      short loc_18001BA3C
0x18001ba19  mov     ebp, [rbx+0Ch]
0x18001ba1c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18001ba23  test    rax, rax
0x18001ba26  jz      short loc_18001BA6C
0x18001ba28  mov     r8d, 100h
0x18001ba2e  lea     rdx, [rsp+278h+Buffer]
0x18001ba33  mov     ecx, ebp
0x18001ba35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba3a  jmp     short loc_18001BA6C
0x18001ba3c  mov     ebp, [rbx+8]
0x18001ba3f  mov     [rsp+278h+Arguments], r15; Arguments
0x18001ba44  mov     [rsp+278h+nSize], 100h; nSize
0x18001ba4c  lea     rax, [rsp+278h+Buffer]
0x18001ba51  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18001ba56  mov     r9d, 400h; dwLanguageId
0x18001ba5c  mov     r8d, ebp; dwMessageId
0x18001ba5f  xor     edx, edx; lpSource
0x18001ba61  mov     ecx, 1200h; dwFlags
0x18001ba66  call    cs:__imp_FormatMessageW
0x18001ba6c  lea     rsi, [r14+rsi*2]
0x18001ba70  mov     r9, [rbx+38h]; unsigned __int16 *
0x18001ba74  mov     rax, [rbx+88h]
0x18001ba7b  mov     rcx, [rbx+80h]
0x18001ba82  mov     rdx, rsi; unsigned __int16 *
0x18001ba85  test    r9, r9
0x18001ba88  jz      short loc_18001BAAC
0x18001ba8a  mov     [rsp+278h+Arguments], rax
0x18001ba8f  mov     qword ptr [rsp+278h+nSize], rcx
0x18001ba94  mov     eax, [rbx+40h]
0x18001ba97  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001ba9b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18001baa2  mov     rcx, r14; this
0x18001baa5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001baaa  jmp     short loc_18001BAC3
0x18001baac  mov     [rsp+278h+lpBuffer], rax
0x18001bab1  mov     r9, rcx; unsigned __int16 *
0x18001bab4  lea     r8, aHsP; "%hs!%p: "
0x18001babb  mov     rcx, r14; this
0x18001babe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001bac3  mov     r14, rax
0x18001bac6  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001bacd  test    r9, r9
0x18001bad0  jz      short loc_18001BAE7
0x18001bad2  lea     r8, aCallerP; "(caller: %p) "
0x18001bad9  mov     rdx, rsi; unsigned __int16 *
0x18001badc  mov     rcx, rax; this
0x18001badf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001bae4  mov     r14, rax
0x18001bae7  call    cs:__imp_GetCurrentThreadId
0x18001baed  lea     rcx, [rsp+278h+Buffer]
0x18001baf2  mov     [rsp+278h+var_240], rcx
0x18001baf7  mov     dword ptr [rsp+278h+Arguments], ebp
0x18001bafb  mov     [rsp+278h+nSize], eax
0x18001baff  mov     eax, [rbx+44h]
0x18001bb02  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001bb06  mov     r9, rdi; unsigned __int16 *
0x18001bb09  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18001bb10  mov     rdx, rsi; unsigned __int16 *
0x18001bb13  mov     rcx, r14; this
0x18001bb16  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001bb1b  cmp     [rbx+18h], r15
0x18001bb1f  jnz     short loc_18001BB31
0x18001bb21  cmp     [rbx+48h], r15
0x18001bb25  jnz     short loc_18001BB31
0x18001bb27  cmp     [rbx+30h], r15
0x18001bb2b  jz      loc_18001BBC1
0x18001bb31  lea     r8, asc_180053CB8; "    "
0x18001bb38  mov     rdx, rsi; unsigned __int16 *
0x18001bb3b  mov     rcx, rax; this
0x18001bb3e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001bb43  mov     r9, [rbx+18h]; unsigned __int16 *
0x18001bb47  test    r9, r9
0x18001bb4a  jz      short loc_18001BB5E
0x18001bb4c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18001bb53  mov     rdx, rsi; unsigned __int16 *
0x18001bb56  mov     rcx, rax; this
0x18001bb59  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001bb5e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18001bb62  test    r9, r9
0x18001bb65  jz      short loc_18001BB79
0x18001bb67  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001bb6e  mov     rdx, rsi; unsigned __int16 *
0x18001bb71  mov     rcx, rax; this
0x18001bb74  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001bb79  mov     rcx, [rbx+28h]
0x18001bb7d  mov     r9, [rbx+30h]; unsigned __int16 *
0x18001bb81  mov     rdx, rsi; unsigned __int16 *
0x18001bb84  test    rcx, rcx
0x18001bb87  jz      short loc_18001BB9F
0x18001bb89  mov     [rsp+278h+lpBuffer], rcx
0x18001bb8e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18001bb95  mov     rcx, rax; this
0x18001bb98  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001bb9d  jmp     short loc_18001BBC1
0x18001bb9f  mov     rcx, rax; this
0x18001bba2  test    r9, r9
0x18001bba5  jz      short loc_18001BBB5
0x18001bba7  lea     r8, aHs; "[%hs]\n"
0x18001bbae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001bbb3  jmp     short loc_18001BBC1
0x18001bbb5  lea     r8, asc_18005102C; "\n"
0x18001bbbc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001bbc1  xor     eax, eax
0x18001bbc3  mov     rcx, [rsp+278h+var_38]
0x18001bbcb  xor     rcx, rsp; StackCookie
0x18001bbce  call    __security_check_cookie
0x18001bbd3  mov     rbx, [rsp+278h+arg_18]
0x18001bbdb  add     rsp, 250h
0x18001bbe2  pop     r15
0x18001bbe4  pop     r14
0x18001bbe6  pop     rdi
0x18001bbe7  pop     rsi
0x18001bbe8  pop     rbp
0x18001bbe9  retn
```
