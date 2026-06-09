# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800055c4`
- end: `0x180005885`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180003048`
- `0x1800032dc`
- `0x180006090`
- `0x180009d70`
- `0x18000a850`
- `0x180034d66`
- `0x180034e9a`

## callees

- `0x1800017a0`
- `0x18000270c`
- `0x1800055c4`
- `0x1800063a8`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000577b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000577b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800056f4`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800056f4`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  const char *v7; // rsi
  const char *v8; // rax
  DWORD v9; // ebp
  unsigned __int16 *v10; // rdi
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
      g_pfnResultLoggingCallback(a3, this, a2, a4);
      if ( *(_WORD *)this )
        return 0;
    }
  }
  v7 = (const char *)&dword_18003CA1C;
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
        goto LABEL_17;
      }
      v8 = "LogHr";
      v7 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v7 = v8;
    goto LABEL_17;
  }
  v7 = "Exception";
LABEL_17:
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
0x1800055c4  mov     [rsp+arg_18], rbx
0x1800055c9  push    rbp
0x1800055ca  push    rsi
0x1800055cb  push    rdi
0x1800055cc  push    r14
0x1800055ce  push    r15
0x1800055d0  sub     rsp, 250h
0x1800055d7  mov     rax, cs:__security_cookie
0x1800055de  xor     rax, rsp
0x1800055e1  mov     [rsp+278h+var_38], rax
0x1800055e9  mov     rbx, r8
0x1800055ec  mov     rdi, rdx
0x1800055ef  mov     r14, rcx
0x1800055f2  xor     r15d, r15d
0x1800055f5  test    rdx, rdx
0x1800055f8  jz      loc_18000585B
0x1800055fe  test    rcx, rcx
0x180005601  jz      loc_18000585B
0x180005607  mov     [rcx], r15w
0x18000560b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005612  test    rax, rax
0x180005615  jz      short loc_180005638
0x180005617  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000561e  jz      short loc_180005638
0x180005620  mov     r8, rdx
0x180005623  mov     rdx, rcx
0x180005626  mov     rcx, rbx
0x180005629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000562e  cmp     [r14], r15w
0x180005632  jnz     loc_18000585B
0x180005638  lea     rsi, dword_18003CA1C
0x18000563f  mov     ecx, [rbx]
0x180005641  mov     bpl, 8
0x180005644  test    ecx, ecx
0x180005646  jz      short loc_180005688
0x180005648  sub     ecx, 1
0x18000564b  jz      short loc_180005670
0x18000564d  sub     ecx, 1
0x180005650  jz      short loc_180005660
0x180005652  cmp     ecx, 1
0x180005655  jnz     short loc_18000568F
0x180005657  lea     rsi, aFailfast; "FailFast"
0x18000565e  jmp     short loc_18000568F
0x180005660  lea     rax, aLoghr; "LogHr"
0x180005667  lea     rsi, aLognt; "LogNt"
0x18000566e  jmp     short loc_18000567E
0x180005670  lea     rax, aReturnhr; "ReturnHr"
0x180005677  lea     rsi, aReturnnt; "ReturnNt"
0x18000567e  test    [rbx+4], bpl
0x180005682  cmovz   rsi, rax
0x180005686  jmp     short loc_18000568F
0x180005688  lea     rsi, aException; "Exception"
0x18000568f  xor     edx, edx; Val
0x180005691  mov     r8d, 200h; Size
0x180005697  lea     rcx, [rsp+278h+Buffer]; void *
0x18000569c  call    memset_0
0x1800056a1  test    [rbx+4], bpl
0x1800056a5  jz      short loc_1800056CA
0x1800056a7  mov     ebp, [rbx+0Ch]
0x1800056aa  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800056b1  test    rax, rax
0x1800056b4  jz      short loc_180005700
0x1800056b6  mov     r8d, 100h
0x1800056bc  lea     rdx, [rsp+278h+Buffer]
0x1800056c1  mov     ecx, ebp
0x1800056c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056c8  jmp     short loc_180005700
0x1800056ca  mov     ebp, [rbx+8]
0x1800056cd  mov     [rsp+278h+Arguments], r15; Arguments
0x1800056d2  mov     [rsp+278h+nSize], 100h; nSize
0x1800056da  lea     rax, [rsp+278h+Buffer]
0x1800056df  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800056e4  mov     r9d, 400h; dwLanguageId
0x1800056ea  mov     r8d, ebp; dwMessageId
0x1800056ed  xor     edx, edx; lpSource
0x1800056ef  mov     ecx, 1200h; dwFlags
0x1800056f4  call    cs:__imp_FormatMessageW
0x1800056fb  nop     dword ptr [rax+rax+00h]
0x180005700  lea     rdi, [r14+rdi*2]
0x180005704  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005708  mov     rax, [rbx+88h]
0x18000570f  mov     rcx, [rbx+80h]
0x180005716  mov     rdx, rdi; unsigned __int16 *
0x180005719  test    r9, r9
0x18000571c  jz      short loc_180005740
0x18000571e  mov     [rsp+278h+Arguments], rax
0x180005723  mov     qword ptr [rsp+278h+nSize], rcx
0x180005728  mov     eax, [rbx+40h]
0x18000572b  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000572f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005736  mov     rcx, r14; this
0x180005739  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000573e  jmp     short loc_180005757
0x180005740  mov     [rsp+278h+lpBuffer], rax
0x180005745  mov     r9, rcx; unsigned __int16 *
0x180005748  lea     r8, aHsP; "%hs!%p: "
0x18000574f  mov     rcx, r14; this
0x180005752  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005757  mov     r14, rax
0x18000575a  mov     r9, [rbx+90h]; unsigned __int16 *
0x180005761  test    r9, r9
0x180005764  jz      short loc_18000577B
0x180005766  lea     r8, aCallerP; "(caller: %p) "
0x18000576d  mov     rdx, rdi; unsigned __int16 *
0x180005770  mov     rcx, rax; this
0x180005773  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005778  mov     r14, rax
0x18000577b  call    cs:__imp_GetCurrentThreadId
0x180005782  nop     dword ptr [rax+rax+00h]
0x180005787  mov     ecx, [rbx+44h]
0x18000578a  lea     rdx, [rsp+278h+Buffer]
0x18000578f  mov     [rsp+278h+var_240], rdx
0x180005794  mov     dword ptr [rsp+278h+Arguments], ebp
0x180005798  mov     [rsp+278h+nSize], eax
0x18000579c  mov     dword ptr [rsp+278h+lpBuffer], ecx
0x1800057a0  mov     r9, rsi; unsigned __int16 *
0x1800057a3  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800057aa  mov     rdx, rdi; unsigned __int16 *
0x1800057ad  mov     rcx, r14; this
0x1800057b0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800057b5  cmp     [rbx+18h], r15
0x1800057b9  jnz     short loc_1800057CB
0x1800057bb  cmp     [rbx+48h], r15
0x1800057bf  jnz     short loc_1800057CB
0x1800057c1  cmp     [rbx+30h], r15
0x1800057c5  jz      loc_18000585B
0x1800057cb  lea     r8, asc_18003CB20; "    "
0x1800057d2  mov     rdx, rdi; unsigned __int16 *
0x1800057d5  mov     rcx, rax; this
0x1800057d8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800057dd  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800057e1  test    r9, r9
0x1800057e4  jz      short loc_1800057F8
0x1800057e6  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800057ed  mov     rdx, rdi; unsigned __int16 *
0x1800057f0  mov     rcx, rax; this
0x1800057f3  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800057f8  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800057fc  test    r9, r9
0x1800057ff  jz      short loc_180005813
0x180005801  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180005808  mov     rdx, rdi; unsigned __int16 *
0x18000580b  mov     rcx, rax; this
0x18000580e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005813  mov     rcx, [rbx+28h]
0x180005817  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000581b  mov     rdx, rdi; unsigned __int16 *
0x18000581e  test    rcx, rcx
0x180005821  jz      short loc_180005839
0x180005823  mov     [rsp+278h+lpBuffer], rcx
0x180005828  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000582f  mov     rcx, rax; this
0x180005832  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005837  jmp     short loc_18000585B
0x180005839  mov     rcx, rax; this
0x18000583c  test    r9, r9
0x18000583f  jz      short loc_18000584F
0x180005841  lea     r8, aHs; "[%hs]\n"
0x180005848  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000584d  jmp     short loc_18000585B
0x18000584f  lea     r8, asc_18003CB98; "\n"
0x180005856  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000585b  xor     eax, eax
0x18000585d  mov     rcx, [rsp+278h+var_38]
0x180005865  xor     rcx, rsp; StackCookie
0x180005868  call    __security_check_cookie
0x18000586d  mov     rbx, [rsp+278h+arg_18]
0x180005875  add     rsp, 250h
0x18000587c  pop     r15
0x18000587e  pop     r14
0x180005880  pop     rdi
0x180005881  pop     rsi
0x180005882  pop     rbp
0x180005883  retn
```
