# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1400073e4`
- end: `0x14000769a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x140003bd8`
- `0x140003e58`
- `0x1400086ac`
- `0x14000d240`
- `0x1400100bc`
- `0x1400101f0`

## callees

- `0x140002190`
- `0x140002c2c`
- `0x1400073e4`
- `0x1400089ac`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140007597`
- `KERNEL32!GetCurrentThreadId` at `0x140007597`
- `KERNEL32!FormatMessageW` at `0x140007516`
- `KERNEL32!FormatMessageW` at `0x140007516`

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
          v7 = (const char *)&byte_140013800;
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
0x1400073e4  mov     [rsp+arg_18], rbx
0x1400073e9  push    rbp
0x1400073ea  push    rsi
0x1400073eb  push    rdi
0x1400073ec  push    r14
0x1400073ee  push    r15
0x1400073f0  sub     rsp, 250h
0x1400073f7  mov     rax, cs:__security_cookie
0x1400073fe  xor     rax, rsp
0x140007401  mov     [rsp+278h+var_38], rax
0x140007409  mov     rbx, r8
0x14000740c  mov     rsi, rdx
0x14000740f  mov     r14, rcx
0x140007412  xor     r15d, r15d
0x140007415  test    rdx, rdx
0x140007418  jz      loc_140007671
0x14000741e  test    rcx, rcx
0x140007421  jz      loc_140007671
0x140007427  mov     [rcx], r15w
0x14000742b  mov     rax, cs:g_pfnResultLoggingCallback
0x140007432  test    rax, rax
0x140007435  jz      short loc_140007458
0x140007437  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000743e  jz      short loc_140007458
0x140007440  mov     r8, rdx
0x140007443  mov     rdx, rcx
0x140007446  mov     rcx, rbx
0x140007449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000744e  cmp     [r14], r15w
0x140007452  jnz     loc_140007671
0x140007458  mov     ecx, [rbx]
0x14000745a  mov     bpl, 8
0x14000745d  test    ecx, ecx
0x14000745f  jz      short loc_1400074AA
0x140007461  sub     ecx, 1
0x140007464  jz      short loc_140007492
0x140007466  sub     ecx, 1
0x140007469  jz      short loc_140007482
0x14000746b  cmp     ecx, 1
0x14000746e  jz      short loc_140007479
0x140007470  lea     rdi, byte_140013800
0x140007477  jmp     short loc_1400074B1
0x140007479  lea     rdi, aFailfast; "FailFast"
0x140007480  jmp     short loc_1400074B1
0x140007482  lea     rax, aLoghr; "LogHr"
0x140007489  lea     rdi, aLognt; "LogNt"
0x140007490  jmp     short loc_1400074A0
0x140007492  lea     rax, aReturnhr; "ReturnHr"
0x140007499  lea     rdi, aReturnnt; "ReturnNt"
0x1400074a0  test    [rbx+4], bpl
0x1400074a4  cmovz   rdi, rax
0x1400074a8  jmp     short loc_1400074B1
0x1400074aa  lea     rdi, aException; "Exception"
0x1400074b1  xor     edx, edx; Val
0x1400074b3  mov     r8d, 200h; Size
0x1400074b9  lea     rcx, [rsp+278h+Buffer]; void *
0x1400074be  call    memset_0
0x1400074c3  test    [rbx+4], bpl
0x1400074c7  jz      short loc_1400074EC
0x1400074c9  mov     ebp, [rbx+0Ch]
0x1400074cc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1400074d3  test    rax, rax
0x1400074d6  jz      short loc_14000751C
0x1400074d8  mov     r8d, 100h
0x1400074de  lea     rdx, [rsp+278h+Buffer]
0x1400074e3  mov     ecx, ebp
0x1400074e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400074ea  jmp     short loc_14000751C
0x1400074ec  mov     ebp, [rbx+8]
0x1400074ef  mov     [rsp+278h+Arguments], r15; Arguments
0x1400074f4  mov     [rsp+278h+nSize], 100h; nSize
0x1400074fc  lea     rax, [rsp+278h+Buffer]
0x140007501  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140007506  mov     r9d, 400h; dwLanguageId
0x14000750c  mov     r8d, ebp; dwMessageId
0x14000750f  xor     edx, edx; lpSource
0x140007511  mov     ecx, 1200h; dwFlags
0x140007516  call    cs:__imp_FormatMessageW
0x14000751c  lea     rsi, [r14+rsi*2]
0x140007520  mov     r9, [rbx+38h]; unsigned __int16 *
0x140007524  mov     rax, [rbx+88h]
0x14000752b  mov     rcx, [rbx+80h]
0x140007532  mov     rdx, rsi; unsigned __int16 *
0x140007535  test    r9, r9
0x140007538  jz      short loc_14000755C
0x14000753a  mov     [rsp+278h+Arguments], rax
0x14000753f  mov     qword ptr [rsp+278h+nSize], rcx
0x140007544  mov     eax, [rbx+40h]
0x140007547  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000754b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140007552  mov     rcx, r14; this
0x140007555  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000755a  jmp     short loc_140007573
0x14000755c  mov     [rsp+278h+lpBuffer], rax
0x140007561  mov     r9, rcx; unsigned __int16 *
0x140007564  lea     r8, aHsP; "%hs!%p: "
0x14000756b  mov     rcx, r14; this
0x14000756e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140007573  mov     r14, rax
0x140007576  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000757d  test    r9, r9
0x140007580  jz      short loc_140007597
0x140007582  lea     r8, aCallerP; "(caller: %p) "
0x140007589  mov     rdx, rsi; unsigned __int16 *
0x14000758c  mov     rcx, rax; this
0x14000758f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140007594  mov     r14, rax
0x140007597  call    cs:__imp_GetCurrentThreadId
0x14000759d  lea     rcx, [rsp+278h+Buffer]
0x1400075a2  mov     [rsp+278h+var_240], rcx
0x1400075a7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1400075ab  mov     [rsp+278h+nSize], eax
0x1400075af  mov     eax, [rbx+44h]
0x1400075b2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400075b6  mov     r9, rdi; unsigned __int16 *
0x1400075b9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1400075c0  mov     rdx, rsi; unsigned __int16 *
0x1400075c3  mov     rcx, r14; this
0x1400075c6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400075cb  cmp     [rbx+18h], r15
0x1400075cf  jnz     short loc_1400075E1
0x1400075d1  cmp     [rbx+48h], r15
0x1400075d5  jnz     short loc_1400075E1
0x1400075d7  cmp     [rbx+30h], r15
0x1400075db  jz      loc_140007671
0x1400075e1  lea     r8, asc_140012E98; "    "
0x1400075e8  mov     rdx, rsi; unsigned __int16 *
0x1400075eb  mov     rcx, rax; this
0x1400075ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400075f3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1400075f7  test    r9, r9
0x1400075fa  jz      short loc_14000760E
0x1400075fc  lea     r8, aMsgWs; "Msg:[%ws] "
0x140007603  mov     rdx, rsi; unsigned __int16 *
0x140007606  mov     rcx, rax; this
0x140007609  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000760e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140007612  test    r9, r9
0x140007615  jz      short loc_140007629
0x140007617  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000761e  mov     rdx, rsi; unsigned __int16 *
0x140007621  mov     rcx, rax; this
0x140007624  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140007629  mov     rcx, [rbx+28h]
0x14000762d  mov     r9, [rbx+30h]; unsigned __int16 *
0x140007631  mov     rdx, rsi; unsigned __int16 *
0x140007634  test    rcx, rcx
0x140007637  jz      short loc_14000764F
0x140007639  mov     [rsp+278h+lpBuffer], rcx
0x14000763e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140007645  mov     rcx, rax; this
0x140007648  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000764d  jmp     short loc_140007671
0x14000764f  mov     rcx, rax; this
0x140007652  test    r9, r9
0x140007655  jz      short loc_140007665
0x140007657  lea     r8, aHs; "[%hs]\n"
0x14000765e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140007663  jmp     short loc_140007671
0x140007665  lea     r8, asc_140012F10; "\n"
0x14000766c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140007671  xor     eax, eax
0x140007673  mov     rcx, [rsp+278h+var_38]
0x14000767b  xor     rcx, rsp; StackCookie
0x14000767e  call    __security_check_cookie
0x140007683  mov     rbx, [rsp+278h+arg_18]
0x14000768b  add     rsp, 250h
0x140007692  pop     r15
0x140007694  pop     r14
0x140007696  pop     rdi
0x140007697  pop     rsi
0x140007698  pop     rbp
0x140007699  retn
```
