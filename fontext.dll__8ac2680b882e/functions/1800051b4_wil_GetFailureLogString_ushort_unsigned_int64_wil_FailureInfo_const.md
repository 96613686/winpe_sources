# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800051b4`
- end: `0x18000546a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180004550`
- `0x180005b98`

## callees

- `0x1800051b4`
- `0x180005e9c`
- `0x18003104a`
- `0x180031070`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005367`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005367`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800052e6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800052e6`

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
          v8 = (const char *)&byte_180037621;
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
0x1800051b4  mov     [rsp+arg_18], rbx
0x1800051b9  push    rbp
0x1800051ba  push    rsi
0x1800051bb  push    rdi
0x1800051bc  push    r14
0x1800051be  push    r15
0x1800051c0  sub     rsp, 250h
0x1800051c7  mov     rax, cs:__security_cookie
0x1800051ce  xor     rax, rsp
0x1800051d1  mov     [rsp+278h+var_38], rax
0x1800051d9  xor     r15d, r15d
0x1800051dc  mov     rbx, r8
0x1800051df  mov     rsi, rdx
0x1800051e2  mov     r14, rcx
0x1800051e5  test    rdx, rdx
0x1800051e8  jz      loc_180005441
0x1800051ee  test    rcx, rcx
0x1800051f1  jz      loc_180005441
0x1800051f7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800051fe  mov     [rcx], r15w
0x180005202  test    rax, rax
0x180005205  jz      short loc_180005228
0x180005207  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000520e  jz      short loc_180005228
0x180005210  mov     r8, rdx
0x180005213  mov     rdx, rcx
0x180005216  mov     rcx, rbx
0x180005219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000521e  cmp     [r14], r15w
0x180005222  jnz     loc_180005441
0x180005228  mov     ecx, [rbx]
0x18000522a  mov     bpl, 8
0x18000522d  test    ecx, ecx
0x18000522f  jz      short loc_18000527A
0x180005231  sub     ecx, 1
0x180005234  jz      short loc_180005262
0x180005236  sub     ecx, 1
0x180005239  jz      short loc_180005252
0x18000523b  cmp     ecx, 1
0x18000523e  jz      short loc_180005249
0x180005240  lea     rdi, byte_180037621
0x180005247  jmp     short loc_180005281
0x180005249  lea     rdi, aFailfast; "FailFast"
0x180005250  jmp     short loc_180005281
0x180005252  lea     rax, aLoghr; "LogHr"
0x180005259  lea     rdi, aLognt; "LogNt"
0x180005260  jmp     short loc_180005270
0x180005262  lea     rax, aReturnhr; "ReturnHr"
0x180005269  lea     rdi, aReturnnt; "ReturnNt"
0x180005270  test    [rbx+4], bpl
0x180005274  cmovz   rdi, rax
0x180005278  jmp     short loc_180005281
0x18000527a  lea     rdi, aException; "Exception"
0x180005281  xor     edx, edx; Val
0x180005283  lea     rcx, [rsp+278h+Buffer]; void *
0x180005288  mov     r8d, 200h; Size
0x18000528e  call    memset_0
0x180005293  test    [rbx+4], bpl
0x180005297  jz      short loc_1800052BC
0x180005299  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800052a0  mov     ebp, [rbx+0Ch]
0x1800052a3  test    rax, rax
0x1800052a6  jz      short loc_1800052EC
0x1800052a8  mov     r8d, 100h
0x1800052ae  lea     rdx, [rsp+278h+Buffer]
0x1800052b3  mov     ecx, ebp
0x1800052b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052ba  jmp     short loc_1800052EC
0x1800052bc  mov     ebp, [rbx+8]
0x1800052bf  lea     rax, [rsp+278h+Buffer]
0x1800052c4  mov     [rsp+278h+Arguments], r15; Arguments
0x1800052c9  mov     r8d, ebp; dwMessageId
0x1800052cc  mov     [rsp+278h+nSize], 100h; nSize
0x1800052d4  mov     r9d, 400h; dwLanguageId
0x1800052da  xor     edx, edx; lpSource
0x1800052dc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800052e1  mov     ecx, 1200h; dwFlags
0x1800052e6  call    cs:__imp_FormatMessageW
0x1800052ec  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800052f0  lea     rsi, [r14+rsi*2]
0x1800052f4  mov     rax, [rbx+88h]
0x1800052fb  mov     rdx, rsi; unsigned __int16 *
0x1800052fe  mov     rcx, [rbx+80h]
0x180005305  test    r9, r9
0x180005308  jz      short loc_18000532C
0x18000530a  mov     [rsp+278h+Arguments], rax
0x18000530f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005316  mov     eax, [rbx+40h]
0x180005319  mov     qword ptr [rsp+278h+nSize], rcx
0x18000531e  mov     rcx, r14; this
0x180005321  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005325  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000532a  jmp     short loc_180005343
0x18000532c  mov     r9, rcx; unsigned __int16 *
0x18000532f  mov     [rsp+278h+lpBuffer], rax
0x180005334  mov     rcx, r14; this
0x180005337  lea     r8, aHsP; "%hs!%p: "
0x18000533e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005343  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000534a  mov     r14, rax
0x18000534d  test    r9, r9
0x180005350  jz      short loc_180005367
0x180005352  lea     r8, aCallerP; "(caller: %p) "
0x180005359  mov     rdx, rsi; unsigned __int16 *
0x18000535c  mov     rcx, rax; this
0x18000535f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005364  mov     r14, rax
0x180005367  call    cs:__imp_GetCurrentThreadId
0x18000536d  lea     rcx, [rsp+278h+Buffer]
0x180005372  mov     r9, rdi; unsigned __int16 *
0x180005375  mov     [rsp+278h+var_240], rcx
0x18000537a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005381  mov     dword ptr [rsp+278h+Arguments], ebp
0x180005385  mov     rdx, rsi; unsigned __int16 *
0x180005388  mov     [rsp+278h+nSize], eax
0x18000538c  mov     rcx, r14; this
0x18000538f  mov     eax, [rbx+44h]
0x180005392  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005396  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000539b  cmp     [rbx+18h], r15
0x18000539f  jnz     short loc_1800053B1
0x1800053a1  cmp     [rbx+48h], r15
0x1800053a5  jnz     short loc_1800053B1
0x1800053a7  cmp     [rbx+30h], r15
0x1800053ab  jz      loc_180005441
0x1800053b1  lea     r8, asc_180037710; "    "
0x1800053b8  mov     rdx, rsi; unsigned __int16 *
0x1800053bb  mov     rcx, rax; this
0x1800053be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800053c3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800053c7  test    r9, r9
0x1800053ca  jz      short loc_1800053DE
0x1800053cc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800053d3  mov     rdx, rsi; unsigned __int16 *
0x1800053d6  mov     rcx, rax; this
0x1800053d9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800053de  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800053e2  test    r9, r9
0x1800053e5  jz      short loc_1800053F9
0x1800053e7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800053ee  mov     rdx, rsi; unsigned __int16 *
0x1800053f1  mov     rcx, rax; this
0x1800053f4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800053f9  mov     rcx, [rbx+28h]
0x1800053fd  mov     rdx, rsi; unsigned __int16 *
0x180005400  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005404  test    rcx, rcx
0x180005407  jz      short loc_18000541F
0x180005409  mov     [rsp+278h+lpBuffer], rcx
0x18000540e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005415  mov     rcx, rax; this
0x180005418  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000541d  jmp     short loc_180005441
0x18000541f  mov     rcx, rax; this
0x180005422  test    r9, r9
0x180005425  jz      short loc_180005435
0x180005427  lea     r8, aHs; "[%hs]\n"
0x18000542e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005433  jmp     short loc_180005441
0x180005435  lea     r8, asc_180037788; "\n"
0x18000543c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005441  xor     eax, eax
0x180005443  mov     rcx, [rsp+278h+var_38]
0x18000544b  xor     rcx, rsp; StackCookie
0x18000544e  call    __security_check_cookie
0x180005453  mov     rbx, [rsp+278h+arg_18]
0x18000545b  add     rsp, 250h
0x180005462  pop     r15
0x180005464  pop     r14
0x180005466  pop     rdi
0x180005467  pop     rsi
0x180005468  pop     rbp
0x180005469  retn
```
