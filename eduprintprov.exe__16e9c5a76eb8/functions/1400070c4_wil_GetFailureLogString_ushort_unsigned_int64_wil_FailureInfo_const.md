# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1400070c4`
- end: `0x14000737a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x140003c24`
- `0x140003e8c`
- `0x140004158`
- `0x140007d88`
- `0x14000bc10`

## callees

- `0x140002600`
- `0x140003168`
- `0x1400070c4`
- `0x140008088`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007277`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007277`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400071f6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400071f6`

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
          v7 = (const char *)&byte_140015CE0;
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
0x1400070c4  mov     [rsp+arg_18], rbx
0x1400070c9  push    rbp
0x1400070ca  push    rsi
0x1400070cb  push    rdi
0x1400070cc  push    r14
0x1400070ce  push    r15
0x1400070d0  sub     rsp, 250h
0x1400070d7  mov     rax, cs:__security_cookie
0x1400070de  xor     rax, rsp
0x1400070e1  mov     [rsp+278h+var_38], rax
0x1400070e9  mov     rbx, r8
0x1400070ec  mov     rsi, rdx
0x1400070ef  mov     r14, rcx
0x1400070f2  xor     r15d, r15d
0x1400070f5  test    rdx, rdx
0x1400070f8  jz      loc_140007351
0x1400070fe  test    rcx, rcx
0x140007101  jz      loc_140007351
0x140007107  mov     [rcx], r15w
0x14000710b  mov     rax, cs:g_pfnResultLoggingCallback
0x140007112  test    rax, rax
0x140007115  jz      short loc_140007138
0x140007117  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000711e  jz      short loc_140007138
0x140007120  mov     r8, rdx
0x140007123  mov     rdx, rcx
0x140007126  mov     rcx, rbx
0x140007129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000712e  cmp     [r14], r15w
0x140007132  jnz     loc_140007351
0x140007138  mov     ecx, [rbx]
0x14000713a  mov     bpl, 8
0x14000713d  test    ecx, ecx
0x14000713f  jz      short loc_14000718A
0x140007141  sub     ecx, 1
0x140007144  jz      short loc_140007172
0x140007146  sub     ecx, 1
0x140007149  jz      short loc_140007162
0x14000714b  cmp     ecx, 1
0x14000714e  jz      short loc_140007159
0x140007150  lea     rdi, byte_140015CE0
0x140007157  jmp     short loc_140007191
0x140007159  lea     rdi, aFailfast; "FailFast"
0x140007160  jmp     short loc_140007191
0x140007162  lea     rax, aLoghr; "LogHr"
0x140007169  lea     rdi, aLognt; "LogNt"
0x140007170  jmp     short loc_140007180
0x140007172  lea     rax, aReturnhr; "ReturnHr"
0x140007179  lea     rdi, aReturnnt; "ReturnNt"
0x140007180  test    [rbx+4], bpl
0x140007184  cmovz   rdi, rax
0x140007188  jmp     short loc_140007191
0x14000718a  lea     rdi, aException; "Exception"
0x140007191  xor     edx, edx; Val
0x140007193  mov     r8d, 200h; Size
0x140007199  lea     rcx, [rsp+278h+Buffer]; void *
0x14000719e  call    memset_0
0x1400071a3  test    [rbx+4], bpl
0x1400071a7  jz      short loc_1400071CC
0x1400071a9  mov     ebp, [rbx+0Ch]
0x1400071ac  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1400071b3  test    rax, rax
0x1400071b6  jz      short loc_1400071FC
0x1400071b8  mov     r8d, 100h
0x1400071be  lea     rdx, [rsp+278h+Buffer]
0x1400071c3  mov     ecx, ebp
0x1400071c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400071ca  jmp     short loc_1400071FC
0x1400071cc  mov     ebp, [rbx+8]
0x1400071cf  mov     [rsp+278h+Arguments], r15; Arguments
0x1400071d4  mov     [rsp+278h+nSize], 100h; nSize
0x1400071dc  lea     rax, [rsp+278h+Buffer]
0x1400071e1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1400071e6  mov     r9d, 400h; dwLanguageId
0x1400071ec  mov     r8d, ebp; dwMessageId
0x1400071ef  xor     edx, edx; lpSource
0x1400071f1  mov     ecx, 1200h; dwFlags
0x1400071f6  call    cs:__imp_FormatMessageW
0x1400071fc  lea     rsi, [r14+rsi*2]
0x140007200  mov     r9, [rbx+38h]; unsigned __int16 *
0x140007204  mov     rax, [rbx+88h]
0x14000720b  mov     rcx, [rbx+80h]
0x140007212  mov     rdx, rsi; unsigned __int16 *
0x140007215  test    r9, r9
0x140007218  jz      short loc_14000723C
0x14000721a  mov     [rsp+278h+Arguments], rax
0x14000721f  mov     qword ptr [rsp+278h+nSize], rcx
0x140007224  mov     eax, [rbx+40h]
0x140007227  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000722b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140007232  mov     rcx, r14; this
0x140007235  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000723a  jmp     short loc_140007253
0x14000723c  mov     [rsp+278h+lpBuffer], rax
0x140007241  mov     r9, rcx; unsigned __int16 *
0x140007244  lea     r8, aHsP; "%hs!%p: "
0x14000724b  mov     rcx, r14; this
0x14000724e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140007253  mov     r14, rax
0x140007256  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000725d  test    r9, r9
0x140007260  jz      short loc_140007277
0x140007262  lea     r8, aCallerP; "(caller: %p) "
0x140007269  mov     rdx, rsi; unsigned __int16 *
0x14000726c  mov     rcx, rax; this
0x14000726f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140007274  mov     r14, rax
0x140007277  call    cs:__imp_GetCurrentThreadId
0x14000727d  lea     rcx, [rsp+278h+Buffer]
0x140007282  mov     [rsp+278h+var_240], rcx
0x140007287  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000728b  mov     [rsp+278h+nSize], eax
0x14000728f  mov     eax, [rbx+44h]
0x140007292  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140007296  mov     r9, rdi; unsigned __int16 *
0x140007299  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1400072a0  mov     rdx, rsi; unsigned __int16 *
0x1400072a3  mov     rcx, r14; this
0x1400072a6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400072ab  cmp     [rbx+18h], r15
0x1400072af  jnz     short loc_1400072C1
0x1400072b1  cmp     [rbx+48h], r15
0x1400072b5  jnz     short loc_1400072C1
0x1400072b7  cmp     [rbx+30h], r15
0x1400072bb  jz      loc_140007351
0x1400072c1  lea     r8, asc_140015E00; "    "
0x1400072c8  mov     rdx, rsi; unsigned __int16 *
0x1400072cb  mov     rcx, rax; this
0x1400072ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400072d3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1400072d7  test    r9, r9
0x1400072da  jz      short loc_1400072EE
0x1400072dc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1400072e3  mov     rdx, rsi; unsigned __int16 *
0x1400072e6  mov     rcx, rax; this
0x1400072e9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400072ee  mov     r9, [rbx+48h]; unsigned __int16 *
0x1400072f2  test    r9, r9
0x1400072f5  jz      short loc_140007309
0x1400072f7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1400072fe  mov     rdx, rsi; unsigned __int16 *
0x140007301  mov     rcx, rax; this
0x140007304  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140007309  mov     rcx, [rbx+28h]
0x14000730d  mov     r9, [rbx+30h]; unsigned __int16 *
0x140007311  mov     rdx, rsi; unsigned __int16 *
0x140007314  test    rcx, rcx
0x140007317  jz      short loc_14000732F
0x140007319  mov     [rsp+278h+lpBuffer], rcx
0x14000731e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140007325  mov     rcx, rax; this
0x140007328  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000732d  jmp     short loc_140007351
0x14000732f  mov     rcx, rax; this
0x140007332  test    r9, r9
0x140007335  jz      short loc_140007345
0x140007337  lea     r8, aHs; "[%hs]\n"
0x14000733e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140007343  jmp     short loc_140007351
0x140007345  lea     r8, asc_140015E78; "\n"
0x14000734c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140007351  xor     eax, eax
0x140007353  mov     rcx, [rsp+278h+var_38]
0x14000735b  xor     rcx, rsp; StackCookie
0x14000735e  call    __security_check_cookie
0x140007363  mov     rbx, [rsp+278h+arg_18]
0x14000736b  add     rsp, 250h
0x140007372  pop     r15
0x140007374  pop     r14
0x140007376  pop     rdi
0x140007377  pop     rsi
0x140007378  pop     rbp
0x140007379  retn
```
