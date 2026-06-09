# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800099e4`
- end: `0x180009c9a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180007790`
- `0x1800079f8`
- `0x18000a344`
- `0x18000d100`

## callees

- `0x1800099e4`
- `0x18000a644`
- `0x180015cbe`
- `0x180015cf0`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180009b97`
- `KERNEL32!GetCurrentThreadId` at `0x180009b97`
- `KERNEL32!FormatMessageW` at `0x180009b16`
- `KERNEL32!FormatMessageW` at `0x180009b16`

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
          v7 = (const char *)&byte_180019DE0;
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
0x1800099e4  mov     [rsp+arg_18], rbx
0x1800099e9  push    rbp
0x1800099ea  push    rsi
0x1800099eb  push    rdi
0x1800099ec  push    r14
0x1800099ee  push    r15
0x1800099f0  sub     rsp, 250h
0x1800099f7  mov     rax, cs:__security_cookie
0x1800099fe  xor     rax, rsp
0x180009a01  mov     [rsp+278h+var_38], rax
0x180009a09  mov     rbx, r8
0x180009a0c  mov     rsi, rdx
0x180009a0f  mov     r14, rcx
0x180009a12  xor     r15d, r15d
0x180009a15  test    rdx, rdx
0x180009a18  jz      loc_180009C71
0x180009a1e  test    rcx, rcx
0x180009a21  jz      loc_180009C71
0x180009a27  mov     [rcx], r15w
0x180009a2b  mov     rax, cs:g_pfnResultLoggingCallback
0x180009a32  test    rax, rax
0x180009a35  jz      short loc_180009A58
0x180009a37  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180009a3e  jz      short loc_180009A58
0x180009a40  mov     r8, rdx
0x180009a43  mov     rdx, rcx
0x180009a46  mov     rcx, rbx
0x180009a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a4e  cmp     [r14], r15w
0x180009a52  jnz     loc_180009C71
0x180009a58  mov     ecx, [rbx]
0x180009a5a  mov     bpl, 8
0x180009a5d  test    ecx, ecx
0x180009a5f  jz      short loc_180009AAA
0x180009a61  sub     ecx, 1
0x180009a64  jz      short loc_180009A92
0x180009a66  sub     ecx, 1
0x180009a69  jz      short loc_180009A82
0x180009a6b  cmp     ecx, 1
0x180009a6e  jz      short loc_180009A79
0x180009a70  lea     rdi, byte_180019DE0
0x180009a77  jmp     short loc_180009AB1
0x180009a79  lea     rdi, aFailfast; "FailFast"
0x180009a80  jmp     short loc_180009AB1
0x180009a82  lea     rax, aLoghr; "LogHr"
0x180009a89  lea     rdi, aLognt; "LogNt"
0x180009a90  jmp     short loc_180009AA0
0x180009a92  lea     rax, aReturnhr; "ReturnHr"
0x180009a99  lea     rdi, aReturnnt; "ReturnNt"
0x180009aa0  test    [rbx+4], bpl
0x180009aa4  cmovz   rdi, rax
0x180009aa8  jmp     short loc_180009AB1
0x180009aaa  lea     rdi, aException; "Exception"
0x180009ab1  xor     edx, edx; Val
0x180009ab3  mov     r8d, 200h; Size
0x180009ab9  lea     rcx, [rsp+278h+Buffer]; void *
0x180009abe  call    memset_0
0x180009ac3  test    [rbx+4], bpl
0x180009ac7  jz      short loc_180009AEC
0x180009ac9  mov     ebp, [rbx+0Ch]
0x180009acc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180009ad3  test    rax, rax
0x180009ad6  jz      short loc_180009B1C
0x180009ad8  mov     r8d, 100h
0x180009ade  lea     rdx, [rsp+278h+Buffer]
0x180009ae3  mov     ecx, ebp
0x180009ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009aea  jmp     short loc_180009B1C
0x180009aec  mov     ebp, [rbx+8]
0x180009aef  mov     [rsp+278h+Arguments], r15; Arguments
0x180009af4  mov     [rsp+278h+nSize], 100h; nSize
0x180009afc  lea     rax, [rsp+278h+Buffer]
0x180009b01  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180009b06  mov     r9d, 400h; dwLanguageId
0x180009b0c  mov     r8d, ebp; dwMessageId
0x180009b0f  xor     edx, edx; lpSource
0x180009b11  mov     ecx, 1200h; dwFlags
0x180009b16  call    cs:__imp_FormatMessageW
0x180009b1c  lea     rsi, [r14+rsi*2]
0x180009b20  mov     r9, [rbx+38h]; unsigned __int16 *
0x180009b24  mov     rax, [rbx+88h]
0x180009b2b  mov     rcx, [rbx+80h]
0x180009b32  mov     rdx, rsi; unsigned __int16 *
0x180009b35  test    r9, r9
0x180009b38  jz      short loc_180009B5C
0x180009b3a  mov     [rsp+278h+Arguments], rax
0x180009b3f  mov     qword ptr [rsp+278h+nSize], rcx
0x180009b44  mov     eax, [rbx+40h]
0x180009b47  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009b4b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180009b52  mov     rcx, r14; this
0x180009b55  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009b5a  jmp     short loc_180009B73
0x180009b5c  mov     [rsp+278h+lpBuffer], rax
0x180009b61  mov     r9, rcx; unsigned __int16 *
0x180009b64  lea     r8, aHsP; "%hs!%p: "
0x180009b6b  mov     rcx, r14; this
0x180009b6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009b73  mov     r14, rax
0x180009b76  mov     r9, [rbx+90h]; unsigned __int16 *
0x180009b7d  test    r9, r9
0x180009b80  jz      short loc_180009B97
0x180009b82  lea     r8, aCallerP; "(caller: %p) "
0x180009b89  mov     rdx, rsi; unsigned __int16 *
0x180009b8c  mov     rcx, rax; this
0x180009b8f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009b94  mov     r14, rax
0x180009b97  call    cs:__imp_GetCurrentThreadId
0x180009b9d  lea     rcx, [rsp+278h+Buffer]
0x180009ba2  mov     [rsp+278h+var_240], rcx
0x180009ba7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180009bab  mov     [rsp+278h+nSize], eax
0x180009baf  mov     eax, [rbx+44h]
0x180009bb2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009bb6  mov     r9, rdi; unsigned __int16 *
0x180009bb9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180009bc0  mov     rdx, rsi; unsigned __int16 *
0x180009bc3  mov     rcx, r14; this
0x180009bc6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009bcb  cmp     [rbx+18h], r15
0x180009bcf  jnz     short loc_180009BE1
0x180009bd1  cmp     [rbx+48h], r15
0x180009bd5  jnz     short loc_180009BE1
0x180009bd7  cmp     [rbx+30h], r15
0x180009bdb  jz      loc_180009C71
0x180009be1  lea     r8, asc_180019EE0; "    "
0x180009be8  mov     rdx, rsi; unsigned __int16 *
0x180009beb  mov     rcx, rax; this
0x180009bee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009bf3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180009bf7  test    r9, r9
0x180009bfa  jz      short loc_180009C0E
0x180009bfc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180009c03  mov     rdx, rsi; unsigned __int16 *
0x180009c06  mov     rcx, rax; this
0x180009c09  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009c0e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180009c12  test    r9, r9
0x180009c15  jz      short loc_180009C29
0x180009c17  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180009c1e  mov     rdx, rsi; unsigned __int16 *
0x180009c21  mov     rcx, rax; this
0x180009c24  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009c29  mov     rcx, [rbx+28h]
0x180009c2d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180009c31  mov     rdx, rsi; unsigned __int16 *
0x180009c34  test    rcx, rcx
0x180009c37  jz      short loc_180009C4F
0x180009c39  mov     [rsp+278h+lpBuffer], rcx
0x180009c3e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180009c45  mov     rcx, rax; this
0x180009c48  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009c4d  jmp     short loc_180009C71
0x180009c4f  mov     rcx, rax; this
0x180009c52  test    r9, r9
0x180009c55  jz      short loc_180009C65
0x180009c57  lea     r8, aHs; "[%hs]\n"
0x180009c5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009c63  jmp     short loc_180009C71
0x180009c65  lea     r8, asc_180019DE4; "\n"
0x180009c6c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009c71  xor     eax, eax
0x180009c73  mov     rcx, [rsp+278h+var_38]
0x180009c7b  xor     rcx, rsp; StackCookie
0x180009c7e  call    __security_check_cookie
0x180009c83  mov     rbx, [rsp+278h+arg_18]
0x180009c8b  add     rsp, 250h
0x180009c92  pop     r15
0x180009c94  pop     r14
0x180009c96  pop     rdi
0x180009c97  pop     rsi
0x180009c98  pop     rbp
0x180009c99  retn
```
