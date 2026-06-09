# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005814`
- end: `0x180005aca`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800040f8`
- `0x1800061c8`

## callees

- `0x180005814`
- `0x1800064c8`
- `0x180009922`
- `0x180009950`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800059c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800059c7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005946`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005946`

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
          v8 = (const char *)&byte_18000C950;
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
0x180005814  mov     [rsp+arg_18], rbx
0x180005819  push    rbp
0x18000581a  push    rsi
0x18000581b  push    rdi
0x18000581c  push    r14
0x18000581e  push    r15
0x180005820  sub     rsp, 250h
0x180005827  mov     rax, cs:__security_cookie
0x18000582e  xor     rax, rsp
0x180005831  mov     [rsp+278h+var_38], rax
0x180005839  xor     r15d, r15d
0x18000583c  mov     rbx, r8
0x18000583f  mov     rsi, rdx
0x180005842  mov     r14, rcx
0x180005845  test    rdx, rdx
0x180005848  jz      loc_180005AA1
0x18000584e  test    rcx, rcx
0x180005851  jz      loc_180005AA1
0x180005857  mov     rax, cs:g_pfnResultLoggingCallback
0x18000585e  mov     [rcx], r15w
0x180005862  test    rax, rax
0x180005865  jz      short loc_180005888
0x180005867  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000586e  jz      short loc_180005888
0x180005870  mov     r8, rdx
0x180005873  mov     rdx, rcx
0x180005876  mov     rcx, rbx
0x180005879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000587e  cmp     [r14], r15w
0x180005882  jnz     loc_180005AA1
0x180005888  mov     ecx, [rbx]
0x18000588a  mov     bpl, 8
0x18000588d  test    ecx, ecx
0x18000588f  jz      short loc_1800058DA
0x180005891  sub     ecx, 1
0x180005894  jz      short loc_1800058C2
0x180005896  sub     ecx, 1
0x180005899  jz      short loc_1800058B2
0x18000589b  cmp     ecx, 1
0x18000589e  jz      short loc_1800058A9
0x1800058a0  lea     rdi, byte_18000C950
0x1800058a7  jmp     short loc_1800058E1
0x1800058a9  lea     rdi, aFailfast; "FailFast"
0x1800058b0  jmp     short loc_1800058E1
0x1800058b2  lea     rax, aLoghr; "LogHr"
0x1800058b9  lea     rdi, aLognt; "LogNt"
0x1800058c0  jmp     short loc_1800058D0
0x1800058c2  lea     rax, aReturnhr; "ReturnHr"
0x1800058c9  lea     rdi, aReturnnt; "ReturnNt"
0x1800058d0  test    [rbx+4], bpl
0x1800058d4  cmovz   rdi, rax
0x1800058d8  jmp     short loc_1800058E1
0x1800058da  lea     rdi, aException; "Exception"
0x1800058e1  xor     edx, edx; Val
0x1800058e3  lea     rcx, [rsp+278h+Buffer]; void *
0x1800058e8  mov     r8d, 200h; Size
0x1800058ee  call    memset_0
0x1800058f3  test    [rbx+4], bpl
0x1800058f7  jz      short loc_18000591C
0x1800058f9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005900  mov     ebp, [rbx+0Ch]
0x180005903  test    rax, rax
0x180005906  jz      short loc_18000594C
0x180005908  mov     r8d, 100h
0x18000590e  lea     rdx, [rsp+278h+Buffer]
0x180005913  mov     ecx, ebp
0x180005915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000591a  jmp     short loc_18000594C
0x18000591c  mov     ebp, [rbx+8]
0x18000591f  lea     rax, [rsp+278h+Buffer]
0x180005924  mov     [rsp+278h+Arguments], r15; Arguments
0x180005929  mov     r8d, ebp; dwMessageId
0x18000592c  mov     [rsp+278h+nSize], 100h; nSize
0x180005934  mov     r9d, 400h; dwLanguageId
0x18000593a  xor     edx, edx; lpSource
0x18000593c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005941  mov     ecx, 1200h; dwFlags
0x180005946  call    cs:__imp_FormatMessageW
0x18000594c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005950  lea     rsi, [r14+rsi*2]
0x180005954  mov     rax, [rbx+88h]
0x18000595b  mov     rdx, rsi; unsigned __int16 *
0x18000595e  mov     rcx, [rbx+80h]
0x180005965  test    r9, r9
0x180005968  jz      short loc_18000598C
0x18000596a  mov     [rsp+278h+Arguments], rax
0x18000596f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005976  mov     eax, [rbx+40h]
0x180005979  mov     qword ptr [rsp+278h+nSize], rcx
0x18000597e  mov     rcx, r14; this
0x180005981  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005985  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000598a  jmp     short loc_1800059A3
0x18000598c  mov     r9, rcx; unsigned __int16 *
0x18000598f  mov     [rsp+278h+lpBuffer], rax
0x180005994  mov     rcx, r14; this
0x180005997  lea     r8, aHsP; "%hs!%p: "
0x18000599e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800059a3  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800059aa  mov     r14, rax
0x1800059ad  test    r9, r9
0x1800059b0  jz      short loc_1800059C7
0x1800059b2  lea     r8, aCallerP; "(caller: %p) "
0x1800059b9  mov     rdx, rsi; unsigned __int16 *
0x1800059bc  mov     rcx, rax; this
0x1800059bf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800059c4  mov     r14, rax
0x1800059c7  call    cs:__imp_GetCurrentThreadId
0x1800059cd  lea     rcx, [rsp+278h+Buffer]
0x1800059d2  mov     r9, rdi; unsigned __int16 *
0x1800059d5  mov     [rsp+278h+var_240], rcx
0x1800059da  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800059e1  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800059e5  mov     rdx, rsi; unsigned __int16 *
0x1800059e8  mov     [rsp+278h+nSize], eax
0x1800059ec  mov     rcx, r14; this
0x1800059ef  mov     eax, [rbx+44h]
0x1800059f2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800059f6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800059fb  cmp     [rbx+18h], r15
0x1800059ff  jnz     short loc_180005A11
0x180005a01  cmp     [rbx+48h], r15
0x180005a05  jnz     short loc_180005A11
0x180005a07  cmp     [rbx+30h], r15
0x180005a0b  jz      loc_180005AA1
0x180005a11  lea     r8, asc_18000C5F8; "    "
0x180005a18  mov     rdx, rsi; unsigned __int16 *
0x180005a1b  mov     rcx, rax; this
0x180005a1e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005a23  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005a27  test    r9, r9
0x180005a2a  jz      short loc_180005A3E
0x180005a2c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005a33  mov     rdx, rsi; unsigned __int16 *
0x180005a36  mov     rcx, rax; this
0x180005a39  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005a3e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005a42  test    r9, r9
0x180005a45  jz      short loc_180005A59
0x180005a47  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180005a4e  mov     rdx, rsi; unsigned __int16 *
0x180005a51  mov     rcx, rax; this
0x180005a54  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005a59  mov     rcx, [rbx+28h]
0x180005a5d  mov     rdx, rsi; unsigned __int16 *
0x180005a60  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005a64  test    rcx, rcx
0x180005a67  jz      short loc_180005A7F
0x180005a69  mov     [rsp+278h+lpBuffer], rcx
0x180005a6e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005a75  mov     rcx, rax; this
0x180005a78  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005a7d  jmp     short loc_180005AA1
0x180005a7f  mov     rcx, rax; this
0x180005a82  test    r9, r9
0x180005a85  jz      short loc_180005A95
0x180005a87  lea     r8, aHs; "[%hs]\n"
0x180005a8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005a93  jmp     short loc_180005AA1
0x180005a95  lea     r8, asc_18000C670; "\n"
0x180005a9c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005aa1  xor     eax, eax
0x180005aa3  mov     rcx, [rsp+278h+var_38]
0x180005aab  xor     rcx, rsp; StackCookie
0x180005aae  call    __security_check_cookie
0x180005ab3  mov     rbx, [rsp+278h+arg_18]
0x180005abb  add     rsp, 250h
0x180005ac2  pop     r15
0x180005ac4  pop     r14
0x180005ac6  pop     rdi
0x180005ac7  pop     rsi
0x180005ac8  pop     rbp
0x180005ac9  retn
```
