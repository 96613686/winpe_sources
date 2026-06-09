# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000459c`
- end: `0x180004852`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800032d4`
- `0x18000353c`
- `0x180004dfc`

## callees

- `0x18000459c`
- `0x1800050fc`
- `0x18001200e`
- `0x180012040`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000474f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000474f`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800046ce`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800046ce`

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
          v8 = (const char *)&dword_180017D14;
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
0x18000459c  mov     [rsp+arg_18], rbx
0x1800045a1  push    rbp
0x1800045a2  push    rsi
0x1800045a3  push    rdi
0x1800045a4  push    r14
0x1800045a6  push    r15
0x1800045a8  sub     rsp, 250h
0x1800045af  mov     rax, cs:__security_cookie
0x1800045b6  xor     rax, rsp
0x1800045b9  mov     [rsp+278h+var_38], rax
0x1800045c1  xor     r15d, r15d
0x1800045c4  mov     rbx, r8
0x1800045c7  mov     rsi, rdx
0x1800045ca  mov     r14, rcx
0x1800045cd  test    rdx, rdx
0x1800045d0  jz      loc_180004829
0x1800045d6  test    rcx, rcx
0x1800045d9  jz      loc_180004829
0x1800045df  mov     rax, cs:g_pfnResultLoggingCallback
0x1800045e6  mov     [rcx], r15w
0x1800045ea  test    rax, rax
0x1800045ed  jz      short loc_180004610
0x1800045ef  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800045f6  jz      short loc_180004610
0x1800045f8  mov     r8, rdx
0x1800045fb  mov     rdx, rcx
0x1800045fe  mov     rcx, rbx
0x180004601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004606  cmp     [r14], r15w
0x18000460a  jnz     loc_180004829
0x180004610  mov     ecx, [rbx]
0x180004612  mov     bpl, 8
0x180004615  test    ecx, ecx
0x180004617  jz      short loc_180004662
0x180004619  sub     ecx, 1
0x18000461c  jz      short loc_18000464A
0x18000461e  sub     ecx, 1
0x180004621  jz      short loc_18000463A
0x180004623  cmp     ecx, 1
0x180004626  jz      short loc_180004631
0x180004628  lea     rdi, dword_180017D14
0x18000462f  jmp     short loc_180004669
0x180004631  lea     rdi, aFailfast; "FailFast"
0x180004638  jmp     short loc_180004669
0x18000463a  lea     rax, aLoghr; "LogHr"
0x180004641  lea     rdi, aLognt; "LogNt"
0x180004648  jmp     short loc_180004658
0x18000464a  lea     rax, aReturnhr; "ReturnHr"
0x180004651  lea     rdi, aReturnnt; "ReturnNt"
0x180004658  test    [rbx+4], bpl
0x18000465c  cmovz   rdi, rax
0x180004660  jmp     short loc_180004669
0x180004662  lea     rdi, aException; "Exception"
0x180004669  xor     edx, edx; Val
0x18000466b  lea     rcx, [rsp+278h+Buffer]; void *
0x180004670  mov     r8d, 200h; Size
0x180004676  call    memset_0
0x18000467b  test    [rbx+4], bpl
0x18000467f  jz      short loc_1800046A4
0x180004681  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004688  mov     ebp, [rbx+0Ch]
0x18000468b  test    rax, rax
0x18000468e  jz      short loc_1800046D4
0x180004690  mov     r8d, 100h
0x180004696  lea     rdx, [rsp+278h+Buffer]
0x18000469b  mov     ecx, ebp
0x18000469d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046a2  jmp     short loc_1800046D4
0x1800046a4  mov     ebp, [rbx+8]
0x1800046a7  lea     rax, [rsp+278h+Buffer]
0x1800046ac  mov     [rsp+278h+Arguments], r15; Arguments
0x1800046b1  mov     r8d, ebp; dwMessageId
0x1800046b4  mov     [rsp+278h+nSize], 100h; nSize
0x1800046bc  mov     r9d, 400h; dwLanguageId
0x1800046c2  xor     edx, edx; lpSource
0x1800046c4  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800046c9  mov     ecx, 1200h; dwFlags
0x1800046ce  call    cs:__imp_FormatMessageW
0x1800046d4  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800046d8  lea     rsi, [r14+rsi*2]
0x1800046dc  mov     rax, [rbx+88h]
0x1800046e3  mov     rdx, rsi; unsigned __int16 *
0x1800046e6  mov     rcx, [rbx+80h]
0x1800046ed  test    r9, r9
0x1800046f0  jz      short loc_180004714
0x1800046f2  mov     [rsp+278h+Arguments], rax
0x1800046f7  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800046fe  mov     eax, [rbx+40h]
0x180004701  mov     qword ptr [rsp+278h+nSize], rcx
0x180004706  mov     rcx, r14; this
0x180004709  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000470d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004712  jmp     short loc_18000472B
0x180004714  mov     r9, rcx; unsigned __int16 *
0x180004717  mov     [rsp+278h+lpBuffer], rax
0x18000471c  mov     rcx, r14; this
0x18000471f  lea     r8, aHsP; "%hs!%p: "
0x180004726  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000472b  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004732  mov     r14, rax
0x180004735  test    r9, r9
0x180004738  jz      short loc_18000474F
0x18000473a  lea     r8, aCallerP; "(caller: %p) "
0x180004741  mov     rdx, rsi; unsigned __int16 *
0x180004744  mov     rcx, rax; this
0x180004747  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000474c  mov     r14, rax
0x18000474f  call    cs:__imp_GetCurrentThreadId
0x180004755  lea     rcx, [rsp+278h+Buffer]
0x18000475a  mov     r9, rdi; unsigned __int16 *
0x18000475d  mov     [rsp+278h+var_240], rcx
0x180004762  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004769  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000476d  mov     rdx, rsi; unsigned __int16 *
0x180004770  mov     [rsp+278h+nSize], eax
0x180004774  mov     rcx, r14; this
0x180004777  mov     eax, [rbx+44h]
0x18000477a  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000477e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004783  cmp     [rbx+18h], r15
0x180004787  jnz     short loc_180004799
0x180004789  cmp     [rbx+48h], r15
0x18000478d  jnz     short loc_180004799
0x18000478f  cmp     [rbx+30h], r15
0x180004793  jz      loc_180004829
0x180004799  lea     r8, asc_180017E00; "    "
0x1800047a0  mov     rdx, rsi; unsigned __int16 *
0x1800047a3  mov     rcx, rax; this
0x1800047a6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800047ab  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800047af  test    r9, r9
0x1800047b2  jz      short loc_1800047C6
0x1800047b4  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800047bb  mov     rdx, rsi; unsigned __int16 *
0x1800047be  mov     rcx, rax; this
0x1800047c1  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800047c6  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800047ca  test    r9, r9
0x1800047cd  jz      short loc_1800047E1
0x1800047cf  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800047d6  mov     rdx, rsi; unsigned __int16 *
0x1800047d9  mov     rcx, rax; this
0x1800047dc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800047e1  mov     rcx, [rbx+28h]
0x1800047e5  mov     rdx, rsi; unsigned __int16 *
0x1800047e8  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800047ec  test    rcx, rcx
0x1800047ef  jz      short loc_180004807
0x1800047f1  mov     [rsp+278h+lpBuffer], rcx
0x1800047f6  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800047fd  mov     rcx, rax; this
0x180004800  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004805  jmp     short loc_180004829
0x180004807  mov     rcx, rax; this
0x18000480a  test    r9, r9
0x18000480d  jz      short loc_18000481D
0x18000480f  lea     r8, aHs; "[%hs]\n"
0x180004816  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000481b  jmp     short loc_180004829
0x18000481d  lea     r8, asc_180017E78; "\n"
0x180004824  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004829  xor     eax, eax
0x18000482b  mov     rcx, [rsp+278h+var_38]
0x180004833  xor     rcx, rsp; StackCookie
0x180004836  call    __security_check_cookie
0x18000483b  mov     rbx, [rsp+278h+arg_18]
0x180004843  add     rsp, 250h
0x18000484a  pop     r15
0x18000484c  pop     r14
0x18000484e  pop     rdi
0x18000484f  pop     rsi
0x180004850  pop     rbp
0x180004851  retn
```
