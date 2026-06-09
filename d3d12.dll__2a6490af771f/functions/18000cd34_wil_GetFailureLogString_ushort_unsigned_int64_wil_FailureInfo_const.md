# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000cd34`
- end: `0x18000cfea`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180009ed0`
- `0x18000e1a0`

## callees

- `0x18000b410`
- `0x18000be78`
- `0x18000cd34`
- `0x18000d2dc`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cee7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cee7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000ce66`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000ce66`

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
          v7 = (const char *)&qword_180017450;
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
0x18000cd34  mov     [rsp+arg_18], rbx
0x18000cd39  push    rbp
0x18000cd3a  push    rsi
0x18000cd3b  push    rdi
0x18000cd3c  push    r14
0x18000cd3e  push    r15
0x18000cd40  sub     rsp, 250h
0x18000cd47  mov     rax, cs:__security_cookie
0x18000cd4e  xor     rax, rsp
0x18000cd51  mov     [rsp+278h+var_38], rax
0x18000cd59  mov     rbx, r8
0x18000cd5c  mov     rsi, rdx
0x18000cd5f  mov     r14, rcx
0x18000cd62  xor     r15d, r15d
0x18000cd65  test    rdx, rdx
0x18000cd68  jz      loc_18000CFC1
0x18000cd6e  test    rcx, rcx
0x18000cd71  jz      loc_18000CFC1
0x18000cd77  mov     [rcx], r15w
0x18000cd7b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000cd82  test    rax, rax
0x18000cd85  jz      short loc_18000CDA8
0x18000cd87  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000cd8e  jz      short loc_18000CDA8
0x18000cd90  mov     r8, rdx
0x18000cd93  mov     rdx, rcx
0x18000cd96  mov     rcx, rbx
0x18000cd99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd9e  cmp     [r14], r15w
0x18000cda2  jnz     loc_18000CFC1
0x18000cda8  mov     ecx, [rbx]
0x18000cdaa  mov     bpl, 8
0x18000cdad  test    ecx, ecx
0x18000cdaf  jz      short loc_18000CDFA
0x18000cdb1  sub     ecx, 1
0x18000cdb4  jz      short loc_18000CDE2
0x18000cdb6  sub     ecx, 1
0x18000cdb9  jz      short loc_18000CDD2
0x18000cdbb  cmp     ecx, 1
0x18000cdbe  jz      short loc_18000CDC9
0x18000cdc0  lea     rdi, qword_180017450
0x18000cdc7  jmp     short loc_18000CE01
0x18000cdc9  lea     rdi, aFailfast; "FailFast"
0x18000cdd0  jmp     short loc_18000CE01
0x18000cdd2  lea     rax, aLoghr; "LogHr"
0x18000cdd9  lea     rdi, aLognt; "LogNt"
0x18000cde0  jmp     short loc_18000CDF0
0x18000cde2  lea     rax, aReturnhr; "ReturnHr"
0x18000cde9  lea     rdi, aReturnnt; "ReturnNt"
0x18000cdf0  test    [rbx+4], bpl
0x18000cdf4  cmovz   rdi, rax
0x18000cdf8  jmp     short loc_18000CE01
0x18000cdfa  lea     rdi, aException; "Exception"
0x18000ce01  xor     edx, edx; Val
0x18000ce03  mov     r8d, 200h; Size
0x18000ce09  lea     rcx, [rsp+278h+Buffer]; void *
0x18000ce0e  call    memset_0
0x18000ce13  test    [rbx+4], bpl
0x18000ce17  jz      short loc_18000CE3C
0x18000ce19  mov     ebp, [rbx+0Ch]
0x18000ce1c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000ce23  test    rax, rax
0x18000ce26  jz      short loc_18000CE6C
0x18000ce28  mov     r8d, 100h
0x18000ce2e  lea     rdx, [rsp+278h+Buffer]
0x18000ce33  mov     ecx, ebp
0x18000ce35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce3a  jmp     short loc_18000CE6C
0x18000ce3c  mov     ebp, [rbx+8]
0x18000ce3f  mov     [rsp+278h+Arguments], r15; Arguments
0x18000ce44  mov     [rsp+278h+nSize], 100h; nSize
0x18000ce4c  lea     rax, [rsp+278h+Buffer]
0x18000ce51  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000ce56  mov     r9d, 400h; dwLanguageId
0x18000ce5c  mov     r8d, ebp; dwMessageId
0x18000ce5f  xor     edx, edx; lpSource
0x18000ce61  mov     ecx, 1200h; dwFlags
0x18000ce66  call    cs:__imp_FormatMessageW
0x18000ce6c  lea     rsi, [r14+rsi*2]
0x18000ce70  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000ce74  mov     rax, [rbx+88h]
0x18000ce7b  mov     rcx, [rbx+80h]
0x18000ce82  mov     rdx, rsi; unsigned __int16 *
0x18000ce85  test    r9, r9
0x18000ce88  jz      short loc_18000CEAC
0x18000ce8a  mov     [rsp+278h+Arguments], rax
0x18000ce8f  mov     qword ptr [rsp+278h+nSize], rcx
0x18000ce94  mov     eax, [rbx+40h]
0x18000ce97  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000ce9b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000cea2  mov     rcx, r14; this
0x18000cea5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ceaa  jmp     short loc_18000CEC3
0x18000ceac  mov     [rsp+278h+lpBuffer], rax
0x18000ceb1  mov     r9, rcx; unsigned __int16 *
0x18000ceb4  lea     r8, aHsP; "%hs!%p: "
0x18000cebb  mov     rcx, r14; this
0x18000cebe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cec3  mov     r14, rax
0x18000cec6  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000cecd  test    r9, r9
0x18000ced0  jz      short loc_18000CEE7
0x18000ced2  lea     r8, aCallerP; "(caller: %p) "
0x18000ced9  mov     rdx, rsi; unsigned __int16 *
0x18000cedc  mov     rcx, rax; this
0x18000cedf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cee4  mov     r14, rax
0x18000cee7  call    cs:__imp_GetCurrentThreadId
0x18000ceed  lea     rcx, [rsp+278h+Buffer]
0x18000cef2  mov     [rsp+278h+var_240], rcx
0x18000cef7  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000cefb  mov     [rsp+278h+nSize], eax
0x18000ceff  mov     eax, [rbx+44h]
0x18000cf02  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000cf06  mov     r9, rdi; unsigned __int16 *
0x18000cf09  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000cf10  mov     rdx, rsi; unsigned __int16 *
0x18000cf13  mov     rcx, r14; this
0x18000cf16  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cf1b  cmp     [rbx+18h], r15
0x18000cf1f  jnz     short loc_18000CF31
0x18000cf21  cmp     [rbx+48h], r15
0x18000cf25  jnz     short loc_18000CF31
0x18000cf27  cmp     [rbx+30h], r15
0x18000cf2b  jz      loc_18000CFC1
0x18000cf31  lea     r8, asc_180017558; "    "
0x18000cf38  mov     rdx, rsi; unsigned __int16 *
0x18000cf3b  mov     rcx, rax; this
0x18000cf3e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cf43  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000cf47  test    r9, r9
0x18000cf4a  jz      short loc_18000CF5E
0x18000cf4c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000cf53  mov     rdx, rsi; unsigned __int16 *
0x18000cf56  mov     rcx, rax; this
0x18000cf59  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cf5e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000cf62  test    r9, r9
0x18000cf65  jz      short loc_18000CF79
0x18000cf67  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000cf6e  mov     rdx, rsi; unsigned __int16 *
0x18000cf71  mov     rcx, rax; this
0x18000cf74  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cf79  mov     rcx, [rbx+28h]
0x18000cf7d  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000cf81  mov     rdx, rsi; unsigned __int16 *
0x18000cf84  test    rcx, rcx
0x18000cf87  jz      short loc_18000CF9F
0x18000cf89  mov     [rsp+278h+lpBuffer], rcx
0x18000cf8e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000cf95  mov     rcx, rax; this
0x18000cf98  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cf9d  jmp     short loc_18000CFC1
0x18000cf9f  mov     rcx, rax; this
0x18000cfa2  test    r9, r9
0x18000cfa5  jz      short loc_18000CFB5
0x18000cfa7  lea     r8, aHs; "[%hs]\n"
0x18000cfae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cfb3  jmp     short loc_18000CFC1
0x18000cfb5  lea     r8, asc_1800175D0; "\n"
0x18000cfbc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cfc1  xor     eax, eax
0x18000cfc3  mov     rcx, [rsp+278h+var_38]
0x18000cfcb  xor     rcx, rsp; StackCookie
0x18000cfce  call    __security_check_cookie
0x18000cfd3  mov     rbx, [rsp+278h+arg_18]
0x18000cfdb  add     rsp, 250h
0x18000cfe2  pop     r15
0x18000cfe4  pop     r14
0x18000cfe6  pop     rdi
0x18000cfe7  pop     rsi
0x18000cfe8  pop     rbp
0x18000cfe9  retn
```
