# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800258c4`
- end: `0x180025b7a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18001ee70`
- `0x180027060`

## callees

- `0x1800210f0`
- `0x180021a54`
- `0x1800258c4`
- `0x180026000`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025a77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025a77`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800259f6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800259f6`

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
          v7 = (const char *)&byte_18004A111;
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
0x1800258c4  mov     [rsp+arg_18], rbx
0x1800258c9  push    rbp
0x1800258ca  push    rsi
0x1800258cb  push    rdi
0x1800258cc  push    r14
0x1800258ce  push    r15
0x1800258d0  sub     rsp, 250h
0x1800258d7  mov     rax, cs:__security_cookie
0x1800258de  xor     rax, rsp
0x1800258e1  mov     [rsp+278h+var_38], rax
0x1800258e9  mov     rbx, r8
0x1800258ec  mov     rsi, rdx
0x1800258ef  mov     r14, rcx
0x1800258f2  xor     r15d, r15d
0x1800258f5  test    rdx, rdx
0x1800258f8  jz      loc_180025B51
0x1800258fe  test    rcx, rcx
0x180025901  jz      loc_180025B51
0x180025907  mov     [rcx], r15w
0x18002590b  mov     rax, cs:g_pfnResultLoggingCallback
0x180025912  test    rax, rax
0x180025915  jz      short loc_180025938
0x180025917  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002591e  jz      short loc_180025938
0x180025920  mov     r8, rdx
0x180025923  mov     rdx, rcx
0x180025926  mov     rcx, rbx
0x180025929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002592e  cmp     [r14], r15w
0x180025932  jnz     loc_180025B51
0x180025938  mov     ecx, [rbx]
0x18002593a  mov     bpl, 8
0x18002593d  test    ecx, ecx
0x18002593f  jz      short loc_18002598A
0x180025941  sub     ecx, 1
0x180025944  jz      short loc_180025972
0x180025946  sub     ecx, 1
0x180025949  jz      short loc_180025962
0x18002594b  cmp     ecx, 1
0x18002594e  jz      short loc_180025959
0x180025950  lea     rdi, byte_18004A111
0x180025957  jmp     short loc_180025991
0x180025959  lea     rdi, aFailfast; "FailFast"
0x180025960  jmp     short loc_180025991
0x180025962  lea     rax, aLoghr; "LogHr"
0x180025969  lea     rdi, aLognt; "LogNt"
0x180025970  jmp     short loc_180025980
0x180025972  lea     rax, aReturnhr; "ReturnHr"
0x180025979  lea     rdi, aReturnnt; "ReturnNt"
0x180025980  test    [rbx+4], bpl
0x180025984  cmovz   rdi, rax
0x180025988  jmp     short loc_180025991
0x18002598a  lea     rdi, aException; "Exception"
0x180025991  xor     edx, edx; Val
0x180025993  mov     r8d, 200h; Size
0x180025999  lea     rcx, [rsp+278h+Buffer]; void *
0x18002599e  call    memset_0
0x1800259a3  test    [rbx+4], bpl
0x1800259a7  jz      short loc_1800259CC
0x1800259a9  mov     ebp, [rbx+0Ch]
0x1800259ac  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800259b3  test    rax, rax
0x1800259b6  jz      short loc_1800259FC
0x1800259b8  mov     r8d, 100h
0x1800259be  lea     rdx, [rsp+278h+Buffer]
0x1800259c3  mov     ecx, ebp
0x1800259c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259ca  jmp     short loc_1800259FC
0x1800259cc  mov     ebp, [rbx+8]
0x1800259cf  mov     [rsp+278h+Arguments], r15; Arguments
0x1800259d4  mov     [rsp+278h+nSize], 100h; nSize
0x1800259dc  lea     rax, [rsp+278h+Buffer]
0x1800259e1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800259e6  mov     r9d, 400h; dwLanguageId
0x1800259ec  mov     r8d, ebp; dwMessageId
0x1800259ef  xor     edx, edx; lpSource
0x1800259f1  mov     ecx, 1200h; dwFlags
0x1800259f6  call    cs:__imp_FormatMessageW
0x1800259fc  lea     rsi, [r14+rsi*2]
0x180025a00  mov     r9, [rbx+38h]; unsigned __int16 *
0x180025a04  mov     rax, [rbx+88h]
0x180025a0b  mov     rcx, [rbx+80h]
0x180025a12  mov     rdx, rsi; unsigned __int16 *
0x180025a15  test    r9, r9
0x180025a18  jz      short loc_180025A3C
0x180025a1a  mov     [rsp+278h+Arguments], rax
0x180025a1f  mov     qword ptr [rsp+278h+nSize], rcx
0x180025a24  mov     eax, [rbx+40h]
0x180025a27  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180025a2b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180025a32  mov     rcx, r14; this
0x180025a35  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025a3a  jmp     short loc_180025A53
0x180025a3c  mov     [rsp+278h+lpBuffer], rax
0x180025a41  mov     r9, rcx; unsigned __int16 *
0x180025a44  lea     r8, aHsP; "%hs!%p: "
0x180025a4b  mov     rcx, r14; this
0x180025a4e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025a53  mov     r14, rax
0x180025a56  mov     r9, [rbx+90h]; unsigned __int16 *
0x180025a5d  test    r9, r9
0x180025a60  jz      short loc_180025A77
0x180025a62  lea     r8, aCallerP; "(caller: %p) "
0x180025a69  mov     rdx, rsi; unsigned __int16 *
0x180025a6c  mov     rcx, rax; this
0x180025a6f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025a74  mov     r14, rax
0x180025a77  call    cs:__imp_GetCurrentThreadId
0x180025a7d  lea     rcx, [rsp+278h+Buffer]
0x180025a82  mov     [rsp+278h+var_240], rcx
0x180025a87  mov     dword ptr [rsp+278h+Arguments], ebp
0x180025a8b  mov     [rsp+278h+nSize], eax
0x180025a8f  mov     eax, [rbx+44h]
0x180025a92  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180025a96  mov     r9, rdi; unsigned __int16 *
0x180025a99  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180025aa0  mov     rdx, rsi; unsigned __int16 *
0x180025aa3  mov     rcx, r14; this
0x180025aa6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025aab  cmp     [rbx+18h], r15
0x180025aaf  jnz     short loc_180025AC1
0x180025ab1  cmp     [rbx+48h], r15
0x180025ab5  jnz     short loc_180025AC1
0x180025ab7  cmp     [rbx+30h], r15
0x180025abb  jz      loc_180025B51
0x180025ac1  lea     r8, asc_18004A940; "    "
0x180025ac8  mov     rdx, rsi; unsigned __int16 *
0x180025acb  mov     rcx, rax; this
0x180025ace  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025ad3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180025ad7  test    r9, r9
0x180025ada  jz      short loc_180025AEE
0x180025adc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180025ae3  mov     rdx, rsi; unsigned __int16 *
0x180025ae6  mov     rcx, rax; this
0x180025ae9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025aee  mov     r9, [rbx+48h]; unsigned __int16 *
0x180025af2  test    r9, r9
0x180025af5  jz      short loc_180025B09
0x180025af7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180025afe  mov     rdx, rsi; unsigned __int16 *
0x180025b01  mov     rcx, rax; this
0x180025b04  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025b09  mov     rcx, [rbx+28h]
0x180025b0d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180025b11  mov     rdx, rsi; unsigned __int16 *
0x180025b14  test    rcx, rcx
0x180025b17  jz      short loc_180025B2F
0x180025b19  mov     [rsp+278h+lpBuffer], rcx
0x180025b1e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180025b25  mov     rcx, rax; this
0x180025b28  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025b2d  jmp     short loc_180025B51
0x180025b2f  mov     rcx, rax; this
0x180025b32  test    r9, r9
0x180025b35  jz      short loc_180025B45
0x180025b37  lea     r8, aHs; "[%hs]\n"
0x180025b3e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025b43  jmp     short loc_180025B51
0x180025b45  lea     r8, asc_18004A9B8; "\n"
0x180025b4c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025b51  xor     eax, eax
0x180025b53  mov     rcx, [rsp+278h+var_38]
0x180025b5b  xor     rcx, rsp; StackCookie
0x180025b5e  call    __security_check_cookie
0x180025b63  mov     rbx, [rsp+278h+arg_18]
0x180025b6b  add     rsp, 250h
0x180025b72  pop     r15
0x180025b74  pop     r14
0x180025b76  pop     rdi
0x180025b77  pop     rsi
0x180025b78  pop     rbp
0x180025b79  retn
```
