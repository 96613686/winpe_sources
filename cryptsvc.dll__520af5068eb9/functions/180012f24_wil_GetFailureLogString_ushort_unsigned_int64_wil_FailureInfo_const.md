# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180012f24`
- end: `0x1800131da`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180011a04`
- `0x180013b4c`

## callees

- `0x18000e2f0`
- `0x18000ec40`
- `0x180012f24`
- `0x180013e4c`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800130d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800130d7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180013056`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180013056`

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
          v8 = (const char *)&qword_18001B3F8;
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
0x180012f24  mov     [rsp+arg_18], rbx
0x180012f29  push    rbp
0x180012f2a  push    rsi
0x180012f2b  push    rdi
0x180012f2c  push    r14
0x180012f2e  push    r15
0x180012f30  sub     rsp, 250h
0x180012f37  mov     rax, cs:__security_cookie
0x180012f3e  xor     rax, rsp
0x180012f41  mov     [rsp+278h+var_38], rax
0x180012f49  xor     r15d, r15d
0x180012f4c  mov     rbx, r8
0x180012f4f  mov     rsi, rdx
0x180012f52  mov     r14, rcx
0x180012f55  test    rdx, rdx
0x180012f58  jz      loc_1800131B1
0x180012f5e  test    rcx, rcx
0x180012f61  jz      loc_1800131B1
0x180012f67  mov     rax, cs:g_pfnResultLoggingCallback
0x180012f6e  mov     [rcx], r15w
0x180012f72  test    rax, rax
0x180012f75  jz      short loc_180012F98
0x180012f77  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180012f7e  jz      short loc_180012F98
0x180012f80  mov     r8, rdx
0x180012f83  mov     rdx, rcx
0x180012f86  mov     rcx, rbx
0x180012f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f8e  cmp     [r14], r15w
0x180012f92  jnz     loc_1800131B1
0x180012f98  mov     ecx, [rbx]
0x180012f9a  mov     bpl, 8
0x180012f9d  test    ecx, ecx
0x180012f9f  jz      short loc_180012FEA
0x180012fa1  sub     ecx, 1
0x180012fa4  jz      short loc_180012FD2
0x180012fa6  sub     ecx, 1
0x180012fa9  jz      short loc_180012FC2
0x180012fab  cmp     ecx, 1
0x180012fae  jz      short loc_180012FB9
0x180012fb0  lea     rdi, qword_18001B3F8
0x180012fb7  jmp     short loc_180012FF1
0x180012fb9  lea     rdi, aFailfast; "FailFast"
0x180012fc0  jmp     short loc_180012FF1
0x180012fc2  lea     rax, aLoghr; "LogHr"
0x180012fc9  lea     rdi, aLognt; "LogNt"
0x180012fd0  jmp     short loc_180012FE0
0x180012fd2  lea     rax, aReturnhr; "ReturnHr"
0x180012fd9  lea     rdi, aReturnnt; "ReturnNt"
0x180012fe0  test    [rbx+4], bpl
0x180012fe4  cmovz   rdi, rax
0x180012fe8  jmp     short loc_180012FF1
0x180012fea  lea     rdi, aException; "Exception"
0x180012ff1  xor     edx, edx; Val
0x180012ff3  lea     rcx, [rsp+278h+Buffer]; void *
0x180012ff8  mov     r8d, 200h; Size
0x180012ffe  call    memset_0
0x180013003  test    [rbx+4], bpl
0x180013007  jz      short loc_18001302C
0x180013009  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180013010  mov     ebp, [rbx+0Ch]
0x180013013  test    rax, rax
0x180013016  jz      short loc_18001305C
0x180013018  mov     r8d, 100h
0x18001301e  lea     rdx, [rsp+278h+Buffer]
0x180013023  mov     ecx, ebp
0x180013025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001302a  jmp     short loc_18001305C
0x18001302c  mov     ebp, [rbx+8]
0x18001302f  lea     rax, [rsp+278h+Buffer]
0x180013034  mov     [rsp+278h+Arguments], r15; Arguments
0x180013039  mov     r8d, ebp; dwMessageId
0x18001303c  mov     [rsp+278h+nSize], 100h; nSize
0x180013044  mov     r9d, 400h; dwLanguageId
0x18001304a  xor     edx, edx; lpSource
0x18001304c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180013051  mov     ecx, 1200h; dwFlags
0x180013056  call    cs:__imp_FormatMessageW
0x18001305c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180013060  lea     rsi, [r14+rsi*2]
0x180013064  mov     rax, [rbx+88h]
0x18001306b  mov     rdx, rsi; unsigned __int16 *
0x18001306e  mov     rcx, [rbx+80h]
0x180013075  test    r9, r9
0x180013078  jz      short loc_18001309C
0x18001307a  mov     [rsp+278h+Arguments], rax
0x18001307f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180013086  mov     eax, [rbx+40h]
0x180013089  mov     qword ptr [rsp+278h+nSize], rcx
0x18001308e  mov     rcx, r14; this
0x180013091  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180013095  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001309a  jmp     short loc_1800130B3
0x18001309c  mov     r9, rcx; unsigned __int16 *
0x18001309f  mov     [rsp+278h+lpBuffer], rax
0x1800130a4  mov     rcx, r14; this
0x1800130a7  lea     r8, aHsP; "%hs!%p: "
0x1800130ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800130b3  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800130ba  mov     r14, rax
0x1800130bd  test    r9, r9
0x1800130c0  jz      short loc_1800130D7
0x1800130c2  lea     r8, aCallerP; "(caller: %p) "
0x1800130c9  mov     rdx, rsi; unsigned __int16 *
0x1800130cc  mov     rcx, rax; this
0x1800130cf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800130d4  mov     r14, rax
0x1800130d7  call    cs:__imp_GetCurrentThreadId
0x1800130dd  lea     rcx, [rsp+278h+Buffer]
0x1800130e2  mov     r9, rdi; unsigned __int16 *
0x1800130e5  mov     [rsp+278h+var_240], rcx
0x1800130ea  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800130f1  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800130f5  mov     rdx, rsi; unsigned __int16 *
0x1800130f8  mov     [rsp+278h+nSize], eax
0x1800130fc  mov     rcx, r14; this
0x1800130ff  mov     eax, [rbx+44h]
0x180013102  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180013106  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001310b  cmp     [rbx+18h], r15
0x18001310f  jnz     short loc_180013121
0x180013111  cmp     [rbx+48h], r15
0x180013115  jnz     short loc_180013121
0x180013117  cmp     [rbx+30h], r15
0x18001311b  jz      loc_1800131B1
0x180013121  lea     r8, asc_18001B0A8; "    "
0x180013128  mov     rdx, rsi; unsigned __int16 *
0x18001312b  mov     rcx, rax; this
0x18001312e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180013133  mov     r9, [rbx+18h]; unsigned __int16 *
0x180013137  test    r9, r9
0x18001313a  jz      short loc_18001314E
0x18001313c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180013143  mov     rdx, rsi; unsigned __int16 *
0x180013146  mov     rcx, rax; this
0x180013149  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001314e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180013152  test    r9, r9
0x180013155  jz      short loc_180013169
0x180013157  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001315e  mov     rdx, rsi; unsigned __int16 *
0x180013161  mov     rcx, rax; this
0x180013164  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180013169  mov     rcx, [rbx+28h]
0x18001316d  mov     rdx, rsi; unsigned __int16 *
0x180013170  mov     r9, [rbx+30h]; unsigned __int16 *
0x180013174  test    rcx, rcx
0x180013177  jz      short loc_18001318F
0x180013179  mov     [rsp+278h+lpBuffer], rcx
0x18001317e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180013185  mov     rcx, rax; this
0x180013188  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001318d  jmp     short loc_1800131B1
0x18001318f  mov     rcx, rax; this
0x180013192  test    r9, r9
0x180013195  jz      short loc_1800131A5
0x180013197  lea     r8, aHs; "[%hs]\n"
0x18001319e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800131a3  jmp     short loc_1800131B1
0x1800131a5  lea     r8, asc_18001B120; "\n"
0x1800131ac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800131b1  xor     eax, eax
0x1800131b3  mov     rcx, [rsp+278h+var_38]
0x1800131bb  xor     rcx, rsp; StackCookie
0x1800131be  call    __security_check_cookie
0x1800131c3  mov     rbx, [rsp+278h+arg_18]
0x1800131cb  add     rsp, 250h
0x1800131d2  pop     r15
0x1800131d4  pop     r14
0x1800131d6  pop     rdi
0x1800131d7  pop     rsi
0x1800131d8  pop     rbp
0x1800131d9  retn
```
