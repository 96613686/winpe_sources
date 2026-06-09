# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800083c4`
- end: `0x180008687`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x180004e40`
- `0x1800050d4`
- `0x180008f64`
- `0x18000d040`
- `0x18004bbcc`
- `0x18004bd00`

## callees

- `0x1800026d0`
- `0x1800031a0`
- `0x1800083c4`
- `0x180009278`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000857d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000857d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800084f6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800084f6`

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
          v7 = (const char *)&word_1800504C6;
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
0x1800083c4  mov     [rsp+arg_18], rbx
0x1800083c9  push    rbp
0x1800083ca  push    rsi
0x1800083cb  push    rdi
0x1800083cc  push    r14
0x1800083ce  push    r15
0x1800083d0  sub     rsp, 250h
0x1800083d7  mov     rax, cs:__security_cookie
0x1800083de  xor     rax, rsp
0x1800083e1  mov     [rsp+278h+var_38], rax
0x1800083e9  mov     rbx, r8
0x1800083ec  mov     rsi, rdx
0x1800083ef  mov     r14, rcx
0x1800083f2  xor     r15d, r15d
0x1800083f5  test    rdx, rdx
0x1800083f8  jz      loc_18000865D
0x1800083fe  test    rcx, rcx
0x180008401  jz      loc_18000865D
0x180008407  mov     [rcx], r15w
0x18000840b  mov     rax, cs:g_pfnResultLoggingCallback
0x180008412  test    rax, rax
0x180008415  jz      short loc_180008438
0x180008417  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000841e  jz      short loc_180008438
0x180008420  mov     r8, rdx
0x180008423  mov     rdx, rcx
0x180008426  mov     rcx, rbx
0x180008429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000842e  cmp     [r14], r15w
0x180008432  jnz     loc_18000865D
0x180008438  mov     ecx, [rbx]
0x18000843a  mov     bpl, 8
0x18000843d  test    ecx, ecx
0x18000843f  jz      short loc_18000848A
0x180008441  sub     ecx, 1
0x180008444  jz      short loc_180008472
0x180008446  sub     ecx, 1
0x180008449  jz      short loc_180008462
0x18000844b  cmp     ecx, 1
0x18000844e  jz      short loc_180008459
0x180008450  lea     rdi, word_1800504C6
0x180008457  jmp     short loc_180008491
0x180008459  lea     rdi, aFailfast; "FailFast"
0x180008460  jmp     short loc_180008491
0x180008462  lea     rax, aLoghr; "LogHr"
0x180008469  lea     rdi, aLognt; "LogNt"
0x180008470  jmp     short loc_180008480
0x180008472  lea     rax, aReturnhr; "ReturnHr"
0x180008479  lea     rdi, aReturnnt; "ReturnNt"
0x180008480  test    [rbx+4], bpl
0x180008484  cmovz   rdi, rax
0x180008488  jmp     short loc_180008491
0x18000848a  lea     rdi, aException; "Exception"
0x180008491  xor     edx, edx; Val
0x180008493  mov     r8d, 200h; Size
0x180008499  lea     rcx, [rsp+278h+Buffer]; void *
0x18000849e  call    memset_0
0x1800084a3  test    [rbx+4], bpl
0x1800084a7  jz      short loc_1800084CC
0x1800084a9  mov     ebp, [rbx+0Ch]
0x1800084ac  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800084b3  test    rax, rax
0x1800084b6  jz      short loc_180008502
0x1800084b8  mov     r8d, 100h
0x1800084be  lea     rdx, [rsp+278h+Buffer]
0x1800084c3  mov     ecx, ebp
0x1800084c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084ca  jmp     short loc_180008502
0x1800084cc  mov     ebp, [rbx+8]
0x1800084cf  mov     [rsp+278h+Arguments], r15; Arguments
0x1800084d4  mov     [rsp+278h+nSize], 100h; nSize
0x1800084dc  lea     rax, [rsp+278h+Buffer]
0x1800084e1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800084e6  mov     r9d, 400h; dwLanguageId
0x1800084ec  mov     r8d, ebp; dwMessageId
0x1800084ef  xor     edx, edx; lpSource
0x1800084f1  mov     ecx, 1200h; dwFlags
0x1800084f6  call    cs:__imp_FormatMessageW
0x1800084fd  nop     dword ptr [rax+rax+00h]
0x180008502  lea     rsi, [r14+rsi*2]
0x180008506  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000850a  mov     rax, [rbx+88h]
0x180008511  mov     rcx, [rbx+80h]
0x180008518  mov     rdx, rsi; unsigned __int16 *
0x18000851b  test    r9, r9
0x18000851e  jz      short loc_180008542
0x180008520  mov     [rsp+278h+Arguments], rax
0x180008525  mov     qword ptr [rsp+278h+nSize], rcx
0x18000852a  mov     eax, [rbx+40h]
0x18000852d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180008531  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180008538  mov     rcx, r14; this
0x18000853b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008540  jmp     short loc_180008559
0x180008542  mov     [rsp+278h+lpBuffer], rax
0x180008547  mov     r9, rcx; unsigned __int16 *
0x18000854a  lea     r8, aHsP; "%hs!%p: "
0x180008551  mov     rcx, r14; this
0x180008554  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008559  mov     r14, rax
0x18000855c  mov     r9, [rbx+90h]; unsigned __int16 *
0x180008563  test    r9, r9
0x180008566  jz      short loc_18000857D
0x180008568  lea     r8, aCallerP; "(caller: %p) "
0x18000856f  mov     rdx, rsi; unsigned __int16 *
0x180008572  mov     rcx, rax; this
0x180008575  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000857a  mov     r14, rax
0x18000857d  call    cs:__imp_GetCurrentThreadId
0x180008584  nop     dword ptr [rax+rax+00h]
0x180008589  lea     rcx, [rsp+278h+Buffer]
0x18000858e  mov     [rsp+278h+var_240], rcx
0x180008593  mov     dword ptr [rsp+278h+Arguments], ebp
0x180008597  mov     [rsp+278h+nSize], eax
0x18000859b  mov     eax, [rbx+44h]
0x18000859e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800085a2  mov     r9, rdi; unsigned __int16 *
0x1800085a5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800085ac  mov     rdx, rsi; unsigned __int16 *
0x1800085af  mov     rcx, r14; this
0x1800085b2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800085b7  cmp     [rbx+18h], r15
0x1800085bb  jnz     short loc_1800085CD
0x1800085bd  cmp     [rbx+48h], r15
0x1800085c1  jnz     short loc_1800085CD
0x1800085c3  cmp     [rbx+30h], r15
0x1800085c7  jz      loc_18000865D
0x1800085cd  lea     r8, asc_1800505C8; "    "
0x1800085d4  mov     rdx, rsi; unsigned __int16 *
0x1800085d7  mov     rcx, rax; this
0x1800085da  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800085df  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800085e3  test    r9, r9
0x1800085e6  jz      short loc_1800085FA
0x1800085e8  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800085ef  mov     rdx, rsi; unsigned __int16 *
0x1800085f2  mov     rcx, rax; this
0x1800085f5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800085fa  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800085fe  test    r9, r9
0x180008601  jz      short loc_180008615
0x180008603  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000860a  mov     rdx, rsi; unsigned __int16 *
0x18000860d  mov     rcx, rax; this
0x180008610  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008615  mov     rcx, [rbx+28h]
0x180008619  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000861d  mov     rdx, rsi; unsigned __int16 *
0x180008620  test    rcx, rcx
0x180008623  jz      short loc_18000863B
0x180008625  mov     [rsp+278h+lpBuffer], rcx
0x18000862a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180008631  mov     rcx, rax; this
0x180008634  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008639  jmp     short loc_18000865D
0x18000863b  mov     rcx, rax; this
0x18000863e  test    r9, r9
0x180008641  jz      short loc_180008651
0x180008643  lea     r8, aHs; "[%hs]\n"
0x18000864a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000864f  jmp     short loc_18000865D
0x180008651  lea     r8, asc_180050640; "\n"
0x180008658  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000865d  xor     eax, eax
0x18000865f  mov     rcx, [rsp+278h+var_38]
0x180008667  xor     rcx, rsp; StackCookie
0x18000866a  call    __security_check_cookie
0x18000866f  mov     rbx, [rsp+278h+arg_18]
0x180008677  add     rsp, 250h
0x18000867e  pop     r15
0x180008680  pop     r14
0x180008682  pop     rdi
0x180008683  pop     rsi
0x180008684  pop     rbp
0x180008685  retn
```
