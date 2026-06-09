# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140005604`
- end: `0x1400058c7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x140003090`
- `0x14000330c`
- `0x140006158`
- `0x14000a760`
- `0x140014d88`
- `0x140015922`
- `0x140015a56`

## callees

- `0x14000271f`
- `0x140005604`
- `0x14000646c`
- `0x140015690`
- `0x140017010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140005736`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140005736`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400057bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400057bd`

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
          v7 = (const char *)&qword_14001A560;
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
0x140005604  mov     [rsp+arg_18], rbx
0x140005609  push    rbp
0x14000560a  push    rsi
0x14000560b  push    rdi
0x14000560c  push    r14
0x14000560e  push    r15
0x140005610  sub     rsp, 250h
0x140005617  mov     rax, cs:__security_cookie
0x14000561e  xor     rax, rsp
0x140005621  mov     [rsp+278h+var_38], rax
0x140005629  mov     rbx, r8
0x14000562c  mov     rsi, rdx
0x14000562f  mov     r14, rcx
0x140005632  xor     r15d, r15d
0x140005635  test    rdx, rdx
0x140005638  jz      loc_14000589D
0x14000563e  test    rcx, rcx
0x140005641  jz      loc_14000589D
0x140005647  mov     [rcx], r15w
0x14000564b  mov     rax, cs:g_pfnResultLoggingCallback
0x140005652  test    rax, rax
0x140005655  jz      short loc_140005678
0x140005657  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000565e  jz      short loc_140005678
0x140005660  mov     r8, rdx
0x140005663  mov     rdx, rcx
0x140005666  mov     rcx, rbx
0x140005669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000566e  cmp     [r14], r15w
0x140005672  jnz     loc_14000589D
0x140005678  mov     ecx, [rbx]
0x14000567a  mov     bpl, 8
0x14000567d  test    ecx, ecx
0x14000567f  jz      short loc_1400056CA
0x140005681  sub     ecx, 1
0x140005684  jz      short loc_1400056B2
0x140005686  sub     ecx, 1
0x140005689  jz      short loc_1400056A2
0x14000568b  cmp     ecx, 1
0x14000568e  jz      short loc_140005699
0x140005690  lea     rdi, qword_14001A560
0x140005697  jmp     short loc_1400056D1
0x140005699  lea     rdi, aFailfast; "FailFast"
0x1400056a0  jmp     short loc_1400056D1
0x1400056a2  lea     rax, aLoghr; "LogHr"
0x1400056a9  lea     rdi, aLognt; "LogNt"
0x1400056b0  jmp     short loc_1400056C0
0x1400056b2  lea     rax, aReturnhr; "ReturnHr"
0x1400056b9  lea     rdi, aReturnnt; "ReturnNt"
0x1400056c0  test    [rbx+4], bpl
0x1400056c4  cmovz   rdi, rax
0x1400056c8  jmp     short loc_1400056D1
0x1400056ca  lea     rdi, aException; "Exception"
0x1400056d1  xor     edx, edx; Val
0x1400056d3  mov     r8d, 200h; Size
0x1400056d9  lea     rcx, [rsp+278h+Buffer]; void *
0x1400056de  call    memset_0
0x1400056e3  test    [rbx+4], bpl
0x1400056e7  jz      short loc_14000570C
0x1400056e9  mov     ebp, [rbx+0Ch]
0x1400056ec  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1400056f3  test    rax, rax
0x1400056f6  jz      short loc_140005742
0x1400056f8  mov     r8d, 100h
0x1400056fe  lea     rdx, [rsp+278h+Buffer]
0x140005703  mov     ecx, ebp
0x140005705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000570a  jmp     short loc_140005742
0x14000570c  mov     ebp, [rbx+8]
0x14000570f  mov     [rsp+278h+Arguments], r15; Arguments
0x140005714  mov     [rsp+278h+nSize], 100h; nSize
0x14000571c  lea     rax, [rsp+278h+Buffer]
0x140005721  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140005726  mov     r9d, 400h; dwLanguageId
0x14000572c  mov     r8d, ebp; dwMessageId
0x14000572f  xor     edx, edx; lpSource
0x140005731  mov     ecx, 1200h; dwFlags
0x140005736  call    cs:__imp_FormatMessageW
0x14000573d  nop     dword ptr [rax+rax+00h]
0x140005742  lea     rsi, [r14+rsi*2]
0x140005746  mov     r9, [rbx+38h]; unsigned __int16 *
0x14000574a  mov     rax, [rbx+88h]
0x140005751  mov     rcx, [rbx+80h]
0x140005758  mov     rdx, rsi; unsigned __int16 *
0x14000575b  test    r9, r9
0x14000575e  jz      short loc_140005782
0x140005760  mov     [rsp+278h+Arguments], rax
0x140005765  mov     qword ptr [rsp+278h+nSize], rcx
0x14000576a  mov     eax, [rbx+40h]
0x14000576d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140005771  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140005778  mov     rcx, r14; this
0x14000577b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005780  jmp     short loc_140005799
0x140005782  mov     [rsp+278h+lpBuffer], rax
0x140005787  mov     r9, rcx; unsigned __int16 *
0x14000578a  lea     r8, aHsP; "%hs!%p: "
0x140005791  mov     rcx, r14; this
0x140005794  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005799  mov     r14, rax
0x14000579c  mov     r9, [rbx+90h]; unsigned __int16 *
0x1400057a3  test    r9, r9
0x1400057a6  jz      short loc_1400057BD
0x1400057a8  lea     r8, aCallerP; "(caller: %p) "
0x1400057af  mov     rdx, rsi; unsigned __int16 *
0x1400057b2  mov     rcx, rax; this
0x1400057b5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400057ba  mov     r14, rax
0x1400057bd  call    cs:__imp_GetCurrentThreadId
0x1400057c4  nop     dword ptr [rax+rax+00h]
0x1400057c9  lea     rcx, [rsp+278h+Buffer]
0x1400057ce  mov     [rsp+278h+var_240], rcx
0x1400057d3  mov     dword ptr [rsp+278h+Arguments], ebp
0x1400057d7  mov     [rsp+278h+nSize], eax
0x1400057db  mov     eax, [rbx+44h]
0x1400057de  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400057e2  mov     r9, rdi; unsigned __int16 *
0x1400057e5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1400057ec  mov     rdx, rsi; unsigned __int16 *
0x1400057ef  mov     rcx, r14; this
0x1400057f2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400057f7  cmp     [rbx+18h], r15
0x1400057fb  jnz     short loc_14000580D
0x1400057fd  cmp     [rbx+48h], r15
0x140005801  jnz     short loc_14000580D
0x140005803  cmp     [rbx+30h], r15
0x140005807  jz      loc_14000589D
0x14000580d  lea     r8, asc_14001A118; "    "
0x140005814  mov     rdx, rsi; unsigned __int16 *
0x140005817  mov     rcx, rax; this
0x14000581a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000581f  mov     r9, [rbx+18h]; unsigned __int16 *
0x140005823  test    r9, r9
0x140005826  jz      short loc_14000583A
0x140005828  lea     r8, aMsgWs; "Msg:[%ws] "
0x14000582f  mov     rdx, rsi; unsigned __int16 *
0x140005832  mov     rcx, rax; this
0x140005835  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000583a  mov     r9, [rbx+48h]; unsigned __int16 *
0x14000583e  test    r9, r9
0x140005841  jz      short loc_140005855
0x140005843  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000584a  mov     rdx, rsi; unsigned __int16 *
0x14000584d  mov     rcx, rax; this
0x140005850  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005855  mov     rcx, [rbx+28h]
0x140005859  mov     r9, [rbx+30h]; unsigned __int16 *
0x14000585d  mov     rdx, rsi; unsigned __int16 *
0x140005860  test    rcx, rcx
0x140005863  jz      short loc_14000587B
0x140005865  mov     [rsp+278h+lpBuffer], rcx
0x14000586a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140005871  mov     rcx, rax; this
0x140005874  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005879  jmp     short loc_14000589D
0x14000587b  mov     rcx, rax; this
0x14000587e  test    r9, r9
0x140005881  jz      short loc_140005891
0x140005883  lea     r8, aHs; "[%hs]\n"
0x14000588a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000588f  jmp     short loc_14000589D
0x140005891  lea     r8, asc_14001A190; "\n"
0x140005898  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000589d  xor     eax, eax
0x14000589f  mov     rcx, [rsp+278h+var_38]
0x1400058a7  xor     rcx, rsp; StackCookie
0x1400058aa  call    __security_check_cookie
0x1400058af  mov     rbx, [rsp+278h+arg_18]
0x1400058b7  add     rsp, 250h
0x1400058be  pop     r15
0x1400058c0  pop     r14
0x1400058c2  pop     rdi
0x1400058c3  pop     rsi
0x1400058c4  pop     rbp
0x1400058c5  retn
```
