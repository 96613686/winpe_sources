# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004664`
- end: `0x18000491a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180003288`
- `0x1800034f0`
- `0x180004fc8`
- `0x180006e20`

## callees

- `0x180004664`
- `0x1800052c8`
- `0x1800133e2`
- `0x180013410`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004817`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004817`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004796`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004796`

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
          v7 = (const char *)&qword_180017890;
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
0x180004664  mov     [rsp+arg_18], rbx
0x180004669  push    rbp
0x18000466a  push    rsi
0x18000466b  push    rdi
0x18000466c  push    r14
0x18000466e  push    r15
0x180004670  sub     rsp, 250h
0x180004677  mov     rax, cs:__security_cookie
0x18000467e  xor     rax, rsp
0x180004681  mov     [rsp+278h+var_38], rax
0x180004689  mov     rbx, r8
0x18000468c  mov     rsi, rdx
0x18000468f  mov     r14, rcx
0x180004692  xor     r15d, r15d
0x180004695  test    rdx, rdx
0x180004698  jz      loc_1800048F1
0x18000469e  test    rcx, rcx
0x1800046a1  jz      loc_1800048F1
0x1800046a7  mov     [rcx], r15w
0x1800046ab  mov     rax, cs:g_pfnResultLoggingCallback
0x1800046b2  test    rax, rax
0x1800046b5  jz      short loc_1800046D8
0x1800046b7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800046be  jz      short loc_1800046D8
0x1800046c0  mov     r8, rdx
0x1800046c3  mov     rdx, rcx
0x1800046c6  mov     rcx, rbx
0x1800046c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046ce  cmp     [r14], r15w
0x1800046d2  jnz     loc_1800048F1
0x1800046d8  mov     ecx, [rbx]
0x1800046da  mov     bpl, 8
0x1800046dd  test    ecx, ecx
0x1800046df  jz      short loc_18000472A
0x1800046e1  sub     ecx, 1
0x1800046e4  jz      short loc_180004712
0x1800046e6  sub     ecx, 1
0x1800046e9  jz      short loc_180004702
0x1800046eb  cmp     ecx, 1
0x1800046ee  jz      short loc_1800046F9
0x1800046f0  lea     rdi, qword_180017890
0x1800046f7  jmp     short loc_180004731
0x1800046f9  lea     rdi, aFailfast; "FailFast"
0x180004700  jmp     short loc_180004731
0x180004702  lea     rax, aLoghr; "LogHr"
0x180004709  lea     rdi, aLognt; "LogNt"
0x180004710  jmp     short loc_180004720
0x180004712  lea     rax, aReturnhr; "ReturnHr"
0x180004719  lea     rdi, aReturnnt; "ReturnNt"
0x180004720  test    [rbx+4], bpl
0x180004724  cmovz   rdi, rax
0x180004728  jmp     short loc_180004731
0x18000472a  lea     rdi, aException; "Exception"
0x180004731  xor     edx, edx; Val
0x180004733  mov     r8d, 200h; Size
0x180004739  lea     rcx, [rsp+278h+Buffer]; void *
0x18000473e  call    memset_0
0x180004743  test    [rbx+4], bpl
0x180004747  jz      short loc_18000476C
0x180004749  mov     ebp, [rbx+0Ch]
0x18000474c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004753  test    rax, rax
0x180004756  jz      short loc_18000479C
0x180004758  mov     r8d, 100h
0x18000475e  lea     rdx, [rsp+278h+Buffer]
0x180004763  mov     ecx, ebp
0x180004765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000476a  jmp     short loc_18000479C
0x18000476c  mov     ebp, [rbx+8]
0x18000476f  mov     [rsp+278h+Arguments], r15; Arguments
0x180004774  mov     [rsp+278h+nSize], 100h; nSize
0x18000477c  lea     rax, [rsp+278h+Buffer]
0x180004781  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004786  mov     r9d, 400h; dwLanguageId
0x18000478c  mov     r8d, ebp; dwMessageId
0x18000478f  xor     edx, edx; lpSource
0x180004791  mov     ecx, 1200h; dwFlags
0x180004796  call    cs:__imp_FormatMessageW
0x18000479c  lea     rsi, [r14+rsi*2]
0x1800047a0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800047a4  mov     rax, [rbx+88h]
0x1800047ab  mov     rcx, [rbx+80h]
0x1800047b2  mov     rdx, rsi; unsigned __int16 *
0x1800047b5  test    r9, r9
0x1800047b8  jz      short loc_1800047DC
0x1800047ba  mov     [rsp+278h+Arguments], rax
0x1800047bf  mov     qword ptr [rsp+278h+nSize], rcx
0x1800047c4  mov     eax, [rbx+40h]
0x1800047c7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800047cb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800047d2  mov     rcx, r14; this
0x1800047d5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800047da  jmp     short loc_1800047F3
0x1800047dc  mov     [rsp+278h+lpBuffer], rax
0x1800047e1  mov     r9, rcx; unsigned __int16 *
0x1800047e4  lea     r8, aHsP; "%hs!%p: "
0x1800047eb  mov     rcx, r14; this
0x1800047ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800047f3  mov     r14, rax
0x1800047f6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800047fd  test    r9, r9
0x180004800  jz      short loc_180004817
0x180004802  lea     r8, aCallerP; "(caller: %p) "
0x180004809  mov     rdx, rsi; unsigned __int16 *
0x18000480c  mov     rcx, rax; this
0x18000480f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004814  mov     r14, rax
0x180004817  call    cs:__imp_GetCurrentThreadId
0x18000481d  lea     rcx, [rsp+278h+Buffer]
0x180004822  mov     [rsp+278h+var_240], rcx
0x180004827  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000482b  mov     [rsp+278h+nSize], eax
0x18000482f  mov     eax, [rbx+44h]
0x180004832  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004836  mov     r9, rdi; unsigned __int16 *
0x180004839  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004840  mov     rdx, rsi; unsigned __int16 *
0x180004843  mov     rcx, r14; this
0x180004846  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000484b  cmp     [rbx+18h], r15
0x18000484f  jnz     short loc_180004861
0x180004851  cmp     [rbx+48h], r15
0x180004855  jnz     short loc_180004861
0x180004857  cmp     [rbx+30h], r15
0x18000485b  jz      loc_1800048F1
0x180004861  lea     r8, asc_180017980; "    "
0x180004868  mov     rdx, rsi; unsigned __int16 *
0x18000486b  mov     rcx, rax; this
0x18000486e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004873  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004877  test    r9, r9
0x18000487a  jz      short loc_18000488E
0x18000487c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004883  mov     rdx, rsi; unsigned __int16 *
0x180004886  mov     rcx, rax; this
0x180004889  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000488e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004892  test    r9, r9
0x180004895  jz      short loc_1800048A9
0x180004897  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000489e  mov     rdx, rsi; unsigned __int16 *
0x1800048a1  mov     rcx, rax; this
0x1800048a4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800048a9  mov     rcx, [rbx+28h]
0x1800048ad  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800048b1  mov     rdx, rsi; unsigned __int16 *
0x1800048b4  test    rcx, rcx
0x1800048b7  jz      short loc_1800048CF
0x1800048b9  mov     [rsp+278h+lpBuffer], rcx
0x1800048be  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800048c5  mov     rcx, rax; this
0x1800048c8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800048cd  jmp     short loc_1800048F1
0x1800048cf  mov     rcx, rax; this
0x1800048d2  test    r9, r9
0x1800048d5  jz      short loc_1800048E5
0x1800048d7  lea     r8, aHs; "[%hs]\n"
0x1800048de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800048e3  jmp     short loc_1800048F1
0x1800048e5  lea     r8, asc_1800179F8; "\n"
0x1800048ec  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800048f1  xor     eax, eax
0x1800048f3  mov     rcx, [rsp+278h+var_38]
0x1800048fb  xor     rcx, rsp; StackCookie
0x1800048fe  call    __security_check_cookie
0x180004903  mov     rbx, [rsp+278h+arg_18]
0x18000490b  add     rsp, 250h
0x180004912  pop     r15
0x180004914  pop     r14
0x180004916  pop     rdi
0x180004917  pop     rsi
0x180004918  pop     rbp
0x180004919  retn
```
