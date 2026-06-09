# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000d1f4`
- end: `0x18000d4aa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000b9e4`
- `0x18000bc54`
- `0x18000e034`
- `0x180010490`

## callees

- `0x180001f90`
- `0x180002a40`
- `0x18000d1f4`
- `0x18000e334`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d3a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d3a7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000d326`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000d326`

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
          v7 = (const char *)&word_1800155AE;
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
0x18000d1f4  mov     [rsp+arg_18], rbx
0x18000d1f9  push    rbp
0x18000d1fa  push    rsi
0x18000d1fb  push    rdi
0x18000d1fc  push    r14
0x18000d1fe  push    r15
0x18000d200  sub     rsp, 250h
0x18000d207  mov     rax, cs:__security_cookie
0x18000d20e  xor     rax, rsp
0x18000d211  mov     [rsp+278h+var_38], rax
0x18000d219  mov     rbx, r8
0x18000d21c  mov     rsi, rdx
0x18000d21f  mov     r14, rcx
0x18000d222  xor     r15d, r15d
0x18000d225  test    rdx, rdx
0x18000d228  jz      loc_18000D481
0x18000d22e  test    rcx, rcx
0x18000d231  jz      loc_18000D481
0x18000d237  mov     [rcx], r15w
0x18000d23b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d242  test    rax, rax
0x18000d245  jz      short loc_18000D268
0x18000d247  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000d24e  jz      short loc_18000D268
0x18000d250  mov     r8, rdx
0x18000d253  mov     rdx, rcx
0x18000d256  mov     rcx, rbx
0x18000d259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d25e  cmp     [r14], r15w
0x18000d262  jnz     loc_18000D481
0x18000d268  mov     ecx, [rbx]
0x18000d26a  mov     bpl, 8
0x18000d26d  test    ecx, ecx
0x18000d26f  jz      short loc_18000D2BA
0x18000d271  sub     ecx, 1
0x18000d274  jz      short loc_18000D2A2
0x18000d276  sub     ecx, 1
0x18000d279  jz      short loc_18000D292
0x18000d27b  cmp     ecx, 1
0x18000d27e  jz      short loc_18000D289
0x18000d280  lea     rdi, word_1800155AE
0x18000d287  jmp     short loc_18000D2C1
0x18000d289  lea     rdi, aFailfast; "FailFast"
0x18000d290  jmp     short loc_18000D2C1
0x18000d292  lea     rax, aLoghr; "LogHr"
0x18000d299  lea     rdi, aLognt; "LogNt"
0x18000d2a0  jmp     short loc_18000D2B0
0x18000d2a2  lea     rax, aReturnhr; "ReturnHr"
0x18000d2a9  lea     rdi, aReturnnt; "ReturnNt"
0x18000d2b0  test    [rbx+4], bpl
0x18000d2b4  cmovz   rdi, rax
0x18000d2b8  jmp     short loc_18000D2C1
0x18000d2ba  lea     rdi, aException; "Exception"
0x18000d2c1  xor     edx, edx; Val
0x18000d2c3  mov     r8d, 200h; Size
0x18000d2c9  lea     rcx, [rsp+278h+Buffer]; void *
0x18000d2ce  call    memset_0
0x18000d2d3  test    [rbx+4], bpl
0x18000d2d7  jz      short loc_18000D2FC
0x18000d2d9  mov     ebp, [rbx+0Ch]
0x18000d2dc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000d2e3  test    rax, rax
0x18000d2e6  jz      short loc_18000D32C
0x18000d2e8  mov     r8d, 100h
0x18000d2ee  lea     rdx, [rsp+278h+Buffer]
0x18000d2f3  mov     ecx, ebp
0x18000d2f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2fa  jmp     short loc_18000D32C
0x18000d2fc  mov     ebp, [rbx+8]
0x18000d2ff  mov     [rsp+278h+Arguments], r15; Arguments
0x18000d304  mov     [rsp+278h+nSize], 100h; nSize
0x18000d30c  lea     rax, [rsp+278h+Buffer]
0x18000d311  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000d316  mov     r9d, 400h; dwLanguageId
0x18000d31c  mov     r8d, ebp; dwMessageId
0x18000d31f  xor     edx, edx; lpSource
0x18000d321  mov     ecx, 1200h; dwFlags
0x18000d326  call    cs:__imp_FormatMessageW
0x18000d32c  lea     rsi, [r14+rsi*2]
0x18000d330  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000d334  mov     rax, [rbx+88h]
0x18000d33b  mov     rcx, [rbx+80h]
0x18000d342  mov     rdx, rsi; unsigned __int16 *
0x18000d345  test    r9, r9
0x18000d348  jz      short loc_18000D36C
0x18000d34a  mov     [rsp+278h+Arguments], rax
0x18000d34f  mov     qword ptr [rsp+278h+nSize], rcx
0x18000d354  mov     eax, [rbx+40h]
0x18000d357  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000d35b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000d362  mov     rcx, r14; this
0x18000d365  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d36a  jmp     short loc_18000D383
0x18000d36c  mov     [rsp+278h+lpBuffer], rax
0x18000d371  mov     r9, rcx; unsigned __int16 *
0x18000d374  lea     r8, aHsP; "%hs!%p: "
0x18000d37b  mov     rcx, r14; this
0x18000d37e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d383  mov     r14, rax
0x18000d386  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000d38d  test    r9, r9
0x18000d390  jz      short loc_18000D3A7
0x18000d392  lea     r8, aCallerP; "(caller: %p) "
0x18000d399  mov     rdx, rsi; unsigned __int16 *
0x18000d39c  mov     rcx, rax; this
0x18000d39f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d3a4  mov     r14, rax
0x18000d3a7  call    cs:__imp_GetCurrentThreadId
0x18000d3ad  lea     rcx, [rsp+278h+Buffer]
0x18000d3b2  mov     [rsp+278h+var_240], rcx
0x18000d3b7  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000d3bb  mov     [rsp+278h+nSize], eax
0x18000d3bf  mov     eax, [rbx+44h]
0x18000d3c2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000d3c6  mov     r9, rdi; unsigned __int16 *
0x18000d3c9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000d3d0  mov     rdx, rsi; unsigned __int16 *
0x18000d3d3  mov     rcx, r14; this
0x18000d3d6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d3db  cmp     [rbx+18h], r15
0x18000d3df  jnz     short loc_18000D3F1
0x18000d3e1  cmp     [rbx+48h], r15
0x18000d3e5  jnz     short loc_18000D3F1
0x18000d3e7  cmp     [rbx+30h], r15
0x18000d3eb  jz      loc_18000D481
0x18000d3f1  lea     r8, asc_180015698; "    "
0x18000d3f8  mov     rdx, rsi; unsigned __int16 *
0x18000d3fb  mov     rcx, rax; this
0x18000d3fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d403  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000d407  test    r9, r9
0x18000d40a  jz      short loc_18000D41E
0x18000d40c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000d413  mov     rdx, rsi; unsigned __int16 *
0x18000d416  mov     rcx, rax; this
0x18000d419  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d41e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000d422  test    r9, r9
0x18000d425  jz      short loc_18000D439
0x18000d427  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000d42e  mov     rdx, rsi; unsigned __int16 *
0x18000d431  mov     rcx, rax; this
0x18000d434  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d439  mov     rcx, [rbx+28h]
0x18000d43d  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000d441  mov     rdx, rsi; unsigned __int16 *
0x18000d444  test    rcx, rcx
0x18000d447  jz      short loc_18000D45F
0x18000d449  mov     [rsp+278h+lpBuffer], rcx
0x18000d44e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000d455  mov     rcx, rax; this
0x18000d458  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d45d  jmp     short loc_18000D481
0x18000d45f  mov     rcx, rax; this
0x18000d462  test    r9, r9
0x18000d465  jz      short loc_18000D475
0x18000d467  lea     r8, aHs; "[%hs]\n"
0x18000d46e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d473  jmp     short loc_18000D481
0x18000d475  lea     r8, asc_180015710; "\n"
0x18000d47c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d481  xor     eax, eax
0x18000d483  mov     rcx, [rsp+278h+var_38]
0x18000d48b  xor     rcx, rsp; StackCookie
0x18000d48e  call    __security_check_cookie
0x18000d493  mov     rbx, [rsp+278h+arg_18]
0x18000d49b  add     rsp, 250h
0x18000d4a2  pop     r15
0x18000d4a4  pop     r14
0x18000d4a6  pop     rdi
0x18000d4a7  pop     rsi
0x18000d4a8  pop     rbp
0x18000d4a9  retn
```
