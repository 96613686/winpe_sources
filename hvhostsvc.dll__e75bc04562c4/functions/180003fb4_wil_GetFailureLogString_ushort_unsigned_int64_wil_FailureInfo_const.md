# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180003fb4`
- end: `0x18000426a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000317c`
- `0x180004afc`
- `0x180004f7c`
- `0x180006190`

## callees

- `0x180002100`
- `0x180002b0c`
- `0x180003fb4`
- `0x180004dfc`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004167`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004167`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800040e6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800040e6`

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
          v7 = (const char *)&word_18000BAF2;
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
0x180003fb4  mov     [rsp+arg_18], rbx
0x180003fb9  push    rbp
0x180003fba  push    rsi
0x180003fbb  push    rdi
0x180003fbc  push    r14
0x180003fbe  push    r15
0x180003fc0  sub     rsp, 250h
0x180003fc7  mov     rax, cs:__security_cookie
0x180003fce  xor     rax, rsp
0x180003fd1  mov     [rsp+278h+var_38], rax
0x180003fd9  mov     rbx, r8
0x180003fdc  mov     rsi, rdx
0x180003fdf  mov     r14, rcx
0x180003fe2  xor     r15d, r15d
0x180003fe5  test    rdx, rdx
0x180003fe8  jz      loc_180004241
0x180003fee  test    rcx, rcx
0x180003ff1  jz      loc_180004241
0x180003ff7  mov     [rcx], r15w
0x180003ffb  mov     rax, cs:g_pfnResultLoggingCallback
0x180004002  test    rax, rax
0x180004005  jz      short loc_180004028
0x180004007  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000400e  jz      short loc_180004028
0x180004010  mov     r8, rdx
0x180004013  mov     rdx, rcx
0x180004016  mov     rcx, rbx
0x180004019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000401e  cmp     [r14], r15w
0x180004022  jnz     loc_180004241
0x180004028  mov     ecx, [rbx]
0x18000402a  mov     bpl, 8
0x18000402d  test    ecx, ecx
0x18000402f  jz      short loc_18000407A
0x180004031  sub     ecx, 1
0x180004034  jz      short loc_180004062
0x180004036  sub     ecx, 1
0x180004039  jz      short loc_180004052
0x18000403b  cmp     ecx, 1
0x18000403e  jz      short loc_180004049
0x180004040  lea     rdi, word_18000BAF2
0x180004047  jmp     short loc_180004081
0x180004049  lea     rdi, aFailfast; "FailFast"
0x180004050  jmp     short loc_180004081
0x180004052  lea     rax, aLoghr; "LogHr"
0x180004059  lea     rdi, aLognt; "LogNt"
0x180004060  jmp     short loc_180004070
0x180004062  lea     rax, aReturnhr; "ReturnHr"
0x180004069  lea     rdi, aReturnnt; "ReturnNt"
0x180004070  test    [rbx+4], bpl
0x180004074  cmovz   rdi, rax
0x180004078  jmp     short loc_180004081
0x18000407a  lea     rdi, aException; "Exception"
0x180004081  xor     edx, edx; Val
0x180004083  mov     r8d, 200h; Size
0x180004089  lea     rcx, [rsp+278h+Buffer]; void *
0x18000408e  call    memset_0
0x180004093  test    [rbx+4], bpl
0x180004097  jz      short loc_1800040BC
0x180004099  mov     ebp, [rbx+0Ch]
0x18000409c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800040a3  test    rax, rax
0x1800040a6  jz      short loc_1800040EC
0x1800040a8  mov     r8d, 100h
0x1800040ae  lea     rdx, [rsp+278h+Buffer]
0x1800040b3  mov     ecx, ebp
0x1800040b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040ba  jmp     short loc_1800040EC
0x1800040bc  mov     ebp, [rbx+8]
0x1800040bf  mov     [rsp+278h+Arguments], r15; Arguments
0x1800040c4  mov     [rsp+278h+nSize], 100h; nSize
0x1800040cc  lea     rax, [rsp+278h+Buffer]
0x1800040d1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800040d6  mov     r9d, 400h; dwLanguageId
0x1800040dc  mov     r8d, ebp; dwMessageId
0x1800040df  xor     edx, edx; lpSource
0x1800040e1  mov     ecx, 1200h; dwFlags
0x1800040e6  call    cs:__imp_FormatMessageW
0x1800040ec  lea     rsi, [r14+rsi*2]
0x1800040f0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800040f4  mov     rax, [rbx+88h]
0x1800040fb  mov     rcx, [rbx+80h]
0x180004102  mov     rdx, rsi; unsigned __int16 *
0x180004105  test    r9, r9
0x180004108  jz      short loc_18000412C
0x18000410a  mov     [rsp+278h+Arguments], rax
0x18000410f  mov     qword ptr [rsp+278h+nSize], rcx
0x180004114  mov     eax, [rbx+40h]
0x180004117  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000411b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004122  mov     rcx, r14; this
0x180004125  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000412a  jmp     short loc_180004143
0x18000412c  mov     [rsp+278h+lpBuffer], rax
0x180004131  mov     r9, rcx; unsigned __int16 *
0x180004134  lea     r8, aHsP; "%hs!%p: "
0x18000413b  mov     rcx, r14; this
0x18000413e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004143  mov     r14, rax
0x180004146  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000414d  test    r9, r9
0x180004150  jz      short loc_180004167
0x180004152  lea     r8, aCallerP; "(caller: %p) "
0x180004159  mov     rdx, rsi; unsigned __int16 *
0x18000415c  mov     rcx, rax; this
0x18000415f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004164  mov     r14, rax
0x180004167  call    cs:__imp_GetCurrentThreadId
0x18000416d  lea     rcx, [rsp+278h+Buffer]
0x180004172  mov     [rsp+278h+var_240], rcx
0x180004177  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000417b  mov     [rsp+278h+nSize], eax
0x18000417f  mov     eax, [rbx+44h]
0x180004182  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004186  mov     r9, rdi; unsigned __int16 *
0x180004189  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004190  mov     rdx, rsi; unsigned __int16 *
0x180004193  mov     rcx, r14; this
0x180004196  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000419b  cmp     [rbx+18h], r15
0x18000419f  jnz     short loc_1800041B1
0x1800041a1  cmp     [rbx+48h], r15
0x1800041a5  jnz     short loc_1800041B1
0x1800041a7  cmp     [rbx+30h], r15
0x1800041ab  jz      loc_180004241
0x1800041b1  lea     r8, asc_18000BBE0; "    "
0x1800041b8  mov     rdx, rsi; unsigned __int16 *
0x1800041bb  mov     rcx, rax; this
0x1800041be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800041c3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800041c7  test    r9, r9
0x1800041ca  jz      short loc_1800041DE
0x1800041cc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800041d3  mov     rdx, rsi; unsigned __int16 *
0x1800041d6  mov     rcx, rax; this
0x1800041d9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800041de  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800041e2  test    r9, r9
0x1800041e5  jz      short loc_1800041F9
0x1800041e7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800041ee  mov     rdx, rsi; unsigned __int16 *
0x1800041f1  mov     rcx, rax; this
0x1800041f4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800041f9  mov     rcx, [rbx+28h]
0x1800041fd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004201  mov     rdx, rsi; unsigned __int16 *
0x180004204  test    rcx, rcx
0x180004207  jz      short loc_18000421F
0x180004209  mov     [rsp+278h+lpBuffer], rcx
0x18000420e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004215  mov     rcx, rax; this
0x180004218  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000421d  jmp     short loc_180004241
0x18000421f  mov     rcx, rax; this
0x180004222  test    r9, r9
0x180004225  jz      short loc_180004235
0x180004227  lea     r8, aHs; "[%hs]\n"
0x18000422e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004233  jmp     short loc_180004241
0x180004235  lea     r8, asc_18000BC58; "\n"
0x18000423c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004241  xor     eax, eax
0x180004243  mov     rcx, [rsp+278h+var_38]
0x18000424b  xor     rcx, rsp; StackCookie
0x18000424e  call    __security_check_cookie
0x180004253  mov     rbx, [rsp+278h+arg_18]
0x18000425b  add     rsp, 250h
0x180004262  pop     r15
0x180004264  pop     r14
0x180004266  pop     rdi
0x180004267  pop     rsi
0x180004268  pop     rbp
0x180004269  retn
```
