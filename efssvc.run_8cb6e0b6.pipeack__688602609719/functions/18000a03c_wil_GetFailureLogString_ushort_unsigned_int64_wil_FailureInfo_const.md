# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000a03c`
- end: `0x18000a2ff`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800091dc`
- `0x18000945c`
- `0x18000a8d0`

## callees

- `0x18000a03c`
- `0x18000abe4`
- `0x18000d192`
- `0x18000d1c0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a1f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a1f5`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a16e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a16e`

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
          v8 = (const char *)&dword_18001424C;
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
0x18000a03c  mov     [rsp+arg_18], rbx
0x18000a041  push    rbp
0x18000a042  push    rsi
0x18000a043  push    rdi
0x18000a044  push    r14
0x18000a046  push    r15
0x18000a048  sub     rsp, 250h
0x18000a04f  mov     rax, cs:__security_cookie
0x18000a056  xor     rax, rsp
0x18000a059  mov     [rsp+278h+var_38], rax
0x18000a061  xor     r15d, r15d
0x18000a064  mov     rbx, r8
0x18000a067  mov     rsi, rdx
0x18000a06a  mov     r14, rcx
0x18000a06d  test    rdx, rdx
0x18000a070  jz      loc_18000A2D5
0x18000a076  test    rcx, rcx
0x18000a079  jz      loc_18000A2D5
0x18000a07f  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a086  mov     [rcx], r15w
0x18000a08a  test    rax, rax
0x18000a08d  jz      short loc_18000A0B0
0x18000a08f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000a096  jz      short loc_18000A0B0
0x18000a098  mov     r8, rdx
0x18000a09b  mov     rdx, rcx
0x18000a09e  mov     rcx, rbx
0x18000a0a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0a6  cmp     [r14], r15w
0x18000a0aa  jnz     loc_18000A2D5
0x18000a0b0  mov     ecx, [rbx]
0x18000a0b2  mov     bpl, 8
0x18000a0b5  test    ecx, ecx
0x18000a0b7  jz      short loc_18000A102
0x18000a0b9  sub     ecx, 1
0x18000a0bc  jz      short loc_18000A0EA
0x18000a0be  sub     ecx, 1
0x18000a0c1  jz      short loc_18000A0DA
0x18000a0c3  cmp     ecx, 1
0x18000a0c6  jz      short loc_18000A0D1
0x18000a0c8  lea     rdi, dword_18001424C
0x18000a0cf  jmp     short loc_18000A109
0x18000a0d1  lea     rdi, aFailfast; "FailFast"
0x18000a0d8  jmp     short loc_18000A109
0x18000a0da  lea     rax, aLoghr; "LogHr"
0x18000a0e1  lea     rdi, aLognt; "LogNt"
0x18000a0e8  jmp     short loc_18000A0F8
0x18000a0ea  lea     rax, aReturnhr; "ReturnHr"
0x18000a0f1  lea     rdi, aReturnnt; "ReturnNt"
0x18000a0f8  test    [rbx+4], bpl
0x18000a0fc  cmovz   rdi, rax
0x18000a100  jmp     short loc_18000A109
0x18000a102  lea     rdi, aException; "Exception"
0x18000a109  xor     edx, edx; Val
0x18000a10b  lea     rcx, [rsp+278h+Buffer]; void *
0x18000a110  mov     r8d, 200h; Size
0x18000a116  call    memset_0
0x18000a11b  test    [rbx+4], bpl
0x18000a11f  jz      short loc_18000A144
0x18000a121  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000a128  mov     ebp, [rbx+0Ch]
0x18000a12b  test    rax, rax
0x18000a12e  jz      short loc_18000A17A
0x18000a130  mov     r8d, 100h
0x18000a136  lea     rdx, [rsp+278h+Buffer]
0x18000a13b  mov     ecx, ebp
0x18000a13d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a142  jmp     short loc_18000A17A
0x18000a144  mov     ebp, [rbx+8]
0x18000a147  lea     rax, [rsp+278h+Buffer]
0x18000a14c  mov     [rsp+278h+Arguments], r15; Arguments
0x18000a151  mov     r8d, ebp; dwMessageId
0x18000a154  mov     [rsp+278h+nSize], 100h; nSize
0x18000a15c  mov     r9d, 400h; dwLanguageId
0x18000a162  xor     edx, edx; lpSource
0x18000a164  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000a169  mov     ecx, 1200h; dwFlags
0x18000a16e  call    cs:__imp_FormatMessageW
0x18000a175  nop     dword ptr [rax+rax+00h]
0x18000a17a  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000a17e  lea     rsi, [r14+rsi*2]
0x18000a182  mov     rax, [rbx+88h]
0x18000a189  mov     rdx, rsi; unsigned __int16 *
0x18000a18c  mov     rcx, [rbx+80h]
0x18000a193  test    r9, r9
0x18000a196  jz      short loc_18000A1BA
0x18000a198  mov     [rsp+278h+Arguments], rax
0x18000a19d  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000a1a4  mov     eax, [rbx+40h]
0x18000a1a7  mov     qword ptr [rsp+278h+nSize], rcx
0x18000a1ac  mov     rcx, r14; this
0x18000a1af  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000a1b3  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a1b8  jmp     short loc_18000A1D1
0x18000a1ba  mov     r9, rcx; unsigned __int16 *
0x18000a1bd  mov     [rsp+278h+lpBuffer], rax
0x18000a1c2  mov     rcx, r14; this
0x18000a1c5  lea     r8, aHsP; "%hs!%p: "
0x18000a1cc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a1d1  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000a1d8  mov     r14, rax
0x18000a1db  test    r9, r9
0x18000a1de  jz      short loc_18000A1F5
0x18000a1e0  lea     r8, aCallerP; "(caller: %p) "
0x18000a1e7  mov     rdx, rsi; unsigned __int16 *
0x18000a1ea  mov     rcx, rax; this
0x18000a1ed  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a1f2  mov     r14, rax
0x18000a1f5  call    cs:__imp_GetCurrentThreadId
0x18000a1fc  nop     dword ptr [rax+rax+00h]
0x18000a201  lea     rcx, [rsp+278h+Buffer]
0x18000a206  mov     r9, rdi; unsigned __int16 *
0x18000a209  mov     [rsp+278h+var_240], rcx
0x18000a20e  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000a215  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000a219  mov     rdx, rsi; unsigned __int16 *
0x18000a21c  mov     [rsp+278h+nSize], eax
0x18000a220  mov     rcx, r14; this
0x18000a223  mov     eax, [rbx+44h]
0x18000a226  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000a22a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a22f  cmp     [rbx+18h], r15
0x18000a233  jnz     short loc_18000A245
0x18000a235  cmp     [rbx+48h], r15
0x18000a239  jnz     short loc_18000A245
0x18000a23b  cmp     [rbx+30h], r15
0x18000a23f  jz      loc_18000A2D5
0x18000a245  lea     r8, asc_180014338; "    "
0x18000a24c  mov     rdx, rsi; unsigned __int16 *
0x18000a24f  mov     rcx, rax; this
0x18000a252  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a257  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000a25b  test    r9, r9
0x18000a25e  jz      short loc_18000A272
0x18000a260  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000a267  mov     rdx, rsi; unsigned __int16 *
0x18000a26a  mov     rcx, rax; this
0x18000a26d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a272  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000a276  test    r9, r9
0x18000a279  jz      short loc_18000A28D
0x18000a27b  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000a282  mov     rdx, rsi; unsigned __int16 *
0x18000a285  mov     rcx, rax; this
0x18000a288  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a28d  mov     rcx, [rbx+28h]
0x18000a291  mov     rdx, rsi; unsigned __int16 *
0x18000a294  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000a298  test    rcx, rcx
0x18000a29b  jz      short loc_18000A2B3
0x18000a29d  mov     [rsp+278h+lpBuffer], rcx
0x18000a2a2  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000a2a9  mov     rcx, rax; this
0x18000a2ac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a2b1  jmp     short loc_18000A2D5
0x18000a2b3  mov     rcx, rax; this
0x18000a2b6  test    r9, r9
0x18000a2b9  jz      short loc_18000A2C9
0x18000a2bb  lea     r8, aHs; "[%hs]\n"
0x18000a2c2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a2c7  jmp     short loc_18000A2D5
0x18000a2c9  lea     r8, asc_1800143B0; "\n"
0x18000a2d0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a2d5  xor     eax, eax
0x18000a2d7  mov     rcx, [rsp+278h+var_38]
0x18000a2df  xor     rcx, rsp; StackCookie
0x18000a2e2  call    __security_check_cookie
0x18000a2e7  mov     rbx, [rsp+278h+arg_18]
0x18000a2ef  add     rsp, 250h
0x18000a2f6  pop     r15
0x18000a2f8  pop     r14
0x18000a2fa  pop     rdi
0x18000a2fb  pop     rsi
0x18000a2fc  pop     rbp
0x18000a2fd  retn
```
