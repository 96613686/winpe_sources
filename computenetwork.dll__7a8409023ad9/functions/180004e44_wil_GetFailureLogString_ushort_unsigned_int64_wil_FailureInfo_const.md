# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004e44`
- end: `0x1800050fa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x1800034f0`
- `0x180003770`
- `0x180003a3c`
- `0x1800060f0`
- `0x1800079f0`
- `0x18000d588`
- `0x18000d6bc`

## callees

- `0x180001600`
- `0x180002062`
- `0x180004e44`
- `0x1800063f0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ff7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ff7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004f76`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004f76`

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
          v7 = (const char *)&byte_18001233F;
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
0x180004e44  mov     [rsp+arg_18], rbx
0x180004e49  push    rbp
0x180004e4a  push    rsi
0x180004e4b  push    rdi
0x180004e4c  push    r14
0x180004e4e  push    r15
0x180004e50  sub     rsp, 250h
0x180004e57  mov     rax, cs:__security_cookie
0x180004e5e  xor     rax, rsp
0x180004e61  mov     [rsp+278h+var_38], rax
0x180004e69  mov     rbx, r8
0x180004e6c  mov     rsi, rdx
0x180004e6f  mov     r14, rcx
0x180004e72  xor     r15d, r15d
0x180004e75  test    rdx, rdx
0x180004e78  jz      loc_1800050D1
0x180004e7e  test    rcx, rcx
0x180004e81  jz      loc_1800050D1
0x180004e87  mov     [rcx], r15w
0x180004e8b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004e92  test    rax, rax
0x180004e95  jz      short loc_180004EB8
0x180004e97  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004e9e  jz      short loc_180004EB8
0x180004ea0  mov     r8, rdx
0x180004ea3  mov     rdx, rcx
0x180004ea6  mov     rcx, rbx
0x180004ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eae  cmp     [r14], r15w
0x180004eb2  jnz     loc_1800050D1
0x180004eb8  mov     ecx, [rbx]
0x180004eba  mov     bpl, 8
0x180004ebd  test    ecx, ecx
0x180004ebf  jz      short loc_180004F0A
0x180004ec1  sub     ecx, 1
0x180004ec4  jz      short loc_180004EF2
0x180004ec6  sub     ecx, 1
0x180004ec9  jz      short loc_180004EE2
0x180004ecb  cmp     ecx, 1
0x180004ece  jz      short loc_180004ED9
0x180004ed0  lea     rdi, byte_18001233F
0x180004ed7  jmp     short loc_180004F11
0x180004ed9  lea     rdi, aFailfast; "FailFast"
0x180004ee0  jmp     short loc_180004F11
0x180004ee2  lea     rax, aLoghr; "LogHr"
0x180004ee9  lea     rdi, aLognt; "LogNt"
0x180004ef0  jmp     short loc_180004F00
0x180004ef2  lea     rax, aReturnhr; "ReturnHr"
0x180004ef9  lea     rdi, aReturnnt; "ReturnNt"
0x180004f00  test    [rbx+4], bpl
0x180004f04  cmovz   rdi, rax
0x180004f08  jmp     short loc_180004F11
0x180004f0a  lea     rdi, aException; "Exception"
0x180004f11  xor     edx, edx; Val
0x180004f13  mov     r8d, 200h; Size
0x180004f19  lea     rcx, [rsp+278h+Buffer]; void *
0x180004f1e  call    memset_0
0x180004f23  test    [rbx+4], bpl
0x180004f27  jz      short loc_180004F4C
0x180004f29  mov     ebp, [rbx+0Ch]
0x180004f2c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004f33  test    rax, rax
0x180004f36  jz      short loc_180004F7C
0x180004f38  mov     r8d, 100h
0x180004f3e  lea     rdx, [rsp+278h+Buffer]
0x180004f43  mov     ecx, ebp
0x180004f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f4a  jmp     short loc_180004F7C
0x180004f4c  mov     ebp, [rbx+8]
0x180004f4f  mov     [rsp+278h+Arguments], r15; Arguments
0x180004f54  mov     [rsp+278h+nSize], 100h; nSize
0x180004f5c  lea     rax, [rsp+278h+Buffer]
0x180004f61  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004f66  mov     r9d, 400h; dwLanguageId
0x180004f6c  mov     r8d, ebp; dwMessageId
0x180004f6f  xor     edx, edx; lpSource
0x180004f71  mov     ecx, 1200h; dwFlags
0x180004f76  call    cs:__imp_FormatMessageW
0x180004f7c  lea     rsi, [r14+rsi*2]
0x180004f80  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004f84  mov     rax, [rbx+88h]
0x180004f8b  mov     rcx, [rbx+80h]
0x180004f92  mov     rdx, rsi; unsigned __int16 *
0x180004f95  test    r9, r9
0x180004f98  jz      short loc_180004FBC
0x180004f9a  mov     [rsp+278h+Arguments], rax
0x180004f9f  mov     qword ptr [rsp+278h+nSize], rcx
0x180004fa4  mov     eax, [rbx+40h]
0x180004fa7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004fab  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004fb2  mov     rcx, r14; this
0x180004fb5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004fba  jmp     short loc_180004FD3
0x180004fbc  mov     [rsp+278h+lpBuffer], rax
0x180004fc1  mov     r9, rcx; unsigned __int16 *
0x180004fc4  lea     r8, aHsP; "%hs!%p: "
0x180004fcb  mov     rcx, r14; this
0x180004fce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004fd3  mov     r14, rax
0x180004fd6  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004fdd  test    r9, r9
0x180004fe0  jz      short loc_180004FF7
0x180004fe2  lea     r8, aCallerP; "(caller: %p) "
0x180004fe9  mov     rdx, rsi; unsigned __int16 *
0x180004fec  mov     rcx, rax; this
0x180004fef  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004ff4  mov     r14, rax
0x180004ff7  call    cs:__imp_GetCurrentThreadId
0x180004ffd  lea     rcx, [rsp+278h+Buffer]
0x180005002  mov     [rsp+278h+var_240], rcx
0x180005007  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000500b  mov     [rsp+278h+nSize], eax
0x18000500f  mov     eax, [rbx+44h]
0x180005012  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005016  mov     r9, rdi; unsigned __int16 *
0x180005019  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005020  mov     rdx, rsi; unsigned __int16 *
0x180005023  mov     rcx, r14; this
0x180005026  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000502b  cmp     [rbx+18h], r15
0x18000502f  jnz     short loc_180005041
0x180005031  cmp     [rbx+48h], r15
0x180005035  jnz     short loc_180005041
0x180005037  cmp     [rbx+30h], r15
0x18000503b  jz      loc_1800050D1
0x180005041  lea     r8, asc_180012440; "    "
0x180005048  mov     rdx, rsi; unsigned __int16 *
0x18000504b  mov     rcx, rax; this
0x18000504e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005053  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005057  test    r9, r9
0x18000505a  jz      short loc_18000506E
0x18000505c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005063  mov     rdx, rsi; unsigned __int16 *
0x180005066  mov     rcx, rax; this
0x180005069  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000506e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005072  test    r9, r9
0x180005075  jz      short loc_180005089
0x180005077  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000507e  mov     rdx, rsi; unsigned __int16 *
0x180005081  mov     rcx, rax; this
0x180005084  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005089  mov     rcx, [rbx+28h]
0x18000508d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005091  mov     rdx, rsi; unsigned __int16 *
0x180005094  test    rcx, rcx
0x180005097  jz      short loc_1800050AF
0x180005099  mov     [rsp+278h+lpBuffer], rcx
0x18000509e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800050a5  mov     rcx, rax; this
0x1800050a8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800050ad  jmp     short loc_1800050D1
0x1800050af  mov     rcx, rax; this
0x1800050b2  test    r9, r9
0x1800050b5  jz      short loc_1800050C5
0x1800050b7  lea     r8, aHs; "[%hs]\n"
0x1800050be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800050c3  jmp     short loc_1800050D1
0x1800050c5  lea     r8, asc_1800124B8; "\n"
0x1800050cc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800050d1  xor     eax, eax
0x1800050d3  mov     rcx, [rsp+278h+var_38]
0x1800050db  xor     rcx, rsp; StackCookie
0x1800050de  call    __security_check_cookie
0x1800050e3  mov     rbx, [rsp+278h+arg_18]
0x1800050eb  add     rsp, 250h
0x1800050f2  pop     r15
0x1800050f4  pop     r14
0x1800050f6  pop     rdi
0x1800050f7  pop     rsi
0x1800050f8  pop     rbp
0x1800050f9  retn
```
