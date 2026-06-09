# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800288e4`
- end: `0x180028b9a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18001aaac`
- `0x180028d34`
- `0x1800296f0`

## callees

- `0x18001d8e0`
- `0x18001e368`
- `0x1800288e4`
- `0x180028ccc`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028a97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028a97`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180028a16`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180028a16`

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
          v7 = (const char *)&qword_1800422E0;
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
0x1800288e4  mov     [rsp+arg_18], rbx
0x1800288e9  push    rbp
0x1800288ea  push    rsi
0x1800288eb  push    rdi
0x1800288ec  push    r14
0x1800288ee  push    r15
0x1800288f0  sub     rsp, 250h
0x1800288f7  mov     rax, cs:__security_cookie
0x1800288fe  xor     rax, rsp
0x180028901  mov     [rsp+278h+var_38], rax
0x180028909  mov     rbx, r8
0x18002890c  mov     rsi, rdx
0x18002890f  mov     r14, rcx
0x180028912  xor     r15d, r15d
0x180028915  test    rdx, rdx
0x180028918  jz      loc_180028B71
0x18002891e  test    rcx, rcx
0x180028921  jz      loc_180028B71
0x180028927  mov     [rcx], r15w
0x18002892b  mov     rax, cs:g_pfnResultLoggingCallback
0x180028932  test    rax, rax
0x180028935  jz      short loc_180028958
0x180028937  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002893e  jz      short loc_180028958
0x180028940  mov     r8, rdx
0x180028943  mov     rdx, rcx
0x180028946  mov     rcx, rbx
0x180028949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002894e  cmp     [r14], r15w
0x180028952  jnz     loc_180028B71
0x180028958  mov     ecx, [rbx]
0x18002895a  mov     bpl, 8
0x18002895d  test    ecx, ecx
0x18002895f  jz      short loc_1800289AA
0x180028961  sub     ecx, 1
0x180028964  jz      short loc_180028992
0x180028966  sub     ecx, 1
0x180028969  jz      short loc_180028982
0x18002896b  cmp     ecx, 1
0x18002896e  jz      short loc_180028979
0x180028970  lea     rdi, qword_1800422E0
0x180028977  jmp     short loc_1800289B1
0x180028979  lea     rdi, aFailfast; "FailFast"
0x180028980  jmp     short loc_1800289B1
0x180028982  lea     rax, aLoghr; "LogHr"
0x180028989  lea     rdi, aLognt; "LogNt"
0x180028990  jmp     short loc_1800289A0
0x180028992  lea     rax, aReturnhr; "ReturnHr"
0x180028999  lea     rdi, aReturnnt; "ReturnNt"
0x1800289a0  test    [rbx+4], bpl
0x1800289a4  cmovz   rdi, rax
0x1800289a8  jmp     short loc_1800289B1
0x1800289aa  lea     rdi, aException; "Exception"
0x1800289b1  xor     edx, edx; Val
0x1800289b3  mov     r8d, 200h; Size
0x1800289b9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800289be  call    memset_0
0x1800289c3  test    [rbx+4], bpl
0x1800289c7  jz      short loc_1800289EC
0x1800289c9  mov     ebp, [rbx+0Ch]
0x1800289cc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800289d3  test    rax, rax
0x1800289d6  jz      short loc_180028A1C
0x1800289d8  mov     r8d, 100h
0x1800289de  lea     rdx, [rsp+278h+Buffer]
0x1800289e3  mov     ecx, ebp
0x1800289e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289ea  jmp     short loc_180028A1C
0x1800289ec  mov     ebp, [rbx+8]
0x1800289ef  mov     [rsp+278h+Arguments], r15; Arguments
0x1800289f4  mov     [rsp+278h+nSize], 100h; nSize
0x1800289fc  lea     rax, [rsp+278h+Buffer]
0x180028a01  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180028a06  mov     r9d, 400h; dwLanguageId
0x180028a0c  mov     r8d, ebp; dwMessageId
0x180028a0f  xor     edx, edx; lpSource
0x180028a11  mov     ecx, 1200h; dwFlags
0x180028a16  call    cs:__imp_FormatMessageW
0x180028a1c  lea     rsi, [r14+rsi*2]
0x180028a20  mov     r9, [rbx+38h]; unsigned __int16 *
0x180028a24  mov     rax, [rbx+88h]
0x180028a2b  mov     rcx, [rbx+80h]
0x180028a32  mov     rdx, rsi; unsigned __int16 *
0x180028a35  test    r9, r9
0x180028a38  jz      short loc_180028A5C
0x180028a3a  mov     [rsp+278h+Arguments], rax
0x180028a3f  mov     qword ptr [rsp+278h+nSize], rcx
0x180028a44  mov     eax, [rbx+40h]
0x180028a47  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180028a4b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180028a52  mov     rcx, r14; this
0x180028a55  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180028a5a  jmp     short loc_180028A73
0x180028a5c  mov     [rsp+278h+lpBuffer], rax
0x180028a61  mov     r9, rcx; unsigned __int16 *
0x180028a64  lea     r8, aHsP; "%hs!%p: "
0x180028a6b  mov     rcx, r14; this
0x180028a6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180028a73  mov     r14, rax
0x180028a76  mov     r9, [rbx+90h]; unsigned __int16 *
0x180028a7d  test    r9, r9
0x180028a80  jz      short loc_180028A97
0x180028a82  lea     r8, aCallerP; "(caller: %p) "
0x180028a89  mov     rdx, rsi; unsigned __int16 *
0x180028a8c  mov     rcx, rax; this
0x180028a8f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180028a94  mov     r14, rax
0x180028a97  call    cs:__imp_GetCurrentThreadId
0x180028a9d  lea     rcx, [rsp+278h+Buffer]
0x180028aa2  mov     [rsp+278h+var_240], rcx
0x180028aa7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180028aab  mov     [rsp+278h+nSize], eax
0x180028aaf  mov     eax, [rbx+44h]
0x180028ab2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180028ab6  mov     r9, rdi; unsigned __int16 *
0x180028ab9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180028ac0  mov     rdx, rsi; unsigned __int16 *
0x180028ac3  mov     rcx, r14; this
0x180028ac6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180028acb  cmp     [rbx+18h], r15
0x180028acf  jnz     short loc_180028AE1
0x180028ad1  cmp     [rbx+48h], r15
0x180028ad5  jnz     short loc_180028AE1
0x180028ad7  cmp     [rbx+30h], r15
0x180028adb  jz      loc_180028B71
0x180028ae1  lea     r8, asc_1800423E8; "    "
0x180028ae8  mov     rdx, rsi; unsigned __int16 *
0x180028aeb  mov     rcx, rax; this
0x180028aee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180028af3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180028af7  test    r9, r9
0x180028afa  jz      short loc_180028B0E
0x180028afc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180028b03  mov     rdx, rsi; unsigned __int16 *
0x180028b06  mov     rcx, rax; this
0x180028b09  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180028b0e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180028b12  test    r9, r9
0x180028b15  jz      short loc_180028B29
0x180028b17  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180028b1e  mov     rdx, rsi; unsigned __int16 *
0x180028b21  mov     rcx, rax; this
0x180028b24  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180028b29  mov     rcx, [rbx+28h]
0x180028b2d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180028b31  mov     rdx, rsi; unsigned __int16 *
0x180028b34  test    rcx, rcx
0x180028b37  jz      short loc_180028B4F
0x180028b39  mov     [rsp+278h+lpBuffer], rcx
0x180028b3e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180028b45  mov     rcx, rax; this
0x180028b48  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180028b4d  jmp     short loc_180028B71
0x180028b4f  mov     rcx, rax; this
0x180028b52  test    r9, r9
0x180028b55  jz      short loc_180028B65
0x180028b57  lea     r8, aHs; "[%hs]\n"
0x180028b5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180028b63  jmp     short loc_180028B71
0x180028b65  lea     r8, asc_180042460; "\n"
0x180028b6c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180028b71  xor     eax, eax
0x180028b73  mov     rcx, [rsp+278h+var_38]
0x180028b7b  xor     rcx, rsp; StackCookie
0x180028b7e  call    __security_check_cookie
0x180028b83  mov     rbx, [rsp+278h+arg_18]
0x180028b8b  add     rsp, 250h
0x180028b92  pop     r15
0x180028b94  pop     r14
0x180028b96  pop     rdi
0x180028b97  pop     rsi
0x180028b98  pop     rbp
0x180028b99  retn
```
