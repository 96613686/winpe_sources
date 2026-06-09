# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140005204`
- end: `0x1400054ba`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x1400027b4`
- `0x140002a34`
- `0x140002ce8`
- `0x140006df0`
- `0x140009230`
- `0x14000e51b`
- `0x14000e64f`

## callees

- `0x140001ebf`
- `0x140005204`
- `0x1400070f0`
- `0x14000ded0`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400053b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400053b7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140005336`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140005336`

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
      g_pfnResultLoggingCallback(a3, this, a2, a4);
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
          v7 = (const char *)&qword_140011E70;
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
0x140005204  mov     [rsp+arg_18], rbx
0x140005209  push    rbp
0x14000520a  push    rsi
0x14000520b  push    rdi
0x14000520c  push    r14
0x14000520e  push    r15
0x140005210  sub     rsp, 250h
0x140005217  mov     rax, cs:__security_cookie
0x14000521e  xor     rax, rsp
0x140005221  mov     [rsp+278h+var_38], rax
0x140005229  mov     rbx, r8
0x14000522c  mov     rsi, rdx
0x14000522f  mov     r14, rcx
0x140005232  xor     r15d, r15d
0x140005235  test    rdx, rdx
0x140005238  jz      loc_140005491
0x14000523e  test    rcx, rcx
0x140005241  jz      loc_140005491
0x140005247  mov     [rcx], r15w
0x14000524b  mov     rax, cs:g_pfnResultLoggingCallback
0x140005252  test    rax, rax
0x140005255  jz      short loc_140005278
0x140005257  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000525e  jz      short loc_140005278
0x140005260  mov     r8, rdx
0x140005263  mov     rdx, rcx
0x140005266  mov     rcx, rbx
0x140005269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000526e  cmp     [r14], r15w
0x140005272  jnz     loc_140005491
0x140005278  mov     ecx, [rbx]
0x14000527a  mov     bpl, 8
0x14000527d  test    ecx, ecx
0x14000527f  jz      short loc_1400052CA
0x140005281  sub     ecx, 1
0x140005284  jz      short loc_1400052B2
0x140005286  sub     ecx, 1
0x140005289  jz      short loc_1400052A2
0x14000528b  cmp     ecx, 1
0x14000528e  jz      short loc_140005299
0x140005290  lea     rdi, qword_140011E70
0x140005297  jmp     short loc_1400052D1
0x140005299  lea     rdi, aFailfast; "FailFast"
0x1400052a0  jmp     short loc_1400052D1
0x1400052a2  lea     rax, aLoghr; "LogHr"
0x1400052a9  lea     rdi, aLognt; "LogNt"
0x1400052b0  jmp     short loc_1400052C0
0x1400052b2  lea     rax, aReturnhr; "ReturnHr"
0x1400052b9  lea     rdi, aReturnnt; "ReturnNt"
0x1400052c0  test    [rbx+4], bpl
0x1400052c4  cmovz   rdi, rax
0x1400052c8  jmp     short loc_1400052D1
0x1400052ca  lea     rdi, aException; "Exception"
0x1400052d1  xor     edx, edx; Val
0x1400052d3  mov     r8d, 200h; Size
0x1400052d9  lea     rcx, [rsp+278h+Buffer]; void *
0x1400052de  call    memset_0
0x1400052e3  test    [rbx+4], bpl
0x1400052e7  jz      short loc_14000530C
0x1400052e9  mov     ebp, [rbx+0Ch]
0x1400052ec  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1400052f3  test    rax, rax
0x1400052f6  jz      short loc_14000533C
0x1400052f8  mov     r8d, 100h
0x1400052fe  lea     rdx, [rsp+278h+Buffer]
0x140005303  mov     ecx, ebp
0x140005305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000530a  jmp     short loc_14000533C
0x14000530c  mov     ebp, [rbx+8]
0x14000530f  mov     [rsp+278h+Arguments], r15; Arguments
0x140005314  mov     [rsp+278h+nSize], 100h; nSize
0x14000531c  lea     rax, [rsp+278h+Buffer]
0x140005321  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140005326  mov     r9d, 400h; dwLanguageId
0x14000532c  mov     r8d, ebp; dwMessageId
0x14000532f  xor     edx, edx; lpSource
0x140005331  mov     ecx, 1200h; dwFlags
0x140005336  call    cs:__imp_FormatMessageW
0x14000533c  lea     rsi, [r14+rsi*2]
0x140005340  mov     r9, [rbx+38h]; unsigned __int16 *
0x140005344  mov     rax, [rbx+88h]
0x14000534b  mov     rcx, [rbx+80h]
0x140005352  mov     rdx, rsi; unsigned __int16 *
0x140005355  test    r9, r9
0x140005358  jz      short loc_14000537C
0x14000535a  mov     [rsp+278h+Arguments], rax
0x14000535f  mov     qword ptr [rsp+278h+nSize], rcx
0x140005364  mov     eax, [rbx+40h]
0x140005367  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000536b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140005372  mov     rcx, r14; this
0x140005375  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000537a  jmp     short loc_140005393
0x14000537c  mov     [rsp+278h+lpBuffer], rax
0x140005381  mov     r9, rcx; unsigned __int16 *
0x140005384  lea     r8, aHsP; "%hs!%p: "
0x14000538b  mov     rcx, r14; this
0x14000538e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005393  mov     r14, rax
0x140005396  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000539d  test    r9, r9
0x1400053a0  jz      short loc_1400053B7
0x1400053a2  lea     r8, aCallerP; "(caller: %p) "
0x1400053a9  mov     rdx, rsi; unsigned __int16 *
0x1400053ac  mov     rcx, rax; this
0x1400053af  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400053b4  mov     r14, rax
0x1400053b7  call    cs:__imp_GetCurrentThreadId
0x1400053bd  lea     rcx, [rsp+278h+Buffer]
0x1400053c2  mov     [rsp+278h+var_240], rcx
0x1400053c7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1400053cb  mov     [rsp+278h+nSize], eax
0x1400053cf  mov     eax, [rbx+44h]
0x1400053d2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400053d6  mov     r9, rdi; unsigned __int16 *
0x1400053d9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1400053e0  mov     rdx, rsi; unsigned __int16 *
0x1400053e3  mov     rcx, r14; this
0x1400053e6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400053eb  cmp     [rbx+18h], r15
0x1400053ef  jnz     short loc_140005401
0x1400053f1  cmp     [rbx+48h], r15
0x1400053f5  jnz     short loc_140005401
0x1400053f7  cmp     [rbx+30h], r15
0x1400053fb  jz      loc_140005491
0x140005401  lea     r8, asc_140011FB0; "    "
0x140005408  mov     rdx, rsi; unsigned __int16 *
0x14000540b  mov     rcx, rax; this
0x14000540e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005413  mov     r9, [rbx+18h]; unsigned __int16 *
0x140005417  test    r9, r9
0x14000541a  jz      short loc_14000542E
0x14000541c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140005423  mov     rdx, rsi; unsigned __int16 *
0x140005426  mov     rcx, rax; this
0x140005429  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000542e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140005432  test    r9, r9
0x140005435  jz      short loc_140005449
0x140005437  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000543e  mov     rdx, rsi; unsigned __int16 *
0x140005441  mov     rcx, rax; this
0x140005444  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005449  mov     rcx, [rbx+28h]
0x14000544d  mov     r9, [rbx+30h]; unsigned __int16 *
0x140005451  mov     rdx, rsi; unsigned __int16 *
0x140005454  test    rcx, rcx
0x140005457  jz      short loc_14000546F
0x140005459  mov     [rsp+278h+lpBuffer], rcx
0x14000545e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140005465  mov     rcx, rax; this
0x140005468  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000546d  jmp     short loc_140005491
0x14000546f  mov     rcx, rax; this
0x140005472  test    r9, r9
0x140005475  jz      short loc_140005485
0x140005477  lea     r8, aHs; "[%hs]\n"
0x14000547e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005483  jmp     short loc_140005491
0x140005485  lea     r8, asc_140012028; "\n"
0x14000548c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005491  xor     eax, eax
0x140005493  mov     rcx, [rsp+278h+var_38]
0x14000549b  xor     rcx, rsp; StackCookie
0x14000549e  call    __security_check_cookie
0x1400054a3  mov     rbx, [rsp+278h+arg_18]
0x1400054ab  add     rsp, 250h
0x1400054b2  pop     r15
0x1400054b4  pop     r14
0x1400054b6  pop     rdi
0x1400054b7  pop     rsi
0x1400054b8  pop     rbp
0x1400054b9  retn
```
