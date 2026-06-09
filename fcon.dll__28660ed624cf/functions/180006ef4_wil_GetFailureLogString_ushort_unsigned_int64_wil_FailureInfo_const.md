# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006ef4`
- end: `0x1800071aa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180005400`
- `0x180007bbc`
- `0x18000829c`
- `0x18000aec0`

## callees

- `0x180003220`
- `0x180004100`
- `0x180006ef4`
- `0x180007ebc`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800070a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800070a7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007026`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007026`

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
          v7 = (const char *)&dword_1800C241C;
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
0x180006ef4  mov     [rsp+arg_18], rbx
0x180006ef9  push    rbp
0x180006efa  push    rsi
0x180006efb  push    rdi
0x180006efc  push    r14
0x180006efe  push    r15
0x180006f00  sub     rsp, 250h
0x180006f07  mov     rax, cs:__security_cookie
0x180006f0e  xor     rax, rsp
0x180006f11  mov     [rsp+278h+var_38], rax
0x180006f19  mov     rbx, r8
0x180006f1c  mov     rsi, rdx
0x180006f1f  mov     r14, rcx
0x180006f22  xor     r15d, r15d
0x180006f25  test    rdx, rdx
0x180006f28  jz      loc_180007181
0x180006f2e  test    rcx, rcx
0x180006f31  jz      loc_180007181
0x180006f37  mov     [rcx], r15w
0x180006f3b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006f42  test    rax, rax
0x180006f45  jz      short loc_180006F68
0x180006f47  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006f4e  jz      short loc_180006F68
0x180006f50  mov     r8, rdx
0x180006f53  mov     rdx, rcx
0x180006f56  mov     rcx, rbx
0x180006f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f5e  cmp     [r14], r15w
0x180006f62  jnz     loc_180007181
0x180006f68  mov     ecx, [rbx]
0x180006f6a  mov     bpl, 8
0x180006f6d  test    ecx, ecx
0x180006f6f  jz      short loc_180006FBA
0x180006f71  sub     ecx, 1
0x180006f74  jz      short loc_180006FA2
0x180006f76  sub     ecx, 1
0x180006f79  jz      short loc_180006F92
0x180006f7b  cmp     ecx, 1
0x180006f7e  jz      short loc_180006F89
0x180006f80  lea     rdi, dword_1800C241C
0x180006f87  jmp     short loc_180006FC1
0x180006f89  lea     rdi, aFailfast; "FailFast"
0x180006f90  jmp     short loc_180006FC1
0x180006f92  lea     rax, aLoghr; "LogHr"
0x180006f99  lea     rdi, aLognt; "LogNt"
0x180006fa0  jmp     short loc_180006FB0
0x180006fa2  lea     rax, aReturnhr; "ReturnHr"
0x180006fa9  lea     rdi, aReturnnt; "ReturnNt"
0x180006fb0  test    [rbx+4], bpl
0x180006fb4  cmovz   rdi, rax
0x180006fb8  jmp     short loc_180006FC1
0x180006fba  lea     rdi, aException; "Exception"
0x180006fc1  xor     edx, edx; Val
0x180006fc3  mov     r8d, 200h; Size
0x180006fc9  lea     rcx, [rsp+278h+Buffer]; void *
0x180006fce  call    memset_0
0x180006fd3  test    [rbx+4], bpl
0x180006fd7  jz      short loc_180006FFC
0x180006fd9  mov     ebp, [rbx+0Ch]
0x180006fdc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180006fe3  test    rax, rax
0x180006fe6  jz      short loc_18000702C
0x180006fe8  mov     r8d, 100h
0x180006fee  lea     rdx, [rsp+278h+Buffer]
0x180006ff3  mov     ecx, ebp
0x180006ff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ffa  jmp     short loc_18000702C
0x180006ffc  mov     ebp, [rbx+8]
0x180006fff  mov     [rsp+278h+Arguments], r15; Arguments
0x180007004  mov     [rsp+278h+nSize], 100h; nSize
0x18000700c  lea     rax, [rsp+278h+Buffer]
0x180007011  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180007016  mov     r9d, 400h; dwLanguageId
0x18000701c  mov     r8d, ebp; dwMessageId
0x18000701f  xor     edx, edx; lpSource
0x180007021  mov     ecx, 1200h; dwFlags
0x180007026  call    cs:__imp_FormatMessageW
0x18000702c  lea     rsi, [r14+rsi*2]
0x180007030  mov     r9, [rbx+38h]; unsigned __int16 *
0x180007034  mov     rax, [rbx+88h]
0x18000703b  mov     rcx, [rbx+80h]
0x180007042  mov     rdx, rsi; unsigned __int16 *
0x180007045  test    r9, r9
0x180007048  jz      short loc_18000706C
0x18000704a  mov     [rsp+278h+Arguments], rax
0x18000704f  mov     qword ptr [rsp+278h+nSize], rcx
0x180007054  mov     eax, [rbx+40h]
0x180007057  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000705b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180007062  mov     rcx, r14; this
0x180007065  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000706a  jmp     short loc_180007083
0x18000706c  mov     [rsp+278h+lpBuffer], rax
0x180007071  mov     r9, rcx; unsigned __int16 *
0x180007074  lea     r8, aHsP; "%hs!%p: "
0x18000707b  mov     rcx, r14; this
0x18000707e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007083  mov     r14, rax
0x180007086  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000708d  test    r9, r9
0x180007090  jz      short loc_1800070A7
0x180007092  lea     r8, aCallerP; "(caller: %p) "
0x180007099  mov     rdx, rsi; unsigned __int16 *
0x18000709c  mov     rcx, rax; this
0x18000709f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800070a4  mov     r14, rax
0x1800070a7  call    cs:__imp_GetCurrentThreadId
0x1800070ad  lea     rcx, [rsp+278h+Buffer]
0x1800070b2  mov     [rsp+278h+var_240], rcx
0x1800070b7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800070bb  mov     [rsp+278h+nSize], eax
0x1800070bf  mov     eax, [rbx+44h]
0x1800070c2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800070c6  mov     r9, rdi; unsigned __int16 *
0x1800070c9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800070d0  mov     rdx, rsi; unsigned __int16 *
0x1800070d3  mov     rcx, r14; this
0x1800070d6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800070db  cmp     [rbx+18h], r15
0x1800070df  jnz     short loc_1800070F1
0x1800070e1  cmp     [rbx+48h], r15
0x1800070e5  jnz     short loc_1800070F1
0x1800070e7  cmp     [rbx+30h], r15
0x1800070eb  jz      loc_180007181
0x1800070f1  lea     r8, asc_1800C2520; "    "
0x1800070f8  mov     rdx, rsi; unsigned __int16 *
0x1800070fb  mov     rcx, rax; this
0x1800070fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007103  mov     r9, [rbx+18h]; unsigned __int16 *
0x180007107  test    r9, r9
0x18000710a  jz      short loc_18000711E
0x18000710c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180007113  mov     rdx, rsi; unsigned __int16 *
0x180007116  mov     rcx, rax; this
0x180007119  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000711e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180007122  test    r9, r9
0x180007125  jz      short loc_180007139
0x180007127  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000712e  mov     rdx, rsi; unsigned __int16 *
0x180007131  mov     rcx, rax; this
0x180007134  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007139  mov     rcx, [rbx+28h]
0x18000713d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180007141  mov     rdx, rsi; unsigned __int16 *
0x180007144  test    rcx, rcx
0x180007147  jz      short loc_18000715F
0x180007149  mov     [rsp+278h+lpBuffer], rcx
0x18000714e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180007155  mov     rcx, rax; this
0x180007158  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000715d  jmp     short loc_180007181
0x18000715f  mov     rcx, rax; this
0x180007162  test    r9, r9
0x180007165  jz      short loc_180007175
0x180007167  lea     r8, aHs; "[%hs]\n"
0x18000716e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007173  jmp     short loc_180007181
0x180007175  lea     r8, asc_1800C2598; "\n"
0x18000717c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007181  xor     eax, eax
0x180007183  mov     rcx, [rsp+278h+var_38]
0x18000718b  xor     rcx, rsp; StackCookie
0x18000718e  call    __security_check_cookie
0x180007193  mov     rbx, [rsp+278h+arg_18]
0x18000719b  add     rsp, 250h
0x1800071a2  pop     r15
0x1800071a4  pop     r14
0x1800071a6  pop     rdi
0x1800071a7  pop     rsi
0x1800071a8  pop     rbp
0x1800071a9  retn
```
