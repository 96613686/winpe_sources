# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180038330`
- end: `0x1800385e0`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `688`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800387ec`

## callees

- `0x180002890`
- `0x180003474`
- `0x180005db0`
- `0x180038330`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800384dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800384dd`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180038459`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180038459`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v6)(__int64, wil *, __int64, const struct wil::FailureInfo *); // rax
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  const unsigned __int16 *v10; // r9
  unsigned __int16 *v11; // rsi
  __int64 v12; // rax
  unsigned __int16 *v13; // rdx
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

  if ( !this )
    return 0;
  v6 = (void (__fastcall *)(__int64, wil *, __int64, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
  *(_WORD *)this = 0;
  if ( v6 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      v6(a3, this, 2048, a4);
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
          v7 = UserSearchPath;
        goto LABEL_17;
      }
      v8 = "LogHr";
      v7 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v7 = v8;
    goto LABEL_17;
  }
  v7 = "Exception";
LABEL_17:
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
  v10 = *(const unsigned __int16 **)(a3 + 56);
  v11 = (unsigned __int16 *)((char *)this + 4096);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = (unsigned __int16 *)((char *)this + 4096);
  if ( v10 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v13, L"%hs(%u)\\%hs!%p: ", v10, lpBuffer, *(_QWORD *)(a3 + 128), v12);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v13, L"%hs!%p: ", *(const unsigned __int16 **)(a3 + 128), v12);
  }
  v15 = *(const unsigned __int16 **)(a3 + 144);
  v16 = (wil::details *)v14;
  if ( v15 )
    v16 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v11, L"(caller: %p) ", v15);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v16,
                          v11,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const unsigned __int16 *)v7,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v11, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v11, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v11, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v11, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v11, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf((wil::details *)v19, v11, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180038330  mov     [rsp+arg_8], rbx
0x180038335  push    rbp
0x180038336  push    rsi
0x180038337  push    rdi
0x180038338  push    r14
0x18003833a  push    r15
0x18003833c  sub     rsp, 250h
0x180038343  mov     rax, cs:__security_cookie
0x18003834a  xor     rax, rsp
0x18003834d  mov     [rsp+278h+var_38], rax
0x180038355  xor     r15d, r15d
0x180038358  mov     rbx, r8
0x18003835b  mov     r14, rcx
0x18003835e  test    rcx, rcx
0x180038361  jz      loc_1800385B7
0x180038367  mov     rax, cs:g_pfnResultLoggingCallback
0x18003836e  mov     [rcx], r15w
0x180038372  test    rax, rax
0x180038375  jz      short loc_18003839B
0x180038377  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003837e  jz      short loc_18003839B
0x180038380  mov     rdx, rcx
0x180038383  mov     r8d, 800h
0x180038389  mov     rcx, rbx
0x18003838c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038391  cmp     [r14], r15w
0x180038395  jnz     loc_1800385B7
0x18003839b  mov     ecx, [rbx]
0x18003839d  mov     sil, 8
0x1800383a0  test    ecx, ecx
0x1800383a2  jz      short loc_1800383ED
0x1800383a4  sub     ecx, 1
0x1800383a7  jz      short loc_1800383D5
0x1800383a9  sub     ecx, 1
0x1800383ac  jz      short loc_1800383C5
0x1800383ae  cmp     ecx, 1
0x1800383b1  jz      short loc_1800383BC
0x1800383b3  lea     rdi, UserSearchPath
0x1800383ba  jmp     short loc_1800383F4
0x1800383bc  lea     rdi, aFailfast; "FailFast"
0x1800383c3  jmp     short loc_1800383F4
0x1800383c5  lea     rax, aLoghr; "LogHr"
0x1800383cc  lea     rdi, aLognt; "LogNt"
0x1800383d3  jmp     short loc_1800383E3
0x1800383d5  lea     rax, aReturnhr; "ReturnHr"
0x1800383dc  lea     rdi, aReturnnt; "ReturnNt"
0x1800383e3  test    [rbx+4], sil
0x1800383e7  cmovz   rdi, rax
0x1800383eb  jmp     short loc_1800383F4
0x1800383ed  lea     rdi, aException; "Exception"
0x1800383f4  xor     edx, edx; Val
0x1800383f6  lea     rcx, [rsp+278h+Buffer]; void *
0x1800383fb  mov     r8d, 200h; Size
0x180038401  call    memset_0
0x180038406  test    [rbx+4], sil
0x18003840a  jz      short loc_18003842F
0x18003840c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180038413  mov     ebp, [rbx+0Ch]
0x180038416  test    rax, rax
0x180038419  jz      short loc_18003845F
0x18003841b  mov     r8d, 100h
0x180038421  lea     rdx, [rsp+278h+Buffer]
0x180038426  mov     ecx, ebp
0x180038428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003842d  jmp     short loc_18003845F
0x18003842f  mov     ebp, [rbx+8]
0x180038432  lea     rax, [rsp+278h+Buffer]
0x180038437  mov     [rsp+278h+Arguments], r15; Arguments
0x18003843c  mov     r8d, ebp; dwMessageId
0x18003843f  mov     [rsp+278h+nSize], 100h; nSize
0x180038447  mov     r9d, 400h; dwLanguageId
0x18003844d  xor     edx, edx; lpSource
0x18003844f  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180038454  mov     ecx, 1200h; dwFlags
0x180038459  call    cs:__imp_FormatMessageW
0x18003845f  mov     r9, [rbx+38h]; unsigned __int16 *
0x180038463  lea     rsi, [r14+1000h]
0x18003846a  mov     rax, [rbx+88h]
0x180038471  mov     rdx, rsi; unsigned __int16 *
0x180038474  mov     rcx, [rbx+80h]
0x18003847b  test    r9, r9
0x18003847e  jz      short loc_1800384A2
0x180038480  mov     [rsp+278h+Arguments], rax
0x180038485  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18003848c  mov     eax, [rbx+40h]
0x18003848f  mov     qword ptr [rsp+278h+nSize], rcx
0x180038494  mov     rcx, r14; this
0x180038497  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18003849b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800384a0  jmp     short loc_1800384B9
0x1800384a2  mov     r9, rcx; unsigned __int16 *
0x1800384a5  mov     [rsp+278h+lpBuffer], rax
0x1800384aa  mov     rcx, r14; this
0x1800384ad  lea     r8, aHsP; "%hs!%p: "
0x1800384b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800384b9  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800384c0  mov     r14, rax
0x1800384c3  test    r9, r9
0x1800384c6  jz      short loc_1800384DD
0x1800384c8  lea     r8, aCallerP; "(caller: %p) "
0x1800384cf  mov     rdx, rsi; unsigned __int16 *
0x1800384d2  mov     rcx, rax; this
0x1800384d5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800384da  mov     r14, rax
0x1800384dd  call    cs:__imp_GetCurrentThreadId
0x1800384e3  lea     rcx, [rsp+278h+Buffer]
0x1800384e8  mov     r9, rdi; unsigned __int16 *
0x1800384eb  mov     [rsp+278h+var_240], rcx
0x1800384f0  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800384f7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800384fb  mov     rdx, rsi; unsigned __int16 *
0x1800384fe  mov     [rsp+278h+nSize], eax
0x180038502  mov     rcx, r14; this
0x180038505  mov     eax, [rbx+44h]
0x180038508  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18003850c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180038511  cmp     [rbx+18h], r15
0x180038515  jnz     short loc_180038527
0x180038517  cmp     [rbx+48h], r15
0x18003851b  jnz     short loc_180038527
0x18003851d  cmp     [rbx+30h], r15
0x180038521  jz      loc_1800385B7
0x180038527  lea     r8, asc_18004FCD8; "    "
0x18003852e  mov     rdx, rsi; unsigned __int16 *
0x180038531  mov     rcx, rax; this
0x180038534  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180038539  mov     r9, [rbx+18h]; unsigned __int16 *
0x18003853d  test    r9, r9
0x180038540  jz      short loc_180038554
0x180038542  lea     r8, aMsgWs; "Msg:[%ws] "
0x180038549  mov     rdx, rsi; unsigned __int16 *
0x18003854c  mov     rcx, rax; this
0x18003854f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180038554  mov     r9, [rbx+48h]; unsigned __int16 *
0x180038558  test    r9, r9
0x18003855b  jz      short loc_18003856F
0x18003855d  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180038564  mov     rdx, rsi; unsigned __int16 *
0x180038567  mov     rcx, rax; this
0x18003856a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003856f  mov     rcx, [rbx+28h]
0x180038573  mov     rdx, rsi; unsigned __int16 *
0x180038576  mov     r9, [rbx+30h]; unsigned __int16 *
0x18003857a  test    rcx, rcx
0x18003857d  jz      short loc_180038595
0x18003857f  mov     [rsp+278h+lpBuffer], rcx
0x180038584  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18003858b  mov     rcx, rax; this
0x18003858e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180038593  jmp     short loc_1800385B7
0x180038595  mov     rcx, rax; this
0x180038598  test    r9, r9
0x18003859b  jz      short loc_1800385AB
0x18003859d  lea     r8, aHs; "[%hs]\n"
0x1800385a4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800385a9  jmp     short loc_1800385B7
0x1800385ab  lea     r8, asc_18004FD50; "\n"
0x1800385b2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800385b7  xor     eax, eax
0x1800385b9  mov     rcx, [rsp+278h+var_38]
0x1800385c1  xor     rcx, rsp; StackCookie
0x1800385c4  call    __security_check_cookie
0x1800385c9  mov     rbx, [rsp+278h+arg_8]
0x1800385d1  add     rsp, 250h
0x1800385d8  pop     r15
0x1800385da  pop     r14
0x1800385dc  pop     rdi
0x1800385dd  pop     rsi
0x1800385de  pop     rbp
0x1800385df  retn
```
