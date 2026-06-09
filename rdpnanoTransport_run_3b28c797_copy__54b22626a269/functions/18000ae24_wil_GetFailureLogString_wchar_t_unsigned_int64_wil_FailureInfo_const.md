# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000ae24`
- end: `0x18000b0e0`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `700`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `6`
- tags: ``

## callers

- `0x180008d10`
- `0x180009600`
- `0x180009880`
- `0x180009b38`
- `0x18000d408`
- `0x180376e5c`
- `0x180376f9f`

## callees

- `0x18000ae24`
- `0x18000b8c8`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`
- `0x180376380`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000afdd`
- `KERNEL32!GetCurrentThreadId` at `0x18000afdd`
- `KERNEL32!FormatMessageW` at `0x18000af5c`
- `KERNEL32!FormatMessageW` at `0x18000af5c`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v7; // rsi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rdi
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
      g_pfnResultLoggingCallback(a3, this, a2, a4);
      if ( *(_WORD *)this )
        return 0;
    }
  }
  v7 = (const char *)&Str1;
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
        goto LABEL_17;
      }
      v8 = "LogHr";
      v7 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v7 = v8;
    goto LABEL_17;
  }
  v7 = "Exception";
LABEL_17:
  memset(Buffer, 0, sizeof(Buffer));
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
0x18000ae24  mov     [rsp+arg_18], rbx
0x18000ae29  push    rbp
0x18000ae2a  push    rsi
0x18000ae2b  push    rdi
0x18000ae2c  push    r14
0x18000ae2e  push    r15
0x18000ae30  mov     eax, 250h
0x18000ae35  call    _alloca_probe
0x18000ae3a  sub     rsp, rax
0x18000ae3d  mov     rax, cs:__security_cookie
0x18000ae44  xor     rax, rsp
0x18000ae47  mov     [rsp+278h+var_38], rax
0x18000ae4f  mov     rbx, r8
0x18000ae52  mov     rdi, rdx
0x18000ae55  mov     r14, rcx
0x18000ae58  xor     r15d, r15d
0x18000ae5b  test    rdx, rdx
0x18000ae5e  jz      loc_18000B0B7
0x18000ae64  test    rcx, rcx
0x18000ae67  jz      loc_18000B0B7
0x18000ae6d  mov     [rcx], r15w
0x18000ae71  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ae78  test    rax, rax
0x18000ae7b  jz      short loc_18000AE9F
0x18000ae7d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000ae84  jz      short loc_18000AE9F
0x18000ae86  mov     r8, rdx
0x18000ae89  mov     rdx, rcx
0x18000ae8c  mov     rcx, rbx
0x18000ae8f  call    cs:__guard_dispatch_icall_fptr
0x18000ae95  cmp     [r14], r15w
0x18000ae99  jnz     loc_18000B0B7
0x18000ae9f  lea     rsi, Str1
0x18000aea6  mov     ecx, [rbx]
0x18000aea8  mov     bpl, 8
0x18000aeab  test    ecx, ecx
0x18000aead  jz      short loc_18000AEEF
0x18000aeaf  sub     ecx, 1
0x18000aeb2  jz      short loc_18000AED7
0x18000aeb4  sub     ecx, 1
0x18000aeb7  jz      short loc_18000AEC7
0x18000aeb9  cmp     ecx, 1
0x18000aebc  jnz     short loc_18000AEF6
0x18000aebe  lea     rsi, aFailfast; "FailFast"
0x18000aec5  jmp     short loc_18000AEF6
0x18000aec7  lea     rax, aLoghr; "LogHr"
0x18000aece  lea     rsi, aLognt; "LogNt"
0x18000aed5  jmp     short loc_18000AEE5
0x18000aed7  lea     rax, aReturnhr; "ReturnHr"
0x18000aede  lea     rsi, aReturnnt; "ReturnNt"
0x18000aee5  test    [rbx+4], bpl
0x18000aee9  cmovz   rsi, rax
0x18000aeed  jmp     short loc_18000AEF6
0x18000aeef  lea     rsi, aException_0; "Exception"
0x18000aef6  xor     edx, edx; Val
0x18000aef8  mov     r8d, 200h; Size
0x18000aefe  lea     rcx, [rsp+278h+Buffer]; void *
0x18000af03  call    memset
0x18000af08  test    [rbx+4], bpl
0x18000af0c  jz      short loc_18000AF32
0x18000af0e  mov     ebp, [rbx+0Ch]
0x18000af11  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x18000af18  test    rax, rax
0x18000af1b  jz      short loc_18000AF62
0x18000af1d  mov     r8d, 100h
0x18000af23  lea     rdx, [rsp+278h+Buffer]
0x18000af28  mov     ecx, ebp
0x18000af2a  call    cs:__guard_dispatch_icall_fptr
0x18000af30  jmp     short loc_18000AF62
0x18000af32  mov     ebp, [rbx+8]
0x18000af35  mov     [rsp+278h+Arguments], r15; Arguments
0x18000af3a  mov     [rsp+278h+nSize], 100h; nSize
0x18000af42  lea     rax, [rsp+278h+Buffer]
0x18000af47  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000af4c  mov     r9d, 400h; dwLanguageId
0x18000af52  mov     r8d, ebp; dwMessageId
0x18000af55  xor     edx, edx; lpSource
0x18000af57  mov     ecx, 1200h; dwFlags
0x18000af5c  call    cs:__imp_FormatMessageW
0x18000af62  lea     rdi, [r14+rdi*2]
0x18000af66  mov     r9, [rbx+38h]; wchar_t *
0x18000af6a  mov     rax, [rbx+88h]
0x18000af71  mov     rcx, [rbx+80h]
0x18000af78  mov     rdx, rdi; wchar_t *
0x18000af7b  test    r9, r9
0x18000af7e  jz      short loc_18000AFA2
0x18000af80  mov     [rsp+278h+Arguments], rax
0x18000af85  mov     qword ptr [rsp+278h+nSize], rcx
0x18000af8a  mov     eax, [rbx+40h]
0x18000af8d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000af91  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000af98  mov     rcx, r14; this
0x18000af9b  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000afa0  jmp     short loc_18000AFB9
0x18000afa2  mov     [rsp+278h+lpBuffer], rax
0x18000afa7  mov     r9, rcx; wchar_t *
0x18000afaa  lea     r8, aHsP; "%hs!%p: "
0x18000afb1  mov     rcx, r14; this
0x18000afb4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000afb9  mov     r14, rax
0x18000afbc  mov     r9, [rbx+90h]; wchar_t *
0x18000afc3  test    r9, r9
0x18000afc6  jz      short loc_18000AFDD
0x18000afc8  lea     r8, aCallerP; "(caller: %p) "
0x18000afcf  mov     rdx, rdi; wchar_t *
0x18000afd2  mov     rcx, rax; this
0x18000afd5  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000afda  mov     r14, rax
0x18000afdd  call    cs:__imp_GetCurrentThreadId
0x18000afe3  lea     rcx, [rsp+278h+Buffer]
0x18000afe8  mov     [rsp+278h+var_240], rcx
0x18000afed  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000aff1  mov     [rsp+278h+nSize], eax
0x18000aff5  mov     eax, [rbx+44h]
0x18000aff8  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000affc  mov     r9, rsi; wchar_t *
0x18000afff  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000b006  mov     rdx, rdi; wchar_t *
0x18000b009  mov     rcx, r14; this
0x18000b00c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000b011  cmp     [rbx+18h], r15
0x18000b015  jnz     short loc_18000B027
0x18000b017  cmp     [rbx+48h], r15
0x18000b01b  jnz     short loc_18000B027
0x18000b01d  cmp     [rbx+30h], r15
0x18000b021  jz      loc_18000B0B7
0x18000b027  lea     r8, asc_1803D4E20; "    "
0x18000b02e  mov     rdx, rdi; wchar_t *
0x18000b031  mov     rcx, rax; this
0x18000b034  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000b039  mov     r9, [rbx+18h]; wchar_t *
0x18000b03d  test    r9, r9
0x18000b040  jz      short loc_18000B054
0x18000b042  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000b049  mov     rdx, rdi; wchar_t *
0x18000b04c  mov     rcx, rax; this
0x18000b04f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000b054  mov     r9, [rbx+48h]; wchar_t *
0x18000b058  test    r9, r9
0x18000b05b  jz      short loc_18000B06F
0x18000b05d  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000b064  mov     rdx, rdi; wchar_t *
0x18000b067  mov     rcx, rax; this
0x18000b06a  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000b06f  mov     rcx, [rbx+28h]
0x18000b073  mov     r9, [rbx+30h]; wchar_t *
0x18000b077  mov     rdx, rdi; wchar_t *
0x18000b07a  test    rcx, rcx
0x18000b07d  jz      short loc_18000B095
0x18000b07f  mov     [rsp+278h+lpBuffer], rcx
0x18000b084  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000b08b  mov     rcx, rax; this
0x18000b08e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000b093  jmp     short loc_18000B0B7
0x18000b095  mov     rcx, rax; this
0x18000b098  test    r9, r9
0x18000b09b  jz      short loc_18000B0AB
0x18000b09d  lea     r8, aHs; "[%hs]\n"
0x18000b0a4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000b0a9  jmp     short loc_18000B0B7
0x18000b0ab  lea     r8, asc_1803D4E98; "\n"
0x18000b0b2  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000b0b7  xor     eax, eax
0x18000b0b9  mov     rcx, [rsp+278h+var_38]
0x18000b0c1  xor     rcx, rsp; StackCookie
0x18000b0c4  call    __security_check_cookie
0x18000b0c9  mov     rbx, [rsp+278h+arg_18]
0x18000b0d1  add     rsp, 250h
0x18000b0d8  pop     r15
0x18000b0da  pop     r14
0x18000b0dc  pop     rdi
0x18000b0dd  pop     rsi
0x18000b0de  pop     rbp
0x18000b0df  retn
```
