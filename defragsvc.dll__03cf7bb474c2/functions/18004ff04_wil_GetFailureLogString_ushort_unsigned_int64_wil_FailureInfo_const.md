# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18004ff04`
- end: `0x1800501ba`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18005088c`
- `0x18005fa60`

## callees

- `0x18004ff04`
- `0x180050b88`
- `0x180067b0a`
- `0x180067b30`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800500b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800500b7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180050036`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180050036`

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
          v8 = (const char *)&byte_180074999;
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
0x18004ff04  mov     [rsp+arg_18], rbx
0x18004ff09  push    rbp
0x18004ff0a  push    rsi
0x18004ff0b  push    rdi
0x18004ff0c  push    r14
0x18004ff0e  push    r15
0x18004ff10  sub     rsp, 250h
0x18004ff17  mov     rax, cs:__security_cookie
0x18004ff1e  xor     rax, rsp
0x18004ff21  mov     [rsp+278h+var_38], rax
0x18004ff29  xor     r15d, r15d
0x18004ff2c  mov     rbx, r8
0x18004ff2f  mov     rsi, rdx
0x18004ff32  mov     r14, rcx
0x18004ff35  test    rdx, rdx
0x18004ff38  jz      loc_180050191
0x18004ff3e  test    rcx, rcx
0x18004ff41  jz      loc_180050191
0x18004ff47  mov     rax, cs:g_pfnResultLoggingCallback
0x18004ff4e  mov     [rcx], r15w
0x18004ff52  test    rax, rax
0x18004ff55  jz      short loc_18004FF78
0x18004ff57  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18004ff5e  jz      short loc_18004FF78
0x18004ff60  mov     r8, rdx
0x18004ff63  mov     rdx, rcx
0x18004ff66  mov     rcx, rbx
0x18004ff69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ff6e  cmp     [r14], r15w
0x18004ff72  jnz     loc_180050191
0x18004ff78  mov     ecx, [rbx]
0x18004ff7a  mov     bpl, 8
0x18004ff7d  test    ecx, ecx
0x18004ff7f  jz      short loc_18004FFCA
0x18004ff81  sub     ecx, 1
0x18004ff84  jz      short loc_18004FFB2
0x18004ff86  sub     ecx, 1
0x18004ff89  jz      short loc_18004FFA2
0x18004ff8b  cmp     ecx, 1
0x18004ff8e  jz      short loc_18004FF99
0x18004ff90  lea     rdi, byte_180074999
0x18004ff97  jmp     short loc_18004FFD1
0x18004ff99  lea     rdi, aFailfast; "FailFast"
0x18004ffa0  jmp     short loc_18004FFD1
0x18004ffa2  lea     rax, aLoghr; "LogHr"
0x18004ffa9  lea     rdi, aLognt; "LogNt"
0x18004ffb0  jmp     short loc_18004FFC0
0x18004ffb2  lea     rax, aReturnhr; "ReturnHr"
0x18004ffb9  lea     rdi, aReturnnt; "ReturnNt"
0x18004ffc0  test    [rbx+4], bpl
0x18004ffc4  cmovz   rdi, rax
0x18004ffc8  jmp     short loc_18004FFD1
0x18004ffca  lea     rdi, aException; "Exception"
0x18004ffd1  xor     edx, edx; Val
0x18004ffd3  lea     rcx, [rsp+278h+Buffer]; void *
0x18004ffd8  mov     r8d, 200h; Size
0x18004ffde  call    memset_0
0x18004ffe3  test    [rbx+4], bpl
0x18004ffe7  jz      short loc_18005000C
0x18004ffe9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18004fff0  mov     ebp, [rbx+0Ch]
0x18004fff3  test    rax, rax
0x18004fff6  jz      short loc_18005003C
0x18004fff8  mov     r8d, 100h
0x18004fffe  lea     rdx, [rsp+278h+Buffer]
0x180050003  mov     ecx, ebp
0x180050005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005000a  jmp     short loc_18005003C
0x18005000c  mov     ebp, [rbx+8]
0x18005000f  lea     rax, [rsp+278h+Buffer]
0x180050014  mov     [rsp+278h+Arguments], r15; Arguments
0x180050019  mov     r8d, ebp; dwMessageId
0x18005001c  mov     [rsp+278h+nSize], 100h; nSize
0x180050024  mov     r9d, 400h; dwLanguageId
0x18005002a  xor     edx, edx; lpSource
0x18005002c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180050031  mov     ecx, 1200h; dwFlags
0x180050036  call    cs:__imp_FormatMessageW
0x18005003c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180050040  lea     rsi, [r14+rsi*2]
0x180050044  mov     rax, [rbx+88h]
0x18005004b  mov     rdx, rsi; unsigned __int16 *
0x18005004e  mov     rcx, [rbx+80h]
0x180050055  test    r9, r9
0x180050058  jz      short loc_18005007C
0x18005005a  mov     [rsp+278h+Arguments], rax
0x18005005f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180050066  mov     eax, [rbx+40h]
0x180050069  mov     qword ptr [rsp+278h+nSize], rcx
0x18005006e  mov     rcx, r14; this
0x180050071  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180050075  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005007a  jmp     short loc_180050093
0x18005007c  mov     r9, rcx; unsigned __int16 *
0x18005007f  mov     [rsp+278h+lpBuffer], rax
0x180050084  mov     rcx, r14; this
0x180050087  lea     r8, aHsP; "%hs!%p: "
0x18005008e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180050093  mov     r9, [rbx+90h]; unsigned __int16 *
0x18005009a  mov     r14, rax
0x18005009d  test    r9, r9
0x1800500a0  jz      short loc_1800500B7
0x1800500a2  lea     r8, aCallerP; "(caller: %p) "
0x1800500a9  mov     rdx, rsi; unsigned __int16 *
0x1800500ac  mov     rcx, rax; this
0x1800500af  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800500b4  mov     r14, rax
0x1800500b7  call    cs:__imp_GetCurrentThreadId
0x1800500bd  lea     rcx, [rsp+278h+Buffer]
0x1800500c2  mov     r9, rdi; unsigned __int16 *
0x1800500c5  mov     [rsp+278h+var_240], rcx
0x1800500ca  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800500d1  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800500d5  mov     rdx, rsi; unsigned __int16 *
0x1800500d8  mov     [rsp+278h+nSize], eax
0x1800500dc  mov     rcx, r14; this
0x1800500df  mov     eax, [rbx+44h]
0x1800500e2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800500e6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800500eb  cmp     [rbx+18h], r15
0x1800500ef  jnz     short loc_180050101
0x1800500f1  cmp     [rbx+48h], r15
0x1800500f5  jnz     short loc_180050101
0x1800500f7  cmp     [rbx+30h], r15
0x1800500fb  jz      loc_180050191
0x180050101  lea     r8, asc_180074A88; "    "
0x180050108  mov     rdx, rsi; unsigned __int16 *
0x18005010b  mov     rcx, rax; this
0x18005010e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180050113  mov     r9, [rbx+18h]; unsigned __int16 *
0x180050117  test    r9, r9
0x18005011a  jz      short loc_18005012E
0x18005011c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180050123  mov     rdx, rsi; unsigned __int16 *
0x180050126  mov     rcx, rax; this
0x180050129  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005012e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180050132  test    r9, r9
0x180050135  jz      short loc_180050149
0x180050137  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18005013e  mov     rdx, rsi; unsigned __int16 *
0x180050141  mov     rcx, rax; this
0x180050144  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180050149  mov     rcx, [rbx+28h]
0x18005014d  mov     rdx, rsi; unsigned __int16 *
0x180050150  mov     r9, [rbx+30h]; unsigned __int16 *
0x180050154  test    rcx, rcx
0x180050157  jz      short loc_18005016F
0x180050159  mov     [rsp+278h+lpBuffer], rcx
0x18005015e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180050165  mov     rcx, rax; this
0x180050168  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005016d  jmp     short loc_180050191
0x18005016f  mov     rcx, rax; this
0x180050172  test    r9, r9
0x180050175  jz      short loc_180050185
0x180050177  lea     r8, aHs; "[%hs]\n"
0x18005017e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180050183  jmp     short loc_180050191
0x180050185  lea     r8, asc_180074B00; "\n"
0x18005018c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180050191  xor     eax, eax
0x180050193  mov     rcx, [rsp+278h+var_38]
0x18005019b  xor     rcx, rsp; StackCookie
0x18005019e  call    __security_check_cookie
0x1800501a3  mov     rbx, [rsp+278h+arg_18]
0x1800501ab  add     rsp, 250h
0x1800501b2  pop     r15
0x1800501b4  pop     r14
0x1800501b6  pop     rdi
0x1800501b7  pop     rsi
0x1800501b8  pop     rbp
0x1800501b9  retn
```
