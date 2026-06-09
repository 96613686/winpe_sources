# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180021184`
- end: `0x18002143a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800218cc`
- `0x180021d60`
- `0x180023020`

## callees

- `0x18001e1e0`
- `0x18001eb7c`
- `0x180021184`
- `0x180021bc8`
- `0x180065010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021337`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021337`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800212b6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800212b6`

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
          v7 = qword_180075F88;
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
0x180021184  mov     [rsp+arg_18], rbx
0x180021189  push    rbp
0x18002118a  push    rsi
0x18002118b  push    rdi
0x18002118c  push    r14
0x18002118e  push    r15
0x180021190  sub     rsp, 250h
0x180021197  mov     rax, cs:__security_cookie
0x18002119e  xor     rax, rsp
0x1800211a1  mov     [rsp+278h+var_38], rax
0x1800211a9  mov     rbx, r8
0x1800211ac  mov     rsi, rdx
0x1800211af  mov     r14, rcx
0x1800211b2  xor     r15d, r15d
0x1800211b5  test    rdx, rdx
0x1800211b8  jz      loc_180021411
0x1800211be  test    rcx, rcx
0x1800211c1  jz      loc_180021411
0x1800211c7  mov     [rcx], r15w
0x1800211cb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800211d2  test    rax, rax
0x1800211d5  jz      short loc_1800211F8
0x1800211d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800211de  jz      short loc_1800211F8
0x1800211e0  mov     r8, rdx
0x1800211e3  mov     rdx, rcx
0x1800211e6  mov     rcx, rbx
0x1800211e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211ee  cmp     [r14], r15w
0x1800211f2  jnz     loc_180021411
0x1800211f8  mov     ecx, [rbx]
0x1800211fa  mov     bpl, 8
0x1800211fd  test    ecx, ecx
0x1800211ff  jz      short loc_18002124A
0x180021201  sub     ecx, 1
0x180021204  jz      short loc_180021232
0x180021206  sub     ecx, 1
0x180021209  jz      short loc_180021222
0x18002120b  cmp     ecx, 1
0x18002120e  jz      short loc_180021219
0x180021210  lea     rdi, qword_180075F88
0x180021217  jmp     short loc_180021251
0x180021219  lea     rdi, aFailfast; "FailFast"
0x180021220  jmp     short loc_180021251
0x180021222  lea     rax, aLoghr; "LogHr"
0x180021229  lea     rdi, aLognt; "LogNt"
0x180021230  jmp     short loc_180021240
0x180021232  lea     rax, aReturnhr; "ReturnHr"
0x180021239  lea     rdi, aReturnnt; "ReturnNt"
0x180021240  test    [rbx+4], bpl
0x180021244  cmovz   rdi, rax
0x180021248  jmp     short loc_180021251
0x18002124a  lea     rdi, aException; "Exception"
0x180021251  xor     edx, edx; Val
0x180021253  mov     r8d, 200h; Size
0x180021259  lea     rcx, [rsp+278h+Buffer]; void *
0x18002125e  call    memset_0
0x180021263  test    [rbx+4], bpl
0x180021267  jz      short loc_18002128C
0x180021269  mov     ebp, [rbx+0Ch]
0x18002126c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180021273  test    rax, rax
0x180021276  jz      short loc_1800212BC
0x180021278  mov     r8d, 100h
0x18002127e  lea     rdx, [rsp+278h+Buffer]
0x180021283  mov     ecx, ebp
0x180021285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002128a  jmp     short loc_1800212BC
0x18002128c  mov     ebp, [rbx+8]
0x18002128f  mov     [rsp+278h+Arguments], r15; Arguments
0x180021294  mov     [rsp+278h+nSize], 100h; nSize
0x18002129c  lea     rax, [rsp+278h+Buffer]
0x1800212a1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800212a6  mov     r9d, 400h; dwLanguageId
0x1800212ac  mov     r8d, ebp; dwMessageId
0x1800212af  xor     edx, edx; lpSource
0x1800212b1  mov     ecx, 1200h; dwFlags
0x1800212b6  call    cs:__imp_FormatMessageW
0x1800212bc  lea     rsi, [r14+rsi*2]
0x1800212c0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800212c4  mov     rax, [rbx+88h]
0x1800212cb  mov     rcx, [rbx+80h]
0x1800212d2  mov     rdx, rsi; unsigned __int16 *
0x1800212d5  test    r9, r9
0x1800212d8  jz      short loc_1800212FC
0x1800212da  mov     [rsp+278h+Arguments], rax
0x1800212df  mov     qword ptr [rsp+278h+nSize], rcx
0x1800212e4  mov     eax, [rbx+40h]
0x1800212e7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800212eb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800212f2  mov     rcx, r14; this
0x1800212f5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800212fa  jmp     short loc_180021313
0x1800212fc  mov     [rsp+278h+lpBuffer], rax
0x180021301  mov     r9, rcx; unsigned __int16 *
0x180021304  lea     r8, aHsP; "%hs!%p: "
0x18002130b  mov     rcx, r14; this
0x18002130e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180021313  mov     r14, rax
0x180021316  mov     r9, [rbx+90h]; unsigned __int16 *
0x18002131d  test    r9, r9
0x180021320  jz      short loc_180021337
0x180021322  lea     r8, aCallerP; "(caller: %p) "
0x180021329  mov     rdx, rsi; unsigned __int16 *
0x18002132c  mov     rcx, rax; this
0x18002132f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180021334  mov     r14, rax
0x180021337  call    cs:__imp_GetCurrentThreadId
0x18002133d  lea     rcx, [rsp+278h+Buffer]
0x180021342  mov     [rsp+278h+var_240], rcx
0x180021347  mov     dword ptr [rsp+278h+Arguments], ebp
0x18002134b  mov     [rsp+278h+nSize], eax
0x18002134f  mov     eax, [rbx+44h]
0x180021352  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180021356  mov     r9, rdi; unsigned __int16 *
0x180021359  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180021360  mov     rdx, rsi; unsigned __int16 *
0x180021363  mov     rcx, r14; this
0x180021366  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002136b  cmp     [rbx+18h], r15
0x18002136f  jnz     short loc_180021381
0x180021371  cmp     [rbx+48h], r15
0x180021375  jnz     short loc_180021381
0x180021377  cmp     [rbx+30h], r15
0x18002137b  jz      loc_180021411
0x180021381  lea     r8, asc_180076090; "    "
0x180021388  mov     rdx, rsi; unsigned __int16 *
0x18002138b  mov     rcx, rax; this
0x18002138e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180021393  mov     r9, [rbx+18h]; unsigned __int16 *
0x180021397  test    r9, r9
0x18002139a  jz      short loc_1800213AE
0x18002139c  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800213a3  mov     rdx, rsi; unsigned __int16 *
0x1800213a6  mov     rcx, rax; this
0x1800213a9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800213ae  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800213b2  test    r9, r9
0x1800213b5  jz      short loc_1800213C9
0x1800213b7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800213be  mov     rdx, rsi; unsigned __int16 *
0x1800213c1  mov     rcx, rax; this
0x1800213c4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800213c9  mov     rcx, [rbx+28h]
0x1800213cd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800213d1  mov     rdx, rsi; unsigned __int16 *
0x1800213d4  test    rcx, rcx
0x1800213d7  jz      short loc_1800213EF
0x1800213d9  mov     [rsp+278h+lpBuffer], rcx
0x1800213de  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800213e5  mov     rcx, rax; this
0x1800213e8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800213ed  jmp     short loc_180021411
0x1800213ef  mov     rcx, rax; this
0x1800213f2  test    r9, r9
0x1800213f5  jz      short loc_180021405
0x1800213f7  lea     r8, aHs; "[%hs]\n"
0x1800213fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180021403  jmp     short loc_180021411
0x180021405  lea     r8, asc_180076108; "\n"
0x18002140c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180021411  xor     eax, eax
0x180021413  mov     rcx, [rsp+278h+var_38]
0x18002141b  xor     rcx, rsp; StackCookie
0x18002141e  call    __security_check_cookie
0x180021423  mov     rbx, [rsp+278h+arg_18]
0x18002142b  add     rsp, 250h
0x180021432  pop     r15
0x180021434  pop     r14
0x180021436  pop     rdi
0x180021437  pop     rsi
0x180021438  pop     rbp
0x180021439  retn
```
