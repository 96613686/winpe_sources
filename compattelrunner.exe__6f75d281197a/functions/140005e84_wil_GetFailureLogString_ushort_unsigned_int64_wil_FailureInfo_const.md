# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140005e84`
- end: `0x14000613a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x1400033e4`
- `0x14000364c`
- `0x1400068cc`
- `0x14000a490`
- `0x14000aebc`

## callees

- `0x140001ba0`
- `0x1400026c0`
- `0x140005e84`
- `0x140006bcc`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006037`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006037`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140005fb6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140005fb6`

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
          v7 = (const char *)&dword_1400ACDEC;
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
0x140005e84  mov     [rsp+arg_18], rbx
0x140005e89  push    rbp
0x140005e8a  push    rsi
0x140005e8b  push    rdi
0x140005e8c  push    r14
0x140005e8e  push    r15
0x140005e90  sub     rsp, 250h
0x140005e97  mov     rax, cs:__security_cookie
0x140005e9e  xor     rax, rsp
0x140005ea1  mov     [rsp+278h+var_38], rax
0x140005ea9  mov     rbx, r8
0x140005eac  mov     rsi, rdx
0x140005eaf  mov     r14, rcx
0x140005eb2  xor     r15d, r15d
0x140005eb5  test    rdx, rdx
0x140005eb8  jz      loc_140006111
0x140005ebe  test    rcx, rcx
0x140005ec1  jz      loc_140006111
0x140005ec7  mov     [rcx], r15w
0x140005ecb  mov     rax, cs:g_pfnResultLoggingCallback
0x140005ed2  test    rax, rax
0x140005ed5  jz      short loc_140005EF8
0x140005ed7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140005ede  jz      short loc_140005EF8
0x140005ee0  mov     r8, rdx
0x140005ee3  mov     rdx, rcx
0x140005ee6  mov     rcx, rbx
0x140005ee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005eee  cmp     [r14], r15w
0x140005ef2  jnz     loc_140006111
0x140005ef8  mov     ecx, [rbx]
0x140005efa  mov     bpl, 8
0x140005efd  test    ecx, ecx
0x140005eff  jz      short loc_140005F4A
0x140005f01  sub     ecx, 1
0x140005f04  jz      short loc_140005F32
0x140005f06  sub     ecx, 1
0x140005f09  jz      short loc_140005F22
0x140005f0b  cmp     ecx, 1
0x140005f0e  jz      short loc_140005F19
0x140005f10  lea     rdi, dword_1400ACDEC
0x140005f17  jmp     short loc_140005F51
0x140005f19  lea     rdi, aFailfast; "FailFast"
0x140005f20  jmp     short loc_140005F51
0x140005f22  lea     rax, aLoghr; "LogHr"
0x140005f29  lea     rdi, aLognt; "LogNt"
0x140005f30  jmp     short loc_140005F40
0x140005f32  lea     rax, aReturnhr; "ReturnHr"
0x140005f39  lea     rdi, aReturnnt; "ReturnNt"
0x140005f40  test    [rbx+4], bpl
0x140005f44  cmovz   rdi, rax
0x140005f48  jmp     short loc_140005F51
0x140005f4a  lea     rdi, aException; "Exception"
0x140005f51  xor     edx, edx; Val
0x140005f53  mov     r8d, 200h; Size
0x140005f59  lea     rcx, [rsp+278h+Buffer]; void *
0x140005f5e  call    memset_0
0x140005f63  test    [rbx+4], bpl
0x140005f67  jz      short loc_140005F8C
0x140005f69  mov     ebp, [rbx+0Ch]
0x140005f6c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140005f73  test    rax, rax
0x140005f76  jz      short loc_140005FBC
0x140005f78  mov     r8d, 100h
0x140005f7e  lea     rdx, [rsp+278h+Buffer]
0x140005f83  mov     ecx, ebp
0x140005f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f8a  jmp     short loc_140005FBC
0x140005f8c  mov     ebp, [rbx+8]
0x140005f8f  mov     [rsp+278h+Arguments], r15; Arguments
0x140005f94  mov     [rsp+278h+nSize], 100h; nSize
0x140005f9c  lea     rax, [rsp+278h+Buffer]
0x140005fa1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140005fa6  mov     r9d, 400h; dwLanguageId
0x140005fac  mov     r8d, ebp; dwMessageId
0x140005faf  xor     edx, edx; lpSource
0x140005fb1  mov     ecx, 1200h; dwFlags
0x140005fb6  call    cs:__imp_FormatMessageW
0x140005fbc  lea     rsi, [r14+rsi*2]
0x140005fc0  mov     r9, [rbx+38h]; unsigned __int16 *
0x140005fc4  mov     rax, [rbx+88h]
0x140005fcb  mov     rcx, [rbx+80h]
0x140005fd2  mov     rdx, rsi; unsigned __int16 *
0x140005fd5  test    r9, r9
0x140005fd8  jz      short loc_140005FFC
0x140005fda  mov     [rsp+278h+Arguments], rax
0x140005fdf  mov     qword ptr [rsp+278h+nSize], rcx
0x140005fe4  mov     eax, [rbx+40h]
0x140005fe7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140005feb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140005ff2  mov     rcx, r14; this
0x140005ff5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005ffa  jmp     short loc_140006013
0x140005ffc  mov     [rsp+278h+lpBuffer], rax
0x140006001  mov     r9, rcx; unsigned __int16 *
0x140006004  lea     r8, aHsP; "%hs!%p: "
0x14000600b  mov     rcx, r14; this
0x14000600e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006013  mov     r14, rax
0x140006016  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000601d  test    r9, r9
0x140006020  jz      short loc_140006037
0x140006022  lea     r8, aCallerP; "(caller: %p) "
0x140006029  mov     rdx, rsi; unsigned __int16 *
0x14000602c  mov     rcx, rax; this
0x14000602f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006034  mov     r14, rax
0x140006037  call    cs:__imp_GetCurrentThreadId
0x14000603d  lea     rcx, [rsp+278h+Buffer]
0x140006042  mov     [rsp+278h+var_240], rcx
0x140006047  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000604b  mov     [rsp+278h+nSize], eax
0x14000604f  mov     eax, [rbx+44h]
0x140006052  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140006056  mov     r9, rdi; unsigned __int16 *
0x140006059  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140006060  mov     rdx, rsi; unsigned __int16 *
0x140006063  mov     rcx, r14; this
0x140006066  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000606b  cmp     [rbx+18h], r15
0x14000606f  jnz     short loc_140006081
0x140006071  cmp     [rbx+48h], r15
0x140006075  jnz     short loc_140006081
0x140006077  cmp     [rbx+30h], r15
0x14000607b  jz      loc_140006111
0x140006081  lea     r8, asc_1400ACF28; "    "
0x140006088  mov     rdx, rsi; unsigned __int16 *
0x14000608b  mov     rcx, rax; this
0x14000608e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006093  mov     r9, [rbx+18h]; unsigned __int16 *
0x140006097  test    r9, r9
0x14000609a  jz      short loc_1400060AE
0x14000609c  lea     r8, aMsgWs; "Msg:[%ws] "
0x1400060a3  mov     rdx, rsi; unsigned __int16 *
0x1400060a6  mov     rcx, rax; this
0x1400060a9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400060ae  mov     r9, [rbx+48h]; unsigned __int16 *
0x1400060b2  test    r9, r9
0x1400060b5  jz      short loc_1400060C9
0x1400060b7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1400060be  mov     rdx, rsi; unsigned __int16 *
0x1400060c1  mov     rcx, rax; this
0x1400060c4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400060c9  mov     rcx, [rbx+28h]
0x1400060cd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1400060d1  mov     rdx, rsi; unsigned __int16 *
0x1400060d4  test    rcx, rcx
0x1400060d7  jz      short loc_1400060EF
0x1400060d9  mov     [rsp+278h+lpBuffer], rcx
0x1400060de  lea     r8, aHsHs_1; "[%hs(%hs)]\n"
0x1400060e5  mov     rcx, rax; this
0x1400060e8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400060ed  jmp     short loc_140006111
0x1400060ef  mov     rcx, rax; this
0x1400060f2  test    r9, r9
0x1400060f5  jz      short loc_140006105
0x1400060f7  lea     r8, aHs_2; "[%hs]\n"
0x1400060fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006103  jmp     short loc_140006111
0x140006105  lea     r8, asc_1400ACFA0; "\n"
0x14000610c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006111  xor     eax, eax
0x140006113  mov     rcx, [rsp+278h+var_38]
0x14000611b  xor     rcx, rsp; StackCookie
0x14000611e  call    __security_check_cookie
0x140006123  mov     rbx, [rsp+278h+arg_18]
0x14000612b  add     rsp, 250h
0x140006132  pop     r15
0x140006134  pop     r14
0x140006136  pop     rdi
0x140006137  pop     rsi
0x140006138  pop     rbp
0x140006139  retn
```
