# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180007794`
- end: `0x180007a57`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180004638`
- `0x180008424`
- `0x1800088e4`
- `0x180009da0`

## callees

- `0x180002af0`
- `0x1800034cc`
- `0x180007794`
- `0x180008738`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800078c6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800078c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000794d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000794d`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rsi
  const wchar_t *v11; // r9
  __int64 v12; // rax
  const wchar_t *v13; // rcx
  wchar_t *v14; // rax
  wil::details *v15; // r14
  const wchar_t *v16; // r9
  wil::details *v17; // rax
  const wchar_t *v18; // r9
  wchar_t *v19; // rax
  const wchar_t *v20; // r9
  const wchar_t *v21; // r9
  const wchar_t *v22; // r9
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
          v7 = (const char *)&qword_18003CB78;
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
  v10 = (wchar_t *)((char *)this + 2 * (_QWORD)a2);
  v11 = *(const wchar_t **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const wchar_t **)(a3 + 128);
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
  v16 = *(const wchar_t **)(a3 + 144);
  if ( v16 )
    v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v15,
                          v10,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const wchar_t *)v7,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v10, L"    ", v18);
    v20 = *(const wchar_t **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const wchar_t **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const wchar_t **)(a3 + 48);
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
0x180007794  mov     [rsp+arg_18], rbx
0x180007799  push    rbp
0x18000779a  push    rsi
0x18000779b  push    rdi
0x18000779c  push    r14
0x18000779e  push    r15
0x1800077a0  sub     rsp, 250h
0x1800077a7  mov     rax, cs:__security_cookie
0x1800077ae  xor     rax, rsp
0x1800077b1  mov     [rsp+278h+var_38], rax
0x1800077b9  mov     rbx, r8
0x1800077bc  mov     rsi, rdx
0x1800077bf  mov     r14, rcx
0x1800077c2  xor     r15d, r15d
0x1800077c5  test    rdx, rdx
0x1800077c8  jz      loc_180007A2D
0x1800077ce  test    rcx, rcx
0x1800077d1  jz      loc_180007A2D
0x1800077d7  mov     [rcx], r15w
0x1800077db  mov     rax, cs:g_pfnResultLoggingCallback
0x1800077e2  test    rax, rax
0x1800077e5  jz      short loc_180007808
0x1800077e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800077ee  jz      short loc_180007808
0x1800077f0  mov     r8, rdx
0x1800077f3  mov     rdx, rcx
0x1800077f6  mov     rcx, rbx
0x1800077f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077fe  cmp     [r14], r15w
0x180007802  jnz     loc_180007A2D
0x180007808  mov     ecx, [rbx]
0x18000780a  mov     bpl, 8
0x18000780d  test    ecx, ecx
0x18000780f  jz      short loc_18000785A
0x180007811  sub     ecx, 1
0x180007814  jz      short loc_180007842
0x180007816  sub     ecx, 1
0x180007819  jz      short loc_180007832
0x18000781b  cmp     ecx, 1
0x18000781e  jz      short loc_180007829
0x180007820  lea     rdi, qword_18003CB78
0x180007827  jmp     short loc_180007861
0x180007829  lea     rdi, aFailfast; "FailFast"
0x180007830  jmp     short loc_180007861
0x180007832  lea     rax, aLoghr; "LogHr"
0x180007839  lea     rdi, aLognt; "LogNt"
0x180007840  jmp     short loc_180007850
0x180007842  lea     rax, aReturnhr; "ReturnHr"
0x180007849  lea     rdi, aReturnnt; "ReturnNt"
0x180007850  test    [rbx+4], bpl
0x180007854  cmovz   rdi, rax
0x180007858  jmp     short loc_180007861
0x18000785a  lea     rdi, aException; "Exception"
0x180007861  xor     edx, edx; Val
0x180007863  mov     r8d, 200h; Size
0x180007869  lea     rcx, [rsp+278h+Buffer]; void *
0x18000786e  call    memset_0
0x180007873  test    [rbx+4], bpl
0x180007877  jz      short loc_18000789C
0x180007879  mov     ebp, [rbx+0Ch]
0x18000787c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180007883  test    rax, rax
0x180007886  jz      short loc_1800078D2
0x180007888  mov     r8d, 100h
0x18000788e  lea     rdx, [rsp+278h+Buffer]
0x180007893  mov     ecx, ebp
0x180007895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000789a  jmp     short loc_1800078D2
0x18000789c  mov     ebp, [rbx+8]
0x18000789f  mov     [rsp+278h+Arguments], r15; Arguments
0x1800078a4  mov     [rsp+278h+nSize], 100h; nSize
0x1800078ac  lea     rax, [rsp+278h+Buffer]
0x1800078b1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800078b6  mov     r9d, 400h; dwLanguageId
0x1800078bc  mov     r8d, ebp; dwMessageId
0x1800078bf  xor     edx, edx; lpSource
0x1800078c1  mov     ecx, 1200h; dwFlags
0x1800078c6  call    cs:__imp_FormatMessageW
0x1800078cd  nop     dword ptr [rax+rax+00h]
0x1800078d2  lea     rsi, [r14+rsi*2]
0x1800078d6  mov     r9, [rbx+38h]; wchar_t *
0x1800078da  mov     rax, [rbx+88h]
0x1800078e1  mov     rcx, [rbx+80h]
0x1800078e8  mov     rdx, rsi; wchar_t *
0x1800078eb  test    r9, r9
0x1800078ee  jz      short loc_180007912
0x1800078f0  mov     [rsp+278h+Arguments], rax
0x1800078f5  mov     qword ptr [rsp+278h+nSize], rcx
0x1800078fa  mov     eax, [rbx+40h]
0x1800078fd  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007901  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180007908  mov     rcx, r14; this
0x18000790b  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007910  jmp     short loc_180007929
0x180007912  mov     [rsp+278h+lpBuffer], rax
0x180007917  mov     r9, rcx; wchar_t *
0x18000791a  lea     r8, aHsP; "%hs!%p: "
0x180007921  mov     rcx, r14; this
0x180007924  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007929  mov     r14, rax
0x18000792c  mov     r9, [rbx+90h]; wchar_t *
0x180007933  test    r9, r9
0x180007936  jz      short loc_18000794D
0x180007938  lea     r8, aCallerP; "(caller: %p) "
0x18000793f  mov     rdx, rsi; wchar_t *
0x180007942  mov     rcx, rax; this
0x180007945  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000794a  mov     r14, rax
0x18000794d  call    cs:__imp_GetCurrentThreadId
0x180007954  nop     dword ptr [rax+rax+00h]
0x180007959  lea     rcx, [rsp+278h+Buffer]
0x18000795e  mov     [rsp+278h+var_240], rcx
0x180007963  mov     dword ptr [rsp+278h+Arguments], ebp
0x180007967  mov     [rsp+278h+nSize], eax
0x18000796b  mov     eax, [rbx+44h]
0x18000796e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007972  mov     r9, rdi; wchar_t *
0x180007975  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000797c  mov     rdx, rsi; wchar_t *
0x18000797f  mov     rcx, r14; this
0x180007982  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007987  cmp     [rbx+18h], r15
0x18000798b  jnz     short loc_18000799D
0x18000798d  cmp     [rbx+48h], r15
0x180007991  jnz     short loc_18000799D
0x180007993  cmp     [rbx+30h], r15
0x180007997  jz      loc_180007A2D
0x18000799d  lea     r8, asc_18003CC68; "    "
0x1800079a4  mov     rdx, rsi; wchar_t *
0x1800079a7  mov     rcx, rax; this
0x1800079aa  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800079af  mov     r9, [rbx+18h]; wchar_t *
0x1800079b3  test    r9, r9
0x1800079b6  jz      short loc_1800079CA
0x1800079b8  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800079bf  mov     rdx, rsi; wchar_t *
0x1800079c2  mov     rcx, rax; this
0x1800079c5  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800079ca  mov     r9, [rbx+48h]; wchar_t *
0x1800079ce  test    r9, r9
0x1800079d1  jz      short loc_1800079E5
0x1800079d3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800079da  mov     rdx, rsi; wchar_t *
0x1800079dd  mov     rcx, rax; this
0x1800079e0  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800079e5  mov     rcx, [rbx+28h]
0x1800079e9  mov     r9, [rbx+30h]; wchar_t *
0x1800079ed  mov     rdx, rsi; wchar_t *
0x1800079f0  test    rcx, rcx
0x1800079f3  jz      short loc_180007A0B
0x1800079f5  mov     [rsp+278h+lpBuffer], rcx
0x1800079fa  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180007a01  mov     rcx, rax; this
0x180007a04  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007a09  jmp     short loc_180007A2D
0x180007a0b  mov     rcx, rax; this
0x180007a0e  test    r9, r9
0x180007a11  jz      short loc_180007A21
0x180007a13  lea     r8, aHs; "[%hs]\n"
0x180007a1a  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007a1f  jmp     short loc_180007A2D
0x180007a21  lea     r8, asc_18003CCE0; "\n"
0x180007a28  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007a2d  xor     eax, eax
0x180007a2f  mov     rcx, [rsp+278h+var_38]
0x180007a37  xor     rcx, rsp; StackCookie
0x180007a3a  call    __security_check_cookie
0x180007a3f  mov     rbx, [rsp+278h+arg_18]
0x180007a47  add     rsp, 250h
0x180007a4e  pop     r15
0x180007a50  pop     r14
0x180007a52  pop     rdi
0x180007a53  pop     rsi
0x180007a54  pop     rbp
0x180007a55  retn
```
