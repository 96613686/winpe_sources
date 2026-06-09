# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005680`
- end: `0x180005936`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000399c`
- `0x180006218`
- `0x180006700`
- `0x180008250`

## callees

- `0x180001a50`
- `0x1800024f0`
- `0x180005680`
- `0x180006518`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005833`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005833`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800057b2`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800057b2`

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
          v7 = (const char *)&word_180013F7A;
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
0x180005680  mov     [rsp+arg_18], rbx
0x180005685  push    rbp
0x180005686  push    rsi
0x180005687  push    rdi
0x180005688  push    r14
0x18000568a  push    r15
0x18000568c  sub     rsp, 250h
0x180005693  mov     rax, cs:__security_cookie
0x18000569a  xor     rax, rsp
0x18000569d  mov     [rsp+278h+var_38], rax
0x1800056a5  mov     rbx, r8
0x1800056a8  mov     rsi, rdx
0x1800056ab  mov     r14, rcx
0x1800056ae  xor     r15d, r15d
0x1800056b1  test    rdx, rdx
0x1800056b4  jz      loc_18000590D
0x1800056ba  test    rcx, rcx
0x1800056bd  jz      loc_18000590D
0x1800056c3  mov     [rcx], r15w
0x1800056c7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800056ce  test    rax, rax
0x1800056d1  jz      short loc_1800056F4
0x1800056d3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800056da  jz      short loc_1800056F4
0x1800056dc  mov     r8, rdx
0x1800056df  mov     rdx, rcx
0x1800056e2  mov     rcx, rbx
0x1800056e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056ea  cmp     [r14], r15w
0x1800056ee  jnz     loc_18000590D
0x1800056f4  mov     ecx, [rbx]
0x1800056f6  mov     bpl, 8
0x1800056f9  test    ecx, ecx
0x1800056fb  jz      short loc_180005746
0x1800056fd  sub     ecx, 1
0x180005700  jz      short loc_18000572E
0x180005702  sub     ecx, 1
0x180005705  jz      short loc_18000571E
0x180005707  cmp     ecx, 1
0x18000570a  jz      short loc_180005715
0x18000570c  lea     rdi, word_180013F7A
0x180005713  jmp     short loc_18000574D
0x180005715  lea     rdi, aFailfast; "FailFast"
0x18000571c  jmp     short loc_18000574D
0x18000571e  lea     rax, aLoghr; "LogHr"
0x180005725  lea     rdi, aLognt; "LogNt"
0x18000572c  jmp     short loc_18000573C
0x18000572e  lea     rax, aReturnhr; "ReturnHr"
0x180005735  lea     rdi, aReturnnt; "ReturnNt"
0x18000573c  test    [rbx+4], bpl
0x180005740  cmovz   rdi, rax
0x180005744  jmp     short loc_18000574D
0x180005746  lea     rdi, aException; "Exception"
0x18000574d  xor     edx, edx; Val
0x18000574f  mov     r8d, 200h; Size
0x180005755  lea     rcx, [rsp+278h+Buffer]; void *
0x18000575a  call    memset_0
0x18000575f  test    [rbx+4], bpl
0x180005763  jz      short loc_180005788
0x180005765  mov     ebp, [rbx+0Ch]
0x180005768  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000576f  test    rax, rax
0x180005772  jz      short loc_1800057B8
0x180005774  mov     r8d, 100h
0x18000577a  lea     rdx, [rsp+278h+Buffer]
0x18000577f  mov     ecx, ebp
0x180005781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005786  jmp     short loc_1800057B8
0x180005788  mov     ebp, [rbx+8]
0x18000578b  mov     [rsp+278h+Arguments], r15; Arguments
0x180005790  mov     [rsp+278h+nSize], 100h; nSize
0x180005798  lea     rax, [rsp+278h+Buffer]
0x18000579d  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800057a2  mov     r9d, 400h; dwLanguageId
0x1800057a8  mov     r8d, ebp; dwMessageId
0x1800057ab  xor     edx, edx; lpSource
0x1800057ad  mov     ecx, 1200h; dwFlags
0x1800057b2  call    cs:__imp_FormatMessageW
0x1800057b8  lea     rsi, [r14+rsi*2]
0x1800057bc  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800057c0  mov     rax, [rbx+88h]
0x1800057c7  mov     rcx, [rbx+80h]
0x1800057ce  mov     rdx, rsi; unsigned __int16 *
0x1800057d1  test    r9, r9
0x1800057d4  jz      short loc_1800057F8
0x1800057d6  mov     [rsp+278h+Arguments], rax
0x1800057db  mov     qword ptr [rsp+278h+nSize], rcx
0x1800057e0  mov     eax, [rbx+40h]
0x1800057e3  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800057e7  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800057ee  mov     rcx, r14; this
0x1800057f1  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800057f6  jmp     short loc_18000580F
0x1800057f8  mov     [rsp+278h+lpBuffer], rax
0x1800057fd  mov     r9, rcx; unsigned __int16 *
0x180005800  lea     r8, aHsP; "%hs!%p: "
0x180005807  mov     rcx, r14; this
0x18000580a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000580f  mov     r14, rax
0x180005812  mov     r9, [rbx+90h]; unsigned __int16 *
0x180005819  test    r9, r9
0x18000581c  jz      short loc_180005833
0x18000581e  lea     r8, aCallerP; "(caller: %p) "
0x180005825  mov     rdx, rsi; unsigned __int16 *
0x180005828  mov     rcx, rax; this
0x18000582b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005830  mov     r14, rax
0x180005833  call    cs:__imp_GetCurrentThreadId
0x180005839  lea     rcx, [rsp+278h+Buffer]
0x18000583e  mov     [rsp+278h+var_240], rcx
0x180005843  mov     dword ptr [rsp+278h+Arguments], ebp
0x180005847  mov     [rsp+278h+nSize], eax
0x18000584b  mov     eax, [rbx+44h]
0x18000584e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005852  mov     r9, rdi; unsigned __int16 *
0x180005855  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000585c  mov     rdx, rsi; unsigned __int16 *
0x18000585f  mov     rcx, r14; this
0x180005862  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005867  cmp     [rbx+18h], r15
0x18000586b  jnz     short loc_18000587D
0x18000586d  cmp     [rbx+48h], r15
0x180005871  jnz     short loc_18000587D
0x180005873  cmp     [rbx+30h], r15
0x180005877  jz      loc_18000590D
0x18000587d  lea     r8, asc_180014068; "    "
0x180005884  mov     rdx, rsi; unsigned __int16 *
0x180005887  mov     rcx, rax; this
0x18000588a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000588f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005893  test    r9, r9
0x180005896  jz      short loc_1800058AA
0x180005898  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000589f  mov     rdx, rsi; unsigned __int16 *
0x1800058a2  mov     rcx, rax; this
0x1800058a5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800058aa  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800058ae  test    r9, r9
0x1800058b1  jz      short loc_1800058C5
0x1800058b3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800058ba  mov     rdx, rsi; unsigned __int16 *
0x1800058bd  mov     rcx, rax; this
0x1800058c0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800058c5  mov     rcx, [rbx+28h]
0x1800058c9  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800058cd  mov     rdx, rsi; unsigned __int16 *
0x1800058d0  test    rcx, rcx
0x1800058d3  jz      short loc_1800058EB
0x1800058d5  mov     [rsp+278h+lpBuffer], rcx
0x1800058da  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800058e1  mov     rcx, rax; this
0x1800058e4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800058e9  jmp     short loc_18000590D
0x1800058eb  mov     rcx, rax; this
0x1800058ee  test    r9, r9
0x1800058f1  jz      short loc_180005901
0x1800058f3  lea     r8, aHs; "[%hs]\n"
0x1800058fa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800058ff  jmp     short loc_18000590D
0x180005901  lea     r8, asc_1800140E0; "\n"
0x180005908  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000590d  xor     eax, eax
0x18000590f  mov     rcx, [rsp+278h+var_38]
0x180005917  xor     rcx, rsp; StackCookie
0x18000591a  call    __security_check_cookie
0x18000591f  mov     rbx, [rsp+278h+arg_18]
0x180005927  add     rsp, 250h
0x18000592e  pop     r15
0x180005930  pop     r14
0x180005932  pop     rdi
0x180005933  pop     rsi
0x180005934  pop     rbp
0x180005935  retn
```
