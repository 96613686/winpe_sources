# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005284`
- end: `0x180005547`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180005d20`
- `0x1800061bc`
- `0x180007690`

## callees

- `0x180002400`
- `0x180002e54`
- `0x180005284`
- `0x180006030`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000543d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000543d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800053b6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800053b6`

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
          v7 = (const char *)&word_1800BBB6A;
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
0x180005284  mov     [rsp+arg_18], rbx
0x180005289  push    rbp
0x18000528a  push    rsi
0x18000528b  push    rdi
0x18000528c  push    r14
0x18000528e  push    r15
0x180005290  sub     rsp, 250h
0x180005297  mov     rax, cs:__security_cookie
0x18000529e  xor     rax, rsp
0x1800052a1  mov     [rsp+278h+var_38], rax
0x1800052a9  mov     rbx, r8
0x1800052ac  mov     rsi, rdx
0x1800052af  mov     r14, rcx
0x1800052b2  xor     r15d, r15d
0x1800052b5  test    rdx, rdx
0x1800052b8  jz      loc_18000551D
0x1800052be  test    rcx, rcx
0x1800052c1  jz      loc_18000551D
0x1800052c7  mov     [rcx], r15w
0x1800052cb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800052d2  test    rax, rax
0x1800052d5  jz      short loc_1800052F8
0x1800052d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800052de  jz      short loc_1800052F8
0x1800052e0  mov     r8, rdx
0x1800052e3  mov     rdx, rcx
0x1800052e6  mov     rcx, rbx
0x1800052e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052ee  cmp     [r14], r15w
0x1800052f2  jnz     loc_18000551D
0x1800052f8  mov     ecx, [rbx]
0x1800052fa  mov     bpl, 8
0x1800052fd  test    ecx, ecx
0x1800052ff  jz      short loc_18000534A
0x180005301  sub     ecx, 1
0x180005304  jz      short loc_180005332
0x180005306  sub     ecx, 1
0x180005309  jz      short loc_180005322
0x18000530b  cmp     ecx, 1
0x18000530e  jz      short loc_180005319
0x180005310  lea     rdi, word_1800BBB6A
0x180005317  jmp     short loc_180005351
0x180005319  lea     rdi, aFailfast; "FailFast"
0x180005320  jmp     short loc_180005351
0x180005322  lea     rax, aLoghr; "LogHr"
0x180005329  lea     rdi, aLognt; "LogNt"
0x180005330  jmp     short loc_180005340
0x180005332  lea     rax, aReturnhr; "ReturnHr"
0x180005339  lea     rdi, aReturnnt; "ReturnNt"
0x180005340  test    [rbx+4], bpl
0x180005344  cmovz   rdi, rax
0x180005348  jmp     short loc_180005351
0x18000534a  lea     rdi, aException; "Exception"
0x180005351  xor     edx, edx; Val
0x180005353  mov     r8d, 200h; Size
0x180005359  lea     rcx, [rsp+278h+Buffer]; void *
0x18000535e  call    memset_0
0x180005363  test    [rbx+4], bpl
0x180005367  jz      short loc_18000538C
0x180005369  mov     ebp, [rbx+0Ch]
0x18000536c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005373  test    rax, rax
0x180005376  jz      short loc_1800053C2
0x180005378  mov     r8d, 100h
0x18000537e  lea     rdx, [rsp+278h+Buffer]
0x180005383  mov     ecx, ebp
0x180005385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000538a  jmp     short loc_1800053C2
0x18000538c  mov     ebp, [rbx+8]
0x18000538f  mov     [rsp+278h+Arguments], r15; Arguments
0x180005394  mov     [rsp+278h+nSize], 100h; nSize
0x18000539c  lea     rax, [rsp+278h+Buffer]
0x1800053a1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800053a6  mov     r9d, 400h; dwLanguageId
0x1800053ac  mov     r8d, ebp; dwMessageId
0x1800053af  xor     edx, edx; lpSource
0x1800053b1  mov     ecx, 1200h; dwFlags
0x1800053b6  call    cs:__imp_FormatMessageW
0x1800053bd  nop     dword ptr [rax+rax+00h]
0x1800053c2  lea     rsi, [r14+rsi*2]
0x1800053c6  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800053ca  mov     rax, [rbx+88h]
0x1800053d1  mov     rcx, [rbx+80h]
0x1800053d8  mov     rdx, rsi; unsigned __int16 *
0x1800053db  test    r9, r9
0x1800053de  jz      short loc_180005402
0x1800053e0  mov     [rsp+278h+Arguments], rax
0x1800053e5  mov     qword ptr [rsp+278h+nSize], rcx
0x1800053ea  mov     eax, [rbx+40h]
0x1800053ed  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800053f1  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800053f8  mov     rcx, r14; this
0x1800053fb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005400  jmp     short loc_180005419
0x180005402  mov     [rsp+278h+lpBuffer], rax
0x180005407  mov     r9, rcx; unsigned __int16 *
0x18000540a  lea     r8, aHsP; "%hs!%p: "
0x180005411  mov     rcx, r14; this
0x180005414  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005419  mov     r14, rax
0x18000541c  mov     r9, [rbx+90h]; unsigned __int16 *
0x180005423  test    r9, r9
0x180005426  jz      short loc_18000543D
0x180005428  lea     r8, aCallerP; "(caller: %p) "
0x18000542f  mov     rdx, rsi; unsigned __int16 *
0x180005432  mov     rcx, rax; this
0x180005435  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000543a  mov     r14, rax
0x18000543d  call    cs:__imp_GetCurrentThreadId
0x180005444  nop     dword ptr [rax+rax+00h]
0x180005449  lea     rcx, [rsp+278h+Buffer]
0x18000544e  mov     [rsp+278h+var_240], rcx
0x180005453  mov     dword ptr [rsp+278h+Arguments], ebp
0x180005457  mov     [rsp+278h+nSize], eax
0x18000545b  mov     eax, [rbx+44h]
0x18000545e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005462  mov     r9, rdi; unsigned __int16 *
0x180005465  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000546c  mov     rdx, rsi; unsigned __int16 *
0x18000546f  mov     rcx, r14; this
0x180005472  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005477  cmp     [rbx+18h], r15
0x18000547b  jnz     short loc_18000548D
0x18000547d  cmp     [rbx+48h], r15
0x180005481  jnz     short loc_18000548D
0x180005483  cmp     [rbx+30h], r15
0x180005487  jz      loc_18000551D
0x18000548d  lea     r8, asc_1800BBC58; "    "
0x180005494  mov     rdx, rsi; unsigned __int16 *
0x180005497  mov     rcx, rax; this
0x18000549a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000549f  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800054a3  test    r9, r9
0x1800054a6  jz      short loc_1800054BA
0x1800054a8  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800054af  mov     rdx, rsi; unsigned __int16 *
0x1800054b2  mov     rcx, rax; this
0x1800054b5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800054ba  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800054be  test    r9, r9
0x1800054c1  jz      short loc_1800054D5
0x1800054c3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800054ca  mov     rdx, rsi; unsigned __int16 *
0x1800054cd  mov     rcx, rax; this
0x1800054d0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800054d5  mov     rcx, [rbx+28h]
0x1800054d9  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800054dd  mov     rdx, rsi; unsigned __int16 *
0x1800054e0  test    rcx, rcx
0x1800054e3  jz      short loc_1800054FB
0x1800054e5  mov     [rsp+278h+lpBuffer], rcx
0x1800054ea  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800054f1  mov     rcx, rax; this
0x1800054f4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800054f9  jmp     short loc_18000551D
0x1800054fb  mov     rcx, rax; this
0x1800054fe  test    r9, r9
0x180005501  jz      short loc_180005511
0x180005503  lea     r8, aHs; "[%hs]\n"
0x18000550a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000550f  jmp     short loc_18000551D
0x180005511  lea     r8, asc_1800BBCD0; "\n"
0x180005518  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000551d  xor     eax, eax
0x18000551f  mov     rcx, [rsp+278h+var_38]
0x180005527  xor     rcx, rsp; StackCookie
0x18000552a  call    __security_check_cookie
0x18000552f  mov     rbx, [rsp+278h+arg_18]
0x180005537  add     rsp, 250h
0x18000553e  pop     r15
0x180005540  pop     r14
0x180005542  pop     rdi
0x180005543  pop     rsi
0x180005544  pop     rbp
0x180005545  retn
```
