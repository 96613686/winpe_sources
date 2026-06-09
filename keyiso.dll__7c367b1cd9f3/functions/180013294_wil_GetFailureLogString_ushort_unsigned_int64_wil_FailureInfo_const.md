# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180013294`
- end: `0x18001354a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180013de4`
- `0x180016a10`

## callees

- `0x18000d0ac`
- `0x180013294`
- `0x1800140e0`
- `0x180018950`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013447`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013447`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800133c6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800133c6`

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
          v7 = (const char *)&word_1800205E6;
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
0x180013294  mov     [rsp+arg_18], rbx
0x180013299  push    rbp
0x18001329a  push    rsi
0x18001329b  push    rdi
0x18001329c  push    r14
0x18001329e  push    r15
0x1800132a0  sub     rsp, 250h
0x1800132a7  mov     rax, cs:__security_cookie
0x1800132ae  xor     rax, rsp
0x1800132b1  mov     [rsp+278h+var_38], rax
0x1800132b9  mov     rbx, r8
0x1800132bc  mov     rsi, rdx
0x1800132bf  mov     r14, rcx
0x1800132c2  xor     r15d, r15d
0x1800132c5  test    rdx, rdx
0x1800132c8  jz      loc_180013521
0x1800132ce  test    rcx, rcx
0x1800132d1  jz      loc_180013521
0x1800132d7  mov     [rcx], r15w
0x1800132db  mov     rax, cs:g_pfnResultLoggingCallback
0x1800132e2  test    rax, rax
0x1800132e5  jz      short loc_180013308
0x1800132e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800132ee  jz      short loc_180013308
0x1800132f0  mov     r8, rdx
0x1800132f3  mov     rdx, rcx
0x1800132f6  mov     rcx, rbx
0x1800132f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132fe  cmp     [r14], r15w
0x180013302  jnz     loc_180013521
0x180013308  mov     ecx, [rbx]
0x18001330a  mov     bpl, 8
0x18001330d  test    ecx, ecx
0x18001330f  jz      short loc_18001335A
0x180013311  sub     ecx, 1
0x180013314  jz      short loc_180013342
0x180013316  sub     ecx, 1
0x180013319  jz      short loc_180013332
0x18001331b  cmp     ecx, 1
0x18001331e  jz      short loc_180013329
0x180013320  lea     rdi, word_1800205E6
0x180013327  jmp     short loc_180013361
0x180013329  lea     rdi, aFailfast; "FailFast"
0x180013330  jmp     short loc_180013361
0x180013332  lea     rax, aLoghr; "LogHr"
0x180013339  lea     rdi, aLognt; "LogNt"
0x180013340  jmp     short loc_180013350
0x180013342  lea     rax, aReturnhr; "ReturnHr"
0x180013349  lea     rdi, aReturnnt; "ReturnNt"
0x180013350  test    [rbx+4], bpl
0x180013354  cmovz   rdi, rax
0x180013358  jmp     short loc_180013361
0x18001335a  lea     rdi, aException; "Exception"
0x180013361  xor     edx, edx; Val
0x180013363  mov     r8d, 200h; Size
0x180013369  lea     rcx, [rsp+278h+Buffer]; void *
0x18001336e  call    memset_0
0x180013373  test    [rbx+4], bpl
0x180013377  jz      short loc_18001339C
0x180013379  mov     ebp, [rbx+0Ch]
0x18001337c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180013383  test    rax, rax
0x180013386  jz      short loc_1800133CC
0x180013388  mov     r8d, 100h
0x18001338e  lea     rdx, [rsp+278h+Buffer]
0x180013393  mov     ecx, ebp
0x180013395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001339a  jmp     short loc_1800133CC
0x18001339c  mov     ebp, [rbx+8]
0x18001339f  mov     [rsp+278h+Arguments], r15; Arguments
0x1800133a4  mov     [rsp+278h+nSize], 100h; nSize
0x1800133ac  lea     rax, [rsp+278h+Buffer]
0x1800133b1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800133b6  mov     r9d, 400h; dwLanguageId
0x1800133bc  mov     r8d, ebp; dwMessageId
0x1800133bf  xor     edx, edx; lpSource
0x1800133c1  mov     ecx, 1200h; dwFlags
0x1800133c6  call    cs:__imp_FormatMessageW
0x1800133cc  lea     rsi, [r14+rsi*2]
0x1800133d0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800133d4  mov     rax, [rbx+88h]
0x1800133db  mov     rcx, [rbx+80h]
0x1800133e2  mov     rdx, rsi; unsigned __int16 *
0x1800133e5  test    r9, r9
0x1800133e8  jz      short loc_18001340C
0x1800133ea  mov     [rsp+278h+Arguments], rax
0x1800133ef  mov     qword ptr [rsp+278h+nSize], rcx
0x1800133f4  mov     eax, [rbx+40h]
0x1800133f7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800133fb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180013402  mov     rcx, r14; this
0x180013405  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001340a  jmp     short loc_180013423
0x18001340c  mov     [rsp+278h+lpBuffer], rax
0x180013411  mov     r9, rcx; unsigned __int16 *
0x180013414  lea     r8, aHsP; "%hs!%p: "
0x18001341b  mov     rcx, r14; this
0x18001341e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180013423  mov     r14, rax
0x180013426  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001342d  test    r9, r9
0x180013430  jz      short loc_180013447
0x180013432  lea     r8, aCallerP; "(caller: %p) "
0x180013439  mov     rdx, rsi; unsigned __int16 *
0x18001343c  mov     rcx, rax; this
0x18001343f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180013444  mov     r14, rax
0x180013447  call    cs:__imp_GetCurrentThreadId
0x18001344d  lea     rcx, [rsp+278h+Buffer]
0x180013452  mov     [rsp+278h+var_240], rcx
0x180013457  mov     dword ptr [rsp+278h+Arguments], ebp
0x18001345b  mov     [rsp+278h+nSize], eax
0x18001345f  mov     eax, [rbx+44h]
0x180013462  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180013466  mov     r9, rdi; unsigned __int16 *
0x180013469  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180013470  mov     rdx, rsi; unsigned __int16 *
0x180013473  mov     rcx, r14; this
0x180013476  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001347b  cmp     [rbx+18h], r15
0x18001347f  jnz     short loc_180013491
0x180013481  cmp     [rbx+48h], r15
0x180013485  jnz     short loc_180013491
0x180013487  cmp     [rbx+30h], r15
0x18001348b  jz      loc_180013521
0x180013491  lea     r8, asc_1800206E8; "    "
0x180013498  mov     rdx, rsi; unsigned __int16 *
0x18001349b  mov     rcx, rax; this
0x18001349e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800134a3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800134a7  test    r9, r9
0x1800134aa  jz      short loc_1800134BE
0x1800134ac  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800134b3  mov     rdx, rsi; unsigned __int16 *
0x1800134b6  mov     rcx, rax; this
0x1800134b9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800134be  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800134c2  test    r9, r9
0x1800134c5  jz      short loc_1800134D9
0x1800134c7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800134ce  mov     rdx, rsi; unsigned __int16 *
0x1800134d1  mov     rcx, rax; this
0x1800134d4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800134d9  mov     rcx, [rbx+28h]
0x1800134dd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800134e1  mov     rdx, rsi; unsigned __int16 *
0x1800134e4  test    rcx, rcx
0x1800134e7  jz      short loc_1800134FF
0x1800134e9  mov     [rsp+278h+lpBuffer], rcx
0x1800134ee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800134f5  mov     rcx, rax; this
0x1800134f8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800134fd  jmp     short loc_180013521
0x1800134ff  mov     rcx, rax; this
0x180013502  test    r9, r9
0x180013505  jz      short loc_180013515
0x180013507  lea     r8, aHs; "[%hs]\n"
0x18001350e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180013513  jmp     short loc_180013521
0x180013515  lea     r8, asc_180020760; "\n"
0x18001351c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180013521  xor     eax, eax
0x180013523  mov     rcx, [rsp+278h+var_38]
0x18001352b  xor     rcx, rsp; StackCookie
0x18001352e  call    __security_check_cookie
0x180013533  mov     rbx, [rsp+278h+arg_18]
0x18001353b  add     rsp, 250h
0x180013542  pop     r15
0x180013544  pop     r14
0x180013546  pop     rdi
0x180013547  pop     rsi
0x180013548  pop     rbp
0x180013549  retn
```
