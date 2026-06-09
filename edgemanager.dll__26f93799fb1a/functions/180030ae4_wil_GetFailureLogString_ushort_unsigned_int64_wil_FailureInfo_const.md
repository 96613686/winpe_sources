# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180030ae4`
- end: `0x180030d9a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18001563c`
- `0x180033b80`

## callees

- `0x18002b530`
- `0x18002c5b0`
- `0x180030ae4`
- `0x180031590`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030c97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030c97`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180030c16`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180030c16`

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
          v7 = (const char *)&qword_18009E510;
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
0x180030ae4  mov     [rsp+arg_18], rbx
0x180030ae9  push    rbp
0x180030aea  push    rsi
0x180030aeb  push    rdi
0x180030aec  push    r14
0x180030aee  push    r15
0x180030af0  sub     rsp, 250h
0x180030af7  mov     rax, cs:__security_cookie
0x180030afe  xor     rax, rsp
0x180030b01  mov     [rsp+278h+var_38], rax
0x180030b09  mov     rbx, r8
0x180030b0c  mov     rsi, rdx
0x180030b0f  mov     r14, rcx
0x180030b12  xor     r15d, r15d
0x180030b15  test    rdx, rdx
0x180030b18  jz      loc_180030D71
0x180030b1e  test    rcx, rcx
0x180030b21  jz      loc_180030D71
0x180030b27  mov     [rcx], r15w
0x180030b2b  mov     rax, cs:g_pfnResultLoggingCallback
0x180030b32  test    rax, rax
0x180030b35  jz      short loc_180030B58
0x180030b37  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180030b3e  jz      short loc_180030B58
0x180030b40  mov     r8, rdx
0x180030b43  mov     rdx, rcx
0x180030b46  mov     rcx, rbx
0x180030b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b4e  cmp     [r14], r15w
0x180030b52  jnz     loc_180030D71
0x180030b58  mov     ecx, [rbx]
0x180030b5a  mov     bpl, 8
0x180030b5d  test    ecx, ecx
0x180030b5f  jz      short loc_180030BAA
0x180030b61  sub     ecx, 1
0x180030b64  jz      short loc_180030B92
0x180030b66  sub     ecx, 1
0x180030b69  jz      short loc_180030B82
0x180030b6b  cmp     ecx, 1
0x180030b6e  jz      short loc_180030B79
0x180030b70  lea     rdi, qword_18009E510
0x180030b77  jmp     short loc_180030BB1
0x180030b79  lea     rdi, aFailfast; "FailFast"
0x180030b80  jmp     short loc_180030BB1
0x180030b82  lea     rax, aLoghr; "LogHr"
0x180030b89  lea     rdi, aLognt; "LogNt"
0x180030b90  jmp     short loc_180030BA0
0x180030b92  lea     rax, aReturnhr; "ReturnHr"
0x180030b99  lea     rdi, aReturnnt; "ReturnNt"
0x180030ba0  test    [rbx+4], bpl
0x180030ba4  cmovz   rdi, rax
0x180030ba8  jmp     short loc_180030BB1
0x180030baa  lea     rdi, aException; "Exception"
0x180030bb1  xor     edx, edx; Val
0x180030bb3  mov     r8d, 200h; Size
0x180030bb9  lea     rcx, [rsp+278h+Buffer]; void *
0x180030bbe  call    memset_0
0x180030bc3  test    [rbx+4], bpl
0x180030bc7  jz      short loc_180030BEC
0x180030bc9  mov     ebp, [rbx+0Ch]
0x180030bcc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180030bd3  test    rax, rax
0x180030bd6  jz      short loc_180030C1C
0x180030bd8  mov     r8d, 100h
0x180030bde  lea     rdx, [rsp+278h+Buffer]
0x180030be3  mov     ecx, ebp
0x180030be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030bea  jmp     short loc_180030C1C
0x180030bec  mov     ebp, [rbx+8]
0x180030bef  mov     [rsp+278h+Arguments], r15; Arguments
0x180030bf4  mov     [rsp+278h+nSize], 100h; nSize
0x180030bfc  lea     rax, [rsp+278h+Buffer]
0x180030c01  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180030c06  mov     r9d, 400h; dwLanguageId
0x180030c0c  mov     r8d, ebp; dwMessageId
0x180030c0f  xor     edx, edx; lpSource
0x180030c11  mov     ecx, 1200h; dwFlags
0x180030c16  call    cs:__imp_FormatMessageW
0x180030c1c  lea     rsi, [r14+rsi*2]
0x180030c20  mov     r9, [rbx+38h]; unsigned __int16 *
0x180030c24  mov     rax, [rbx+88h]
0x180030c2b  mov     rcx, [rbx+80h]
0x180030c32  mov     rdx, rsi; unsigned __int16 *
0x180030c35  test    r9, r9
0x180030c38  jz      short loc_180030C5C
0x180030c3a  mov     [rsp+278h+Arguments], rax
0x180030c3f  mov     qword ptr [rsp+278h+nSize], rcx
0x180030c44  mov     eax, [rbx+40h]
0x180030c47  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180030c4b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180030c52  mov     rcx, r14; this
0x180030c55  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180030c5a  jmp     short loc_180030C73
0x180030c5c  mov     [rsp+278h+lpBuffer], rax
0x180030c61  mov     r9, rcx; unsigned __int16 *
0x180030c64  lea     r8, aHsP; "%hs!%p: "
0x180030c6b  mov     rcx, r14; this
0x180030c6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180030c73  mov     r14, rax
0x180030c76  mov     r9, [rbx+90h]; unsigned __int16 *
0x180030c7d  test    r9, r9
0x180030c80  jz      short loc_180030C97
0x180030c82  lea     r8, aCallerP; "(caller: %p) "
0x180030c89  mov     rdx, rsi; unsigned __int16 *
0x180030c8c  mov     rcx, rax; this
0x180030c8f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180030c94  mov     r14, rax
0x180030c97  call    cs:__imp_GetCurrentThreadId
0x180030c9d  lea     rcx, [rsp+278h+Buffer]
0x180030ca2  mov     [rsp+278h+var_240], rcx
0x180030ca7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180030cab  mov     [rsp+278h+nSize], eax
0x180030caf  mov     eax, [rbx+44h]
0x180030cb2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180030cb6  mov     r9, rdi; unsigned __int16 *
0x180030cb9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180030cc0  mov     rdx, rsi; unsigned __int16 *
0x180030cc3  mov     rcx, r14; this
0x180030cc6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180030ccb  cmp     [rbx+18h], r15
0x180030ccf  jnz     short loc_180030CE1
0x180030cd1  cmp     [rbx+48h], r15
0x180030cd5  jnz     short loc_180030CE1
0x180030cd7  cmp     [rbx+30h], r15
0x180030cdb  jz      loc_180030D71
0x180030ce1  lea     r8, asc_18009EAE0; "    "
0x180030ce8  mov     rdx, rsi; unsigned __int16 *
0x180030ceb  mov     rcx, rax; this
0x180030cee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180030cf3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180030cf7  test    r9, r9
0x180030cfa  jz      short loc_180030D0E
0x180030cfc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180030d03  mov     rdx, rsi; unsigned __int16 *
0x180030d06  mov     rcx, rax; this
0x180030d09  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180030d0e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180030d12  test    r9, r9
0x180030d15  jz      short loc_180030D29
0x180030d17  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180030d1e  mov     rdx, rsi; unsigned __int16 *
0x180030d21  mov     rcx, rax; this
0x180030d24  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180030d29  mov     rcx, [rbx+28h]
0x180030d2d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180030d31  mov     rdx, rsi; unsigned __int16 *
0x180030d34  test    rcx, rcx
0x180030d37  jz      short loc_180030D4F
0x180030d39  mov     [rsp+278h+lpBuffer], rcx
0x180030d3e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180030d45  mov     rcx, rax; this
0x180030d48  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180030d4d  jmp     short loc_180030D71
0x180030d4f  mov     rcx, rax; this
0x180030d52  test    r9, r9
0x180030d55  jz      short loc_180030D65
0x180030d57  lea     r8, aHs; "[%hs]\n"
0x180030d5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180030d63  jmp     short loc_180030D71
0x180030d65  lea     r8, asc_18009EB58; "\n"
0x180030d6c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180030d71  xor     eax, eax
0x180030d73  mov     rcx, [rsp+278h+var_38]
0x180030d7b  xor     rcx, rsp; StackCookie
0x180030d7e  call    __security_check_cookie
0x180030d83  mov     rbx, [rsp+278h+arg_18]
0x180030d8b  add     rsp, 250h
0x180030d92  pop     r15
0x180030d94  pop     r14
0x180030d96  pop     rdi
0x180030d97  pop     rsi
0x180030d98  pop     rbp
0x180030d99  retn
```
