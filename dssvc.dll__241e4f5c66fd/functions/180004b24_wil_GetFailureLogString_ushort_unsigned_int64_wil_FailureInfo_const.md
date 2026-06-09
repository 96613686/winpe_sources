# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004b24`
- end: `0x180004dda`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180003cd8`
- `0x1800055ac`
- `0x18001aeb0`

## callees

- `0x180004b24`
- `0x1800058ac`
- `0x18001b30a`
- `0x18001b340`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004cd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004cd7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004c56`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004c56`

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
          v8 = (const char *)&dword_18001EA9C;
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
0x180004b24  mov     [rsp+arg_18], rbx
0x180004b29  push    rbp
0x180004b2a  push    rsi
0x180004b2b  push    rdi
0x180004b2c  push    r14
0x180004b2e  push    r15
0x180004b30  sub     rsp, 250h
0x180004b37  mov     rax, cs:__security_cookie
0x180004b3e  xor     rax, rsp
0x180004b41  mov     [rsp+278h+var_38], rax
0x180004b49  xor     r15d, r15d
0x180004b4c  mov     rbx, r8
0x180004b4f  mov     rsi, rdx
0x180004b52  mov     r14, rcx
0x180004b55  test    rdx, rdx
0x180004b58  jz      loc_180004DB1
0x180004b5e  test    rcx, rcx
0x180004b61  jz      loc_180004DB1
0x180004b67  mov     rax, cs:g_pfnResultLoggingCallback
0x180004b6e  mov     [rcx], r15w
0x180004b72  test    rax, rax
0x180004b75  jz      short loc_180004B98
0x180004b77  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004b7e  jz      short loc_180004B98
0x180004b80  mov     r8, rdx
0x180004b83  mov     rdx, rcx
0x180004b86  mov     rcx, rbx
0x180004b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b8e  cmp     [r14], r15w
0x180004b92  jnz     loc_180004DB1
0x180004b98  mov     ecx, [rbx]
0x180004b9a  mov     bpl, 8
0x180004b9d  test    ecx, ecx
0x180004b9f  jz      short loc_180004BEA
0x180004ba1  sub     ecx, 1
0x180004ba4  jz      short loc_180004BD2
0x180004ba6  sub     ecx, 1
0x180004ba9  jz      short loc_180004BC2
0x180004bab  cmp     ecx, 1
0x180004bae  jz      short loc_180004BB9
0x180004bb0  lea     rdi, dword_18001EA9C
0x180004bb7  jmp     short loc_180004BF1
0x180004bb9  lea     rdi, aFailfast; "FailFast"
0x180004bc0  jmp     short loc_180004BF1
0x180004bc2  lea     rax, aLoghr; "LogHr"
0x180004bc9  lea     rdi, aLognt; "LogNt"
0x180004bd0  jmp     short loc_180004BE0
0x180004bd2  lea     rax, aReturnhr; "ReturnHr"
0x180004bd9  lea     rdi, aReturnnt; "ReturnNt"
0x180004be0  test    [rbx+4], bpl
0x180004be4  cmovz   rdi, rax
0x180004be8  jmp     short loc_180004BF1
0x180004bea  lea     rdi, aException; "Exception"
0x180004bf1  xor     edx, edx; Val
0x180004bf3  lea     rcx, [rsp+278h+Buffer]; void *
0x180004bf8  mov     r8d, 200h; Size
0x180004bfe  call    memset_0
0x180004c03  test    [rbx+4], bpl
0x180004c07  jz      short loc_180004C2C
0x180004c09  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004c10  mov     ebp, [rbx+0Ch]
0x180004c13  test    rax, rax
0x180004c16  jz      short loc_180004C5C
0x180004c18  mov     r8d, 100h
0x180004c1e  lea     rdx, [rsp+278h+Buffer]
0x180004c23  mov     ecx, ebp
0x180004c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c2a  jmp     short loc_180004C5C
0x180004c2c  mov     ebp, [rbx+8]
0x180004c2f  lea     rax, [rsp+278h+Buffer]
0x180004c34  mov     [rsp+278h+Arguments], r15; Arguments
0x180004c39  mov     r8d, ebp; dwMessageId
0x180004c3c  mov     [rsp+278h+nSize], 100h; nSize
0x180004c44  mov     r9d, 400h; dwLanguageId
0x180004c4a  xor     edx, edx; lpSource
0x180004c4c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004c51  mov     ecx, 1200h; dwFlags
0x180004c56  call    cs:__imp_FormatMessageW
0x180004c5c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004c60  lea     rsi, [r14+rsi*2]
0x180004c64  mov     rax, [rbx+88h]
0x180004c6b  mov     rdx, rsi; unsigned __int16 *
0x180004c6e  mov     rcx, [rbx+80h]
0x180004c75  test    r9, r9
0x180004c78  jz      short loc_180004C9C
0x180004c7a  mov     [rsp+278h+Arguments], rax
0x180004c7f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004c86  mov     eax, [rbx+40h]
0x180004c89  mov     qword ptr [rsp+278h+nSize], rcx
0x180004c8e  mov     rcx, r14; this
0x180004c91  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004c95  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004c9a  jmp     short loc_180004CB3
0x180004c9c  mov     r9, rcx; unsigned __int16 *
0x180004c9f  mov     [rsp+278h+lpBuffer], rax
0x180004ca4  mov     rcx, r14; this
0x180004ca7  lea     r8, aHsP; "%hs!%p: "
0x180004cae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004cb3  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004cba  mov     r14, rax
0x180004cbd  test    r9, r9
0x180004cc0  jz      short loc_180004CD7
0x180004cc2  lea     r8, aCallerP; "(caller: %p) "
0x180004cc9  mov     rdx, rsi; unsigned __int16 *
0x180004ccc  mov     rcx, rax; this
0x180004ccf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004cd4  mov     r14, rax
0x180004cd7  call    cs:__imp_GetCurrentThreadId
0x180004cdd  lea     rcx, [rsp+278h+Buffer]
0x180004ce2  mov     r9, rdi; unsigned __int16 *
0x180004ce5  mov     [rsp+278h+var_240], rcx
0x180004cea  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004cf1  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004cf5  mov     rdx, rsi; unsigned __int16 *
0x180004cf8  mov     [rsp+278h+nSize], eax
0x180004cfc  mov     rcx, r14; this
0x180004cff  mov     eax, [rbx+44h]
0x180004d02  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004d06  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004d0b  cmp     [rbx+18h], r15
0x180004d0f  jnz     short loc_180004D21
0x180004d11  cmp     [rbx+48h], r15
0x180004d15  jnz     short loc_180004D21
0x180004d17  cmp     [rbx+30h], r15
0x180004d1b  jz      loc_180004DB1
0x180004d21  lea     r8, asc_18001EB90; "    "
0x180004d28  mov     rdx, rsi; unsigned __int16 *
0x180004d2b  mov     rcx, rax; this
0x180004d2e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004d33  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004d37  test    r9, r9
0x180004d3a  jz      short loc_180004D4E
0x180004d3c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004d43  mov     rdx, rsi; unsigned __int16 *
0x180004d46  mov     rcx, rax; this
0x180004d49  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004d4e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004d52  test    r9, r9
0x180004d55  jz      short loc_180004D69
0x180004d57  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180004d5e  mov     rdx, rsi; unsigned __int16 *
0x180004d61  mov     rcx, rax; this
0x180004d64  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004d69  mov     rcx, [rbx+28h]
0x180004d6d  mov     rdx, rsi; unsigned __int16 *
0x180004d70  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004d74  test    rcx, rcx
0x180004d77  jz      short loc_180004D8F
0x180004d79  mov     [rsp+278h+lpBuffer], rcx
0x180004d7e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004d85  mov     rcx, rax; this
0x180004d88  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004d8d  jmp     short loc_180004DB1
0x180004d8f  mov     rcx, rax; this
0x180004d92  test    r9, r9
0x180004d95  jz      short loc_180004DA5
0x180004d97  lea     r8, aHs; "[%hs]\n"
0x180004d9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004da3  jmp     short loc_180004DB1
0x180004da5  lea     r8, asc_18001EC08; "\n"
0x180004dac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004db1  xor     eax, eax
0x180004db3  mov     rcx, [rsp+278h+var_38]
0x180004dbb  xor     rcx, rsp; StackCookie
0x180004dbe  call    __security_check_cookie
0x180004dc3  mov     rbx, [rsp+278h+arg_18]
0x180004dcb  add     rsp, 250h
0x180004dd2  pop     r15
0x180004dd4  pop     r14
0x180004dd6  pop     rdi
0x180004dd7  pop     rsi
0x180004dd8  pop     rbp
0x180004dd9  retn
```
