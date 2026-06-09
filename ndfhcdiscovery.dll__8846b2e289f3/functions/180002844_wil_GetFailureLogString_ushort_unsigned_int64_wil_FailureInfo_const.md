# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180002844`
- end: `0x180002b07`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180003ce0`
- `0x18000b484`

## callees

- `0x180002844`
- `0x180002e0c`
- `0x180013686`
- `0x1800136b0`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800029fd`
- `KERNEL32!GetCurrentThreadId` at `0x1800029fd`
- `KERNEL32!FormatMessageW` at `0x180002976`
- `KERNEL32!FormatMessageW` at `0x180002976`

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
          v7 = (const char *)&word_18001855E;
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
0x180002844  mov     [rsp+arg_18], rbx
0x180002849  push    rbp
0x18000284a  push    rsi
0x18000284b  push    rdi
0x18000284c  push    r14
0x18000284e  push    r15
0x180002850  sub     rsp, 250h
0x180002857  mov     rax, cs:__security_cookie
0x18000285e  xor     rax, rsp
0x180002861  mov     [rsp+278h+var_38], rax
0x180002869  mov     rbx, r8
0x18000286c  mov     rsi, rdx
0x18000286f  mov     r14, rcx
0x180002872  xor     r15d, r15d
0x180002875  test    rdx, rdx
0x180002878  jz      loc_180002ADD
0x18000287e  test    rcx, rcx
0x180002881  jz      loc_180002ADD
0x180002887  mov     [rcx], r15w
0x18000288b  mov     rax, cs:g_pfnResultLoggingCallback
0x180002892  test    rax, rax
0x180002895  jz      short loc_1800028B8
0x180002897  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000289e  jz      short loc_1800028B8
0x1800028a0  mov     r8, rdx
0x1800028a3  mov     rdx, rcx
0x1800028a6  mov     rcx, rbx
0x1800028a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028ae  cmp     [r14], r15w
0x1800028b2  jnz     loc_180002ADD
0x1800028b8  mov     ecx, [rbx]
0x1800028ba  mov     bpl, 8
0x1800028bd  test    ecx, ecx
0x1800028bf  jz      short loc_18000290A
0x1800028c1  sub     ecx, 1
0x1800028c4  jz      short loc_1800028F2
0x1800028c6  sub     ecx, 1
0x1800028c9  jz      short loc_1800028E2
0x1800028cb  cmp     ecx, 1
0x1800028ce  jz      short loc_1800028D9
0x1800028d0  lea     rdi, word_18001855E
0x1800028d7  jmp     short loc_180002911
0x1800028d9  lea     rdi, aFailfast; "FailFast"
0x1800028e0  jmp     short loc_180002911
0x1800028e2  lea     rax, aLoghr; "LogHr"
0x1800028e9  lea     rdi, aLognt; "LogNt"
0x1800028f0  jmp     short loc_180002900
0x1800028f2  lea     rax, aReturnhr; "ReturnHr"
0x1800028f9  lea     rdi, aReturnnt; "ReturnNt"
0x180002900  test    [rbx+4], bpl
0x180002904  cmovz   rdi, rax
0x180002908  jmp     short loc_180002911
0x18000290a  lea     rdi, aException; "Exception"
0x180002911  xor     edx, edx; Val
0x180002913  mov     r8d, 200h; Size
0x180002919  lea     rcx, [rsp+278h+Buffer]; void *
0x18000291e  call    memset_0
0x180002923  test    [rbx+4], bpl
0x180002927  jz      short loc_18000294C
0x180002929  mov     ebp, [rbx+0Ch]
0x18000292c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180002933  test    rax, rax
0x180002936  jz      short loc_180002982
0x180002938  mov     r8d, 100h
0x18000293e  lea     rdx, [rsp+278h+Buffer]
0x180002943  mov     ecx, ebp
0x180002945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000294a  jmp     short loc_180002982
0x18000294c  mov     ebp, [rbx+8]
0x18000294f  mov     [rsp+278h+Arguments], r15; Arguments
0x180002954  mov     [rsp+278h+nSize], 100h; nSize
0x18000295c  lea     rax, [rsp+278h+Buffer]
0x180002961  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180002966  mov     r9d, 400h; dwLanguageId
0x18000296c  mov     r8d, ebp; dwMessageId
0x18000296f  xor     edx, edx; lpSource
0x180002971  mov     ecx, 1200h; dwFlags
0x180002976  call    cs:__imp_FormatMessageW
0x18000297d  nop     dword ptr [rax+rax+00h]
0x180002982  lea     rsi, [r14+rsi*2]
0x180002986  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000298a  mov     rax, [rbx+88h]
0x180002991  mov     rcx, [rbx+80h]
0x180002998  mov     rdx, rsi; unsigned __int16 *
0x18000299b  test    r9, r9
0x18000299e  jz      short loc_1800029C2
0x1800029a0  mov     [rsp+278h+Arguments], rax
0x1800029a5  mov     qword ptr [rsp+278h+nSize], rcx
0x1800029aa  mov     eax, [rbx+40h]
0x1800029ad  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800029b1  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800029b8  mov     rcx, r14; this
0x1800029bb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800029c0  jmp     short loc_1800029D9
0x1800029c2  mov     [rsp+278h+lpBuffer], rax
0x1800029c7  mov     r9, rcx; unsigned __int16 *
0x1800029ca  lea     r8, aHsP; "%hs!%p: "
0x1800029d1  mov     rcx, r14; this
0x1800029d4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800029d9  mov     r14, rax
0x1800029dc  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800029e3  test    r9, r9
0x1800029e6  jz      short loc_1800029FD
0x1800029e8  lea     r8, aCallerP; "(caller: %p) "
0x1800029ef  mov     rdx, rsi; unsigned __int16 *
0x1800029f2  mov     rcx, rax; this
0x1800029f5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800029fa  mov     r14, rax
0x1800029fd  call    cs:__imp_GetCurrentThreadId
0x180002a04  nop     dword ptr [rax+rax+00h]
0x180002a09  lea     rcx, [rsp+278h+Buffer]
0x180002a0e  mov     [rsp+278h+var_240], rcx
0x180002a13  mov     dword ptr [rsp+278h+Arguments], ebp
0x180002a17  mov     [rsp+278h+nSize], eax
0x180002a1b  mov     eax, [rbx+44h]
0x180002a1e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180002a22  mov     r9, rdi; unsigned __int16 *
0x180002a25  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180002a2c  mov     rdx, rsi; unsigned __int16 *
0x180002a2f  mov     rcx, r14; this
0x180002a32  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002a37  cmp     [rbx+18h], r15
0x180002a3b  jnz     short loc_180002A4D
0x180002a3d  cmp     [rbx+48h], r15
0x180002a41  jnz     short loc_180002A4D
0x180002a43  cmp     [rbx+30h], r15
0x180002a47  jz      loc_180002ADD
0x180002a4d  lea     r8, asc_180018690; "    "
0x180002a54  mov     rdx, rsi; unsigned __int16 *
0x180002a57  mov     rcx, rax; this
0x180002a5a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002a5f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180002a63  test    r9, r9
0x180002a66  jz      short loc_180002A7A
0x180002a68  lea     r8, aMsgWs; "Msg:[%ws] "
0x180002a6f  mov     rdx, rsi; unsigned __int16 *
0x180002a72  mov     rcx, rax; this
0x180002a75  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002a7a  mov     r9, [rbx+48h]; unsigned __int16 *
0x180002a7e  test    r9, r9
0x180002a81  jz      short loc_180002A95
0x180002a83  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180002a8a  mov     rdx, rsi; unsigned __int16 *
0x180002a8d  mov     rcx, rax; this
0x180002a90  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002a95  mov     rcx, [rbx+28h]
0x180002a99  mov     r9, [rbx+30h]; unsigned __int16 *
0x180002a9d  mov     rdx, rsi; unsigned __int16 *
0x180002aa0  test    rcx, rcx
0x180002aa3  jz      short loc_180002ABB
0x180002aa5  mov     [rsp+278h+lpBuffer], rcx
0x180002aaa  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180002ab1  mov     rcx, rax; this
0x180002ab4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002ab9  jmp     short loc_180002ADD
0x180002abb  mov     rcx, rax; this
0x180002abe  test    r9, r9
0x180002ac1  jz      short loc_180002AD1
0x180002ac3  lea     r8, aHs; "[%hs]\n"
0x180002aca  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002acf  jmp     short loc_180002ADD
0x180002ad1  lea     r8, asc_180018708; "\n"
0x180002ad8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002add  xor     eax, eax
0x180002adf  mov     rcx, [rsp+278h+var_38]
0x180002ae7  xor     rcx, rsp; StackCookie
0x180002aea  call    __security_check_cookie
0x180002aef  mov     rbx, [rsp+278h+arg_18]
0x180002af7  add     rsp, 250h
0x180002afe  pop     r15
0x180002b00  pop     r14
0x180002b02  pop     rdi
0x180002b03  pop     rsi
0x180002b04  pop     rbp
0x180002b05  retn
```
