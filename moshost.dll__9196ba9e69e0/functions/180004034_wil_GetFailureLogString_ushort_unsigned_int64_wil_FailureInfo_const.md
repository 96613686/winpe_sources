# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004034`
- end: `0x1800042ea`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x180002c90`
- `0x180002ef8`
- `0x180004994`
- `0x180006190`
- `0x18000c900`
- `0x18000ca34`

## callees

- `0x180001d00`
- `0x180002722`
- `0x180004034`
- `0x180004c94`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800041e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800041e7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004166`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004166`

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
          v7 = (const char *)&byte_180011073;
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
0x180004034  mov     [rsp+arg_18], rbx
0x180004039  push    rbp
0x18000403a  push    rsi
0x18000403b  push    rdi
0x18000403c  push    r14
0x18000403e  push    r15
0x180004040  sub     rsp, 250h
0x180004047  mov     rax, cs:__security_cookie
0x18000404e  xor     rax, rsp
0x180004051  mov     [rsp+278h+var_38], rax
0x180004059  mov     rbx, r8
0x18000405c  mov     rsi, rdx
0x18000405f  mov     r14, rcx
0x180004062  xor     r15d, r15d
0x180004065  test    rdx, rdx
0x180004068  jz      loc_1800042C1
0x18000406e  test    rcx, rcx
0x180004071  jz      loc_1800042C1
0x180004077  mov     [rcx], r15w
0x18000407b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004082  test    rax, rax
0x180004085  jz      short loc_1800040A8
0x180004087  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000408e  jz      short loc_1800040A8
0x180004090  mov     r8, rdx
0x180004093  mov     rdx, rcx
0x180004096  mov     rcx, rbx
0x180004099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000409e  cmp     [r14], r15w
0x1800040a2  jnz     loc_1800042C1
0x1800040a8  mov     ecx, [rbx]
0x1800040aa  mov     bpl, 8
0x1800040ad  test    ecx, ecx
0x1800040af  jz      short loc_1800040FA
0x1800040b1  sub     ecx, 1
0x1800040b4  jz      short loc_1800040E2
0x1800040b6  sub     ecx, 1
0x1800040b9  jz      short loc_1800040D2
0x1800040bb  cmp     ecx, 1
0x1800040be  jz      short loc_1800040C9
0x1800040c0  lea     rdi, byte_180011073
0x1800040c7  jmp     short loc_180004101
0x1800040c9  lea     rdi, aFailfast; "FailFast"
0x1800040d0  jmp     short loc_180004101
0x1800040d2  lea     rax, aLoghr; "LogHr"
0x1800040d9  lea     rdi, aLognt; "LogNt"
0x1800040e0  jmp     short loc_1800040F0
0x1800040e2  lea     rax, aReturnhr; "ReturnHr"
0x1800040e9  lea     rdi, aReturnnt; "ReturnNt"
0x1800040f0  test    [rbx+4], bpl
0x1800040f4  cmovz   rdi, rax
0x1800040f8  jmp     short loc_180004101
0x1800040fa  lea     rdi, aException; "Exception"
0x180004101  xor     edx, edx; Val
0x180004103  mov     r8d, 200h; Size
0x180004109  lea     rcx, [rsp+278h+Buffer]; void *
0x18000410e  call    memset_0
0x180004113  test    [rbx+4], bpl
0x180004117  jz      short loc_18000413C
0x180004119  mov     ebp, [rbx+0Ch]
0x18000411c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004123  test    rax, rax
0x180004126  jz      short loc_18000416C
0x180004128  mov     r8d, 100h
0x18000412e  lea     rdx, [rsp+278h+Buffer]
0x180004133  mov     ecx, ebp
0x180004135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000413a  jmp     short loc_18000416C
0x18000413c  mov     ebp, [rbx+8]
0x18000413f  mov     [rsp+278h+Arguments], r15; Arguments
0x180004144  mov     [rsp+278h+nSize], 100h; nSize
0x18000414c  lea     rax, [rsp+278h+Buffer]
0x180004151  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004156  mov     r9d, 400h; dwLanguageId
0x18000415c  mov     r8d, ebp; dwMessageId
0x18000415f  xor     edx, edx; lpSource
0x180004161  mov     ecx, 1200h; dwFlags
0x180004166  call    cs:__imp_FormatMessageW
0x18000416c  lea     rsi, [r14+rsi*2]
0x180004170  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004174  mov     rax, [rbx+88h]
0x18000417b  mov     rcx, [rbx+80h]
0x180004182  mov     rdx, rsi; unsigned __int16 *
0x180004185  test    r9, r9
0x180004188  jz      short loc_1800041AC
0x18000418a  mov     [rsp+278h+Arguments], rax
0x18000418f  mov     qword ptr [rsp+278h+nSize], rcx
0x180004194  mov     eax, [rbx+40h]
0x180004197  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000419b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800041a2  mov     rcx, r14; this
0x1800041a5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800041aa  jmp     short loc_1800041C3
0x1800041ac  mov     [rsp+278h+lpBuffer], rax
0x1800041b1  mov     r9, rcx; unsigned __int16 *
0x1800041b4  lea     r8, aHsP; "%hs!%p: "
0x1800041bb  mov     rcx, r14; this
0x1800041be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800041c3  mov     r14, rax
0x1800041c6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800041cd  test    r9, r9
0x1800041d0  jz      short loc_1800041E7
0x1800041d2  lea     r8, aCallerP; "(caller: %p) "
0x1800041d9  mov     rdx, rsi; unsigned __int16 *
0x1800041dc  mov     rcx, rax; this
0x1800041df  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800041e4  mov     r14, rax
0x1800041e7  call    cs:__imp_GetCurrentThreadId
0x1800041ed  lea     rcx, [rsp+278h+Buffer]
0x1800041f2  mov     [rsp+278h+var_240], rcx
0x1800041f7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800041fb  mov     [rsp+278h+nSize], eax
0x1800041ff  mov     eax, [rbx+44h]
0x180004202  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004206  mov     r9, rdi; unsigned __int16 *
0x180004209  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004210  mov     rdx, rsi; unsigned __int16 *
0x180004213  mov     rcx, r14; this
0x180004216  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000421b  cmp     [rbx+18h], r15
0x18000421f  jnz     short loc_180004231
0x180004221  cmp     [rbx+48h], r15
0x180004225  jnz     short loc_180004231
0x180004227  cmp     [rbx+30h], r15
0x18000422b  jz      loc_1800042C1
0x180004231  lea     r8, asc_180011178; "    "
0x180004238  mov     rdx, rsi; unsigned __int16 *
0x18000423b  mov     rcx, rax; this
0x18000423e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004243  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004247  test    r9, r9
0x18000424a  jz      short loc_18000425E
0x18000424c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004253  mov     rdx, rsi; unsigned __int16 *
0x180004256  mov     rcx, rax; this
0x180004259  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000425e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004262  test    r9, r9
0x180004265  jz      short loc_180004279
0x180004267  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000426e  mov     rdx, rsi; unsigned __int16 *
0x180004271  mov     rcx, rax; this
0x180004274  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004279  mov     rcx, [rbx+28h]
0x18000427d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004281  mov     rdx, rsi; unsigned __int16 *
0x180004284  test    rcx, rcx
0x180004287  jz      short loc_18000429F
0x180004289  mov     [rsp+278h+lpBuffer], rcx
0x18000428e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004295  mov     rcx, rax; this
0x180004298  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000429d  jmp     short loc_1800042C1
0x18000429f  mov     rcx, rax; this
0x1800042a2  test    r9, r9
0x1800042a5  jz      short loc_1800042B5
0x1800042a7  lea     r8, aHs; "[%hs]\n"
0x1800042ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800042b3  jmp     short loc_1800042C1
0x1800042b5  lea     r8, asc_1800111F0; "\n"
0x1800042bc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800042c1  xor     eax, eax
0x1800042c3  mov     rcx, [rsp+278h+var_38]
0x1800042cb  xor     rcx, rsp; StackCookie
0x1800042ce  call    __security_check_cookie
0x1800042d3  mov     rbx, [rsp+278h+arg_18]
0x1800042db  add     rsp, 250h
0x1800042e2  pop     r15
0x1800042e4  pop     r14
0x1800042e6  pop     rdi
0x1800042e7  pop     rsi
0x1800042e8  pop     rbp
0x1800042e9  retn
```
