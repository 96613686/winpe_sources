# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004394`
- end: `0x18000464a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180005428`
- `0x180008f80`

## callees

- `0x180004394`
- `0x180005724`
- `0x18002e202`
- `0x18002e230`
- `0x180030010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x1800044c6`
- `KERNEL32!FormatMessageW` at `0x1800044c6`
- `KERNEL32!GetCurrentThreadId` at `0x180004547`
- `KERNEL32!GetCurrentThreadId` at `0x180004547`

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
          v7 = (const char *)&byte_180033E20;
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
0x180004394  mov     [rsp+arg_18], rbx
0x180004399  push    rbp
0x18000439a  push    rsi
0x18000439b  push    rdi
0x18000439c  push    r14
0x18000439e  push    r15
0x1800043a0  sub     rsp, 250h
0x1800043a7  mov     rax, cs:__security_cookie
0x1800043ae  xor     rax, rsp
0x1800043b1  mov     [rsp+278h+var_38], rax
0x1800043b9  mov     rbx, r8
0x1800043bc  mov     rsi, rdx
0x1800043bf  mov     r14, rcx
0x1800043c2  xor     r15d, r15d
0x1800043c5  test    rdx, rdx
0x1800043c8  jz      loc_180004621
0x1800043ce  test    rcx, rcx
0x1800043d1  jz      loc_180004621
0x1800043d7  mov     [rcx], r15w
0x1800043db  mov     rax, cs:g_pfnResultLoggingCallback
0x1800043e2  test    rax, rax
0x1800043e5  jz      short loc_180004408
0x1800043e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800043ee  jz      short loc_180004408
0x1800043f0  mov     r8, rdx
0x1800043f3  mov     rdx, rcx
0x1800043f6  mov     rcx, rbx
0x1800043f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043fe  cmp     [r14], r15w
0x180004402  jnz     loc_180004621
0x180004408  mov     ecx, [rbx]
0x18000440a  mov     bpl, 8
0x18000440d  test    ecx, ecx
0x18000440f  jz      short loc_18000445A
0x180004411  sub     ecx, 1
0x180004414  jz      short loc_180004442
0x180004416  sub     ecx, 1
0x180004419  jz      short loc_180004432
0x18000441b  cmp     ecx, 1
0x18000441e  jz      short loc_180004429
0x180004420  lea     rdi, byte_180033E20
0x180004427  jmp     short loc_180004461
0x180004429  lea     rdi, aFailfast; "FailFast"
0x180004430  jmp     short loc_180004461
0x180004432  lea     rax, aLoghr; "LogHr"
0x180004439  lea     rdi, aLognt; "LogNt"
0x180004440  jmp     short loc_180004450
0x180004442  lea     rax, aReturnhr; "ReturnHr"
0x180004449  lea     rdi, aReturnnt; "ReturnNt"
0x180004450  test    [rbx+4], bpl
0x180004454  cmovz   rdi, rax
0x180004458  jmp     short loc_180004461
0x18000445a  lea     rdi, aException; "Exception"
0x180004461  xor     edx, edx; Val
0x180004463  mov     r8d, 200h; Size
0x180004469  lea     rcx, [rsp+278h+Buffer]; void *
0x18000446e  call    memset_0
0x180004473  test    [rbx+4], bpl
0x180004477  jz      short loc_18000449C
0x180004479  mov     ebp, [rbx+0Ch]
0x18000447c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004483  test    rax, rax
0x180004486  jz      short loc_1800044CC
0x180004488  mov     r8d, 100h
0x18000448e  lea     rdx, [rsp+278h+Buffer]
0x180004493  mov     ecx, ebp
0x180004495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000449a  jmp     short loc_1800044CC
0x18000449c  mov     ebp, [rbx+8]
0x18000449f  mov     [rsp+278h+Arguments], r15; Arguments
0x1800044a4  mov     [rsp+278h+nSize], 100h; nSize
0x1800044ac  lea     rax, [rsp+278h+Buffer]
0x1800044b1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800044b6  mov     r9d, 400h; dwLanguageId
0x1800044bc  mov     r8d, ebp; dwMessageId
0x1800044bf  xor     edx, edx; lpSource
0x1800044c1  mov     ecx, 1200h; dwFlags
0x1800044c6  call    cs:__imp_FormatMessageW
0x1800044cc  lea     rsi, [r14+rsi*2]
0x1800044d0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800044d4  mov     rax, [rbx+88h]
0x1800044db  mov     rcx, [rbx+80h]
0x1800044e2  mov     rdx, rsi; unsigned __int16 *
0x1800044e5  test    r9, r9
0x1800044e8  jz      short loc_18000450C
0x1800044ea  mov     [rsp+278h+Arguments], rax
0x1800044ef  mov     qword ptr [rsp+278h+nSize], rcx
0x1800044f4  mov     eax, [rbx+40h]
0x1800044f7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800044fb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004502  mov     rcx, r14; this
0x180004505  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000450a  jmp     short loc_180004523
0x18000450c  mov     [rsp+278h+lpBuffer], rax
0x180004511  mov     r9, rcx; unsigned __int16 *
0x180004514  lea     r8, aHsP; "%hs!%p: "
0x18000451b  mov     rcx, r14; this
0x18000451e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004523  mov     r14, rax
0x180004526  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000452d  test    r9, r9
0x180004530  jz      short loc_180004547
0x180004532  lea     r8, aCallerP; "(caller: %p) "
0x180004539  mov     rdx, rsi; unsigned __int16 *
0x18000453c  mov     rcx, rax; this
0x18000453f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004544  mov     r14, rax
0x180004547  call    cs:__imp_GetCurrentThreadId
0x18000454d  lea     rcx, [rsp+278h+Buffer]
0x180004552  mov     [rsp+278h+var_240], rcx
0x180004557  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000455b  mov     [rsp+278h+nSize], eax
0x18000455f  mov     eax, [rbx+44h]
0x180004562  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004566  mov     r9, rdi; unsigned __int16 *
0x180004569  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004570  mov     rdx, rsi; unsigned __int16 *
0x180004573  mov     rcx, r14; this
0x180004576  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000457b  cmp     [rbx+18h], r15
0x18000457f  jnz     short loc_180004591
0x180004581  cmp     [rbx+48h], r15
0x180004585  jnz     short loc_180004591
0x180004587  cmp     [rbx+30h], r15
0x18000458b  jz      loc_180004621
0x180004591  lea     r8, asc_180033F28; "    "
0x180004598  mov     rdx, rsi; unsigned __int16 *
0x18000459b  mov     rcx, rax; this
0x18000459e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800045a3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800045a7  test    r9, r9
0x1800045aa  jz      short loc_1800045BE
0x1800045ac  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800045b3  mov     rdx, rsi; unsigned __int16 *
0x1800045b6  mov     rcx, rax; this
0x1800045b9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800045be  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800045c2  test    r9, r9
0x1800045c5  jz      short loc_1800045D9
0x1800045c7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800045ce  mov     rdx, rsi; unsigned __int16 *
0x1800045d1  mov     rcx, rax; this
0x1800045d4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800045d9  mov     rcx, [rbx+28h]
0x1800045dd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800045e1  mov     rdx, rsi; unsigned __int16 *
0x1800045e4  test    rcx, rcx
0x1800045e7  jz      short loc_1800045FF
0x1800045e9  mov     [rsp+278h+lpBuffer], rcx
0x1800045ee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800045f5  mov     rcx, rax; this
0x1800045f8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800045fd  jmp     short loc_180004621
0x1800045ff  mov     rcx, rax; this
0x180004602  test    r9, r9
0x180004605  jz      short loc_180004615
0x180004607  lea     r8, aHs; "[%hs]\n"
0x18000460e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004613  jmp     short loc_180004621
0x180004615  lea     r8, asc_180033FA0; "\n"
0x18000461c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004621  xor     eax, eax
0x180004623  mov     rcx, [rsp+278h+var_38]
0x18000462b  xor     rcx, rsp; StackCookie
0x18000462e  call    __security_check_cookie
0x180004633  mov     rbx, [rsp+278h+arg_18]
0x18000463b  add     rsp, 250h
0x180004642  pop     r15
0x180004644  pop     r14
0x180004646  pop     rdi
0x180004647  pop     rsi
0x180004648  pop     rbp
0x180004649  retn
```
