# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18002ba78`
- end: `0x18002bd2e`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180029888`
- `0x18002cddc`
- `0x18002f8f0`

## callees

- `0x180001e80`
- `0x1800028ac`
- `0x18002ba78`
- `0x18002d0dc`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002bc2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002bc2b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002bbaa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002bbaa`

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
          v7 = (const char *)&word_180063CC2;
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
0x18002ba78  mov     [rsp+arg_18], rbx
0x18002ba7d  push    rbp
0x18002ba7e  push    rsi
0x18002ba7f  push    rdi
0x18002ba80  push    r14
0x18002ba82  push    r15
0x18002ba84  sub     rsp, 250h
0x18002ba8b  mov     rax, cs:__security_cookie
0x18002ba92  xor     rax, rsp
0x18002ba95  mov     [rsp+278h+var_38], rax
0x18002ba9d  mov     rbx, r8
0x18002baa0  mov     rsi, rdx
0x18002baa3  mov     r14, rcx
0x18002baa6  xor     r15d, r15d
0x18002baa9  test    rdx, rdx
0x18002baac  jz      loc_18002BD05
0x18002bab2  test    rcx, rcx
0x18002bab5  jz      loc_18002BD05
0x18002babb  mov     [rcx], r15w
0x18002babf  mov     rax, cs:g_pfnResultLoggingCallback
0x18002bac6  test    rax, rax
0x18002bac9  jz      short loc_18002BAEC
0x18002bacb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002bad2  jz      short loc_18002BAEC
0x18002bad4  mov     r8, rdx
0x18002bad7  mov     rdx, rcx
0x18002bada  mov     rcx, rbx
0x18002badd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bae2  cmp     [r14], r15w
0x18002bae6  jnz     loc_18002BD05
0x18002baec  mov     ecx, [rbx]
0x18002baee  mov     bpl, 8
0x18002baf1  test    ecx, ecx
0x18002baf3  jz      short loc_18002BB3E
0x18002baf5  sub     ecx, 1
0x18002baf8  jz      short loc_18002BB26
0x18002bafa  sub     ecx, 1
0x18002bafd  jz      short loc_18002BB16
0x18002baff  cmp     ecx, 1
0x18002bb02  jz      short loc_18002BB0D
0x18002bb04  lea     rdi, word_180063CC2
0x18002bb0b  jmp     short loc_18002BB45
0x18002bb0d  lea     rdi, aFailfast; "FailFast"
0x18002bb14  jmp     short loc_18002BB45
0x18002bb16  lea     rax, aLoghr; "LogHr"
0x18002bb1d  lea     rdi, aLognt; "LogNt"
0x18002bb24  jmp     short loc_18002BB34
0x18002bb26  lea     rax, aReturnhr; "ReturnHr"
0x18002bb2d  lea     rdi, aReturnnt; "ReturnNt"
0x18002bb34  test    [rbx+4], bpl
0x18002bb38  cmovz   rdi, rax
0x18002bb3c  jmp     short loc_18002BB45
0x18002bb3e  lea     rdi, aException; "Exception"
0x18002bb45  xor     edx, edx; Val
0x18002bb47  mov     r8d, 200h; Size
0x18002bb4d  lea     rcx, [rsp+278h+Buffer]; void *
0x18002bb52  call    memset_0
0x18002bb57  test    [rbx+4], bpl
0x18002bb5b  jz      short loc_18002BB80
0x18002bb5d  mov     ebp, [rbx+0Ch]
0x18002bb60  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18002bb67  test    rax, rax
0x18002bb6a  jz      short loc_18002BBB0
0x18002bb6c  mov     r8d, 100h
0x18002bb72  lea     rdx, [rsp+278h+Buffer]
0x18002bb77  mov     ecx, ebp
0x18002bb79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb7e  jmp     short loc_18002BBB0
0x18002bb80  mov     ebp, [rbx+8]
0x18002bb83  mov     [rsp+278h+Arguments], r15; Arguments
0x18002bb88  mov     [rsp+278h+nSize], 100h; nSize
0x18002bb90  lea     rax, [rsp+278h+Buffer]
0x18002bb95  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18002bb9a  mov     r9d, 400h; dwLanguageId
0x18002bba0  mov     r8d, ebp; dwMessageId
0x18002bba3  xor     edx, edx; lpSource
0x18002bba5  mov     ecx, 1200h; dwFlags
0x18002bbaa  call    cs:__imp_FormatMessageW
0x18002bbb0  lea     rsi, [r14+rsi*2]
0x18002bbb4  mov     r9, [rbx+38h]; unsigned __int16 *
0x18002bbb8  mov     rax, [rbx+88h]
0x18002bbbf  mov     rcx, [rbx+80h]
0x18002bbc6  mov     rdx, rsi; unsigned __int16 *
0x18002bbc9  test    r9, r9
0x18002bbcc  jz      short loc_18002BBF0
0x18002bbce  mov     [rsp+278h+Arguments], rax
0x18002bbd3  mov     qword ptr [rsp+278h+nSize], rcx
0x18002bbd8  mov     eax, [rbx+40h]
0x18002bbdb  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18002bbdf  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18002bbe6  mov     rcx, r14; this
0x18002bbe9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002bbee  jmp     short loc_18002BC07
0x18002bbf0  mov     [rsp+278h+lpBuffer], rax
0x18002bbf5  mov     r9, rcx; unsigned __int16 *
0x18002bbf8  lea     r8, aHsP; "%hs!%p: "
0x18002bbff  mov     rcx, r14; this
0x18002bc02  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002bc07  mov     r14, rax
0x18002bc0a  mov     r9, [rbx+90h]; unsigned __int16 *
0x18002bc11  test    r9, r9
0x18002bc14  jz      short loc_18002BC2B
0x18002bc16  lea     r8, aCallerP; "(caller: %p) "
0x18002bc1d  mov     rdx, rsi; unsigned __int16 *
0x18002bc20  mov     rcx, rax; this
0x18002bc23  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002bc28  mov     r14, rax
0x18002bc2b  call    cs:__imp_GetCurrentThreadId
0x18002bc31  lea     rcx, [rsp+278h+Buffer]
0x18002bc36  mov     [rsp+278h+var_240], rcx
0x18002bc3b  mov     dword ptr [rsp+278h+Arguments], ebp
0x18002bc3f  mov     [rsp+278h+nSize], eax
0x18002bc43  mov     eax, [rbx+44h]
0x18002bc46  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18002bc4a  mov     r9, rdi; unsigned __int16 *
0x18002bc4d  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18002bc54  mov     rdx, rsi; unsigned __int16 *
0x18002bc57  mov     rcx, r14; this
0x18002bc5a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002bc5f  cmp     [rbx+18h], r15
0x18002bc63  jnz     short loc_18002BC75
0x18002bc65  cmp     [rbx+48h], r15
0x18002bc69  jnz     short loc_18002BC75
0x18002bc6b  cmp     [rbx+30h], r15
0x18002bc6f  jz      loc_18002BD05
0x18002bc75  lea     r8, asc_1800641F0; "    "
0x18002bc7c  mov     rdx, rsi; unsigned __int16 *
0x18002bc7f  mov     rcx, rax; this
0x18002bc82  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002bc87  mov     r9, [rbx+18h]; unsigned __int16 *
0x18002bc8b  test    r9, r9
0x18002bc8e  jz      short loc_18002BCA2
0x18002bc90  lea     r8, aMsgWs; "Msg:[%ws] "
0x18002bc97  mov     rdx, rsi; unsigned __int16 *
0x18002bc9a  mov     rcx, rax; this
0x18002bc9d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002bca2  mov     r9, [rbx+48h]; unsigned __int16 *
0x18002bca6  test    r9, r9
0x18002bca9  jz      short loc_18002BCBD
0x18002bcab  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18002bcb2  mov     rdx, rsi; unsigned __int16 *
0x18002bcb5  mov     rcx, rax; this
0x18002bcb8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002bcbd  mov     rcx, [rbx+28h]
0x18002bcc1  mov     r9, [rbx+30h]; unsigned __int16 *
0x18002bcc5  mov     rdx, rsi; unsigned __int16 *
0x18002bcc8  test    rcx, rcx
0x18002bccb  jz      short loc_18002BCE3
0x18002bccd  mov     [rsp+278h+lpBuffer], rcx
0x18002bcd2  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18002bcd9  mov     rcx, rax; this
0x18002bcdc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002bce1  jmp     short loc_18002BD05
0x18002bce3  mov     rcx, rax; this
0x18002bce6  test    r9, r9
0x18002bce9  jz      short loc_18002BCF9
0x18002bceb  lea     r8, aHs; "[%hs]\n"
0x18002bcf2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002bcf7  jmp     short loc_18002BD05
0x18002bcf9  lea     r8, asc_180064268; "\n"
0x18002bd00  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002bd05  xor     eax, eax
0x18002bd07  mov     rcx, [rsp+278h+var_38]
0x18002bd0f  xor     rcx, rsp; StackCookie
0x18002bd12  call    __security_check_cookie
0x18002bd17  mov     rbx, [rsp+278h+arg_18]
0x18002bd1f  add     rsp, 250h
0x18002bd26  pop     r15
0x18002bd28  pop     r14
0x18002bd2a  pop     rdi
0x18002bd2b  pop     rsi
0x18002bd2c  pop     rbp
0x18002bd2d  retn
```
