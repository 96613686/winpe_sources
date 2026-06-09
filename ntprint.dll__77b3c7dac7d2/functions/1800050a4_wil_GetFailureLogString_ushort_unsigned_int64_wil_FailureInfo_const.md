# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800050a4`
- end: `0x18000535a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800038dc`
- `0x180005bec`
- `0x180038900`

## callees

- `0x180002300`
- `0x180002f48`
- `0x1800050a4`
- `0x180005eec`
- `0x18003a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005257`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005257`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800051d6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800051d6`

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
          v8 = (const char *)&dword_18003C41C;
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
0x1800050a4  mov     [rsp+arg_18], rbx
0x1800050a9  push    rbp
0x1800050aa  push    rsi
0x1800050ab  push    rdi
0x1800050ac  push    r14
0x1800050ae  push    r15
0x1800050b0  sub     rsp, 250h
0x1800050b7  mov     rax, cs:__security_cookie
0x1800050be  xor     rax, rsp
0x1800050c1  mov     [rsp+278h+var_38], rax
0x1800050c9  xor     r15d, r15d
0x1800050cc  mov     rbx, r8
0x1800050cf  mov     rsi, rdx
0x1800050d2  mov     r14, rcx
0x1800050d5  test    rdx, rdx
0x1800050d8  jz      loc_180005331
0x1800050de  test    rcx, rcx
0x1800050e1  jz      loc_180005331
0x1800050e7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800050ee  mov     [rcx], r15w
0x1800050f2  test    rax, rax
0x1800050f5  jz      short loc_180005118
0x1800050f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800050fe  jz      short loc_180005118
0x180005100  mov     r8, rdx
0x180005103  mov     rdx, rcx
0x180005106  mov     rcx, rbx
0x180005109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000510e  cmp     [r14], r15w
0x180005112  jnz     loc_180005331
0x180005118  mov     ecx, [rbx]
0x18000511a  mov     bpl, 8
0x18000511d  test    ecx, ecx
0x18000511f  jz      short loc_18000516A
0x180005121  sub     ecx, 1
0x180005124  jz      short loc_180005152
0x180005126  sub     ecx, 1
0x180005129  jz      short loc_180005142
0x18000512b  cmp     ecx, 1
0x18000512e  jz      short loc_180005139
0x180005130  lea     rdi, dword_18003C41C
0x180005137  jmp     short loc_180005171
0x180005139  lea     rdi, aFailfast; "FailFast"
0x180005140  jmp     short loc_180005171
0x180005142  lea     rax, aLoghr; "LogHr"
0x180005149  lea     rdi, aLognt; "LogNt"
0x180005150  jmp     short loc_180005160
0x180005152  lea     rax, aReturnhr; "ReturnHr"
0x180005159  lea     rdi, aReturnnt; "ReturnNt"
0x180005160  test    [rbx+4], bpl
0x180005164  cmovz   rdi, rax
0x180005168  jmp     short loc_180005171
0x18000516a  lea     rdi, aException; "Exception"
0x180005171  xor     edx, edx; Val
0x180005173  lea     rcx, [rsp+278h+Buffer]; void *
0x180005178  mov     r8d, 200h; Size
0x18000517e  call    memset_0
0x180005183  test    [rbx+4], bpl
0x180005187  jz      short loc_1800051AC
0x180005189  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005190  mov     ebp, [rbx+0Ch]
0x180005193  test    rax, rax
0x180005196  jz      short loc_1800051DC
0x180005198  mov     r8d, 100h
0x18000519e  lea     rdx, [rsp+278h+Buffer]
0x1800051a3  mov     ecx, ebp
0x1800051a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051aa  jmp     short loc_1800051DC
0x1800051ac  mov     ebp, [rbx+8]
0x1800051af  lea     rax, [rsp+278h+Buffer]
0x1800051b4  mov     [rsp+278h+Arguments], r15; Arguments
0x1800051b9  mov     r8d, ebp; dwMessageId
0x1800051bc  mov     [rsp+278h+nSize], 100h; nSize
0x1800051c4  mov     r9d, 400h; dwLanguageId
0x1800051ca  xor     edx, edx; lpSource
0x1800051cc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800051d1  mov     ecx, 1200h; dwFlags
0x1800051d6  call    cs:__imp_FormatMessageW
0x1800051dc  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800051e0  lea     rsi, [r14+rsi*2]
0x1800051e4  mov     rax, [rbx+88h]
0x1800051eb  mov     rdx, rsi; unsigned __int16 *
0x1800051ee  mov     rcx, [rbx+80h]
0x1800051f5  test    r9, r9
0x1800051f8  jz      short loc_18000521C
0x1800051fa  mov     [rsp+278h+Arguments], rax
0x1800051ff  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005206  mov     eax, [rbx+40h]
0x180005209  mov     qword ptr [rsp+278h+nSize], rcx
0x18000520e  mov     rcx, r14; this
0x180005211  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005215  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000521a  jmp     short loc_180005233
0x18000521c  mov     r9, rcx; unsigned __int16 *
0x18000521f  mov     [rsp+278h+lpBuffer], rax
0x180005224  mov     rcx, r14; this
0x180005227  lea     r8, aHsP; "%hs!%p: "
0x18000522e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005233  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000523a  mov     r14, rax
0x18000523d  test    r9, r9
0x180005240  jz      short loc_180005257
0x180005242  lea     r8, aCallerP; "(caller: %p) "
0x180005249  mov     rdx, rsi; unsigned __int16 *
0x18000524c  mov     rcx, rax; this
0x18000524f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005254  mov     r14, rax
0x180005257  call    cs:__imp_GetCurrentThreadId
0x18000525d  lea     rcx, [rsp+278h+Buffer]
0x180005262  mov     r9, rdi; unsigned __int16 *
0x180005265  mov     [rsp+278h+var_240], rcx
0x18000526a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005271  mov     dword ptr [rsp+278h+Arguments], ebp
0x180005275  mov     rdx, rsi; unsigned __int16 *
0x180005278  mov     [rsp+278h+nSize], eax
0x18000527c  mov     rcx, r14; this
0x18000527f  mov     eax, [rbx+44h]
0x180005282  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005286  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000528b  cmp     [rbx+18h], r15
0x18000528f  jnz     short loc_1800052A1
0x180005291  cmp     [rbx+48h], r15
0x180005295  jnz     short loc_1800052A1
0x180005297  cmp     [rbx+30h], r15
0x18000529b  jz      loc_180005331
0x1800052a1  lea     r8, asc_18003C510; "    "
0x1800052a8  mov     rdx, rsi; unsigned __int16 *
0x1800052ab  mov     rcx, rax; this
0x1800052ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800052b3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800052b7  test    r9, r9
0x1800052ba  jz      short loc_1800052CE
0x1800052bc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800052c3  mov     rdx, rsi; unsigned __int16 *
0x1800052c6  mov     rcx, rax; this
0x1800052c9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800052ce  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800052d2  test    r9, r9
0x1800052d5  jz      short loc_1800052E9
0x1800052d7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800052de  mov     rdx, rsi; unsigned __int16 *
0x1800052e1  mov     rcx, rax; this
0x1800052e4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800052e9  mov     rcx, [rbx+28h]
0x1800052ed  mov     rdx, rsi; unsigned __int16 *
0x1800052f0  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800052f4  test    rcx, rcx
0x1800052f7  jz      short loc_18000530F
0x1800052f9  mov     [rsp+278h+lpBuffer], rcx
0x1800052fe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005305  mov     rcx, rax; this
0x180005308  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000530d  jmp     short loc_180005331
0x18000530f  mov     rcx, rax; this
0x180005312  test    r9, r9
0x180005315  jz      short loc_180005325
0x180005317  lea     r8, aHs; "[%hs]\n"
0x18000531e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005323  jmp     short loc_180005331
0x180005325  lea     r8, asc_18003C588; "\n"
0x18000532c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005331  xor     eax, eax
0x180005333  mov     rcx, [rsp+278h+var_38]
0x18000533b  xor     rcx, rsp; StackCookie
0x18000533e  call    __security_check_cookie
0x180005343  mov     rbx, [rsp+278h+arg_18]
0x18000534b  add     rsp, 250h
0x180005352  pop     r15
0x180005354  pop     r14
0x180005356  pop     rdi
0x180005357  pop     rsi
0x180005358  pop     rbp
0x180005359  retn
```
