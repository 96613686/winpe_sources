# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1802659e4`
- end: `0x180265c9a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180264690`
- `0x1802663c8`

## callees

- `0x18025b100`
- `0x18025bb98`
- `0x1802659e4`
- `0x1802666c8`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180265b97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180265b97`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180265b16`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180265b16`

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
          v8 = (const char *)&word_18037105A;
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
0x1802659e4  mov     [rsp+arg_18], rbx
0x1802659e9  push    rbp
0x1802659ea  push    rsi
0x1802659eb  push    rdi
0x1802659ec  push    r14
0x1802659ee  push    r15
0x1802659f0  sub     rsp, 250h
0x1802659f7  mov     rax, cs:__security_cookie
0x1802659fe  xor     rax, rsp
0x180265a01  mov     [rsp+278h+var_38], rax
0x180265a09  xor     r15d, r15d
0x180265a0c  mov     rbx, r8
0x180265a0f  mov     rsi, rdx
0x180265a12  mov     r14, rcx
0x180265a15  test    rdx, rdx
0x180265a18  jz      loc_180265C71
0x180265a1e  test    rcx, rcx
0x180265a21  jz      loc_180265C71
0x180265a27  mov     rax, cs:g_pfnResultLoggingCallback
0x180265a2e  mov     [rcx], r15w
0x180265a32  test    rax, rax
0x180265a35  jz      short loc_180265A58
0x180265a37  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180265a3e  jz      short loc_180265A58
0x180265a40  mov     r8, rdx
0x180265a43  mov     rdx, rcx
0x180265a46  mov     rcx, rbx
0x180265a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180265a4e  cmp     [r14], r15w
0x180265a52  jnz     loc_180265C71
0x180265a58  mov     ecx, [rbx]
0x180265a5a  mov     bpl, 8
0x180265a5d  test    ecx, ecx
0x180265a5f  jz      short loc_180265AAA
0x180265a61  sub     ecx, 1
0x180265a64  jz      short loc_180265A92
0x180265a66  sub     ecx, 1
0x180265a69  jz      short loc_180265A82
0x180265a6b  cmp     ecx, 1
0x180265a6e  jz      short loc_180265A79
0x180265a70  lea     rdi, word_18037105A
0x180265a77  jmp     short loc_180265AB1
0x180265a79  lea     rdi, aFailfast; "FailFast"
0x180265a80  jmp     short loc_180265AB1
0x180265a82  lea     rax, aLoghr; "LogHr"
0x180265a89  lea     rdi, aLognt; "LogNt"
0x180265a90  jmp     short loc_180265AA0
0x180265a92  lea     rax, aReturnhr; "ReturnHr"
0x180265a99  lea     rdi, aReturnnt; "ReturnNt"
0x180265aa0  test    [rbx+4], bpl
0x180265aa4  cmovz   rdi, rax
0x180265aa8  jmp     short loc_180265AB1
0x180265aaa  lea     rdi, aException; "Exception"
0x180265ab1  xor     edx, edx; Val
0x180265ab3  lea     rcx, [rsp+278h+Buffer]; void *
0x180265ab8  mov     r8d, 200h; Size
0x180265abe  call    memset_0
0x180265ac3  test    [rbx+4], bpl
0x180265ac7  jz      short loc_180265AEC
0x180265ac9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180265ad0  mov     ebp, [rbx+0Ch]
0x180265ad3  test    rax, rax
0x180265ad6  jz      short loc_180265B1C
0x180265ad8  mov     r8d, 100h
0x180265ade  lea     rdx, [rsp+278h+Buffer]
0x180265ae3  mov     ecx, ebp
0x180265ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180265aea  jmp     short loc_180265B1C
0x180265aec  mov     ebp, [rbx+8]
0x180265aef  lea     rax, [rsp+278h+Buffer]
0x180265af4  mov     [rsp+278h+Arguments], r15; Arguments
0x180265af9  mov     r8d, ebp; dwMessageId
0x180265afc  mov     [rsp+278h+nSize], 100h; nSize
0x180265b04  mov     r9d, 400h; dwLanguageId
0x180265b0a  xor     edx, edx; lpSource
0x180265b0c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180265b11  mov     ecx, 1200h; dwFlags
0x180265b16  call    cs:__imp_FormatMessageW
0x180265b1c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180265b20  lea     rsi, [r14+rsi*2]
0x180265b24  mov     rax, [rbx+88h]
0x180265b2b  mov     rdx, rsi; unsigned __int16 *
0x180265b2e  mov     rcx, [rbx+80h]
0x180265b35  test    r9, r9
0x180265b38  jz      short loc_180265B5C
0x180265b3a  mov     [rsp+278h+Arguments], rax
0x180265b3f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180265b46  mov     eax, [rbx+40h]
0x180265b49  mov     qword ptr [rsp+278h+nSize], rcx
0x180265b4e  mov     rcx, r14; this
0x180265b51  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180265b55  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180265b5a  jmp     short loc_180265B73
0x180265b5c  mov     r9, rcx; unsigned __int16 *
0x180265b5f  mov     [rsp+278h+lpBuffer], rax
0x180265b64  mov     rcx, r14; this
0x180265b67  lea     r8, aHsP; "%hs!%p: "
0x180265b6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180265b73  mov     r9, [rbx+90h]; unsigned __int16 *
0x180265b7a  mov     r14, rax
0x180265b7d  test    r9, r9
0x180265b80  jz      short loc_180265B97
0x180265b82  lea     r8, aCallerP; "(caller: %p) "
0x180265b89  mov     rdx, rsi; unsigned __int16 *
0x180265b8c  mov     rcx, rax; this
0x180265b8f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180265b94  mov     r14, rax
0x180265b97  call    cs:__imp_GetCurrentThreadId
0x180265b9d  lea     rcx, [rsp+278h+Buffer]
0x180265ba2  mov     r9, rdi; unsigned __int16 *
0x180265ba5  mov     [rsp+278h+var_240], rcx
0x180265baa  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180265bb1  mov     dword ptr [rsp+278h+Arguments], ebp
0x180265bb5  mov     rdx, rsi; unsigned __int16 *
0x180265bb8  mov     [rsp+278h+nSize], eax
0x180265bbc  mov     rcx, r14; this
0x180265bbf  mov     eax, [rbx+44h]
0x180265bc2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180265bc6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180265bcb  cmp     [rbx+18h], r15
0x180265bcf  jnz     short loc_180265BE1
0x180265bd1  cmp     [rbx+48h], r15
0x180265bd5  jnz     short loc_180265BE1
0x180265bd7  cmp     [rbx+30h], r15
0x180265bdb  jz      loc_180265C71
0x180265be1  lea     r8, asc_1803E95F0; "    "
0x180265be8  mov     rdx, rsi; unsigned __int16 *
0x180265beb  mov     rcx, rax; this
0x180265bee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180265bf3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180265bf7  test    r9, r9
0x180265bfa  jz      short loc_180265C0E
0x180265bfc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180265c03  mov     rdx, rsi; unsigned __int16 *
0x180265c06  mov     rcx, rax; this
0x180265c09  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180265c0e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180265c12  test    r9, r9
0x180265c15  jz      short loc_180265C29
0x180265c17  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180265c1e  mov     rdx, rsi; unsigned __int16 *
0x180265c21  mov     rcx, rax; this
0x180265c24  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180265c29  mov     rcx, [rbx+28h]
0x180265c2d  mov     rdx, rsi; unsigned __int16 *
0x180265c30  mov     r9, [rbx+30h]; unsigned __int16 *
0x180265c34  test    rcx, rcx
0x180265c37  jz      short loc_180265C4F
0x180265c39  mov     [rsp+278h+lpBuffer], rcx
0x180265c3e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180265c45  mov     rcx, rax; this
0x180265c48  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180265c4d  jmp     short loc_180265C71
0x180265c4f  mov     rcx, rax; this
0x180265c52  test    r9, r9
0x180265c55  jz      short loc_180265C65
0x180265c57  lea     r8, aHs; "[%hs]\n"
0x180265c5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180265c63  jmp     short loc_180265C71
0x180265c65  lea     r8, asc_1803E9668; "\n"
0x180265c6c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180265c71  xor     eax, eax
0x180265c73  mov     rcx, [rsp+278h+var_38]
0x180265c7b  xor     rcx, rsp; StackCookie
0x180265c7e  call    __security_check_cookie
0x180265c83  mov     rbx, [rsp+278h+arg_18]
0x180265c8b  add     rsp, 250h
0x180265c92  pop     r15
0x180265c94  pop     r14
0x180265c96  pop     rdi
0x180265c97  pop     rsi
0x180265c98  pop     rbp
0x180265c99  retn
```
