# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140005024`
- end: `0x1400052da`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140003054`
- `0x1400032c4`
- `0x140006cd4`

## callees

- `0x140001fa0`
- `0x140002bc6`
- `0x140005024`
- `0x140006fd4`
- `0x140010010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400051d7`
- `KERNEL32!GetCurrentThreadId` at `0x1400051d7`
- `KERNEL32!FormatMessageW` at `0x140005156`
- `KERNEL32!FormatMessageW` at `0x140005156`

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
          v8 = (const char *)&word_14001269A;
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
0x140005024  mov     [rsp+arg_18], rbx
0x140005029  push    rbp
0x14000502a  push    rsi
0x14000502b  push    rdi
0x14000502c  push    r14
0x14000502e  push    r15
0x140005030  sub     rsp, 250h
0x140005037  mov     rax, cs:__security_cookie
0x14000503e  xor     rax, rsp
0x140005041  mov     [rsp+278h+var_38], rax
0x140005049  xor     r15d, r15d
0x14000504c  mov     rbx, r8
0x14000504f  mov     rsi, rdx
0x140005052  mov     r14, rcx
0x140005055  test    rdx, rdx
0x140005058  jz      loc_1400052B1
0x14000505e  test    rcx, rcx
0x140005061  jz      loc_1400052B1
0x140005067  mov     rax, cs:g_pfnResultLoggingCallback
0x14000506e  mov     [rcx], r15w
0x140005072  test    rax, rax
0x140005075  jz      short loc_140005098
0x140005077  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000507e  jz      short loc_140005098
0x140005080  mov     r8, rdx
0x140005083  mov     rdx, rcx
0x140005086  mov     rcx, rbx
0x140005089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000508e  cmp     [r14], r15w
0x140005092  jnz     loc_1400052B1
0x140005098  mov     ecx, [rbx]
0x14000509a  mov     bpl, 8
0x14000509d  test    ecx, ecx
0x14000509f  jz      short loc_1400050EA
0x1400050a1  sub     ecx, 1
0x1400050a4  jz      short loc_1400050D2
0x1400050a6  sub     ecx, 1
0x1400050a9  jz      short loc_1400050C2
0x1400050ab  cmp     ecx, 1
0x1400050ae  jz      short loc_1400050B9
0x1400050b0  lea     rdi, word_14001269A
0x1400050b7  jmp     short loc_1400050F1
0x1400050b9  lea     rdi, aFailfast; "FailFast"
0x1400050c0  jmp     short loc_1400050F1
0x1400050c2  lea     rax, aLoghr; "LogHr"
0x1400050c9  lea     rdi, aLognt; "LogNt"
0x1400050d0  jmp     short loc_1400050E0
0x1400050d2  lea     rax, aReturnhr; "ReturnHr"
0x1400050d9  lea     rdi, aReturnnt; "ReturnNt"
0x1400050e0  test    [rbx+4], bpl
0x1400050e4  cmovz   rdi, rax
0x1400050e8  jmp     short loc_1400050F1
0x1400050ea  lea     rdi, aException; "Exception"
0x1400050f1  xor     edx, edx; Val
0x1400050f3  lea     rcx, [rsp+278h+Buffer]; void *
0x1400050f8  mov     r8d, 200h; Size
0x1400050fe  call    memset_0
0x140005103  test    [rbx+4], bpl
0x140005107  jz      short loc_14000512C
0x140005109  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140005110  mov     ebp, [rbx+0Ch]
0x140005113  test    rax, rax
0x140005116  jz      short loc_14000515C
0x140005118  mov     r8d, 100h
0x14000511e  lea     rdx, [rsp+278h+Buffer]
0x140005123  mov     ecx, ebp
0x140005125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000512a  jmp     short loc_14000515C
0x14000512c  mov     ebp, [rbx+8]
0x14000512f  lea     rax, [rsp+278h+Buffer]
0x140005134  mov     [rsp+278h+Arguments], r15; Arguments
0x140005139  mov     r8d, ebp; dwMessageId
0x14000513c  mov     [rsp+278h+nSize], 100h; nSize
0x140005144  mov     r9d, 400h; dwLanguageId
0x14000514a  xor     edx, edx; lpSource
0x14000514c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140005151  mov     ecx, 1200h; dwFlags
0x140005156  call    cs:__imp_FormatMessageW
0x14000515c  mov     r9, [rbx+38h]; unsigned __int16 *
0x140005160  lea     rsi, [r14+rsi*2]
0x140005164  mov     rax, [rbx+88h]
0x14000516b  mov     rdx, rsi; unsigned __int16 *
0x14000516e  mov     rcx, [rbx+80h]
0x140005175  test    r9, r9
0x140005178  jz      short loc_14000519C
0x14000517a  mov     [rsp+278h+Arguments], rax
0x14000517f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140005186  mov     eax, [rbx+40h]
0x140005189  mov     qword ptr [rsp+278h+nSize], rcx
0x14000518e  mov     rcx, r14; this
0x140005191  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140005195  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000519a  jmp     short loc_1400051B3
0x14000519c  mov     r9, rcx; unsigned __int16 *
0x14000519f  mov     [rsp+278h+lpBuffer], rax
0x1400051a4  mov     rcx, r14; this
0x1400051a7  lea     r8, aHsP; "%hs!%p: "
0x1400051ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400051b3  mov     r9, [rbx+90h]; unsigned __int16 *
0x1400051ba  mov     r14, rax
0x1400051bd  test    r9, r9
0x1400051c0  jz      short loc_1400051D7
0x1400051c2  lea     r8, aCallerP; "(caller: %p) "
0x1400051c9  mov     rdx, rsi; unsigned __int16 *
0x1400051cc  mov     rcx, rax; this
0x1400051cf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400051d4  mov     r14, rax
0x1400051d7  call    cs:__imp_GetCurrentThreadId
0x1400051dd  lea     rcx, [rsp+278h+Buffer]
0x1400051e2  mov     r9, rdi; unsigned __int16 *
0x1400051e5  mov     [rsp+278h+var_240], rcx
0x1400051ea  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1400051f1  mov     dword ptr [rsp+278h+Arguments], ebp
0x1400051f5  mov     rdx, rsi; unsigned __int16 *
0x1400051f8  mov     [rsp+278h+nSize], eax
0x1400051fc  mov     rcx, r14; this
0x1400051ff  mov     eax, [rbx+44h]
0x140005202  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140005206  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000520b  cmp     [rbx+18h], r15
0x14000520f  jnz     short loc_140005221
0x140005211  cmp     [rbx+48h], r15
0x140005215  jnz     short loc_140005221
0x140005217  cmp     [rbx+30h], r15
0x14000521b  jz      loc_1400052B1
0x140005221  lea     r8, asc_140012350; "    "
0x140005228  mov     rdx, rsi; unsigned __int16 *
0x14000522b  mov     rcx, rax; this
0x14000522e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005233  mov     r9, [rbx+18h]; unsigned __int16 *
0x140005237  test    r9, r9
0x14000523a  jz      short loc_14000524E
0x14000523c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140005243  mov     rdx, rsi; unsigned __int16 *
0x140005246  mov     rcx, rax; this
0x140005249  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000524e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140005252  test    r9, r9
0x140005255  jz      short loc_140005269
0x140005257  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000525e  mov     rdx, rsi; unsigned __int16 *
0x140005261  mov     rcx, rax; this
0x140005264  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005269  mov     rcx, [rbx+28h]
0x14000526d  mov     rdx, rsi; unsigned __int16 *
0x140005270  mov     r9, [rbx+30h]; unsigned __int16 *
0x140005274  test    rcx, rcx
0x140005277  jz      short loc_14000528F
0x140005279  mov     [rsp+278h+lpBuffer], rcx
0x14000527e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140005285  mov     rcx, rax; this
0x140005288  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000528d  jmp     short loc_1400052B1
0x14000528f  mov     rcx, rax; this
0x140005292  test    r9, r9
0x140005295  jz      short loc_1400052A5
0x140005297  lea     r8, aHs; "[%hs]\n"
0x14000529e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400052a3  jmp     short loc_1400052B1
0x1400052a5  lea     r8, asc_1400123C8; "\n"
0x1400052ac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400052b1  xor     eax, eax
0x1400052b3  mov     rcx, [rsp+278h+var_38]
0x1400052bb  xor     rcx, rsp; StackCookie
0x1400052be  call    __security_check_cookie
0x1400052c3  mov     rbx, [rsp+278h+arg_18]
0x1400052cb  add     rsp, 250h
0x1400052d2  pop     r15
0x1400052d4  pop     r14
0x1400052d6  pop     rdi
0x1400052d7  pop     rsi
0x1400052d8  pop     rbp
0x1400052d9  retn
```
