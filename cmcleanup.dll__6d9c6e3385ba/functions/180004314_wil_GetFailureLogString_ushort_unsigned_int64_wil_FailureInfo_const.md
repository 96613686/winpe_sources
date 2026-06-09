# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004314`
- end: `0x1800045ca`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800024e0`
- `0x180002750`
- `0x180004d90`
- `0x1800079b0`

## callees

- `0x180001510`
- `0x1800020c4`
- `0x180004314`
- `0x180005090`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800044c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800044c7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004446`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004446`

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
          v7 = (const char *)&dword_18000A91C;
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
0x180004314  mov     [rsp+arg_18], rbx
0x180004319  push    rbp
0x18000431a  push    rsi
0x18000431b  push    rdi
0x18000431c  push    r14
0x18000431e  push    r15
0x180004320  sub     rsp, 250h
0x180004327  mov     rax, cs:__security_cookie
0x18000432e  xor     rax, rsp
0x180004331  mov     [rsp+278h+var_38], rax
0x180004339  mov     rbx, r8
0x18000433c  mov     rsi, rdx
0x18000433f  mov     r14, rcx
0x180004342  xor     r15d, r15d
0x180004345  test    rdx, rdx
0x180004348  jz      loc_1800045A1
0x18000434e  test    rcx, rcx
0x180004351  jz      loc_1800045A1
0x180004357  mov     [rcx], r15w
0x18000435b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004362  test    rax, rax
0x180004365  jz      short loc_180004388
0x180004367  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000436e  jz      short loc_180004388
0x180004370  mov     r8, rdx
0x180004373  mov     rdx, rcx
0x180004376  mov     rcx, rbx
0x180004379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000437e  cmp     [r14], r15w
0x180004382  jnz     loc_1800045A1
0x180004388  mov     ecx, [rbx]
0x18000438a  mov     bpl, 8
0x18000438d  test    ecx, ecx
0x18000438f  jz      short loc_1800043DA
0x180004391  sub     ecx, 1
0x180004394  jz      short loc_1800043C2
0x180004396  sub     ecx, 1
0x180004399  jz      short loc_1800043B2
0x18000439b  cmp     ecx, 1
0x18000439e  jz      short loc_1800043A9
0x1800043a0  lea     rdi, dword_18000A91C
0x1800043a7  jmp     short loc_1800043E1
0x1800043a9  lea     rdi, aFailfast; "FailFast"
0x1800043b0  jmp     short loc_1800043E1
0x1800043b2  lea     rax, aLoghr; "LogHr"
0x1800043b9  lea     rdi, aLognt; "LogNt"
0x1800043c0  jmp     short loc_1800043D0
0x1800043c2  lea     rax, aReturnhr; "ReturnHr"
0x1800043c9  lea     rdi, aReturnnt; "ReturnNt"
0x1800043d0  test    [rbx+4], bpl
0x1800043d4  cmovz   rdi, rax
0x1800043d8  jmp     short loc_1800043E1
0x1800043da  lea     rdi, aException; "Exception"
0x1800043e1  xor     edx, edx; Val
0x1800043e3  mov     r8d, 200h; Size
0x1800043e9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800043ee  call    memset_0
0x1800043f3  test    [rbx+4], bpl
0x1800043f7  jz      short loc_18000441C
0x1800043f9  mov     ebp, [rbx+0Ch]
0x1800043fc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004403  test    rax, rax
0x180004406  jz      short loc_18000444C
0x180004408  mov     r8d, 100h
0x18000440e  lea     rdx, [rsp+278h+Buffer]
0x180004413  mov     ecx, ebp
0x180004415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000441a  jmp     short loc_18000444C
0x18000441c  mov     ebp, [rbx+8]
0x18000441f  mov     [rsp+278h+Arguments], r15; Arguments
0x180004424  mov     [rsp+278h+nSize], 100h; nSize
0x18000442c  lea     rax, [rsp+278h+Buffer]
0x180004431  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004436  mov     r9d, 400h; dwLanguageId
0x18000443c  mov     r8d, ebp; dwMessageId
0x18000443f  xor     edx, edx; lpSource
0x180004441  mov     ecx, 1200h; dwFlags
0x180004446  call    cs:__imp_FormatMessageW
0x18000444c  lea     rsi, [r14+rsi*2]
0x180004450  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004454  mov     rax, [rbx+88h]
0x18000445b  mov     rcx, [rbx+80h]
0x180004462  mov     rdx, rsi; unsigned __int16 *
0x180004465  test    r9, r9
0x180004468  jz      short loc_18000448C
0x18000446a  mov     [rsp+278h+Arguments], rax
0x18000446f  mov     qword ptr [rsp+278h+nSize], rcx
0x180004474  mov     eax, [rbx+40h]
0x180004477  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000447b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004482  mov     rcx, r14; this
0x180004485  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000448a  jmp     short loc_1800044A3
0x18000448c  mov     [rsp+278h+lpBuffer], rax
0x180004491  mov     r9, rcx; unsigned __int16 *
0x180004494  lea     r8, aHsP; "%hs!%p: "
0x18000449b  mov     rcx, r14; this
0x18000449e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800044a3  mov     r14, rax
0x1800044a6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800044ad  test    r9, r9
0x1800044b0  jz      short loc_1800044C7
0x1800044b2  lea     r8, aCallerP; "(caller: %p) "
0x1800044b9  mov     rdx, rsi; unsigned __int16 *
0x1800044bc  mov     rcx, rax; this
0x1800044bf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800044c4  mov     r14, rax
0x1800044c7  call    cs:__imp_GetCurrentThreadId
0x1800044cd  lea     rcx, [rsp+278h+Buffer]
0x1800044d2  mov     [rsp+278h+var_240], rcx
0x1800044d7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800044db  mov     [rsp+278h+nSize], eax
0x1800044df  mov     eax, [rbx+44h]
0x1800044e2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800044e6  mov     r9, rdi; unsigned __int16 *
0x1800044e9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800044f0  mov     rdx, rsi; unsigned __int16 *
0x1800044f3  mov     rcx, r14; this
0x1800044f6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800044fb  cmp     [rbx+18h], r15
0x1800044ff  jnz     short loc_180004511
0x180004501  cmp     [rbx+48h], r15
0x180004505  jnz     short loc_180004511
0x180004507  cmp     [rbx+30h], r15
0x18000450b  jz      loc_1800045A1
0x180004511  lea     r8, asc_18000AA20; "    "
0x180004518  mov     rdx, rsi; unsigned __int16 *
0x18000451b  mov     rcx, rax; this
0x18000451e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004523  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004527  test    r9, r9
0x18000452a  jz      short loc_18000453E
0x18000452c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004533  mov     rdx, rsi; unsigned __int16 *
0x180004536  mov     rcx, rax; this
0x180004539  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000453e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004542  test    r9, r9
0x180004545  jz      short loc_180004559
0x180004547  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000454e  mov     rdx, rsi; unsigned __int16 *
0x180004551  mov     rcx, rax; this
0x180004554  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004559  mov     rcx, [rbx+28h]
0x18000455d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004561  mov     rdx, rsi; unsigned __int16 *
0x180004564  test    rcx, rcx
0x180004567  jz      short loc_18000457F
0x180004569  mov     [rsp+278h+lpBuffer], rcx
0x18000456e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004575  mov     rcx, rax; this
0x180004578  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000457d  jmp     short loc_1800045A1
0x18000457f  mov     rcx, rax; this
0x180004582  test    r9, r9
0x180004585  jz      short loc_180004595
0x180004587  lea     r8, aHs; "[%hs]\n"
0x18000458e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004593  jmp     short loc_1800045A1
0x180004595  lea     r8, asc_18000AA98; "\n"
0x18000459c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800045a1  xor     eax, eax
0x1800045a3  mov     rcx, [rsp+278h+var_38]
0x1800045ab  xor     rcx, rsp; StackCookie
0x1800045ae  call    __security_check_cookie
0x1800045b3  mov     rbx, [rsp+278h+arg_18]
0x1800045bb  add     rsp, 250h
0x1800045c2  pop     r15
0x1800045c4  pop     r14
0x1800045c6  pop     rdi
0x1800045c7  pop     rsi
0x1800045c8  pop     rbp
0x1800045c9  retn
```
