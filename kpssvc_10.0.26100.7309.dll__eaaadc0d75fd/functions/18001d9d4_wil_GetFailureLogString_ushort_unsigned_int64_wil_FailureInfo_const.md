# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18001d9d4`
- end: `0x18001dc95`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18001b800`
- `0x18001ba78`
- `0x180022e50`

## callees

- `0x18001d9d4`
- `0x180023160`
- `0x18003100e`
- `0x180031040`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001db8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001db8b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001db04`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001db04`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rsi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rdi
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
  v8 = (const char *)&qword_180034D88;
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
        goto LABEL_17;
      }
      v9 = "LogHr";
      v8 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v8 = v9;
    goto LABEL_17;
  }
  v8 = "Exception";
LABEL_17:
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
0x18001d9d4  mov     [rsp+arg_18], rbx
0x18001d9d9  push    rbp
0x18001d9da  push    rsi
0x18001d9db  push    rdi
0x18001d9dc  push    r14
0x18001d9de  push    r15
0x18001d9e0  sub     rsp, 250h
0x18001d9e7  mov     rax, cs:__security_cookie
0x18001d9ee  xor     rax, rsp
0x18001d9f1  mov     [rsp+278h+var_38], rax
0x18001d9f9  xor     r15d, r15d
0x18001d9fc  mov     rbx, r8
0x18001d9ff  mov     rdi, rdx
0x18001da02  mov     r14, rcx
0x18001da05  test    rdx, rdx
0x18001da08  jz      loc_18001DC6B
0x18001da0e  test    rcx, rcx
0x18001da11  jz      loc_18001DC6B
0x18001da17  mov     rax, cs:g_pfnResultLoggingCallback
0x18001da1e  mov     [rcx], r15w
0x18001da22  test    rax, rax
0x18001da25  jz      short loc_18001DA48
0x18001da27  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001da2e  jz      short loc_18001DA48
0x18001da30  mov     r8, rdx
0x18001da33  mov     rdx, rcx
0x18001da36  mov     rcx, rbx
0x18001da39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da3e  cmp     [r14], r15w
0x18001da42  jnz     loc_18001DC6B
0x18001da48  mov     ecx, [rbx]
0x18001da4a  lea     rsi, qword_180034D88
0x18001da51  mov     bpl, 8
0x18001da54  test    ecx, ecx
0x18001da56  jz      short loc_18001DA98
0x18001da58  sub     ecx, 1
0x18001da5b  jz      short loc_18001DA80
0x18001da5d  sub     ecx, 1
0x18001da60  jz      short loc_18001DA70
0x18001da62  cmp     ecx, 1
0x18001da65  jnz     short loc_18001DA9F
0x18001da67  lea     rsi, aFailfast; "FailFast"
0x18001da6e  jmp     short loc_18001DA9F
0x18001da70  lea     rax, aLoghr; "LogHr"
0x18001da77  lea     rsi, aLognt; "LogNt"
0x18001da7e  jmp     short loc_18001DA8E
0x18001da80  lea     rax, aReturnhr; "ReturnHr"
0x18001da87  lea     rsi, aReturnnt; "ReturnNt"
0x18001da8e  test    [rbx+4], bpl
0x18001da92  cmovz   rsi, rax
0x18001da96  jmp     short loc_18001DA9F
0x18001da98  lea     rsi, aException; "Exception"
0x18001da9f  xor     edx, edx; Val
0x18001daa1  lea     rcx, [rsp+278h+Buffer]; void *
0x18001daa6  mov     r8d, 200h; Size
0x18001daac  call    memset_0
0x18001dab1  test    [rbx+4], bpl
0x18001dab5  jz      short loc_18001DADA
0x18001dab7  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18001dabe  mov     ebp, [rbx+0Ch]
0x18001dac1  test    rax, rax
0x18001dac4  jz      short loc_18001DB10
0x18001dac6  mov     r8d, 100h
0x18001dacc  lea     rdx, [rsp+278h+Buffer]
0x18001dad1  mov     ecx, ebp
0x18001dad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dad8  jmp     short loc_18001DB10
0x18001dada  mov     ebp, [rbx+8]
0x18001dadd  lea     rax, [rsp+278h+Buffer]
0x18001dae2  mov     [rsp+278h+Arguments], r15; Arguments
0x18001dae7  mov     r8d, ebp; dwMessageId
0x18001daea  mov     [rsp+278h+nSize], 100h; nSize
0x18001daf2  mov     r9d, 400h; dwLanguageId
0x18001daf8  xor     edx, edx; lpSource
0x18001dafa  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18001daff  mov     ecx, 1200h; dwFlags
0x18001db04  call    cs:__imp_FormatMessageW
0x18001db0b  nop     dword ptr [rax+rax+00h]
0x18001db10  mov     r9, [rbx+38h]; unsigned __int16 *
0x18001db14  lea     rdi, [r14+rdi*2]
0x18001db18  mov     rax, [rbx+88h]
0x18001db1f  mov     rdx, rdi; unsigned __int16 *
0x18001db22  mov     rcx, [rbx+80h]
0x18001db29  test    r9, r9
0x18001db2c  jz      short loc_18001DB50
0x18001db2e  mov     [rsp+278h+Arguments], rax
0x18001db33  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18001db3a  mov     eax, [rbx+40h]
0x18001db3d  mov     qword ptr [rsp+278h+nSize], rcx
0x18001db42  mov     rcx, r14; this
0x18001db45  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001db49  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001db4e  jmp     short loc_18001DB67
0x18001db50  mov     r9, rcx; unsigned __int16 *
0x18001db53  mov     [rsp+278h+lpBuffer], rax
0x18001db58  mov     rcx, r14; this
0x18001db5b  lea     r8, aHsP; "%hs!%p: "
0x18001db62  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001db67  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001db6e  mov     r14, rax
0x18001db71  test    r9, r9
0x18001db74  jz      short loc_18001DB8B
0x18001db76  lea     r8, aCallerP; "(caller: %p) "
0x18001db7d  mov     rdx, rdi; unsigned __int16 *
0x18001db80  mov     rcx, rax; this
0x18001db83  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001db88  mov     r14, rax
0x18001db8b  call    cs:__imp_GetCurrentThreadId
0x18001db92  nop     dword ptr [rax+rax+00h]
0x18001db97  mov     ecx, [rbx+44h]
0x18001db9a  lea     rdx, [rsp+278h+Buffer]
0x18001db9f  mov     [rsp+278h+var_240], rdx
0x18001dba4  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18001dbab  mov     dword ptr [rsp+278h+Arguments], ebp
0x18001dbaf  mov     r9, rsi; unsigned __int16 *
0x18001dbb2  mov     [rsp+278h+nSize], eax
0x18001dbb6  mov     rdx, rdi; unsigned __int16 *
0x18001dbb9  mov     dword ptr [rsp+278h+lpBuffer], ecx
0x18001dbbd  mov     rcx, r14; this
0x18001dbc0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001dbc5  cmp     [rbx+18h], r15
0x18001dbc9  jnz     short loc_18001DBDB
0x18001dbcb  cmp     [rbx+48h], r15
0x18001dbcf  jnz     short loc_18001DBDB
0x18001dbd1  cmp     [rbx+30h], r15
0x18001dbd5  jz      loc_18001DC6B
0x18001dbdb  lea     r8, asc_180034E78; "    "
0x18001dbe2  mov     rdx, rdi; unsigned __int16 *
0x18001dbe5  mov     rcx, rax; this
0x18001dbe8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001dbed  mov     r9, [rbx+18h]; unsigned __int16 *
0x18001dbf1  test    r9, r9
0x18001dbf4  jz      short loc_18001DC08
0x18001dbf6  lea     r8, aMsgWs; "Msg:[%ws] "
0x18001dbfd  mov     rdx, rdi; unsigned __int16 *
0x18001dc00  mov     rcx, rax; this
0x18001dc03  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001dc08  mov     r9, [rbx+48h]; unsigned __int16 *
0x18001dc0c  test    r9, r9
0x18001dc0f  jz      short loc_18001DC23
0x18001dc11  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001dc18  mov     rdx, rdi; unsigned __int16 *
0x18001dc1b  mov     rcx, rax; this
0x18001dc1e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001dc23  mov     rcx, [rbx+28h]
0x18001dc27  mov     rdx, rdi; unsigned __int16 *
0x18001dc2a  mov     r9, [rbx+30h]; unsigned __int16 *
0x18001dc2e  test    rcx, rcx
0x18001dc31  jz      short loc_18001DC49
0x18001dc33  mov     [rsp+278h+lpBuffer], rcx
0x18001dc38  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18001dc3f  mov     rcx, rax; this
0x18001dc42  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001dc47  jmp     short loc_18001DC6B
0x18001dc49  mov     rcx, rax; this
0x18001dc4c  test    r9, r9
0x18001dc4f  jz      short loc_18001DC5F
0x18001dc51  lea     r8, aHs; "[%hs]\n"
0x18001dc58  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001dc5d  jmp     short loc_18001DC6B
0x18001dc5f  lea     r8, asc_180034EF0; "\n"
0x18001dc66  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001dc6b  xor     eax, eax
0x18001dc6d  mov     rcx, [rsp+278h+var_38]
0x18001dc75  xor     rcx, rsp; StackCookie
0x18001dc78  call    __security_check_cookie
0x18001dc7d  mov     rbx, [rsp+278h+arg_18]
0x18001dc85  add     rsp, 250h
0x18001dc8c  pop     r15
0x18001dc8e  pop     r14
0x18001dc90  pop     rdi
0x18001dc91  pop     rsi
0x18001dc92  pop     rbp
0x18001dc93  retn
```
