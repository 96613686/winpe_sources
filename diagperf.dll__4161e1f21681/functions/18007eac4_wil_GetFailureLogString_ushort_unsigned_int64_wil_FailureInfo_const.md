# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18007eac4`
- end: `0x18007ed7a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18007a458`
- `0x18007f64c`
- `0x180083160`

## callees

- `0x18007eac4`
- `0x18007f94c`
- `0x1800cf032`
- `0x1800cf080`
- `0x1800d6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007ec77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007ec77`
- `KERNEL32!FormatMessageW` at `0x18007ebf6`
- `KERNEL32!FormatMessageW` at `0x18007ebf6`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        STRSAFE_LPWSTR pszDest,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  const unsigned __int16 *Data4; // rdi
  const unsigned __int16 *p_Keyword; // rax
  DWORD v9; // ebp
  unsigned __int16 *v10; // rsi
  const unsigned __int16 *v11; // r9
  __int64 v12; // rax
  const unsigned __int16 *v13; // rcx
  wchar_t *v14; // rax
  wchar_t *v15; // r14
  const unsigned __int16 *v16; // r9
  wchar_t *v17; // rax
  const unsigned __int16 *v18; // r9
  wchar_t *v19; // rax
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
  if ( !pszDest )
    return 0;
  *pszDest = 0;
  if ( g_pfnResultLoggingCallback )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      g_pfnResultLoggingCallback(a3, pszDest, a2);
      if ( *pszDest )
        return 0;
    }
  }
  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      p_Keyword = (const unsigned __int16 *)&UMDF_PROVIDER.EventHeader.EventDescriptor.Keyword;
      Data4 = (const unsigned __int16 *)UMDF_PROVIDER.EventHeader.ProviderId.Data4;
    }
    else
    {
      if ( *(_DWORD *)a3 != 2 )
      {
        if ( *(_DWORD *)a3 == 3 )
          Data4 = &UMDF_PROVIDER.BufferContext.ProcessorIndex;
        else
          Data4 = &qword_1800E3778;
        goto LABEL_18;
      }
      p_Keyword = &UMDF_PROVIDER.EventHeader.ActivityId.Data2;
      Data4 = (const unsigned __int16 *)&UMDF_PROVIDER.EventHeader.ProcessorTime + 2;
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      Data4 = p_Keyword;
    goto LABEL_18;
  }
  Data4 = (const unsigned __int16 *)&UMDF_PROVIDER.EventHeader.TimeStamp;
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
  v10 = &pszDest[(_QWORD)a2];
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const unsigned __int16 **)(a3 + 128);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(
            pszDest,
            v10,
            (const unsigned __int16 *)&UMDF_PROVIDER.UserData,
            v11,
            lpBuffer,
            v13,
            v12);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(pszDest, v10, L"%hs!%p: ", v13, v12);
  }
  v15 = v14;
  v16 = *(const unsigned __int16 **)(a3 + 144);
  if ( v16 )
    v15 = wil::details::LogStringPrintf(v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = wil::details::LogStringPrintf(
          v15,
          v10,
          L"%hs(%d) tid(%x) %08X %ws",
          Data4,
          lpBuffera,
          *(_QWORD *)nSize,
          Arguments,
          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v10, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf(v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf(v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf(v19, v10, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf(v19, v10, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf(v19, v10, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18007eac4  mov     [rsp+arg_18], rbx
0x18007eac9  push    rbp
0x18007eaca  push    rsi
0x18007eacb  push    rdi
0x18007eacc  push    r14
0x18007eace  push    r15
0x18007ead0  sub     rsp, 250h
0x18007ead7  mov     rax, cs:__security_cookie
0x18007eade  xor     rax, rsp
0x18007eae1  mov     [rsp+278h+var_38], rax
0x18007eae9  mov     rbx, r8
0x18007eaec  mov     rsi, rdx
0x18007eaef  mov     r14, rcx
0x18007eaf2  xor     r15d, r15d
0x18007eaf5  test    rdx, rdx
0x18007eaf8  jz      loc_18007ED51
0x18007eafe  test    rcx, rcx
0x18007eb01  jz      loc_18007ED51
0x18007eb07  mov     [rcx], r15w
0x18007eb0b  mov     rax, cs:g_pfnResultLoggingCallback
0x18007eb12  test    rax, rax
0x18007eb15  jz      short loc_18007EB38
0x18007eb17  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18007eb1e  jz      short loc_18007EB38
0x18007eb20  mov     r8, rdx
0x18007eb23  mov     rdx, rcx
0x18007eb26  mov     rcx, rbx
0x18007eb29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eb2e  cmp     [r14], r15w
0x18007eb32  jnz     loc_18007ED51
0x18007eb38  mov     ecx, [rbx]
0x18007eb3a  mov     bpl, 8
0x18007eb3d  test    ecx, ecx
0x18007eb3f  jz      short loc_18007EB8A
0x18007eb41  sub     ecx, 1
0x18007eb44  jz      short loc_18007EB72
0x18007eb46  sub     ecx, 1
0x18007eb49  jz      short loc_18007EB62
0x18007eb4b  cmp     ecx, 1
0x18007eb4e  jz      short loc_18007EB59
0x18007eb50  lea     rdi, qword_1800E3778
0x18007eb57  jmp     short loc_18007EB91
0x18007eb59  lea     rdi, UMDF_PROVIDER.BufferContext
0x18007eb60  jmp     short loc_18007EB91
0x18007eb62  lea     rax, UMDF_PROVIDER.EventHeader.ActivityId.Data2
0x18007eb69  lea     rdi, UMDF_PROVIDER.EventHeader.38h+4
0x18007eb70  jmp     short loc_18007EB80
0x18007eb72  lea     rax, UMDF_PROVIDER.EventHeader.EventDescriptor.Keyword
0x18007eb79  lea     rdi, UMDF_PROVIDER.EventHeader.ProviderId.Data4
0x18007eb80  test    [rbx+4], bpl
0x18007eb84  cmovz   rdi, rax
0x18007eb88  jmp     short loc_18007EB91
0x18007eb8a  lea     rdi, UMDF_PROVIDER.EventHeader.TimeStamp
0x18007eb91  xor     edx, edx; Val
0x18007eb93  mov     r8d, 200h; Size
0x18007eb99  lea     rcx, [rsp+278h+Buffer]; void *
0x18007eb9e  call    memset_0
0x18007eba3  test    [rbx+4], bpl
0x18007eba7  jz      short loc_18007EBCC
0x18007eba9  mov     ebp, [rbx+0Ch]
0x18007ebac  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18007ebb3  test    rax, rax
0x18007ebb6  jz      short loc_18007EBFC
0x18007ebb8  mov     r8d, 100h
0x18007ebbe  lea     rdx, [rsp+278h+Buffer]
0x18007ebc3  mov     ecx, ebp
0x18007ebc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ebca  jmp     short loc_18007EBFC
0x18007ebcc  mov     ebp, [rbx+8]
0x18007ebcf  mov     [rsp+278h+Arguments], r15; Arguments
0x18007ebd4  mov     [rsp+278h+nSize], 100h; nSize
0x18007ebdc  lea     rax, [rsp+278h+Buffer]
0x18007ebe1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18007ebe6  mov     r9d, 400h; dwLanguageId
0x18007ebec  mov     r8d, ebp; dwMessageId
0x18007ebef  xor     edx, edx; lpSource
0x18007ebf1  mov     ecx, 1200h; dwFlags
0x18007ebf6  call    cs:__imp_FormatMessageW
0x18007ebfc  lea     rsi, [r14+rsi*2]
0x18007ec00  mov     r9, [rbx+38h]; unsigned __int16 *
0x18007ec04  mov     rax, [rbx+88h]
0x18007ec0b  mov     rcx, [rbx+80h]
0x18007ec12  mov     rdx, rsi; unsigned __int16 *
0x18007ec15  test    r9, r9
0x18007ec18  jz      short loc_18007EC3C
0x18007ec1a  mov     [rsp+278h+Arguments], rax
0x18007ec1f  mov     qword ptr [rsp+278h+nSize], rcx
0x18007ec24  mov     eax, [rbx+40h]
0x18007ec27  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18007ec2b  lea     r8, UMDF_PROVIDER.UserData; unsigned __int16 *
0x18007ec32  mov     rcx, r14; pszDest
0x18007ec35  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18007ec3a  jmp     short loc_18007EC53
0x18007ec3c  mov     [rsp+278h+lpBuffer], rax
0x18007ec41  mov     r9, rcx; unsigned __int16 *
0x18007ec44  lea     r8, aHsP; "%hs!%p: "
0x18007ec4b  mov     rcx, r14; pszDest
0x18007ec4e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18007ec53  mov     r14, rax
0x18007ec56  mov     r9, [rbx+90h]; unsigned __int16 *
0x18007ec5d  test    r9, r9
0x18007ec60  jz      short loc_18007EC77
0x18007ec62  lea     r8, aCallerP; "(caller: %p) "
0x18007ec69  mov     rdx, rsi; unsigned __int16 *
0x18007ec6c  mov     rcx, rax; pszDest
0x18007ec6f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18007ec74  mov     r14, rax
0x18007ec77  call    cs:__imp_GetCurrentThreadId
0x18007ec7d  lea     rcx, [rsp+278h+Buffer]
0x18007ec82  mov     [rsp+278h+var_240], rcx
0x18007ec87  mov     dword ptr [rsp+278h+Arguments], ebp
0x18007ec8b  mov     [rsp+278h+nSize], eax
0x18007ec8f  mov     eax, [rbx+44h]
0x18007ec92  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18007ec96  mov     r9, rdi; unsigned __int16 *
0x18007ec99  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18007eca0  mov     rdx, rsi; unsigned __int16 *
0x18007eca3  mov     rcx, r14; pszDest
0x18007eca6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18007ecab  cmp     [rbx+18h], r15
0x18007ecaf  jnz     short loc_18007ECC1
0x18007ecb1  cmp     [rbx+48h], r15
0x18007ecb5  jnz     short loc_18007ECC1
0x18007ecb7  cmp     [rbx+30h], r15
0x18007ecbb  jz      loc_18007ED51
0x18007ecc1  lea     r8, asc_1800E3340; "    "
0x18007ecc8  mov     rdx, rsi; unsigned __int16 *
0x18007eccb  mov     rcx, rax; pszDest
0x18007ecce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18007ecd3  mov     r9, [rbx+18h]; unsigned __int16 *
0x18007ecd7  test    r9, r9
0x18007ecda  jz      short loc_18007ECEE
0x18007ecdc  lea     r8, aMsgWs; "Msg:[%ws] "
0x18007ece3  mov     rdx, rsi; unsigned __int16 *
0x18007ece6  mov     rcx, rax; pszDest
0x18007ece9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18007ecee  mov     r9, [rbx+48h]; unsigned __int16 *
0x18007ecf2  test    r9, r9
0x18007ecf5  jz      short loc_18007ED09
0x18007ecf7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18007ecfe  mov     rdx, rsi; unsigned __int16 *
0x18007ed01  mov     rcx, rax; pszDest
0x18007ed04  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18007ed09  mov     rcx, [rbx+28h]
0x18007ed0d  mov     r9, [rbx+30h]; unsigned __int16 *
0x18007ed11  mov     rdx, rsi; unsigned __int16 *
0x18007ed14  test    rcx, rcx
0x18007ed17  jz      short loc_18007ED2F
0x18007ed19  mov     [rsp+278h+lpBuffer], rcx
0x18007ed1e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18007ed25  mov     rcx, rax; pszDest
0x18007ed28  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18007ed2d  jmp     short loc_18007ED51
0x18007ed2f  mov     rcx, rax; pszDest
0x18007ed32  test    r9, r9
0x18007ed35  jz      short loc_18007ED45
0x18007ed37  lea     r8, aHs; "[%hs]\n"
0x18007ed3e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18007ed43  jmp     short loc_18007ED51
0x18007ed45  lea     r8, asc_1800E33B8; "\n"
0x18007ed4c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18007ed51  xor     eax, eax
0x18007ed53  mov     rcx, [rsp+278h+var_38]
0x18007ed5b  xor     rcx, rsp; StackCookie
0x18007ed5e  call    __security_check_cookie
0x18007ed63  mov     rbx, [rsp+278h+arg_18]
0x18007ed6b  add     rsp, 250h
0x18007ed72  pop     r15
0x18007ed74  pop     r14
0x18007ed76  pop     rdi
0x18007ed77  pop     rsi
0x18007ed78  pop     rbp
0x18007ed79  retn
```
