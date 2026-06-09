# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180003db4`
- end: `0x18000406a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180002f4c`
- `0x18000474c`
- `0x180004c04`
- `0x1800063f0`

## callees

- `0x180003db4`
- `0x180004a4c`
- `0x18002d1d2`
- `0x18002d200`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003f67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003f67`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003ee6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003ee6`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
          v7 = (const char *)&qword_180033AE0;
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
0x180003db4  mov     [rsp+arg_18], rbx
0x180003db9  push    rbp
0x180003dba  push    rsi
0x180003dbb  push    rdi
0x180003dbc  push    r14
0x180003dbe  push    r15
0x180003dc0  sub     rsp, 250h
0x180003dc7  mov     rax, cs:__security_cookie
0x180003dce  xor     rax, rsp
0x180003dd1  mov     [rsp+278h+var_38], rax
0x180003dd9  mov     rbx, r8
0x180003ddc  mov     rsi, rdx
0x180003ddf  mov     r14, rcx
0x180003de2  xor     r15d, r15d
0x180003de5  test    rdx, rdx
0x180003de8  jz      loc_180004041
0x180003dee  test    rcx, rcx
0x180003df1  jz      loc_180004041
0x180003df7  mov     [rcx], r15w
0x180003dfb  mov     rax, cs:g_pfnResultLoggingCallback
0x180003e02  test    rax, rax
0x180003e05  jz      short loc_180003E28
0x180003e07  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003e0e  jz      short loc_180003E28
0x180003e10  mov     r8, rdx
0x180003e13  mov     rdx, rcx
0x180003e16  mov     rcx, rbx
0x180003e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e1e  cmp     [r14], r15w
0x180003e22  jnz     loc_180004041
0x180003e28  mov     ecx, [rbx]
0x180003e2a  mov     bpl, 8
0x180003e2d  test    ecx, ecx
0x180003e2f  jz      short loc_180003E7A
0x180003e31  sub     ecx, 1
0x180003e34  jz      short loc_180003E62
0x180003e36  sub     ecx, 1
0x180003e39  jz      short loc_180003E52
0x180003e3b  cmp     ecx, 1
0x180003e3e  jz      short loc_180003E49
0x180003e40  lea     rdi, qword_180033AE0
0x180003e47  jmp     short loc_180003E81
0x180003e49  lea     rdi, aFailfast; "FailFast"
0x180003e50  jmp     short loc_180003E81
0x180003e52  lea     rax, aLoghr; "LogHr"
0x180003e59  lea     rdi, aLognt; "LogNt"
0x180003e60  jmp     short loc_180003E70
0x180003e62  lea     rax, aReturnhr; "ReturnHr"
0x180003e69  lea     rdi, aReturnnt; "ReturnNt"
0x180003e70  test    [rbx+4], bpl
0x180003e74  cmovz   rdi, rax
0x180003e78  jmp     short loc_180003E81
0x180003e7a  lea     rdi, aException; "Exception"
0x180003e81  xor     edx, edx; Val
0x180003e83  mov     r8d, 200h; Size
0x180003e89  lea     rcx, [rsp+278h+Buffer]; void *
0x180003e8e  call    memset_0
0x180003e93  test    [rbx+4], bpl
0x180003e97  jz      short loc_180003EBC
0x180003e99  mov     ebp, [rbx+0Ch]
0x180003e9c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180003ea3  test    rax, rax
0x180003ea6  jz      short loc_180003EEC
0x180003ea8  mov     r8d, 100h
0x180003eae  lea     rdx, [rsp+278h+Buffer]
0x180003eb3  mov     ecx, ebp
0x180003eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eba  jmp     short loc_180003EEC
0x180003ebc  mov     ebp, [rbx+8]
0x180003ebf  mov     [rsp+278h+Arguments], r15; Arguments
0x180003ec4  mov     [rsp+278h+nSize], 100h; nSize
0x180003ecc  lea     rax, [rsp+278h+Buffer]
0x180003ed1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180003ed6  mov     r9d, 400h; dwLanguageId
0x180003edc  mov     r8d, ebp; dwMessageId
0x180003edf  xor     edx, edx; lpSource
0x180003ee1  mov     ecx, 1200h; dwFlags
0x180003ee6  call    cs:__imp_FormatMessageW
0x180003eec  lea     rsi, [r14+rsi*2]
0x180003ef0  mov     r9, [rbx+38h]; unsigned __int16 *
0x180003ef4  mov     rax, [rbx+88h]
0x180003efb  mov     rcx, [rbx+80h]
0x180003f02  mov     rdx, rsi; unsigned __int16 *
0x180003f05  test    r9, r9
0x180003f08  jz      short loc_180003F2C
0x180003f0a  mov     [rsp+278h+Arguments], rax
0x180003f0f  mov     qword ptr [rsp+278h+nSize], rcx
0x180003f14  mov     eax, [rbx+40h]
0x180003f17  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003f1b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180003f22  mov     rcx, r14; this
0x180003f25  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003f2a  jmp     short loc_180003F43
0x180003f2c  mov     [rsp+278h+lpBuffer], rax
0x180003f31  mov     r9, rcx; unsigned __int16 *
0x180003f34  lea     r8, aHsP; "%hs!%p: "
0x180003f3b  mov     rcx, r14; this
0x180003f3e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003f43  mov     r14, rax
0x180003f46  mov     r9, [rbx+90h]; unsigned __int16 *
0x180003f4d  test    r9, r9
0x180003f50  jz      short loc_180003F67
0x180003f52  lea     r8, aCallerP; "(caller: %p) "
0x180003f59  mov     rdx, rsi; unsigned __int16 *
0x180003f5c  mov     rcx, rax; this
0x180003f5f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003f64  mov     r14, rax
0x180003f67  call    cs:__imp_GetCurrentThreadId
0x180003f6d  lea     rcx, [rsp+278h+Buffer]
0x180003f72  mov     [rsp+278h+var_240], rcx
0x180003f77  mov     dword ptr [rsp+278h+Arguments], ebp
0x180003f7b  mov     [rsp+278h+nSize], eax
0x180003f7f  mov     eax, [rbx+44h]
0x180003f82  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003f86  mov     r9, rdi; unsigned __int16 *
0x180003f89  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180003f90  mov     rdx, rsi; unsigned __int16 *
0x180003f93  mov     rcx, r14; this
0x180003f96  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003f9b  cmp     [rbx+18h], r15
0x180003f9f  jnz     short loc_180003FB1
0x180003fa1  cmp     [rbx+48h], r15
0x180003fa5  jnz     short loc_180003FB1
0x180003fa7  cmp     [rbx+30h], r15
0x180003fab  jz      loc_180004041
0x180003fb1  lea     r8, asc_180033BD0; "    "
0x180003fb8  mov     rdx, rsi; unsigned __int16 *
0x180003fbb  mov     rcx, rax; this
0x180003fbe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003fc3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180003fc7  test    r9, r9
0x180003fca  jz      short loc_180003FDE
0x180003fcc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180003fd3  mov     rdx, rsi; unsigned __int16 *
0x180003fd6  mov     rcx, rax; this
0x180003fd9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003fde  mov     r9, [rbx+48h]; unsigned __int16 *
0x180003fe2  test    r9, r9
0x180003fe5  jz      short loc_180003FF9
0x180003fe7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180003fee  mov     rdx, rsi; unsigned __int16 *
0x180003ff1  mov     rcx, rax; this
0x180003ff4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003ff9  mov     rcx, [rbx+28h]
0x180003ffd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004001  mov     rdx, rsi; unsigned __int16 *
0x180004004  test    rcx, rcx
0x180004007  jz      short loc_18000401F
0x180004009  mov     [rsp+278h+lpBuffer], rcx
0x18000400e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004015  mov     rcx, rax; this
0x180004018  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000401d  jmp     short loc_180004041
0x18000401f  mov     rcx, rax; this
0x180004022  test    r9, r9
0x180004025  jz      short loc_180004035
0x180004027  lea     r8, aHs; "[%hs]\n"
0x18000402e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004033  jmp     short loc_180004041
0x180004035  lea     r8, asc_180033C48; "\n"
0x18000403c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004041  xor     eax, eax
0x180004043  mov     rcx, [rsp+278h+var_38]
0x18000404b  xor     rcx, rsp; StackCookie
0x18000404e  call    __security_check_cookie
0x180004053  mov     rbx, [rsp+278h+arg_18]
0x18000405b  add     rsp, 250h
0x180004062  pop     r15
0x180004064  pop     r14
0x180004066  pop     rdi
0x180004067  pop     rsi
0x180004068  pop     rbp
0x180004069  retn
```
