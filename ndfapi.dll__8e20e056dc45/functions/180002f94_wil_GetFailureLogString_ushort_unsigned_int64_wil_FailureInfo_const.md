# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180002f94`
- end: `0x18000324a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180003f40`
- `0x180007b54`
- `0x1800092bc`
- `0x18000fdb8`

## callees

- `0x180002f94`
- `0x180003540`
- `0x18001f652`
- `0x18001f690`
- `0x180021010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180003147`
- `KERNEL32!GetCurrentThreadId` at `0x180003147`
- `KERNEL32!FormatMessageW` at `0x1800030c6`
- `KERNEL32!FormatMessageW` at `0x1800030c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
          v7 = (const char *)&word_180025E76;
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
0x180002f94  mov     [rsp+arg_18], rbx
0x180002f99  push    rbp
0x180002f9a  push    rsi
0x180002f9b  push    rdi
0x180002f9c  push    r14
0x180002f9e  push    r15
0x180002fa0  sub     rsp, 250h
0x180002fa7  mov     rax, cs:__security_cookie
0x180002fae  xor     rax, rsp
0x180002fb1  mov     [rsp+278h+var_38], rax
0x180002fb9  mov     rbx, r8
0x180002fbc  mov     rsi, rdx
0x180002fbf  mov     r14, rcx
0x180002fc2  xor     r15d, r15d
0x180002fc5  test    rdx, rdx
0x180002fc8  jz      loc_180003221
0x180002fce  test    rcx, rcx
0x180002fd1  jz      loc_180003221
0x180002fd7  mov     [rcx], r15w
0x180002fdb  mov     rax, cs:g_pfnResultLoggingCallback
0x180002fe2  test    rax, rax
0x180002fe5  jz      short loc_180003008
0x180002fe7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002fee  jz      short loc_180003008
0x180002ff0  mov     r8, rdx
0x180002ff3  mov     rdx, rcx
0x180002ff6  mov     rcx, rbx
0x180002ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ffe  cmp     [r14], r15w
0x180003002  jnz     loc_180003221
0x180003008  mov     ecx, [rbx]
0x18000300a  mov     bpl, 8
0x18000300d  test    ecx, ecx
0x18000300f  jz      short loc_18000305A
0x180003011  sub     ecx, 1
0x180003014  jz      short loc_180003042
0x180003016  sub     ecx, 1
0x180003019  jz      short loc_180003032
0x18000301b  cmp     ecx, 1
0x18000301e  jz      short loc_180003029
0x180003020  lea     rdi, word_180025E76
0x180003027  jmp     short loc_180003061
0x180003029  lea     rdi, aFailfast; "FailFast"
0x180003030  jmp     short loc_180003061
0x180003032  lea     rax, aLoghr; "LogHr"
0x180003039  lea     rdi, aLognt; "LogNt"
0x180003040  jmp     short loc_180003050
0x180003042  lea     rax, aReturnhr; "ReturnHr"
0x180003049  lea     rdi, aReturnnt; "ReturnNt"
0x180003050  test    [rbx+4], bpl
0x180003054  cmovz   rdi, rax
0x180003058  jmp     short loc_180003061
0x18000305a  lea     rdi, aException; "Exception"
0x180003061  xor     edx, edx; Val
0x180003063  mov     r8d, 200h; Size
0x180003069  lea     rcx, [rsp+278h+Buffer]; void *
0x18000306e  call    memset_0
0x180003073  test    [rbx+4], bpl
0x180003077  jz      short loc_18000309C
0x180003079  mov     ebp, [rbx+0Ch]
0x18000307c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180003083  test    rax, rax
0x180003086  jz      short loc_1800030CC
0x180003088  mov     r8d, 100h
0x18000308e  lea     rdx, [rsp+278h+Buffer]
0x180003093  mov     ecx, ebp
0x180003095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000309a  jmp     short loc_1800030CC
0x18000309c  mov     ebp, [rbx+8]
0x18000309f  mov     [rsp+278h+Arguments], r15; Arguments
0x1800030a4  mov     [rsp+278h+nSize], 100h; nSize
0x1800030ac  lea     rax, [rsp+278h+Buffer]
0x1800030b1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800030b6  mov     r9d, 400h; dwLanguageId
0x1800030bc  mov     r8d, ebp; dwMessageId
0x1800030bf  xor     edx, edx; lpSource
0x1800030c1  mov     ecx, 1200h; dwFlags
0x1800030c6  call    cs:__imp_FormatMessageW
0x1800030cc  lea     rsi, [r14+rsi*2]
0x1800030d0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800030d4  mov     rax, [rbx+88h]
0x1800030db  mov     rcx, [rbx+80h]
0x1800030e2  mov     rdx, rsi; unsigned __int16 *
0x1800030e5  test    r9, r9
0x1800030e8  jz      short loc_18000310C
0x1800030ea  mov     [rsp+278h+Arguments], rax
0x1800030ef  mov     qword ptr [rsp+278h+nSize], rcx
0x1800030f4  mov     eax, [rbx+40h]
0x1800030f7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800030fb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180003102  mov     rcx, r14; this
0x180003105  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000310a  jmp     short loc_180003123
0x18000310c  mov     [rsp+278h+lpBuffer], rax
0x180003111  mov     r9, rcx; unsigned __int16 *
0x180003114  lea     r8, aHsP; "%hs!%p: "
0x18000311b  mov     rcx, r14; this
0x18000311e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003123  mov     r14, rax
0x180003126  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000312d  test    r9, r9
0x180003130  jz      short loc_180003147
0x180003132  lea     r8, aCallerP; "(caller: %p) "
0x180003139  mov     rdx, rsi; unsigned __int16 *
0x18000313c  mov     rcx, rax; this
0x18000313f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003144  mov     r14, rax
0x180003147  call    cs:__imp_GetCurrentThreadId
0x18000314d  lea     rcx, [rsp+278h+Buffer]
0x180003152  mov     [rsp+278h+var_240], rcx
0x180003157  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000315b  mov     [rsp+278h+nSize], eax
0x18000315f  mov     eax, [rbx+44h]
0x180003162  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003166  mov     r9, rdi; unsigned __int16 *
0x180003169  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180003170  mov     rdx, rsi; unsigned __int16 *
0x180003173  mov     rcx, r14; this
0x180003176  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000317b  cmp     [rbx+18h], r15
0x18000317f  jnz     short loc_180003191
0x180003181  cmp     [rbx+48h], r15
0x180003185  jnz     short loc_180003191
0x180003187  cmp     [rbx+30h], r15
0x18000318b  jz      loc_180003221
0x180003191  lea     r8, asc_180025F60; "    "
0x180003198  mov     rdx, rsi; unsigned __int16 *
0x18000319b  mov     rcx, rax; this
0x18000319e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800031a3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800031a7  test    r9, r9
0x1800031aa  jz      short loc_1800031BE
0x1800031ac  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800031b3  mov     rdx, rsi; unsigned __int16 *
0x1800031b6  mov     rcx, rax; this
0x1800031b9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800031be  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800031c2  test    r9, r9
0x1800031c5  jz      short loc_1800031D9
0x1800031c7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800031ce  mov     rdx, rsi; unsigned __int16 *
0x1800031d1  mov     rcx, rax; this
0x1800031d4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800031d9  mov     rcx, [rbx+28h]
0x1800031dd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800031e1  mov     rdx, rsi; unsigned __int16 *
0x1800031e4  test    rcx, rcx
0x1800031e7  jz      short loc_1800031FF
0x1800031e9  mov     [rsp+278h+lpBuffer], rcx
0x1800031ee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800031f5  mov     rcx, rax; this
0x1800031f8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800031fd  jmp     short loc_180003221
0x1800031ff  mov     rcx, rax; this
0x180003202  test    r9, r9
0x180003205  jz      short loc_180003215
0x180003207  lea     r8, aHs; "[%hs]\n"
0x18000320e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003213  jmp     short loc_180003221
0x180003215  lea     r8, asc_180025FD8; "\n"
0x18000321c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003221  xor     eax, eax
0x180003223  mov     rcx, [rsp+278h+var_38]
0x18000322b  xor     rcx, rsp; StackCookie
0x18000322e  call    __security_check_cookie
0x180003233  mov     rbx, [rsp+278h+arg_18]
0x18000323b  add     rsp, 250h
0x180003242  pop     r15
0x180003244  pop     r14
0x180003246  pop     rdi
0x180003247  pop     rsi
0x180003248  pop     rbp
0x180003249  retn
```
