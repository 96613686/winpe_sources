# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180027194`
- end: `0x18002744a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180025dd0`
- `0x180027aa0`

## callees

- `0x18001b334`
- `0x18001b7e0`
- `0x18001c10c`
- `0x180027194`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027347`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027347`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800272c6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800272c6`

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
          v8 = (const char *)&qword_180035DE8;
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
0x180027194  mov     [rsp+arg_18], rbx
0x180027199  push    rbp
0x18002719a  push    rsi
0x18002719b  push    rdi
0x18002719c  push    r14
0x18002719e  push    r15
0x1800271a0  sub     rsp, 250h
0x1800271a7  mov     rax, cs:__security_cookie
0x1800271ae  xor     rax, rsp
0x1800271b1  mov     [rsp+278h+var_38], rax
0x1800271b9  xor     r15d, r15d
0x1800271bc  mov     rbx, r8
0x1800271bf  mov     rsi, rdx
0x1800271c2  mov     r14, rcx
0x1800271c5  test    rdx, rdx
0x1800271c8  jz      loc_180027421
0x1800271ce  test    rcx, rcx
0x1800271d1  jz      loc_180027421
0x1800271d7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800271de  mov     [rcx], r15w
0x1800271e2  test    rax, rax
0x1800271e5  jz      short loc_180027208
0x1800271e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800271ee  jz      short loc_180027208
0x1800271f0  mov     r8, rdx
0x1800271f3  mov     rdx, rcx
0x1800271f6  mov     rcx, rbx
0x1800271f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271fe  cmp     [r14], r15w
0x180027202  jnz     loc_180027421
0x180027208  mov     ecx, [rbx]
0x18002720a  mov     bpl, 8
0x18002720d  test    ecx, ecx
0x18002720f  jz      short loc_18002725A
0x180027211  sub     ecx, 1
0x180027214  jz      short loc_180027242
0x180027216  sub     ecx, 1
0x180027219  jz      short loc_180027232
0x18002721b  cmp     ecx, 1
0x18002721e  jz      short loc_180027229
0x180027220  lea     rdi, qword_180035DE8
0x180027227  jmp     short loc_180027261
0x180027229  lea     rdi, aFailfast; "FailFast"
0x180027230  jmp     short loc_180027261
0x180027232  lea     rax, aLoghr; "LogHr"
0x180027239  lea     rdi, aLognt; "LogNt"
0x180027240  jmp     short loc_180027250
0x180027242  lea     rax, aReturnhr; "ReturnHr"
0x180027249  lea     rdi, aReturnnt; "ReturnNt"
0x180027250  test    [rbx+4], bpl
0x180027254  cmovz   rdi, rax
0x180027258  jmp     short loc_180027261
0x18002725a  lea     rdi, aException; "Exception"
0x180027261  xor     edx, edx; Val
0x180027263  lea     rcx, [rsp+278h+Buffer]; void *
0x180027268  mov     r8d, 200h; Size
0x18002726e  call    memset_0
0x180027273  test    [rbx+4], bpl
0x180027277  jz      short loc_18002729C
0x180027279  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180027280  mov     ebp, [rbx+0Ch]
0x180027283  test    rax, rax
0x180027286  jz      short loc_1800272CC
0x180027288  mov     r8d, 100h
0x18002728e  lea     rdx, [rsp+278h+Buffer]
0x180027293  mov     ecx, ebp
0x180027295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002729a  jmp     short loc_1800272CC
0x18002729c  mov     ebp, [rbx+8]
0x18002729f  lea     rax, [rsp+278h+Buffer]
0x1800272a4  mov     [rsp+278h+Arguments], r15; Arguments
0x1800272a9  mov     r8d, ebp; dwMessageId
0x1800272ac  mov     [rsp+278h+nSize], 100h; nSize
0x1800272b4  mov     r9d, 400h; dwLanguageId
0x1800272ba  xor     edx, edx; lpSource
0x1800272bc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800272c1  mov     ecx, 1200h; dwFlags
0x1800272c6  call    cs:__imp_FormatMessageW
0x1800272cc  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800272d0  lea     rsi, [r14+rsi*2]
0x1800272d4  mov     rax, [rbx+88h]
0x1800272db  mov     rdx, rsi; unsigned __int16 *
0x1800272de  mov     rcx, [rbx+80h]
0x1800272e5  test    r9, r9
0x1800272e8  jz      short loc_18002730C
0x1800272ea  mov     [rsp+278h+Arguments], rax
0x1800272ef  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800272f6  mov     eax, [rbx+40h]
0x1800272f9  mov     qword ptr [rsp+278h+nSize], rcx
0x1800272fe  mov     rcx, r14; this
0x180027301  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180027305  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002730a  jmp     short loc_180027323
0x18002730c  mov     r9, rcx; unsigned __int16 *
0x18002730f  mov     [rsp+278h+lpBuffer], rax
0x180027314  mov     rcx, r14; this
0x180027317  lea     r8, aHsP; "%hs!%p: "
0x18002731e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180027323  mov     r9, [rbx+90h]; unsigned __int16 *
0x18002732a  mov     r14, rax
0x18002732d  test    r9, r9
0x180027330  jz      short loc_180027347
0x180027332  lea     r8, aCallerP; "(caller: %p) "
0x180027339  mov     rdx, rsi; unsigned __int16 *
0x18002733c  mov     rcx, rax; this
0x18002733f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180027344  mov     r14, rax
0x180027347  call    cs:__imp_GetCurrentThreadId
0x18002734d  lea     rcx, [rsp+278h+Buffer]
0x180027352  mov     r9, rdi; unsigned __int16 *
0x180027355  mov     [rsp+278h+var_240], rcx
0x18002735a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180027361  mov     dword ptr [rsp+278h+Arguments], ebp
0x180027365  mov     rdx, rsi; unsigned __int16 *
0x180027368  mov     [rsp+278h+nSize], eax
0x18002736c  mov     rcx, r14; this
0x18002736f  mov     eax, [rbx+44h]
0x180027372  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180027376  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002737b  cmp     [rbx+18h], r15
0x18002737f  jnz     short loc_180027391
0x180027381  cmp     [rbx+48h], r15
0x180027385  jnz     short loc_180027391
0x180027387  cmp     [rbx+30h], r15
0x18002738b  jz      loc_180027421
0x180027391  lea     r8, asc_180035ED8; "    "
0x180027398  mov     rdx, rsi; unsigned __int16 *
0x18002739b  mov     rcx, rax; this
0x18002739e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800273a3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800273a7  test    r9, r9
0x1800273aa  jz      short loc_1800273BE
0x1800273ac  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800273b3  mov     rdx, rsi; unsigned __int16 *
0x1800273b6  mov     rcx, rax; this
0x1800273b9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800273be  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800273c2  test    r9, r9
0x1800273c5  jz      short loc_1800273D9
0x1800273c7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800273ce  mov     rdx, rsi; unsigned __int16 *
0x1800273d1  mov     rcx, rax; this
0x1800273d4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800273d9  mov     rcx, [rbx+28h]
0x1800273dd  mov     rdx, rsi; unsigned __int16 *
0x1800273e0  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800273e4  test    rcx, rcx
0x1800273e7  jz      short loc_1800273FF
0x1800273e9  mov     [rsp+278h+lpBuffer], rcx
0x1800273ee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800273f5  mov     rcx, rax; this
0x1800273f8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800273fd  jmp     short loc_180027421
0x1800273ff  mov     rcx, rax; this
0x180027402  test    r9, r9
0x180027405  jz      short loc_180027415
0x180027407  lea     r8, aHs; "[%hs]\n"
0x18002740e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180027413  jmp     short loc_180027421
0x180027415  lea     r8, asc_180035F50; "\n"
0x18002741c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180027421  xor     eax, eax
0x180027423  mov     rcx, [rsp+278h+var_38]
0x18002742b  xor     rcx, rsp; StackCookie
0x18002742e  call    __security_check_cookie
0x180027433  mov     rbx, [rsp+278h+arg_18]
0x18002743b  add     rsp, 250h
0x180027442  pop     r15
0x180027444  pop     r14
0x180027446  pop     rdi
0x180027447  pop     rsi
0x180027448  pop     rbp
0x180027449  retn
```
