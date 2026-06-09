# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140004794`
- end: `0x140004a4a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140003868`
- `0x140005174`
- `0x1400067a0`

## callees

- `0x1400029a0`
- `0x140003390`
- `0x140004794`
- `0x140005474`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400048c6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400048c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004947`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004947`

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
          v7 = (const char *)&qword_14001A178;
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
0x140004794  mov     [rsp+arg_18], rbx
0x140004799  push    rbp
0x14000479a  push    rsi
0x14000479b  push    rdi
0x14000479c  push    r14
0x14000479e  push    r15
0x1400047a0  sub     rsp, 250h
0x1400047a7  mov     rax, cs:__security_cookie
0x1400047ae  xor     rax, rsp
0x1400047b1  mov     [rsp+278h+var_38], rax
0x1400047b9  mov     rbx, r8
0x1400047bc  mov     rsi, rdx
0x1400047bf  mov     r14, rcx
0x1400047c2  xor     r15d, r15d
0x1400047c5  test    rdx, rdx
0x1400047c8  jz      loc_140004A21
0x1400047ce  test    rcx, rcx
0x1400047d1  jz      loc_140004A21
0x1400047d7  mov     [rcx], r15w
0x1400047db  mov     rax, cs:g_pfnResultLoggingCallback
0x1400047e2  test    rax, rax
0x1400047e5  jz      short loc_140004808
0x1400047e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400047ee  jz      short loc_140004808
0x1400047f0  mov     r8, rdx
0x1400047f3  mov     rdx, rcx
0x1400047f6  mov     rcx, rbx
0x1400047f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400047fe  cmp     [r14], r15w
0x140004802  jnz     loc_140004A21
0x140004808  mov     ecx, [rbx]
0x14000480a  mov     bpl, 8
0x14000480d  test    ecx, ecx
0x14000480f  jz      short loc_14000485A
0x140004811  sub     ecx, 1
0x140004814  jz      short loc_140004842
0x140004816  sub     ecx, 1
0x140004819  jz      short loc_140004832
0x14000481b  cmp     ecx, 1
0x14000481e  jz      short loc_140004829
0x140004820  lea     rdi, qword_14001A178
0x140004827  jmp     short loc_140004861
0x140004829  lea     rdi, aFailfast; "FailFast"
0x140004830  jmp     short loc_140004861
0x140004832  lea     rax, aLoghr; "LogHr"
0x140004839  lea     rdi, aLognt; "LogNt"
0x140004840  jmp     short loc_140004850
0x140004842  lea     rax, aReturnhr; "ReturnHr"
0x140004849  lea     rdi, aReturnnt; "ReturnNt"
0x140004850  test    [rbx+4], bpl
0x140004854  cmovz   rdi, rax
0x140004858  jmp     short loc_140004861
0x14000485a  lea     rdi, aException; "Exception"
0x140004861  xor     edx, edx; Val
0x140004863  mov     r8d, 200h; Size
0x140004869  lea     rcx, [rsp+278h+Buffer]; void *
0x14000486e  call    memset_0
0x140004873  test    [rbx+4], bpl
0x140004877  jz      short loc_14000489C
0x140004879  mov     ebp, [rbx+0Ch]
0x14000487c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140004883  test    rax, rax
0x140004886  jz      short loc_1400048CC
0x140004888  mov     r8d, 100h
0x14000488e  lea     rdx, [rsp+278h+Buffer]
0x140004893  mov     ecx, ebp
0x140004895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000489a  jmp     short loc_1400048CC
0x14000489c  mov     ebp, [rbx+8]
0x14000489f  mov     [rsp+278h+Arguments], r15; Arguments
0x1400048a4  mov     [rsp+278h+nSize], 100h; nSize
0x1400048ac  lea     rax, [rsp+278h+Buffer]
0x1400048b1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1400048b6  mov     r9d, 400h; dwLanguageId
0x1400048bc  mov     r8d, ebp; dwMessageId
0x1400048bf  xor     edx, edx; lpSource
0x1400048c1  mov     ecx, 1200h; dwFlags
0x1400048c6  call    cs:__imp_FormatMessageW
0x1400048cc  lea     rsi, [r14+rsi*2]
0x1400048d0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1400048d4  mov     rax, [rbx+88h]
0x1400048db  mov     rcx, [rbx+80h]
0x1400048e2  mov     rdx, rsi; unsigned __int16 *
0x1400048e5  test    r9, r9
0x1400048e8  jz      short loc_14000490C
0x1400048ea  mov     [rsp+278h+Arguments], rax
0x1400048ef  mov     qword ptr [rsp+278h+nSize], rcx
0x1400048f4  mov     eax, [rbx+40h]
0x1400048f7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400048fb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140004902  mov     rcx, r14; this
0x140004905  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000490a  jmp     short loc_140004923
0x14000490c  mov     [rsp+278h+lpBuffer], rax
0x140004911  mov     r9, rcx; unsigned __int16 *
0x140004914  lea     r8, aHsP; "%hs!%p: "
0x14000491b  mov     rcx, r14; this
0x14000491e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004923  mov     r14, rax
0x140004926  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000492d  test    r9, r9
0x140004930  jz      short loc_140004947
0x140004932  lea     r8, aCallerP; "(caller: %p) "
0x140004939  mov     rdx, rsi; unsigned __int16 *
0x14000493c  mov     rcx, rax; this
0x14000493f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004944  mov     r14, rax
0x140004947  call    cs:__imp_GetCurrentThreadId
0x14000494d  lea     rcx, [rsp+278h+Buffer]
0x140004952  mov     [rsp+278h+var_240], rcx
0x140004957  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000495b  mov     [rsp+278h+nSize], eax
0x14000495f  mov     eax, [rbx+44h]
0x140004962  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140004966  mov     r9, rdi; unsigned __int16 *
0x140004969  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140004970  mov     rdx, rsi; unsigned __int16 *
0x140004973  mov     rcx, r14; this
0x140004976  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000497b  cmp     [rbx+18h], r15
0x14000497f  jnz     short loc_140004991
0x140004981  cmp     [rbx+48h], r15
0x140004985  jnz     short loc_140004991
0x140004987  cmp     [rbx+30h], r15
0x14000498b  jz      loc_140004A21
0x140004991  lea     r8, asc_140019EA8; "    "
0x140004998  mov     rdx, rsi; unsigned __int16 *
0x14000499b  mov     rcx, rax; this
0x14000499e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400049a3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1400049a7  test    r9, r9
0x1400049aa  jz      short loc_1400049BE
0x1400049ac  lea     r8, aMsgWs; "Msg:[%ws] "
0x1400049b3  mov     rdx, rsi; unsigned __int16 *
0x1400049b6  mov     rcx, rax; this
0x1400049b9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400049be  mov     r9, [rbx+48h]; unsigned __int16 *
0x1400049c2  test    r9, r9
0x1400049c5  jz      short loc_1400049D9
0x1400049c7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1400049ce  mov     rdx, rsi; unsigned __int16 *
0x1400049d1  mov     rcx, rax; this
0x1400049d4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400049d9  mov     rcx, [rbx+28h]
0x1400049dd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1400049e1  mov     rdx, rsi; unsigned __int16 *
0x1400049e4  test    rcx, rcx
0x1400049e7  jz      short loc_1400049FF
0x1400049e9  mov     [rsp+278h+lpBuffer], rcx
0x1400049ee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1400049f5  mov     rcx, rax; this
0x1400049f8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400049fd  jmp     short loc_140004A21
0x1400049ff  mov     rcx, rax; this
0x140004a02  test    r9, r9
0x140004a05  jz      short loc_140004A15
0x140004a07  lea     r8, aHs; "[%hs]\n"
0x140004a0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004a13  jmp     short loc_140004A21
0x140004a15  lea     r8, asc_140019F20; "\n"
0x140004a1c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004a21  xor     eax, eax
0x140004a23  mov     rcx, [rsp+278h+var_38]
0x140004a2b  xor     rcx, rsp; StackCookie
0x140004a2e  call    __security_check_cookie
0x140004a33  mov     rbx, [rsp+278h+arg_18]
0x140004a3b  add     rsp, 250h
0x140004a42  pop     r15
0x140004a44  pop     r14
0x140004a46  pop     rdi
0x140004a47  pop     rsi
0x140004a48  pop     rbp
0x140004a49  retn
```
