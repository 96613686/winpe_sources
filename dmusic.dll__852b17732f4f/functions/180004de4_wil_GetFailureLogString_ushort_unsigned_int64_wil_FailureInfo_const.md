# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004de4`
- end: `0x18000509a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000286c`
- `0x180002ad4`
- `0x180005918`
- `0x1800090f0`

## callees

- `0x1800016d0`
- `0x1800021a8`
- `0x180004de4`
- `0x180005c18`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f97`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004f16`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004f16`

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
          v7 = (const char *)&dword_180024F9C;
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
0x180004de4  mov     [rsp+arg_18], rbx
0x180004de9  push    rbp
0x180004dea  push    rsi
0x180004deb  push    rdi
0x180004dec  push    r14
0x180004dee  push    r15
0x180004df0  sub     rsp, 250h
0x180004df7  mov     rax, cs:__security_cookie
0x180004dfe  xor     rax, rsp
0x180004e01  mov     [rsp+278h+var_38], rax
0x180004e09  mov     rbx, r8
0x180004e0c  mov     rsi, rdx
0x180004e0f  mov     r14, rcx
0x180004e12  xor     r15d, r15d
0x180004e15  test    rdx, rdx
0x180004e18  jz      loc_180005071
0x180004e1e  test    rcx, rcx
0x180004e21  jz      loc_180005071
0x180004e27  mov     [rcx], r15w
0x180004e2b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004e32  test    rax, rax
0x180004e35  jz      short loc_180004E58
0x180004e37  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004e3e  jz      short loc_180004E58
0x180004e40  mov     r8, rdx
0x180004e43  mov     rdx, rcx
0x180004e46  mov     rcx, rbx
0x180004e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e4e  cmp     [r14], r15w
0x180004e52  jnz     loc_180005071
0x180004e58  mov     ecx, [rbx]
0x180004e5a  mov     bpl, 8
0x180004e5d  test    ecx, ecx
0x180004e5f  jz      short loc_180004EAA
0x180004e61  sub     ecx, 1
0x180004e64  jz      short loc_180004E92
0x180004e66  sub     ecx, 1
0x180004e69  jz      short loc_180004E82
0x180004e6b  cmp     ecx, 1
0x180004e6e  jz      short loc_180004E79
0x180004e70  lea     rdi, dword_180024F9C
0x180004e77  jmp     short loc_180004EB1
0x180004e79  lea     rdi, aFailfast; "FailFast"
0x180004e80  jmp     short loc_180004EB1
0x180004e82  lea     rax, aLoghr; "LogHr"
0x180004e89  lea     rdi, aLognt; "LogNt"
0x180004e90  jmp     short loc_180004EA0
0x180004e92  lea     rax, aReturnhr; "ReturnHr"
0x180004e99  lea     rdi, aReturnnt; "ReturnNt"
0x180004ea0  test    [rbx+4], bpl
0x180004ea4  cmovz   rdi, rax
0x180004ea8  jmp     short loc_180004EB1
0x180004eaa  lea     rdi, aException; "Exception"
0x180004eb1  xor     edx, edx; Val
0x180004eb3  mov     r8d, 200h; Size
0x180004eb9  lea     rcx, [rsp+278h+Buffer]; void *
0x180004ebe  call    memset_0
0x180004ec3  test    [rbx+4], bpl
0x180004ec7  jz      short loc_180004EEC
0x180004ec9  mov     ebp, [rbx+0Ch]
0x180004ecc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004ed3  test    rax, rax
0x180004ed6  jz      short loc_180004F1C
0x180004ed8  mov     r8d, 100h
0x180004ede  lea     rdx, [rsp+278h+Buffer]
0x180004ee3  mov     ecx, ebp
0x180004ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eea  jmp     short loc_180004F1C
0x180004eec  mov     ebp, [rbx+8]
0x180004eef  mov     [rsp+278h+Arguments], r15; Arguments
0x180004ef4  mov     [rsp+278h+nSize], 100h; nSize
0x180004efc  lea     rax, [rsp+278h+Buffer]
0x180004f01  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004f06  mov     r9d, 400h; dwLanguageId
0x180004f0c  mov     r8d, ebp; dwMessageId
0x180004f0f  xor     edx, edx; lpSource
0x180004f11  mov     ecx, 1200h; dwFlags
0x180004f16  call    cs:__imp_FormatMessageW
0x180004f1c  lea     rsi, [r14+rsi*2]
0x180004f20  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004f24  mov     rax, [rbx+88h]
0x180004f2b  mov     rcx, [rbx+80h]
0x180004f32  mov     rdx, rsi; unsigned __int16 *
0x180004f35  test    r9, r9
0x180004f38  jz      short loc_180004F5C
0x180004f3a  mov     [rsp+278h+Arguments], rax
0x180004f3f  mov     qword ptr [rsp+278h+nSize], rcx
0x180004f44  mov     eax, [rbx+40h]
0x180004f47  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004f4b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004f52  mov     rcx, r14; this
0x180004f55  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f5a  jmp     short loc_180004F73
0x180004f5c  mov     [rsp+278h+lpBuffer], rax
0x180004f61  mov     r9, rcx; unsigned __int16 *
0x180004f64  lea     r8, aHsP; "%hs!%p: "
0x180004f6b  mov     rcx, r14; this
0x180004f6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f73  mov     r14, rax
0x180004f76  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004f7d  test    r9, r9
0x180004f80  jz      short loc_180004F97
0x180004f82  lea     r8, aCallerP; "(caller: %p) "
0x180004f89  mov     rdx, rsi; unsigned __int16 *
0x180004f8c  mov     rcx, rax; this
0x180004f8f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f94  mov     r14, rax
0x180004f97  call    cs:__imp_GetCurrentThreadId
0x180004f9d  lea     rcx, [rsp+278h+Buffer]
0x180004fa2  mov     [rsp+278h+var_240], rcx
0x180004fa7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004fab  mov     [rsp+278h+nSize], eax
0x180004faf  mov     eax, [rbx+44h]
0x180004fb2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004fb6  mov     r9, rdi; unsigned __int16 *
0x180004fb9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004fc0  mov     rdx, rsi; unsigned __int16 *
0x180004fc3  mov     rcx, r14; this
0x180004fc6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004fcb  cmp     [rbx+18h], r15
0x180004fcf  jnz     short loc_180004FE1
0x180004fd1  cmp     [rbx+48h], r15
0x180004fd5  jnz     short loc_180004FE1
0x180004fd7  cmp     [rbx+30h], r15
0x180004fdb  jz      loc_180005071
0x180004fe1  lea     r8, asc_1800250A0; "    "
0x180004fe8  mov     rdx, rsi; unsigned __int16 *
0x180004feb  mov     rcx, rax; this
0x180004fee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004ff3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004ff7  test    r9, r9
0x180004ffa  jz      short loc_18000500E
0x180004ffc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005003  mov     rdx, rsi; unsigned __int16 *
0x180005006  mov     rcx, rax; this
0x180005009  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000500e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005012  test    r9, r9
0x180005015  jz      short loc_180005029
0x180005017  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000501e  mov     rdx, rsi; unsigned __int16 *
0x180005021  mov     rcx, rax; this
0x180005024  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005029  mov     rcx, [rbx+28h]
0x18000502d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005031  mov     rdx, rsi; unsigned __int16 *
0x180005034  test    rcx, rcx
0x180005037  jz      short loc_18000504F
0x180005039  mov     [rsp+278h+lpBuffer], rcx
0x18000503e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005045  mov     rcx, rax; this
0x180005048  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000504d  jmp     short loc_180005071
0x18000504f  mov     rcx, rax; this
0x180005052  test    r9, r9
0x180005055  jz      short loc_180005065
0x180005057  lea     r8, aHs; "[%hs]\n"
0x18000505e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005063  jmp     short loc_180005071
0x180005065  lea     r8, asc_180025118; "\n"
0x18000506c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005071  xor     eax, eax
0x180005073  mov     rcx, [rsp+278h+var_38]
0x18000507b  xor     rcx, rsp; StackCookie
0x18000507e  call    __security_check_cookie
0x180005083  mov     rbx, [rsp+278h+arg_18]
0x18000508b  add     rsp, 250h
0x180005092  pop     r15
0x180005094  pop     r14
0x180005096  pop     rdi
0x180005097  pop     rsi
0x180005098  pop     rbp
0x180005099  retn
```
