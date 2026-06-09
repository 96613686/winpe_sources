# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004ba4`
- end: `0x180004e5a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180003d28`
- `0x1800055bc`
- `0x180005a84`
- `0x180006cc0`

## callees

- `0x180002b10`
- `0x1800035a0`
- `0x180004ba4`
- `0x1800058bc`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d57`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004cd6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004cd6`

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
          v7 = (const char *)&qword_18001DBF0;
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
0x180004ba4  mov     [rsp+arg_18], rbx
0x180004ba9  push    rbp
0x180004baa  push    rsi
0x180004bab  push    rdi
0x180004bac  push    r14
0x180004bae  push    r15
0x180004bb0  sub     rsp, 250h
0x180004bb7  mov     rax, cs:__security_cookie
0x180004bbe  xor     rax, rsp
0x180004bc1  mov     [rsp+278h+var_38], rax
0x180004bc9  mov     rbx, r8
0x180004bcc  mov     rsi, rdx
0x180004bcf  mov     r14, rcx
0x180004bd2  xor     r15d, r15d
0x180004bd5  test    rdx, rdx
0x180004bd8  jz      loc_180004E31
0x180004bde  test    rcx, rcx
0x180004be1  jz      loc_180004E31
0x180004be7  mov     [rcx], r15w
0x180004beb  mov     rax, cs:g_pfnResultLoggingCallback
0x180004bf2  test    rax, rax
0x180004bf5  jz      short loc_180004C18
0x180004bf7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004bfe  jz      short loc_180004C18
0x180004c00  mov     r8, rdx
0x180004c03  mov     rdx, rcx
0x180004c06  mov     rcx, rbx
0x180004c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c0e  cmp     [r14], r15w
0x180004c12  jnz     loc_180004E31
0x180004c18  mov     ecx, [rbx]
0x180004c1a  mov     bpl, 8
0x180004c1d  test    ecx, ecx
0x180004c1f  jz      short loc_180004C6A
0x180004c21  sub     ecx, 1
0x180004c24  jz      short loc_180004C52
0x180004c26  sub     ecx, 1
0x180004c29  jz      short loc_180004C42
0x180004c2b  cmp     ecx, 1
0x180004c2e  jz      short loc_180004C39
0x180004c30  lea     rdi, qword_18001DBF0
0x180004c37  jmp     short loc_180004C71
0x180004c39  lea     rdi, aFailfast; "FailFast"
0x180004c40  jmp     short loc_180004C71
0x180004c42  lea     rax, aLoghr; "LogHr"
0x180004c49  lea     rdi, aLognt; "LogNt"
0x180004c50  jmp     short loc_180004C60
0x180004c52  lea     rax, aReturnhr; "ReturnHr"
0x180004c59  lea     rdi, aReturnnt; "ReturnNt"
0x180004c60  test    [rbx+4], bpl
0x180004c64  cmovz   rdi, rax
0x180004c68  jmp     short loc_180004C71
0x180004c6a  lea     rdi, aException; "Exception"
0x180004c71  xor     edx, edx; Val
0x180004c73  mov     r8d, 200h; Size
0x180004c79  lea     rcx, [rsp+278h+Buffer]; void *
0x180004c7e  call    memset_0
0x180004c83  test    [rbx+4], bpl
0x180004c87  jz      short loc_180004CAC
0x180004c89  mov     ebp, [rbx+0Ch]
0x180004c8c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004c93  test    rax, rax
0x180004c96  jz      short loc_180004CDC
0x180004c98  mov     r8d, 100h
0x180004c9e  lea     rdx, [rsp+278h+Buffer]
0x180004ca3  mov     ecx, ebp
0x180004ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004caa  jmp     short loc_180004CDC
0x180004cac  mov     ebp, [rbx+8]
0x180004caf  mov     [rsp+278h+Arguments], r15; Arguments
0x180004cb4  mov     [rsp+278h+nSize], 100h; nSize
0x180004cbc  lea     rax, [rsp+278h+Buffer]
0x180004cc1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004cc6  mov     r9d, 400h; dwLanguageId
0x180004ccc  mov     r8d, ebp; dwMessageId
0x180004ccf  xor     edx, edx; lpSource
0x180004cd1  mov     ecx, 1200h; dwFlags
0x180004cd6  call    cs:__imp_FormatMessageW
0x180004cdc  lea     rsi, [r14+rsi*2]
0x180004ce0  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004ce4  mov     rax, [rbx+88h]
0x180004ceb  mov     rcx, [rbx+80h]
0x180004cf2  mov     rdx, rsi; unsigned __int16 *
0x180004cf5  test    r9, r9
0x180004cf8  jz      short loc_180004D1C
0x180004cfa  mov     [rsp+278h+Arguments], rax
0x180004cff  mov     qword ptr [rsp+278h+nSize], rcx
0x180004d04  mov     eax, [rbx+40h]
0x180004d07  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004d0b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004d12  mov     rcx, r14; this
0x180004d15  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004d1a  jmp     short loc_180004D33
0x180004d1c  mov     [rsp+278h+lpBuffer], rax
0x180004d21  mov     r9, rcx; unsigned __int16 *
0x180004d24  lea     r8, aHsP; "%hs!%p: "
0x180004d2b  mov     rcx, r14; this
0x180004d2e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004d33  mov     r14, rax
0x180004d36  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004d3d  test    r9, r9
0x180004d40  jz      short loc_180004D57
0x180004d42  lea     r8, aCallerP; "(caller: %p) "
0x180004d49  mov     rdx, rsi; unsigned __int16 *
0x180004d4c  mov     rcx, rax; this
0x180004d4f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004d54  mov     r14, rax
0x180004d57  call    cs:__imp_GetCurrentThreadId
0x180004d5d  lea     rcx, [rsp+278h+Buffer]
0x180004d62  mov     [rsp+278h+var_240], rcx
0x180004d67  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004d6b  mov     [rsp+278h+nSize], eax
0x180004d6f  mov     eax, [rbx+44h]
0x180004d72  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004d76  mov     r9, rdi; unsigned __int16 *
0x180004d79  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004d80  mov     rdx, rsi; unsigned __int16 *
0x180004d83  mov     rcx, r14; this
0x180004d86  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004d8b  cmp     [rbx+18h], r15
0x180004d8f  jnz     short loc_180004DA1
0x180004d91  cmp     [rbx+48h], r15
0x180004d95  jnz     short loc_180004DA1
0x180004d97  cmp     [rbx+30h], r15
0x180004d9b  jz      loc_180004E31
0x180004da1  lea     r8, asc_18001DCF8; "    "
0x180004da8  mov     rdx, rsi; unsigned __int16 *
0x180004dab  mov     rcx, rax; this
0x180004dae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004db3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004db7  test    r9, r9
0x180004dba  jz      short loc_180004DCE
0x180004dbc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004dc3  mov     rdx, rsi; unsigned __int16 *
0x180004dc6  mov     rcx, rax; this
0x180004dc9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004dce  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004dd2  test    r9, r9
0x180004dd5  jz      short loc_180004DE9
0x180004dd7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180004dde  mov     rdx, rsi; unsigned __int16 *
0x180004de1  mov     rcx, rax; this
0x180004de4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004de9  mov     rcx, [rbx+28h]
0x180004ded  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004df1  mov     rdx, rsi; unsigned __int16 *
0x180004df4  test    rcx, rcx
0x180004df7  jz      short loc_180004E0F
0x180004df9  mov     [rsp+278h+lpBuffer], rcx
0x180004dfe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004e05  mov     rcx, rax; this
0x180004e08  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004e0d  jmp     short loc_180004E31
0x180004e0f  mov     rcx, rax; this
0x180004e12  test    r9, r9
0x180004e15  jz      short loc_180004E25
0x180004e17  lea     r8, aHs; "[%hs]\n"
0x180004e1e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004e23  jmp     short loc_180004E31
0x180004e25  lea     r8, asc_18001DD70; "\n"
0x180004e2c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004e31  xor     eax, eax
0x180004e33  mov     rcx, [rsp+278h+var_38]
0x180004e3b  xor     rcx, rsp; StackCookie
0x180004e3e  call    __security_check_cookie
0x180004e43  mov     rbx, [rsp+278h+arg_18]
0x180004e4b  add     rsp, 250h
0x180004e52  pop     r15
0x180004e54  pop     r14
0x180004e56  pop     rdi
0x180004e57  pop     rsi
0x180004e58  pop     rbp
0x180004e59  retn
```
