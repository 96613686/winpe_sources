# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180007470`
- end: `0x180007731`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wchar_t *Buffer, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180003884`
- `0x180003af8`
- `0x180008388`
- `0x18000f580`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x180007470`
- `0x180008690`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000762e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000762e`
- `api-ms-win-core-misc-l1-1-0!FormatMessageW` at `0x1800075ad`
- `api-ms-win-core-misc-l1-1-0!FormatMessageW` at `0x1800075ad`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wchar_t *Buffer,
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
  wchar_t *v14; // rax
  wchar_t *v15; // r14
  const unsigned __int16 *v16; // r9
  wchar_t *v17; // rax
  const unsigned __int16 *v18; // r9
  wchar_t *v19; // rax
  const unsigned __int16 *v20; // r9
  const unsigned __int16 *v21; // r9
  const unsigned __int16 *v22; // r9
  LPWSTR lpBuffer; // [rsp+20h] [rbp-268h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-268h]
  DWORD nSize[2]; // [rsp+28h] [rbp-260h]
  va_list *Arguments; // [rsp+30h] [rbp-258h]
  WCHAR Buffera[256]; // [rsp+50h] [rbp-238h] BYREF

  if ( !a2 )
    return 0;
  if ( !Buffer )
    return 0;
  *Buffer = 0;
  if ( g_pfnResultLoggingCallback )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      g_pfnResultLoggingCallback(a3, Buffer, a2);
      if ( *Buffer )
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
          v7 = (const char *)&dword_18002ED8C;
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
  memset_0(Buffera, 0, sizeof(Buffera));
  if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
  {
    v9 = *(_DWORD *)(a3 + 12);
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(v9, Buffera, 0x100u);
  }
  else
  {
    v9 = *(_DWORD *)(a3 + 8);
    FormatMessageW(0x1200u, 0, v9, 0x400u, Buffera, 0x100u, 0);
  }
  v10 = &Buffer[(_QWORD)a2];
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const unsigned __int16 **)(a3 + 128);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(Buffer, v10, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, v13, v12);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(Buffer, v10, L"%hs!%p: ", v13, v12);
  }
  v15 = v14;
  v16 = *(const unsigned __int16 **)(a3 + 144);
  if ( v16 )
    v15 = wil::details::LogStringPrintf(v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = wil::details::LogStringPrintf(
          v15,
          v10,
          L"%hs(%d) tid(%x) %08X %ws",
          (const unsigned __int16 *)v7,
          lpBuffera,
          *(_QWORD *)nSize,
          Arguments,
          Buffera,
          -2);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v10, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf(v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf(v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf(v19, v10, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf(v19, v10, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf(v19, v10, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180007470  mov     rax, rsp
0x180007473  push    rbp
0x180007474  push    rsi
0x180007475  push    rdi
0x180007476  push    r14
0x180007478  push    r15
0x18000747a  sub     rsp, 260h
0x180007481  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x18000748a  mov     [rax+20h], rbx
0x18000748e  mov     rax, cs:__security_cookie
0x180007495  xor     rax, rsp
0x180007498  mov     [rsp+288h+var_38], rax
0x1800074a0  mov     rbx, r8
0x1800074a3  mov     rsi, rdx
0x1800074a6  mov     r14, rcx
0x1800074a9  xor     r15d, r15d
0x1800074ac  test    rdx, rdx
0x1800074af  jz      loc_180007708
0x1800074b5  test    rcx, rcx
0x1800074b8  jz      loc_180007708
0x1800074be  mov     [rcx], r15w
0x1800074c2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800074c9  test    rax, rax
0x1800074cc  jz      short loc_1800074EF
0x1800074ce  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800074d5  jz      short loc_1800074EF
0x1800074d7  mov     r8, rdx
0x1800074da  mov     rdx, rcx
0x1800074dd  mov     rcx, rbx
0x1800074e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074e5  cmp     [r14], r15w
0x1800074e9  jnz     loc_180007708
0x1800074ef  mov     ecx, [rbx]
0x1800074f1  mov     bpl, 8
0x1800074f4  test    ecx, ecx
0x1800074f6  jz      short loc_180007541
0x1800074f8  sub     ecx, 1
0x1800074fb  jz      short loc_180007529
0x1800074fd  sub     ecx, 1
0x180007500  jz      short loc_180007519
0x180007502  cmp     ecx, 1
0x180007505  jz      short loc_180007510
0x180007507  lea     rdi, dword_18002ED8C
0x18000750e  jmp     short loc_180007548
0x180007510  lea     rdi, aFailfast; "FailFast"
0x180007517  jmp     short loc_180007548
0x180007519  lea     rax, aLoghr; "LogHr"
0x180007520  lea     rdi, aLognt; "LogNt"
0x180007527  jmp     short loc_180007537
0x180007529  lea     rax, aReturnhr; "ReturnHr"
0x180007530  lea     rdi, aReturnnt; "ReturnNt"
0x180007537  test    [rbx+4], bpl
0x18000753b  cmovz   rdi, rax
0x18000753f  jmp     short loc_180007548
0x180007541  lea     rdi, aException; "Exception"
0x180007548  xor     edx, edx; Val
0x18000754a  mov     r8d, 200h; Size
0x180007550  lea     rcx, [rsp+288h+Buffer]; void *
0x180007555  call    memset_0
0x18000755a  test    [rbx+4], bpl
0x18000755e  jz      short loc_180007583
0x180007560  mov     ebp, [rbx+0Ch]
0x180007563  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000756a  test    rax, rax
0x18000756d  jz      short loc_1800075B3
0x18000756f  mov     r8d, 100h
0x180007575  lea     rdx, [rsp+288h+Buffer]
0x18000757a  mov     ecx, ebp
0x18000757c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007581  jmp     short loc_1800075B3
0x180007583  mov     ebp, [rbx+8]
0x180007586  mov     [rsp+288h+Arguments], r15; Arguments
0x18000758b  mov     [rsp+288h+nSize], 100h; nSize
0x180007593  lea     rax, [rsp+288h+Buffer]
0x180007598  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x18000759d  mov     r9d, 400h; dwLanguageId
0x1800075a3  mov     r8d, ebp; dwMessageId
0x1800075a6  xor     edx, edx; lpSource
0x1800075a8  mov     ecx, 1200h; dwFlags
0x1800075ad  call    cs:__imp_FormatMessageW
0x1800075b3  lea     rsi, [r14+rsi*2]
0x1800075b7  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800075bb  mov     rax, [rbx+88h]
0x1800075c2  mov     rcx, [rbx+80h]
0x1800075c9  mov     rdx, rsi; unsigned __int16 *
0x1800075cc  test    r9, r9
0x1800075cf  jz      short loc_1800075F3
0x1800075d1  mov     [rsp+288h+Arguments], rax
0x1800075d6  mov     qword ptr [rsp+288h+nSize], rcx
0x1800075db  mov     eax, [rbx+40h]
0x1800075de  mov     dword ptr [rsp+288h+lpBuffer], eax
0x1800075e2  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800075e9  mov     rcx, r14; Buffer
0x1800075ec  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800075f1  jmp     short loc_18000760A
0x1800075f3  mov     [rsp+288h+lpBuffer], rax
0x1800075f8  mov     r9, rcx; unsigned __int16 *
0x1800075fb  lea     r8, aHsP; "%hs!%p: "
0x180007602  mov     rcx, r14; Buffer
0x180007605  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000760a  mov     r14, rax
0x18000760d  mov     r9, [rbx+90h]; unsigned __int16 *
0x180007614  test    r9, r9
0x180007617  jz      short loc_18000762E
0x180007619  lea     r8, aCallerP; "(caller: %p) "
0x180007620  mov     rdx, rsi; unsigned __int16 *
0x180007623  mov     rcx, rax; Buffer
0x180007626  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000762b  mov     r14, rax
0x18000762e  call    cs:__imp_GetCurrentThreadId
0x180007634  lea     rcx, [rsp+288h+Buffer]
0x180007639  mov     [rsp+288h+var_250], rcx
0x18000763e  mov     dword ptr [rsp+288h+Arguments], ebp
0x180007642  mov     [rsp+288h+nSize], eax
0x180007646  mov     eax, [rbx+44h]
0x180007649  mov     dword ptr [rsp+288h+lpBuffer], eax
0x18000764d  mov     r9, rdi; unsigned __int16 *
0x180007650  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180007657  mov     rdx, rsi; unsigned __int16 *
0x18000765a  mov     rcx, r14; Buffer
0x18000765d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007662  cmp     [rbx+18h], r15
0x180007666  jnz     short loc_180007678
0x180007668  cmp     [rbx+48h], r15
0x18000766c  jnz     short loc_180007678
0x18000766e  cmp     [rbx+30h], r15
0x180007672  jz      loc_180007708
0x180007678  lea     r8, asc_18002EF38; "    "
0x18000767f  mov     rdx, rsi; unsigned __int16 *
0x180007682  mov     rcx, rax; Buffer
0x180007685  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000768a  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000768e  test    r9, r9
0x180007691  jz      short loc_1800076A5
0x180007693  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000769a  mov     rdx, rsi; unsigned __int16 *
0x18000769d  mov     rcx, rax; Buffer
0x1800076a0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800076a5  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800076a9  test    r9, r9
0x1800076ac  jz      short loc_1800076C0
0x1800076ae  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800076b5  mov     rdx, rsi; unsigned __int16 *
0x1800076b8  mov     rcx, rax; Buffer
0x1800076bb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800076c0  mov     rcx, [rbx+28h]
0x1800076c4  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800076c8  mov     rdx, rsi; unsigned __int16 *
0x1800076cb  test    rcx, rcx
0x1800076ce  jz      short loc_1800076E6
0x1800076d0  mov     [rsp+288h+lpBuffer], rcx
0x1800076d5  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800076dc  mov     rcx, rax; Buffer
0x1800076df  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800076e4  jmp     short loc_180007708
0x1800076e6  mov     rcx, rax; Buffer
0x1800076e9  test    r9, r9
0x1800076ec  jz      short loc_1800076FC
0x1800076ee  lea     r8, aHs; "[%hs]\n"
0x1800076f5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800076fa  jmp     short loc_180007708
0x1800076fc  lea     r8, asc_18002EFB0; "\n"
0x180007703  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007708  xor     eax, eax
0x18000770a  mov     rcx, [rsp+288h+var_38]
0x180007712  xor     rcx, rsp; StackCookie
0x180007715  call    __security_check_cookie
0x18000771a  mov     rbx, [rsp+288h+arg_18]
0x180007722  add     rsp, 260h
0x180007729  pop     r15
0x18000772b  pop     r14
0x18000772d  pop     rdi
0x18000772e  pop     rsi
0x18000772f  pop     rbp
0x180007730  retn
```
