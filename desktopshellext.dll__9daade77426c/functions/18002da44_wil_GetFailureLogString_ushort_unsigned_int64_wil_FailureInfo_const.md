# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18002da44`
- end: `0x18002dcfa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180011668`
- `0x18002e174`
- `0x18002ee30`

## callees

- `0x18002a3d0`
- `0x18002af50`
- `0x18002da44`
- `0x18002dfd4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002dbf7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002dbf7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002db76`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002db76`

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
          v7 = (const char *)&word_180091822;
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
0x18002da44  mov     [rsp+arg_18], rbx
0x18002da49  push    rbp
0x18002da4a  push    rsi
0x18002da4b  push    rdi
0x18002da4c  push    r14
0x18002da4e  push    r15
0x18002da50  sub     rsp, 250h
0x18002da57  mov     rax, cs:__security_cookie
0x18002da5e  xor     rax, rsp
0x18002da61  mov     [rsp+278h+var_38], rax
0x18002da69  mov     rbx, r8
0x18002da6c  mov     rsi, rdx
0x18002da6f  mov     r14, rcx
0x18002da72  xor     r15d, r15d
0x18002da75  test    rdx, rdx
0x18002da78  jz      loc_18002DCD1
0x18002da7e  test    rcx, rcx
0x18002da81  jz      loc_18002DCD1
0x18002da87  mov     [rcx], r15w
0x18002da8b  mov     rax, cs:g_pfnResultLoggingCallback
0x18002da92  test    rax, rax
0x18002da95  jz      short loc_18002DAB8
0x18002da97  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002da9e  jz      short loc_18002DAB8
0x18002daa0  mov     r8, rdx
0x18002daa3  mov     rdx, rcx
0x18002daa6  mov     rcx, rbx
0x18002daa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002daae  cmp     [r14], r15w
0x18002dab2  jnz     loc_18002DCD1
0x18002dab8  mov     ecx, [rbx]
0x18002daba  mov     bpl, 8
0x18002dabd  test    ecx, ecx
0x18002dabf  jz      short loc_18002DB0A
0x18002dac1  sub     ecx, 1
0x18002dac4  jz      short loc_18002DAF2
0x18002dac6  sub     ecx, 1
0x18002dac9  jz      short loc_18002DAE2
0x18002dacb  cmp     ecx, 1
0x18002dace  jz      short loc_18002DAD9
0x18002dad0  lea     rdi, word_180091822
0x18002dad7  jmp     short loc_18002DB11
0x18002dad9  lea     rdi, aFailfast; "FailFast"
0x18002dae0  jmp     short loc_18002DB11
0x18002dae2  lea     rax, aLoghr; "LogHr"
0x18002dae9  lea     rdi, aLognt; "LogNt"
0x18002daf0  jmp     short loc_18002DB00
0x18002daf2  lea     rax, aReturnhr; "ReturnHr"
0x18002daf9  lea     rdi, aReturnnt; "ReturnNt"
0x18002db00  test    [rbx+4], bpl
0x18002db04  cmovz   rdi, rax
0x18002db08  jmp     short loc_18002DB11
0x18002db0a  lea     rdi, aException; "Exception"
0x18002db11  xor     edx, edx; Val
0x18002db13  mov     r8d, 200h; Size
0x18002db19  lea     rcx, [rsp+278h+Buffer]; void *
0x18002db1e  call    memset_0
0x18002db23  test    [rbx+4], bpl
0x18002db27  jz      short loc_18002DB4C
0x18002db29  mov     ebp, [rbx+0Ch]
0x18002db2c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18002db33  test    rax, rax
0x18002db36  jz      short loc_18002DB7C
0x18002db38  mov     r8d, 100h
0x18002db3e  lea     rdx, [rsp+278h+Buffer]
0x18002db43  mov     ecx, ebp
0x18002db45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db4a  jmp     short loc_18002DB7C
0x18002db4c  mov     ebp, [rbx+8]
0x18002db4f  mov     [rsp+278h+Arguments], r15; Arguments
0x18002db54  mov     [rsp+278h+nSize], 100h; nSize
0x18002db5c  lea     rax, [rsp+278h+Buffer]
0x18002db61  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18002db66  mov     r9d, 400h; dwLanguageId
0x18002db6c  mov     r8d, ebp; dwMessageId
0x18002db6f  xor     edx, edx; lpSource
0x18002db71  mov     ecx, 1200h; dwFlags
0x18002db76  call    cs:__imp_FormatMessageW
0x18002db7c  lea     rsi, [r14+rsi*2]
0x18002db80  mov     r9, [rbx+38h]; unsigned __int16 *
0x18002db84  mov     rax, [rbx+88h]
0x18002db8b  mov     rcx, [rbx+80h]
0x18002db92  mov     rdx, rsi; unsigned __int16 *
0x18002db95  test    r9, r9
0x18002db98  jz      short loc_18002DBBC
0x18002db9a  mov     [rsp+278h+Arguments], rax
0x18002db9f  mov     qword ptr [rsp+278h+nSize], rcx
0x18002dba4  mov     eax, [rbx+40h]
0x18002dba7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18002dbab  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18002dbb2  mov     rcx, r14; this
0x18002dbb5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002dbba  jmp     short loc_18002DBD3
0x18002dbbc  mov     [rsp+278h+lpBuffer], rax
0x18002dbc1  mov     r9, rcx; unsigned __int16 *
0x18002dbc4  lea     r8, aHsP; "%hs!%p: "
0x18002dbcb  mov     rcx, r14; this
0x18002dbce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002dbd3  mov     r14, rax
0x18002dbd6  mov     r9, [rbx+90h]; unsigned __int16 *
0x18002dbdd  test    r9, r9
0x18002dbe0  jz      short loc_18002DBF7
0x18002dbe2  lea     r8, aCallerP; "(caller: %p) "
0x18002dbe9  mov     rdx, rsi; unsigned __int16 *
0x18002dbec  mov     rcx, rax; this
0x18002dbef  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002dbf4  mov     r14, rax
0x18002dbf7  call    cs:__imp_GetCurrentThreadId
0x18002dbfd  lea     rcx, [rsp+278h+Buffer]
0x18002dc02  mov     [rsp+278h+var_240], rcx
0x18002dc07  mov     dword ptr [rsp+278h+Arguments], ebp
0x18002dc0b  mov     [rsp+278h+nSize], eax
0x18002dc0f  mov     eax, [rbx+44h]
0x18002dc12  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18002dc16  mov     r9, rdi; unsigned __int16 *
0x18002dc19  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18002dc20  mov     rdx, rsi; unsigned __int16 *
0x18002dc23  mov     rcx, r14; this
0x18002dc26  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002dc2b  cmp     [rbx+18h], r15
0x18002dc2f  jnz     short loc_18002DC41
0x18002dc31  cmp     [rbx+48h], r15
0x18002dc35  jnz     short loc_18002DC41
0x18002dc37  cmp     [rbx+30h], r15
0x18002dc3b  jz      loc_18002DCD1
0x18002dc41  lea     r8, asc_180091910; "    "
0x18002dc48  mov     rdx, rsi; unsigned __int16 *
0x18002dc4b  mov     rcx, rax; this
0x18002dc4e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002dc53  mov     r9, [rbx+18h]; unsigned __int16 *
0x18002dc57  test    r9, r9
0x18002dc5a  jz      short loc_18002DC6E
0x18002dc5c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18002dc63  mov     rdx, rsi; unsigned __int16 *
0x18002dc66  mov     rcx, rax; this
0x18002dc69  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002dc6e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18002dc72  test    r9, r9
0x18002dc75  jz      short loc_18002DC89
0x18002dc77  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18002dc7e  mov     rdx, rsi; unsigned __int16 *
0x18002dc81  mov     rcx, rax; this
0x18002dc84  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002dc89  mov     rcx, [rbx+28h]
0x18002dc8d  mov     r9, [rbx+30h]; unsigned __int16 *
0x18002dc91  mov     rdx, rsi; unsigned __int16 *
0x18002dc94  test    rcx, rcx
0x18002dc97  jz      short loc_18002DCAF
0x18002dc99  mov     [rsp+278h+lpBuffer], rcx
0x18002dc9e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18002dca5  mov     rcx, rax; this
0x18002dca8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002dcad  jmp     short loc_18002DCD1
0x18002dcaf  mov     rcx, rax; this
0x18002dcb2  test    r9, r9
0x18002dcb5  jz      short loc_18002DCC5
0x18002dcb7  lea     r8, aHs; "[%hs]\n"
0x18002dcbe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002dcc3  jmp     short loc_18002DCD1
0x18002dcc5  lea     r8, asc_180091988; "\n"
0x18002dccc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002dcd1  xor     eax, eax
0x18002dcd3  mov     rcx, [rsp+278h+var_38]
0x18002dcdb  xor     rcx, rsp; StackCookie
0x18002dcde  call    __security_check_cookie
0x18002dce3  mov     rbx, [rsp+278h+arg_18]
0x18002dceb  add     rsp, 250h
0x18002dcf2  pop     r15
0x18002dcf4  pop     r14
0x18002dcf6  pop     rdi
0x18002dcf7  pop     rsi
0x18002dcf8  pop     rbp
0x18002dcf9  retn
```
