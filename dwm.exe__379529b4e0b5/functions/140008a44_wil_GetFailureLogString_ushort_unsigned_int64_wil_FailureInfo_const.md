# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140008a44`
- end: `0x140008cfa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140006f40`
- `0x14000943c`

## callees

- `0x140005530`
- `0x1400061b8`
- `0x140008a44`
- `0x14000973c`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008bf7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008bf7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140008b76`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140008b76`

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
          v8 = (const char *)&dword_1400128B4;
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
0x140008a44  mov     [rsp+arg_18], rbx
0x140008a49  push    rbp
0x140008a4a  push    rsi
0x140008a4b  push    rdi
0x140008a4c  push    r14
0x140008a4e  push    r15
0x140008a50  sub     rsp, 250h
0x140008a57  mov     rax, cs:__security_cookie
0x140008a5e  xor     rax, rsp
0x140008a61  mov     [rsp+278h+var_38], rax
0x140008a69  xor     r15d, r15d
0x140008a6c  mov     rbx, r8
0x140008a6f  mov     rsi, rdx
0x140008a72  mov     r14, rcx
0x140008a75  test    rdx, rdx
0x140008a78  jz      loc_140008CD1
0x140008a7e  test    rcx, rcx
0x140008a81  jz      loc_140008CD1
0x140008a87  mov     rax, cs:g_pfnResultLoggingCallback
0x140008a8e  mov     [rcx], r15w
0x140008a92  test    rax, rax
0x140008a95  jz      short loc_140008AB8
0x140008a97  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140008a9e  jz      short loc_140008AB8
0x140008aa0  mov     r8, rdx
0x140008aa3  mov     rdx, rcx
0x140008aa6  mov     rcx, rbx
0x140008aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008aae  cmp     [r14], r15w
0x140008ab2  jnz     loc_140008CD1
0x140008ab8  mov     ecx, [rbx]
0x140008aba  mov     bpl, 8
0x140008abd  test    ecx, ecx
0x140008abf  jz      short loc_140008B0A
0x140008ac1  sub     ecx, 1
0x140008ac4  jz      short loc_140008AF2
0x140008ac6  sub     ecx, 1
0x140008ac9  jz      short loc_140008AE2
0x140008acb  cmp     ecx, 1
0x140008ace  jz      short loc_140008AD9
0x140008ad0  lea     rdi, dword_1400128B4
0x140008ad7  jmp     short loc_140008B11
0x140008ad9  lea     rdi, aFailfast; "FailFast"
0x140008ae0  jmp     short loc_140008B11
0x140008ae2  lea     rax, aLoghr; "LogHr"
0x140008ae9  lea     rdi, aLognt; "LogNt"
0x140008af0  jmp     short loc_140008B00
0x140008af2  lea     rax, aReturnhr; "ReturnHr"
0x140008af9  lea     rdi, aReturnnt; "ReturnNt"
0x140008b00  test    [rbx+4], bpl
0x140008b04  cmovz   rdi, rax
0x140008b08  jmp     short loc_140008B11
0x140008b0a  lea     rdi, aException; "Exception"
0x140008b11  xor     edx, edx; Val
0x140008b13  lea     rcx, [rsp+278h+Buffer]; void *
0x140008b18  mov     r8d, 200h; Size
0x140008b1e  call    memset_0
0x140008b23  test    [rbx+4], bpl
0x140008b27  jz      short loc_140008B4C
0x140008b29  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140008b30  mov     ebp, [rbx+0Ch]
0x140008b33  test    rax, rax
0x140008b36  jz      short loc_140008B7C
0x140008b38  mov     r8d, 100h
0x140008b3e  lea     rdx, [rsp+278h+Buffer]
0x140008b43  mov     ecx, ebp
0x140008b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008b4a  jmp     short loc_140008B7C
0x140008b4c  mov     ebp, [rbx+8]
0x140008b4f  lea     rax, [rsp+278h+Buffer]
0x140008b54  mov     [rsp+278h+Arguments], r15; Arguments
0x140008b59  mov     r8d, ebp; dwMessageId
0x140008b5c  mov     [rsp+278h+nSize], 100h; nSize
0x140008b64  mov     r9d, 400h; dwLanguageId
0x140008b6a  xor     edx, edx; lpSource
0x140008b6c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140008b71  mov     ecx, 1200h; dwFlags
0x140008b76  call    cs:__imp_FormatMessageW
0x140008b7c  mov     r9, [rbx+38h]; unsigned __int16 *
0x140008b80  lea     rsi, [r14+rsi*2]
0x140008b84  mov     rax, [rbx+88h]
0x140008b8b  mov     rdx, rsi; unsigned __int16 *
0x140008b8e  mov     rcx, [rbx+80h]
0x140008b95  test    r9, r9
0x140008b98  jz      short loc_140008BBC
0x140008b9a  mov     [rsp+278h+Arguments], rax
0x140008b9f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140008ba6  mov     eax, [rbx+40h]
0x140008ba9  mov     qword ptr [rsp+278h+nSize], rcx
0x140008bae  mov     rcx, r14; this
0x140008bb1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140008bb5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140008bba  jmp     short loc_140008BD3
0x140008bbc  mov     r9, rcx; unsigned __int16 *
0x140008bbf  mov     [rsp+278h+lpBuffer], rax
0x140008bc4  mov     rcx, r14; this
0x140008bc7  lea     r8, aHsP; "%hs!%p: "
0x140008bce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140008bd3  mov     r9, [rbx+90h]; unsigned __int16 *
0x140008bda  mov     r14, rax
0x140008bdd  test    r9, r9
0x140008be0  jz      short loc_140008BF7
0x140008be2  lea     r8, aCallerP; "(caller: %p) "
0x140008be9  mov     rdx, rsi; unsigned __int16 *
0x140008bec  mov     rcx, rax; this
0x140008bef  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140008bf4  mov     r14, rax
0x140008bf7  call    cs:__imp_GetCurrentThreadId
0x140008bfd  lea     rcx, [rsp+278h+Buffer]
0x140008c02  mov     r9, rdi; unsigned __int16 *
0x140008c05  mov     [rsp+278h+var_240], rcx
0x140008c0a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140008c11  mov     dword ptr [rsp+278h+Arguments], ebp
0x140008c15  mov     rdx, rsi; unsigned __int16 *
0x140008c18  mov     [rsp+278h+nSize], eax
0x140008c1c  mov     rcx, r14; this
0x140008c1f  mov     eax, [rbx+44h]
0x140008c22  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140008c26  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140008c2b  cmp     [rbx+18h], r15
0x140008c2f  jnz     short loc_140008C41
0x140008c31  cmp     [rbx+48h], r15
0x140008c35  jnz     short loc_140008C41
0x140008c37  cmp     [rbx+30h], r15
0x140008c3b  jz      loc_140008CD1
0x140008c41  lea     r8, asc_1400129A8; "    "
0x140008c48  mov     rdx, rsi; unsigned __int16 *
0x140008c4b  mov     rcx, rax; this
0x140008c4e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140008c53  mov     r9, [rbx+18h]; unsigned __int16 *
0x140008c57  test    r9, r9
0x140008c5a  jz      short loc_140008C6E
0x140008c5c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140008c63  mov     rdx, rsi; unsigned __int16 *
0x140008c66  mov     rcx, rax; this
0x140008c69  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140008c6e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140008c72  test    r9, r9
0x140008c75  jz      short loc_140008C89
0x140008c77  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140008c7e  mov     rdx, rsi; unsigned __int16 *
0x140008c81  mov     rcx, rax; this
0x140008c84  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140008c89  mov     rcx, [rbx+28h]
0x140008c8d  mov     rdx, rsi; unsigned __int16 *
0x140008c90  mov     r9, [rbx+30h]; unsigned __int16 *
0x140008c94  test    rcx, rcx
0x140008c97  jz      short loc_140008CAF
0x140008c99  mov     [rsp+278h+lpBuffer], rcx
0x140008c9e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140008ca5  mov     rcx, rax; this
0x140008ca8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140008cad  jmp     short loc_140008CD1
0x140008caf  mov     rcx, rax; this
0x140008cb2  test    r9, r9
0x140008cb5  jz      short loc_140008CC5
0x140008cb7  lea     r8, aHs; "[%hs]\n"
0x140008cbe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140008cc3  jmp     short loc_140008CD1
0x140008cc5  lea     r8, asc_140012A20; "\n"
0x140008ccc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140008cd1  xor     eax, eax
0x140008cd3  mov     rcx, [rsp+278h+var_38]
0x140008cdb  xor     rcx, rsp; StackCookie
0x140008cde  call    __security_check_cookie
0x140008ce3  mov     rbx, [rsp+278h+arg_18]
0x140008ceb  add     rsp, 250h
0x140008cf2  pop     r15
0x140008cf4  pop     r14
0x140008cf6  pop     rdi
0x140008cf7  pop     rsi
0x140008cf8  pop     rbp
0x140008cf9  retn
```
