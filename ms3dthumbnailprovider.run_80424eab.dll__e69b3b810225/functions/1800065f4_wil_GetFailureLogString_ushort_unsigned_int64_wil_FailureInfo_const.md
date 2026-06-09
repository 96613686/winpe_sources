# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800065f4`
- end: `0x1800068aa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800047a4`
- `0x180004a14`
- `0x1800070fc`
- `0x180009ae0`

## callees

- `0x180001ef0`
- `0x180002954`
- `0x1800065f4`
- `0x1800073fc`
- `0x18000b010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180006726`
- `KERNEL32!FormatMessageW` at `0x180006726`
- `KERNEL32!GetCurrentThreadId` at `0x1800067a7`
- `KERNEL32!GetCurrentThreadId` at `0x1800067a7`

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
          v7 = (const char *)&byte_18000CFC0;
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
0x1800065f4  mov     [rsp+arg_18], rbx
0x1800065f9  push    rbp
0x1800065fa  push    rsi
0x1800065fb  push    rdi
0x1800065fc  push    r14
0x1800065fe  push    r15
0x180006600  sub     rsp, 250h
0x180006607  mov     rax, cs:__security_cookie
0x18000660e  xor     rax, rsp
0x180006611  mov     [rsp+278h+var_38], rax
0x180006619  mov     rbx, r8
0x18000661c  mov     rsi, rdx
0x18000661f  mov     r14, rcx
0x180006622  xor     r15d, r15d
0x180006625  test    rdx, rdx
0x180006628  jz      loc_180006881
0x18000662e  test    rcx, rcx
0x180006631  jz      loc_180006881
0x180006637  mov     [rcx], r15w
0x18000663b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006642  test    rax, rax
0x180006645  jz      short loc_180006668
0x180006647  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000664e  jz      short loc_180006668
0x180006650  mov     r8, rdx
0x180006653  mov     rdx, rcx
0x180006656  mov     rcx, rbx
0x180006659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000665e  cmp     [r14], r15w
0x180006662  jnz     loc_180006881
0x180006668  mov     ecx, [rbx]
0x18000666a  mov     bpl, 8
0x18000666d  test    ecx, ecx
0x18000666f  jz      short loc_1800066BA
0x180006671  sub     ecx, 1
0x180006674  jz      short loc_1800066A2
0x180006676  sub     ecx, 1
0x180006679  jz      short loc_180006692
0x18000667b  cmp     ecx, 1
0x18000667e  jz      short loc_180006689
0x180006680  lea     rdi, byte_18000CFC0
0x180006687  jmp     short loc_1800066C1
0x180006689  lea     rdi, aFailfast; "FailFast"
0x180006690  jmp     short loc_1800066C1
0x180006692  lea     rax, aLoghr; "LogHr"
0x180006699  lea     rdi, aLognt; "LogNt"
0x1800066a0  jmp     short loc_1800066B0
0x1800066a2  lea     rax, aReturnhr; "ReturnHr"
0x1800066a9  lea     rdi, aReturnnt; "ReturnNt"
0x1800066b0  test    [rbx+4], bpl
0x1800066b4  cmovz   rdi, rax
0x1800066b8  jmp     short loc_1800066C1
0x1800066ba  lea     rdi, aException; "Exception"
0x1800066c1  xor     edx, edx; Val
0x1800066c3  mov     r8d, 200h; Size
0x1800066c9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800066ce  call    memset_0
0x1800066d3  test    [rbx+4], bpl
0x1800066d7  jz      short loc_1800066FC
0x1800066d9  mov     ebp, [rbx+0Ch]
0x1800066dc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800066e3  test    rax, rax
0x1800066e6  jz      short loc_18000672C
0x1800066e8  mov     r8d, 100h
0x1800066ee  lea     rdx, [rsp+278h+Buffer]
0x1800066f3  mov     ecx, ebp
0x1800066f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066fa  jmp     short loc_18000672C
0x1800066fc  mov     ebp, [rbx+8]
0x1800066ff  mov     [rsp+278h+Arguments], r15; Arguments
0x180006704  mov     [rsp+278h+nSize], 100h; nSize
0x18000670c  lea     rax, [rsp+278h+Buffer]
0x180006711  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006716  mov     r9d, 400h; dwLanguageId
0x18000671c  mov     r8d, ebp; dwMessageId
0x18000671f  xor     edx, edx; lpSource
0x180006721  mov     ecx, 1200h; dwFlags
0x180006726  call    cs:__imp_FormatMessageW
0x18000672c  lea     rsi, [r14+rsi*2]
0x180006730  mov     r9, [rbx+38h]; unsigned __int16 *
0x180006734  mov     rax, [rbx+88h]
0x18000673b  mov     rcx, [rbx+80h]
0x180006742  mov     rdx, rsi; unsigned __int16 *
0x180006745  test    r9, r9
0x180006748  jz      short loc_18000676C
0x18000674a  mov     [rsp+278h+Arguments], rax
0x18000674f  mov     qword ptr [rsp+278h+nSize], rcx
0x180006754  mov     eax, [rbx+40h]
0x180006757  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000675b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006762  mov     rcx, r14; this
0x180006765  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000676a  jmp     short loc_180006783
0x18000676c  mov     [rsp+278h+lpBuffer], rax
0x180006771  mov     r9, rcx; unsigned __int16 *
0x180006774  lea     r8, aHsP; "%hs!%p: "
0x18000677b  mov     rcx, r14; this
0x18000677e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006783  mov     r14, rax
0x180006786  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000678d  test    r9, r9
0x180006790  jz      short loc_1800067A7
0x180006792  lea     r8, aCallerP; "(caller: %p) "
0x180006799  mov     rdx, rsi; unsigned __int16 *
0x18000679c  mov     rcx, rax; this
0x18000679f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800067a4  mov     r14, rax
0x1800067a7  call    cs:__imp_GetCurrentThreadId
0x1800067ad  lea     rcx, [rsp+278h+Buffer]
0x1800067b2  mov     [rsp+278h+var_240], rcx
0x1800067b7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800067bb  mov     [rsp+278h+nSize], eax
0x1800067bf  mov     eax, [rbx+44h]
0x1800067c2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800067c6  mov     r9, rdi; unsigned __int16 *
0x1800067c9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800067d0  mov     rdx, rsi; unsigned __int16 *
0x1800067d3  mov     rcx, r14; this
0x1800067d6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800067db  cmp     [rbx+18h], r15
0x1800067df  jnz     short loc_1800067F1
0x1800067e1  cmp     [rbx+48h], r15
0x1800067e5  jnz     short loc_1800067F1
0x1800067e7  cmp     [rbx+30h], r15
0x1800067eb  jz      loc_180006881
0x1800067f1  lea     r8, asc_18000D0B0; "    "
0x1800067f8  mov     rdx, rsi; unsigned __int16 *
0x1800067fb  mov     rcx, rax; this
0x1800067fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006803  mov     r9, [rbx+18h]; unsigned __int16 *
0x180006807  test    r9, r9
0x18000680a  jz      short loc_18000681E
0x18000680c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006813  mov     rdx, rsi; unsigned __int16 *
0x180006816  mov     rcx, rax; this
0x180006819  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000681e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180006822  test    r9, r9
0x180006825  jz      short loc_180006839
0x180006827  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000682e  mov     rdx, rsi; unsigned __int16 *
0x180006831  mov     rcx, rax; this
0x180006834  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006839  mov     rcx, [rbx+28h]
0x18000683d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006841  mov     rdx, rsi; unsigned __int16 *
0x180006844  test    rcx, rcx
0x180006847  jz      short loc_18000685F
0x180006849  mov     [rsp+278h+lpBuffer], rcx
0x18000684e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006855  mov     rcx, rax; this
0x180006858  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000685d  jmp     short loc_180006881
0x18000685f  mov     rcx, rax; this
0x180006862  test    r9, r9
0x180006865  jz      short loc_180006875
0x180006867  lea     r8, aHs; "[%hs]\n"
0x18000686e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006873  jmp     short loc_180006881
0x180006875  lea     r8, asc_18000D128; "\n"
0x18000687c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006881  xor     eax, eax
0x180006883  mov     rcx, [rsp+278h+var_38]
0x18000688b  xor     rcx, rsp; StackCookie
0x18000688e  call    __security_check_cookie
0x180006893  mov     rbx, [rsp+278h+arg_18]
0x18000689b  add     rsp, 250h
0x1800068a2  pop     r15
0x1800068a4  pop     r14
0x1800068a6  pop     rdi
0x1800068a7  pop     rsi
0x1800068a8  pop     rbp
0x1800068a9  retn
```
