# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005534`
- end: `0x1800057ea`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180004064`
- `0x1800042e4`
- `0x180005f44`
- `0x180007890`
- `0x180007f34`
- `0x18002e1d0`
- `0x18002e304`

## callees

- `0x180002490`
- `0x180002ef8`
- `0x180005534`
- `0x180006244`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800056e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800056e7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005666`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005666`

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
          v7 = (const char *)&word_1800321F2;
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
0x180005534  mov     [rsp+arg_18], rbx
0x180005539  push    rbp
0x18000553a  push    rsi
0x18000553b  push    rdi
0x18000553c  push    r14
0x18000553e  push    r15
0x180005540  sub     rsp, 250h
0x180005547  mov     rax, cs:__security_cookie
0x18000554e  xor     rax, rsp
0x180005551  mov     [rsp+278h+var_38], rax
0x180005559  mov     rbx, r8
0x18000555c  mov     rsi, rdx
0x18000555f  mov     r14, rcx
0x180005562  xor     r15d, r15d
0x180005565  test    rdx, rdx
0x180005568  jz      loc_1800057C1
0x18000556e  test    rcx, rcx
0x180005571  jz      loc_1800057C1
0x180005577  mov     [rcx], r15w
0x18000557b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005582  test    rax, rax
0x180005585  jz      short loc_1800055A8
0x180005587  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000558e  jz      short loc_1800055A8
0x180005590  mov     r8, rdx
0x180005593  mov     rdx, rcx
0x180005596  mov     rcx, rbx
0x180005599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000559e  cmp     [r14], r15w
0x1800055a2  jnz     loc_1800057C1
0x1800055a8  mov     ecx, [rbx]
0x1800055aa  mov     bpl, 8
0x1800055ad  test    ecx, ecx
0x1800055af  jz      short loc_1800055FA
0x1800055b1  sub     ecx, 1
0x1800055b4  jz      short loc_1800055E2
0x1800055b6  sub     ecx, 1
0x1800055b9  jz      short loc_1800055D2
0x1800055bb  cmp     ecx, 1
0x1800055be  jz      short loc_1800055C9
0x1800055c0  lea     rdi, word_1800321F2
0x1800055c7  jmp     short loc_180005601
0x1800055c9  lea     rdi, aFailfast; "FailFast"
0x1800055d0  jmp     short loc_180005601
0x1800055d2  lea     rax, aLoghr; "LogHr"
0x1800055d9  lea     rdi, aLognt; "LogNt"
0x1800055e0  jmp     short loc_1800055F0
0x1800055e2  lea     rax, aReturnhr; "ReturnHr"
0x1800055e9  lea     rdi, aReturnnt; "ReturnNt"
0x1800055f0  test    [rbx+4], bpl
0x1800055f4  cmovz   rdi, rax
0x1800055f8  jmp     short loc_180005601
0x1800055fa  lea     rdi, aException; "Exception"
0x180005601  xor     edx, edx; Val
0x180005603  mov     r8d, 200h; Size
0x180005609  lea     rcx, [rsp+278h+Buffer]; void *
0x18000560e  call    memset_0
0x180005613  test    [rbx+4], bpl
0x180005617  jz      short loc_18000563C
0x180005619  mov     ebp, [rbx+0Ch]
0x18000561c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005623  test    rax, rax
0x180005626  jz      short loc_18000566C
0x180005628  mov     r8d, 100h
0x18000562e  lea     rdx, [rsp+278h+Buffer]
0x180005633  mov     ecx, ebp
0x180005635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000563a  jmp     short loc_18000566C
0x18000563c  mov     ebp, [rbx+8]
0x18000563f  mov     [rsp+278h+Arguments], r15; Arguments
0x180005644  mov     [rsp+278h+nSize], 100h; nSize
0x18000564c  lea     rax, [rsp+278h+Buffer]
0x180005651  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005656  mov     r9d, 400h; dwLanguageId
0x18000565c  mov     r8d, ebp; dwMessageId
0x18000565f  xor     edx, edx; lpSource
0x180005661  mov     ecx, 1200h; dwFlags
0x180005666  call    cs:__imp_FormatMessageW
0x18000566c  lea     rsi, [r14+rsi*2]
0x180005670  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005674  mov     rax, [rbx+88h]
0x18000567b  mov     rcx, [rbx+80h]
0x180005682  mov     rdx, rsi; unsigned __int16 *
0x180005685  test    r9, r9
0x180005688  jz      short loc_1800056AC
0x18000568a  mov     [rsp+278h+Arguments], rax
0x18000568f  mov     qword ptr [rsp+278h+nSize], rcx
0x180005694  mov     eax, [rbx+40h]
0x180005697  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000569b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800056a2  mov     rcx, r14; this
0x1800056a5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800056aa  jmp     short loc_1800056C3
0x1800056ac  mov     [rsp+278h+lpBuffer], rax
0x1800056b1  mov     r9, rcx; unsigned __int16 *
0x1800056b4  lea     r8, aHsP; "%hs!%p: "
0x1800056bb  mov     rcx, r14; this
0x1800056be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800056c3  mov     r14, rax
0x1800056c6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800056cd  test    r9, r9
0x1800056d0  jz      short loc_1800056E7
0x1800056d2  lea     r8, aCallerP; "(caller: %p) "
0x1800056d9  mov     rdx, rsi; unsigned __int16 *
0x1800056dc  mov     rcx, rax; this
0x1800056df  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800056e4  mov     r14, rax
0x1800056e7  call    cs:__imp_GetCurrentThreadId
0x1800056ed  lea     rcx, [rsp+278h+Buffer]
0x1800056f2  mov     [rsp+278h+var_240], rcx
0x1800056f7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800056fb  mov     [rsp+278h+nSize], eax
0x1800056ff  mov     eax, [rbx+44h]
0x180005702  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005706  mov     r9, rdi; unsigned __int16 *
0x180005709  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005710  mov     rdx, rsi; unsigned __int16 *
0x180005713  mov     rcx, r14; this
0x180005716  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000571b  cmp     [rbx+18h], r15
0x18000571f  jnz     short loc_180005731
0x180005721  cmp     [rbx+48h], r15
0x180005725  jnz     short loc_180005731
0x180005727  cmp     [rbx+30h], r15
0x18000572b  jz      loc_1800057C1
0x180005731  lea     r8, asc_1800322E0; "    "
0x180005738  mov     rdx, rsi; unsigned __int16 *
0x18000573b  mov     rcx, rax; this
0x18000573e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005743  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005747  test    r9, r9
0x18000574a  jz      short loc_18000575E
0x18000574c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005753  mov     rdx, rsi; unsigned __int16 *
0x180005756  mov     rcx, rax; this
0x180005759  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000575e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005762  test    r9, r9
0x180005765  jz      short loc_180005779
0x180005767  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000576e  mov     rdx, rsi; unsigned __int16 *
0x180005771  mov     rcx, rax; this
0x180005774  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005779  mov     rcx, [rbx+28h]
0x18000577d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005781  mov     rdx, rsi; unsigned __int16 *
0x180005784  test    rcx, rcx
0x180005787  jz      short loc_18000579F
0x180005789  mov     [rsp+278h+lpBuffer], rcx
0x18000578e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005795  mov     rcx, rax; this
0x180005798  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000579d  jmp     short loc_1800057C1
0x18000579f  mov     rcx, rax; this
0x1800057a2  test    r9, r9
0x1800057a5  jz      short loc_1800057B5
0x1800057a7  lea     r8, aHs; "[%hs]\n"
0x1800057ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800057b3  jmp     short loc_1800057C1
0x1800057b5  lea     r8, asc_180032358; "\n"
0x1800057bc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800057c1  xor     eax, eax
0x1800057c3  mov     rcx, [rsp+278h+var_38]
0x1800057cb  xor     rcx, rsp; StackCookie
0x1800057ce  call    __security_check_cookie
0x1800057d3  mov     rbx, [rsp+278h+arg_18]
0x1800057db  add     rsp, 250h
0x1800057e2  pop     r15
0x1800057e4  pop     r14
0x1800057e6  pop     rdi
0x1800057e7  pop     rsi
0x1800057e8  pop     rbp
0x1800057e9  retn
```
