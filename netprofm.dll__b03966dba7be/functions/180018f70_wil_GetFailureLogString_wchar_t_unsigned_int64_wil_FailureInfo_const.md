# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180018f70`
- end: `0x180019226`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180014840`
- `0x180019b80`
- `0x18001a20c`
- `0x18001d7a0`

## callees

- `0x1800120d0`
- `0x180012f40`
- `0x180018f70`
- `0x180019e80`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019123`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019123`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800190a2`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800190a2`

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
          v7 = (const char *)&byte_180047588;
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
0x180018f70  mov     [rsp+arg_18], rbx
0x180018f75  push    rbp
0x180018f76  push    rsi
0x180018f77  push    rdi
0x180018f78  push    r14
0x180018f7a  push    r15
0x180018f7c  sub     rsp, 250h
0x180018f83  mov     rax, cs:__security_cookie
0x180018f8a  xor     rax, rsp
0x180018f8d  mov     [rsp+278h+var_38], rax
0x180018f95  mov     rbx, r8
0x180018f98  mov     rsi, rdx
0x180018f9b  mov     r14, rcx
0x180018f9e  xor     r15d, r15d
0x180018fa1  test    rdx, rdx
0x180018fa4  jz      loc_1800191FD
0x180018faa  test    rcx, rcx
0x180018fad  jz      loc_1800191FD
0x180018fb3  mov     [rcx], r15w
0x180018fb7  mov     rax, cs:g_pfnResultLoggingCallback
0x180018fbe  test    rax, rax
0x180018fc1  jz      short loc_180018FE4
0x180018fc3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180018fca  jz      short loc_180018FE4
0x180018fcc  mov     r8, rdx
0x180018fcf  mov     rdx, rcx
0x180018fd2  mov     rcx, rbx
0x180018fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fda  cmp     [r14], r15w
0x180018fde  jnz     loc_1800191FD
0x180018fe4  mov     ecx, [rbx]
0x180018fe6  mov     bpl, 8
0x180018fe9  test    ecx, ecx
0x180018feb  jz      short loc_180019036
0x180018fed  sub     ecx, 1
0x180018ff0  jz      short loc_18001901E
0x180018ff2  sub     ecx, 1
0x180018ff5  jz      short loc_18001900E
0x180018ff7  cmp     ecx, 1
0x180018ffa  jz      short loc_180019005
0x180018ffc  lea     rdi, byte_180047588
0x180019003  jmp     short loc_18001903D
0x180019005  lea     rdi, aFailfast; "FailFast"
0x18001900c  jmp     short loc_18001903D
0x18001900e  lea     rax, aLoghr; "LogHr"
0x180019015  lea     rdi, aLognt; "LogNt"
0x18001901c  jmp     short loc_18001902C
0x18001901e  lea     rax, aReturnhr; "ReturnHr"
0x180019025  lea     rdi, aReturnnt; "ReturnNt"
0x18001902c  test    [rbx+4], bpl
0x180019030  cmovz   rdi, rax
0x180019034  jmp     short loc_18001903D
0x180019036  lea     rdi, aException; "Exception"
0x18001903d  xor     edx, edx; Val
0x18001903f  mov     r8d, 200h; Size
0x180019045  lea     rcx, [rsp+278h+Buffer]; void *
0x18001904a  call    memset_0
0x18001904f  test    [rbx+4], bpl
0x180019053  jz      short loc_180019078
0x180019055  mov     ebp, [rbx+0Ch]
0x180019058  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x18001905f  test    rax, rax
0x180019062  jz      short loc_1800190A8
0x180019064  mov     r8d, 100h
0x18001906a  lea     rdx, [rsp+278h+Buffer]
0x18001906f  mov     ecx, ebp
0x180019071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019076  jmp     short loc_1800190A8
0x180019078  mov     ebp, [rbx+8]
0x18001907b  mov     [rsp+278h+Arguments], r15; Arguments
0x180019080  mov     [rsp+278h+nSize], 100h; nSize
0x180019088  lea     rax, [rsp+278h+Buffer]
0x18001908d  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180019092  mov     r9d, 400h; dwLanguageId
0x180019098  mov     r8d, ebp; dwMessageId
0x18001909b  xor     edx, edx; lpSource
0x18001909d  mov     ecx, 1200h; dwFlags
0x1800190a2  call    cs:__imp_FormatMessageW
0x1800190a8  lea     rsi, [r14+rsi*2]
0x1800190ac  mov     r9, [rbx+38h]; wchar_t *
0x1800190b0  mov     rax, [rbx+88h]
0x1800190b7  mov     rcx, [rbx+80h]
0x1800190be  mov     rdx, rsi; wchar_t *
0x1800190c1  test    r9, r9
0x1800190c4  jz      short loc_1800190E8
0x1800190c6  mov     [rsp+278h+Arguments], rax
0x1800190cb  mov     qword ptr [rsp+278h+nSize], rcx
0x1800190d0  mov     eax, [rbx+40h]
0x1800190d3  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800190d7  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800190de  mov     rcx, r14; this
0x1800190e1  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800190e6  jmp     short loc_1800190FF
0x1800190e8  mov     [rsp+278h+lpBuffer], rax
0x1800190ed  mov     r9, rcx; wchar_t *
0x1800190f0  lea     r8, aHsP; "%hs!%p: "
0x1800190f7  mov     rcx, r14; this
0x1800190fa  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800190ff  mov     r14, rax
0x180019102  mov     r9, [rbx+90h]; wchar_t *
0x180019109  test    r9, r9
0x18001910c  jz      short loc_180019123
0x18001910e  lea     r8, aCallerP; "(caller: %p) "
0x180019115  mov     rdx, rsi; wchar_t *
0x180019118  mov     rcx, rax; this
0x18001911b  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180019120  mov     r14, rax
0x180019123  call    cs:__imp_GetCurrentThreadId
0x180019129  lea     rcx, [rsp+278h+Buffer]
0x18001912e  mov     [rsp+278h+var_240], rcx
0x180019133  mov     dword ptr [rsp+278h+Arguments], ebp
0x180019137  mov     [rsp+278h+nSize], eax
0x18001913b  mov     eax, [rbx+44h]
0x18001913e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180019142  mov     r9, rdi; wchar_t *
0x180019145  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18001914c  mov     rdx, rsi; wchar_t *
0x18001914f  mov     rcx, r14; this
0x180019152  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180019157  cmp     [rbx+18h], r15
0x18001915b  jnz     short loc_18001916D
0x18001915d  cmp     [rbx+48h], r15
0x180019161  jnz     short loc_18001916D
0x180019163  cmp     [rbx+30h], r15
0x180019167  jz      loc_1800191FD
0x18001916d  lea     r8, asc_180047798; "    "
0x180019174  mov     rdx, rsi; wchar_t *
0x180019177  mov     rcx, rax; this
0x18001917a  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18001917f  mov     r9, [rbx+18h]; wchar_t *
0x180019183  test    r9, r9
0x180019186  jz      short loc_18001919A
0x180019188  lea     r8, aMsgWs; "Msg:[%ws] "
0x18001918f  mov     rdx, rsi; wchar_t *
0x180019192  mov     rcx, rax; this
0x180019195  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18001919a  mov     r9, [rbx+48h]; wchar_t *
0x18001919e  test    r9, r9
0x1800191a1  jz      short loc_1800191B5
0x1800191a3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800191aa  mov     rdx, rsi; wchar_t *
0x1800191ad  mov     rcx, rax; this
0x1800191b0  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800191b5  mov     rcx, [rbx+28h]
0x1800191b9  mov     r9, [rbx+30h]; wchar_t *
0x1800191bd  mov     rdx, rsi; wchar_t *
0x1800191c0  test    rcx, rcx
0x1800191c3  jz      short loc_1800191DB
0x1800191c5  mov     [rsp+278h+lpBuffer], rcx
0x1800191ca  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800191d1  mov     rcx, rax; this
0x1800191d4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800191d9  jmp     short loc_1800191FD
0x1800191db  mov     rcx, rax; this
0x1800191de  test    r9, r9
0x1800191e1  jz      short loc_1800191F1
0x1800191e3  lea     r8, aHs; "[%hs]\n"
0x1800191ea  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800191ef  jmp     short loc_1800191FD
0x1800191f1  lea     r8, asc_180047810; "\n"
0x1800191f8  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800191fd  xor     eax, eax
0x1800191ff  mov     rcx, [rsp+278h+var_38]
0x180019207  xor     rcx, rsp; StackCookie
0x18001920a  call    __security_check_cookie
0x18001920f  mov     rbx, [rsp+278h+arg_18]
0x180019217  add     rsp, 250h
0x18001921e  pop     r15
0x180019220  pop     r14
0x180019222  pop     rdi
0x180019223  pop     rsi
0x180019224  pop     rbp
0x180019225  retn
```
