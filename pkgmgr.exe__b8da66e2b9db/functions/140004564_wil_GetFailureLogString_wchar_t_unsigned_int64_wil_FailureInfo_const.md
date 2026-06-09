# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140004564`
- end: `0x140004825`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140003640`
- `0x140004f0c`
- `0x1400064d0`

## callees

- `0x140002360`
- `0x140002d98`
- `0x140004564`
- `0x140005214`
- `0x14002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004722`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004722`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400046a1`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400046a1`

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
  LPWSTR lpBuffer; // [rsp+20h] [rbp-268h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-268h]
  DWORD nSize[2]; // [rsp+28h] [rbp-260h]
  va_list *Arguments; // [rsp+30h] [rbp-258h]
  WCHAR Buffer[256]; // [rsp+50h] [rbp-238h] BYREF

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
          v7 = (const char *)&qword_14002D1C8;
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
                          Buffer,
                          -2);
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
0x140004564  mov     rax, rsp
0x140004567  push    rbp
0x140004568  push    rsi
0x140004569  push    rdi
0x14000456a  push    r14
0x14000456c  push    r15
0x14000456e  sub     rsp, 260h
0x140004575  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x14000457e  mov     [rax+20h], rbx
0x140004582  mov     rax, cs:__security_cookie
0x140004589  xor     rax, rsp
0x14000458c  mov     [rsp+288h+var_38], rax
0x140004594  mov     rbx, r8
0x140004597  mov     rsi, rdx
0x14000459a  mov     r14, rcx
0x14000459d  xor     r15d, r15d
0x1400045a0  test    rdx, rdx
0x1400045a3  jz      loc_1400047FC
0x1400045a9  test    rcx, rcx
0x1400045ac  jz      loc_1400047FC
0x1400045b2  mov     [rcx], r15w
0x1400045b6  mov     rax, cs:g_pfnResultLoggingCallback
0x1400045bd  test    rax, rax
0x1400045c0  jz      short loc_1400045E3
0x1400045c2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400045c9  jz      short loc_1400045E3
0x1400045cb  mov     r8, rdx
0x1400045ce  mov     rdx, rcx
0x1400045d1  mov     rcx, rbx
0x1400045d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400045d9  cmp     [r14], r15w
0x1400045dd  jnz     loc_1400047FC
0x1400045e3  mov     ecx, [rbx]
0x1400045e5  mov     bpl, 8
0x1400045e8  test    ecx, ecx
0x1400045ea  jz      short loc_140004635
0x1400045ec  sub     ecx, 1
0x1400045ef  jz      short loc_14000461D
0x1400045f1  sub     ecx, 1
0x1400045f4  jz      short loc_14000460D
0x1400045f6  cmp     ecx, 1
0x1400045f9  jz      short loc_140004604
0x1400045fb  lea     rdi, qword_14002D1C8
0x140004602  jmp     short loc_14000463C
0x140004604  lea     rdi, aFailfast; "FailFast"
0x14000460b  jmp     short loc_14000463C
0x14000460d  lea     rax, aLoghr; "LogHr"
0x140004614  lea     rdi, aLognt; "LogNt"
0x14000461b  jmp     short loc_14000462B
0x14000461d  lea     rax, aReturnhr; "ReturnHr"
0x140004624  lea     rdi, aReturnnt; "ReturnNt"
0x14000462b  test    [rbx+4], bpl
0x14000462f  cmovz   rdi, rax
0x140004633  jmp     short loc_14000463C
0x140004635  lea     rdi, aException; "Exception"
0x14000463c  xor     edx, edx; Val
0x14000463e  mov     r8d, 200h; Size
0x140004644  lea     rcx, [rsp+288h+Buffer]; void *
0x140004649  call    memset_0
0x14000464e  test    [rbx+4], bpl
0x140004652  jz      short loc_140004677
0x140004654  mov     ebp, [rbx+0Ch]
0x140004657  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x14000465e  test    rax, rax
0x140004661  jz      short loc_1400046A7
0x140004663  mov     r8d, 100h
0x140004669  lea     rdx, [rsp+288h+Buffer]
0x14000466e  mov     ecx, ebp
0x140004670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004675  jmp     short loc_1400046A7
0x140004677  mov     ebp, [rbx+8]
0x14000467a  mov     [rsp+288h+Arguments], r15; Arguments
0x14000467f  mov     [rsp+288h+nSize], 100h; nSize
0x140004687  lea     rax, [rsp+288h+Buffer]
0x14000468c  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x140004691  mov     r9d, 400h; dwLanguageId
0x140004697  mov     r8d, ebp; dwMessageId
0x14000469a  xor     edx, edx; lpSource
0x14000469c  mov     ecx, 1200h; dwFlags
0x1400046a1  call    cs:__imp_FormatMessageW
0x1400046a7  lea     rsi, [r14+rsi*2]
0x1400046ab  mov     r9, [rbx+38h]; wchar_t *
0x1400046af  mov     rax, [rbx+88h]
0x1400046b6  mov     rcx, [rbx+80h]
0x1400046bd  mov     rdx, rsi; wchar_t *
0x1400046c0  test    r9, r9
0x1400046c3  jz      short loc_1400046E7
0x1400046c5  mov     [rsp+288h+Arguments], rax
0x1400046ca  mov     qword ptr [rsp+288h+nSize], rcx
0x1400046cf  mov     eax, [rbx+40h]
0x1400046d2  mov     dword ptr [rsp+288h+lpBuffer], eax
0x1400046d6  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1400046dd  mov     rcx, r14; this
0x1400046e0  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400046e5  jmp     short loc_1400046FE
0x1400046e7  mov     [rsp+288h+lpBuffer], rax
0x1400046ec  mov     r9, rcx; wchar_t *
0x1400046ef  lea     r8, aHsP; "%hs!%p: "
0x1400046f6  mov     rcx, r14; this
0x1400046f9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400046fe  mov     r14, rax
0x140004701  mov     r9, [rbx+90h]; wchar_t *
0x140004708  test    r9, r9
0x14000470b  jz      short loc_140004722
0x14000470d  lea     r8, aCallerP; "(caller: %p) "
0x140004714  mov     rdx, rsi; wchar_t *
0x140004717  mov     rcx, rax; this
0x14000471a  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14000471f  mov     r14, rax
0x140004722  call    cs:__imp_GetCurrentThreadId
0x140004728  lea     rcx, [rsp+288h+Buffer]
0x14000472d  mov     [rsp+288h+var_250], rcx
0x140004732  mov     dword ptr [rsp+288h+Arguments], ebp
0x140004736  mov     [rsp+288h+nSize], eax
0x14000473a  mov     eax, [rbx+44h]
0x14000473d  mov     dword ptr [rsp+288h+lpBuffer], eax
0x140004741  mov     r9, rdi; wchar_t *
0x140004744  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x14000474b  mov     rdx, rsi; wchar_t *
0x14000474e  mov     rcx, r14; this
0x140004751  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140004756  cmp     [rbx+18h], r15
0x14000475a  jnz     short loc_14000476C
0x14000475c  cmp     [rbx+48h], r15
0x140004760  jnz     short loc_14000476C
0x140004762  cmp     [rbx+30h], r15
0x140004766  jz      loc_1400047FC
0x14000476c  lea     r8, asc_14002D2D0; "    "
0x140004773  mov     rdx, rsi; wchar_t *
0x140004776  mov     rcx, rax; this
0x140004779  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14000477e  mov     r9, [rbx+18h]; wchar_t *
0x140004782  test    r9, r9
0x140004785  jz      short loc_140004799
0x140004787  lea     r8, aMsgWs; "Msg:[%ws] "
0x14000478e  mov     rdx, rsi; wchar_t *
0x140004791  mov     rcx, rax; this
0x140004794  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140004799  mov     r9, [rbx+48h]; wchar_t *
0x14000479d  test    r9, r9
0x1400047a0  jz      short loc_1400047B4
0x1400047a2  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1400047a9  mov     rdx, rsi; wchar_t *
0x1400047ac  mov     rcx, rax; this
0x1400047af  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400047b4  mov     rcx, [rbx+28h]
0x1400047b8  mov     r9, [rbx+30h]; wchar_t *
0x1400047bc  mov     rdx, rsi; wchar_t *
0x1400047bf  test    rcx, rcx
0x1400047c2  jz      short loc_1400047DA
0x1400047c4  mov     [rsp+288h+lpBuffer], rcx
0x1400047c9  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1400047d0  mov     rcx, rax; this
0x1400047d3  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400047d8  jmp     short loc_1400047FC
0x1400047da  mov     rcx, rax; this
0x1400047dd  test    r9, r9
0x1400047e0  jz      short loc_1400047F0
0x1400047e2  lea     r8, aHs; "[%hs]\n"
0x1400047e9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400047ee  jmp     short loc_1400047FC
0x1400047f0  lea     r8, asc_14002D348; "\n"
0x1400047f7  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400047fc  xor     eax, eax
0x1400047fe  mov     rcx, [rsp+288h+var_38]
0x140004806  xor     rcx, rsp; StackCookie
0x140004809  call    __security_check_cookie
0x14000480e  mov     rbx, [rsp+288h+arg_18]
0x140004816  add     rsp, 260h
0x14000481d  pop     r15
0x14000481f  pop     r14
0x140004821  pop     rdi
0x140004822  pop     rsi
0x140004823  pop     rbp
0x140004824  retn
```
