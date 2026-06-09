# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000ee78`
- end: `0x18000f12e`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180007008`

## callees

- `0x18000d0a0`
- `0x18000ddc4`
- `0x18000ee78`
- `0x18000f424`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f02b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f02b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000efaa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000efaa`

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
          v8 = (const char *)&qword_180019770;
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
0x18000ee78  mov     [rsp+arg_18], rbx
0x18000ee7d  push    rbp
0x18000ee7e  push    rsi
0x18000ee7f  push    rdi
0x18000ee80  push    r14
0x18000ee82  push    r15
0x18000ee84  sub     rsp, 250h
0x18000ee8b  mov     rax, cs:__security_cookie
0x18000ee92  xor     rax, rsp
0x18000ee95  mov     [rsp+278h+var_38], rax
0x18000ee9d  xor     r15d, r15d
0x18000eea0  mov     rbx, r8
0x18000eea3  mov     rsi, rdx
0x18000eea6  mov     r14, rcx
0x18000eea9  test    rdx, rdx
0x18000eeac  jz      loc_18000F105
0x18000eeb2  test    rcx, rcx
0x18000eeb5  jz      loc_18000F105
0x18000eebb  mov     rax, cs:g_pfnResultLoggingCallback
0x18000eec2  mov     [rcx], r15w
0x18000eec6  test    rax, rax
0x18000eec9  jz      short loc_18000EEEC
0x18000eecb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000eed2  jz      short loc_18000EEEC
0x18000eed4  mov     r8, rdx
0x18000eed7  mov     rdx, rcx
0x18000eeda  mov     rcx, rbx
0x18000eedd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eee2  cmp     [r14], r15w
0x18000eee6  jnz     loc_18000F105
0x18000eeec  mov     ecx, [rbx]
0x18000eeee  mov     bpl, 8
0x18000eef1  test    ecx, ecx
0x18000eef3  jz      short loc_18000EF3E
0x18000eef5  sub     ecx, 1
0x18000eef8  jz      short loc_18000EF26
0x18000eefa  sub     ecx, 1
0x18000eefd  jz      short loc_18000EF16
0x18000eeff  cmp     ecx, 1
0x18000ef02  jz      short loc_18000EF0D
0x18000ef04  lea     rdi, qword_180019770
0x18000ef0b  jmp     short loc_18000EF45
0x18000ef0d  lea     rdi, aFailfast; "FailFast"
0x18000ef14  jmp     short loc_18000EF45
0x18000ef16  lea     rax, aLoghr; "LogHr"
0x18000ef1d  lea     rdi, aLognt; "LogNt"
0x18000ef24  jmp     short loc_18000EF34
0x18000ef26  lea     rax, aReturnhr; "ReturnHr"
0x18000ef2d  lea     rdi, aReturnnt; "ReturnNt"
0x18000ef34  test    [rbx+4], bpl
0x18000ef38  cmovz   rdi, rax
0x18000ef3c  jmp     short loc_18000EF45
0x18000ef3e  lea     rdi, aException; "Exception"
0x18000ef45  xor     edx, edx; Val
0x18000ef47  lea     rcx, [rsp+278h+Buffer]; void *
0x18000ef4c  mov     r8d, 200h; Size
0x18000ef52  call    memset_0
0x18000ef57  test    [rbx+4], bpl
0x18000ef5b  jz      short loc_18000EF80
0x18000ef5d  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000ef64  mov     ebp, [rbx+0Ch]
0x18000ef67  test    rax, rax
0x18000ef6a  jz      short loc_18000EFB0
0x18000ef6c  mov     r8d, 100h
0x18000ef72  lea     rdx, [rsp+278h+Buffer]
0x18000ef77  mov     ecx, ebp
0x18000ef79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef7e  jmp     short loc_18000EFB0
0x18000ef80  mov     ebp, [rbx+8]
0x18000ef83  lea     rax, [rsp+278h+Buffer]
0x18000ef88  mov     [rsp+278h+Arguments], r15; Arguments
0x18000ef8d  mov     r8d, ebp; dwMessageId
0x18000ef90  mov     [rsp+278h+nSize], 100h; nSize
0x18000ef98  mov     r9d, 400h; dwLanguageId
0x18000ef9e  xor     edx, edx; lpSource
0x18000efa0  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000efa5  mov     ecx, 1200h; dwFlags
0x18000efaa  call    cs:__imp_FormatMessageW
0x18000efb0  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000efb4  lea     rsi, [r14+rsi*2]
0x18000efb8  mov     rax, [rbx+88h]
0x18000efbf  mov     rdx, rsi; unsigned __int16 *
0x18000efc2  mov     rcx, [rbx+80h]
0x18000efc9  test    r9, r9
0x18000efcc  jz      short loc_18000EFF0
0x18000efce  mov     [rsp+278h+Arguments], rax
0x18000efd3  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000efda  mov     eax, [rbx+40h]
0x18000efdd  mov     qword ptr [rsp+278h+nSize], rcx
0x18000efe2  mov     rcx, r14; this
0x18000efe5  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000efe9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000efee  jmp     short loc_18000F007
0x18000eff0  mov     r9, rcx; unsigned __int16 *
0x18000eff3  mov     [rsp+278h+lpBuffer], rax
0x18000eff8  mov     rcx, r14; this
0x18000effb  lea     r8, aHsP; "%hs!%p: "
0x18000f002  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f007  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000f00e  mov     r14, rax
0x18000f011  test    r9, r9
0x18000f014  jz      short loc_18000F02B
0x18000f016  lea     r8, aCallerP; "(caller: %p) "
0x18000f01d  mov     rdx, rsi; unsigned __int16 *
0x18000f020  mov     rcx, rax; this
0x18000f023  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f028  mov     r14, rax
0x18000f02b  call    cs:__imp_GetCurrentThreadId
0x18000f031  lea     rcx, [rsp+278h+Buffer]
0x18000f036  mov     r9, rdi; unsigned __int16 *
0x18000f039  mov     [rsp+278h+var_240], rcx
0x18000f03e  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000f045  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000f049  mov     rdx, rsi; unsigned __int16 *
0x18000f04c  mov     [rsp+278h+nSize], eax
0x18000f050  mov     rcx, r14; this
0x18000f053  mov     eax, [rbx+44h]
0x18000f056  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000f05a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f05f  cmp     [rbx+18h], r15
0x18000f063  jnz     short loc_18000F075
0x18000f065  cmp     [rbx+48h], r15
0x18000f069  jnz     short loc_18000F075
0x18000f06b  cmp     [rbx+30h], r15
0x18000f06f  jz      loc_18000F105
0x18000f075  lea     r8, asc_180019860; "    "
0x18000f07c  mov     rdx, rsi; unsigned __int16 *
0x18000f07f  mov     rcx, rax; this
0x18000f082  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f087  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000f08b  test    r9, r9
0x18000f08e  jz      short loc_18000F0A2
0x18000f090  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000f097  mov     rdx, rsi; unsigned __int16 *
0x18000f09a  mov     rcx, rax; this
0x18000f09d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f0a2  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000f0a6  test    r9, r9
0x18000f0a9  jz      short loc_18000F0BD
0x18000f0ab  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000f0b2  mov     rdx, rsi; unsigned __int16 *
0x18000f0b5  mov     rcx, rax; this
0x18000f0b8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f0bd  mov     rcx, [rbx+28h]
0x18000f0c1  mov     rdx, rsi; unsigned __int16 *
0x18000f0c4  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000f0c8  test    rcx, rcx
0x18000f0cb  jz      short loc_18000F0E3
0x18000f0cd  mov     [rsp+278h+lpBuffer], rcx
0x18000f0d2  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000f0d9  mov     rcx, rax; this
0x18000f0dc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f0e1  jmp     short loc_18000F105
0x18000f0e3  mov     rcx, rax; this
0x18000f0e6  test    r9, r9
0x18000f0e9  jz      short loc_18000F0F9
0x18000f0eb  lea     r8, aHs; "[%hs]\n"
0x18000f0f2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f0f7  jmp     short loc_18000F105
0x18000f0f9  lea     r8, asc_1800198D8; "\n"
0x18000f100  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f105  xor     eax, eax
0x18000f107  mov     rcx, [rsp+278h+var_38]
0x18000f10f  xor     rcx, rsp; StackCookie
0x18000f112  call    __security_check_cookie
0x18000f117  mov     rbx, [rsp+278h+arg_18]
0x18000f11f  add     rsp, 250h
0x18000f126  pop     r15
0x18000f128  pop     r14
0x18000f12a  pop     rdi
0x18000f12b  pop     rsi
0x18000f12c  pop     rbp
0x18000f12d  retn
```
