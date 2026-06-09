# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005144`
- end: `0x1800053fa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180005b68`
- `0x180005ff0`
- `0x1800073c0`

## callees

- `0x1800023e0`
- `0x180002e14`
- `0x180005144`
- `0x180005e64`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800052f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800052f7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005276`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005276`

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
          v7 = (const char *)&word_1800B6B6A;
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
0x180005144  mov     [rsp+arg_18], rbx
0x180005149  push    rbp
0x18000514a  push    rsi
0x18000514b  push    rdi
0x18000514c  push    r14
0x18000514e  push    r15
0x180005150  sub     rsp, 250h
0x180005157  mov     rax, cs:__security_cookie
0x18000515e  xor     rax, rsp
0x180005161  mov     [rsp+278h+var_38], rax
0x180005169  mov     rbx, r8
0x18000516c  mov     rsi, rdx
0x18000516f  mov     r14, rcx
0x180005172  xor     r15d, r15d
0x180005175  test    rdx, rdx
0x180005178  jz      loc_1800053D1
0x18000517e  test    rcx, rcx
0x180005181  jz      loc_1800053D1
0x180005187  mov     [rcx], r15w
0x18000518b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005192  test    rax, rax
0x180005195  jz      short loc_1800051B8
0x180005197  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000519e  jz      short loc_1800051B8
0x1800051a0  mov     r8, rdx
0x1800051a3  mov     rdx, rcx
0x1800051a6  mov     rcx, rbx
0x1800051a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051ae  cmp     [r14], r15w
0x1800051b2  jnz     loc_1800053D1
0x1800051b8  mov     ecx, [rbx]
0x1800051ba  mov     bpl, 8
0x1800051bd  test    ecx, ecx
0x1800051bf  jz      short loc_18000520A
0x1800051c1  sub     ecx, 1
0x1800051c4  jz      short loc_1800051F2
0x1800051c6  sub     ecx, 1
0x1800051c9  jz      short loc_1800051E2
0x1800051cb  cmp     ecx, 1
0x1800051ce  jz      short loc_1800051D9
0x1800051d0  lea     rdi, word_1800B6B6A
0x1800051d7  jmp     short loc_180005211
0x1800051d9  lea     rdi, aFailfast; "FailFast"
0x1800051e0  jmp     short loc_180005211
0x1800051e2  lea     rax, aLoghr; "LogHr"
0x1800051e9  lea     rdi, aLognt; "LogNt"
0x1800051f0  jmp     short loc_180005200
0x1800051f2  lea     rax, aReturnhr; "ReturnHr"
0x1800051f9  lea     rdi, aReturnnt; "ReturnNt"
0x180005200  test    [rbx+4], bpl
0x180005204  cmovz   rdi, rax
0x180005208  jmp     short loc_180005211
0x18000520a  lea     rdi, aException; "Exception"
0x180005211  xor     edx, edx; Val
0x180005213  mov     r8d, 200h; Size
0x180005219  lea     rcx, [rsp+278h+Buffer]; void *
0x18000521e  call    memset_0
0x180005223  test    [rbx+4], bpl
0x180005227  jz      short loc_18000524C
0x180005229  mov     ebp, [rbx+0Ch]
0x18000522c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005233  test    rax, rax
0x180005236  jz      short loc_18000527C
0x180005238  mov     r8d, 100h
0x18000523e  lea     rdx, [rsp+278h+Buffer]
0x180005243  mov     ecx, ebp
0x180005245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000524a  jmp     short loc_18000527C
0x18000524c  mov     ebp, [rbx+8]
0x18000524f  mov     [rsp+278h+Arguments], r15; Arguments
0x180005254  mov     [rsp+278h+nSize], 100h; nSize
0x18000525c  lea     rax, [rsp+278h+Buffer]
0x180005261  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005266  mov     r9d, 400h; dwLanguageId
0x18000526c  mov     r8d, ebp; dwMessageId
0x18000526f  xor     edx, edx; lpSource
0x180005271  mov     ecx, 1200h; dwFlags
0x180005276  call    cs:__imp_FormatMessageW
0x18000527c  lea     rsi, [r14+rsi*2]
0x180005280  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005284  mov     rax, [rbx+88h]
0x18000528b  mov     rcx, [rbx+80h]
0x180005292  mov     rdx, rsi; unsigned __int16 *
0x180005295  test    r9, r9
0x180005298  jz      short loc_1800052BC
0x18000529a  mov     [rsp+278h+Arguments], rax
0x18000529f  mov     qword ptr [rsp+278h+nSize], rcx
0x1800052a4  mov     eax, [rbx+40h]
0x1800052a7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800052ab  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800052b2  mov     rcx, r14; this
0x1800052b5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800052ba  jmp     short loc_1800052D3
0x1800052bc  mov     [rsp+278h+lpBuffer], rax
0x1800052c1  mov     r9, rcx; unsigned __int16 *
0x1800052c4  lea     r8, aHsP; "%hs!%p: "
0x1800052cb  mov     rcx, r14; this
0x1800052ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800052d3  mov     r14, rax
0x1800052d6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800052dd  test    r9, r9
0x1800052e0  jz      short loc_1800052F7
0x1800052e2  lea     r8, aCallerP; "(caller: %p) "
0x1800052e9  mov     rdx, rsi; unsigned __int16 *
0x1800052ec  mov     rcx, rax; this
0x1800052ef  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800052f4  mov     r14, rax
0x1800052f7  call    cs:__imp_GetCurrentThreadId
0x1800052fd  lea     rcx, [rsp+278h+Buffer]
0x180005302  mov     [rsp+278h+var_240], rcx
0x180005307  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000530b  mov     [rsp+278h+nSize], eax
0x18000530f  mov     eax, [rbx+44h]
0x180005312  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005316  mov     r9, rdi; unsigned __int16 *
0x180005319  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005320  mov     rdx, rsi; unsigned __int16 *
0x180005323  mov     rcx, r14; this
0x180005326  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000532b  cmp     [rbx+18h], r15
0x18000532f  jnz     short loc_180005341
0x180005331  cmp     [rbx+48h], r15
0x180005335  jnz     short loc_180005341
0x180005337  cmp     [rbx+30h], r15
0x18000533b  jz      loc_1800053D1
0x180005341  lea     r8, asc_1800B6C58; "    "
0x180005348  mov     rdx, rsi; unsigned __int16 *
0x18000534b  mov     rcx, rax; this
0x18000534e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005353  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005357  test    r9, r9
0x18000535a  jz      short loc_18000536E
0x18000535c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005363  mov     rdx, rsi; unsigned __int16 *
0x180005366  mov     rcx, rax; this
0x180005369  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000536e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005372  test    r9, r9
0x180005375  jz      short loc_180005389
0x180005377  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000537e  mov     rdx, rsi; unsigned __int16 *
0x180005381  mov     rcx, rax; this
0x180005384  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005389  mov     rcx, [rbx+28h]
0x18000538d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005391  mov     rdx, rsi; unsigned __int16 *
0x180005394  test    rcx, rcx
0x180005397  jz      short loc_1800053AF
0x180005399  mov     [rsp+278h+lpBuffer], rcx
0x18000539e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800053a5  mov     rcx, rax; this
0x1800053a8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800053ad  jmp     short loc_1800053D1
0x1800053af  mov     rcx, rax; this
0x1800053b2  test    r9, r9
0x1800053b5  jz      short loc_1800053C5
0x1800053b7  lea     r8, aHs; "[%hs]\n"
0x1800053be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800053c3  jmp     short loc_1800053D1
0x1800053c5  lea     r8, asc_1800B6CD0; "\n"
0x1800053cc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800053d1  xor     eax, eax
0x1800053d3  mov     rcx, [rsp+278h+var_38]
0x1800053db  xor     rcx, rsp; StackCookie
0x1800053de  call    __security_check_cookie
0x1800053e3  mov     rbx, [rsp+278h+arg_18]
0x1800053eb  add     rsp, 250h
0x1800053f2  pop     r15
0x1800053f4  pop     r14
0x1800053f6  pop     rdi
0x1800053f7  pop     rsi
0x1800053f8  pop     rbp
0x1800053f9  retn
```
