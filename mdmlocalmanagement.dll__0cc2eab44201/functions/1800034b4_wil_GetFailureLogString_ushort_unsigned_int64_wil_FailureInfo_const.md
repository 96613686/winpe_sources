# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800034b4`
- end: `0x180003777`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800023a0`
- `0x180002624`
- `0x180003e7c`
- `0x1800057a0`

## callees

- `0x180001660`
- `0x180001fea`
- `0x1800034b4`
- `0x180004190`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000366d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000366d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800035e6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800035e6`

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
          v7 = (const char *)&byte_180008619;
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
0x1800034b4  mov     [rsp+arg_18], rbx
0x1800034b9  push    rbp
0x1800034ba  push    rsi
0x1800034bb  push    rdi
0x1800034bc  push    r14
0x1800034be  push    r15
0x1800034c0  sub     rsp, 250h
0x1800034c7  mov     rax, cs:__security_cookie
0x1800034ce  xor     rax, rsp
0x1800034d1  mov     [rsp+278h+var_38], rax
0x1800034d9  mov     rbx, r8
0x1800034dc  mov     rsi, rdx
0x1800034df  mov     r14, rcx
0x1800034e2  xor     r15d, r15d
0x1800034e5  test    rdx, rdx
0x1800034e8  jz      loc_18000374D
0x1800034ee  test    rcx, rcx
0x1800034f1  jz      loc_18000374D
0x1800034f7  mov     [rcx], r15w
0x1800034fb  mov     rax, cs:g_pfnResultLoggingCallback
0x180003502  test    rax, rax
0x180003505  jz      short loc_180003528
0x180003507  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000350e  jz      short loc_180003528
0x180003510  mov     r8, rdx
0x180003513  mov     rdx, rcx
0x180003516  mov     rcx, rbx
0x180003519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000351e  cmp     [r14], r15w
0x180003522  jnz     loc_18000374D
0x180003528  mov     ecx, [rbx]
0x18000352a  mov     bpl, 8
0x18000352d  test    ecx, ecx
0x18000352f  jz      short loc_18000357A
0x180003531  sub     ecx, 1
0x180003534  jz      short loc_180003562
0x180003536  sub     ecx, 1
0x180003539  jz      short loc_180003552
0x18000353b  cmp     ecx, 1
0x18000353e  jz      short loc_180003549
0x180003540  lea     rdi, byte_180008619
0x180003547  jmp     short loc_180003581
0x180003549  lea     rdi, aFailfast; "FailFast"
0x180003550  jmp     short loc_180003581
0x180003552  lea     rax, aLoghr; "LogHr"
0x180003559  lea     rdi, aLognt; "LogNt"
0x180003560  jmp     short loc_180003570
0x180003562  lea     rax, aReturnhr; "ReturnHr"
0x180003569  lea     rdi, aReturnnt; "ReturnNt"
0x180003570  test    [rbx+4], bpl
0x180003574  cmovz   rdi, rax
0x180003578  jmp     short loc_180003581
0x18000357a  lea     rdi, aException; "Exception"
0x180003581  xor     edx, edx; Val
0x180003583  mov     r8d, 200h; Size
0x180003589  lea     rcx, [rsp+278h+Buffer]; void *
0x18000358e  call    memset_0
0x180003593  test    [rbx+4], bpl
0x180003597  jz      short loc_1800035BC
0x180003599  mov     ebp, [rbx+0Ch]
0x18000359c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800035a3  test    rax, rax
0x1800035a6  jz      short loc_1800035F2
0x1800035a8  mov     r8d, 100h
0x1800035ae  lea     rdx, [rsp+278h+Buffer]
0x1800035b3  mov     ecx, ebp
0x1800035b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035ba  jmp     short loc_1800035F2
0x1800035bc  mov     ebp, [rbx+8]
0x1800035bf  mov     [rsp+278h+Arguments], r15; Arguments
0x1800035c4  mov     [rsp+278h+nSize], 100h; nSize
0x1800035cc  lea     rax, [rsp+278h+Buffer]
0x1800035d1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800035d6  mov     r9d, 400h; dwLanguageId
0x1800035dc  mov     r8d, ebp; dwMessageId
0x1800035df  xor     edx, edx; lpSource
0x1800035e1  mov     ecx, 1200h; dwFlags
0x1800035e6  call    cs:__imp_FormatMessageW
0x1800035ed  nop     dword ptr [rax+rax+00h]
0x1800035f2  lea     rsi, [r14+rsi*2]
0x1800035f6  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800035fa  mov     rax, [rbx+88h]
0x180003601  mov     rcx, [rbx+80h]
0x180003608  mov     rdx, rsi; unsigned __int16 *
0x18000360b  test    r9, r9
0x18000360e  jz      short loc_180003632
0x180003610  mov     [rsp+278h+Arguments], rax
0x180003615  mov     qword ptr [rsp+278h+nSize], rcx
0x18000361a  mov     eax, [rbx+40h]
0x18000361d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003621  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180003628  mov     rcx, r14; this
0x18000362b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003630  jmp     short loc_180003649
0x180003632  mov     [rsp+278h+lpBuffer], rax
0x180003637  mov     r9, rcx; unsigned __int16 *
0x18000363a  lea     r8, aHsP; "%hs!%p: "
0x180003641  mov     rcx, r14; this
0x180003644  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003649  mov     r14, rax
0x18000364c  mov     r9, [rbx+90h]; unsigned __int16 *
0x180003653  test    r9, r9
0x180003656  jz      short loc_18000366D
0x180003658  lea     r8, aCallerP; "(caller: %p) "
0x18000365f  mov     rdx, rsi; unsigned __int16 *
0x180003662  mov     rcx, rax; this
0x180003665  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000366a  mov     r14, rax
0x18000366d  call    cs:__imp_GetCurrentThreadId
0x180003674  nop     dword ptr [rax+rax+00h]
0x180003679  lea     rcx, [rsp+278h+Buffer]
0x18000367e  mov     [rsp+278h+var_240], rcx
0x180003683  mov     dword ptr [rsp+278h+Arguments], ebp
0x180003687  mov     [rsp+278h+nSize], eax
0x18000368b  mov     eax, [rbx+44h]
0x18000368e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003692  mov     r9, rdi; unsigned __int16 *
0x180003695  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000369c  mov     rdx, rsi; unsigned __int16 *
0x18000369f  mov     rcx, r14; this
0x1800036a2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800036a7  cmp     [rbx+18h], r15
0x1800036ab  jnz     short loc_1800036BD
0x1800036ad  cmp     [rbx+48h], r15
0x1800036b1  jnz     short loc_1800036BD
0x1800036b3  cmp     [rbx+30h], r15
0x1800036b7  jz      loc_18000374D
0x1800036bd  lea     r8, asc_180008720; "    "
0x1800036c4  mov     rdx, rsi; unsigned __int16 *
0x1800036c7  mov     rcx, rax; this
0x1800036ca  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800036cf  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800036d3  test    r9, r9
0x1800036d6  jz      short loc_1800036EA
0x1800036d8  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800036df  mov     rdx, rsi; unsigned __int16 *
0x1800036e2  mov     rcx, rax; this
0x1800036e5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800036ea  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800036ee  test    r9, r9
0x1800036f1  jz      short loc_180003705
0x1800036f3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800036fa  mov     rdx, rsi; unsigned __int16 *
0x1800036fd  mov     rcx, rax; this
0x180003700  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003705  mov     rcx, [rbx+28h]
0x180003709  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000370d  mov     rdx, rsi; unsigned __int16 *
0x180003710  test    rcx, rcx
0x180003713  jz      short loc_18000372B
0x180003715  mov     [rsp+278h+lpBuffer], rcx
0x18000371a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180003721  mov     rcx, rax; this
0x180003724  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003729  jmp     short loc_18000374D
0x18000372b  mov     rcx, rax; this
0x18000372e  test    r9, r9
0x180003731  jz      short loc_180003741
0x180003733  lea     r8, aHs; "[%hs]\n"
0x18000373a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000373f  jmp     short loc_18000374D
0x180003741  lea     r8, asc_180008798; "\n"
0x180003748  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000374d  xor     eax, eax
0x18000374f  mov     rcx, [rsp+278h+var_38]
0x180003757  xor     rcx, rsp; StackCookie
0x18000375a  call    __security_check_cookie
0x18000375f  mov     rbx, [rsp+278h+arg_18]
0x180003767  add     rsp, 250h
0x18000376e  pop     r15
0x180003770  pop     r14
0x180003772  pop     rdi
0x180003773  pop     rsi
0x180003774  pop     rbp
0x180003775  retn
```
