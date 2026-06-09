# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180020064`
- end: `0x18002031a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180020944`
- `0x180023010`

## callees

- `0x180013b20`
- `0x180014610`
- `0x180020064`
- `0x180020c40`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020217`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020217`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180020196`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180020196`

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
          v7 = (const char *)&word_180028D1A;
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
0x180020064  mov     [rsp+arg_18], rbx
0x180020069  push    rbp
0x18002006a  push    rsi
0x18002006b  push    rdi
0x18002006c  push    r14
0x18002006e  push    r15
0x180020070  sub     rsp, 250h
0x180020077  mov     rax, cs:__security_cookie
0x18002007e  xor     rax, rsp
0x180020081  mov     [rsp+278h+var_38], rax
0x180020089  mov     rbx, r8
0x18002008c  mov     rsi, rdx
0x18002008f  mov     r14, rcx
0x180020092  xor     r15d, r15d
0x180020095  test    rdx, rdx
0x180020098  jz      loc_1800202F1
0x18002009e  test    rcx, rcx
0x1800200a1  jz      loc_1800202F1
0x1800200a7  mov     [rcx], r15w
0x1800200ab  mov     rax, cs:g_pfnResultLoggingCallback
0x1800200b2  test    rax, rax
0x1800200b5  jz      short loc_1800200D8
0x1800200b7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800200be  jz      short loc_1800200D8
0x1800200c0  mov     r8, rdx
0x1800200c3  mov     rdx, rcx
0x1800200c6  mov     rcx, rbx
0x1800200c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200ce  cmp     [r14], r15w
0x1800200d2  jnz     loc_1800202F1
0x1800200d8  mov     ecx, [rbx]
0x1800200da  mov     bpl, 8
0x1800200dd  test    ecx, ecx
0x1800200df  jz      short loc_18002012A
0x1800200e1  sub     ecx, 1
0x1800200e4  jz      short loc_180020112
0x1800200e6  sub     ecx, 1
0x1800200e9  jz      short loc_180020102
0x1800200eb  cmp     ecx, 1
0x1800200ee  jz      short loc_1800200F9
0x1800200f0  lea     rdi, word_180028D1A
0x1800200f7  jmp     short loc_180020131
0x1800200f9  lea     rdi, aFailfast; "FailFast"
0x180020100  jmp     short loc_180020131
0x180020102  lea     rax, aLoghr; "LogHr"
0x180020109  lea     rdi, aLognt; "LogNt"
0x180020110  jmp     short loc_180020120
0x180020112  lea     rax, aReturnhr; "ReturnHr"
0x180020119  lea     rdi, aReturnnt; "ReturnNt"
0x180020120  test    [rbx+4], bpl
0x180020124  cmovz   rdi, rax
0x180020128  jmp     short loc_180020131
0x18002012a  lea     rdi, aException; "Exception"
0x180020131  xor     edx, edx; Val
0x180020133  mov     r8d, 200h; Size
0x180020139  lea     rcx, [rsp+278h+Buffer]; void *
0x18002013e  call    memset_0
0x180020143  test    [rbx+4], bpl
0x180020147  jz      short loc_18002016C
0x180020149  mov     ebp, [rbx+0Ch]
0x18002014c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180020153  test    rax, rax
0x180020156  jz      short loc_18002019C
0x180020158  mov     r8d, 100h
0x18002015e  lea     rdx, [rsp+278h+Buffer]
0x180020163  mov     ecx, ebp
0x180020165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002016a  jmp     short loc_18002019C
0x18002016c  mov     ebp, [rbx+8]
0x18002016f  mov     [rsp+278h+Arguments], r15; Arguments
0x180020174  mov     [rsp+278h+nSize], 100h; nSize
0x18002017c  lea     rax, [rsp+278h+Buffer]
0x180020181  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180020186  mov     r9d, 400h; dwLanguageId
0x18002018c  mov     r8d, ebp; dwMessageId
0x18002018f  xor     edx, edx; lpSource
0x180020191  mov     ecx, 1200h; dwFlags
0x180020196  call    cs:__imp_FormatMessageW
0x18002019c  lea     rsi, [r14+rsi*2]
0x1800201a0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800201a4  mov     rax, [rbx+88h]
0x1800201ab  mov     rcx, [rbx+80h]
0x1800201b2  mov     rdx, rsi; unsigned __int16 *
0x1800201b5  test    r9, r9
0x1800201b8  jz      short loc_1800201DC
0x1800201ba  mov     [rsp+278h+Arguments], rax
0x1800201bf  mov     qword ptr [rsp+278h+nSize], rcx
0x1800201c4  mov     eax, [rbx+40h]
0x1800201c7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800201cb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800201d2  mov     rcx, r14; this
0x1800201d5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800201da  jmp     short loc_1800201F3
0x1800201dc  mov     [rsp+278h+lpBuffer], rax
0x1800201e1  mov     r9, rcx; unsigned __int16 *
0x1800201e4  lea     r8, aHsP; "%hs!%p: "
0x1800201eb  mov     rcx, r14; this
0x1800201ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800201f3  mov     r14, rax
0x1800201f6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800201fd  test    r9, r9
0x180020200  jz      short loc_180020217
0x180020202  lea     r8, aCallerP; "(caller: %p) "
0x180020209  mov     rdx, rsi; unsigned __int16 *
0x18002020c  mov     rcx, rax; this
0x18002020f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180020214  mov     r14, rax
0x180020217  call    cs:__imp_GetCurrentThreadId
0x18002021d  lea     rcx, [rsp+278h+Buffer]
0x180020222  mov     [rsp+278h+var_240], rcx
0x180020227  mov     dword ptr [rsp+278h+Arguments], ebp
0x18002022b  mov     [rsp+278h+nSize], eax
0x18002022f  mov     eax, [rbx+44h]
0x180020232  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180020236  mov     r9, rdi; unsigned __int16 *
0x180020239  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180020240  mov     rdx, rsi; unsigned __int16 *
0x180020243  mov     rcx, r14; this
0x180020246  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002024b  cmp     [rbx+18h], r15
0x18002024f  jnz     short loc_180020261
0x180020251  cmp     [rbx+48h], r15
0x180020255  jnz     short loc_180020261
0x180020257  cmp     [rbx+30h], r15
0x18002025b  jz      loc_1800202F1
0x180020261  lea     r8, asc_18002B028; "    "
0x180020268  mov     rdx, rsi; unsigned __int16 *
0x18002026b  mov     rcx, rax; this
0x18002026e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180020273  mov     r9, [rbx+18h]; unsigned __int16 *
0x180020277  test    r9, r9
0x18002027a  jz      short loc_18002028E
0x18002027c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180020283  mov     rdx, rsi; unsigned __int16 *
0x180020286  mov     rcx, rax; this
0x180020289  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002028e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180020292  test    r9, r9
0x180020295  jz      short loc_1800202A9
0x180020297  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18002029e  mov     rdx, rsi; unsigned __int16 *
0x1800202a1  mov     rcx, rax; this
0x1800202a4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800202a9  mov     rcx, [rbx+28h]
0x1800202ad  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800202b1  mov     rdx, rsi; unsigned __int16 *
0x1800202b4  test    rcx, rcx
0x1800202b7  jz      short loc_1800202CF
0x1800202b9  mov     [rsp+278h+lpBuffer], rcx
0x1800202be  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800202c5  mov     rcx, rax; this
0x1800202c8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800202cd  jmp     short loc_1800202F1
0x1800202cf  mov     rcx, rax; this
0x1800202d2  test    r9, r9
0x1800202d5  jz      short loc_1800202E5
0x1800202d7  lea     r8, aHs; "[%hs]\n"
0x1800202de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800202e3  jmp     short loc_1800202F1
0x1800202e5  lea     r8, asc_18002B0A0; "\n"
0x1800202ec  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800202f1  xor     eax, eax
0x1800202f3  mov     rcx, [rsp+278h+var_38]
0x1800202fb  xor     rcx, rsp; StackCookie
0x1800202fe  call    __security_check_cookie
0x180020303  mov     rbx, [rsp+278h+arg_18]
0x18002030b  add     rsp, 250h
0x180020312  pop     r15
0x180020314  pop     r14
0x180020316  pop     rdi
0x180020317  pop     rsi
0x180020318  pop     rbp
0x180020319  retn
```
