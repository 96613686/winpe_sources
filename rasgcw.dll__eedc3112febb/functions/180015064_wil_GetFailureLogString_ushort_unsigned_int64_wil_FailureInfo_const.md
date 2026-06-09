# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180015064`
- end: `0x18001531a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180013e7c`
- `0x180015ac0`
- `0x180017ee0`

## callees

- `0x180015064`
- `0x180015dc0`
- `0x18002f382`
- `0x18002f3b0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015217`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015217`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180015196`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180015196`

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
          v7 = (const char *)&Format;
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
0x180015064  mov     [rsp+arg_18], rbx
0x180015069  push    rbp
0x18001506a  push    rsi
0x18001506b  push    rdi
0x18001506c  push    r14
0x18001506e  push    r15
0x180015070  sub     rsp, 250h
0x180015077  mov     rax, cs:__security_cookie
0x18001507e  xor     rax, rsp
0x180015081  mov     [rsp+278h+var_38], rax
0x180015089  mov     rbx, r8
0x18001508c  mov     rsi, rdx
0x18001508f  mov     r14, rcx
0x180015092  xor     r15d, r15d
0x180015095  test    rdx, rdx
0x180015098  jz      loc_1800152F1
0x18001509e  test    rcx, rcx
0x1800150a1  jz      loc_1800152F1
0x1800150a7  mov     [rcx], r15w
0x1800150ab  mov     rax, cs:g_pfnResultLoggingCallback
0x1800150b2  test    rax, rax
0x1800150b5  jz      short loc_1800150D8
0x1800150b7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800150be  jz      short loc_1800150D8
0x1800150c0  mov     r8, rdx
0x1800150c3  mov     rdx, rcx
0x1800150c6  mov     rcx, rbx
0x1800150c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800150ce  cmp     [r14], r15w
0x1800150d2  jnz     loc_1800152F1
0x1800150d8  mov     ecx, [rbx]
0x1800150da  mov     bpl, 8
0x1800150dd  test    ecx, ecx
0x1800150df  jz      short loc_18001512A
0x1800150e1  sub     ecx, 1
0x1800150e4  jz      short loc_180015112
0x1800150e6  sub     ecx, 1
0x1800150e9  jz      short loc_180015102
0x1800150eb  cmp     ecx, 1
0x1800150ee  jz      short loc_1800150F9
0x1800150f0  lea     rdi, Format
0x1800150f7  jmp     short loc_180015131
0x1800150f9  lea     rdi, aFailfast; "FailFast"
0x180015100  jmp     short loc_180015131
0x180015102  lea     rax, aLoghr; "LogHr"
0x180015109  lea     rdi, aLognt; "LogNt"
0x180015110  jmp     short loc_180015120
0x180015112  lea     rax, aReturnhr; "ReturnHr"
0x180015119  lea     rdi, aReturnnt; "ReturnNt"
0x180015120  test    [rbx+4], bpl
0x180015124  cmovz   rdi, rax
0x180015128  jmp     short loc_180015131
0x18001512a  lea     rdi, aException; "Exception"
0x180015131  xor     edx, edx; Val
0x180015133  mov     r8d, 200h; Size
0x180015139  lea     rcx, [rsp+278h+Buffer]; void *
0x18001513e  call    memset_0
0x180015143  test    [rbx+4], bpl
0x180015147  jz      short loc_18001516C
0x180015149  mov     ebp, [rbx+0Ch]
0x18001514c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180015153  test    rax, rax
0x180015156  jz      short loc_18001519C
0x180015158  mov     r8d, 100h
0x18001515e  lea     rdx, [rsp+278h+Buffer]
0x180015163  mov     ecx, ebp
0x180015165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001516a  jmp     short loc_18001519C
0x18001516c  mov     ebp, [rbx+8]
0x18001516f  mov     [rsp+278h+Arguments], r15; Arguments
0x180015174  mov     [rsp+278h+nSize], 100h; nSize
0x18001517c  lea     rax, [rsp+278h+Buffer]
0x180015181  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180015186  mov     r9d, 400h; dwLanguageId
0x18001518c  mov     r8d, ebp; dwMessageId
0x18001518f  xor     edx, edx; lpSource
0x180015191  mov     ecx, 1200h; dwFlags
0x180015196  call    cs:__imp_FormatMessageW
0x18001519c  lea     rsi, [r14+rsi*2]
0x1800151a0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800151a4  mov     rax, [rbx+88h]
0x1800151ab  mov     rcx, [rbx+80h]
0x1800151b2  mov     rdx, rsi; unsigned __int16 *
0x1800151b5  test    r9, r9
0x1800151b8  jz      short loc_1800151DC
0x1800151ba  mov     [rsp+278h+Arguments], rax
0x1800151bf  mov     qword ptr [rsp+278h+nSize], rcx
0x1800151c4  mov     eax, [rbx+40h]
0x1800151c7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800151cb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800151d2  mov     rcx, r14; this
0x1800151d5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800151da  jmp     short loc_1800151F3
0x1800151dc  mov     [rsp+278h+lpBuffer], rax
0x1800151e1  mov     r9, rcx; unsigned __int16 *
0x1800151e4  lea     r8, aHsP; "%hs!%p: "
0x1800151eb  mov     rcx, r14; this
0x1800151ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800151f3  mov     r14, rax
0x1800151f6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800151fd  test    r9, r9
0x180015200  jz      short loc_180015217
0x180015202  lea     r8, aCallerP; "(caller: %p) "
0x180015209  mov     rdx, rsi; unsigned __int16 *
0x18001520c  mov     rcx, rax; this
0x18001520f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180015214  mov     r14, rax
0x180015217  call    cs:__imp_GetCurrentThreadId
0x18001521d  lea     rcx, [rsp+278h+Buffer]
0x180015222  mov     [rsp+278h+var_240], rcx
0x180015227  mov     dword ptr [rsp+278h+Arguments], ebp
0x18001522b  mov     [rsp+278h+nSize], eax
0x18001522f  mov     eax, [rbx+44h]
0x180015232  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180015236  mov     r9, rdi; unsigned __int16 *
0x180015239  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180015240  mov     rdx, rsi; unsigned __int16 *
0x180015243  mov     rcx, r14; this
0x180015246  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001524b  cmp     [rbx+18h], r15
0x18001524f  jnz     short loc_180015261
0x180015251  cmp     [rbx+48h], r15
0x180015255  jnz     short loc_180015261
0x180015257  cmp     [rbx+30h], r15
0x18001525b  jz      loc_1800152F1
0x180015261  lea     r8, asc_180038058; "    "
0x180015268  mov     rdx, rsi; unsigned __int16 *
0x18001526b  mov     rcx, rax; this
0x18001526e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180015273  mov     r9, [rbx+18h]; unsigned __int16 *
0x180015277  test    r9, r9
0x18001527a  jz      short loc_18001528E
0x18001527c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180015283  mov     rdx, rsi; unsigned __int16 *
0x180015286  mov     rcx, rax; this
0x180015289  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001528e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180015292  test    r9, r9
0x180015295  jz      short loc_1800152A9
0x180015297  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001529e  mov     rdx, rsi; unsigned __int16 *
0x1800152a1  mov     rcx, rax; this
0x1800152a4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800152a9  mov     rcx, [rbx+28h]
0x1800152ad  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800152b1  mov     rdx, rsi; unsigned __int16 *
0x1800152b4  test    rcx, rcx
0x1800152b7  jz      short loc_1800152CF
0x1800152b9  mov     [rsp+278h+lpBuffer], rcx
0x1800152be  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800152c5  mov     rcx, rax; this
0x1800152c8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800152cd  jmp     short loc_1800152F1
0x1800152cf  mov     rcx, rax; this
0x1800152d2  test    r9, r9
0x1800152d5  jz      short loc_1800152E5
0x1800152d7  lea     r8, aHs; "[%hs]\n"
0x1800152de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800152e3  jmp     short loc_1800152F1
0x1800152e5  lea     r8, asc_1800380D0; "\n"
0x1800152ec  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800152f1  xor     eax, eax
0x1800152f3  mov     rcx, [rsp+278h+var_38]
0x1800152fb  xor     rcx, rsp; StackCookie
0x1800152fe  call    __security_check_cookie
0x180015303  mov     rbx, [rsp+278h+arg_18]
0x18001530b  add     rsp, 250h
0x180015312  pop     r15
0x180015314  pop     r14
0x180015316  pop     rdi
0x180015317  pop     rsi
0x180015318  pop     rbp
0x180015319  retn
```
