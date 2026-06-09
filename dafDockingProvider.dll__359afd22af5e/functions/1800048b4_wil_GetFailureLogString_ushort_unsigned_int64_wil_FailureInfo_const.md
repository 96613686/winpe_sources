# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800048b4`
- end: `0x180004b6a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180002710`
- `0x180002978`
- `0x180005214`
- `0x180008110`

## callees

- `0x1800048b4`
- `0x180005514`
- `0x18001ca3e`
- `0x18001ca70`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a67`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800049e6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800049e6`

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
          v7 = (const char *)&qword_180020D78;
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
0x1800048b4  mov     [rsp+arg_18], rbx
0x1800048b9  push    rbp
0x1800048ba  push    rsi
0x1800048bb  push    rdi
0x1800048bc  push    r14
0x1800048be  push    r15
0x1800048c0  sub     rsp, 250h
0x1800048c7  mov     rax, cs:__security_cookie
0x1800048ce  xor     rax, rsp
0x1800048d1  mov     [rsp+278h+var_38], rax
0x1800048d9  mov     rbx, r8
0x1800048dc  mov     rsi, rdx
0x1800048df  mov     r14, rcx
0x1800048e2  xor     r15d, r15d
0x1800048e5  test    rdx, rdx
0x1800048e8  jz      loc_180004B41
0x1800048ee  test    rcx, rcx
0x1800048f1  jz      loc_180004B41
0x1800048f7  mov     [rcx], r15w
0x1800048fb  mov     rax, cs:g_pfnResultLoggingCallback
0x180004902  test    rax, rax
0x180004905  jz      short loc_180004928
0x180004907  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000490e  jz      short loc_180004928
0x180004910  mov     r8, rdx
0x180004913  mov     rdx, rcx
0x180004916  mov     rcx, rbx
0x180004919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000491e  cmp     [r14], r15w
0x180004922  jnz     loc_180004B41
0x180004928  mov     ecx, [rbx]
0x18000492a  mov     bpl, 8
0x18000492d  test    ecx, ecx
0x18000492f  jz      short loc_18000497A
0x180004931  sub     ecx, 1
0x180004934  jz      short loc_180004962
0x180004936  sub     ecx, 1
0x180004939  jz      short loc_180004952
0x18000493b  cmp     ecx, 1
0x18000493e  jz      short loc_180004949
0x180004940  lea     rdi, qword_180020D78
0x180004947  jmp     short loc_180004981
0x180004949  lea     rdi, aFailfast; "FailFast"
0x180004950  jmp     short loc_180004981
0x180004952  lea     rax, aLoghr; "LogHr"
0x180004959  lea     rdi, aLognt; "LogNt"
0x180004960  jmp     short loc_180004970
0x180004962  lea     rax, aReturnhr; "ReturnHr"
0x180004969  lea     rdi, aReturnnt; "ReturnNt"
0x180004970  test    [rbx+4], bpl
0x180004974  cmovz   rdi, rax
0x180004978  jmp     short loc_180004981
0x18000497a  lea     rdi, aException; "Exception"
0x180004981  xor     edx, edx; Val
0x180004983  mov     r8d, 200h; Size
0x180004989  lea     rcx, [rsp+278h+Buffer]; void *
0x18000498e  call    memset_0
0x180004993  test    [rbx+4], bpl
0x180004997  jz      short loc_1800049BC
0x180004999  mov     ebp, [rbx+0Ch]
0x18000499c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800049a3  test    rax, rax
0x1800049a6  jz      short loc_1800049EC
0x1800049a8  mov     r8d, 100h
0x1800049ae  lea     rdx, [rsp+278h+Buffer]
0x1800049b3  mov     ecx, ebp
0x1800049b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049ba  jmp     short loc_1800049EC
0x1800049bc  mov     ebp, [rbx+8]
0x1800049bf  mov     [rsp+278h+Arguments], r15; Arguments
0x1800049c4  mov     [rsp+278h+nSize], 100h; nSize
0x1800049cc  lea     rax, [rsp+278h+Buffer]
0x1800049d1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800049d6  mov     r9d, 400h; dwLanguageId
0x1800049dc  mov     r8d, ebp; dwMessageId
0x1800049df  xor     edx, edx; lpSource
0x1800049e1  mov     ecx, 1200h; dwFlags
0x1800049e6  call    cs:__imp_FormatMessageW
0x1800049ec  lea     rsi, [r14+rsi*2]
0x1800049f0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800049f4  mov     rax, [rbx+88h]
0x1800049fb  mov     rcx, [rbx+80h]
0x180004a02  mov     rdx, rsi; unsigned __int16 *
0x180004a05  test    r9, r9
0x180004a08  jz      short loc_180004A2C
0x180004a0a  mov     [rsp+278h+Arguments], rax
0x180004a0f  mov     qword ptr [rsp+278h+nSize], rcx
0x180004a14  mov     eax, [rbx+40h]
0x180004a17  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004a1b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004a22  mov     rcx, r14; this
0x180004a25  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004a2a  jmp     short loc_180004A43
0x180004a2c  mov     [rsp+278h+lpBuffer], rax
0x180004a31  mov     r9, rcx; unsigned __int16 *
0x180004a34  lea     r8, aHsP; "%hs!%p: "
0x180004a3b  mov     rcx, r14; this
0x180004a3e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004a43  mov     r14, rax
0x180004a46  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004a4d  test    r9, r9
0x180004a50  jz      short loc_180004A67
0x180004a52  lea     r8, aCallerP; "(caller: %p) "
0x180004a59  mov     rdx, rsi; unsigned __int16 *
0x180004a5c  mov     rcx, rax; this
0x180004a5f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004a64  mov     r14, rax
0x180004a67  call    cs:__imp_GetCurrentThreadId
0x180004a6d  lea     rcx, [rsp+278h+Buffer]
0x180004a72  mov     [rsp+278h+var_240], rcx
0x180004a77  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004a7b  mov     [rsp+278h+nSize], eax
0x180004a7f  mov     eax, [rbx+44h]
0x180004a82  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004a86  mov     r9, rdi; unsigned __int16 *
0x180004a89  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004a90  mov     rdx, rsi; unsigned __int16 *
0x180004a93  mov     rcx, r14; this
0x180004a96  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004a9b  cmp     [rbx+18h], r15
0x180004a9f  jnz     short loc_180004AB1
0x180004aa1  cmp     [rbx+48h], r15
0x180004aa5  jnz     short loc_180004AB1
0x180004aa7  cmp     [rbx+30h], r15
0x180004aab  jz      loc_180004B41
0x180004ab1  lea     r8, asc_180020E68; "    "
0x180004ab8  mov     rdx, rsi; unsigned __int16 *
0x180004abb  mov     rcx, rax; this
0x180004abe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004ac3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004ac7  test    r9, r9
0x180004aca  jz      short loc_180004ADE
0x180004acc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004ad3  mov     rdx, rsi; unsigned __int16 *
0x180004ad6  mov     rcx, rax; this
0x180004ad9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004ade  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004ae2  test    r9, r9
0x180004ae5  jz      short loc_180004AF9
0x180004ae7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180004aee  mov     rdx, rsi; unsigned __int16 *
0x180004af1  mov     rcx, rax; this
0x180004af4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004af9  mov     rcx, [rbx+28h]
0x180004afd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004b01  mov     rdx, rsi; unsigned __int16 *
0x180004b04  test    rcx, rcx
0x180004b07  jz      short loc_180004B1F
0x180004b09  mov     [rsp+278h+lpBuffer], rcx
0x180004b0e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004b15  mov     rcx, rax; this
0x180004b18  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b1d  jmp     short loc_180004B41
0x180004b1f  mov     rcx, rax; this
0x180004b22  test    r9, r9
0x180004b25  jz      short loc_180004B35
0x180004b27  lea     r8, aHs; "[%hs]\n"
0x180004b2e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b33  jmp     short loc_180004B41
0x180004b35  lea     r8, asc_180020EE0; "\n"
0x180004b3c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b41  xor     eax, eax
0x180004b43  mov     rcx, [rsp+278h+var_38]
0x180004b4b  xor     rcx, rsp; StackCookie
0x180004b4e  call    __security_check_cookie
0x180004b53  mov     rbx, [rsp+278h+arg_18]
0x180004b5b  add     rsp, 250h
0x180004b62  pop     r15
0x180004b64  pop     r14
0x180004b66  pop     rdi
0x180004b67  pop     rsi
0x180004b68  pop     rbp
0x180004b69  retn
```
