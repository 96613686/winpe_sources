# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006444`
- end: `0x1800066fa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180003e94`
- `0x1800040fc`
- `0x180007a74`

## callees

- `0x180006444`
- `0x180007d74`
- `0x18000ccde`
- `0x18000cd10`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006576`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006576`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800065f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800065f7`

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
          v8 = (const char *)&byte_18000FDD5;
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
0x180006444  mov     [rsp+arg_18], rbx
0x180006449  push    rbp
0x18000644a  push    rsi
0x18000644b  push    rdi
0x18000644c  push    r14
0x18000644e  push    r15
0x180006450  sub     rsp, 250h
0x180006457  mov     rax, cs:__security_cookie
0x18000645e  xor     rax, rsp
0x180006461  mov     [rsp+278h+var_38], rax
0x180006469  xor     r15d, r15d
0x18000646c  mov     rbx, r8
0x18000646f  mov     rsi, rdx
0x180006472  mov     r14, rcx
0x180006475  test    rdx, rdx
0x180006478  jz      loc_1800066D1
0x18000647e  test    rcx, rcx
0x180006481  jz      loc_1800066D1
0x180006487  mov     rax, cs:g_pfnResultLoggingCallback
0x18000648e  mov     [rcx], r15w
0x180006492  test    rax, rax
0x180006495  jz      short loc_1800064B8
0x180006497  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000649e  jz      short loc_1800064B8
0x1800064a0  mov     r8, rdx
0x1800064a3  mov     rdx, rcx
0x1800064a6  mov     rcx, rbx
0x1800064a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064ae  cmp     [r14], r15w
0x1800064b2  jnz     loc_1800066D1
0x1800064b8  mov     ecx, [rbx]
0x1800064ba  mov     bpl, 8
0x1800064bd  test    ecx, ecx
0x1800064bf  jz      short loc_18000650A
0x1800064c1  sub     ecx, 1
0x1800064c4  jz      short loc_1800064F2
0x1800064c6  sub     ecx, 1
0x1800064c9  jz      short loc_1800064E2
0x1800064cb  cmp     ecx, 1
0x1800064ce  jz      short loc_1800064D9
0x1800064d0  lea     rdi, byte_18000FDD5
0x1800064d7  jmp     short loc_180006511
0x1800064d9  lea     rdi, aFailfast; "FailFast"
0x1800064e0  jmp     short loc_180006511
0x1800064e2  lea     rax, aLoghr; "LogHr"
0x1800064e9  lea     rdi, aLognt; "LogNt"
0x1800064f0  jmp     short loc_180006500
0x1800064f2  lea     rax, aReturnhr; "ReturnHr"
0x1800064f9  lea     rdi, aReturnnt; "ReturnNt"
0x180006500  test    [rbx+4], bpl
0x180006504  cmovz   rdi, rax
0x180006508  jmp     short loc_180006511
0x18000650a  lea     rdi, aException; "Exception"
0x180006511  xor     edx, edx; Val
0x180006513  lea     rcx, [rsp+278h+Buffer]; void *
0x180006518  mov     r8d, 200h; Size
0x18000651e  call    memset_0
0x180006523  test    [rbx+4], bpl
0x180006527  jz      short loc_18000654C
0x180006529  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180006530  mov     ebp, [rbx+0Ch]
0x180006533  test    rax, rax
0x180006536  jz      short loc_18000657C
0x180006538  mov     r8d, 100h
0x18000653e  lea     rdx, [rsp+278h+Buffer]
0x180006543  mov     ecx, ebp
0x180006545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000654a  jmp     short loc_18000657C
0x18000654c  mov     ebp, [rbx+8]
0x18000654f  lea     rax, [rsp+278h+Buffer]
0x180006554  mov     [rsp+278h+Arguments], r15; Arguments
0x180006559  mov     r8d, ebp; dwMessageId
0x18000655c  mov     [rsp+278h+nSize], 100h; nSize
0x180006564  mov     r9d, 400h; dwLanguageId
0x18000656a  xor     edx, edx; lpSource
0x18000656c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006571  mov     ecx, 1200h; dwFlags
0x180006576  call    cs:__imp_FormatMessageW
0x18000657c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180006580  lea     rsi, [r14+rsi*2]
0x180006584  mov     rax, [rbx+88h]
0x18000658b  mov     rdx, rsi; unsigned __int16 *
0x18000658e  mov     rcx, [rbx+80h]
0x180006595  test    r9, r9
0x180006598  jz      short loc_1800065BC
0x18000659a  mov     [rsp+278h+Arguments], rax
0x18000659f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800065a6  mov     eax, [rbx+40h]
0x1800065a9  mov     qword ptr [rsp+278h+nSize], rcx
0x1800065ae  mov     rcx, r14; this
0x1800065b1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800065b5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800065ba  jmp     short loc_1800065D3
0x1800065bc  mov     r9, rcx; unsigned __int16 *
0x1800065bf  mov     [rsp+278h+lpBuffer], rax
0x1800065c4  mov     rcx, r14; this
0x1800065c7  lea     r8, aHsP; "%hs!%p: "
0x1800065ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800065d3  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800065da  mov     r14, rax
0x1800065dd  test    r9, r9
0x1800065e0  jz      short loc_1800065F7
0x1800065e2  lea     r8, aCallerP; "(caller: %p) "
0x1800065e9  mov     rdx, rsi; unsigned __int16 *
0x1800065ec  mov     rcx, rax; this
0x1800065ef  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800065f4  mov     r14, rax
0x1800065f7  call    cs:__imp_GetCurrentThreadId
0x1800065fd  lea     rcx, [rsp+278h+Buffer]
0x180006602  mov     r9, rdi; unsigned __int16 *
0x180006605  mov     [rsp+278h+var_240], rcx
0x18000660a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006611  mov     dword ptr [rsp+278h+Arguments], ebp
0x180006615  mov     rdx, rsi; unsigned __int16 *
0x180006618  mov     [rsp+278h+nSize], eax
0x18000661c  mov     rcx, r14; this
0x18000661f  mov     eax, [rbx+44h]
0x180006622  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006626  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000662b  cmp     [rbx+18h], r15
0x18000662f  jnz     short loc_180006641
0x180006631  cmp     [rbx+48h], r15
0x180006635  jnz     short loc_180006641
0x180006637  cmp     [rbx+30h], r15
0x18000663b  jz      loc_1800066D1
0x180006641  lea     r8, asc_18000FEC8; "    "
0x180006648  mov     rdx, rsi; unsigned __int16 *
0x18000664b  mov     rcx, rax; this
0x18000664e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006653  mov     r9, [rbx+18h]; unsigned __int16 *
0x180006657  test    r9, r9
0x18000665a  jz      short loc_18000666E
0x18000665c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006663  mov     rdx, rsi; unsigned __int16 *
0x180006666  mov     rcx, rax; this
0x180006669  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000666e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180006672  test    r9, r9
0x180006675  jz      short loc_180006689
0x180006677  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000667e  mov     rdx, rsi; unsigned __int16 *
0x180006681  mov     rcx, rax; this
0x180006684  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006689  mov     rcx, [rbx+28h]
0x18000668d  mov     rdx, rsi; unsigned __int16 *
0x180006690  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006694  test    rcx, rcx
0x180006697  jz      short loc_1800066AF
0x180006699  mov     [rsp+278h+lpBuffer], rcx
0x18000669e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800066a5  mov     rcx, rax; this
0x1800066a8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800066ad  jmp     short loc_1800066D1
0x1800066af  mov     rcx, rax; this
0x1800066b2  test    r9, r9
0x1800066b5  jz      short loc_1800066C5
0x1800066b7  lea     r8, aHs; "[%hs]\n"
0x1800066be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800066c3  jmp     short loc_1800066D1
0x1800066c5  lea     r8, asc_18000FF40; "\n"
0x1800066cc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800066d1  xor     eax, eax
0x1800066d3  mov     rcx, [rsp+278h+var_38]
0x1800066db  xor     rcx, rsp; StackCookie
0x1800066de  call    __security_check_cookie
0x1800066e3  mov     rbx, [rsp+278h+arg_18]
0x1800066eb  add     rsp, 250h
0x1800066f2  pop     r15
0x1800066f4  pop     r14
0x1800066f6  pop     rdi
0x1800066f7  pop     rsi
0x1800066f8  pop     rbp
0x1800066f9  retn
```
