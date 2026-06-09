# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140006f1c`
- end: `0x1400071d2`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140005b48`
- `0x140007870`
- `0x1400154a0`

## callees

- `0x1400030d3`
- `0x140006f1c`
- `0x140007b50`
- `0x14006a120`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400070cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400070cf`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000704e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000704e`

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
          v8 = qword_140070CA8;
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
0x140006f1c  mov     [rsp+arg_18], rbx
0x140006f21  push    rbp
0x140006f22  push    rsi
0x140006f23  push    rdi
0x140006f24  push    r14
0x140006f26  push    r15
0x140006f28  sub     rsp, 250h
0x140006f2f  mov     rax, cs:__security_cookie
0x140006f36  xor     rax, rsp
0x140006f39  mov     [rsp+278h+var_38], rax
0x140006f41  xor     r15d, r15d
0x140006f44  mov     rbx, r8
0x140006f47  mov     rsi, rdx
0x140006f4a  mov     r14, rcx
0x140006f4d  test    rdx, rdx
0x140006f50  jz      loc_1400071A9
0x140006f56  test    rcx, rcx
0x140006f59  jz      loc_1400071A9
0x140006f5f  mov     rax, cs:g_pfnResultLoggingCallback
0x140006f66  mov     [rcx], r15w
0x140006f6a  test    rax, rax
0x140006f6d  jz      short loc_140006F90
0x140006f6f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140006f76  jz      short loc_140006F90
0x140006f78  mov     r8, rdx
0x140006f7b  mov     rdx, rcx
0x140006f7e  mov     rcx, rbx
0x140006f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006f86  cmp     [r14], r15w
0x140006f8a  jnz     loc_1400071A9
0x140006f90  mov     ecx, [rbx]
0x140006f92  mov     bpl, 8
0x140006f95  test    ecx, ecx
0x140006f97  jz      short loc_140006FE2
0x140006f99  sub     ecx, 1
0x140006f9c  jz      short loc_140006FCA
0x140006f9e  sub     ecx, 1
0x140006fa1  jz      short loc_140006FBA
0x140006fa3  cmp     ecx, 1
0x140006fa6  jz      short loc_140006FB1
0x140006fa8  lea     rdi, qword_140070CA8
0x140006faf  jmp     short loc_140006FE9
0x140006fb1  lea     rdi, aFailfast; "FailFast"
0x140006fb8  jmp     short loc_140006FE9
0x140006fba  lea     rax, aLoghr; "LogHr"
0x140006fc1  lea     rdi, aLognt; "LogNt"
0x140006fc8  jmp     short loc_140006FD8
0x140006fca  lea     rax, aReturnhr; "ReturnHr"
0x140006fd1  lea     rdi, aReturnnt; "ReturnNt"
0x140006fd8  test    [rbx+4], bpl
0x140006fdc  cmovz   rdi, rax
0x140006fe0  jmp     short loc_140006FE9
0x140006fe2  lea     rdi, aException; "Exception"
0x140006fe9  xor     edx, edx; Val
0x140006feb  lea     rcx, [rsp+278h+Buffer]; void *
0x140006ff0  mov     r8d, 200h; Size
0x140006ff6  call    memset_0
0x140006ffb  test    [rbx+4], bpl
0x140006fff  jz      short loc_140007024
0x140007001  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140007008  mov     ebp, [rbx+0Ch]
0x14000700b  test    rax, rax
0x14000700e  jz      short loc_140007054
0x140007010  mov     r8d, 100h
0x140007016  lea     rdx, [rsp+278h+Buffer]
0x14000701b  mov     ecx, ebp
0x14000701d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007022  jmp     short loc_140007054
0x140007024  mov     ebp, [rbx+8]
0x140007027  lea     rax, [rsp+278h+Buffer]
0x14000702c  mov     [rsp+278h+Arguments], r15; Arguments
0x140007031  mov     r8d, ebp; dwMessageId
0x140007034  mov     [rsp+278h+nSize], 100h; nSize
0x14000703c  mov     r9d, 400h; dwLanguageId
0x140007042  xor     edx, edx; lpSource
0x140007044  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140007049  mov     ecx, 1200h; dwFlags
0x14000704e  call    cs:__imp_FormatMessageW
0x140007054  mov     r9, [rbx+38h]; unsigned __int16 *
0x140007058  lea     rsi, [r14+rsi*2]
0x14000705c  mov     rax, [rbx+88h]
0x140007063  mov     rdx, rsi; unsigned __int16 *
0x140007066  mov     rcx, [rbx+80h]
0x14000706d  test    r9, r9
0x140007070  jz      short loc_140007094
0x140007072  mov     [rsp+278h+Arguments], rax
0x140007077  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x14000707e  mov     eax, [rbx+40h]
0x140007081  mov     qword ptr [rsp+278h+nSize], rcx
0x140007086  mov     rcx, r14; this
0x140007089  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000708d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140007092  jmp     short loc_1400070AB
0x140007094  mov     r9, rcx; unsigned __int16 *
0x140007097  mov     [rsp+278h+lpBuffer], rax
0x14000709c  mov     rcx, r14; this
0x14000709f  lea     r8, aHsP; "%hs!%p: "
0x1400070a6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400070ab  mov     r9, [rbx+90h]; unsigned __int16 *
0x1400070b2  mov     r14, rax
0x1400070b5  test    r9, r9
0x1400070b8  jz      short loc_1400070CF
0x1400070ba  lea     r8, aCallerP; "(caller: %p) "
0x1400070c1  mov     rdx, rsi; unsigned __int16 *
0x1400070c4  mov     rcx, rax; this
0x1400070c7  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400070cc  mov     r14, rax
0x1400070cf  call    cs:__imp_GetCurrentThreadId
0x1400070d5  lea     rcx, [rsp+278h+Buffer]
0x1400070da  mov     r9, rdi; unsigned __int16 *
0x1400070dd  mov     [rsp+278h+var_240], rcx
0x1400070e2  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1400070e9  mov     dword ptr [rsp+278h+Arguments], ebp
0x1400070ed  mov     rdx, rsi; unsigned __int16 *
0x1400070f0  mov     [rsp+278h+nSize], eax
0x1400070f4  mov     rcx, r14; this
0x1400070f7  mov     eax, [rbx+44h]
0x1400070fa  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400070fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140007103  cmp     [rbx+18h], r15
0x140007107  jnz     short loc_140007119
0x140007109  cmp     [rbx+48h], r15
0x14000710d  jnz     short loc_140007119
0x14000710f  cmp     [rbx+30h], r15
0x140007113  jz      loc_1400071A9
0x140007119  lea     r8, asc_140070D98; "    "
0x140007120  mov     rdx, rsi; unsigned __int16 *
0x140007123  mov     rcx, rax; this
0x140007126  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000712b  mov     r9, [rbx+18h]; unsigned __int16 *
0x14000712f  test    r9, r9
0x140007132  jz      short loc_140007146
0x140007134  lea     r8, aMsgWs; "Msg:[%ws] "
0x14000713b  mov     rdx, rsi; unsigned __int16 *
0x14000713e  mov     rcx, rax; this
0x140007141  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140007146  mov     r9, [rbx+48h]; unsigned __int16 *
0x14000714a  test    r9, r9
0x14000714d  jz      short loc_140007161
0x14000714f  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140007156  mov     rdx, rsi; unsigned __int16 *
0x140007159  mov     rcx, rax; this
0x14000715c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140007161  mov     rcx, [rbx+28h]
0x140007165  mov     rdx, rsi; unsigned __int16 *
0x140007168  mov     r9, [rbx+30h]; unsigned __int16 *
0x14000716c  test    rcx, rcx
0x14000716f  jz      short loc_140007187
0x140007171  mov     [rsp+278h+lpBuffer], rcx
0x140007176  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x14000717d  mov     rcx, rax; this
0x140007180  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140007185  jmp     short loc_1400071A9
0x140007187  mov     rcx, rax; this
0x14000718a  test    r9, r9
0x14000718d  jz      short loc_14000719D
0x14000718f  lea     r8, aHs; "[%hs]\n"
0x140007196  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000719b  jmp     short loc_1400071A9
0x14000719d  lea     r8, asc_140070E10; "\n"
0x1400071a4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400071a9  xor     eax, eax
0x1400071ab  mov     rcx, [rsp+278h+var_38]
0x1400071b3  xor     rcx, rsp; StackCookie
0x1400071b6  call    __security_check_cookie
0x1400071bb  mov     rbx, [rsp+278h+arg_18]
0x1400071c3  add     rsp, 250h
0x1400071ca  pop     r15
0x1400071cc  pop     r14
0x1400071ce  pop     rdi
0x1400071cf  pop     rsi
0x1400071d0  pop     rbp
0x1400071d1  retn
```
