# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000bed4`
- end: `0x18000c18a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000ae18`
- `0x18000b088`
- `0x18000c830`

## callees

- `0x180001ce0`
- `0x180002616`
- `0x18000bed4`
- `0x18000cb30`
- `0x18000e010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000c087`
- `KERNEL32!GetCurrentThreadId` at `0x18000c087`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000c006`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000c006`

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
          v8 = (const char *)&word_18000FB6A;
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
0x18000bed4  mov     [rsp+arg_18], rbx
0x18000bed9  push    rbp
0x18000beda  push    rsi
0x18000bedb  push    rdi
0x18000bedc  push    r14
0x18000bede  push    r15
0x18000bee0  sub     rsp, 250h
0x18000bee7  mov     rax, cs:__security_cookie
0x18000beee  xor     rax, rsp
0x18000bef1  mov     [rsp+278h+var_38], rax
0x18000bef9  xor     r15d, r15d
0x18000befc  mov     rbx, r8
0x18000beff  mov     rsi, rdx
0x18000bf02  mov     r14, rcx
0x18000bf05  test    rdx, rdx
0x18000bf08  jz      loc_18000C161
0x18000bf0e  test    rcx, rcx
0x18000bf11  jz      loc_18000C161
0x18000bf17  mov     rax, cs:g_pfnResultLoggingCallback
0x18000bf1e  mov     [rcx], r15w
0x18000bf22  test    rax, rax
0x18000bf25  jz      short loc_18000BF48
0x18000bf27  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000bf2e  jz      short loc_18000BF48
0x18000bf30  mov     r8, rdx
0x18000bf33  mov     rdx, rcx
0x18000bf36  mov     rcx, rbx
0x18000bf39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf3e  cmp     [r14], r15w
0x18000bf42  jnz     loc_18000C161
0x18000bf48  mov     ecx, [rbx]
0x18000bf4a  mov     bpl, 8
0x18000bf4d  test    ecx, ecx
0x18000bf4f  jz      short loc_18000BF9A
0x18000bf51  sub     ecx, 1
0x18000bf54  jz      short loc_18000BF82
0x18000bf56  sub     ecx, 1
0x18000bf59  jz      short loc_18000BF72
0x18000bf5b  cmp     ecx, 1
0x18000bf5e  jz      short loc_18000BF69
0x18000bf60  lea     rdi, word_18000FB6A
0x18000bf67  jmp     short loc_18000BFA1
0x18000bf69  lea     rdi, aFailfast; "FailFast"
0x18000bf70  jmp     short loc_18000BFA1
0x18000bf72  lea     rax, aLoghr; "LogHr"
0x18000bf79  lea     rdi, aLognt; "LogNt"
0x18000bf80  jmp     short loc_18000BF90
0x18000bf82  lea     rax, aReturnhr; "ReturnHr"
0x18000bf89  lea     rdi, aReturnnt; "ReturnNt"
0x18000bf90  test    [rbx+4], bpl
0x18000bf94  cmovz   rdi, rax
0x18000bf98  jmp     short loc_18000BFA1
0x18000bf9a  lea     rdi, aException; "Exception"
0x18000bfa1  xor     edx, edx; Val
0x18000bfa3  lea     rcx, [rsp+278h+Buffer]; void *
0x18000bfa8  mov     r8d, 200h; Size
0x18000bfae  call    memset_0
0x18000bfb3  test    [rbx+4], bpl
0x18000bfb7  jz      short loc_18000BFDC
0x18000bfb9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000bfc0  mov     ebp, [rbx+0Ch]
0x18000bfc3  test    rax, rax
0x18000bfc6  jz      short loc_18000C00C
0x18000bfc8  mov     r8d, 100h
0x18000bfce  lea     rdx, [rsp+278h+Buffer]
0x18000bfd3  mov     ecx, ebp
0x18000bfd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfda  jmp     short loc_18000C00C
0x18000bfdc  mov     ebp, [rbx+8]
0x18000bfdf  lea     rax, [rsp+278h+Buffer]
0x18000bfe4  mov     [rsp+278h+Arguments], r15; Arguments
0x18000bfe9  mov     r8d, ebp; dwMessageId
0x18000bfec  mov     [rsp+278h+nSize], 100h; nSize
0x18000bff4  mov     r9d, 400h; dwLanguageId
0x18000bffa  xor     edx, edx; lpSource
0x18000bffc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000c001  mov     ecx, 1200h; dwFlags
0x18000c006  call    cs:__imp_FormatMessageW
0x18000c00c  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000c010  lea     rsi, [r14+rsi*2]
0x18000c014  mov     rax, [rbx+88h]
0x18000c01b  mov     rdx, rsi; unsigned __int16 *
0x18000c01e  mov     rcx, [rbx+80h]
0x18000c025  test    r9, r9
0x18000c028  jz      short loc_18000C04C
0x18000c02a  mov     [rsp+278h+Arguments], rax
0x18000c02f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000c036  mov     eax, [rbx+40h]
0x18000c039  mov     qword ptr [rsp+278h+nSize], rcx
0x18000c03e  mov     rcx, r14; this
0x18000c041  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000c045  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c04a  jmp     short loc_18000C063
0x18000c04c  mov     r9, rcx; unsigned __int16 *
0x18000c04f  mov     [rsp+278h+lpBuffer], rax
0x18000c054  mov     rcx, r14; this
0x18000c057  lea     r8, aHsP; "%hs!%p: "
0x18000c05e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c063  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000c06a  mov     r14, rax
0x18000c06d  test    r9, r9
0x18000c070  jz      short loc_18000C087
0x18000c072  lea     r8, aCallerP; "(caller: %p) "
0x18000c079  mov     rdx, rsi; unsigned __int16 *
0x18000c07c  mov     rcx, rax; this
0x18000c07f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c084  mov     r14, rax
0x18000c087  call    cs:__imp_GetCurrentThreadId
0x18000c08d  lea     rcx, [rsp+278h+Buffer]
0x18000c092  mov     r9, rdi; unsigned __int16 *
0x18000c095  mov     [rsp+278h+var_240], rcx
0x18000c09a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000c0a1  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000c0a5  mov     rdx, rsi; unsigned __int16 *
0x18000c0a8  mov     [rsp+278h+nSize], eax
0x18000c0ac  mov     rcx, r14; this
0x18000c0af  mov     eax, [rbx+44h]
0x18000c0b2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000c0b6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c0bb  cmp     [rbx+18h], r15
0x18000c0bf  jnz     short loc_18000C0D1
0x18000c0c1  cmp     [rbx+48h], r15
0x18000c0c5  jnz     short loc_18000C0D1
0x18000c0c7  cmp     [rbx+30h], r15
0x18000c0cb  jz      loc_18000C161
0x18000c0d1  lea     r8, asc_18000FC68; "    "
0x18000c0d8  mov     rdx, rsi; unsigned __int16 *
0x18000c0db  mov     rcx, rax; this
0x18000c0de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c0e3  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000c0e7  test    r9, r9
0x18000c0ea  jz      short loc_18000C0FE
0x18000c0ec  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000c0f3  mov     rdx, rsi; unsigned __int16 *
0x18000c0f6  mov     rcx, rax; this
0x18000c0f9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c0fe  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000c102  test    r9, r9
0x18000c105  jz      short loc_18000C119
0x18000c107  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000c10e  mov     rdx, rsi; unsigned __int16 *
0x18000c111  mov     rcx, rax; this
0x18000c114  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c119  mov     rcx, [rbx+28h]
0x18000c11d  mov     rdx, rsi; unsigned __int16 *
0x18000c120  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000c124  test    rcx, rcx
0x18000c127  jz      short loc_18000C13F
0x18000c129  mov     [rsp+278h+lpBuffer], rcx
0x18000c12e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000c135  mov     rcx, rax; this
0x18000c138  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c13d  jmp     short loc_18000C161
0x18000c13f  mov     rcx, rax; this
0x18000c142  test    r9, r9
0x18000c145  jz      short loc_18000C155
0x18000c147  lea     r8, aHs; "[%hs]\n"
0x18000c14e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c153  jmp     short loc_18000C161
0x18000c155  lea     r8, asc_18000FCE0; "\n"
0x18000c15c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c161  xor     eax, eax
0x18000c163  mov     rcx, [rsp+278h+var_38]
0x18000c16b  xor     rcx, rsp; StackCookie
0x18000c16e  call    __security_check_cookie
0x18000c173  mov     rbx, [rsp+278h+arg_18]
0x18000c17b  add     rsp, 250h
0x18000c182  pop     r15
0x18000c184  pop     r14
0x18000c186  pop     rdi
0x18000c187  pop     rsi
0x18000c188  pop     rbp
0x18000c189  retn
```
