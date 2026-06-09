# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140078a54`
- end: `0x140078d0a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140077474`
- `0x1400795ac`
- `0x14007bb00`

## callees

- `0x140075de0`
- `0x14007680c`
- `0x140078a54`
- `0x1400798ac`
- `0x140098010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x140078b86`
- `KERNEL32!FormatMessageW` at `0x140078b86`
- `KERNEL32!GetCurrentThreadId` at `0x140078c07`
- `KERNEL32!GetCurrentThreadId` at `0x140078c07`

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
          v7 = (const char *)&byte_14009CD2F;
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
0x140078a54  mov     [rsp+arg_18], rbx
0x140078a59  push    rbp
0x140078a5a  push    rsi
0x140078a5b  push    rdi
0x140078a5c  push    r14
0x140078a5e  push    r15
0x140078a60  sub     rsp, 250h
0x140078a67  mov     rax, cs:__security_cookie
0x140078a6e  xor     rax, rsp
0x140078a71  mov     [rsp+278h+var_38], rax
0x140078a79  mov     rbx, r8
0x140078a7c  mov     rsi, rdx
0x140078a7f  mov     r14, rcx
0x140078a82  xor     r15d, r15d
0x140078a85  test    rdx, rdx
0x140078a88  jz      loc_140078CE1
0x140078a8e  test    rcx, rcx
0x140078a91  jz      loc_140078CE1
0x140078a97  mov     [rcx], r15w
0x140078a9b  mov     rax, cs:g_pfnResultLoggingCallback
0x140078aa2  test    rax, rax
0x140078aa5  jz      short loc_140078AC8
0x140078aa7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140078aae  jz      short loc_140078AC8
0x140078ab0  mov     r8, rdx
0x140078ab3  mov     rdx, rcx
0x140078ab6  mov     rcx, rbx
0x140078ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140078abe  cmp     [r14], r15w
0x140078ac2  jnz     loc_140078CE1
0x140078ac8  mov     ecx, [rbx]
0x140078aca  mov     bpl, 8
0x140078acd  test    ecx, ecx
0x140078acf  jz      short loc_140078B1A
0x140078ad1  sub     ecx, 1
0x140078ad4  jz      short loc_140078B02
0x140078ad6  sub     ecx, 1
0x140078ad9  jz      short loc_140078AF2
0x140078adb  cmp     ecx, 1
0x140078ade  jz      short loc_140078AE9
0x140078ae0  lea     rdi, byte_14009CD2F
0x140078ae7  jmp     short loc_140078B21
0x140078ae9  lea     rdi, aFailfast; "FailFast"
0x140078af0  jmp     short loc_140078B21
0x140078af2  lea     rax, aLoghr; "LogHr"
0x140078af9  lea     rdi, aLognt; "LogNt"
0x140078b00  jmp     short loc_140078B10
0x140078b02  lea     rax, aReturnhr; "ReturnHr"
0x140078b09  lea     rdi, aReturnnt; "ReturnNt"
0x140078b10  test    [rbx+4], bpl
0x140078b14  cmovz   rdi, rax
0x140078b18  jmp     short loc_140078B21
0x140078b1a  lea     rdi, aException; "Exception"
0x140078b21  xor     edx, edx; Val
0x140078b23  mov     r8d, 200h; Size
0x140078b29  lea     rcx, [rsp+278h+Buffer]; void *
0x140078b2e  call    memset_0
0x140078b33  test    [rbx+4], bpl
0x140078b37  jz      short loc_140078B5C
0x140078b39  mov     ebp, [rbx+0Ch]
0x140078b3c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140078b43  test    rax, rax
0x140078b46  jz      short loc_140078B8C
0x140078b48  mov     r8d, 100h
0x140078b4e  lea     rdx, [rsp+278h+Buffer]
0x140078b53  mov     ecx, ebp
0x140078b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140078b5a  jmp     short loc_140078B8C
0x140078b5c  mov     ebp, [rbx+8]
0x140078b5f  mov     [rsp+278h+Arguments], r15; Arguments
0x140078b64  mov     [rsp+278h+nSize], 100h; nSize
0x140078b6c  lea     rax, [rsp+278h+Buffer]
0x140078b71  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140078b76  mov     r9d, 400h; dwLanguageId
0x140078b7c  mov     r8d, ebp; dwMessageId
0x140078b7f  xor     edx, edx; lpSource
0x140078b81  mov     ecx, 1200h; dwFlags
0x140078b86  call    cs:__imp_FormatMessageW
0x140078b8c  lea     rsi, [r14+rsi*2]
0x140078b90  mov     r9, [rbx+38h]; unsigned __int16 *
0x140078b94  mov     rax, [rbx+88h]
0x140078b9b  mov     rcx, [rbx+80h]
0x140078ba2  mov     rdx, rsi; unsigned __int16 *
0x140078ba5  test    r9, r9
0x140078ba8  jz      short loc_140078BCC
0x140078baa  mov     [rsp+278h+Arguments], rax
0x140078baf  mov     qword ptr [rsp+278h+nSize], rcx
0x140078bb4  mov     eax, [rbx+40h]
0x140078bb7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140078bbb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140078bc2  mov     rcx, r14; this
0x140078bc5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140078bca  jmp     short loc_140078BE3
0x140078bcc  mov     [rsp+278h+lpBuffer], rax
0x140078bd1  mov     r9, rcx; unsigned __int16 *
0x140078bd4  lea     r8, aHsP; "%hs!%p: "
0x140078bdb  mov     rcx, r14; this
0x140078bde  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140078be3  mov     r14, rax
0x140078be6  mov     r9, [rbx+90h]; unsigned __int16 *
0x140078bed  test    r9, r9
0x140078bf0  jz      short loc_140078C07
0x140078bf2  lea     r8, aCallerP; "(caller: %p) "
0x140078bf9  mov     rdx, rsi; unsigned __int16 *
0x140078bfc  mov     rcx, rax; this
0x140078bff  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140078c04  mov     r14, rax
0x140078c07  call    cs:__imp_GetCurrentThreadId
0x140078c0d  lea     rcx, [rsp+278h+Buffer]
0x140078c12  mov     [rsp+278h+var_240], rcx
0x140078c17  mov     dword ptr [rsp+278h+Arguments], ebp
0x140078c1b  mov     [rsp+278h+nSize], eax
0x140078c1f  mov     eax, [rbx+44h]
0x140078c22  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140078c26  mov     r9, rdi; unsigned __int16 *
0x140078c29  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140078c30  mov     rdx, rsi; unsigned __int16 *
0x140078c33  mov     rcx, r14; this
0x140078c36  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140078c3b  cmp     [rbx+18h], r15
0x140078c3f  jnz     short loc_140078C51
0x140078c41  cmp     [rbx+48h], r15
0x140078c45  jnz     short loc_140078C51
0x140078c47  cmp     [rbx+30h], r15
0x140078c4b  jz      loc_140078CE1
0x140078c51  lea     r8, asc_14009CE30; "    "
0x140078c58  mov     rdx, rsi; unsigned __int16 *
0x140078c5b  mov     rcx, rax; this
0x140078c5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140078c63  mov     r9, [rbx+18h]; unsigned __int16 *
0x140078c67  test    r9, r9
0x140078c6a  jz      short loc_140078C7E
0x140078c6c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140078c73  mov     rdx, rsi; unsigned __int16 *
0x140078c76  mov     rcx, rax; this
0x140078c79  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140078c7e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140078c82  test    r9, r9
0x140078c85  jz      short loc_140078C99
0x140078c87  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140078c8e  mov     rdx, rsi; unsigned __int16 *
0x140078c91  mov     rcx, rax; this
0x140078c94  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140078c99  mov     rcx, [rbx+28h]
0x140078c9d  mov     r9, [rbx+30h]; unsigned __int16 *
0x140078ca1  mov     rdx, rsi; unsigned __int16 *
0x140078ca4  test    rcx, rcx
0x140078ca7  jz      short loc_140078CBF
0x140078ca9  mov     [rsp+278h+lpBuffer], rcx
0x140078cae  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140078cb5  mov     rcx, rax; this
0x140078cb8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140078cbd  jmp     short loc_140078CE1
0x140078cbf  mov     rcx, rax; this
0x140078cc2  test    r9, r9
0x140078cc5  jz      short loc_140078CD5
0x140078cc7  lea     r8, aHs; "[%hs]\n"
0x140078cce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140078cd3  jmp     short loc_140078CE1
0x140078cd5  lea     r8, asc_14009CEA8; "\n"
0x140078cdc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140078ce1  xor     eax, eax
0x140078ce3  mov     rcx, [rsp+278h+var_38]
0x140078ceb  xor     rcx, rsp; StackCookie
0x140078cee  call    __security_check_cookie
0x140078cf3  mov     rbx, [rsp+278h+arg_18]
0x140078cfb  add     rsp, 250h
0x140078d02  pop     r15
0x140078d04  pop     r14
0x140078d06  pop     rdi
0x140078d07  pop     rsi
0x140078d08  pop     rbp
0x140078d09  retn
```
