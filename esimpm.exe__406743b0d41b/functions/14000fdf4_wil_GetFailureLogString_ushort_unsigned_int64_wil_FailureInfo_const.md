# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x14000fdf4`
- end: `0x1400100aa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x14000d69c`
- `0x14000d91c`
- `0x14001083c`
- `0x140014060`
- `0x140016548`
- `0x14003c2d1`
- `0x14003c405`

## callees

- `0x140002f60`
- `0x140003b28`
- `0x14000fdf4`
- `0x140010b3c`
- `0x14003e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000ffa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000ffa7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000ff26`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000ff26`

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
          v7 = (const char *)&byte_14005E3A8;
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
0x14000fdf4  mov     [rsp+arg_18], rbx
0x14000fdf9  push    rbp
0x14000fdfa  push    rsi
0x14000fdfb  push    rdi
0x14000fdfc  push    r14
0x14000fdfe  push    r15
0x14000fe00  sub     rsp, 250h
0x14000fe07  mov     rax, cs:__security_cookie
0x14000fe0e  xor     rax, rsp
0x14000fe11  mov     [rsp+278h+var_38], rax
0x14000fe19  mov     rbx, r8
0x14000fe1c  mov     rsi, rdx
0x14000fe1f  mov     r14, rcx
0x14000fe22  xor     r15d, r15d
0x14000fe25  test    rdx, rdx
0x14000fe28  jz      loc_140010081
0x14000fe2e  test    rcx, rcx
0x14000fe31  jz      loc_140010081
0x14000fe37  mov     [rcx], r15w
0x14000fe3b  mov     rax, cs:g_pfnResultLoggingCallback
0x14000fe42  test    rax, rax
0x14000fe45  jz      short loc_14000FE68
0x14000fe47  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000fe4e  jz      short loc_14000FE68
0x14000fe50  mov     r8, rdx
0x14000fe53  mov     rdx, rcx
0x14000fe56  mov     rcx, rbx
0x14000fe59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fe5e  cmp     [r14], r15w
0x14000fe62  jnz     loc_140010081
0x14000fe68  mov     ecx, [rbx]
0x14000fe6a  mov     bpl, 8
0x14000fe6d  test    ecx, ecx
0x14000fe6f  jz      short loc_14000FEBA
0x14000fe71  sub     ecx, 1
0x14000fe74  jz      short loc_14000FEA2
0x14000fe76  sub     ecx, 1
0x14000fe79  jz      short loc_14000FE92
0x14000fe7b  cmp     ecx, 1
0x14000fe7e  jz      short loc_14000FE89
0x14000fe80  lea     rdi, byte_14005E3A8
0x14000fe87  jmp     short loc_14000FEC1
0x14000fe89  lea     rdi, aFailfast; "FailFast"
0x14000fe90  jmp     short loc_14000FEC1
0x14000fe92  lea     rax, aLoghr; "LogHr"
0x14000fe99  lea     rdi, aLognt; "LogNt"
0x14000fea0  jmp     short loc_14000FEB0
0x14000fea2  lea     rax, aReturnhr; "ReturnHr"
0x14000fea9  lea     rdi, aReturnnt; "ReturnNt"
0x14000feb0  test    [rbx+4], bpl
0x14000feb4  cmovz   rdi, rax
0x14000feb8  jmp     short loc_14000FEC1
0x14000feba  lea     rdi, aException; "Exception"
0x14000fec1  xor     edx, edx; Val
0x14000fec3  mov     r8d, 200h; Size
0x14000fec9  lea     rcx, [rsp+278h+Buffer]; void *
0x14000fece  call    memset_0
0x14000fed3  test    [rbx+4], bpl
0x14000fed7  jz      short loc_14000FEFC
0x14000fed9  mov     ebp, [rbx+0Ch]
0x14000fedc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x14000fee3  test    rax, rax
0x14000fee6  jz      short loc_14000FF2C
0x14000fee8  mov     r8d, 100h
0x14000feee  lea     rdx, [rsp+278h+Buffer]
0x14000fef3  mov     ecx, ebp
0x14000fef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fefa  jmp     short loc_14000FF2C
0x14000fefc  mov     ebp, [rbx+8]
0x14000feff  mov     [rsp+278h+Arguments], r15; Arguments
0x14000ff04  mov     [rsp+278h+nSize], 100h; nSize
0x14000ff0c  lea     rax, [rsp+278h+Buffer]
0x14000ff11  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x14000ff16  mov     r9d, 400h; dwLanguageId
0x14000ff1c  mov     r8d, ebp; dwMessageId
0x14000ff1f  xor     edx, edx; lpSource
0x14000ff21  mov     ecx, 1200h; dwFlags
0x14000ff26  call    cs:__imp_FormatMessageW
0x14000ff2c  lea     rsi, [r14+rsi*2]
0x14000ff30  mov     r9, [rbx+38h]; unsigned __int16 *
0x14000ff34  mov     rax, [rbx+88h]
0x14000ff3b  mov     rcx, [rbx+80h]
0x14000ff42  mov     rdx, rsi; unsigned __int16 *
0x14000ff45  test    r9, r9
0x14000ff48  jz      short loc_14000FF6C
0x14000ff4a  mov     [rsp+278h+Arguments], rax
0x14000ff4f  mov     qword ptr [rsp+278h+nSize], rcx
0x14000ff54  mov     eax, [rbx+40h]
0x14000ff57  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000ff5b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x14000ff62  mov     rcx, r14; this
0x14000ff65  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000ff6a  jmp     short loc_14000FF83
0x14000ff6c  mov     [rsp+278h+lpBuffer], rax
0x14000ff71  mov     r9, rcx; unsigned __int16 *
0x14000ff74  lea     r8, aHsP; "%hs!%p: "
0x14000ff7b  mov     rcx, r14; this
0x14000ff7e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000ff83  mov     r14, rax
0x14000ff86  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000ff8d  test    r9, r9
0x14000ff90  jz      short loc_14000FFA7
0x14000ff92  lea     r8, aCallerP; "(caller: %p) "
0x14000ff99  mov     rdx, rsi; unsigned __int16 *
0x14000ff9c  mov     rcx, rax; this
0x14000ff9f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000ffa4  mov     r14, rax
0x14000ffa7  call    cs:__imp_GetCurrentThreadId
0x14000ffad  lea     rcx, [rsp+278h+Buffer]
0x14000ffb2  mov     [rsp+278h+var_240], rcx
0x14000ffb7  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000ffbb  mov     [rsp+278h+nSize], eax
0x14000ffbf  mov     eax, [rbx+44h]
0x14000ffc2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000ffc6  mov     r9, rdi; unsigned __int16 *
0x14000ffc9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x14000ffd0  mov     rdx, rsi; unsigned __int16 *
0x14000ffd3  mov     rcx, r14; this
0x14000ffd6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000ffdb  cmp     [rbx+18h], r15
0x14000ffdf  jnz     short loc_14000FFF1
0x14000ffe1  cmp     [rbx+48h], r15
0x14000ffe5  jnz     short loc_14000FFF1
0x14000ffe7  cmp     [rbx+30h], r15
0x14000ffeb  jz      loc_140010081
0x14000fff1  lea     r8, asc_14005E498; "    "
0x14000fff8  mov     rdx, rsi; unsigned __int16 *
0x14000fffb  mov     rcx, rax; this
0x14000fffe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140010003  mov     r9, [rbx+18h]; unsigned __int16 *
0x140010007  test    r9, r9
0x14001000a  jz      short loc_14001001E
0x14001000c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140010013  mov     rdx, rsi; unsigned __int16 *
0x140010016  mov     rcx, rax; this
0x140010019  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14001001e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140010022  test    r9, r9
0x140010025  jz      short loc_140010039
0x140010027  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14001002e  mov     rdx, rsi; unsigned __int16 *
0x140010031  mov     rcx, rax; this
0x140010034  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140010039  mov     rcx, [rbx+28h]
0x14001003d  mov     r9, [rbx+30h]; unsigned __int16 *
0x140010041  mov     rdx, rsi; unsigned __int16 *
0x140010044  test    rcx, rcx
0x140010047  jz      short loc_14001005F
0x140010049  mov     [rsp+278h+lpBuffer], rcx
0x14001004e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140010055  mov     rcx, rax; this
0x140010058  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14001005d  jmp     short loc_140010081
0x14001005f  mov     rcx, rax; this
0x140010062  test    r9, r9
0x140010065  jz      short loc_140010075
0x140010067  lea     r8, aHs; "[%hs]\n"
0x14001006e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140010073  jmp     short loc_140010081
0x140010075  lea     r8, asc_14005E510; "\n"
0x14001007c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140010081  xor     eax, eax
0x140010083  mov     rcx, [rsp+278h+var_38]
0x14001008b  xor     rcx, rsp; StackCookie
0x14001008e  call    __security_check_cookie
0x140010093  mov     rbx, [rsp+278h+arg_18]
0x14001009b  add     rsp, 250h
0x1400100a2  pop     r15
0x1400100a4  pop     r14
0x1400100a6  pop     rdi
0x1400100a7  pop     rsi
0x1400100a8  pop     rbp
0x1400100a9  retn
```
