# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005584`
- end: `0x18000583a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180003d2c`
- `0x180003fac`
- `0x180005fb0`
- `0x180007b30`
- `0x180008a10`
- `0x180030751`
- `0x180030885`
- `0x180030df9`
- `0x180031076`

## callees

- `0x1800021d0`
- `0x180002b78`
- `0x180005584`
- `0x1800062b0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005737`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005737`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800056b6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800056b6`

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
          v7 = (const char *)&word_180037512;
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
0x180005584  mov     [rsp+arg_18], rbx
0x180005589  push    rbp
0x18000558a  push    rsi
0x18000558b  push    rdi
0x18000558c  push    r14
0x18000558e  push    r15
0x180005590  sub     rsp, 250h
0x180005597  mov     rax, cs:__security_cookie
0x18000559e  xor     rax, rsp
0x1800055a1  mov     [rsp+278h+var_38], rax
0x1800055a9  mov     rbx, r8
0x1800055ac  mov     rsi, rdx
0x1800055af  mov     r14, rcx
0x1800055b2  xor     r15d, r15d
0x1800055b5  test    rdx, rdx
0x1800055b8  jz      loc_180005811
0x1800055be  test    rcx, rcx
0x1800055c1  jz      loc_180005811
0x1800055c7  mov     [rcx], r15w
0x1800055cb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800055d2  test    rax, rax
0x1800055d5  jz      short loc_1800055F8
0x1800055d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800055de  jz      short loc_1800055F8
0x1800055e0  mov     r8, rdx
0x1800055e3  mov     rdx, rcx
0x1800055e6  mov     rcx, rbx
0x1800055e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055ee  cmp     [r14], r15w
0x1800055f2  jnz     loc_180005811
0x1800055f8  mov     ecx, [rbx]
0x1800055fa  mov     bpl, 8
0x1800055fd  test    ecx, ecx
0x1800055ff  jz      short loc_18000564A
0x180005601  sub     ecx, 1
0x180005604  jz      short loc_180005632
0x180005606  sub     ecx, 1
0x180005609  jz      short loc_180005622
0x18000560b  cmp     ecx, 1
0x18000560e  jz      short loc_180005619
0x180005610  lea     rdi, word_180037512
0x180005617  jmp     short loc_180005651
0x180005619  lea     rdi, aFailfast; "FailFast"
0x180005620  jmp     short loc_180005651
0x180005622  lea     rax, aLoghr; "LogHr"
0x180005629  lea     rdi, aLognt; "LogNt"
0x180005630  jmp     short loc_180005640
0x180005632  lea     rax, aReturnhr; "ReturnHr"
0x180005639  lea     rdi, aReturnnt; "ReturnNt"
0x180005640  test    [rbx+4], bpl
0x180005644  cmovz   rdi, rax
0x180005648  jmp     short loc_180005651
0x18000564a  lea     rdi, aException; "Exception"
0x180005651  xor     edx, edx; Val
0x180005653  mov     r8d, 200h; Size
0x180005659  lea     rcx, [rsp+278h+Buffer]; void *
0x18000565e  call    memset_0
0x180005663  test    [rbx+4], bpl
0x180005667  jz      short loc_18000568C
0x180005669  mov     ebp, [rbx+0Ch]
0x18000566c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005673  test    rax, rax
0x180005676  jz      short loc_1800056BC
0x180005678  mov     r8d, 100h
0x18000567e  lea     rdx, [rsp+278h+Buffer]
0x180005683  mov     ecx, ebp
0x180005685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000568a  jmp     short loc_1800056BC
0x18000568c  mov     ebp, [rbx+8]
0x18000568f  mov     [rsp+278h+Arguments], r15; Arguments
0x180005694  mov     [rsp+278h+nSize], 100h; nSize
0x18000569c  lea     rax, [rsp+278h+Buffer]
0x1800056a1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800056a6  mov     r9d, 400h; dwLanguageId
0x1800056ac  mov     r8d, ebp; dwMessageId
0x1800056af  xor     edx, edx; lpSource
0x1800056b1  mov     ecx, 1200h; dwFlags
0x1800056b6  call    cs:__imp_FormatMessageW
0x1800056bc  lea     rsi, [r14+rsi*2]
0x1800056c0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800056c4  mov     rax, [rbx+88h]
0x1800056cb  mov     rcx, [rbx+80h]
0x1800056d2  mov     rdx, rsi; unsigned __int16 *
0x1800056d5  test    r9, r9
0x1800056d8  jz      short loc_1800056FC
0x1800056da  mov     [rsp+278h+Arguments], rax
0x1800056df  mov     qword ptr [rsp+278h+nSize], rcx
0x1800056e4  mov     eax, [rbx+40h]
0x1800056e7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800056eb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800056f2  mov     rcx, r14; this
0x1800056f5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800056fa  jmp     short loc_180005713
0x1800056fc  mov     [rsp+278h+lpBuffer], rax
0x180005701  mov     r9, rcx; unsigned __int16 *
0x180005704  lea     r8, aHsP; "%hs!%p: "
0x18000570b  mov     rcx, r14; this
0x18000570e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005713  mov     r14, rax
0x180005716  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000571d  test    r9, r9
0x180005720  jz      short loc_180005737
0x180005722  lea     r8, aCallerP; "(caller: %p) "
0x180005729  mov     rdx, rsi; unsigned __int16 *
0x18000572c  mov     rcx, rax; this
0x18000572f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005734  mov     r14, rax
0x180005737  call    cs:__imp_GetCurrentThreadId
0x18000573d  lea     rcx, [rsp+278h+Buffer]
0x180005742  mov     [rsp+278h+var_240], rcx
0x180005747  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000574b  mov     [rsp+278h+nSize], eax
0x18000574f  mov     eax, [rbx+44h]
0x180005752  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005756  mov     r9, rdi; unsigned __int16 *
0x180005759  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005760  mov     rdx, rsi; unsigned __int16 *
0x180005763  mov     rcx, r14; this
0x180005766  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000576b  cmp     [rbx+18h], r15
0x18000576f  jnz     short loc_180005781
0x180005771  cmp     [rbx+48h], r15
0x180005775  jnz     short loc_180005781
0x180005777  cmp     [rbx+30h], r15
0x18000577b  jz      loc_180005811
0x180005781  lea     r8, asc_180037600; "    "
0x180005788  mov     rdx, rsi; unsigned __int16 *
0x18000578b  mov     rcx, rax; this
0x18000578e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005793  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005797  test    r9, r9
0x18000579a  jz      short loc_1800057AE
0x18000579c  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800057a3  mov     rdx, rsi; unsigned __int16 *
0x1800057a6  mov     rcx, rax; this
0x1800057a9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800057ae  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800057b2  test    r9, r9
0x1800057b5  jz      short loc_1800057C9
0x1800057b7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800057be  mov     rdx, rsi; unsigned __int16 *
0x1800057c1  mov     rcx, rax; this
0x1800057c4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800057c9  mov     rcx, [rbx+28h]
0x1800057cd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800057d1  mov     rdx, rsi; unsigned __int16 *
0x1800057d4  test    rcx, rcx
0x1800057d7  jz      short loc_1800057EF
0x1800057d9  mov     [rsp+278h+lpBuffer], rcx
0x1800057de  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800057e5  mov     rcx, rax; this
0x1800057e8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800057ed  jmp     short loc_180005811
0x1800057ef  mov     rcx, rax; this
0x1800057f2  test    r9, r9
0x1800057f5  jz      short loc_180005805
0x1800057f7  lea     r8, aHs; "[%hs]\n"
0x1800057fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005803  jmp     short loc_180005811
0x180005805  lea     r8, asc_180037678; "\n"
0x18000580c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005811  xor     eax, eax
0x180005813  mov     rcx, [rsp+278h+var_38]
0x18000581b  xor     rcx, rsp; StackCookie
0x18000581e  call    __security_check_cookie
0x180005823  mov     rbx, [rsp+278h+arg_18]
0x18000582b  add     rsp, 250h
0x180005832  pop     r15
0x180005834  pop     r14
0x180005836  pop     rdi
0x180005837  pop     rsi
0x180005838  pop     rbp
0x180005839  retn
```
