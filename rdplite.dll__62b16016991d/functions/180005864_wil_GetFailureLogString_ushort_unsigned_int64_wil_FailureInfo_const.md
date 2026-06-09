# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005864`
- end: `0x180005b1a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180006168`
- `0x1800065e4`
- `0x180007770`

## callees

- `0x1800036f0`
- `0x180004154`
- `0x180005864`
- `0x180006464`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a17`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005996`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005996`

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
          v7 = (const char *)&qword_18002D6C0;
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
0x180005864  mov     [rsp+arg_18], rbx
0x180005869  push    rbp
0x18000586a  push    rsi
0x18000586b  push    rdi
0x18000586c  push    r14
0x18000586e  push    r15
0x180005870  sub     rsp, 250h
0x180005877  mov     rax, cs:__security_cookie
0x18000587e  xor     rax, rsp
0x180005881  mov     [rsp+278h+var_38], rax
0x180005889  mov     rbx, r8
0x18000588c  mov     rsi, rdx
0x18000588f  mov     r14, rcx
0x180005892  xor     r15d, r15d
0x180005895  test    rdx, rdx
0x180005898  jz      loc_180005AF1
0x18000589e  test    rcx, rcx
0x1800058a1  jz      loc_180005AF1
0x1800058a7  mov     [rcx], r15w
0x1800058ab  mov     rax, cs:g_pfnResultLoggingCallback
0x1800058b2  test    rax, rax
0x1800058b5  jz      short loc_1800058D8
0x1800058b7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800058be  jz      short loc_1800058D8
0x1800058c0  mov     r8, rdx
0x1800058c3  mov     rdx, rcx
0x1800058c6  mov     rcx, rbx
0x1800058c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058ce  cmp     [r14], r15w
0x1800058d2  jnz     loc_180005AF1
0x1800058d8  mov     ecx, [rbx]
0x1800058da  mov     bpl, 8
0x1800058dd  test    ecx, ecx
0x1800058df  jz      short loc_18000592A
0x1800058e1  sub     ecx, 1
0x1800058e4  jz      short loc_180005912
0x1800058e6  sub     ecx, 1
0x1800058e9  jz      short loc_180005902
0x1800058eb  cmp     ecx, 1
0x1800058ee  jz      short loc_1800058F9
0x1800058f0  lea     rdi, qword_18002D6C0
0x1800058f7  jmp     short loc_180005931
0x1800058f9  lea     rdi, aFailfast; "FailFast"
0x180005900  jmp     short loc_180005931
0x180005902  lea     rax, aLoghr; "LogHr"
0x180005909  lea     rdi, aLognt; "LogNt"
0x180005910  jmp     short loc_180005920
0x180005912  lea     rax, aReturnhr; "ReturnHr"
0x180005919  lea     rdi, aReturnnt; "ReturnNt"
0x180005920  test    [rbx+4], bpl
0x180005924  cmovz   rdi, rax
0x180005928  jmp     short loc_180005931
0x18000592a  lea     rdi, aException; "Exception"
0x180005931  xor     edx, edx; Val
0x180005933  mov     r8d, 200h; Size
0x180005939  lea     rcx, [rsp+278h+Buffer]; void *
0x18000593e  call    memset_0
0x180005943  test    [rbx+4], bpl
0x180005947  jz      short loc_18000596C
0x180005949  mov     ebp, [rbx+0Ch]
0x18000594c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005953  test    rax, rax
0x180005956  jz      short loc_18000599C
0x180005958  mov     r8d, 100h
0x18000595e  lea     rdx, [rsp+278h+Buffer]
0x180005963  mov     ecx, ebp
0x180005965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000596a  jmp     short loc_18000599C
0x18000596c  mov     ebp, [rbx+8]
0x18000596f  mov     [rsp+278h+Arguments], r15; Arguments
0x180005974  mov     [rsp+278h+nSize], 100h; nSize
0x18000597c  lea     rax, [rsp+278h+Buffer]
0x180005981  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005986  mov     r9d, 400h; dwLanguageId
0x18000598c  mov     r8d, ebp; dwMessageId
0x18000598f  xor     edx, edx; lpSource
0x180005991  mov     ecx, 1200h; dwFlags
0x180005996  call    cs:__imp_FormatMessageW
0x18000599c  lea     rsi, [r14+rsi*2]
0x1800059a0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800059a4  mov     rax, [rbx+88h]
0x1800059ab  mov     rcx, [rbx+80h]
0x1800059b2  mov     rdx, rsi; unsigned __int16 *
0x1800059b5  test    r9, r9
0x1800059b8  jz      short loc_1800059DC
0x1800059ba  mov     [rsp+278h+Arguments], rax
0x1800059bf  mov     qword ptr [rsp+278h+nSize], rcx
0x1800059c4  mov     eax, [rbx+40h]
0x1800059c7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800059cb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800059d2  mov     rcx, r14; this
0x1800059d5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800059da  jmp     short loc_1800059F3
0x1800059dc  mov     [rsp+278h+lpBuffer], rax
0x1800059e1  mov     r9, rcx; unsigned __int16 *
0x1800059e4  lea     r8, aHsP; "%hs!%p: "
0x1800059eb  mov     rcx, r14; this
0x1800059ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800059f3  mov     r14, rax
0x1800059f6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800059fd  test    r9, r9
0x180005a00  jz      short loc_180005A17
0x180005a02  lea     r8, aCallerP; "(caller: %p) "
0x180005a09  mov     rdx, rsi; unsigned __int16 *
0x180005a0c  mov     rcx, rax; this
0x180005a0f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005a14  mov     r14, rax
0x180005a17  call    cs:__imp_GetCurrentThreadId
0x180005a1d  lea     rcx, [rsp+278h+Buffer]
0x180005a22  mov     [rsp+278h+var_240], rcx
0x180005a27  mov     dword ptr [rsp+278h+Arguments], ebp
0x180005a2b  mov     [rsp+278h+nSize], eax
0x180005a2f  mov     eax, [rbx+44h]
0x180005a32  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005a36  mov     r9, rdi; unsigned __int16 *
0x180005a39  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005a40  mov     rdx, rsi; unsigned __int16 *
0x180005a43  mov     rcx, r14; this
0x180005a46  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005a4b  cmp     [rbx+18h], r15
0x180005a4f  jnz     short loc_180005A61
0x180005a51  cmp     [rbx+48h], r15
0x180005a55  jnz     short loc_180005A61
0x180005a57  cmp     [rbx+30h], r15
0x180005a5b  jz      loc_180005AF1
0x180005a61  lea     r8, asc_18002D7E0; "    "
0x180005a68  mov     rdx, rsi; unsigned __int16 *
0x180005a6b  mov     rcx, rax; this
0x180005a6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005a73  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005a77  test    r9, r9
0x180005a7a  jz      short loc_180005A8E
0x180005a7c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005a83  mov     rdx, rsi; unsigned __int16 *
0x180005a86  mov     rcx, rax; this
0x180005a89  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005a8e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005a92  test    r9, r9
0x180005a95  jz      short loc_180005AA9
0x180005a97  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180005a9e  mov     rdx, rsi; unsigned __int16 *
0x180005aa1  mov     rcx, rax; this
0x180005aa4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005aa9  mov     rcx, [rbx+28h]
0x180005aad  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005ab1  mov     rdx, rsi; unsigned __int16 *
0x180005ab4  test    rcx, rcx
0x180005ab7  jz      short loc_180005ACF
0x180005ab9  mov     [rsp+278h+lpBuffer], rcx
0x180005abe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005ac5  mov     rcx, rax; this
0x180005ac8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005acd  jmp     short loc_180005AF1
0x180005acf  mov     rcx, rax; this
0x180005ad2  test    r9, r9
0x180005ad5  jz      short loc_180005AE5
0x180005ad7  lea     r8, aHs; "[%hs]\n"
0x180005ade  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005ae3  jmp     short loc_180005AF1
0x180005ae5  lea     r8, asc_18002D858; "\n"
0x180005aec  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005af1  xor     eax, eax
0x180005af3  mov     rcx, [rsp+278h+var_38]
0x180005afb  xor     rcx, rsp; StackCookie
0x180005afe  call    __security_check_cookie
0x180005b03  mov     rbx, [rsp+278h+arg_18]
0x180005b0b  add     rsp, 250h
0x180005b12  pop     r15
0x180005b14  pop     r14
0x180005b16  pop     rdi
0x180005b17  pop     rsi
0x180005b18  pop     rbp
0x180005b19  retn
```
