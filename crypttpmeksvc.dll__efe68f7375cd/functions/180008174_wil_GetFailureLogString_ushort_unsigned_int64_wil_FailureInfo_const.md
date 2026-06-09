# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180008174`
- end: `0x18000842a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180007e24`

## callees

- `0x180008174`
- `0x1800086dc`
- `0x18000a7ce`
- `0x18000a800`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008327`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008327`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800082a6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800082a6`

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
          v8 = (const char *)&qword_18000E260;
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
0x180008174  mov     [rsp+arg_18], rbx
0x180008179  push    rbp
0x18000817a  push    rsi
0x18000817b  push    rdi
0x18000817c  push    r14
0x18000817e  push    r15
0x180008180  sub     rsp, 250h
0x180008187  mov     rax, cs:__security_cookie
0x18000818e  xor     rax, rsp
0x180008191  mov     [rsp+278h+var_38], rax
0x180008199  xor     r15d, r15d
0x18000819c  mov     rbx, r8
0x18000819f  mov     rsi, rdx
0x1800081a2  mov     r14, rcx
0x1800081a5  test    rdx, rdx
0x1800081a8  jz      loc_180008401
0x1800081ae  test    rcx, rcx
0x1800081b1  jz      loc_180008401
0x1800081b7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800081be  mov     [rcx], r15w
0x1800081c2  test    rax, rax
0x1800081c5  jz      short loc_1800081E8
0x1800081c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800081ce  jz      short loc_1800081E8
0x1800081d0  mov     r8, rdx
0x1800081d3  mov     rdx, rcx
0x1800081d6  mov     rcx, rbx
0x1800081d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081de  cmp     [r14], r15w
0x1800081e2  jnz     loc_180008401
0x1800081e8  mov     ecx, [rbx]
0x1800081ea  mov     bpl, 8
0x1800081ed  test    ecx, ecx
0x1800081ef  jz      short loc_18000823A
0x1800081f1  sub     ecx, 1
0x1800081f4  jz      short loc_180008222
0x1800081f6  sub     ecx, 1
0x1800081f9  jz      short loc_180008212
0x1800081fb  cmp     ecx, 1
0x1800081fe  jz      short loc_180008209
0x180008200  lea     rdi, qword_18000E260
0x180008207  jmp     short loc_180008241
0x180008209  lea     rdi, aFailfast; "FailFast"
0x180008210  jmp     short loc_180008241
0x180008212  lea     rax, aLoghr; "LogHr"
0x180008219  lea     rdi, aLognt; "LogNt"
0x180008220  jmp     short loc_180008230
0x180008222  lea     rax, aReturnhr; "ReturnHr"
0x180008229  lea     rdi, aReturnnt; "ReturnNt"
0x180008230  test    [rbx+4], bpl
0x180008234  cmovz   rdi, rax
0x180008238  jmp     short loc_180008241
0x18000823a  lea     rdi, aException; "Exception"
0x180008241  xor     edx, edx; Val
0x180008243  lea     rcx, [rsp+278h+Buffer]; void *
0x180008248  mov     r8d, 200h; Size
0x18000824e  call    memset_0
0x180008253  test    [rbx+4], bpl
0x180008257  jz      short loc_18000827C
0x180008259  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180008260  mov     ebp, [rbx+0Ch]
0x180008263  test    rax, rax
0x180008266  jz      short loc_1800082AC
0x180008268  mov     r8d, 100h
0x18000826e  lea     rdx, [rsp+278h+Buffer]
0x180008273  mov     ecx, ebp
0x180008275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000827a  jmp     short loc_1800082AC
0x18000827c  mov     ebp, [rbx+8]
0x18000827f  lea     rax, [rsp+278h+Buffer]
0x180008284  mov     [rsp+278h+Arguments], r15; Arguments
0x180008289  mov     r8d, ebp; dwMessageId
0x18000828c  mov     [rsp+278h+nSize], 100h; nSize
0x180008294  mov     r9d, 400h; dwLanguageId
0x18000829a  xor     edx, edx; lpSource
0x18000829c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800082a1  mov     ecx, 1200h; dwFlags
0x1800082a6  call    cs:__imp_FormatMessageW
0x1800082ac  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800082b0  lea     rsi, [r14+rsi*2]
0x1800082b4  mov     rax, [rbx+88h]
0x1800082bb  mov     rdx, rsi; unsigned __int16 *
0x1800082be  mov     rcx, [rbx+80h]
0x1800082c5  test    r9, r9
0x1800082c8  jz      short loc_1800082EC
0x1800082ca  mov     [rsp+278h+Arguments], rax
0x1800082cf  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800082d6  mov     eax, [rbx+40h]
0x1800082d9  mov     qword ptr [rsp+278h+nSize], rcx
0x1800082de  mov     rcx, r14; this
0x1800082e1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800082e5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800082ea  jmp     short loc_180008303
0x1800082ec  mov     r9, rcx; unsigned __int16 *
0x1800082ef  mov     [rsp+278h+lpBuffer], rax
0x1800082f4  mov     rcx, r14; this
0x1800082f7  lea     r8, aHsP; "%hs!%p: "
0x1800082fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008303  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000830a  mov     r14, rax
0x18000830d  test    r9, r9
0x180008310  jz      short loc_180008327
0x180008312  lea     r8, aCallerP; "(caller: %p) "
0x180008319  mov     rdx, rsi; unsigned __int16 *
0x18000831c  mov     rcx, rax; this
0x18000831f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008324  mov     r14, rax
0x180008327  call    cs:__imp_GetCurrentThreadId
0x18000832d  lea     rcx, [rsp+278h+Buffer]
0x180008332  mov     r9, rdi; unsigned __int16 *
0x180008335  mov     [rsp+278h+var_240], rcx
0x18000833a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180008341  mov     dword ptr [rsp+278h+Arguments], ebp
0x180008345  mov     rdx, rsi; unsigned __int16 *
0x180008348  mov     [rsp+278h+nSize], eax
0x18000834c  mov     rcx, r14; this
0x18000834f  mov     eax, [rbx+44h]
0x180008352  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180008356  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000835b  cmp     [rbx+18h], r15
0x18000835f  jnz     short loc_180008371
0x180008361  cmp     [rbx+48h], r15
0x180008365  jnz     short loc_180008371
0x180008367  cmp     [rbx+30h], r15
0x18000836b  jz      loc_180008401
0x180008371  lea     r8, asc_18000E350; "    "
0x180008378  mov     rdx, rsi; unsigned __int16 *
0x18000837b  mov     rcx, rax; this
0x18000837e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008383  mov     r9, [rbx+18h]; unsigned __int16 *
0x180008387  test    r9, r9
0x18000838a  jz      short loc_18000839E
0x18000838c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180008393  mov     rdx, rsi; unsigned __int16 *
0x180008396  mov     rcx, rax; this
0x180008399  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000839e  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800083a2  test    r9, r9
0x1800083a5  jz      short loc_1800083B9
0x1800083a7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800083ae  mov     rdx, rsi; unsigned __int16 *
0x1800083b1  mov     rcx, rax; this
0x1800083b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800083b9  mov     rcx, [rbx+28h]
0x1800083bd  mov     rdx, rsi; unsigned __int16 *
0x1800083c0  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800083c4  test    rcx, rcx
0x1800083c7  jz      short loc_1800083DF
0x1800083c9  mov     [rsp+278h+lpBuffer], rcx
0x1800083ce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800083d5  mov     rcx, rax; this
0x1800083d8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800083dd  jmp     short loc_180008401
0x1800083df  mov     rcx, rax; this
0x1800083e2  test    r9, r9
0x1800083e5  jz      short loc_1800083F5
0x1800083e7  lea     r8, aHs_0; "[%hs]\n"
0x1800083ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800083f3  jmp     short loc_180008401
0x1800083f5  lea     r8, asc_18000E3C8; "\n"
0x1800083fc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008401  xor     eax, eax
0x180008403  mov     rcx, [rsp+278h+var_38]
0x18000840b  xor     rcx, rsp; StackCookie
0x18000840e  call    __security_check_cookie
0x180008413  mov     rbx, [rsp+278h+arg_18]
0x18000841b  add     rsp, 250h
0x180008422  pop     r15
0x180008424  pop     r14
0x180008426  pop     rdi
0x180008427  pop     rsi
0x180008428  pop     rbp
0x180008429  retn
```
