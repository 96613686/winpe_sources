# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005d24`
- end: `0x180005fda`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180003e3c`
- `0x1800068b0`
- `0x1800096e0`
- `0x180009f3d`
- `0x18000a071`

## callees

- `0x180005d24`
- `0x180006bb0`
- `0x1800098f6`
- `0x180009930`
- `0x18000b010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180005e56`
- `KERNEL32!FormatMessageW` at `0x180005e56`
- `KERNEL32!GetCurrentThreadId` at `0x180005ed7`
- `KERNEL32!GetCurrentThreadId` at `0x180005ed7`

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
          v7 = (const char *)&word_18000DE4C;
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
0x180005d24  mov     [rsp+arg_18], rbx
0x180005d29  push    rbp
0x180005d2a  push    rsi
0x180005d2b  push    rdi
0x180005d2c  push    r14
0x180005d2e  push    r15
0x180005d30  sub     rsp, 250h
0x180005d37  mov     rax, cs:__security_cookie
0x180005d3e  xor     rax, rsp
0x180005d41  mov     [rsp+278h+var_38], rax
0x180005d49  mov     rbx, r8
0x180005d4c  mov     rsi, rdx
0x180005d4f  mov     r14, rcx
0x180005d52  xor     r15d, r15d
0x180005d55  test    rdx, rdx
0x180005d58  jz      loc_180005FB1
0x180005d5e  test    rcx, rcx
0x180005d61  jz      loc_180005FB1
0x180005d67  mov     [rcx], r15w
0x180005d6b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005d72  test    rax, rax
0x180005d75  jz      short loc_180005D98
0x180005d77  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005d7e  jz      short loc_180005D98
0x180005d80  mov     r8, rdx
0x180005d83  mov     rdx, rcx
0x180005d86  mov     rcx, rbx
0x180005d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d8e  cmp     [r14], r15w
0x180005d92  jnz     loc_180005FB1
0x180005d98  mov     ecx, [rbx]
0x180005d9a  mov     bpl, 8
0x180005d9d  test    ecx, ecx
0x180005d9f  jz      short loc_180005DEA
0x180005da1  sub     ecx, 1
0x180005da4  jz      short loc_180005DD2
0x180005da6  sub     ecx, 1
0x180005da9  jz      short loc_180005DC2
0x180005dab  cmp     ecx, 1
0x180005dae  jz      short loc_180005DB9
0x180005db0  lea     rdi, word_18000DE4C
0x180005db7  jmp     short loc_180005DF1
0x180005db9  lea     rdi, aFailfast; "FailFast"
0x180005dc0  jmp     short loc_180005DF1
0x180005dc2  lea     rax, aLoghr; "LogHr"
0x180005dc9  lea     rdi, aLognt; "LogNt"
0x180005dd0  jmp     short loc_180005DE0
0x180005dd2  lea     rax, aReturnhr; "ReturnHr"
0x180005dd9  lea     rdi, aReturnnt; "ReturnNt"
0x180005de0  test    [rbx+4], bpl
0x180005de4  cmovz   rdi, rax
0x180005de8  jmp     short loc_180005DF1
0x180005dea  lea     rdi, aException; "Exception"
0x180005df1  xor     edx, edx; Val
0x180005df3  mov     r8d, 200h; Size
0x180005df9  lea     rcx, [rsp+278h+Buffer]; void *
0x180005dfe  call    memset_0
0x180005e03  test    [rbx+4], bpl
0x180005e07  jz      short loc_180005E2C
0x180005e09  mov     ebp, [rbx+0Ch]
0x180005e0c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005e13  test    rax, rax
0x180005e16  jz      short loc_180005E5C
0x180005e18  mov     r8d, 100h
0x180005e1e  lea     rdx, [rsp+278h+Buffer]
0x180005e23  mov     ecx, ebp
0x180005e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e2a  jmp     short loc_180005E5C
0x180005e2c  mov     ebp, [rbx+8]
0x180005e2f  mov     [rsp+278h+Arguments], r15; Arguments
0x180005e34  mov     [rsp+278h+nSize], 100h; nSize
0x180005e3c  lea     rax, [rsp+278h+Buffer]
0x180005e41  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005e46  mov     r9d, 400h; dwLanguageId
0x180005e4c  mov     r8d, ebp; dwMessageId
0x180005e4f  xor     edx, edx; lpSource
0x180005e51  mov     ecx, 1200h; dwFlags
0x180005e56  call    cs:__imp_FormatMessageW
0x180005e5c  lea     rsi, [r14+rsi*2]
0x180005e60  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005e64  mov     rax, [rbx+88h]
0x180005e6b  mov     rcx, [rbx+80h]
0x180005e72  mov     rdx, rsi; unsigned __int16 *
0x180005e75  test    r9, r9
0x180005e78  jz      short loc_180005E9C
0x180005e7a  mov     [rsp+278h+Arguments], rax
0x180005e7f  mov     qword ptr [rsp+278h+nSize], rcx
0x180005e84  mov     eax, [rbx+40h]
0x180005e87  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005e8b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005e92  mov     rcx, r14; this
0x180005e95  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005e9a  jmp     short loc_180005EB3
0x180005e9c  mov     [rsp+278h+lpBuffer], rax
0x180005ea1  mov     r9, rcx; unsigned __int16 *
0x180005ea4  lea     r8, aHsP; "%hs!%p: "
0x180005eab  mov     rcx, r14; this
0x180005eae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005eb3  mov     r14, rax
0x180005eb6  mov     r9, [rbx+90h]; unsigned __int16 *
0x180005ebd  test    r9, r9
0x180005ec0  jz      short loc_180005ED7
0x180005ec2  lea     r8, aCallerP; "(caller: %p) "
0x180005ec9  mov     rdx, rsi; unsigned __int16 *
0x180005ecc  mov     rcx, rax; this
0x180005ecf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005ed4  mov     r14, rax
0x180005ed7  call    cs:__imp_GetCurrentThreadId
0x180005edd  lea     rcx, [rsp+278h+Buffer]
0x180005ee2  mov     [rsp+278h+var_240], rcx
0x180005ee7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180005eeb  mov     [rsp+278h+nSize], eax
0x180005eef  mov     eax, [rbx+44h]
0x180005ef2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005ef6  mov     r9, rdi; unsigned __int16 *
0x180005ef9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005f00  mov     rdx, rsi; unsigned __int16 *
0x180005f03  mov     rcx, r14; this
0x180005f06  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f0b  cmp     [rbx+18h], r15
0x180005f0f  jnz     short loc_180005F21
0x180005f11  cmp     [rbx+48h], r15
0x180005f15  jnz     short loc_180005F21
0x180005f17  cmp     [rbx+30h], r15
0x180005f1b  jz      loc_180005FB1
0x180005f21  lea     r8, asc_18000DF40; "    "
0x180005f28  mov     rdx, rsi; unsigned __int16 *
0x180005f2b  mov     rcx, rax; this
0x180005f2e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f33  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005f37  test    r9, r9
0x180005f3a  jz      short loc_180005F4E
0x180005f3c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005f43  mov     rdx, rsi; unsigned __int16 *
0x180005f46  mov     rcx, rax; this
0x180005f49  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f4e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005f52  test    r9, r9
0x180005f55  jz      short loc_180005F69
0x180005f57  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180005f5e  mov     rdx, rsi; unsigned __int16 *
0x180005f61  mov     rcx, rax; this
0x180005f64  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f69  mov     rcx, [rbx+28h]
0x180005f6d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005f71  mov     rdx, rsi; unsigned __int16 *
0x180005f74  test    rcx, rcx
0x180005f77  jz      short loc_180005F8F
0x180005f79  mov     [rsp+278h+lpBuffer], rcx
0x180005f7e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005f85  mov     rcx, rax; this
0x180005f88  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f8d  jmp     short loc_180005FB1
0x180005f8f  mov     rcx, rax; this
0x180005f92  test    r9, r9
0x180005f95  jz      short loc_180005FA5
0x180005f97  lea     r8, aHs; "[%hs]\n"
0x180005f9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005fa3  jmp     short loc_180005FB1
0x180005fa5  lea     r8, asc_18000DFB8; "\n"
0x180005fac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005fb1  xor     eax, eax
0x180005fb3  mov     rcx, [rsp+278h+var_38]
0x180005fbb  xor     rcx, rsp; StackCookie
0x180005fbe  call    __security_check_cookie
0x180005fc3  mov     rbx, [rsp+278h+arg_18]
0x180005fcb  add     rsp, 250h
0x180005fd2  pop     r15
0x180005fd4  pop     r14
0x180005fd6  pop     rdi
0x180005fd7  pop     rsi
0x180005fd8  pop     rbp
0x180005fd9  retn
```
