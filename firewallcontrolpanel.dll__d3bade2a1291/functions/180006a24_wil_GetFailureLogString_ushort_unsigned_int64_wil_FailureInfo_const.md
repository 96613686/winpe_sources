# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006a24`
- end: `0x180006cda`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180005c20`
- `0x180007410`
- `0x180008940`

## callees

- `0x180006a24`
- `0x180007714`
- `0x180030e6e`
- `0x180030ea0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006bd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006bd7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006b56`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006b56`

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
          v7 = (const char *)&qword_1800369D0;
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
0x180006a24  mov     [rsp+arg_18], rbx
0x180006a29  push    rbp
0x180006a2a  push    rsi
0x180006a2b  push    rdi
0x180006a2c  push    r14
0x180006a2e  push    r15
0x180006a30  sub     rsp, 250h
0x180006a37  mov     rax, cs:__security_cookie
0x180006a3e  xor     rax, rsp
0x180006a41  mov     [rsp+278h+var_38], rax
0x180006a49  mov     rbx, r8
0x180006a4c  mov     rsi, rdx
0x180006a4f  mov     r14, rcx
0x180006a52  xor     r15d, r15d
0x180006a55  test    rdx, rdx
0x180006a58  jz      loc_180006CB1
0x180006a5e  test    rcx, rcx
0x180006a61  jz      loc_180006CB1
0x180006a67  mov     [rcx], r15w
0x180006a6b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006a72  test    rax, rax
0x180006a75  jz      short loc_180006A98
0x180006a77  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006a7e  jz      short loc_180006A98
0x180006a80  mov     r8, rdx
0x180006a83  mov     rdx, rcx
0x180006a86  mov     rcx, rbx
0x180006a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a8e  cmp     [r14], r15w
0x180006a92  jnz     loc_180006CB1
0x180006a98  mov     ecx, [rbx]
0x180006a9a  mov     bpl, 8
0x180006a9d  test    ecx, ecx
0x180006a9f  jz      short loc_180006AEA
0x180006aa1  sub     ecx, 1
0x180006aa4  jz      short loc_180006AD2
0x180006aa6  sub     ecx, 1
0x180006aa9  jz      short loc_180006AC2
0x180006aab  cmp     ecx, 1
0x180006aae  jz      short loc_180006AB9
0x180006ab0  lea     rdi, qword_1800369D0
0x180006ab7  jmp     short loc_180006AF1
0x180006ab9  lea     rdi, aFailfast; "FailFast"
0x180006ac0  jmp     short loc_180006AF1
0x180006ac2  lea     rax, aLoghr; "LogHr"
0x180006ac9  lea     rdi, aLognt; "LogNt"
0x180006ad0  jmp     short loc_180006AE0
0x180006ad2  lea     rax, aReturnhr; "ReturnHr"
0x180006ad9  lea     rdi, aReturnnt; "ReturnNt"
0x180006ae0  test    [rbx+4], bpl
0x180006ae4  cmovz   rdi, rax
0x180006ae8  jmp     short loc_180006AF1
0x180006aea  lea     rdi, aException; "Exception"
0x180006af1  xor     edx, edx; Val
0x180006af3  mov     r8d, 200h; Size
0x180006af9  lea     rcx, [rsp+278h+Buffer]; void *
0x180006afe  call    memset_0
0x180006b03  test    [rbx+4], bpl
0x180006b07  jz      short loc_180006B2C
0x180006b09  mov     ebp, [rbx+0Ch]
0x180006b0c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180006b13  test    rax, rax
0x180006b16  jz      short loc_180006B5C
0x180006b18  mov     r8d, 100h
0x180006b1e  lea     rdx, [rsp+278h+Buffer]
0x180006b23  mov     ecx, ebp
0x180006b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b2a  jmp     short loc_180006B5C
0x180006b2c  mov     ebp, [rbx+8]
0x180006b2f  mov     [rsp+278h+Arguments], r15; Arguments
0x180006b34  mov     [rsp+278h+nSize], 100h; nSize
0x180006b3c  lea     rax, [rsp+278h+Buffer]
0x180006b41  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006b46  mov     r9d, 400h; dwLanguageId
0x180006b4c  mov     r8d, ebp; dwMessageId
0x180006b4f  xor     edx, edx; lpSource
0x180006b51  mov     ecx, 1200h; dwFlags
0x180006b56  call    cs:__imp_FormatMessageW
0x180006b5c  lea     rsi, [r14+rsi*2]
0x180006b60  mov     r9, [rbx+38h]; unsigned __int16 *
0x180006b64  mov     rax, [rbx+88h]
0x180006b6b  mov     rcx, [rbx+80h]
0x180006b72  mov     rdx, rsi; unsigned __int16 *
0x180006b75  test    r9, r9
0x180006b78  jz      short loc_180006B9C
0x180006b7a  mov     [rsp+278h+Arguments], rax
0x180006b7f  mov     qword ptr [rsp+278h+nSize], rcx
0x180006b84  mov     eax, [rbx+40h]
0x180006b87  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006b8b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006b92  mov     rcx, r14; this
0x180006b95  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006b9a  jmp     short loc_180006BB3
0x180006b9c  mov     [rsp+278h+lpBuffer], rax
0x180006ba1  mov     r9, rcx; unsigned __int16 *
0x180006ba4  lea     r8, aHsP; "%hs!%p: "
0x180006bab  mov     rcx, r14; this
0x180006bae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006bb3  mov     r14, rax
0x180006bb6  mov     r9, [rbx+90h]; unsigned __int16 *
0x180006bbd  test    r9, r9
0x180006bc0  jz      short loc_180006BD7
0x180006bc2  lea     r8, aCallerP; "(caller: %p) "
0x180006bc9  mov     rdx, rsi; unsigned __int16 *
0x180006bcc  mov     rcx, rax; this
0x180006bcf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006bd4  mov     r14, rax
0x180006bd7  call    cs:__imp_GetCurrentThreadId
0x180006bdd  lea     rcx, [rsp+278h+Buffer]
0x180006be2  mov     [rsp+278h+var_240], rcx
0x180006be7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180006beb  mov     [rsp+278h+nSize], eax
0x180006bef  mov     eax, [rbx+44h]
0x180006bf2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006bf6  mov     r9, rdi; unsigned __int16 *
0x180006bf9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006c00  mov     rdx, rsi; unsigned __int16 *
0x180006c03  mov     rcx, r14; this
0x180006c06  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006c0b  cmp     [rbx+18h], r15
0x180006c0f  jnz     short loc_180006C21
0x180006c11  cmp     [rbx+48h], r15
0x180006c15  jnz     short loc_180006C21
0x180006c17  cmp     [rbx+30h], r15
0x180006c1b  jz      loc_180006CB1
0x180006c21  lea     r8, asc_180036AC0; "    "
0x180006c28  mov     rdx, rsi; unsigned __int16 *
0x180006c2b  mov     rcx, rax; this
0x180006c2e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006c33  mov     r9, [rbx+18h]; unsigned __int16 *
0x180006c37  test    r9, r9
0x180006c3a  jz      short loc_180006C4E
0x180006c3c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006c43  mov     rdx, rsi; unsigned __int16 *
0x180006c46  mov     rcx, rax; this
0x180006c49  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006c4e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180006c52  test    r9, r9
0x180006c55  jz      short loc_180006C69
0x180006c57  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180006c5e  mov     rdx, rsi; unsigned __int16 *
0x180006c61  mov     rcx, rax; this
0x180006c64  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006c69  mov     rcx, [rbx+28h]
0x180006c6d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006c71  mov     rdx, rsi; unsigned __int16 *
0x180006c74  test    rcx, rcx
0x180006c77  jz      short loc_180006C8F
0x180006c79  mov     [rsp+278h+lpBuffer], rcx
0x180006c7e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006c85  mov     rcx, rax; this
0x180006c88  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006c8d  jmp     short loc_180006CB1
0x180006c8f  mov     rcx, rax; this
0x180006c92  test    r9, r9
0x180006c95  jz      short loc_180006CA5
0x180006c97  lea     r8, aHs; "[%hs]\n"
0x180006c9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006ca3  jmp     short loc_180006CB1
0x180006ca5  lea     r8, asc_180036B38; "\n"
0x180006cac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006cb1  xor     eax, eax
0x180006cb3  mov     rcx, [rsp+278h+var_38]
0x180006cbb  xor     rcx, rsp; StackCookie
0x180006cbe  call    __security_check_cookie
0x180006cc3  mov     rbx, [rsp+278h+arg_18]
0x180006ccb  add     rsp, 250h
0x180006cd2  pop     r15
0x180006cd4  pop     r14
0x180006cd6  pop     rdi
0x180006cd7  pop     rsi
0x180006cd8  pop     rbp
0x180006cd9  retn
```
