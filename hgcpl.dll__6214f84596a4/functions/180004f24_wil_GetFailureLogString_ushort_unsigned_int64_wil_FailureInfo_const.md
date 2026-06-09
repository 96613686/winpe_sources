# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004f24`
- end: `0x1800051da`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000427c`
- `0x180005930`

## callees

- `0x180004f24`
- `0x180005c30`
- `0x180018a52`
- `0x180018a80`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800050d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800050d7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005056`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005056`

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
          v8 = (const char *)&word_18001D746;
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
0x180004f24  mov     [rsp+arg_18], rbx
0x180004f29  push    rbp
0x180004f2a  push    rsi
0x180004f2b  push    rdi
0x180004f2c  push    r14
0x180004f2e  push    r15
0x180004f30  sub     rsp, 250h
0x180004f37  mov     rax, cs:__security_cookie
0x180004f3e  xor     rax, rsp
0x180004f41  mov     [rsp+278h+var_38], rax
0x180004f49  xor     r15d, r15d
0x180004f4c  mov     rbx, r8
0x180004f4f  mov     rsi, rdx
0x180004f52  mov     r14, rcx
0x180004f55  test    rdx, rdx
0x180004f58  jz      loc_1800051B1
0x180004f5e  test    rcx, rcx
0x180004f61  jz      loc_1800051B1
0x180004f67  mov     rax, cs:g_pfnResultLoggingCallback
0x180004f6e  mov     [rcx], r15w
0x180004f72  test    rax, rax
0x180004f75  jz      short loc_180004F98
0x180004f77  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004f7e  jz      short loc_180004F98
0x180004f80  mov     r8, rdx
0x180004f83  mov     rdx, rcx
0x180004f86  mov     rcx, rbx
0x180004f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f8e  cmp     [r14], r15w
0x180004f92  jnz     loc_1800051B1
0x180004f98  mov     ecx, [rbx]
0x180004f9a  mov     bpl, 8
0x180004f9d  test    ecx, ecx
0x180004f9f  jz      short loc_180004FEA
0x180004fa1  sub     ecx, 1
0x180004fa4  jz      short loc_180004FD2
0x180004fa6  sub     ecx, 1
0x180004fa9  jz      short loc_180004FC2
0x180004fab  cmp     ecx, 1
0x180004fae  jz      short loc_180004FB9
0x180004fb0  lea     rdi, word_18001D746
0x180004fb7  jmp     short loc_180004FF1
0x180004fb9  lea     rdi, aFailfast; "FailFast"
0x180004fc0  jmp     short loc_180004FF1
0x180004fc2  lea     rax, aLoghr; "LogHr"
0x180004fc9  lea     rdi, aLognt; "LogNt"
0x180004fd0  jmp     short loc_180004FE0
0x180004fd2  lea     rax, aReturnhr; "ReturnHr"
0x180004fd9  lea     rdi, aReturnnt; "ReturnNt"
0x180004fe0  test    [rbx+4], bpl
0x180004fe4  cmovz   rdi, rax
0x180004fe8  jmp     short loc_180004FF1
0x180004fea  lea     rdi, aException; "Exception"
0x180004ff1  xor     edx, edx; Val
0x180004ff3  lea     rcx, [rsp+278h+Buffer]; void *
0x180004ff8  mov     r8d, 200h; Size
0x180004ffe  call    memset_0
0x180005003  test    [rbx+4], bpl
0x180005007  jz      short loc_18000502C
0x180005009  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005010  mov     ebp, [rbx+0Ch]
0x180005013  test    rax, rax
0x180005016  jz      short loc_18000505C
0x180005018  mov     r8d, 100h
0x18000501e  lea     rdx, [rsp+278h+Buffer]
0x180005023  mov     ecx, ebp
0x180005025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000502a  jmp     short loc_18000505C
0x18000502c  mov     ebp, [rbx+8]
0x18000502f  lea     rax, [rsp+278h+Buffer]
0x180005034  mov     [rsp+278h+Arguments], r15; Arguments
0x180005039  mov     r8d, ebp; dwMessageId
0x18000503c  mov     [rsp+278h+nSize], 100h; nSize
0x180005044  mov     r9d, 400h; dwLanguageId
0x18000504a  xor     edx, edx; lpSource
0x18000504c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005051  mov     ecx, 1200h; dwFlags
0x180005056  call    cs:__imp_FormatMessageW
0x18000505c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005060  lea     rsi, [r14+rsi*2]
0x180005064  mov     rax, [rbx+88h]
0x18000506b  mov     rdx, rsi; unsigned __int16 *
0x18000506e  mov     rcx, [rbx+80h]
0x180005075  test    r9, r9
0x180005078  jz      short loc_18000509C
0x18000507a  mov     [rsp+278h+Arguments], rax
0x18000507f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005086  mov     eax, [rbx+40h]
0x180005089  mov     qword ptr [rsp+278h+nSize], rcx
0x18000508e  mov     rcx, r14; this
0x180005091  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005095  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000509a  jmp     short loc_1800050B3
0x18000509c  mov     r9, rcx; unsigned __int16 *
0x18000509f  mov     [rsp+278h+lpBuffer], rax
0x1800050a4  mov     rcx, r14; this
0x1800050a7  lea     r8, aHsP; "%hs!%p: "
0x1800050ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800050b3  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800050ba  mov     r14, rax
0x1800050bd  test    r9, r9
0x1800050c0  jz      short loc_1800050D7
0x1800050c2  lea     r8, aCallerP; "(caller: %p) "
0x1800050c9  mov     rdx, rsi; unsigned __int16 *
0x1800050cc  mov     rcx, rax; this
0x1800050cf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800050d4  mov     r14, rax
0x1800050d7  call    cs:__imp_GetCurrentThreadId
0x1800050dd  lea     rcx, [rsp+278h+Buffer]
0x1800050e2  mov     r9, rdi; unsigned __int16 *
0x1800050e5  mov     [rsp+278h+var_240], rcx
0x1800050ea  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800050f1  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800050f5  mov     rdx, rsi; unsigned __int16 *
0x1800050f8  mov     [rsp+278h+nSize], eax
0x1800050fc  mov     rcx, r14; this
0x1800050ff  mov     eax, [rbx+44h]
0x180005102  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005106  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000510b  cmp     [rbx+18h], r15
0x18000510f  jnz     short loc_180005121
0x180005111  cmp     [rbx+48h], r15
0x180005115  jnz     short loc_180005121
0x180005117  cmp     [rbx+30h], r15
0x18000511b  jz      loc_1800051B1
0x180005121  lea     r8, asc_18001D830; "    "
0x180005128  mov     rdx, rsi; unsigned __int16 *
0x18000512b  mov     rcx, rax; this
0x18000512e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005133  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005137  test    r9, r9
0x18000513a  jz      short loc_18000514E
0x18000513c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005143  mov     rdx, rsi; unsigned __int16 *
0x180005146  mov     rcx, rax; this
0x180005149  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000514e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005152  test    r9, r9
0x180005155  jz      short loc_180005169
0x180005157  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000515e  mov     rdx, rsi; unsigned __int16 *
0x180005161  mov     rcx, rax; this
0x180005164  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005169  mov     rcx, [rbx+28h]
0x18000516d  mov     rdx, rsi; unsigned __int16 *
0x180005170  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005174  test    rcx, rcx
0x180005177  jz      short loc_18000518F
0x180005179  mov     [rsp+278h+lpBuffer], rcx
0x18000517e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005185  mov     rcx, rax; this
0x180005188  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000518d  jmp     short loc_1800051B1
0x18000518f  mov     rcx, rax; this
0x180005192  test    r9, r9
0x180005195  jz      short loc_1800051A5
0x180005197  lea     r8, aHs; "[%hs]\n"
0x18000519e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800051a3  jmp     short loc_1800051B1
0x1800051a5  lea     r8, asc_18001D8A8; "\n"
0x1800051ac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800051b1  xor     eax, eax
0x1800051b3  mov     rcx, [rsp+278h+var_38]
0x1800051bb  xor     rcx, rsp; StackCookie
0x1800051be  call    __security_check_cookie
0x1800051c3  mov     rbx, [rsp+278h+arg_18]
0x1800051cb  add     rsp, 250h
0x1800051d2  pop     r15
0x1800051d4  pop     r14
0x1800051d6  pop     rdi
0x1800051d7  pop     rsi
0x1800051d8  pop     rbp
0x1800051d9  retn
```
