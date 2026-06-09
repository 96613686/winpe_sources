# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000cea4`
- end: `0x18000d15a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000bf5c`
- `0x18000d610`
- `0x18000dac0`
- `0x18000ee40`

## callees

- `0x18000a520`
- `0x18000aef8`
- `0x18000cea4`
- `0x18000d910`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d057`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d057`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000cfd6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000cfd6`

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
          v7 = (const char *)&byte_1800223E7;
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
0x18000cea4  mov     [rsp+arg_18], rbx
0x18000cea9  push    rbp
0x18000ceaa  push    rsi
0x18000ceab  push    rdi
0x18000ceac  push    r14
0x18000ceae  push    r15
0x18000ceb0  sub     rsp, 250h
0x18000ceb7  mov     rax, cs:__security_cookie
0x18000cebe  xor     rax, rsp
0x18000cec1  mov     [rsp+278h+var_38], rax
0x18000cec9  mov     rbx, r8
0x18000cecc  mov     rsi, rdx
0x18000cecf  mov     r14, rcx
0x18000ced2  xor     r15d, r15d
0x18000ced5  test    rdx, rdx
0x18000ced8  jz      loc_18000D131
0x18000cede  test    rcx, rcx
0x18000cee1  jz      loc_18000D131
0x18000cee7  mov     [rcx], r15w
0x18000ceeb  mov     rax, cs:g_pfnResultLoggingCallback
0x18000cef2  test    rax, rax
0x18000cef5  jz      short loc_18000CF18
0x18000cef7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000cefe  jz      short loc_18000CF18
0x18000cf00  mov     r8, rdx
0x18000cf03  mov     rdx, rcx
0x18000cf06  mov     rcx, rbx
0x18000cf09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf0e  cmp     [r14], r15w
0x18000cf12  jnz     loc_18000D131
0x18000cf18  mov     ecx, [rbx]
0x18000cf1a  mov     bpl, 8
0x18000cf1d  test    ecx, ecx
0x18000cf1f  jz      short loc_18000CF6A
0x18000cf21  sub     ecx, 1
0x18000cf24  jz      short loc_18000CF52
0x18000cf26  sub     ecx, 1
0x18000cf29  jz      short loc_18000CF42
0x18000cf2b  cmp     ecx, 1
0x18000cf2e  jz      short loc_18000CF39
0x18000cf30  lea     rdi, byte_1800223E7
0x18000cf37  jmp     short loc_18000CF71
0x18000cf39  lea     rdi, aFailfast; "FailFast"
0x18000cf40  jmp     short loc_18000CF71
0x18000cf42  lea     rax, aLoghr; "LogHr"
0x18000cf49  lea     rdi, aLognt; "LogNt"
0x18000cf50  jmp     short loc_18000CF60
0x18000cf52  lea     rax, aReturnhr; "ReturnHr"
0x18000cf59  lea     rdi, aReturnnt; "ReturnNt"
0x18000cf60  test    [rbx+4], bpl
0x18000cf64  cmovz   rdi, rax
0x18000cf68  jmp     short loc_18000CF71
0x18000cf6a  lea     rdi, aException; "Exception"
0x18000cf71  xor     edx, edx; Val
0x18000cf73  mov     r8d, 200h; Size
0x18000cf79  lea     rcx, [rsp+278h+Buffer]; void *
0x18000cf7e  call    memset_0
0x18000cf83  test    [rbx+4], bpl
0x18000cf87  jz      short loc_18000CFAC
0x18000cf89  mov     ebp, [rbx+0Ch]
0x18000cf8c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000cf93  test    rax, rax
0x18000cf96  jz      short loc_18000CFDC
0x18000cf98  mov     r8d, 100h
0x18000cf9e  lea     rdx, [rsp+278h+Buffer]
0x18000cfa3  mov     ecx, ebp
0x18000cfa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfaa  jmp     short loc_18000CFDC
0x18000cfac  mov     ebp, [rbx+8]
0x18000cfaf  mov     [rsp+278h+Arguments], r15; Arguments
0x18000cfb4  mov     [rsp+278h+nSize], 100h; nSize
0x18000cfbc  lea     rax, [rsp+278h+Buffer]
0x18000cfc1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000cfc6  mov     r9d, 400h; dwLanguageId
0x18000cfcc  mov     r8d, ebp; dwMessageId
0x18000cfcf  xor     edx, edx; lpSource
0x18000cfd1  mov     ecx, 1200h; dwFlags
0x18000cfd6  call    cs:__imp_FormatMessageW
0x18000cfdc  lea     rsi, [r14+rsi*2]
0x18000cfe0  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000cfe4  mov     rax, [rbx+88h]
0x18000cfeb  mov     rcx, [rbx+80h]
0x18000cff2  mov     rdx, rsi; unsigned __int16 *
0x18000cff5  test    r9, r9
0x18000cff8  jz      short loc_18000D01C
0x18000cffa  mov     [rsp+278h+Arguments], rax
0x18000cfff  mov     qword ptr [rsp+278h+nSize], rcx
0x18000d004  mov     eax, [rbx+40h]
0x18000d007  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000d00b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000d012  mov     rcx, r14; this
0x18000d015  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d01a  jmp     short loc_18000D033
0x18000d01c  mov     [rsp+278h+lpBuffer], rax
0x18000d021  mov     r9, rcx; unsigned __int16 *
0x18000d024  lea     r8, aHsP; "%hs!%p: "
0x18000d02b  mov     rcx, r14; this
0x18000d02e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d033  mov     r14, rax
0x18000d036  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000d03d  test    r9, r9
0x18000d040  jz      short loc_18000D057
0x18000d042  lea     r8, aCallerP; "(caller: %p) "
0x18000d049  mov     rdx, rsi; unsigned __int16 *
0x18000d04c  mov     rcx, rax; this
0x18000d04f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d054  mov     r14, rax
0x18000d057  call    cs:__imp_GetCurrentThreadId
0x18000d05d  lea     rcx, [rsp+278h+Buffer]
0x18000d062  mov     [rsp+278h+var_240], rcx
0x18000d067  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000d06b  mov     [rsp+278h+nSize], eax
0x18000d06f  mov     eax, [rbx+44h]
0x18000d072  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000d076  mov     r9, rdi; unsigned __int16 *
0x18000d079  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000d080  mov     rdx, rsi; unsigned __int16 *
0x18000d083  mov     rcx, r14; this
0x18000d086  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d08b  cmp     [rbx+18h], r15
0x18000d08f  jnz     short loc_18000D0A1
0x18000d091  cmp     [rbx+48h], r15
0x18000d095  jnz     short loc_18000D0A1
0x18000d097  cmp     [rbx+30h], r15
0x18000d09b  jz      loc_18000D131
0x18000d0a1  lea     r8, asc_180022508; "    "
0x18000d0a8  mov     rdx, rsi; unsigned __int16 *
0x18000d0ab  mov     rcx, rax; this
0x18000d0ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d0b3  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000d0b7  test    r9, r9
0x18000d0ba  jz      short loc_18000D0CE
0x18000d0bc  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000d0c3  mov     rdx, rsi; unsigned __int16 *
0x18000d0c6  mov     rcx, rax; this
0x18000d0c9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d0ce  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000d0d2  test    r9, r9
0x18000d0d5  jz      short loc_18000D0E9
0x18000d0d7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000d0de  mov     rdx, rsi; unsigned __int16 *
0x18000d0e1  mov     rcx, rax; this
0x18000d0e4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d0e9  mov     rcx, [rbx+28h]
0x18000d0ed  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000d0f1  mov     rdx, rsi; unsigned __int16 *
0x18000d0f4  test    rcx, rcx
0x18000d0f7  jz      short loc_18000D10F
0x18000d0f9  mov     [rsp+278h+lpBuffer], rcx
0x18000d0fe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000d105  mov     rcx, rax; this
0x18000d108  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d10d  jmp     short loc_18000D131
0x18000d10f  mov     rcx, rax; this
0x18000d112  test    r9, r9
0x18000d115  jz      short loc_18000D125
0x18000d117  lea     r8, aHs; "[%hs]\n"
0x18000d11e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d123  jmp     short loc_18000D131
0x18000d125  lea     r8, asc_180022580; "\n"
0x18000d12c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d131  xor     eax, eax
0x18000d133  mov     rcx, [rsp+278h+var_38]
0x18000d13b  xor     rcx, rsp; StackCookie
0x18000d13e  call    __security_check_cookie
0x18000d143  mov     rbx, [rsp+278h+arg_18]
0x18000d14b  add     rsp, 250h
0x18000d152  pop     r15
0x18000d154  pop     r14
0x18000d156  pop     rdi
0x18000d157  pop     rsi
0x18000d158  pop     rbp
0x18000d159  retn
```
