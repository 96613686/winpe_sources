# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800098e4`
- end: `0x180009b9a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800079d0`
- `0x180007c38`
- `0x18000a240`

## callees

- `0x1800098e4`
- `0x18000a540`
- `0x18000d89e`
- `0x18000d8d0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009a97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009a97`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009a16`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009a16`

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
          v8 = (const char *)&qword_1800103C0;
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
0x1800098e4  mov     [rsp+arg_18], rbx
0x1800098e9  push    rbp
0x1800098ea  push    rsi
0x1800098eb  push    rdi
0x1800098ec  push    r14
0x1800098ee  push    r15
0x1800098f0  sub     rsp, 250h
0x1800098f7  mov     rax, cs:__security_cookie
0x1800098fe  xor     rax, rsp
0x180009901  mov     [rsp+278h+var_38], rax
0x180009909  xor     r15d, r15d
0x18000990c  mov     rbx, r8
0x18000990f  mov     rsi, rdx
0x180009912  mov     r14, rcx
0x180009915  test    rdx, rdx
0x180009918  jz      loc_180009B71
0x18000991e  test    rcx, rcx
0x180009921  jz      loc_180009B71
0x180009927  mov     rax, cs:g_pfnResultLoggingCallback
0x18000992e  mov     [rcx], r15w
0x180009932  test    rax, rax
0x180009935  jz      short loc_180009958
0x180009937  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000993e  jz      short loc_180009958
0x180009940  mov     r8, rdx
0x180009943  mov     rdx, rcx
0x180009946  mov     rcx, rbx
0x180009949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000994e  cmp     [r14], r15w
0x180009952  jnz     loc_180009B71
0x180009958  mov     ecx, [rbx]
0x18000995a  mov     bpl, 8
0x18000995d  test    ecx, ecx
0x18000995f  jz      short loc_1800099AA
0x180009961  sub     ecx, 1
0x180009964  jz      short loc_180009992
0x180009966  sub     ecx, 1
0x180009969  jz      short loc_180009982
0x18000996b  cmp     ecx, 1
0x18000996e  jz      short loc_180009979
0x180009970  lea     rdi, qword_1800103C0
0x180009977  jmp     short loc_1800099B1
0x180009979  lea     rdi, aFailfast; "FailFast"
0x180009980  jmp     short loc_1800099B1
0x180009982  lea     rax, aLoghr; "LogHr"
0x180009989  lea     rdi, aLognt; "LogNt"
0x180009990  jmp     short loc_1800099A0
0x180009992  lea     rax, aReturnhr; "ReturnHr"
0x180009999  lea     rdi, aReturnnt; "ReturnNt"
0x1800099a0  test    [rbx+4], bpl
0x1800099a4  cmovz   rdi, rax
0x1800099a8  jmp     short loc_1800099B1
0x1800099aa  lea     rdi, aException; "Exception"
0x1800099b1  xor     edx, edx; Val
0x1800099b3  lea     rcx, [rsp+278h+Buffer]; void *
0x1800099b8  mov     r8d, 200h; Size
0x1800099be  call    memset_0
0x1800099c3  test    [rbx+4], bpl
0x1800099c7  jz      short loc_1800099EC
0x1800099c9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800099d0  mov     ebp, [rbx+0Ch]
0x1800099d3  test    rax, rax
0x1800099d6  jz      short loc_180009A1C
0x1800099d8  mov     r8d, 100h
0x1800099de  lea     rdx, [rsp+278h+Buffer]
0x1800099e3  mov     ecx, ebp
0x1800099e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099ea  jmp     short loc_180009A1C
0x1800099ec  mov     ebp, [rbx+8]
0x1800099ef  lea     rax, [rsp+278h+Buffer]
0x1800099f4  mov     [rsp+278h+Arguments], r15; Arguments
0x1800099f9  mov     r8d, ebp; dwMessageId
0x1800099fc  mov     [rsp+278h+nSize], 100h; nSize
0x180009a04  mov     r9d, 400h; dwLanguageId
0x180009a0a  xor     edx, edx; lpSource
0x180009a0c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180009a11  mov     ecx, 1200h; dwFlags
0x180009a16  call    cs:__imp_FormatMessageW
0x180009a1c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180009a20  lea     rsi, [r14+rsi*2]
0x180009a24  mov     rax, [rbx+88h]
0x180009a2b  mov     rdx, rsi; unsigned __int16 *
0x180009a2e  mov     rcx, [rbx+80h]
0x180009a35  test    r9, r9
0x180009a38  jz      short loc_180009A5C
0x180009a3a  mov     [rsp+278h+Arguments], rax
0x180009a3f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180009a46  mov     eax, [rbx+40h]
0x180009a49  mov     qword ptr [rsp+278h+nSize], rcx
0x180009a4e  mov     rcx, r14; this
0x180009a51  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009a55  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009a5a  jmp     short loc_180009A73
0x180009a5c  mov     r9, rcx; unsigned __int16 *
0x180009a5f  mov     [rsp+278h+lpBuffer], rax
0x180009a64  mov     rcx, r14; this
0x180009a67  lea     r8, aHsP; "%hs!%p: "
0x180009a6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009a73  mov     r9, [rbx+90h]; unsigned __int16 *
0x180009a7a  mov     r14, rax
0x180009a7d  test    r9, r9
0x180009a80  jz      short loc_180009A97
0x180009a82  lea     r8, aCallerP; "(caller: %p) "
0x180009a89  mov     rdx, rsi; unsigned __int16 *
0x180009a8c  mov     rcx, rax; this
0x180009a8f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009a94  mov     r14, rax
0x180009a97  call    cs:__imp_GetCurrentThreadId
0x180009a9d  lea     rcx, [rsp+278h+Buffer]
0x180009aa2  mov     r9, rdi; unsigned __int16 *
0x180009aa5  mov     [rsp+278h+var_240], rcx
0x180009aaa  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180009ab1  mov     dword ptr [rsp+278h+Arguments], ebp
0x180009ab5  mov     rdx, rsi; unsigned __int16 *
0x180009ab8  mov     [rsp+278h+nSize], eax
0x180009abc  mov     rcx, r14; this
0x180009abf  mov     eax, [rbx+44h]
0x180009ac2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009ac6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009acb  cmp     [rbx+18h], r15
0x180009acf  jnz     short loc_180009AE1
0x180009ad1  cmp     [rbx+48h], r15
0x180009ad5  jnz     short loc_180009AE1
0x180009ad7  cmp     [rbx+30h], r15
0x180009adb  jz      loc_180009B71
0x180009ae1  lea     r8, asc_18000FFE8; "    "
0x180009ae8  mov     rdx, rsi; unsigned __int16 *
0x180009aeb  mov     rcx, rax; this
0x180009aee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009af3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180009af7  test    r9, r9
0x180009afa  jz      short loc_180009B0E
0x180009afc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180009b03  mov     rdx, rsi; unsigned __int16 *
0x180009b06  mov     rcx, rax; this
0x180009b09  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009b0e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180009b12  test    r9, r9
0x180009b15  jz      short loc_180009B29
0x180009b17  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180009b1e  mov     rdx, rsi; unsigned __int16 *
0x180009b21  mov     rcx, rax; this
0x180009b24  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009b29  mov     rcx, [rbx+28h]
0x180009b2d  mov     rdx, rsi; unsigned __int16 *
0x180009b30  mov     r9, [rbx+30h]; unsigned __int16 *
0x180009b34  test    rcx, rcx
0x180009b37  jz      short loc_180009B4F
0x180009b39  mov     [rsp+278h+lpBuffer], rcx
0x180009b3e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180009b45  mov     rcx, rax; this
0x180009b48  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009b4d  jmp     short loc_180009B71
0x180009b4f  mov     rcx, rax; this
0x180009b52  test    r9, r9
0x180009b55  jz      short loc_180009B65
0x180009b57  lea     r8, aHs; "[%hs]\n"
0x180009b5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009b63  jmp     short loc_180009B71
0x180009b65  lea     r8, asc_180010060; "\n"
0x180009b6c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009b71  xor     eax, eax
0x180009b73  mov     rcx, [rsp+278h+var_38]
0x180009b7b  xor     rcx, rsp; StackCookie
0x180009b7e  call    __security_check_cookie
0x180009b83  mov     rbx, [rsp+278h+arg_18]
0x180009b8b  add     rsp, 250h
0x180009b92  pop     r15
0x180009b94  pop     r14
0x180009b96  pop     rdi
0x180009b97  pop     rsi
0x180009b98  pop     rbp
0x180009b99  retn
```
