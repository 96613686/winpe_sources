# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000cd54`
- end: `0x18000d00a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180005570`
- `0x1800057f0`
- `0x180005aa4`
- `0x18000de68`
- `0x180018fa0`
- `0x180020e57`
- `0x180020f8b`
- `0x180021830`
- `0x180021c76`

## callees

- `0x180002e50`
- `0x180003940`
- `0x18000cd54`
- `0x18000e274`
- `0x180023010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x18000ce86`
- `KERNEL32!FormatMessageW` at `0x18000ce86`
- `KERNEL32!GetCurrentThreadId` at `0x18000cf07`
- `KERNEL32!GetCurrentThreadId` at `0x18000cf07`

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
          v7 = (const char *)&byte_180025210;
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
0x18000cd54  mov     [rsp+arg_18], rbx
0x18000cd59  push    rbp
0x18000cd5a  push    rsi
0x18000cd5b  push    rdi
0x18000cd5c  push    r14
0x18000cd5e  push    r15
0x18000cd60  sub     rsp, 250h
0x18000cd67  mov     rax, cs:__security_cookie
0x18000cd6e  xor     rax, rsp
0x18000cd71  mov     [rsp+278h+var_38], rax
0x18000cd79  mov     rbx, r8
0x18000cd7c  mov     rsi, rdx
0x18000cd7f  mov     r14, rcx
0x18000cd82  xor     r15d, r15d
0x18000cd85  test    rdx, rdx
0x18000cd88  jz      loc_18000CFE1
0x18000cd8e  test    rcx, rcx
0x18000cd91  jz      loc_18000CFE1
0x18000cd97  mov     [rcx], r15w
0x18000cd9b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000cda2  test    rax, rax
0x18000cda5  jz      short loc_18000CDC8
0x18000cda7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000cdae  jz      short loc_18000CDC8
0x18000cdb0  mov     r8, rdx
0x18000cdb3  mov     rdx, rcx
0x18000cdb6  mov     rcx, rbx
0x18000cdb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdbe  cmp     [r14], r15w
0x18000cdc2  jnz     loc_18000CFE1
0x18000cdc8  mov     ecx, [rbx]
0x18000cdca  mov     bpl, 8
0x18000cdcd  test    ecx, ecx
0x18000cdcf  jz      short loc_18000CE1A
0x18000cdd1  sub     ecx, 1
0x18000cdd4  jz      short loc_18000CE02
0x18000cdd6  sub     ecx, 1
0x18000cdd9  jz      short loc_18000CDF2
0x18000cddb  cmp     ecx, 1
0x18000cdde  jz      short loc_18000CDE9
0x18000cde0  lea     rdi, byte_180025210
0x18000cde7  jmp     short loc_18000CE21
0x18000cde9  lea     rdi, aFailfast; "FailFast"
0x18000cdf0  jmp     short loc_18000CE21
0x18000cdf2  lea     rax, aLoghr; "LogHr"
0x18000cdf9  lea     rdi, aLognt; "LogNt"
0x18000ce00  jmp     short loc_18000CE10
0x18000ce02  lea     rax, aReturnhr; "ReturnHr"
0x18000ce09  lea     rdi, aReturnnt; "ReturnNt"
0x18000ce10  test    [rbx+4], bpl
0x18000ce14  cmovz   rdi, rax
0x18000ce18  jmp     short loc_18000CE21
0x18000ce1a  lea     rdi, aException; "Exception"
0x18000ce21  xor     edx, edx; Val
0x18000ce23  mov     r8d, 200h; Size
0x18000ce29  lea     rcx, [rsp+278h+Buffer]; void *
0x18000ce2e  call    memset_0
0x18000ce33  test    [rbx+4], bpl
0x18000ce37  jz      short loc_18000CE5C
0x18000ce39  mov     ebp, [rbx+0Ch]
0x18000ce3c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000ce43  test    rax, rax
0x18000ce46  jz      short loc_18000CE8C
0x18000ce48  mov     r8d, 100h
0x18000ce4e  lea     rdx, [rsp+278h+Buffer]
0x18000ce53  mov     ecx, ebp
0x18000ce55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce5a  jmp     short loc_18000CE8C
0x18000ce5c  mov     ebp, [rbx+8]
0x18000ce5f  mov     [rsp+278h+Arguments], r15; Arguments
0x18000ce64  mov     [rsp+278h+nSize], 100h; nSize
0x18000ce6c  lea     rax, [rsp+278h+Buffer]
0x18000ce71  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000ce76  mov     r9d, 400h; dwLanguageId
0x18000ce7c  mov     r8d, ebp; dwMessageId
0x18000ce7f  xor     edx, edx; lpSource
0x18000ce81  mov     ecx, 1200h; dwFlags
0x18000ce86  call    cs:__imp_FormatMessageW
0x18000ce8c  lea     rsi, [r14+rsi*2]
0x18000ce90  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000ce94  mov     rax, [rbx+88h]
0x18000ce9b  mov     rcx, [rbx+80h]
0x18000cea2  mov     rdx, rsi; unsigned __int16 *
0x18000cea5  test    r9, r9
0x18000cea8  jz      short loc_18000CECC
0x18000ceaa  mov     [rsp+278h+Arguments], rax
0x18000ceaf  mov     qword ptr [rsp+278h+nSize], rcx
0x18000ceb4  mov     eax, [rbx+40h]
0x18000ceb7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000cebb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000cec2  mov     rcx, r14; this
0x18000cec5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ceca  jmp     short loc_18000CEE3
0x18000cecc  mov     [rsp+278h+lpBuffer], rax
0x18000ced1  mov     r9, rcx; unsigned __int16 *
0x18000ced4  lea     r8, aHsP; "%hs!%p: "
0x18000cedb  mov     rcx, r14; this
0x18000cede  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cee3  mov     r14, rax
0x18000cee6  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000ceed  test    r9, r9
0x18000cef0  jz      short loc_18000CF07
0x18000cef2  lea     r8, aCallerP; "(caller: %p) "
0x18000cef9  mov     rdx, rsi; unsigned __int16 *
0x18000cefc  mov     rcx, rax; this
0x18000ceff  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cf04  mov     r14, rax
0x18000cf07  call    cs:__imp_GetCurrentThreadId
0x18000cf0d  lea     rcx, [rsp+278h+Buffer]
0x18000cf12  mov     [rsp+278h+var_240], rcx
0x18000cf17  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000cf1b  mov     [rsp+278h+nSize], eax
0x18000cf1f  mov     eax, [rbx+44h]
0x18000cf22  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000cf26  mov     r9, rdi; unsigned __int16 *
0x18000cf29  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000cf30  mov     rdx, rsi; unsigned __int16 *
0x18000cf33  mov     rcx, r14; this
0x18000cf36  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cf3b  cmp     [rbx+18h], r15
0x18000cf3f  jnz     short loc_18000CF51
0x18000cf41  cmp     [rbx+48h], r15
0x18000cf45  jnz     short loc_18000CF51
0x18000cf47  cmp     [rbx+30h], r15
0x18000cf4b  jz      loc_18000CFE1
0x18000cf51  lea     r8, asc_180025330; "    "
0x18000cf58  mov     rdx, rsi; unsigned __int16 *
0x18000cf5b  mov     rcx, rax; this
0x18000cf5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cf63  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000cf67  test    r9, r9
0x18000cf6a  jz      short loc_18000CF7E
0x18000cf6c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000cf73  mov     rdx, rsi; unsigned __int16 *
0x18000cf76  mov     rcx, rax; this
0x18000cf79  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cf7e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000cf82  test    r9, r9
0x18000cf85  jz      short loc_18000CF99
0x18000cf87  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000cf8e  mov     rdx, rsi; unsigned __int16 *
0x18000cf91  mov     rcx, rax; this
0x18000cf94  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cf99  mov     rcx, [rbx+28h]
0x18000cf9d  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000cfa1  mov     rdx, rsi; unsigned __int16 *
0x18000cfa4  test    rcx, rcx
0x18000cfa7  jz      short loc_18000CFBF
0x18000cfa9  mov     [rsp+278h+lpBuffer], rcx
0x18000cfae  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000cfb5  mov     rcx, rax; this
0x18000cfb8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cfbd  jmp     short loc_18000CFE1
0x18000cfbf  mov     rcx, rax; this
0x18000cfc2  test    r9, r9
0x18000cfc5  jz      short loc_18000CFD5
0x18000cfc7  lea     r8, aHs; "[%hs]\n"
0x18000cfce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cfd3  jmp     short loc_18000CFE1
0x18000cfd5  lea     r8, asc_1800253A8; "\n"
0x18000cfdc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cfe1  xor     eax, eax
0x18000cfe3  mov     rcx, [rsp+278h+var_38]
0x18000cfeb  xor     rcx, rsp; StackCookie
0x18000cfee  call    __security_check_cookie
0x18000cff3  mov     rbx, [rsp+278h+arg_18]
0x18000cffb  add     rsp, 250h
0x18000d002  pop     r15
0x18000d004  pop     r14
0x18000d006  pop     rdi
0x18000d007  pop     rsi
0x18000d008  pop     rbp
0x18000d009  retn
```
