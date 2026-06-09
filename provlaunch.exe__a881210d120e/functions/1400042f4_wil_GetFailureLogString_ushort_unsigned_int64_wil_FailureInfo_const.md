# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1400042f4`
- end: `0x1400045aa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x1400027dc`
- `0x140002a5c`
- `0x140002d10`
- `0x140004c54`
- `0x140006820`
- `0x14000a66f`
- `0x14000a7a3`

## callees

- `0x1400042f4`
- `0x140004f54`
- `0x14000a33e`
- `0x14000a370`
- `0x14000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400044a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400044a7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140004426`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140004426`

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
      g_pfnResultLoggingCallback(a3, this, a2, a4);
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
          v7 = (const char *)&byte_14000C830;
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
0x1400042f4  mov     [rsp+arg_18], rbx
0x1400042f9  push    rbp
0x1400042fa  push    rsi
0x1400042fb  push    rdi
0x1400042fc  push    r14
0x1400042fe  push    r15
0x140004300  sub     rsp, 250h
0x140004307  mov     rax, cs:__security_cookie
0x14000430e  xor     rax, rsp
0x140004311  mov     [rsp+278h+var_38], rax
0x140004319  mov     rbx, r8
0x14000431c  mov     rsi, rdx
0x14000431f  mov     r14, rcx
0x140004322  xor     r15d, r15d
0x140004325  test    rdx, rdx
0x140004328  jz      loc_140004581
0x14000432e  test    rcx, rcx
0x140004331  jz      loc_140004581
0x140004337  mov     [rcx], r15w
0x14000433b  mov     rax, cs:g_pfnResultLoggingCallback
0x140004342  test    rax, rax
0x140004345  jz      short loc_140004368
0x140004347  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000434e  jz      short loc_140004368
0x140004350  mov     r8, rdx
0x140004353  mov     rdx, rcx
0x140004356  mov     rcx, rbx
0x140004359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000435e  cmp     [r14], r15w
0x140004362  jnz     loc_140004581
0x140004368  mov     ecx, [rbx]
0x14000436a  mov     bpl, 8
0x14000436d  test    ecx, ecx
0x14000436f  jz      short loc_1400043BA
0x140004371  sub     ecx, 1
0x140004374  jz      short loc_1400043A2
0x140004376  sub     ecx, 1
0x140004379  jz      short loc_140004392
0x14000437b  cmp     ecx, 1
0x14000437e  jz      short loc_140004389
0x140004380  lea     rdi, byte_14000C830
0x140004387  jmp     short loc_1400043C1
0x140004389  lea     rdi, aFailfast; "FailFast"
0x140004390  jmp     short loc_1400043C1
0x140004392  lea     rax, aLoghr; "LogHr"
0x140004399  lea     rdi, aLognt; "LogNt"
0x1400043a0  jmp     short loc_1400043B0
0x1400043a2  lea     rax, aReturnhr; "ReturnHr"
0x1400043a9  lea     rdi, aReturnnt; "ReturnNt"
0x1400043b0  test    [rbx+4], bpl
0x1400043b4  cmovz   rdi, rax
0x1400043b8  jmp     short loc_1400043C1
0x1400043ba  lea     rdi, aException; "Exception"
0x1400043c1  xor     edx, edx; Val
0x1400043c3  mov     r8d, 200h; Size
0x1400043c9  lea     rcx, [rsp+278h+Buffer]; void *
0x1400043ce  call    memset_0
0x1400043d3  test    [rbx+4], bpl
0x1400043d7  jz      short loc_1400043FC
0x1400043d9  mov     ebp, [rbx+0Ch]
0x1400043dc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1400043e3  test    rax, rax
0x1400043e6  jz      short loc_14000442C
0x1400043e8  mov     r8d, 100h
0x1400043ee  lea     rdx, [rsp+278h+Buffer]
0x1400043f3  mov     ecx, ebp
0x1400043f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400043fa  jmp     short loc_14000442C
0x1400043fc  mov     ebp, [rbx+8]
0x1400043ff  mov     [rsp+278h+Arguments], r15; Arguments
0x140004404  mov     [rsp+278h+nSize], 100h; nSize
0x14000440c  lea     rax, [rsp+278h+Buffer]
0x140004411  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140004416  mov     r9d, 400h; dwLanguageId
0x14000441c  mov     r8d, ebp; dwMessageId
0x14000441f  xor     edx, edx; lpSource
0x140004421  mov     ecx, 1200h; dwFlags
0x140004426  call    cs:__imp_FormatMessageW
0x14000442c  lea     rsi, [r14+rsi*2]
0x140004430  mov     r9, [rbx+38h]; unsigned __int16 *
0x140004434  mov     rax, [rbx+88h]
0x14000443b  mov     rcx, [rbx+80h]
0x140004442  mov     rdx, rsi; unsigned __int16 *
0x140004445  test    r9, r9
0x140004448  jz      short loc_14000446C
0x14000444a  mov     [rsp+278h+Arguments], rax
0x14000444f  mov     qword ptr [rsp+278h+nSize], rcx
0x140004454  mov     eax, [rbx+40h]
0x140004457  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000445b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140004462  mov     rcx, r14; this
0x140004465  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000446a  jmp     short loc_140004483
0x14000446c  mov     [rsp+278h+lpBuffer], rax
0x140004471  mov     r9, rcx; unsigned __int16 *
0x140004474  lea     r8, aHsP; "%hs!%p: "
0x14000447b  mov     rcx, r14; this
0x14000447e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004483  mov     r14, rax
0x140004486  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000448d  test    r9, r9
0x140004490  jz      short loc_1400044A7
0x140004492  lea     r8, aCallerP; "(caller: %p) "
0x140004499  mov     rdx, rsi; unsigned __int16 *
0x14000449c  mov     rcx, rax; this
0x14000449f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400044a4  mov     r14, rax
0x1400044a7  call    cs:__imp_GetCurrentThreadId
0x1400044ad  lea     rcx, [rsp+278h+Buffer]
0x1400044b2  mov     [rsp+278h+var_240], rcx
0x1400044b7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1400044bb  mov     [rsp+278h+nSize], eax
0x1400044bf  mov     eax, [rbx+44h]
0x1400044c2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400044c6  mov     r9, rdi; unsigned __int16 *
0x1400044c9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1400044d0  mov     rdx, rsi; unsigned __int16 *
0x1400044d3  mov     rcx, r14; this
0x1400044d6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400044db  cmp     [rbx+18h], r15
0x1400044df  jnz     short loc_1400044F1
0x1400044e1  cmp     [rbx+48h], r15
0x1400044e5  jnz     short loc_1400044F1
0x1400044e7  cmp     [rbx+30h], r15
0x1400044eb  jz      loc_140004581
0x1400044f1  lea     r8, asc_14000C920; "    "
0x1400044f8  mov     rdx, rsi; unsigned __int16 *
0x1400044fb  mov     rcx, rax; this
0x1400044fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004503  mov     r9, [rbx+18h]; unsigned __int16 *
0x140004507  test    r9, r9
0x14000450a  jz      short loc_14000451E
0x14000450c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140004513  mov     rdx, rsi; unsigned __int16 *
0x140004516  mov     rcx, rax; this
0x140004519  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000451e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140004522  test    r9, r9
0x140004525  jz      short loc_140004539
0x140004527  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000452e  mov     rdx, rsi; unsigned __int16 *
0x140004531  mov     rcx, rax; this
0x140004534  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004539  mov     rcx, [rbx+28h]
0x14000453d  mov     r9, [rbx+30h]; unsigned __int16 *
0x140004541  mov     rdx, rsi; unsigned __int16 *
0x140004544  test    rcx, rcx
0x140004547  jz      short loc_14000455F
0x140004549  mov     [rsp+278h+lpBuffer], rcx
0x14000454e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140004555  mov     rcx, rax; this
0x140004558  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000455d  jmp     short loc_140004581
0x14000455f  mov     rcx, rax; this
0x140004562  test    r9, r9
0x140004565  jz      short loc_140004575
0x140004567  lea     r8, aHs; "[%hs]\n"
0x14000456e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004573  jmp     short loc_140004581
0x140004575  lea     r8, asc_14000C998; "\n"
0x14000457c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004581  xor     eax, eax
0x140004583  mov     rcx, [rsp+278h+var_38]
0x14000458b  xor     rcx, rsp; StackCookie
0x14000458e  call    __security_check_cookie
0x140004593  mov     rbx, [rsp+278h+arg_18]
0x14000459b  add     rsp, 250h
0x1400045a2  pop     r15
0x1400045a4  pop     r14
0x1400045a6  pop     rdi
0x1400045a7  pop     rsi
0x1400045a8  pop     rbp
0x1400045a9  retn
```
