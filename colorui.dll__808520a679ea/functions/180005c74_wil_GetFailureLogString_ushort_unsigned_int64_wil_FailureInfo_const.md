# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005c74`
- end: `0x180005f2a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000261c`
- `0x180002884`
- `0x180006ba0`

## callees

- `0x180005c74`
- `0x180006ea0`
- `0x1800184ce`
- `0x180018500`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180005e27`
- `KERNEL32!GetCurrentThreadId` at `0x180005e27`
- `KERNEL32!FormatMessageW` at `0x180005da6`
- `KERNEL32!FormatMessageW` at `0x180005da6`

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
          v8 = (const char *)&word_18001C2DE;
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
0x180005c74  mov     [rsp+arg_18], rbx
0x180005c79  push    rbp
0x180005c7a  push    rsi
0x180005c7b  push    rdi
0x180005c7c  push    r14
0x180005c7e  push    r15
0x180005c80  sub     rsp, 250h
0x180005c87  mov     rax, cs:__security_cookie
0x180005c8e  xor     rax, rsp
0x180005c91  mov     [rsp+278h+var_38], rax
0x180005c99  xor     r15d, r15d
0x180005c9c  mov     rbx, r8
0x180005c9f  mov     rsi, rdx
0x180005ca2  mov     r14, rcx
0x180005ca5  test    rdx, rdx
0x180005ca8  jz      loc_180005F01
0x180005cae  test    rcx, rcx
0x180005cb1  jz      loc_180005F01
0x180005cb7  mov     rax, cs:g_pfnResultLoggingCallback
0x180005cbe  mov     [rcx], r15w
0x180005cc2  test    rax, rax
0x180005cc5  jz      short loc_180005CE8
0x180005cc7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005cce  jz      short loc_180005CE8
0x180005cd0  mov     r8, rdx
0x180005cd3  mov     rdx, rcx
0x180005cd6  mov     rcx, rbx
0x180005cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cde  cmp     [r14], r15w
0x180005ce2  jnz     loc_180005F01
0x180005ce8  mov     ecx, [rbx]
0x180005cea  mov     bpl, 8
0x180005ced  test    ecx, ecx
0x180005cef  jz      short loc_180005D3A
0x180005cf1  sub     ecx, 1
0x180005cf4  jz      short loc_180005D22
0x180005cf6  sub     ecx, 1
0x180005cf9  jz      short loc_180005D12
0x180005cfb  cmp     ecx, 1
0x180005cfe  jz      short loc_180005D09
0x180005d00  lea     rdi, word_18001C2DE
0x180005d07  jmp     short loc_180005D41
0x180005d09  lea     rdi, aFailfast; "FailFast"
0x180005d10  jmp     short loc_180005D41
0x180005d12  lea     rax, aLoghr; "LogHr"
0x180005d19  lea     rdi, aLognt; "LogNt"
0x180005d20  jmp     short loc_180005D30
0x180005d22  lea     rax, aReturnhr; "ReturnHr"
0x180005d29  lea     rdi, aReturnnt; "ReturnNt"
0x180005d30  test    [rbx+4], bpl
0x180005d34  cmovz   rdi, rax
0x180005d38  jmp     short loc_180005D41
0x180005d3a  lea     rdi, aException; "Exception"
0x180005d41  xor     edx, edx; Val
0x180005d43  lea     rcx, [rsp+278h+Buffer]; void *
0x180005d48  mov     r8d, 200h; Size
0x180005d4e  call    memset_0
0x180005d53  test    [rbx+4], bpl
0x180005d57  jz      short loc_180005D7C
0x180005d59  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005d60  mov     ebp, [rbx+0Ch]
0x180005d63  test    rax, rax
0x180005d66  jz      short loc_180005DAC
0x180005d68  mov     r8d, 100h
0x180005d6e  lea     rdx, [rsp+278h+Buffer]
0x180005d73  mov     ecx, ebp
0x180005d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d7a  jmp     short loc_180005DAC
0x180005d7c  mov     ebp, [rbx+8]
0x180005d7f  lea     rax, [rsp+278h+Buffer]
0x180005d84  mov     [rsp+278h+Arguments], r15; Arguments
0x180005d89  mov     r8d, ebp; dwMessageId
0x180005d8c  mov     [rsp+278h+nSize], 100h; nSize
0x180005d94  mov     r9d, 400h; dwLanguageId
0x180005d9a  xor     edx, edx; lpSource
0x180005d9c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005da1  mov     ecx, 1200h; dwFlags
0x180005da6  call    cs:__imp_FormatMessageW
0x180005dac  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005db0  lea     rsi, [r14+rsi*2]
0x180005db4  mov     rax, [rbx+88h]
0x180005dbb  mov     rdx, rsi; unsigned __int16 *
0x180005dbe  mov     rcx, [rbx+80h]
0x180005dc5  test    r9, r9
0x180005dc8  jz      short loc_180005DEC
0x180005dca  mov     [rsp+278h+Arguments], rax
0x180005dcf  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005dd6  mov     eax, [rbx+40h]
0x180005dd9  mov     qword ptr [rsp+278h+nSize], rcx
0x180005dde  mov     rcx, r14; this
0x180005de1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005de5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005dea  jmp     short loc_180005E03
0x180005dec  mov     r9, rcx; unsigned __int16 *
0x180005def  mov     [rsp+278h+lpBuffer], rax
0x180005df4  mov     rcx, r14; this
0x180005df7  lea     r8, aHsP; "%hs!%p: "
0x180005dfe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005e03  mov     r9, [rbx+90h]; unsigned __int16 *
0x180005e0a  mov     r14, rax
0x180005e0d  test    r9, r9
0x180005e10  jz      short loc_180005E27
0x180005e12  lea     r8, aCallerP; "(caller: %p) "
0x180005e19  mov     rdx, rsi; unsigned __int16 *
0x180005e1c  mov     rcx, rax; this
0x180005e1f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005e24  mov     r14, rax
0x180005e27  call    cs:__imp_GetCurrentThreadId
0x180005e2d  lea     rcx, [rsp+278h+Buffer]
0x180005e32  mov     r9, rdi; unsigned __int16 *
0x180005e35  mov     [rsp+278h+var_240], rcx
0x180005e3a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005e41  mov     dword ptr [rsp+278h+Arguments], ebp
0x180005e45  mov     rdx, rsi; unsigned __int16 *
0x180005e48  mov     [rsp+278h+nSize], eax
0x180005e4c  mov     rcx, r14; this
0x180005e4f  mov     eax, [rbx+44h]
0x180005e52  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005e56  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005e5b  cmp     [rbx+18h], r15
0x180005e5f  jnz     short loc_180005E71
0x180005e61  cmp     [rbx+48h], r15
0x180005e65  jnz     short loc_180005E71
0x180005e67  cmp     [rbx+30h], r15
0x180005e6b  jz      loc_180005F01
0x180005e71  lea     r8, asc_18001C3C8; "    "
0x180005e78  mov     rdx, rsi; unsigned __int16 *
0x180005e7b  mov     rcx, rax; this
0x180005e7e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005e83  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005e87  test    r9, r9
0x180005e8a  jz      short loc_180005E9E
0x180005e8c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005e93  mov     rdx, rsi; unsigned __int16 *
0x180005e96  mov     rcx, rax; this
0x180005e99  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005e9e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005ea2  test    r9, r9
0x180005ea5  jz      short loc_180005EB9
0x180005ea7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180005eae  mov     rdx, rsi; unsigned __int16 *
0x180005eb1  mov     rcx, rax; this
0x180005eb4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005eb9  mov     rcx, [rbx+28h]
0x180005ebd  mov     rdx, rsi; unsigned __int16 *
0x180005ec0  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005ec4  test    rcx, rcx
0x180005ec7  jz      short loc_180005EDF
0x180005ec9  mov     [rsp+278h+lpBuffer], rcx
0x180005ece  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005ed5  mov     rcx, rax; this
0x180005ed8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005edd  jmp     short loc_180005F01
0x180005edf  mov     rcx, rax; this
0x180005ee2  test    r9, r9
0x180005ee5  jz      short loc_180005EF5
0x180005ee7  lea     r8, aHs; "[%hs]\n"
0x180005eee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005ef3  jmp     short loc_180005F01
0x180005ef5  lea     r8, asc_18001C440; "\n"
0x180005efc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f01  xor     eax, eax
0x180005f03  mov     rcx, [rsp+278h+var_38]
0x180005f0b  xor     rcx, rsp; StackCookie
0x180005f0e  call    __security_check_cookie
0x180005f13  mov     rbx, [rsp+278h+arg_18]
0x180005f1b  add     rsp, 250h
0x180005f22  pop     r15
0x180005f24  pop     r14
0x180005f26  pop     rdi
0x180005f27  pop     rsi
0x180005f28  pop     rbp
0x180005f29  retn
```
