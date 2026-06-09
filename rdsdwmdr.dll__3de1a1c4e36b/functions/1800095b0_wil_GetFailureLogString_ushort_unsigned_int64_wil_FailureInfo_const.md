# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800095b0`
- end: `0x180009866`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180007230`
- `0x18000a448`

## callees

- `0x1800095b0`
- `0x18000a748`
- `0x18002b93a`
- `0x18002b960`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009763`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009763`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800096e2`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800096e2`

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
          v8 = (const char *)&word_18002F722;
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
0x1800095b0  mov     [rsp+arg_18], rbx
0x1800095b5  push    rbp
0x1800095b6  push    rsi
0x1800095b7  push    rdi
0x1800095b8  push    r14
0x1800095ba  push    r15
0x1800095bc  sub     rsp, 250h
0x1800095c3  mov     rax, cs:__security_cookie
0x1800095ca  xor     rax, rsp
0x1800095cd  mov     [rsp+278h+var_38], rax
0x1800095d5  xor     r15d, r15d
0x1800095d8  mov     rbx, r8
0x1800095db  mov     rsi, rdx
0x1800095de  mov     r14, rcx
0x1800095e1  test    rdx, rdx
0x1800095e4  jz      loc_18000983D
0x1800095ea  test    rcx, rcx
0x1800095ed  jz      loc_18000983D
0x1800095f3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800095fa  mov     [rcx], r15w
0x1800095fe  test    rax, rax
0x180009601  jz      short loc_180009624
0x180009603  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000960a  jz      short loc_180009624
0x18000960c  mov     r8, rdx
0x18000960f  mov     rdx, rcx
0x180009612  mov     rcx, rbx
0x180009615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000961a  cmp     [r14], r15w
0x18000961e  jnz     loc_18000983D
0x180009624  mov     ecx, [rbx]
0x180009626  mov     bpl, 8
0x180009629  test    ecx, ecx
0x18000962b  jz      short loc_180009676
0x18000962d  sub     ecx, 1
0x180009630  jz      short loc_18000965E
0x180009632  sub     ecx, 1
0x180009635  jz      short loc_18000964E
0x180009637  cmp     ecx, 1
0x18000963a  jz      short loc_180009645
0x18000963c  lea     rdi, word_18002F722
0x180009643  jmp     short loc_18000967D
0x180009645  lea     rdi, aFailfast; "FailFast"
0x18000964c  jmp     short loc_18000967D
0x18000964e  lea     rax, aLoghr; "LogHr"
0x180009655  lea     rdi, aLognt; "LogNt"
0x18000965c  jmp     short loc_18000966C
0x18000965e  lea     rax, aReturnhr; "ReturnHr"
0x180009665  lea     rdi, aReturnnt; "ReturnNt"
0x18000966c  test    [rbx+4], bpl
0x180009670  cmovz   rdi, rax
0x180009674  jmp     short loc_18000967D
0x180009676  lea     rdi, aException; "Exception"
0x18000967d  xor     edx, edx; Val
0x18000967f  lea     rcx, [rsp+278h+Buffer]; void *
0x180009684  mov     r8d, 200h; Size
0x18000968a  call    memset_0
0x18000968f  test    [rbx+4], bpl
0x180009693  jz      short loc_1800096B8
0x180009695  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000969c  mov     ebp, [rbx+0Ch]
0x18000969f  test    rax, rax
0x1800096a2  jz      short loc_1800096E8
0x1800096a4  mov     r8d, 100h
0x1800096aa  lea     rdx, [rsp+278h+Buffer]
0x1800096af  mov     ecx, ebp
0x1800096b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096b6  jmp     short loc_1800096E8
0x1800096b8  mov     ebp, [rbx+8]
0x1800096bb  lea     rax, [rsp+278h+Buffer]
0x1800096c0  mov     [rsp+278h+Arguments], r15; Arguments
0x1800096c5  mov     r8d, ebp; dwMessageId
0x1800096c8  mov     [rsp+278h+nSize], 100h; nSize
0x1800096d0  mov     r9d, 400h; dwLanguageId
0x1800096d6  xor     edx, edx; lpSource
0x1800096d8  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800096dd  mov     ecx, 1200h; dwFlags
0x1800096e2  call    cs:__imp_FormatMessageW
0x1800096e8  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800096ec  lea     rsi, [r14+rsi*2]
0x1800096f0  mov     rax, [rbx+88h]
0x1800096f7  mov     rdx, rsi; unsigned __int16 *
0x1800096fa  mov     rcx, [rbx+80h]
0x180009701  test    r9, r9
0x180009704  jz      short loc_180009728
0x180009706  mov     [rsp+278h+Arguments], rax
0x18000970b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180009712  mov     eax, [rbx+40h]
0x180009715  mov     qword ptr [rsp+278h+nSize], rcx
0x18000971a  mov     rcx, r14; this
0x18000971d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009721  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009726  jmp     short loc_18000973F
0x180009728  mov     r9, rcx; unsigned __int16 *
0x18000972b  mov     [rsp+278h+lpBuffer], rax
0x180009730  mov     rcx, r14; this
0x180009733  lea     r8, aHsP; "%hs!%p: "
0x18000973a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000973f  mov     r9, [rbx+90h]; unsigned __int16 *
0x180009746  mov     r14, rax
0x180009749  test    r9, r9
0x18000974c  jz      short loc_180009763
0x18000974e  lea     r8, aCallerP; "(caller: %p) "
0x180009755  mov     rdx, rsi; unsigned __int16 *
0x180009758  mov     rcx, rax; this
0x18000975b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009760  mov     r14, rax
0x180009763  call    cs:__imp_GetCurrentThreadId
0x180009769  lea     rcx, [rsp+278h+Buffer]
0x18000976e  mov     r9, rdi; unsigned __int16 *
0x180009771  mov     [rsp+278h+var_240], rcx
0x180009776  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000977d  mov     dword ptr [rsp+278h+Arguments], ebp
0x180009781  mov     rdx, rsi; unsigned __int16 *
0x180009784  mov     [rsp+278h+nSize], eax
0x180009788  mov     rcx, r14; this
0x18000978b  mov     eax, [rbx+44h]
0x18000978e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009792  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009797  cmp     [rbx+18h], r15
0x18000979b  jnz     short loc_1800097AD
0x18000979d  cmp     [rbx+48h], r15
0x1800097a1  jnz     short loc_1800097AD
0x1800097a3  cmp     [rbx+30h], r15
0x1800097a7  jz      loc_18000983D
0x1800097ad  lea     r8, asc_18002F830; "    "
0x1800097b4  mov     rdx, rsi; unsigned __int16 *
0x1800097b7  mov     rcx, rax; this
0x1800097ba  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800097bf  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800097c3  test    r9, r9
0x1800097c6  jz      short loc_1800097DA
0x1800097c8  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800097cf  mov     rdx, rsi; unsigned __int16 *
0x1800097d2  mov     rcx, rax; this
0x1800097d5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800097da  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800097de  test    r9, r9
0x1800097e1  jz      short loc_1800097F5
0x1800097e3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800097ea  mov     rdx, rsi; unsigned __int16 *
0x1800097ed  mov     rcx, rax; this
0x1800097f0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800097f5  mov     rcx, [rbx+28h]
0x1800097f9  mov     rdx, rsi; unsigned __int16 *
0x1800097fc  mov     r9, [rbx+30h]; unsigned __int16 *
0x180009800  test    rcx, rcx
0x180009803  jz      short loc_18000981B
0x180009805  mov     [rsp+278h+lpBuffer], rcx
0x18000980a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180009811  mov     rcx, rax; this
0x180009814  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009819  jmp     short loc_18000983D
0x18000981b  mov     rcx, rax; this
0x18000981e  test    r9, r9
0x180009821  jz      short loc_180009831
0x180009823  lea     r8, aHs; "[%hs]\n"
0x18000982a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000982f  jmp     short loc_18000983D
0x180009831  lea     r8, asc_18002F8A8; "\n"
0x180009838  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000983d  xor     eax, eax
0x18000983f  mov     rcx, [rsp+278h+var_38]
0x180009847  xor     rcx, rsp; StackCookie
0x18000984a  call    __security_check_cookie
0x18000984f  mov     rbx, [rsp+278h+arg_18]
0x180009857  add     rsp, 250h
0x18000985e  pop     r15
0x180009860  pop     r14
0x180009862  pop     rdi
0x180009863  pop     rsi
0x180009864  pop     rbp
0x180009865  retn
```
