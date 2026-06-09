# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800067f4`
- end: `0x180006aaa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800035f4`
- `0x18000385c`
- `0x1800078c4`
- `0x18000c8f0`

## callees

- `0x180002270`
- `0x180002be8`
- `0x1800067f4`
- `0x180007bc4`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800069a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800069a7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006926`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006926`

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
          v7 = (const char *)&byte_180016B57;
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
0x1800067f4  mov     [rsp+arg_18], rbx
0x1800067f9  push    rbp
0x1800067fa  push    rsi
0x1800067fb  push    rdi
0x1800067fc  push    r14
0x1800067fe  push    r15
0x180006800  sub     rsp, 250h
0x180006807  mov     rax, cs:__security_cookie
0x18000680e  xor     rax, rsp
0x180006811  mov     [rsp+278h+var_38], rax
0x180006819  mov     rbx, r8
0x18000681c  mov     rsi, rdx
0x18000681f  mov     r14, rcx
0x180006822  xor     r15d, r15d
0x180006825  test    rdx, rdx
0x180006828  jz      loc_180006A81
0x18000682e  test    rcx, rcx
0x180006831  jz      loc_180006A81
0x180006837  mov     [rcx], r15w
0x18000683b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006842  test    rax, rax
0x180006845  jz      short loc_180006868
0x180006847  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000684e  jz      short loc_180006868
0x180006850  mov     r8, rdx
0x180006853  mov     rdx, rcx
0x180006856  mov     rcx, rbx
0x180006859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000685e  cmp     [r14], r15w
0x180006862  jnz     loc_180006A81
0x180006868  mov     ecx, [rbx]
0x18000686a  mov     bpl, 8
0x18000686d  test    ecx, ecx
0x18000686f  jz      short loc_1800068BA
0x180006871  sub     ecx, 1
0x180006874  jz      short loc_1800068A2
0x180006876  sub     ecx, 1
0x180006879  jz      short loc_180006892
0x18000687b  cmp     ecx, 1
0x18000687e  jz      short loc_180006889
0x180006880  lea     rdi, byte_180016B57
0x180006887  jmp     short loc_1800068C1
0x180006889  lea     rdi, aFailfast; "FailFast"
0x180006890  jmp     short loc_1800068C1
0x180006892  lea     rax, aLoghr; "LogHr"
0x180006899  lea     rdi, aLognt; "LogNt"
0x1800068a0  jmp     short loc_1800068B0
0x1800068a2  lea     rax, aReturnhr; "ReturnHr"
0x1800068a9  lea     rdi, aReturnnt; "ReturnNt"
0x1800068b0  test    [rbx+4], bpl
0x1800068b4  cmovz   rdi, rax
0x1800068b8  jmp     short loc_1800068C1
0x1800068ba  lea     rdi, aException; "Exception"
0x1800068c1  xor     edx, edx; Val
0x1800068c3  mov     r8d, 200h; Size
0x1800068c9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800068ce  call    memset_0
0x1800068d3  test    [rbx+4], bpl
0x1800068d7  jz      short loc_1800068FC
0x1800068d9  mov     ebp, [rbx+0Ch]
0x1800068dc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800068e3  test    rax, rax
0x1800068e6  jz      short loc_18000692C
0x1800068e8  mov     r8d, 100h
0x1800068ee  lea     rdx, [rsp+278h+Buffer]
0x1800068f3  mov     ecx, ebp
0x1800068f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068fa  jmp     short loc_18000692C
0x1800068fc  mov     ebp, [rbx+8]
0x1800068ff  mov     [rsp+278h+Arguments], r15; Arguments
0x180006904  mov     [rsp+278h+nSize], 100h; nSize
0x18000690c  lea     rax, [rsp+278h+Buffer]
0x180006911  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006916  mov     r9d, 400h; dwLanguageId
0x18000691c  mov     r8d, ebp; dwMessageId
0x18000691f  xor     edx, edx; lpSource
0x180006921  mov     ecx, 1200h; dwFlags
0x180006926  call    cs:__imp_FormatMessageW
0x18000692c  lea     rsi, [r14+rsi*2]
0x180006930  mov     r9, [rbx+38h]; unsigned __int16 *
0x180006934  mov     rax, [rbx+88h]
0x18000693b  mov     rcx, [rbx+80h]
0x180006942  mov     rdx, rsi; unsigned __int16 *
0x180006945  test    r9, r9
0x180006948  jz      short loc_18000696C
0x18000694a  mov     [rsp+278h+Arguments], rax
0x18000694f  mov     qword ptr [rsp+278h+nSize], rcx
0x180006954  mov     eax, [rbx+40h]
0x180006957  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000695b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006962  mov     rcx, r14; this
0x180006965  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000696a  jmp     short loc_180006983
0x18000696c  mov     [rsp+278h+lpBuffer], rax
0x180006971  mov     r9, rcx; unsigned __int16 *
0x180006974  lea     r8, aHsP; "%hs!%p: "
0x18000697b  mov     rcx, r14; this
0x18000697e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006983  mov     r14, rax
0x180006986  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000698d  test    r9, r9
0x180006990  jz      short loc_1800069A7
0x180006992  lea     r8, aCallerP; "(caller: %p) "
0x180006999  mov     rdx, rsi; unsigned __int16 *
0x18000699c  mov     rcx, rax; this
0x18000699f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800069a4  mov     r14, rax
0x1800069a7  call    cs:__imp_GetCurrentThreadId
0x1800069ad  lea     rcx, [rsp+278h+Buffer]
0x1800069b2  mov     [rsp+278h+var_240], rcx
0x1800069b7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800069bb  mov     [rsp+278h+nSize], eax
0x1800069bf  mov     eax, [rbx+44h]
0x1800069c2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800069c6  mov     r9, rdi; unsigned __int16 *
0x1800069c9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800069d0  mov     rdx, rsi; unsigned __int16 *
0x1800069d3  mov     rcx, r14; this
0x1800069d6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800069db  cmp     [rbx+18h], r15
0x1800069df  jnz     short loc_1800069F1
0x1800069e1  cmp     [rbx+48h], r15
0x1800069e5  jnz     short loc_1800069F1
0x1800069e7  cmp     [rbx+30h], r15
0x1800069eb  jz      loc_180006A81
0x1800069f1  lea     r8, asc_180016C68; "    "
0x1800069f8  mov     rdx, rsi; unsigned __int16 *
0x1800069fb  mov     rcx, rax; this
0x1800069fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006a03  mov     r9, [rbx+18h]; unsigned __int16 *
0x180006a07  test    r9, r9
0x180006a0a  jz      short loc_180006A1E
0x180006a0c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006a13  mov     rdx, rsi; unsigned __int16 *
0x180006a16  mov     rcx, rax; this
0x180006a19  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006a1e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180006a22  test    r9, r9
0x180006a25  jz      short loc_180006A39
0x180006a27  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180006a2e  mov     rdx, rsi; unsigned __int16 *
0x180006a31  mov     rcx, rax; this
0x180006a34  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006a39  mov     rcx, [rbx+28h]
0x180006a3d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006a41  mov     rdx, rsi; unsigned __int16 *
0x180006a44  test    rcx, rcx
0x180006a47  jz      short loc_180006A5F
0x180006a49  mov     [rsp+278h+lpBuffer], rcx
0x180006a4e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006a55  mov     rcx, rax; this
0x180006a58  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006a5d  jmp     short loc_180006A81
0x180006a5f  mov     rcx, rax; this
0x180006a62  test    r9, r9
0x180006a65  jz      short loc_180006A75
0x180006a67  lea     r8, aHs; "[%hs]\n"
0x180006a6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006a73  jmp     short loc_180006A81
0x180006a75  lea     r8, asc_180016CE0; "\n"
0x180006a7c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006a81  xor     eax, eax
0x180006a83  mov     rcx, [rsp+278h+var_38]
0x180006a8b  xor     rcx, rsp; StackCookie
0x180006a8e  call    __security_check_cookie
0x180006a93  mov     rbx, [rsp+278h+arg_18]
0x180006a9b  add     rsp, 250h
0x180006aa2  pop     r15
0x180006aa4  pop     r14
0x180006aa6  pop     rdi
0x180006aa7  pop     rsi
0x180006aa8  pop     rbp
0x180006aa9  retn
```
