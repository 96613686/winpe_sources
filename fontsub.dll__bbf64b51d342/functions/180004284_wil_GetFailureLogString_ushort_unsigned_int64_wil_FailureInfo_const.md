# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004284`
- end: `0x18000453a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800031ec`
- `0x180004d34`

## callees

- `0x180004284`
- `0x180005034`
- `0x18001abfa`
- `0x18001ac90`
- `0x18001c010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x1800043b6`
- `KERNEL32!FormatMessageW` at `0x1800043b6`
- `KERNEL32!GetCurrentThreadId` at `0x180004437`
- `KERNEL32!GetCurrentThreadId` at `0x180004437`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rdi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rsi
  __int64 v13; // rax
  unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // r9
  wil::details *v16; // r14
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
  v7 = (void (__fastcall *)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
  *(_WORD *)this = 0;
  if ( v7 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      v7(a3, this, a2, a4);
      if ( *(_WORD *)this )
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
          v8 = (const char *)&byte_18001D570;
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
  v12 = (unsigned __int16 *)((char *)this + 2 * (_QWORD)a2);
  v13 = *(_QWORD *)(a3 + 136);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, *(_QWORD *)(a3 + 128), v13);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs!%p: ", *(const unsigned __int16 **)(a3 + 128), v13);
  }
  v15 = *(const unsigned __int16 **)(a3 + 144);
  v16 = (wil::details *)v14;
  if ( v15 )
    v16 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v12, L"(caller: %p) ", v15);
  LODWORD(Arguments) = v10;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
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
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180004284  mov     [rsp+arg_18], rbx
0x180004289  push    rbp
0x18000428a  push    rsi
0x18000428b  push    rdi
0x18000428c  push    r14
0x18000428e  push    r15
0x180004290  sub     rsp, 250h
0x180004297  mov     rax, cs:__security_cookie
0x18000429e  xor     rax, rsp
0x1800042a1  mov     [rsp+278h+var_38], rax
0x1800042a9  xor     r15d, r15d
0x1800042ac  mov     rbx, r8
0x1800042af  mov     rsi, rdx
0x1800042b2  mov     r14, rcx
0x1800042b5  test    rdx, rdx
0x1800042b8  jz      loc_180004511
0x1800042be  test    rcx, rcx
0x1800042c1  jz      loc_180004511
0x1800042c7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800042ce  mov     [rcx], r15w
0x1800042d2  test    rax, rax
0x1800042d5  jz      short loc_1800042F8
0x1800042d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800042de  jz      short loc_1800042F8
0x1800042e0  mov     r8, rdx
0x1800042e3  mov     rdx, rcx
0x1800042e6  mov     rcx, rbx
0x1800042e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042ee  cmp     [r14], r15w
0x1800042f2  jnz     loc_180004511
0x1800042f8  mov     ecx, [rbx]
0x1800042fa  mov     bpl, 8
0x1800042fd  test    ecx, ecx
0x1800042ff  jz      short loc_18000434A
0x180004301  sub     ecx, 1
0x180004304  jz      short loc_180004332
0x180004306  sub     ecx, 1
0x180004309  jz      short loc_180004322
0x18000430b  cmp     ecx, 1
0x18000430e  jz      short loc_180004319
0x180004310  lea     rdi, byte_18001D570
0x180004317  jmp     short loc_180004351
0x180004319  lea     rdi, aFailfast; "FailFast"
0x180004320  jmp     short loc_180004351
0x180004322  lea     rax, aLoghr; "LogHr"
0x180004329  lea     rdi, aLognt; "LogNt"
0x180004330  jmp     short loc_180004340
0x180004332  lea     rax, aReturnhr; "ReturnHr"
0x180004339  lea     rdi, aReturnnt; "ReturnNt"
0x180004340  test    [rbx+4], bpl
0x180004344  cmovz   rdi, rax
0x180004348  jmp     short loc_180004351
0x18000434a  lea     rdi, aException; "Exception"
0x180004351  xor     edx, edx; Val
0x180004353  lea     rcx, [rsp+278h+Buffer]; void *
0x180004358  mov     r8d, 200h; Size
0x18000435e  call    memset_0
0x180004363  test    [rbx+4], bpl
0x180004367  jz      short loc_18000438C
0x180004369  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004370  mov     ebp, [rbx+0Ch]
0x180004373  test    rax, rax
0x180004376  jz      short loc_1800043BC
0x180004378  mov     r8d, 100h
0x18000437e  lea     rdx, [rsp+278h+Buffer]
0x180004383  mov     ecx, ebp
0x180004385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000438a  jmp     short loc_1800043BC
0x18000438c  mov     ebp, [rbx+8]
0x18000438f  lea     rax, [rsp+278h+Buffer]
0x180004394  mov     [rsp+278h+Arguments], r15; Arguments
0x180004399  mov     r8d, ebp; dwMessageId
0x18000439c  mov     [rsp+278h+nSize], 100h; nSize
0x1800043a4  mov     r9d, 400h; dwLanguageId
0x1800043aa  xor     edx, edx; lpSource
0x1800043ac  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800043b1  mov     ecx, 1200h; dwFlags
0x1800043b6  call    cs:__imp_FormatMessageW
0x1800043bc  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800043c0  lea     rsi, [r14+rsi*2]
0x1800043c4  mov     rax, [rbx+88h]
0x1800043cb  mov     rdx, rsi; unsigned __int16 *
0x1800043ce  mov     rcx, [rbx+80h]
0x1800043d5  test    r9, r9
0x1800043d8  jz      short loc_1800043FC
0x1800043da  mov     [rsp+278h+Arguments], rax
0x1800043df  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800043e6  mov     eax, [rbx+40h]
0x1800043e9  mov     qword ptr [rsp+278h+nSize], rcx
0x1800043ee  mov     rcx, r14; this
0x1800043f1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800043f5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800043fa  jmp     short loc_180004413
0x1800043fc  mov     r9, rcx; unsigned __int16 *
0x1800043ff  mov     [rsp+278h+lpBuffer], rax
0x180004404  mov     rcx, r14; this
0x180004407  lea     r8, aHsP; "%hs!%p: "
0x18000440e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004413  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000441a  mov     r14, rax
0x18000441d  test    r9, r9
0x180004420  jz      short loc_180004437
0x180004422  lea     r8, aCallerP; "(caller: %p) "
0x180004429  mov     rdx, rsi; unsigned __int16 *
0x18000442c  mov     rcx, rax; this
0x18000442f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004434  mov     r14, rax
0x180004437  call    cs:__imp_GetCurrentThreadId
0x18000443d  lea     rcx, [rsp+278h+Buffer]
0x180004442  mov     r9, rdi; unsigned __int16 *
0x180004445  mov     [rsp+278h+var_240], rcx
0x18000444a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004451  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004455  mov     rdx, rsi; unsigned __int16 *
0x180004458  mov     [rsp+278h+nSize], eax
0x18000445c  mov     rcx, r14; this
0x18000445f  mov     eax, [rbx+44h]
0x180004462  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004466  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000446b  cmp     [rbx+18h], r15
0x18000446f  jnz     short loc_180004481
0x180004471  cmp     [rbx+48h], r15
0x180004475  jnz     short loc_180004481
0x180004477  cmp     [rbx+30h], r15
0x18000447b  jz      loc_180004511
0x180004481  lea     r8, asc_18001D660; "    "
0x180004488  mov     rdx, rsi; unsigned __int16 *
0x18000448b  mov     rcx, rax; this
0x18000448e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004493  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004497  test    r9, r9
0x18000449a  jz      short loc_1800044AE
0x18000449c  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800044a3  mov     rdx, rsi; unsigned __int16 *
0x1800044a6  mov     rcx, rax; this
0x1800044a9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800044ae  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800044b2  test    r9, r9
0x1800044b5  jz      short loc_1800044C9
0x1800044b7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800044be  mov     rdx, rsi; unsigned __int16 *
0x1800044c1  mov     rcx, rax; this
0x1800044c4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800044c9  mov     rcx, [rbx+28h]
0x1800044cd  mov     rdx, rsi; unsigned __int16 *
0x1800044d0  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800044d4  test    rcx, rcx
0x1800044d7  jz      short loc_1800044EF
0x1800044d9  mov     [rsp+278h+lpBuffer], rcx
0x1800044de  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800044e5  mov     rcx, rax; this
0x1800044e8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800044ed  jmp     short loc_180004511
0x1800044ef  mov     rcx, rax; this
0x1800044f2  test    r9, r9
0x1800044f5  jz      short loc_180004505
0x1800044f7  lea     r8, aHs; "[%hs]\n"
0x1800044fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004503  jmp     short loc_180004511
0x180004505  lea     r8, asc_18001D6D8; "\n"
0x18000450c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004511  xor     eax, eax
0x180004513  mov     rcx, [rsp+278h+var_38]
0x18000451b  xor     rcx, rsp; StackCookie
0x18000451e  call    __security_check_cookie
0x180004523  mov     rbx, [rsp+278h+arg_18]
0x18000452b  add     rsp, 250h
0x180004532  pop     r15
0x180004534  pop     r14
0x180004536  pop     rdi
0x180004537  pop     rsi
0x180004538  pop     rbp
0x180004539  retn
```
