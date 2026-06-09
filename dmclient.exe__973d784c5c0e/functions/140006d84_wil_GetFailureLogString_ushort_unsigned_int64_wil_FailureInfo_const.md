# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140006d84`
- end: `0x140007047`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x140003608`
- `0x140003884`
- `0x140003b48`
- `0x140007c9c`
- `0x14000c800`

## callees

- `0x140006d84`
- `0x140007fb0`
- `0x1400195e2`
- `0x140019610`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006f3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006f3d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140006eb6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140006eb6`

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
          v7 = (const char *)&word_14001D5D2;
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
0x140006d84  mov     [rsp+arg_18], rbx
0x140006d89  push    rbp
0x140006d8a  push    rsi
0x140006d8b  push    rdi
0x140006d8c  push    r14
0x140006d8e  push    r15
0x140006d90  sub     rsp, 250h
0x140006d97  mov     rax, cs:__security_cookie
0x140006d9e  xor     rax, rsp
0x140006da1  mov     [rsp+278h+var_38], rax
0x140006da9  mov     rbx, r8
0x140006dac  mov     rsi, rdx
0x140006daf  mov     r14, rcx
0x140006db2  xor     r15d, r15d
0x140006db5  test    rdx, rdx
0x140006db8  jz      loc_14000701D
0x140006dbe  test    rcx, rcx
0x140006dc1  jz      loc_14000701D
0x140006dc7  mov     [rcx], r15w
0x140006dcb  mov     rax, cs:g_pfnResultLoggingCallback
0x140006dd2  test    rax, rax
0x140006dd5  jz      short loc_140006DF8
0x140006dd7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140006dde  jz      short loc_140006DF8
0x140006de0  mov     r8, rdx
0x140006de3  mov     rdx, rcx
0x140006de6  mov     rcx, rbx
0x140006de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006dee  cmp     [r14], r15w
0x140006df2  jnz     loc_14000701D
0x140006df8  mov     ecx, [rbx]
0x140006dfa  mov     bpl, 8
0x140006dfd  test    ecx, ecx
0x140006dff  jz      short loc_140006E4A
0x140006e01  sub     ecx, 1
0x140006e04  jz      short loc_140006E32
0x140006e06  sub     ecx, 1
0x140006e09  jz      short loc_140006E22
0x140006e0b  cmp     ecx, 1
0x140006e0e  jz      short loc_140006E19
0x140006e10  lea     rdi, word_14001D5D2
0x140006e17  jmp     short loc_140006E51
0x140006e19  lea     rdi, aFailfast; "FailFast"
0x140006e20  jmp     short loc_140006E51
0x140006e22  lea     rax, aLoghr; "LogHr"
0x140006e29  lea     rdi, aLognt; "LogNt"
0x140006e30  jmp     short loc_140006E40
0x140006e32  lea     rax, aReturnhr; "ReturnHr"
0x140006e39  lea     rdi, aReturnnt; "ReturnNt"
0x140006e40  test    [rbx+4], bpl
0x140006e44  cmovz   rdi, rax
0x140006e48  jmp     short loc_140006E51
0x140006e4a  lea     rdi, aException; "Exception"
0x140006e51  xor     edx, edx; Val
0x140006e53  mov     r8d, 200h; Size
0x140006e59  lea     rcx, [rsp+278h+Buffer]; void *
0x140006e5e  call    memset_0
0x140006e63  test    [rbx+4], bpl
0x140006e67  jz      short loc_140006E8C
0x140006e69  mov     ebp, [rbx+0Ch]
0x140006e6c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140006e73  test    rax, rax
0x140006e76  jz      short loc_140006EC2
0x140006e78  mov     r8d, 100h
0x140006e7e  lea     rdx, [rsp+278h+Buffer]
0x140006e83  mov     ecx, ebp
0x140006e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006e8a  jmp     short loc_140006EC2
0x140006e8c  mov     ebp, [rbx+8]
0x140006e8f  mov     [rsp+278h+Arguments], r15; Arguments
0x140006e94  mov     [rsp+278h+nSize], 100h; nSize
0x140006e9c  lea     rax, [rsp+278h+Buffer]
0x140006ea1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140006ea6  mov     r9d, 400h; dwLanguageId
0x140006eac  mov     r8d, ebp; dwMessageId
0x140006eaf  xor     edx, edx; lpSource
0x140006eb1  mov     ecx, 1200h; dwFlags
0x140006eb6  call    cs:__imp_FormatMessageW
0x140006ebd  nop     dword ptr [rax+rax+00h]
0x140006ec2  lea     rsi, [r14+rsi*2]
0x140006ec6  mov     r9, [rbx+38h]; unsigned __int16 *
0x140006eca  mov     rax, [rbx+88h]
0x140006ed1  mov     rcx, [rbx+80h]
0x140006ed8  mov     rdx, rsi; unsigned __int16 *
0x140006edb  test    r9, r9
0x140006ede  jz      short loc_140006F02
0x140006ee0  mov     [rsp+278h+Arguments], rax
0x140006ee5  mov     qword ptr [rsp+278h+nSize], rcx
0x140006eea  mov     eax, [rbx+40h]
0x140006eed  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140006ef1  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140006ef8  mov     rcx, r14; this
0x140006efb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006f00  jmp     short loc_140006F19
0x140006f02  mov     [rsp+278h+lpBuffer], rax
0x140006f07  mov     r9, rcx; unsigned __int16 *
0x140006f0a  lea     r8, aHsP; "%hs!%p: "
0x140006f11  mov     rcx, r14; this
0x140006f14  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006f19  mov     r14, rax
0x140006f1c  mov     r9, [rbx+90h]; unsigned __int16 *
0x140006f23  test    r9, r9
0x140006f26  jz      short loc_140006F3D
0x140006f28  lea     r8, aCallerP; "(caller: %p) "
0x140006f2f  mov     rdx, rsi; unsigned __int16 *
0x140006f32  mov     rcx, rax; this
0x140006f35  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006f3a  mov     r14, rax
0x140006f3d  call    cs:__imp_GetCurrentThreadId
0x140006f44  nop     dword ptr [rax+rax+00h]
0x140006f49  lea     rcx, [rsp+278h+Buffer]
0x140006f4e  mov     [rsp+278h+var_240], rcx
0x140006f53  mov     dword ptr [rsp+278h+Arguments], ebp
0x140006f57  mov     [rsp+278h+nSize], eax
0x140006f5b  mov     eax, [rbx+44h]
0x140006f5e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140006f62  mov     r9, rdi; unsigned __int16 *
0x140006f65  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140006f6c  mov     rdx, rsi; unsigned __int16 *
0x140006f6f  mov     rcx, r14; this
0x140006f72  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006f77  cmp     [rbx+18h], r15
0x140006f7b  jnz     short loc_140006F8D
0x140006f7d  cmp     [rbx+48h], r15
0x140006f81  jnz     short loc_140006F8D
0x140006f83  cmp     [rbx+30h], r15
0x140006f87  jz      loc_14000701D
0x140006f8d  lea     r8, asc_14001D6C0; "    "
0x140006f94  mov     rdx, rsi; unsigned __int16 *
0x140006f97  mov     rcx, rax; this
0x140006f9a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006f9f  mov     r9, [rbx+18h]; unsigned __int16 *
0x140006fa3  test    r9, r9
0x140006fa6  jz      short loc_140006FBA
0x140006fa8  lea     r8, aMsgWs; "Msg:[%ws] "
0x140006faf  mov     rdx, rsi; unsigned __int16 *
0x140006fb2  mov     rcx, rax; this
0x140006fb5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006fba  mov     r9, [rbx+48h]; unsigned __int16 *
0x140006fbe  test    r9, r9
0x140006fc1  jz      short loc_140006FD5
0x140006fc3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140006fca  mov     rdx, rsi; unsigned __int16 *
0x140006fcd  mov     rcx, rax; this
0x140006fd0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006fd5  mov     rcx, [rbx+28h]
0x140006fd9  mov     r9, [rbx+30h]; unsigned __int16 *
0x140006fdd  mov     rdx, rsi; unsigned __int16 *
0x140006fe0  test    rcx, rcx
0x140006fe3  jz      short loc_140006FFB
0x140006fe5  mov     [rsp+278h+lpBuffer], rcx
0x140006fea  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140006ff1  mov     rcx, rax; this
0x140006ff4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006ff9  jmp     short loc_14000701D
0x140006ffb  mov     rcx, rax; this
0x140006ffe  test    r9, r9
0x140007001  jz      short loc_140007011
0x140007003  lea     r8, aHs; "[%hs]\n"
0x14000700a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000700f  jmp     short loc_14000701D
0x140007011  lea     r8, asc_14001D738; "\n"
0x140007018  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000701d  xor     eax, eax
0x14000701f  mov     rcx, [rsp+278h+var_38]
0x140007027  xor     rcx, rsp; StackCookie
0x14000702a  call    __security_check_cookie
0x14000702f  mov     rbx, [rsp+278h+arg_18]
0x140007037  add     rsp, 250h
0x14000703e  pop     r15
0x140007040  pop     r14
0x140007042  pop     rdi
0x140007043  pop     rsi
0x140007044  pop     rbp
0x140007045  retn
```
