# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18003bc84`
- end: `0x18003bf47`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180021728`
- `0x18003c828`
- `0x18003ed00`

## callees

- `0x180038270`
- `0x180038e64`
- `0x18003bc84`
- `0x18003c510`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003be3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003be3d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003bdb6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003bdb6`

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
          v7 = (const char *)&dword_180087A9C;
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
0x18003bc84  mov     [rsp+arg_18], rbx
0x18003bc89  push    rbp
0x18003bc8a  push    rsi
0x18003bc8b  push    rdi
0x18003bc8c  push    r14
0x18003bc8e  push    r15
0x18003bc90  sub     rsp, 250h
0x18003bc97  mov     rax, cs:__security_cookie
0x18003bc9e  xor     rax, rsp
0x18003bca1  mov     [rsp+278h+var_38], rax
0x18003bca9  mov     rbx, r8
0x18003bcac  mov     rsi, rdx
0x18003bcaf  mov     r14, rcx
0x18003bcb2  xor     r15d, r15d
0x18003bcb5  test    rdx, rdx
0x18003bcb8  jz      loc_18003BF1D
0x18003bcbe  test    rcx, rcx
0x18003bcc1  jz      loc_18003BF1D
0x18003bcc7  mov     [rcx], r15w
0x18003bccb  mov     rax, cs:g_pfnResultLoggingCallback
0x18003bcd2  test    rax, rax
0x18003bcd5  jz      short loc_18003BCF8
0x18003bcd7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003bcde  jz      short loc_18003BCF8
0x18003bce0  mov     r8, rdx
0x18003bce3  mov     rdx, rcx
0x18003bce6  mov     rcx, rbx
0x18003bce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bcee  cmp     [r14], r15w
0x18003bcf2  jnz     loc_18003BF1D
0x18003bcf8  mov     ecx, [rbx]
0x18003bcfa  mov     bpl, 8
0x18003bcfd  test    ecx, ecx
0x18003bcff  jz      short loc_18003BD4A
0x18003bd01  sub     ecx, 1
0x18003bd04  jz      short loc_18003BD32
0x18003bd06  sub     ecx, 1
0x18003bd09  jz      short loc_18003BD22
0x18003bd0b  cmp     ecx, 1
0x18003bd0e  jz      short loc_18003BD19
0x18003bd10  lea     rdi, dword_180087A9C
0x18003bd17  jmp     short loc_18003BD51
0x18003bd19  lea     rdi, aFailfast; "FailFast"
0x18003bd20  jmp     short loc_18003BD51
0x18003bd22  lea     rax, aLoghr; "LogHr"
0x18003bd29  lea     rdi, aLognt; "LogNt"
0x18003bd30  jmp     short loc_18003BD40
0x18003bd32  lea     rax, aReturnhr; "ReturnHr"
0x18003bd39  lea     rdi, aReturnnt; "ReturnNt"
0x18003bd40  test    [rbx+4], bpl
0x18003bd44  cmovz   rdi, rax
0x18003bd48  jmp     short loc_18003BD51
0x18003bd4a  lea     rdi, aException; "Exception"
0x18003bd51  xor     edx, edx; Val
0x18003bd53  mov     r8d, 200h; Size
0x18003bd59  lea     rcx, [rsp+278h+Buffer]; void *
0x18003bd5e  call    memset_0
0x18003bd63  test    [rbx+4], bpl
0x18003bd67  jz      short loc_18003BD8C
0x18003bd69  mov     ebp, [rbx+0Ch]
0x18003bd6c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18003bd73  test    rax, rax
0x18003bd76  jz      short loc_18003BDC2
0x18003bd78  mov     r8d, 100h
0x18003bd7e  lea     rdx, [rsp+278h+Buffer]
0x18003bd83  mov     ecx, ebp
0x18003bd85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bd8a  jmp     short loc_18003BDC2
0x18003bd8c  mov     ebp, [rbx+8]
0x18003bd8f  mov     [rsp+278h+Arguments], r15; Arguments
0x18003bd94  mov     [rsp+278h+nSize], 100h; nSize
0x18003bd9c  lea     rax, [rsp+278h+Buffer]
0x18003bda1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18003bda6  mov     r9d, 400h; dwLanguageId
0x18003bdac  mov     r8d, ebp; dwMessageId
0x18003bdaf  xor     edx, edx; lpSource
0x18003bdb1  mov     ecx, 1200h; dwFlags
0x18003bdb6  call    cs:__imp_FormatMessageW
0x18003bdbd  nop     dword ptr [rax+rax+00h]
0x18003bdc2  lea     rsi, [r14+rsi*2]
0x18003bdc6  mov     r9, [rbx+38h]; unsigned __int16 *
0x18003bdca  mov     rax, [rbx+88h]
0x18003bdd1  mov     rcx, [rbx+80h]
0x18003bdd8  mov     rdx, rsi; unsigned __int16 *
0x18003bddb  test    r9, r9
0x18003bdde  jz      short loc_18003BE02
0x18003bde0  mov     [rsp+278h+Arguments], rax
0x18003bde5  mov     qword ptr [rsp+278h+nSize], rcx
0x18003bdea  mov     eax, [rbx+40h]
0x18003bded  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18003bdf1  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18003bdf8  mov     rcx, r14; this
0x18003bdfb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003be00  jmp     short loc_18003BE19
0x18003be02  mov     [rsp+278h+lpBuffer], rax
0x18003be07  mov     r9, rcx; unsigned __int16 *
0x18003be0a  lea     r8, aHsP; "%hs!%p: "
0x18003be11  mov     rcx, r14; this
0x18003be14  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003be19  mov     r14, rax
0x18003be1c  mov     r9, [rbx+90h]; unsigned __int16 *
0x18003be23  test    r9, r9
0x18003be26  jz      short loc_18003BE3D
0x18003be28  lea     r8, aCallerP; "(caller: %p) "
0x18003be2f  mov     rdx, rsi; unsigned __int16 *
0x18003be32  mov     rcx, rax; this
0x18003be35  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003be3a  mov     r14, rax
0x18003be3d  call    cs:__imp_GetCurrentThreadId
0x18003be44  nop     dword ptr [rax+rax+00h]
0x18003be49  lea     rcx, [rsp+278h+Buffer]
0x18003be4e  mov     [rsp+278h+var_240], rcx
0x18003be53  mov     dword ptr [rsp+278h+Arguments], ebp
0x18003be57  mov     [rsp+278h+nSize], eax
0x18003be5b  mov     eax, [rbx+44h]
0x18003be5e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18003be62  mov     r9, rdi; unsigned __int16 *
0x18003be65  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18003be6c  mov     rdx, rsi; unsigned __int16 *
0x18003be6f  mov     rcx, r14; this
0x18003be72  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003be77  cmp     [rbx+18h], r15
0x18003be7b  jnz     short loc_18003BE8D
0x18003be7d  cmp     [rbx+48h], r15
0x18003be81  jnz     short loc_18003BE8D
0x18003be83  cmp     [rbx+30h], r15
0x18003be87  jz      loc_18003BF1D
0x18003be8d  lea     r8, asc_1800891B0; "    "
0x18003be94  mov     rdx, rsi; unsigned __int16 *
0x18003be97  mov     rcx, rax; this
0x18003be9a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003be9f  mov     r9, [rbx+18h]; unsigned __int16 *
0x18003bea3  test    r9, r9
0x18003bea6  jz      short loc_18003BEBA
0x18003bea8  lea     r8, aMsgWs; "Msg:[%ws] "
0x18003beaf  mov     rdx, rsi; unsigned __int16 *
0x18003beb2  mov     rcx, rax; this
0x18003beb5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003beba  mov     r9, [rbx+48h]; unsigned __int16 *
0x18003bebe  test    r9, r9
0x18003bec1  jz      short loc_18003BED5
0x18003bec3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18003beca  mov     rdx, rsi; unsigned __int16 *
0x18003becd  mov     rcx, rax; this
0x18003bed0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003bed5  mov     rcx, [rbx+28h]
0x18003bed9  mov     r9, [rbx+30h]; unsigned __int16 *
0x18003bedd  mov     rdx, rsi; unsigned __int16 *
0x18003bee0  test    rcx, rcx
0x18003bee3  jz      short loc_18003BEFB
0x18003bee5  mov     [rsp+278h+lpBuffer], rcx
0x18003beea  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18003bef1  mov     rcx, rax; this
0x18003bef4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003bef9  jmp     short loc_18003BF1D
0x18003befb  mov     rcx, rax; this
0x18003befe  test    r9, r9
0x18003bf01  jz      short loc_18003BF11
0x18003bf03  lea     r8, aHs; "[%hs]\n"
0x18003bf0a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003bf0f  jmp     short loc_18003BF1D
0x18003bf11  lea     r8, asc_180089228; "\n"
0x18003bf18  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003bf1d  xor     eax, eax
0x18003bf1f  mov     rcx, [rsp+278h+var_38]
0x18003bf27  xor     rcx, rsp; StackCookie
0x18003bf2a  call    __security_check_cookie
0x18003bf2f  mov     rbx, [rsp+278h+arg_18]
0x18003bf37  add     rsp, 250h
0x18003bf3e  pop     r15
0x18003bf40  pop     r14
0x18003bf42  pop     rdi
0x18003bf43  pop     rsi
0x18003bf44  pop     rbp
0x18003bf45  retn
```
