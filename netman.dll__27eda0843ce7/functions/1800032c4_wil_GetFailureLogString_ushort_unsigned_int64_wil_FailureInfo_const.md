# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800032c4`
- end: `0x18000357a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180003f90`
- `0x180005aa8`
- `0x180005d10`
- `0x180011b90`

## callees

- `0x180001710`
- `0x180002320`
- `0x1800032c4`
- `0x180003870`
- `0x180036010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x1800033f6`
- `KERNEL32!FormatMessageW` at `0x1800033f6`
- `KERNEL32!GetCurrentThreadId` at `0x180003477`
- `KERNEL32!GetCurrentThreadId` at `0x180003477`

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
          v7 = (const char *)&word_18003AB3A;
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
0x1800032c4  mov     [rsp+arg_18], rbx
0x1800032c9  push    rbp
0x1800032ca  push    rsi
0x1800032cb  push    rdi
0x1800032cc  push    r14
0x1800032ce  push    r15
0x1800032d0  sub     rsp, 250h
0x1800032d7  mov     rax, cs:__security_cookie
0x1800032de  xor     rax, rsp
0x1800032e1  mov     [rsp+278h+var_38], rax
0x1800032e9  mov     rbx, r8
0x1800032ec  mov     rsi, rdx
0x1800032ef  mov     r14, rcx
0x1800032f2  xor     r15d, r15d
0x1800032f5  test    rdx, rdx
0x1800032f8  jz      loc_180003551
0x1800032fe  test    rcx, rcx
0x180003301  jz      loc_180003551
0x180003307  mov     [rcx], r15w
0x18000330b  mov     rax, cs:g_pfnResultLoggingCallback
0x180003312  test    rax, rax
0x180003315  jz      short loc_180003338
0x180003317  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000331e  jz      short loc_180003338
0x180003320  mov     r8, rdx
0x180003323  mov     rdx, rcx
0x180003326  mov     rcx, rbx
0x180003329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000332e  cmp     [r14], r15w
0x180003332  jnz     loc_180003551
0x180003338  mov     ecx, [rbx]
0x18000333a  mov     bpl, 8
0x18000333d  test    ecx, ecx
0x18000333f  jz      short loc_18000338A
0x180003341  sub     ecx, 1
0x180003344  jz      short loc_180003372
0x180003346  sub     ecx, 1
0x180003349  jz      short loc_180003362
0x18000334b  cmp     ecx, 1
0x18000334e  jz      short loc_180003359
0x180003350  lea     rdi, word_18003AB3A
0x180003357  jmp     short loc_180003391
0x180003359  lea     rdi, aFailfast; "FailFast"
0x180003360  jmp     short loc_180003391
0x180003362  lea     rax, aLoghr; "LogHr"
0x180003369  lea     rdi, aLognt; "LogNt"
0x180003370  jmp     short loc_180003380
0x180003372  lea     rax, aReturnhr; "ReturnHr"
0x180003379  lea     rdi, aReturnnt; "ReturnNt"
0x180003380  test    [rbx+4], bpl
0x180003384  cmovz   rdi, rax
0x180003388  jmp     short loc_180003391
0x18000338a  lea     rdi, aException; "Exception"
0x180003391  xor     edx, edx; Val
0x180003393  mov     r8d, 200h; Size
0x180003399  lea     rcx, [rsp+278h+Buffer]; void *
0x18000339e  call    memset_0
0x1800033a3  test    [rbx+4], bpl
0x1800033a7  jz      short loc_1800033CC
0x1800033a9  mov     ebp, [rbx+0Ch]
0x1800033ac  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800033b3  test    rax, rax
0x1800033b6  jz      short loc_1800033FC
0x1800033b8  mov     r8d, 100h
0x1800033be  lea     rdx, [rsp+278h+Buffer]
0x1800033c3  mov     ecx, ebp
0x1800033c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033ca  jmp     short loc_1800033FC
0x1800033cc  mov     ebp, [rbx+8]
0x1800033cf  mov     [rsp+278h+Arguments], r15; Arguments
0x1800033d4  mov     [rsp+278h+nSize], 100h; nSize
0x1800033dc  lea     rax, [rsp+278h+Buffer]
0x1800033e1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800033e6  mov     r9d, 400h; dwLanguageId
0x1800033ec  mov     r8d, ebp; dwMessageId
0x1800033ef  xor     edx, edx; lpSource
0x1800033f1  mov     ecx, 1200h; dwFlags
0x1800033f6  call    cs:__imp_FormatMessageW
0x1800033fc  lea     rsi, [r14+rsi*2]
0x180003400  mov     r9, [rbx+38h]; unsigned __int16 *
0x180003404  mov     rax, [rbx+88h]
0x18000340b  mov     rcx, [rbx+80h]
0x180003412  mov     rdx, rsi; unsigned __int16 *
0x180003415  test    r9, r9
0x180003418  jz      short loc_18000343C
0x18000341a  mov     [rsp+278h+Arguments], rax
0x18000341f  mov     qword ptr [rsp+278h+nSize], rcx
0x180003424  mov     eax, [rbx+40h]
0x180003427  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000342b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180003432  mov     rcx, r14; this
0x180003435  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000343a  jmp     short loc_180003453
0x18000343c  mov     [rsp+278h+lpBuffer], rax
0x180003441  mov     r9, rcx; unsigned __int16 *
0x180003444  lea     r8, aHsP; "%hs!%p: "
0x18000344b  mov     rcx, r14; this
0x18000344e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003453  mov     r14, rax
0x180003456  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000345d  test    r9, r9
0x180003460  jz      short loc_180003477
0x180003462  lea     r8, aCallerP; "(caller: %p) "
0x180003469  mov     rdx, rsi; unsigned __int16 *
0x18000346c  mov     rcx, rax; this
0x18000346f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003474  mov     r14, rax
0x180003477  call    cs:__imp_GetCurrentThreadId
0x18000347d  lea     rcx, [rsp+278h+Buffer]
0x180003482  mov     [rsp+278h+var_240], rcx
0x180003487  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000348b  mov     [rsp+278h+nSize], eax
0x18000348f  mov     eax, [rbx+44h]
0x180003492  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003496  mov     r9, rdi; unsigned __int16 *
0x180003499  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800034a0  mov     rdx, rsi; unsigned __int16 *
0x1800034a3  mov     rcx, r14; this
0x1800034a6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800034ab  cmp     [rbx+18h], r15
0x1800034af  jnz     short loc_1800034C1
0x1800034b1  cmp     [rbx+48h], r15
0x1800034b5  jnz     short loc_1800034C1
0x1800034b7  cmp     [rbx+30h], r15
0x1800034bb  jz      loc_180003551
0x1800034c1  lea     r8, asc_18003AC28; "    "
0x1800034c8  mov     rdx, rsi; unsigned __int16 *
0x1800034cb  mov     rcx, rax; this
0x1800034ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800034d3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800034d7  test    r9, r9
0x1800034da  jz      short loc_1800034EE
0x1800034dc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800034e3  mov     rdx, rsi; unsigned __int16 *
0x1800034e6  mov     rcx, rax; this
0x1800034e9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800034ee  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800034f2  test    r9, r9
0x1800034f5  jz      short loc_180003509
0x1800034f7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800034fe  mov     rdx, rsi; unsigned __int16 *
0x180003501  mov     rcx, rax; this
0x180003504  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003509  mov     rcx, [rbx+28h]
0x18000350d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180003511  mov     rdx, rsi; unsigned __int16 *
0x180003514  test    rcx, rcx
0x180003517  jz      short loc_18000352F
0x180003519  mov     [rsp+278h+lpBuffer], rcx
0x18000351e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180003525  mov     rcx, rax; this
0x180003528  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000352d  jmp     short loc_180003551
0x18000352f  mov     rcx, rax; this
0x180003532  test    r9, r9
0x180003535  jz      short loc_180003545
0x180003537  lea     r8, aHs; "[%hs]\n"
0x18000353e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003543  jmp     short loc_180003551
0x180003545  lea     r8, asc_18003ACA0; "\n"
0x18000354c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003551  xor     eax, eax
0x180003553  mov     rcx, [rsp+278h+var_38]
0x18000355b  xor     rcx, rsp; StackCookie
0x18000355e  call    __security_check_cookie
0x180003563  mov     rbx, [rsp+278h+arg_18]
0x18000356b  add     rsp, 250h
0x180003572  pop     r15
0x180003574  pop     r14
0x180003576  pop     rdi
0x180003577  pop     rsi
0x180003578  pop     rbp
0x180003579  retn
```
