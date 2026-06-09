# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180012f34`
- end: `0x1800131ea`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180013b30`

## callees

- `0x18000f970`
- `0x1800103e8`
- `0x180012f34`
- `0x180013e2c`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800130e7`
- `KERNEL32!GetCurrentThreadId` at `0x1800130e7`
- `KERNEL32!FormatMessageW` at `0x180013066`
- `KERNEL32!FormatMessageW` at `0x180013066`

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
          v8 = (const char *)&qword_180029548;
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
0x180012f34  mov     [rsp+arg_18], rbx
0x180012f39  push    rbp
0x180012f3a  push    rsi
0x180012f3b  push    rdi
0x180012f3c  push    r14
0x180012f3e  push    r15
0x180012f40  sub     rsp, 250h
0x180012f47  mov     rax, cs:__security_cookie
0x180012f4e  xor     rax, rsp
0x180012f51  mov     [rsp+278h+var_38], rax
0x180012f59  xor     r15d, r15d
0x180012f5c  mov     rbx, r8
0x180012f5f  mov     rsi, rdx
0x180012f62  mov     r14, rcx
0x180012f65  test    rdx, rdx
0x180012f68  jz      loc_1800131C1
0x180012f6e  test    rcx, rcx
0x180012f71  jz      loc_1800131C1
0x180012f77  mov     rax, cs:g_pfnResultLoggingCallback
0x180012f7e  mov     [rcx], r15w
0x180012f82  test    rax, rax
0x180012f85  jz      short loc_180012FA8
0x180012f87  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180012f8e  jz      short loc_180012FA8
0x180012f90  mov     r8, rdx
0x180012f93  mov     rdx, rcx
0x180012f96  mov     rcx, rbx
0x180012f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f9e  cmp     [r14], r15w
0x180012fa2  jnz     loc_1800131C1
0x180012fa8  mov     ecx, [rbx]
0x180012faa  mov     bpl, 8
0x180012fad  test    ecx, ecx
0x180012faf  jz      short loc_180012FFA
0x180012fb1  sub     ecx, 1
0x180012fb4  jz      short loc_180012FE2
0x180012fb6  sub     ecx, 1
0x180012fb9  jz      short loc_180012FD2
0x180012fbb  cmp     ecx, 1
0x180012fbe  jz      short loc_180012FC9
0x180012fc0  lea     rdi, qword_180029548
0x180012fc7  jmp     short loc_180013001
0x180012fc9  lea     rdi, aFailfast; "FailFast"
0x180012fd0  jmp     short loc_180013001
0x180012fd2  lea     rax, aLoghr; "LogHr"
0x180012fd9  lea     rdi, aLognt; "LogNt"
0x180012fe0  jmp     short loc_180012FF0
0x180012fe2  lea     rax, aReturnhr; "ReturnHr"
0x180012fe9  lea     rdi, aReturnnt; "ReturnNt"
0x180012ff0  test    [rbx+4], bpl
0x180012ff4  cmovz   rdi, rax
0x180012ff8  jmp     short loc_180013001
0x180012ffa  lea     rdi, aException; "Exception"
0x180013001  xor     edx, edx; Val
0x180013003  lea     rcx, [rsp+278h+Buffer]; void *
0x180013008  mov     r8d, 200h; Size
0x18001300e  call    memset_0
0x180013013  test    [rbx+4], bpl
0x180013017  jz      short loc_18001303C
0x180013019  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180013020  mov     ebp, [rbx+0Ch]
0x180013023  test    rax, rax
0x180013026  jz      short loc_18001306C
0x180013028  mov     r8d, 100h
0x18001302e  lea     rdx, [rsp+278h+Buffer]
0x180013033  mov     ecx, ebp
0x180013035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001303a  jmp     short loc_18001306C
0x18001303c  mov     ebp, [rbx+8]
0x18001303f  lea     rax, [rsp+278h+Buffer]
0x180013044  mov     [rsp+278h+Arguments], r15; Arguments
0x180013049  mov     r8d, ebp; dwMessageId
0x18001304c  mov     [rsp+278h+nSize], 100h; nSize
0x180013054  mov     r9d, 400h; dwLanguageId
0x18001305a  xor     edx, edx; lpSource
0x18001305c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180013061  mov     ecx, 1200h; dwFlags
0x180013066  call    cs:__imp_FormatMessageW
0x18001306c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180013070  lea     rsi, [r14+rsi*2]
0x180013074  mov     rax, [rbx+88h]
0x18001307b  mov     rdx, rsi; unsigned __int16 *
0x18001307e  mov     rcx, [rbx+80h]
0x180013085  test    r9, r9
0x180013088  jz      short loc_1800130AC
0x18001308a  mov     [rsp+278h+Arguments], rax
0x18001308f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180013096  mov     eax, [rbx+40h]
0x180013099  mov     qword ptr [rsp+278h+nSize], rcx
0x18001309e  mov     rcx, r14; this
0x1800130a1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800130a5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800130aa  jmp     short loc_1800130C3
0x1800130ac  mov     r9, rcx; unsigned __int16 *
0x1800130af  mov     [rsp+278h+lpBuffer], rax
0x1800130b4  mov     rcx, r14; this
0x1800130b7  lea     r8, aHsP; "%hs!%p: "
0x1800130be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800130c3  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800130ca  mov     r14, rax
0x1800130cd  test    r9, r9
0x1800130d0  jz      short loc_1800130E7
0x1800130d2  lea     r8, aCallerP; "(caller: %p) "
0x1800130d9  mov     rdx, rsi; unsigned __int16 *
0x1800130dc  mov     rcx, rax; this
0x1800130df  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800130e4  mov     r14, rax
0x1800130e7  call    cs:__imp_GetCurrentThreadId
0x1800130ed  lea     rcx, [rsp+278h+Buffer]
0x1800130f2  mov     r9, rdi; unsigned __int16 *
0x1800130f5  mov     [rsp+278h+var_240], rcx
0x1800130fa  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180013101  mov     dword ptr [rsp+278h+Arguments], ebp
0x180013105  mov     rdx, rsi; unsigned __int16 *
0x180013108  mov     [rsp+278h+nSize], eax
0x18001310c  mov     rcx, r14; this
0x18001310f  mov     eax, [rbx+44h]
0x180013112  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180013116  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001311b  cmp     [rbx+18h], r15
0x18001311f  jnz     short loc_180013131
0x180013121  cmp     [rbx+48h], r15
0x180013125  jnz     short loc_180013131
0x180013127  cmp     [rbx+30h], r15
0x18001312b  jz      loc_1800131C1
0x180013131  lea     r8, asc_180027958; "    "
0x180013138  mov     rdx, rsi; unsigned __int16 *
0x18001313b  mov     rcx, rax; this
0x18001313e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180013143  mov     r9, [rbx+18h]; unsigned __int16 *
0x180013147  test    r9, r9
0x18001314a  jz      short loc_18001315E
0x18001314c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180013153  mov     rdx, rsi; unsigned __int16 *
0x180013156  mov     rcx, rax; this
0x180013159  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001315e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180013162  test    r9, r9
0x180013165  jz      short loc_180013179
0x180013167  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001316e  mov     rdx, rsi; unsigned __int16 *
0x180013171  mov     rcx, rax; this
0x180013174  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180013179  mov     rcx, [rbx+28h]
0x18001317d  mov     rdx, rsi; unsigned __int16 *
0x180013180  mov     r9, [rbx+30h]; unsigned __int16 *
0x180013184  test    rcx, rcx
0x180013187  jz      short loc_18001319F
0x180013189  mov     [rsp+278h+lpBuffer], rcx
0x18001318e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180013195  mov     rcx, rax; this
0x180013198  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001319d  jmp     short loc_1800131C1
0x18001319f  mov     rcx, rax; this
0x1800131a2  test    r9, r9
0x1800131a5  jz      short loc_1800131B5
0x1800131a7  lea     r8, aHs; "[%hs]\n"
0x1800131ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800131b3  jmp     short loc_1800131C1
0x1800131b5  lea     r8, asc_1800279D0; "\n"
0x1800131bc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800131c1  xor     eax, eax
0x1800131c3  mov     rcx, [rsp+278h+var_38]
0x1800131cb  xor     rcx, rsp; StackCookie
0x1800131ce  call    __security_check_cookie
0x1800131d3  mov     rbx, [rsp+278h+arg_18]
0x1800131db  add     rsp, 250h
0x1800131e2  pop     r15
0x1800131e4  pop     r14
0x1800131e6  pop     rdi
0x1800131e7  pop     rsi
0x1800131e8  pop     rbp
0x1800131e9  retn
```
