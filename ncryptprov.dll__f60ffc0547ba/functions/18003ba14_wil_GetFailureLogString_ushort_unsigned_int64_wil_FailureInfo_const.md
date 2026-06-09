# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18003ba14`
- end: `0x18003bcd7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18003c6ac`
- `0x18003eff0`

## callees

- `0x180038970`
- `0x18003ba14`
- `0x18003c9bc`
- `0x180062310`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003bbcd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003bbcd`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003bb46`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003bb46`

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
          v7 = (const char *)&word_18006C302;
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
0x18003ba14  mov     [rsp+arg_18], rbx
0x18003ba19  push    rbp
0x18003ba1a  push    rsi
0x18003ba1b  push    rdi
0x18003ba1c  push    r14
0x18003ba1e  push    r15
0x18003ba20  sub     rsp, 250h
0x18003ba27  mov     rax, cs:__security_cookie
0x18003ba2e  xor     rax, rsp
0x18003ba31  mov     [rsp+278h+var_38], rax
0x18003ba39  mov     rbx, r8
0x18003ba3c  mov     rsi, rdx
0x18003ba3f  mov     r14, rcx
0x18003ba42  xor     r15d, r15d
0x18003ba45  test    rdx, rdx
0x18003ba48  jz      loc_18003BCAD
0x18003ba4e  test    rcx, rcx
0x18003ba51  jz      loc_18003BCAD
0x18003ba57  mov     [rcx], r15w
0x18003ba5b  mov     rax, cs:g_pfnResultLoggingCallback
0x18003ba62  test    rax, rax
0x18003ba65  jz      short loc_18003BA88
0x18003ba67  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003ba6e  jz      short loc_18003BA88
0x18003ba70  mov     r8, rdx
0x18003ba73  mov     rdx, rcx
0x18003ba76  mov     rcx, rbx
0x18003ba79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba7e  cmp     [r14], r15w
0x18003ba82  jnz     loc_18003BCAD
0x18003ba88  mov     ecx, [rbx]
0x18003ba8a  mov     bpl, 8
0x18003ba8d  test    ecx, ecx
0x18003ba8f  jz      short loc_18003BADA
0x18003ba91  sub     ecx, 1
0x18003ba94  jz      short loc_18003BAC2
0x18003ba96  sub     ecx, 1
0x18003ba99  jz      short loc_18003BAB2
0x18003ba9b  cmp     ecx, 1
0x18003ba9e  jz      short loc_18003BAA9
0x18003baa0  lea     rdi, word_18006C302
0x18003baa7  jmp     short loc_18003BAE1
0x18003baa9  lea     rdi, aFailfast; "FailFast"
0x18003bab0  jmp     short loc_18003BAE1
0x18003bab2  lea     rax, aLoghr; "LogHr"
0x18003bab9  lea     rdi, aLognt; "LogNt"
0x18003bac0  jmp     short loc_18003BAD0
0x18003bac2  lea     rax, aReturnhr; "ReturnHr"
0x18003bac9  lea     rdi, aReturnnt; "ReturnNt"
0x18003bad0  test    [rbx+4], bpl
0x18003bad4  cmovz   rdi, rax
0x18003bad8  jmp     short loc_18003BAE1
0x18003bada  lea     rdi, aException; "Exception"
0x18003bae1  xor     edx, edx; Val
0x18003bae3  mov     r8d, 200h; Size
0x18003bae9  lea     rcx, [rsp+278h+Buffer]; void *
0x18003baee  call    memset_0
0x18003baf3  test    [rbx+4], bpl
0x18003baf7  jz      short loc_18003BB1C
0x18003baf9  mov     ebp, [rbx+0Ch]
0x18003bafc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18003bb03  test    rax, rax
0x18003bb06  jz      short loc_18003BB52
0x18003bb08  mov     r8d, 100h
0x18003bb0e  lea     rdx, [rsp+278h+Buffer]
0x18003bb13  mov     ecx, ebp
0x18003bb15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb1a  jmp     short loc_18003BB52
0x18003bb1c  mov     ebp, [rbx+8]
0x18003bb1f  mov     [rsp+278h+Arguments], r15; Arguments
0x18003bb24  mov     [rsp+278h+nSize], 100h; nSize
0x18003bb2c  lea     rax, [rsp+278h+Buffer]
0x18003bb31  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18003bb36  mov     r9d, 400h; dwLanguageId
0x18003bb3c  mov     r8d, ebp; dwMessageId
0x18003bb3f  xor     edx, edx; lpSource
0x18003bb41  mov     ecx, 1200h; dwFlags
0x18003bb46  call    cs:__imp_FormatMessageW
0x18003bb4d  nop     dword ptr [rax+rax+00h]
0x18003bb52  lea     rsi, [r14+rsi*2]
0x18003bb56  mov     r9, [rbx+38h]; unsigned __int16 *
0x18003bb5a  mov     rax, [rbx+88h]
0x18003bb61  mov     rcx, [rbx+80h]
0x18003bb68  mov     rdx, rsi; unsigned __int16 *
0x18003bb6b  test    r9, r9
0x18003bb6e  jz      short loc_18003BB92
0x18003bb70  mov     [rsp+278h+Arguments], rax
0x18003bb75  mov     qword ptr [rsp+278h+nSize], rcx
0x18003bb7a  mov     eax, [rbx+40h]
0x18003bb7d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18003bb81  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18003bb88  mov     rcx, r14; this
0x18003bb8b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003bb90  jmp     short loc_18003BBA9
0x18003bb92  mov     [rsp+278h+lpBuffer], rax
0x18003bb97  mov     r9, rcx; unsigned __int16 *
0x18003bb9a  lea     r8, aHsP; "%hs!%p: "
0x18003bba1  mov     rcx, r14; this
0x18003bba4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003bba9  mov     r14, rax
0x18003bbac  mov     r9, [rbx+90h]; unsigned __int16 *
0x18003bbb3  test    r9, r9
0x18003bbb6  jz      short loc_18003BBCD
0x18003bbb8  lea     r8, aCallerP; "(caller: %p) "
0x18003bbbf  mov     rdx, rsi; unsigned __int16 *
0x18003bbc2  mov     rcx, rax; this
0x18003bbc5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003bbca  mov     r14, rax
0x18003bbcd  call    cs:__imp_GetCurrentThreadId
0x18003bbd4  nop     dword ptr [rax+rax+00h]
0x18003bbd9  lea     rcx, [rsp+278h+Buffer]
0x18003bbde  mov     [rsp+278h+var_240], rcx
0x18003bbe3  mov     dword ptr [rsp+278h+Arguments], ebp
0x18003bbe7  mov     [rsp+278h+nSize], eax
0x18003bbeb  mov     eax, [rbx+44h]
0x18003bbee  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18003bbf2  mov     r9, rdi; unsigned __int16 *
0x18003bbf5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18003bbfc  mov     rdx, rsi; unsigned __int16 *
0x18003bbff  mov     rcx, r14; this
0x18003bc02  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003bc07  cmp     [rbx+18h], r15
0x18003bc0b  jnz     short loc_18003BC1D
0x18003bc0d  cmp     [rbx+48h], r15
0x18003bc11  jnz     short loc_18003BC1D
0x18003bc13  cmp     [rbx+30h], r15
0x18003bc17  jz      loc_18003BCAD
0x18003bc1d  lea     r8, asc_18006BF00; "    "
0x18003bc24  mov     rdx, rsi; unsigned __int16 *
0x18003bc27  mov     rcx, rax; this
0x18003bc2a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003bc2f  mov     r9, [rbx+18h]; unsigned __int16 *
0x18003bc33  test    r9, r9
0x18003bc36  jz      short loc_18003BC4A
0x18003bc38  lea     r8, aMsgWs; "Msg:[%ws] "
0x18003bc3f  mov     rdx, rsi; unsigned __int16 *
0x18003bc42  mov     rcx, rax; this
0x18003bc45  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003bc4a  mov     r9, [rbx+48h]; unsigned __int16 *
0x18003bc4e  test    r9, r9
0x18003bc51  jz      short loc_18003BC65
0x18003bc53  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18003bc5a  mov     rdx, rsi; unsigned __int16 *
0x18003bc5d  mov     rcx, rax; this
0x18003bc60  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003bc65  mov     rcx, [rbx+28h]
0x18003bc69  mov     r9, [rbx+30h]; unsigned __int16 *
0x18003bc6d  mov     rdx, rsi; unsigned __int16 *
0x18003bc70  test    rcx, rcx
0x18003bc73  jz      short loc_18003BC8B
0x18003bc75  mov     [rsp+278h+lpBuffer], rcx
0x18003bc7a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18003bc81  mov     rcx, rax; this
0x18003bc84  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003bc89  jmp     short loc_18003BCAD
0x18003bc8b  mov     rcx, rax; this
0x18003bc8e  test    r9, r9
0x18003bc91  jz      short loc_18003BCA1
0x18003bc93  lea     r8, aHs; "[%hs]\n"
0x18003bc9a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003bc9f  jmp     short loc_18003BCAD
0x18003bca1  lea     r8, asc_18006BF78; "\n"
0x18003bca8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003bcad  xor     eax, eax
0x18003bcaf  mov     rcx, [rsp+278h+var_38]
0x18003bcb7  xor     rcx, rsp; StackCookie
0x18003bcba  call    __security_check_cookie
0x18003bcbf  mov     rbx, [rsp+278h+arg_18]
0x18003bcc7  add     rsp, 250h
0x18003bcce  pop     r15
0x18003bcd0  pop     r14
0x18003bcd2  pop     rdi
0x18003bcd3  pop     rsi
0x18003bcd4  pop     rbp
0x18003bcd5  retn
```
