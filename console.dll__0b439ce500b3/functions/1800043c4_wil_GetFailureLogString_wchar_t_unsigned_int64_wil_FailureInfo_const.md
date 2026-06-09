# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800043c4`
- end: `0x180004687`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800034c4`
- `0x180004dfc`
- `0x1800052ac`
- `0x180006530`

## callees

- `0x1800015b0`
- `0x180002088`
- `0x1800043c4`
- `0x180005110`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000457d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000457d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800044f6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800044f6`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rsi
  const wchar_t *v11; // r9
  __int64 v12; // rax
  const wchar_t *v13; // rcx
  wchar_t *v14; // rax
  wil::details *v15; // r14
  const wchar_t *v16; // r9
  wil::details *v17; // rax
  const wchar_t *v18; // r9
  wchar_t *v19; // rax
  const wchar_t *v20; // r9
  const wchar_t *v21; // r9
  const wchar_t *v22; // r9
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
          v7 = (const char *)&word_18001C4C2;
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
  v10 = (wchar_t *)((char *)this + 2 * (_QWORD)a2);
  v11 = *(const wchar_t **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const wchar_t **)(a3 + 128);
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
  v16 = *(const wchar_t **)(a3 + 144);
  if ( v16 )
    v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v15,
                          v10,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const wchar_t *)v7,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v10, L"    ", v18);
    v20 = *(const wchar_t **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const wchar_t **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const wchar_t **)(a3 + 48);
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
0x1800043c4  mov     [rsp+arg_18], rbx
0x1800043c9  push    rbp
0x1800043ca  push    rsi
0x1800043cb  push    rdi
0x1800043cc  push    r14
0x1800043ce  push    r15
0x1800043d0  sub     rsp, 250h
0x1800043d7  mov     rax, cs:__security_cookie
0x1800043de  xor     rax, rsp
0x1800043e1  mov     [rsp+278h+var_38], rax
0x1800043e9  mov     rbx, r8
0x1800043ec  mov     rsi, rdx
0x1800043ef  mov     r14, rcx
0x1800043f2  xor     r15d, r15d
0x1800043f5  test    rdx, rdx
0x1800043f8  jz      loc_18000465D
0x1800043fe  test    rcx, rcx
0x180004401  jz      loc_18000465D
0x180004407  mov     [rcx], r15w
0x18000440b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004412  test    rax, rax
0x180004415  jz      short loc_180004438
0x180004417  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000441e  jz      short loc_180004438
0x180004420  mov     r8, rdx
0x180004423  mov     rdx, rcx
0x180004426  mov     rcx, rbx
0x180004429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000442e  cmp     [r14], r15w
0x180004432  jnz     loc_18000465D
0x180004438  mov     ecx, [rbx]
0x18000443a  mov     bpl, 8
0x18000443d  test    ecx, ecx
0x18000443f  jz      short loc_18000448A
0x180004441  sub     ecx, 1
0x180004444  jz      short loc_180004472
0x180004446  sub     ecx, 1
0x180004449  jz      short loc_180004462
0x18000444b  cmp     ecx, 1
0x18000444e  jz      short loc_180004459
0x180004450  lea     rdi, word_18001C4C2
0x180004457  jmp     short loc_180004491
0x180004459  lea     rdi, aFailfast; "FailFast"
0x180004460  jmp     short loc_180004491
0x180004462  lea     rax, aLoghr; "LogHr"
0x180004469  lea     rdi, aLognt; "LogNt"
0x180004470  jmp     short loc_180004480
0x180004472  lea     rax, aReturnhr; "ReturnHr"
0x180004479  lea     rdi, aReturnnt; "ReturnNt"
0x180004480  test    [rbx+4], bpl
0x180004484  cmovz   rdi, rax
0x180004488  jmp     short loc_180004491
0x18000448a  lea     rdi, aException; "Exception"
0x180004491  xor     edx, edx; Val
0x180004493  mov     r8d, 200h; Size
0x180004499  lea     rcx, [rsp+278h+Buffer]; void *
0x18000449e  call    memset_0
0x1800044a3  test    [rbx+4], bpl
0x1800044a7  jz      short loc_1800044CC
0x1800044a9  mov     ebp, [rbx+0Ch]
0x1800044ac  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x1800044b3  test    rax, rax
0x1800044b6  jz      short loc_180004502
0x1800044b8  mov     r8d, 100h
0x1800044be  lea     rdx, [rsp+278h+Buffer]
0x1800044c3  mov     ecx, ebp
0x1800044c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044ca  jmp     short loc_180004502
0x1800044cc  mov     ebp, [rbx+8]
0x1800044cf  mov     [rsp+278h+Arguments], r15; Arguments
0x1800044d4  mov     [rsp+278h+nSize], 100h; nSize
0x1800044dc  lea     rax, [rsp+278h+Buffer]
0x1800044e1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800044e6  mov     r9d, 400h; dwLanguageId
0x1800044ec  mov     r8d, ebp; dwMessageId
0x1800044ef  xor     edx, edx; lpSource
0x1800044f1  mov     ecx, 1200h; dwFlags
0x1800044f6  call    cs:__imp_FormatMessageW
0x1800044fd  nop     dword ptr [rax+rax+00h]
0x180004502  lea     rsi, [r14+rsi*2]
0x180004506  mov     r9, [rbx+38h]; wchar_t *
0x18000450a  mov     rax, [rbx+88h]
0x180004511  mov     rcx, [rbx+80h]
0x180004518  mov     rdx, rsi; wchar_t *
0x18000451b  test    r9, r9
0x18000451e  jz      short loc_180004542
0x180004520  mov     [rsp+278h+Arguments], rax
0x180004525  mov     qword ptr [rsp+278h+nSize], rcx
0x18000452a  mov     eax, [rbx+40h]
0x18000452d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004531  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004538  mov     rcx, r14; this
0x18000453b  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004540  jmp     short loc_180004559
0x180004542  mov     [rsp+278h+lpBuffer], rax
0x180004547  mov     r9, rcx; wchar_t *
0x18000454a  lea     r8, aHsP; "%hs!%p: "
0x180004551  mov     rcx, r14; this
0x180004554  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004559  mov     r14, rax
0x18000455c  mov     r9, [rbx+90h]; wchar_t *
0x180004563  test    r9, r9
0x180004566  jz      short loc_18000457D
0x180004568  lea     r8, aCallerP; "(caller: %p) "
0x18000456f  mov     rdx, rsi; wchar_t *
0x180004572  mov     rcx, rax; this
0x180004575  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000457a  mov     r14, rax
0x18000457d  call    cs:__imp_GetCurrentThreadId
0x180004584  nop     dword ptr [rax+rax+00h]
0x180004589  lea     rcx, [rsp+278h+Buffer]
0x18000458e  mov     [rsp+278h+var_240], rcx
0x180004593  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004597  mov     [rsp+278h+nSize], eax
0x18000459b  mov     eax, [rbx+44h]
0x18000459e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800045a2  mov     r9, rdi; wchar_t *
0x1800045a5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800045ac  mov     rdx, rsi; wchar_t *
0x1800045af  mov     rcx, r14; this
0x1800045b2  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800045b7  cmp     [rbx+18h], r15
0x1800045bb  jnz     short loc_1800045CD
0x1800045bd  cmp     [rbx+48h], r15
0x1800045c1  jnz     short loc_1800045CD
0x1800045c3  cmp     [rbx+30h], r15
0x1800045c7  jz      loc_18000465D
0x1800045cd  lea     r8, asc_18001C5B0; "    "
0x1800045d4  mov     rdx, rsi; wchar_t *
0x1800045d7  mov     rcx, rax; this
0x1800045da  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800045df  mov     r9, [rbx+18h]; wchar_t *
0x1800045e3  test    r9, r9
0x1800045e6  jz      short loc_1800045FA
0x1800045e8  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800045ef  mov     rdx, rsi; wchar_t *
0x1800045f2  mov     rcx, rax; this
0x1800045f5  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800045fa  mov     r9, [rbx+48h]; wchar_t *
0x1800045fe  test    r9, r9
0x180004601  jz      short loc_180004615
0x180004603  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000460a  mov     rdx, rsi; wchar_t *
0x18000460d  mov     rcx, rax; this
0x180004610  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004615  mov     rcx, [rbx+28h]
0x180004619  mov     r9, [rbx+30h]; wchar_t *
0x18000461d  mov     rdx, rsi; wchar_t *
0x180004620  test    rcx, rcx
0x180004623  jz      short loc_18000463B
0x180004625  mov     [rsp+278h+lpBuffer], rcx
0x18000462a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004631  mov     rcx, rax; this
0x180004634  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004639  jmp     short loc_18000465D
0x18000463b  mov     rcx, rax; this
0x18000463e  test    r9, r9
0x180004641  jz      short loc_180004651
0x180004643  lea     r8, aHs; "[%hs]\n"
0x18000464a  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000464f  jmp     short loc_18000465D
0x180004651  lea     r8, asc_18001C628; "\n"
0x180004658  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000465d  xor     eax, eax
0x18000465f  mov     rcx, [rsp+278h+var_38]
0x180004667  xor     rcx, rsp; StackCookie
0x18000466a  call    __security_check_cookie
0x18000466f  mov     rbx, [rsp+278h+arg_18]
0x180004677  add     rsp, 250h
0x18000467e  pop     r15
0x180004680  pop     r14
0x180004682  pop     rdi
0x180004683  pop     rsi
0x180004684  pop     rbp
0x180004685  retn
```
