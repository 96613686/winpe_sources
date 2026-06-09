# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x14000ab34`
- end: `0x14000adea`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14000b9b4`
- `0x14000eeb0`

## callees

- `0x140002070`
- `0x140002c68`
- `0x14000ab34`
- `0x14000bc94`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000ace7`
- `KERNEL32!GetCurrentThreadId` at `0x14000ace7`
- `KERNEL32!FormatMessageW` at `0x14000ac66`
- `KERNEL32!FormatMessageW` at `0x14000ac66`

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
          v7 = (const char *)&dword_140069964;
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
0x14000ab34  mov     [rsp+arg_18], rbx
0x14000ab39  push    rbp
0x14000ab3a  push    rsi
0x14000ab3b  push    rdi
0x14000ab3c  push    r14
0x14000ab3e  push    r15
0x14000ab40  sub     rsp, 250h
0x14000ab47  mov     rax, cs:__security_cookie
0x14000ab4e  xor     rax, rsp
0x14000ab51  mov     [rsp+278h+var_38], rax
0x14000ab59  mov     rbx, r8
0x14000ab5c  mov     rsi, rdx
0x14000ab5f  mov     r14, rcx
0x14000ab62  xor     r15d, r15d
0x14000ab65  test    rdx, rdx
0x14000ab68  jz      loc_14000ADC1
0x14000ab6e  test    rcx, rcx
0x14000ab71  jz      loc_14000ADC1
0x14000ab77  mov     [rcx], r15w
0x14000ab7b  mov     rax, cs:g_pfnResultLoggingCallback
0x14000ab82  test    rax, rax
0x14000ab85  jz      short loc_14000ABA8
0x14000ab87  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000ab8e  jz      short loc_14000ABA8
0x14000ab90  mov     r8, rdx
0x14000ab93  mov     rdx, rcx
0x14000ab96  mov     rcx, rbx
0x14000ab99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ab9e  cmp     [r14], r15w
0x14000aba2  jnz     loc_14000ADC1
0x14000aba8  mov     ecx, [rbx]
0x14000abaa  mov     bpl, 8
0x14000abad  test    ecx, ecx
0x14000abaf  jz      short loc_14000ABFA
0x14000abb1  sub     ecx, 1
0x14000abb4  jz      short loc_14000ABE2
0x14000abb6  sub     ecx, 1
0x14000abb9  jz      short loc_14000ABD2
0x14000abbb  cmp     ecx, 1
0x14000abbe  jz      short loc_14000ABC9
0x14000abc0  lea     rdi, dword_140069964
0x14000abc7  jmp     short loc_14000AC01
0x14000abc9  lea     rdi, aFailfast; "FailFast"
0x14000abd0  jmp     short loc_14000AC01
0x14000abd2  lea     rax, aLoghr; "LogHr"
0x14000abd9  lea     rdi, aLognt; "LogNt"
0x14000abe0  jmp     short loc_14000ABF0
0x14000abe2  lea     rax, aReturnhr; "ReturnHr"
0x14000abe9  lea     rdi, aReturnnt; "ReturnNt"
0x14000abf0  test    [rbx+4], bpl
0x14000abf4  cmovz   rdi, rax
0x14000abf8  jmp     short loc_14000AC01
0x14000abfa  lea     rdi, aException; "Exception"
0x14000ac01  xor     edx, edx; Val
0x14000ac03  mov     r8d, 200h; Size
0x14000ac09  lea     rcx, [rsp+278h+Buffer]; void *
0x14000ac0e  call    memset_0
0x14000ac13  test    [rbx+4], bpl
0x14000ac17  jz      short loc_14000AC3C
0x14000ac19  mov     ebp, [rbx+0Ch]
0x14000ac1c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x14000ac23  test    rax, rax
0x14000ac26  jz      short loc_14000AC6C
0x14000ac28  mov     r8d, 100h
0x14000ac2e  lea     rdx, [rsp+278h+Buffer]
0x14000ac33  mov     ecx, ebp
0x14000ac35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ac3a  jmp     short loc_14000AC6C
0x14000ac3c  mov     ebp, [rbx+8]
0x14000ac3f  mov     [rsp+278h+Arguments], r15; Arguments
0x14000ac44  mov     [rsp+278h+nSize], 100h; nSize
0x14000ac4c  lea     rax, [rsp+278h+Buffer]
0x14000ac51  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x14000ac56  mov     r9d, 400h; dwLanguageId
0x14000ac5c  mov     r8d, ebp; dwMessageId
0x14000ac5f  xor     edx, edx; lpSource
0x14000ac61  mov     ecx, 1200h; dwFlags
0x14000ac66  call    cs:__imp_FormatMessageW
0x14000ac6c  lea     rsi, [r14+rsi*2]
0x14000ac70  mov     r9, [rbx+38h]; wchar_t *
0x14000ac74  mov     rax, [rbx+88h]
0x14000ac7b  mov     rcx, [rbx+80h]
0x14000ac82  mov     rdx, rsi; wchar_t *
0x14000ac85  test    r9, r9
0x14000ac88  jz      short loc_14000ACAC
0x14000ac8a  mov     [rsp+278h+Arguments], rax
0x14000ac8f  mov     qword ptr [rsp+278h+nSize], rcx
0x14000ac94  mov     eax, [rbx+40h]
0x14000ac97  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000ac9b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x14000aca2  mov     rcx, r14; this
0x14000aca5  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14000acaa  jmp     short loc_14000ACC3
0x14000acac  mov     [rsp+278h+lpBuffer], rax
0x14000acb1  mov     r9, rcx; wchar_t *
0x14000acb4  lea     r8, aHsP; "%hs!%p: "
0x14000acbb  mov     rcx, r14; this
0x14000acbe  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14000acc3  mov     r14, rax
0x14000acc6  mov     r9, [rbx+90h]; wchar_t *
0x14000accd  test    r9, r9
0x14000acd0  jz      short loc_14000ACE7
0x14000acd2  lea     r8, aCallerP; "(caller: %p) "
0x14000acd9  mov     rdx, rsi; wchar_t *
0x14000acdc  mov     rcx, rax; this
0x14000acdf  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14000ace4  mov     r14, rax
0x14000ace7  call    cs:__imp_GetCurrentThreadId
0x14000aced  lea     rcx, [rsp+278h+Buffer]
0x14000acf2  mov     [rsp+278h+var_240], rcx
0x14000acf7  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000acfb  mov     [rsp+278h+nSize], eax
0x14000acff  mov     eax, [rbx+44h]
0x14000ad02  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000ad06  mov     r9, rdi; wchar_t *
0x14000ad09  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x14000ad10  mov     rdx, rsi; wchar_t *
0x14000ad13  mov     rcx, r14; this
0x14000ad16  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14000ad1b  cmp     [rbx+18h], r15
0x14000ad1f  jnz     short loc_14000AD31
0x14000ad21  cmp     [rbx+48h], r15
0x14000ad25  jnz     short loc_14000AD31
0x14000ad27  cmp     [rbx+30h], r15
0x14000ad2b  jz      loc_14000ADC1
0x14000ad31  lea     r8, asc_140069A50; "    "
0x14000ad38  mov     rdx, rsi; wchar_t *
0x14000ad3b  mov     rcx, rax; this
0x14000ad3e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14000ad43  mov     r9, [rbx+18h]; wchar_t *
0x14000ad47  test    r9, r9
0x14000ad4a  jz      short loc_14000AD5E
0x14000ad4c  lea     r8, aMsgWs; "Msg:[%ws] "
0x14000ad53  mov     rdx, rsi; wchar_t *
0x14000ad56  mov     rcx, rax; this
0x14000ad59  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14000ad5e  mov     r9, [rbx+48h]; wchar_t *
0x14000ad62  test    r9, r9
0x14000ad65  jz      short loc_14000AD79
0x14000ad67  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000ad6e  mov     rdx, rsi; wchar_t *
0x14000ad71  mov     rcx, rax; this
0x14000ad74  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14000ad79  mov     rcx, [rbx+28h]
0x14000ad7d  mov     r9, [rbx+30h]; wchar_t *
0x14000ad81  mov     rdx, rsi; wchar_t *
0x14000ad84  test    rcx, rcx
0x14000ad87  jz      short loc_14000AD9F
0x14000ad89  mov     [rsp+278h+lpBuffer], rcx
0x14000ad8e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x14000ad95  mov     rcx, rax; this
0x14000ad98  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14000ad9d  jmp     short loc_14000ADC1
0x14000ad9f  mov     rcx, rax; this
0x14000ada2  test    r9, r9
0x14000ada5  jz      short loc_14000ADB5
0x14000ada7  lea     r8, aHs; "[%hs]\n"
0x14000adae  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14000adb3  jmp     short loc_14000ADC1
0x14000adb5  lea     r8, asc_140069960; "\n"
0x14000adbc  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14000adc1  xor     eax, eax
0x14000adc3  mov     rcx, [rsp+278h+var_38]
0x14000adcb  xor     rcx, rsp; StackCookie
0x14000adce  call    __security_check_cookie
0x14000add3  mov     rbx, [rsp+278h+arg_18]
0x14000addb  add     rsp, 250h
0x14000ade2  pop     r15
0x14000ade4  pop     r14
0x14000ade6  pop     rdi
0x14000ade7  pop     rsi
0x14000ade8  pop     rbp
0x14000ade9  retn
```
