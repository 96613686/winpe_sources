# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800046d4`
- end: `0x180004997`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180002f44`
- `0x180005110`
- `0x1800055c0`
- `0x1800077b0`

## callees

- `0x180001800`
- `0x1800023e0`
- `0x1800046d4`
- `0x180005424`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000488d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000488d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004806`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004806`

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
          v7 = (const char *)&qword_18002A440;
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
0x1800046d4  mov     [rsp+arg_18], rbx
0x1800046d9  push    rbp
0x1800046da  push    rsi
0x1800046db  push    rdi
0x1800046dc  push    r14
0x1800046de  push    r15
0x1800046e0  sub     rsp, 250h
0x1800046e7  mov     rax, cs:__security_cookie
0x1800046ee  xor     rax, rsp
0x1800046f1  mov     [rsp+278h+var_38], rax
0x1800046f9  mov     rbx, r8
0x1800046fc  mov     rsi, rdx
0x1800046ff  mov     r14, rcx
0x180004702  xor     r15d, r15d
0x180004705  test    rdx, rdx
0x180004708  jz      loc_18000496D
0x18000470e  test    rcx, rcx
0x180004711  jz      loc_18000496D
0x180004717  mov     [rcx], r15w
0x18000471b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004722  test    rax, rax
0x180004725  jz      short loc_180004748
0x180004727  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000472e  jz      short loc_180004748
0x180004730  mov     r8, rdx
0x180004733  mov     rdx, rcx
0x180004736  mov     rcx, rbx
0x180004739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000473e  cmp     [r14], r15w
0x180004742  jnz     loc_18000496D
0x180004748  mov     ecx, [rbx]
0x18000474a  mov     bpl, 8
0x18000474d  test    ecx, ecx
0x18000474f  jz      short loc_18000479A
0x180004751  sub     ecx, 1
0x180004754  jz      short loc_180004782
0x180004756  sub     ecx, 1
0x180004759  jz      short loc_180004772
0x18000475b  cmp     ecx, 1
0x18000475e  jz      short loc_180004769
0x180004760  lea     rdi, qword_18002A440
0x180004767  jmp     short loc_1800047A1
0x180004769  lea     rdi, aFailfast; "FailFast"
0x180004770  jmp     short loc_1800047A1
0x180004772  lea     rax, aLoghr; "LogHr"
0x180004779  lea     rdi, aLognt; "LogNt"
0x180004780  jmp     short loc_180004790
0x180004782  lea     rax, aReturnhr; "ReturnHr"
0x180004789  lea     rdi, aReturnnt; "ReturnNt"
0x180004790  test    [rbx+4], bpl
0x180004794  cmovz   rdi, rax
0x180004798  jmp     short loc_1800047A1
0x18000479a  lea     rdi, aException; "Exception"
0x1800047a1  xor     edx, edx; Val
0x1800047a3  mov     r8d, 200h; Size
0x1800047a9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800047ae  call    memset_0
0x1800047b3  test    [rbx+4], bpl
0x1800047b7  jz      short loc_1800047DC
0x1800047b9  mov     ebp, [rbx+0Ch]
0x1800047bc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800047c3  test    rax, rax
0x1800047c6  jz      short loc_180004812
0x1800047c8  mov     r8d, 100h
0x1800047ce  lea     rdx, [rsp+278h+Buffer]
0x1800047d3  mov     ecx, ebp
0x1800047d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047da  jmp     short loc_180004812
0x1800047dc  mov     ebp, [rbx+8]
0x1800047df  mov     [rsp+278h+Arguments], r15; Arguments
0x1800047e4  mov     [rsp+278h+nSize], 100h; nSize
0x1800047ec  lea     rax, [rsp+278h+Buffer]
0x1800047f1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800047f6  mov     r9d, 400h; dwLanguageId
0x1800047fc  mov     r8d, ebp; dwMessageId
0x1800047ff  xor     edx, edx; lpSource
0x180004801  mov     ecx, 1200h; dwFlags
0x180004806  call    cs:__imp_FormatMessageW
0x18000480d  nop     dword ptr [rax+rax+00h]
0x180004812  lea     rsi, [r14+rsi*2]
0x180004816  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000481a  mov     rax, [rbx+88h]
0x180004821  mov     rcx, [rbx+80h]
0x180004828  mov     rdx, rsi; unsigned __int16 *
0x18000482b  test    r9, r9
0x18000482e  jz      short loc_180004852
0x180004830  mov     [rsp+278h+Arguments], rax
0x180004835  mov     qword ptr [rsp+278h+nSize], rcx
0x18000483a  mov     eax, [rbx+40h]
0x18000483d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004841  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004848  mov     rcx, r14; this
0x18000484b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004850  jmp     short loc_180004869
0x180004852  mov     [rsp+278h+lpBuffer], rax
0x180004857  mov     r9, rcx; unsigned __int16 *
0x18000485a  lea     r8, aHsP; "%hs!%p: "
0x180004861  mov     rcx, r14; this
0x180004864  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004869  mov     r14, rax
0x18000486c  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004873  test    r9, r9
0x180004876  jz      short loc_18000488D
0x180004878  lea     r8, aCallerP; "(caller: %p) "
0x18000487f  mov     rdx, rsi; unsigned __int16 *
0x180004882  mov     rcx, rax; this
0x180004885  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000488a  mov     r14, rax
0x18000488d  call    cs:__imp_GetCurrentThreadId
0x180004894  nop     dword ptr [rax+rax+00h]
0x180004899  lea     rcx, [rsp+278h+Buffer]
0x18000489e  mov     [rsp+278h+var_240], rcx
0x1800048a3  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800048a7  mov     [rsp+278h+nSize], eax
0x1800048ab  mov     eax, [rbx+44h]
0x1800048ae  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800048b2  mov     r9, rdi; unsigned __int16 *
0x1800048b5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800048bc  mov     rdx, rsi; unsigned __int16 *
0x1800048bf  mov     rcx, r14; this
0x1800048c2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800048c7  cmp     [rbx+18h], r15
0x1800048cb  jnz     short loc_1800048DD
0x1800048cd  cmp     [rbx+48h], r15
0x1800048d1  jnz     short loc_1800048DD
0x1800048d3  cmp     [rbx+30h], r15
0x1800048d7  jz      loc_18000496D
0x1800048dd  lea     r8, asc_18002A530; "    "
0x1800048e4  mov     rdx, rsi; unsigned __int16 *
0x1800048e7  mov     rcx, rax; this
0x1800048ea  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800048ef  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800048f3  test    r9, r9
0x1800048f6  jz      short loc_18000490A
0x1800048f8  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800048ff  mov     rdx, rsi; unsigned __int16 *
0x180004902  mov     rcx, rax; this
0x180004905  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000490a  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000490e  test    r9, r9
0x180004911  jz      short loc_180004925
0x180004913  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000491a  mov     rdx, rsi; unsigned __int16 *
0x18000491d  mov     rcx, rax; this
0x180004920  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004925  mov     rcx, [rbx+28h]
0x180004929  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000492d  mov     rdx, rsi; unsigned __int16 *
0x180004930  test    rcx, rcx
0x180004933  jz      short loc_18000494B
0x180004935  mov     [rsp+278h+lpBuffer], rcx
0x18000493a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004941  mov     rcx, rax; this
0x180004944  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004949  jmp     short loc_18000496D
0x18000494b  mov     rcx, rax; this
0x18000494e  test    r9, r9
0x180004951  jz      short loc_180004961
0x180004953  lea     r8, aHs; "[%hs]\n"
0x18000495a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000495f  jmp     short loc_18000496D
0x180004961  lea     r8, asc_18002A5A8; "\n"
0x180004968  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000496d  xor     eax, eax
0x18000496f  mov     rcx, [rsp+278h+var_38]
0x180004977  xor     rcx, rsp; StackCookie
0x18000497a  call    __security_check_cookie
0x18000497f  mov     rbx, [rsp+278h+arg_18]
0x180004987  add     rsp, 250h
0x18000498e  pop     r15
0x180004990  pop     r14
0x180004992  pop     rdi
0x180004993  pop     rsi
0x180004994  pop     rbp
0x180004995  retn
```
