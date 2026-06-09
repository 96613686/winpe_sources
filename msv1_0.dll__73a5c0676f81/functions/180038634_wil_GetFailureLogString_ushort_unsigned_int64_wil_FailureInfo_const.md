# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180038634`
- end: `0x1800388ea`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180039218`
- `0x18003ba80`

## callees

- `0x18002fb50`
- `0x180030844`
- `0x180038634`
- `0x180039514`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800387e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800387e7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180038766`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180038766`

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
          v7 = byte_180072560;
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
0x180038634  mov     [rsp+arg_18], rbx
0x180038639  push    rbp
0x18003863a  push    rsi
0x18003863b  push    rdi
0x18003863c  push    r14
0x18003863e  push    r15
0x180038640  sub     rsp, 250h
0x180038647  mov     rax, cs:__security_cookie
0x18003864e  xor     rax, rsp
0x180038651  mov     [rsp+278h+var_38], rax
0x180038659  mov     rbx, r8
0x18003865c  mov     rsi, rdx
0x18003865f  mov     r14, rcx
0x180038662  xor     r15d, r15d
0x180038665  test    rdx, rdx
0x180038668  jz      loc_1800388C1
0x18003866e  test    rcx, rcx
0x180038671  jz      loc_1800388C1
0x180038677  mov     [rcx], r15w
0x18003867b  mov     rax, cs:g_pfnResultLoggingCallback
0x180038682  test    rax, rax
0x180038685  jz      short loc_1800386A8
0x180038687  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003868e  jz      short loc_1800386A8
0x180038690  mov     r8, rdx
0x180038693  mov     rdx, rcx
0x180038696  mov     rcx, rbx
0x180038699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003869e  cmp     [r14], r15w
0x1800386a2  jnz     loc_1800388C1
0x1800386a8  mov     ecx, [rbx]
0x1800386aa  mov     bpl, 8
0x1800386ad  test    ecx, ecx
0x1800386af  jz      short loc_1800386FA
0x1800386b1  sub     ecx, 1
0x1800386b4  jz      short loc_1800386E2
0x1800386b6  sub     ecx, 1
0x1800386b9  jz      short loc_1800386D2
0x1800386bb  cmp     ecx, 1
0x1800386be  jz      short loc_1800386C9
0x1800386c0  lea     rdi, byte_180072560
0x1800386c7  jmp     short loc_180038701
0x1800386c9  lea     rdi, aFailfast; "FailFast"
0x1800386d0  jmp     short loc_180038701
0x1800386d2  lea     rax, aLoghr; "LogHr"
0x1800386d9  lea     rdi, aLognt; "LogNt"
0x1800386e0  jmp     short loc_1800386F0
0x1800386e2  lea     rax, aReturnhr; "ReturnHr"
0x1800386e9  lea     rdi, aReturnnt; "ReturnNt"
0x1800386f0  test    [rbx+4], bpl
0x1800386f4  cmovz   rdi, rax
0x1800386f8  jmp     short loc_180038701
0x1800386fa  lea     rdi, aException; "Exception"
0x180038701  xor     edx, edx; Val
0x180038703  mov     r8d, 200h; Size
0x180038709  lea     rcx, [rsp+278h+Buffer]; void *
0x18003870e  call    memset_0
0x180038713  test    [rbx+4], bpl
0x180038717  jz      short loc_18003873C
0x180038719  mov     ebp, [rbx+0Ch]
0x18003871c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180038723  test    rax, rax
0x180038726  jz      short loc_18003876C
0x180038728  mov     r8d, 100h
0x18003872e  lea     rdx, [rsp+278h+Buffer]
0x180038733  mov     ecx, ebp
0x180038735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003873a  jmp     short loc_18003876C
0x18003873c  mov     ebp, [rbx+8]
0x18003873f  mov     [rsp+278h+Arguments], r15; Arguments
0x180038744  mov     [rsp+278h+nSize], 100h; nSize
0x18003874c  lea     rax, [rsp+278h+Buffer]
0x180038751  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180038756  mov     r9d, 400h; dwLanguageId
0x18003875c  mov     r8d, ebp; dwMessageId
0x18003875f  xor     edx, edx; lpSource
0x180038761  mov     ecx, 1200h; dwFlags
0x180038766  call    cs:__imp_FormatMessageW
0x18003876c  lea     rsi, [r14+rsi*2]
0x180038770  mov     r9, [rbx+38h]; unsigned __int16 *
0x180038774  mov     rax, [rbx+88h]
0x18003877b  mov     rcx, [rbx+80h]
0x180038782  mov     rdx, rsi; unsigned __int16 *
0x180038785  test    r9, r9
0x180038788  jz      short loc_1800387AC
0x18003878a  mov     [rsp+278h+Arguments], rax
0x18003878f  mov     qword ptr [rsp+278h+nSize], rcx
0x180038794  mov     eax, [rbx+40h]
0x180038797  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18003879b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800387a2  mov     rcx, r14; this
0x1800387a5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800387aa  jmp     short loc_1800387C3
0x1800387ac  mov     [rsp+278h+lpBuffer], rax
0x1800387b1  mov     r9, rcx; unsigned __int16 *
0x1800387b4  lea     r8, aHsP; "%hs!%p: "
0x1800387bb  mov     rcx, r14; this
0x1800387be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800387c3  mov     r14, rax
0x1800387c6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800387cd  test    r9, r9
0x1800387d0  jz      short loc_1800387E7
0x1800387d2  lea     r8, aCallerP; "(caller: %p) "
0x1800387d9  mov     rdx, rsi; unsigned __int16 *
0x1800387dc  mov     rcx, rax; this
0x1800387df  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800387e4  mov     r14, rax
0x1800387e7  call    cs:__imp_GetCurrentThreadId
0x1800387ed  lea     rcx, [rsp+278h+Buffer]
0x1800387f2  mov     [rsp+278h+var_240], rcx
0x1800387f7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800387fb  mov     [rsp+278h+nSize], eax
0x1800387ff  mov     eax, [rbx+44h]
0x180038802  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180038806  mov     r9, rdi; unsigned __int16 *
0x180038809  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180038810  mov     rdx, rsi; unsigned __int16 *
0x180038813  mov     rcx, r14; this
0x180038816  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003881b  cmp     [rbx+18h], r15
0x18003881f  jnz     short loc_180038831
0x180038821  cmp     [rbx+48h], r15
0x180038825  jnz     short loc_180038831
0x180038827  cmp     [rbx+30h], r15
0x18003882b  jz      loc_1800388C1
0x180038831  lea     r8, asc_180072E38; "    "
0x180038838  mov     rdx, rsi; unsigned __int16 *
0x18003883b  mov     rcx, rax; this
0x18003883e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180038843  mov     r9, [rbx+18h]; unsigned __int16 *
0x180038847  test    r9, r9
0x18003884a  jz      short loc_18003885E
0x18003884c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180038853  mov     rdx, rsi; unsigned __int16 *
0x180038856  mov     rcx, rax; this
0x180038859  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003885e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180038862  test    r9, r9
0x180038865  jz      short loc_180038879
0x180038867  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18003886e  mov     rdx, rsi; unsigned __int16 *
0x180038871  mov     rcx, rax; this
0x180038874  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180038879  mov     rcx, [rbx+28h]
0x18003887d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180038881  mov     rdx, rsi; unsigned __int16 *
0x180038884  test    rcx, rcx
0x180038887  jz      short loc_18003889F
0x180038889  mov     [rsp+278h+lpBuffer], rcx
0x18003888e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180038895  mov     rcx, rax; this
0x180038898  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003889d  jmp     short loc_1800388C1
0x18003889f  mov     rcx, rax; this
0x1800388a2  test    r9, r9
0x1800388a5  jz      short loc_1800388B5
0x1800388a7  lea     r8, aHs; "[%hs]\n"
0x1800388ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800388b3  jmp     short loc_1800388C1
0x1800388b5  lea     r8, asc_180072F08; "\n"
0x1800388bc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800388c1  xor     eax, eax
0x1800388c3  mov     rcx, [rsp+278h+var_38]
0x1800388cb  xor     rcx, rsp; StackCookie
0x1800388ce  call    __security_check_cookie
0x1800388d3  mov     rbx, [rsp+278h+arg_18]
0x1800388db  add     rsp, 250h
0x1800388e2  pop     r15
0x1800388e4  pop     r14
0x1800388e6  pop     rdi
0x1800388e7  pop     rsi
0x1800388e8  pop     rbp
0x1800388e9  retn
```
