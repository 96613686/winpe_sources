# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18003ab7c`
- end: `0x18003ae32`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180027c4c`
- `0x18003af5c`
- `0x18003b6d0`

## callees

- `0x18002e5f0`
- `0x18002f2f4`
- `0x18003ab7c`
- `0x18003af0c`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ad2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ad2f`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003acae`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003acae`

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
          v7 = (const char *)&qword_18008ACA0;
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
0x18003ab7c  mov     [rsp+arg_18], rbx
0x18003ab81  push    rbp
0x18003ab82  push    rsi
0x18003ab83  push    rdi
0x18003ab84  push    r14
0x18003ab86  push    r15
0x18003ab88  sub     rsp, 250h
0x18003ab8f  mov     rax, cs:__security_cookie
0x18003ab96  xor     rax, rsp
0x18003ab99  mov     [rsp+278h+var_38], rax
0x18003aba1  mov     rbx, r8
0x18003aba4  mov     rsi, rdx
0x18003aba7  mov     r14, rcx
0x18003abaa  xor     r15d, r15d
0x18003abad  test    rdx, rdx
0x18003abb0  jz      loc_18003AE09
0x18003abb6  test    rcx, rcx
0x18003abb9  jz      loc_18003AE09
0x18003abbf  mov     [rcx], r15w
0x18003abc3  mov     rax, cs:g_pfnResultLoggingCallback
0x18003abca  test    rax, rax
0x18003abcd  jz      short loc_18003ABF0
0x18003abcf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003abd6  jz      short loc_18003ABF0
0x18003abd8  mov     r8, rdx
0x18003abdb  mov     rdx, rcx
0x18003abde  mov     rcx, rbx
0x18003abe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003abe6  cmp     [r14], r15w
0x18003abea  jnz     loc_18003AE09
0x18003abf0  mov     ecx, [rbx]
0x18003abf2  mov     bpl, 8
0x18003abf5  test    ecx, ecx
0x18003abf7  jz      short loc_18003AC42
0x18003abf9  sub     ecx, 1
0x18003abfc  jz      short loc_18003AC2A
0x18003abfe  sub     ecx, 1
0x18003ac01  jz      short loc_18003AC1A
0x18003ac03  cmp     ecx, 1
0x18003ac06  jz      short loc_18003AC11
0x18003ac08  lea     rdi, qword_18008ACA0
0x18003ac0f  jmp     short loc_18003AC49
0x18003ac11  lea     rdi, aFailfast; "FailFast"
0x18003ac18  jmp     short loc_18003AC49
0x18003ac1a  lea     rax, aLoghr; "LogHr"
0x18003ac21  lea     rdi, aLognt; "LogNt"
0x18003ac28  jmp     short loc_18003AC38
0x18003ac2a  lea     rax, aReturnhr; "ReturnHr"
0x18003ac31  lea     rdi, aReturnnt; "ReturnNt"
0x18003ac38  test    [rbx+4], bpl
0x18003ac3c  cmovz   rdi, rax
0x18003ac40  jmp     short loc_18003AC49
0x18003ac42  lea     rdi, aException; "Exception"
0x18003ac49  xor     edx, edx; Val
0x18003ac4b  mov     r8d, 200h; Size
0x18003ac51  lea     rcx, [rsp+278h+Buffer]; void *
0x18003ac56  call    memset_0
0x18003ac5b  test    [rbx+4], bpl
0x18003ac5f  jz      short loc_18003AC84
0x18003ac61  mov     ebp, [rbx+0Ch]
0x18003ac64  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18003ac6b  test    rax, rax
0x18003ac6e  jz      short loc_18003ACB4
0x18003ac70  mov     r8d, 100h
0x18003ac76  lea     rdx, [rsp+278h+Buffer]
0x18003ac7b  mov     ecx, ebp
0x18003ac7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac82  jmp     short loc_18003ACB4
0x18003ac84  mov     ebp, [rbx+8]
0x18003ac87  mov     [rsp+278h+Arguments], r15; Arguments
0x18003ac8c  mov     [rsp+278h+nSize], 100h; nSize
0x18003ac94  lea     rax, [rsp+278h+Buffer]
0x18003ac99  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18003ac9e  mov     r9d, 400h; dwLanguageId
0x18003aca4  mov     r8d, ebp; dwMessageId
0x18003aca7  xor     edx, edx; lpSource
0x18003aca9  mov     ecx, 1200h; dwFlags
0x18003acae  call    cs:__imp_FormatMessageW
0x18003acb4  lea     rsi, [r14+rsi*2]
0x18003acb8  mov     r9, [rbx+38h]; unsigned __int16 *
0x18003acbc  mov     rax, [rbx+88h]
0x18003acc3  mov     rcx, [rbx+80h]
0x18003acca  mov     rdx, rsi; unsigned __int16 *
0x18003accd  test    r9, r9
0x18003acd0  jz      short loc_18003ACF4
0x18003acd2  mov     [rsp+278h+Arguments], rax
0x18003acd7  mov     qword ptr [rsp+278h+nSize], rcx
0x18003acdc  mov     eax, [rbx+40h]
0x18003acdf  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18003ace3  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18003acea  mov     rcx, r14; this
0x18003aced  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003acf2  jmp     short loc_18003AD0B
0x18003acf4  mov     [rsp+278h+lpBuffer], rax
0x18003acf9  mov     r9, rcx; unsigned __int16 *
0x18003acfc  lea     r8, aHsP; "%hs!%p: "
0x18003ad03  mov     rcx, r14; this
0x18003ad06  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003ad0b  mov     r14, rax
0x18003ad0e  mov     r9, [rbx+90h]; unsigned __int16 *
0x18003ad15  test    r9, r9
0x18003ad18  jz      short loc_18003AD2F
0x18003ad1a  lea     r8, aCallerP; "(caller: %p) "
0x18003ad21  mov     rdx, rsi; unsigned __int16 *
0x18003ad24  mov     rcx, rax; this
0x18003ad27  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003ad2c  mov     r14, rax
0x18003ad2f  call    cs:__imp_GetCurrentThreadId
0x18003ad35  lea     rcx, [rsp+278h+Buffer]
0x18003ad3a  mov     [rsp+278h+var_240], rcx
0x18003ad3f  mov     dword ptr [rsp+278h+Arguments], ebp
0x18003ad43  mov     [rsp+278h+nSize], eax
0x18003ad47  mov     eax, [rbx+44h]
0x18003ad4a  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18003ad4e  mov     r9, rdi; unsigned __int16 *
0x18003ad51  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18003ad58  mov     rdx, rsi; unsigned __int16 *
0x18003ad5b  mov     rcx, r14; this
0x18003ad5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003ad63  cmp     [rbx+18h], r15
0x18003ad67  jnz     short loc_18003AD79
0x18003ad69  cmp     [rbx+48h], r15
0x18003ad6d  jnz     short loc_18003AD79
0x18003ad6f  cmp     [rbx+30h], r15
0x18003ad73  jz      loc_18003AE09
0x18003ad79  lea     r8, asc_18008ADA8; "    "
0x18003ad80  mov     rdx, rsi; unsigned __int16 *
0x18003ad83  mov     rcx, rax; this
0x18003ad86  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003ad8b  mov     r9, [rbx+18h]; unsigned __int16 *
0x18003ad8f  test    r9, r9
0x18003ad92  jz      short loc_18003ADA6
0x18003ad94  lea     r8, aMsgWs; "Msg:[%ws] "
0x18003ad9b  mov     rdx, rsi; unsigned __int16 *
0x18003ad9e  mov     rcx, rax; this
0x18003ada1  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003ada6  mov     r9, [rbx+48h]; unsigned __int16 *
0x18003adaa  test    r9, r9
0x18003adad  jz      short loc_18003ADC1
0x18003adaf  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18003adb6  mov     rdx, rsi; unsigned __int16 *
0x18003adb9  mov     rcx, rax; this
0x18003adbc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003adc1  mov     rcx, [rbx+28h]
0x18003adc5  mov     r9, [rbx+30h]; unsigned __int16 *
0x18003adc9  mov     rdx, rsi; unsigned __int16 *
0x18003adcc  test    rcx, rcx
0x18003adcf  jz      short loc_18003ADE7
0x18003add1  mov     [rsp+278h+lpBuffer], rcx
0x18003add6  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18003addd  mov     rcx, rax; this
0x18003ade0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003ade5  jmp     short loc_18003AE09
0x18003ade7  mov     rcx, rax; this
0x18003adea  test    r9, r9
0x18003aded  jz      short loc_18003ADFD
0x18003adef  lea     r8, aHs; "[%hs]\n"
0x18003adf6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003adfb  jmp     short loc_18003AE09
0x18003adfd  lea     r8, asc_18008AE20; "\n"
0x18003ae04  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003ae09  xor     eax, eax
0x18003ae0b  mov     rcx, [rsp+278h+var_38]
0x18003ae13  xor     rcx, rsp; StackCookie
0x18003ae16  call    __security_check_cookie
0x18003ae1b  mov     rbx, [rsp+278h+arg_18]
0x18003ae23  add     rsp, 250h
0x18003ae2a  pop     r15
0x18003ae2c  pop     r14
0x18003ae2e  pop     rdi
0x18003ae2f  pop     rsi
0x18003ae30  pop     rbp
0x18003ae31  retn
```
