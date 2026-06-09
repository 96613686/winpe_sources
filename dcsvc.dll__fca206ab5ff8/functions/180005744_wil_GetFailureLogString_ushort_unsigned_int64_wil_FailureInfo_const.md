# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005744`
- end: `0x1800059fa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800031bc`
- `0x180003424`
- `0x1800062f8`
- `0x18000a350`

## callees

- `0x180001cf0`
- `0x1800026c8`
- `0x180005744`
- `0x1800065f8`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005876`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005876`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800058f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800058f7`

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
          v7 = (const char *)&qword_1800162C0;
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
0x180005744  mov     [rsp+arg_18], rbx
0x180005749  push    rbp
0x18000574a  push    rsi
0x18000574b  push    rdi
0x18000574c  push    r14
0x18000574e  push    r15
0x180005750  sub     rsp, 250h
0x180005757  mov     rax, cs:__security_cookie
0x18000575e  xor     rax, rsp
0x180005761  mov     [rsp+278h+var_38], rax
0x180005769  mov     rbx, r8
0x18000576c  mov     rsi, rdx
0x18000576f  mov     r14, rcx
0x180005772  xor     r15d, r15d
0x180005775  test    rdx, rdx
0x180005778  jz      loc_1800059D1
0x18000577e  test    rcx, rcx
0x180005781  jz      loc_1800059D1
0x180005787  mov     [rcx], r15w
0x18000578b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005792  test    rax, rax
0x180005795  jz      short loc_1800057B8
0x180005797  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000579e  jz      short loc_1800057B8
0x1800057a0  mov     r8, rdx
0x1800057a3  mov     rdx, rcx
0x1800057a6  mov     rcx, rbx
0x1800057a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057ae  cmp     [r14], r15w
0x1800057b2  jnz     loc_1800059D1
0x1800057b8  mov     ecx, [rbx]
0x1800057ba  mov     bpl, 8
0x1800057bd  test    ecx, ecx
0x1800057bf  jz      short loc_18000580A
0x1800057c1  sub     ecx, 1
0x1800057c4  jz      short loc_1800057F2
0x1800057c6  sub     ecx, 1
0x1800057c9  jz      short loc_1800057E2
0x1800057cb  cmp     ecx, 1
0x1800057ce  jz      short loc_1800057D9
0x1800057d0  lea     rdi, qword_1800162C0
0x1800057d7  jmp     short loc_180005811
0x1800057d9  lea     rdi, aFailfast; "FailFast"
0x1800057e0  jmp     short loc_180005811
0x1800057e2  lea     rax, aLoghr; "LogHr"
0x1800057e9  lea     rdi, aLognt; "LogNt"
0x1800057f0  jmp     short loc_180005800
0x1800057f2  lea     rax, aReturnhr; "ReturnHr"
0x1800057f9  lea     rdi, aReturnnt; "ReturnNt"
0x180005800  test    [rbx+4], bpl
0x180005804  cmovz   rdi, rax
0x180005808  jmp     short loc_180005811
0x18000580a  lea     rdi, aException; "Exception"
0x180005811  xor     edx, edx; Val
0x180005813  mov     r8d, 200h; Size
0x180005819  lea     rcx, [rsp+278h+Buffer]; void *
0x18000581e  call    memset_0
0x180005823  test    [rbx+4], bpl
0x180005827  jz      short loc_18000584C
0x180005829  mov     ebp, [rbx+0Ch]
0x18000582c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005833  test    rax, rax
0x180005836  jz      short loc_18000587C
0x180005838  mov     r8d, 100h
0x18000583e  lea     rdx, [rsp+278h+Buffer]
0x180005843  mov     ecx, ebp
0x180005845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000584a  jmp     short loc_18000587C
0x18000584c  mov     ebp, [rbx+8]
0x18000584f  mov     [rsp+278h+Arguments], r15; Arguments
0x180005854  mov     [rsp+278h+nSize], 100h; nSize
0x18000585c  lea     rax, [rsp+278h+Buffer]
0x180005861  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005866  mov     r9d, 400h; dwLanguageId
0x18000586c  mov     r8d, ebp; dwMessageId
0x18000586f  xor     edx, edx; lpSource
0x180005871  mov     ecx, 1200h; dwFlags
0x180005876  call    cs:__imp_FormatMessageW
0x18000587c  lea     rsi, [r14+rsi*2]
0x180005880  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005884  mov     rax, [rbx+88h]
0x18000588b  mov     rcx, [rbx+80h]
0x180005892  mov     rdx, rsi; unsigned __int16 *
0x180005895  test    r9, r9
0x180005898  jz      short loc_1800058BC
0x18000589a  mov     [rsp+278h+Arguments], rax
0x18000589f  mov     qword ptr [rsp+278h+nSize], rcx
0x1800058a4  mov     eax, [rbx+40h]
0x1800058a7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800058ab  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800058b2  mov     rcx, r14; this
0x1800058b5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800058ba  jmp     short loc_1800058D3
0x1800058bc  mov     [rsp+278h+lpBuffer], rax
0x1800058c1  mov     r9, rcx; unsigned __int16 *
0x1800058c4  lea     r8, aHsP; "%hs!%p: "
0x1800058cb  mov     rcx, r14; this
0x1800058ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800058d3  mov     r14, rax
0x1800058d6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800058dd  test    r9, r9
0x1800058e0  jz      short loc_1800058F7
0x1800058e2  lea     r8, aCallerP; "(caller: %p) "
0x1800058e9  mov     rdx, rsi; unsigned __int16 *
0x1800058ec  mov     rcx, rax; this
0x1800058ef  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800058f4  mov     r14, rax
0x1800058f7  call    cs:__imp_GetCurrentThreadId
0x1800058fd  lea     rcx, [rsp+278h+Buffer]
0x180005902  mov     [rsp+278h+var_240], rcx
0x180005907  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000590b  mov     [rsp+278h+nSize], eax
0x18000590f  mov     eax, [rbx+44h]
0x180005912  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005916  mov     r9, rdi; unsigned __int16 *
0x180005919  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005920  mov     rdx, rsi; unsigned __int16 *
0x180005923  mov     rcx, r14; this
0x180005926  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000592b  cmp     [rbx+18h], r15
0x18000592f  jnz     short loc_180005941
0x180005931  cmp     [rbx+48h], r15
0x180005935  jnz     short loc_180005941
0x180005937  cmp     [rbx+30h], r15
0x18000593b  jz      loc_1800059D1
0x180005941  lea     r8, asc_180015BB8; "    "
0x180005948  mov     rdx, rsi; unsigned __int16 *
0x18000594b  mov     rcx, rax; this
0x18000594e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005953  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005957  test    r9, r9
0x18000595a  jz      short loc_18000596E
0x18000595c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005963  mov     rdx, rsi; unsigned __int16 *
0x180005966  mov     rcx, rax; this
0x180005969  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000596e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005972  test    r9, r9
0x180005975  jz      short loc_180005989
0x180005977  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000597e  mov     rdx, rsi; unsigned __int16 *
0x180005981  mov     rcx, rax; this
0x180005984  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005989  mov     rcx, [rbx+28h]
0x18000598d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005991  mov     rdx, rsi; unsigned __int16 *
0x180005994  test    rcx, rcx
0x180005997  jz      short loc_1800059AF
0x180005999  mov     [rsp+278h+lpBuffer], rcx
0x18000599e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800059a5  mov     rcx, rax; this
0x1800059a8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800059ad  jmp     short loc_1800059D1
0x1800059af  mov     rcx, rax; this
0x1800059b2  test    r9, r9
0x1800059b5  jz      short loc_1800059C5
0x1800059b7  lea     r8, aHs; "[%hs]\n"
0x1800059be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800059c3  jmp     short loc_1800059D1
0x1800059c5  lea     r8, asc_180015C30; "\n"
0x1800059cc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800059d1  xor     eax, eax
0x1800059d3  mov     rcx, [rsp+278h+var_38]
0x1800059db  xor     rcx, rsp; StackCookie
0x1800059de  call    __security_check_cookie
0x1800059e3  mov     rbx, [rsp+278h+arg_18]
0x1800059eb  add     rsp, 250h
0x1800059f2  pop     r15
0x1800059f4  pop     r14
0x1800059f6  pop     rdi
0x1800059f7  pop     rsi
0x1800059f8  pop     rbp
0x1800059f9  retn
```
