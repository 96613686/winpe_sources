# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18003bc34`
- end: `0x18003beea`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18003c5e0`
- `0x180046b90`

## callees

- `0x180024220`
- `0x180024bf4`
- `0x18003bc34`
- `0x18003c8dc`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003bde7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003bde7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003bd66`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003bd66`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rdi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rsi
  __int64 v13; // rax
  unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // r9
  wil::details *v16; // r14
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
  v7 = (void (__fastcall *)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
  *(_WORD *)this = 0;
  if ( v7 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      v7(a3, this, a2, a4);
      if ( *(_WORD *)this )
        return 0;
    }
  }
  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      v9 = "ReturnHr";
      v8 = "ReturnNt";
    }
    else
    {
      if ( *(_DWORD *)a3 != 2 )
      {
        if ( *(_DWORD *)a3 == 3 )
          v8 = "FailFast";
        else
          v8 = (const char *)&byte_1800912B0;
        goto LABEL_18;
      }
      v9 = "LogHr";
      v8 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v8 = v9;
    goto LABEL_18;
  }
  v8 = "Exception";
LABEL_18:
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
  {
    v10 = *(_DWORD *)(a3 + 12);
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(v10, Buffer, 0x100u);
  }
  else
  {
    v10 = *(_DWORD *)(a3 + 8);
    FormatMessageW(0x1200u, 0, v10, 0x400u, Buffer, 0x100u, 0);
  }
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = (unsigned __int16 *)((char *)this + 2 * (_QWORD)a2);
  v13 = *(_QWORD *)(a3 + 136);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, *(_QWORD *)(a3 + 128), v13);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs!%p: ", *(const unsigned __int16 **)(a3 + 128), v13);
  }
  v15 = *(const unsigned __int16 **)(a3 + 144);
  v16 = (wil::details *)v14;
  if ( v15 )
    v16 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v12, L"(caller: %p) ", v15);
  LODWORD(Arguments) = v10;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v16,
                          v12,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const unsigned __int16 *)v8,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v12, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003bc34  mov     [rsp+arg_18], rbx
0x18003bc39  push    rbp
0x18003bc3a  push    rsi
0x18003bc3b  push    rdi
0x18003bc3c  push    r14
0x18003bc3e  push    r15
0x18003bc40  sub     rsp, 250h
0x18003bc47  mov     rax, cs:__security_cookie
0x18003bc4e  xor     rax, rsp
0x18003bc51  mov     [rsp+278h+var_38], rax
0x18003bc59  xor     r15d, r15d
0x18003bc5c  mov     rbx, r8
0x18003bc5f  mov     rsi, rdx
0x18003bc62  mov     r14, rcx
0x18003bc65  test    rdx, rdx
0x18003bc68  jz      loc_18003BEC1
0x18003bc6e  test    rcx, rcx
0x18003bc71  jz      loc_18003BEC1
0x18003bc77  mov     rax, cs:g_pfnResultLoggingCallback
0x18003bc7e  mov     [rcx], r15w
0x18003bc82  test    rax, rax
0x18003bc85  jz      short loc_18003BCA8
0x18003bc87  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003bc8e  jz      short loc_18003BCA8
0x18003bc90  mov     r8, rdx
0x18003bc93  mov     rdx, rcx
0x18003bc96  mov     rcx, rbx
0x18003bc99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc9e  cmp     [r14], r15w
0x18003bca2  jnz     loc_18003BEC1
0x18003bca8  mov     ecx, [rbx]
0x18003bcaa  mov     bpl, 8
0x18003bcad  test    ecx, ecx
0x18003bcaf  jz      short loc_18003BCFA
0x18003bcb1  sub     ecx, 1
0x18003bcb4  jz      short loc_18003BCE2
0x18003bcb6  sub     ecx, 1
0x18003bcb9  jz      short loc_18003BCD2
0x18003bcbb  cmp     ecx, 1
0x18003bcbe  jz      short loc_18003BCC9
0x18003bcc0  lea     rdi, byte_1800912B0
0x18003bcc7  jmp     short loc_18003BD01
0x18003bcc9  lea     rdi, aFailfast; "FailFast"
0x18003bcd0  jmp     short loc_18003BD01
0x18003bcd2  lea     rax, aLoghr; "LogHr"
0x18003bcd9  lea     rdi, aLognt; "LogNt"
0x18003bce0  jmp     short loc_18003BCF0
0x18003bce2  lea     rax, aReturnhr; "ReturnHr"
0x18003bce9  lea     rdi, aReturnnt; "ReturnNt"
0x18003bcf0  test    [rbx+4], bpl
0x18003bcf4  cmovz   rdi, rax
0x18003bcf8  jmp     short loc_18003BD01
0x18003bcfa  lea     rdi, aException; "Exception"
0x18003bd01  xor     edx, edx; Val
0x18003bd03  lea     rcx, [rsp+278h+Buffer]; void *
0x18003bd08  mov     r8d, 200h; Size
0x18003bd0e  call    memset_0
0x18003bd13  test    [rbx+4], bpl
0x18003bd17  jz      short loc_18003BD3C
0x18003bd19  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18003bd20  mov     ebp, [rbx+0Ch]
0x18003bd23  test    rax, rax
0x18003bd26  jz      short loc_18003BD6C
0x18003bd28  mov     r8d, 100h
0x18003bd2e  lea     rdx, [rsp+278h+Buffer]
0x18003bd33  mov     ecx, ebp
0x18003bd35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bd3a  jmp     short loc_18003BD6C
0x18003bd3c  mov     ebp, [rbx+8]
0x18003bd3f  lea     rax, [rsp+278h+Buffer]
0x18003bd44  mov     [rsp+278h+Arguments], r15; Arguments
0x18003bd49  mov     r8d, ebp; dwMessageId
0x18003bd4c  mov     [rsp+278h+nSize], 100h; nSize
0x18003bd54  mov     r9d, 400h; dwLanguageId
0x18003bd5a  xor     edx, edx; lpSource
0x18003bd5c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18003bd61  mov     ecx, 1200h; dwFlags
0x18003bd66  call    cs:__imp_FormatMessageW
0x18003bd6c  mov     r9, [rbx+38h]; unsigned __int16 *
0x18003bd70  lea     rsi, [r14+rsi*2]
0x18003bd74  mov     rax, [rbx+88h]
0x18003bd7b  mov     rdx, rsi; unsigned __int16 *
0x18003bd7e  mov     rcx, [rbx+80h]
0x18003bd85  test    r9, r9
0x18003bd88  jz      short loc_18003BDAC
0x18003bd8a  mov     [rsp+278h+Arguments], rax
0x18003bd8f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18003bd96  mov     eax, [rbx+40h]
0x18003bd99  mov     qword ptr [rsp+278h+nSize], rcx
0x18003bd9e  mov     rcx, r14; this
0x18003bda1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18003bda5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003bdaa  jmp     short loc_18003BDC3
0x18003bdac  mov     r9, rcx; unsigned __int16 *
0x18003bdaf  mov     [rsp+278h+lpBuffer], rax
0x18003bdb4  mov     rcx, r14; this
0x18003bdb7  lea     r8, aHsP; "%hs!%p: "
0x18003bdbe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003bdc3  mov     r9, [rbx+90h]; unsigned __int16 *
0x18003bdca  mov     r14, rax
0x18003bdcd  test    r9, r9
0x18003bdd0  jz      short loc_18003BDE7
0x18003bdd2  lea     r8, aCallerP; "(caller: %p) "
0x18003bdd9  mov     rdx, rsi; unsigned __int16 *
0x18003bddc  mov     rcx, rax; this
0x18003bddf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003bde4  mov     r14, rax
0x18003bde7  call    cs:__imp_GetCurrentThreadId
0x18003bded  lea     rcx, [rsp+278h+Buffer]
0x18003bdf2  mov     r9, rdi; unsigned __int16 *
0x18003bdf5  mov     [rsp+278h+var_240], rcx
0x18003bdfa  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18003be01  mov     dword ptr [rsp+278h+Arguments], ebp
0x18003be05  mov     rdx, rsi; unsigned __int16 *
0x18003be08  mov     [rsp+278h+nSize], eax
0x18003be0c  mov     rcx, r14; this
0x18003be0f  mov     eax, [rbx+44h]
0x18003be12  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18003be16  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003be1b  cmp     [rbx+18h], r15
0x18003be1f  jnz     short loc_18003BE31
0x18003be21  cmp     [rbx+48h], r15
0x18003be25  jnz     short loc_18003BE31
0x18003be27  cmp     [rbx+30h], r15
0x18003be2b  jz      loc_18003BEC1
0x18003be31  lea     r8, asc_1800913A0; "    "
0x18003be38  mov     rdx, rsi; unsigned __int16 *
0x18003be3b  mov     rcx, rax; this
0x18003be3e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003be43  mov     r9, [rbx+18h]; unsigned __int16 *
0x18003be47  test    r9, r9
0x18003be4a  jz      short loc_18003BE5E
0x18003be4c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18003be53  mov     rdx, rsi; unsigned __int16 *
0x18003be56  mov     rcx, rax; this
0x18003be59  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003be5e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18003be62  test    r9, r9
0x18003be65  jz      short loc_18003BE79
0x18003be67  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18003be6e  mov     rdx, rsi; unsigned __int16 *
0x18003be71  mov     rcx, rax; this
0x18003be74  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003be79  mov     rcx, [rbx+28h]
0x18003be7d  mov     rdx, rsi; unsigned __int16 *
0x18003be80  mov     r9, [rbx+30h]; unsigned __int16 *
0x18003be84  test    rcx, rcx
0x18003be87  jz      short loc_18003BE9F
0x18003be89  mov     [rsp+278h+lpBuffer], rcx
0x18003be8e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18003be95  mov     rcx, rax; this
0x18003be98  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003be9d  jmp     short loc_18003BEC1
0x18003be9f  mov     rcx, rax; this
0x18003bea2  test    r9, r9
0x18003bea5  jz      short loc_18003BEB5
0x18003bea7  lea     r8, aHs; "[%hs]\n"
0x18003beae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003beb3  jmp     short loc_18003BEC1
0x18003beb5  lea     r8, asc_180091418; "\n"
0x18003bebc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003bec1  xor     eax, eax
0x18003bec3  mov     rcx, [rsp+278h+var_38]
0x18003becb  xor     rcx, rsp; StackCookie
0x18003bece  call    __security_check_cookie
0x18003bed3  mov     rbx, [rsp+278h+arg_18]
0x18003bedb  add     rsp, 250h
0x18003bee2  pop     r15
0x18003bee4  pop     r14
0x18003bee6  pop     rdi
0x18003bee7  pop     rsi
0x18003bee8  pop     rbp
0x18003bee9  retn
```
