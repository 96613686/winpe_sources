# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x14000eb2c`
- end: `0x14000edef`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x14000de30`
- `0x14000e0b0`
- `0x14000f3d0`

## callees

- `0x140001af3`
- `0x14000eb2c`
- `0x14000f6e4`
- `0x1400109c0`
- `0x140011010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x14000ec5e`
- `KERNEL32!FormatMessageW` at `0x14000ec5e`
- `KERNEL32!GetCurrentThreadId` at `0x14000ece5`
- `KERNEL32!GetCurrentThreadId` at `0x14000ece5`

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
          v8 = (const char *)&byte_140012D60;
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
0x14000eb2c  mov     [rsp+arg_18], rbx
0x14000eb31  push    rbp
0x14000eb32  push    rsi
0x14000eb33  push    rdi
0x14000eb34  push    r14
0x14000eb36  push    r15
0x14000eb38  sub     rsp, 250h
0x14000eb3f  mov     rax, cs:__security_cookie
0x14000eb46  xor     rax, rsp
0x14000eb49  mov     [rsp+278h+var_38], rax
0x14000eb51  xor     r15d, r15d
0x14000eb54  mov     rbx, r8
0x14000eb57  mov     rsi, rdx
0x14000eb5a  mov     r14, rcx
0x14000eb5d  test    rdx, rdx
0x14000eb60  jz      loc_14000EDC5
0x14000eb66  test    rcx, rcx
0x14000eb69  jz      loc_14000EDC5
0x14000eb6f  mov     rax, cs:g_pfnResultLoggingCallback
0x14000eb76  mov     [rcx], r15w
0x14000eb7a  test    rax, rax
0x14000eb7d  jz      short loc_14000EBA0
0x14000eb7f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000eb86  jz      short loc_14000EBA0
0x14000eb88  mov     r8, rdx
0x14000eb8b  mov     rdx, rcx
0x14000eb8e  mov     rcx, rbx
0x14000eb91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eb96  cmp     [r14], r15w
0x14000eb9a  jnz     loc_14000EDC5
0x14000eba0  mov     ecx, [rbx]
0x14000eba2  mov     bpl, 8
0x14000eba5  test    ecx, ecx
0x14000eba7  jz      short loc_14000EBF2
0x14000eba9  sub     ecx, 1
0x14000ebac  jz      short loc_14000EBDA
0x14000ebae  sub     ecx, 1
0x14000ebb1  jz      short loc_14000EBCA
0x14000ebb3  cmp     ecx, 1
0x14000ebb6  jz      short loc_14000EBC1
0x14000ebb8  lea     rdi, byte_140012D60
0x14000ebbf  jmp     short loc_14000EBF9
0x14000ebc1  lea     rdi, aFailfast; "FailFast"
0x14000ebc8  jmp     short loc_14000EBF9
0x14000ebca  lea     rax, aLoghr; "LogHr"
0x14000ebd1  lea     rdi, aLognt; "LogNt"
0x14000ebd8  jmp     short loc_14000EBE8
0x14000ebda  lea     rax, aReturnhr; "ReturnHr"
0x14000ebe1  lea     rdi, aReturnnt; "ReturnNt"
0x14000ebe8  test    [rbx+4], bpl
0x14000ebec  cmovz   rdi, rax
0x14000ebf0  jmp     short loc_14000EBF9
0x14000ebf2  lea     rdi, aException; "Exception"
0x14000ebf9  xor     edx, edx; Val
0x14000ebfb  lea     rcx, [rsp+278h+Buffer]; void *
0x14000ec00  mov     r8d, 200h; Size
0x14000ec06  call    memset_0
0x14000ec0b  test    [rbx+4], bpl
0x14000ec0f  jz      short loc_14000EC34
0x14000ec11  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x14000ec18  mov     ebp, [rbx+0Ch]
0x14000ec1b  test    rax, rax
0x14000ec1e  jz      short loc_14000EC6A
0x14000ec20  mov     r8d, 100h
0x14000ec26  lea     rdx, [rsp+278h+Buffer]
0x14000ec2b  mov     ecx, ebp
0x14000ec2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ec32  jmp     short loc_14000EC6A
0x14000ec34  mov     ebp, [rbx+8]
0x14000ec37  lea     rax, [rsp+278h+Buffer]
0x14000ec3c  mov     [rsp+278h+Arguments], r15; Arguments
0x14000ec41  mov     r8d, ebp; dwMessageId
0x14000ec44  mov     [rsp+278h+nSize], 100h; nSize
0x14000ec4c  mov     r9d, 400h; dwLanguageId
0x14000ec52  xor     edx, edx; lpSource
0x14000ec54  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x14000ec59  mov     ecx, 1200h; dwFlags
0x14000ec5e  call    cs:__imp_FormatMessageW
0x14000ec65  nop     dword ptr [rax+rax+00h]
0x14000ec6a  mov     r9, [rbx+38h]; unsigned __int16 *
0x14000ec6e  lea     rsi, [r14+rsi*2]
0x14000ec72  mov     rax, [rbx+88h]
0x14000ec79  mov     rdx, rsi; unsigned __int16 *
0x14000ec7c  mov     rcx, [rbx+80h]
0x14000ec83  test    r9, r9
0x14000ec86  jz      short loc_14000ECAA
0x14000ec88  mov     [rsp+278h+Arguments], rax
0x14000ec8d  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x14000ec94  mov     eax, [rbx+40h]
0x14000ec97  mov     qword ptr [rsp+278h+nSize], rcx
0x14000ec9c  mov     rcx, r14; this
0x14000ec9f  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000eca3  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000eca8  jmp     short loc_14000ECC1
0x14000ecaa  mov     r9, rcx; unsigned __int16 *
0x14000ecad  mov     [rsp+278h+lpBuffer], rax
0x14000ecb2  mov     rcx, r14; this
0x14000ecb5  lea     r8, aHsP; "%hs!%p: "
0x14000ecbc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000ecc1  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000ecc8  mov     r14, rax
0x14000eccb  test    r9, r9
0x14000ecce  jz      short loc_14000ECE5
0x14000ecd0  lea     r8, aCallerP; "(caller: %p) "
0x14000ecd7  mov     rdx, rsi; unsigned __int16 *
0x14000ecda  mov     rcx, rax; this
0x14000ecdd  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000ece2  mov     r14, rax
0x14000ece5  call    cs:__imp_GetCurrentThreadId
0x14000ecec  nop     dword ptr [rax+rax+00h]
0x14000ecf1  lea     rcx, [rsp+278h+Buffer]
0x14000ecf6  mov     r9, rdi; unsigned __int16 *
0x14000ecf9  mov     [rsp+278h+var_240], rcx
0x14000ecfe  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x14000ed05  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000ed09  mov     rdx, rsi; unsigned __int16 *
0x14000ed0c  mov     [rsp+278h+nSize], eax
0x14000ed10  mov     rcx, r14; this
0x14000ed13  mov     eax, [rbx+44h]
0x14000ed16  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000ed1a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000ed1f  cmp     [rbx+18h], r15
0x14000ed23  jnz     short loc_14000ED35
0x14000ed25  cmp     [rbx+48h], r15
0x14000ed29  jnz     short loc_14000ED35
0x14000ed2b  cmp     [rbx+30h], r15
0x14000ed2f  jz      loc_14000EDC5
0x14000ed35  lea     r8, asc_140013878; "    "
0x14000ed3c  mov     rdx, rsi; unsigned __int16 *
0x14000ed3f  mov     rcx, rax; this
0x14000ed42  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000ed47  mov     r9, [rbx+18h]; unsigned __int16 *
0x14000ed4b  test    r9, r9
0x14000ed4e  jz      short loc_14000ED62
0x14000ed50  lea     r8, aMsgWs; "Msg:[%ws] "
0x14000ed57  mov     rdx, rsi; unsigned __int16 *
0x14000ed5a  mov     rcx, rax; this
0x14000ed5d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000ed62  mov     r9, [rbx+48h]; unsigned __int16 *
0x14000ed66  test    r9, r9
0x14000ed69  jz      short loc_14000ED7D
0x14000ed6b  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000ed72  mov     rdx, rsi; unsigned __int16 *
0x14000ed75  mov     rcx, rax; this
0x14000ed78  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000ed7d  mov     rcx, [rbx+28h]
0x14000ed81  mov     rdx, rsi; unsigned __int16 *
0x14000ed84  mov     r9, [rbx+30h]; unsigned __int16 *
0x14000ed88  test    rcx, rcx
0x14000ed8b  jz      short loc_14000EDA3
0x14000ed8d  mov     [rsp+278h+lpBuffer], rcx
0x14000ed92  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x14000ed99  mov     rcx, rax; this
0x14000ed9c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000eda1  jmp     short loc_14000EDC5
0x14000eda3  mov     rcx, rax; this
0x14000eda6  test    r9, r9
0x14000eda9  jz      short loc_14000EDB9
0x14000edab  lea     r8, aHs; "[%hs]\n"
0x14000edb2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000edb7  jmp     short loc_14000EDC5
0x14000edb9  lea     r8, asc_1400138F0; "\n"
0x14000edc0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000edc5  xor     eax, eax
0x14000edc7  mov     rcx, [rsp+278h+var_38]
0x14000edcf  xor     rcx, rsp; StackCookie
0x14000edd2  call    __security_check_cookie
0x14000edd7  mov     rbx, [rsp+278h+arg_18]
0x14000eddf  add     rsp, 250h
0x14000ede6  pop     r15
0x14000ede8  pop     r14
0x14000edea  pop     rdi
0x14000edeb  pop     rsi
0x14000edec  pop     rbp
0x14000eded  retn
```
