# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005c94`
- end: `0x180005f4a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000360c`
- `0x180006a0c`

## callees

- `0x180002620`
- `0x180002f40`
- `0x180005c94`
- `0x180006d0c`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005dc6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005dc6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005e47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005e47`

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
          v8 = (const char *)&word_18001582A;
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
0x180005c94  mov     [rsp+arg_18], rbx
0x180005c99  push    rbp
0x180005c9a  push    rsi
0x180005c9b  push    rdi
0x180005c9c  push    r14
0x180005c9e  push    r15
0x180005ca0  sub     rsp, 250h
0x180005ca7  mov     rax, cs:__security_cookie
0x180005cae  xor     rax, rsp
0x180005cb1  mov     [rsp+278h+var_38], rax
0x180005cb9  xor     r15d, r15d
0x180005cbc  mov     rbx, r8
0x180005cbf  mov     rsi, rdx
0x180005cc2  mov     r14, rcx
0x180005cc5  test    rdx, rdx
0x180005cc8  jz      loc_180005F21
0x180005cce  test    rcx, rcx
0x180005cd1  jz      loc_180005F21
0x180005cd7  mov     rax, cs:g_pfnResultLoggingCallback
0x180005cde  mov     [rcx], r15w
0x180005ce2  test    rax, rax
0x180005ce5  jz      short loc_180005D08
0x180005ce7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005cee  jz      short loc_180005D08
0x180005cf0  mov     r8, rdx
0x180005cf3  mov     rdx, rcx
0x180005cf6  mov     rcx, rbx
0x180005cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cfe  cmp     [r14], r15w
0x180005d02  jnz     loc_180005F21
0x180005d08  mov     ecx, [rbx]
0x180005d0a  mov     bpl, 8
0x180005d0d  test    ecx, ecx
0x180005d0f  jz      short loc_180005D5A
0x180005d11  sub     ecx, 1
0x180005d14  jz      short loc_180005D42
0x180005d16  sub     ecx, 1
0x180005d19  jz      short loc_180005D32
0x180005d1b  cmp     ecx, 1
0x180005d1e  jz      short loc_180005D29
0x180005d20  lea     rdi, word_18001582A
0x180005d27  jmp     short loc_180005D61
0x180005d29  lea     rdi, aFailfast; "FailFast"
0x180005d30  jmp     short loc_180005D61
0x180005d32  lea     rax, aLoghr; "LogHr"
0x180005d39  lea     rdi, aLognt; "LogNt"
0x180005d40  jmp     short loc_180005D50
0x180005d42  lea     rax, aReturnhr; "ReturnHr"
0x180005d49  lea     rdi, aReturnnt; "ReturnNt"
0x180005d50  test    [rbx+4], bpl
0x180005d54  cmovz   rdi, rax
0x180005d58  jmp     short loc_180005D61
0x180005d5a  lea     rdi, aException; "Exception"
0x180005d61  xor     edx, edx; Val
0x180005d63  lea     rcx, [rsp+278h+Buffer]; void *
0x180005d68  mov     r8d, 200h; Size
0x180005d6e  call    memset_0
0x180005d73  test    [rbx+4], bpl
0x180005d77  jz      short loc_180005D9C
0x180005d79  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005d80  mov     ebp, [rbx+0Ch]
0x180005d83  test    rax, rax
0x180005d86  jz      short loc_180005DCC
0x180005d88  mov     r8d, 100h
0x180005d8e  lea     rdx, [rsp+278h+Buffer]
0x180005d93  mov     ecx, ebp
0x180005d95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d9a  jmp     short loc_180005DCC
0x180005d9c  mov     ebp, [rbx+8]
0x180005d9f  lea     rax, [rsp+278h+Buffer]
0x180005da4  mov     [rsp+278h+Arguments], r15; Arguments
0x180005da9  mov     r8d, ebp; dwMessageId
0x180005dac  mov     [rsp+278h+nSize], 100h; nSize
0x180005db4  mov     r9d, 400h; dwLanguageId
0x180005dba  xor     edx, edx; lpSource
0x180005dbc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005dc1  mov     ecx, 1200h; dwFlags
0x180005dc6  call    cs:__imp_FormatMessageW
0x180005dcc  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005dd0  lea     rsi, [r14+rsi*2]
0x180005dd4  mov     rax, [rbx+88h]
0x180005ddb  mov     rdx, rsi; unsigned __int16 *
0x180005dde  mov     rcx, [rbx+80h]
0x180005de5  test    r9, r9
0x180005de8  jz      short loc_180005E0C
0x180005dea  mov     [rsp+278h+Arguments], rax
0x180005def  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005df6  mov     eax, [rbx+40h]
0x180005df9  mov     qword ptr [rsp+278h+nSize], rcx
0x180005dfe  mov     rcx, r14; this
0x180005e01  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005e05  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005e0a  jmp     short loc_180005E23
0x180005e0c  mov     r9, rcx; unsigned __int16 *
0x180005e0f  mov     [rsp+278h+lpBuffer], rax
0x180005e14  mov     rcx, r14; this
0x180005e17  lea     r8, aHsP; "%hs!%p: "
0x180005e1e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005e23  mov     r9, [rbx+90h]; unsigned __int16 *
0x180005e2a  mov     r14, rax
0x180005e2d  test    r9, r9
0x180005e30  jz      short loc_180005E47
0x180005e32  lea     r8, aCallerP; "(caller: %p) "
0x180005e39  mov     rdx, rsi; unsigned __int16 *
0x180005e3c  mov     rcx, rax; this
0x180005e3f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005e44  mov     r14, rax
0x180005e47  call    cs:__imp_GetCurrentThreadId
0x180005e4d  lea     rcx, [rsp+278h+Buffer]
0x180005e52  mov     r9, rdi; unsigned __int16 *
0x180005e55  mov     [rsp+278h+var_240], rcx
0x180005e5a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005e61  mov     dword ptr [rsp+278h+Arguments], ebp
0x180005e65  mov     rdx, rsi; unsigned __int16 *
0x180005e68  mov     [rsp+278h+nSize], eax
0x180005e6c  mov     rcx, r14; this
0x180005e6f  mov     eax, [rbx+44h]
0x180005e72  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005e76  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005e7b  cmp     [rbx+18h], r15
0x180005e7f  jnz     short loc_180005E91
0x180005e81  cmp     [rbx+48h], r15
0x180005e85  jnz     short loc_180005E91
0x180005e87  cmp     [rbx+30h], r15
0x180005e8b  jz      loc_180005F21
0x180005e91  lea     r8, asc_180015428; "    "
0x180005e98  mov     rdx, rsi; unsigned __int16 *
0x180005e9b  mov     rcx, rax; this
0x180005e9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005ea3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005ea7  test    r9, r9
0x180005eaa  jz      short loc_180005EBE
0x180005eac  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005eb3  mov     rdx, rsi; unsigned __int16 *
0x180005eb6  mov     rcx, rax; this
0x180005eb9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005ebe  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005ec2  test    r9, r9
0x180005ec5  jz      short loc_180005ED9
0x180005ec7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180005ece  mov     rdx, rsi; unsigned __int16 *
0x180005ed1  mov     rcx, rax; this
0x180005ed4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005ed9  mov     rcx, [rbx+28h]
0x180005edd  mov     rdx, rsi; unsigned __int16 *
0x180005ee0  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005ee4  test    rcx, rcx
0x180005ee7  jz      short loc_180005EFF
0x180005ee9  mov     [rsp+278h+lpBuffer], rcx
0x180005eee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005ef5  mov     rcx, rax; this
0x180005ef8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005efd  jmp     short loc_180005F21
0x180005eff  mov     rcx, rax; this
0x180005f02  test    r9, r9
0x180005f05  jz      short loc_180005F15
0x180005f07  lea     r8, aHs; "[%hs]\n"
0x180005f0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f13  jmp     short loc_180005F21
0x180005f15  lea     r8, asc_1800154A0; "\n"
0x180005f1c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f21  xor     eax, eax
0x180005f23  mov     rcx, [rsp+278h+var_38]
0x180005f2b  xor     rcx, rsp; StackCookie
0x180005f2e  call    __security_check_cookie
0x180005f33  mov     rbx, [rsp+278h+arg_18]
0x180005f3b  add     rsp, 250h
0x180005f42  pop     r15
0x180005f44  pop     r14
0x180005f46  pop     rdi
0x180005f47  pop     rsi
0x180005f48  pop     rbp
0x180005f49  retn
```
