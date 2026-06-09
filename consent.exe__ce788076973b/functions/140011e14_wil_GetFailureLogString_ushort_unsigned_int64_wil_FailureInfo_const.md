# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140011e14`
- end: `0x1400120ca`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140011258`
- `0x140012400`
- `0x140012850`
- `0x1400137f0`

## callees

- `0x14000f3fc`
- `0x140010ad3`
- `0x140011e14`
- `0x14001e050`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140011fc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140011fc7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140011f46`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140011f46`

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
          v7 = (const char *)&qword_140021870;
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
0x140011e14  mov     [rsp+arg_18], rbx
0x140011e19  push    rbp
0x140011e1a  push    rsi
0x140011e1b  push    rdi
0x140011e1c  push    r14
0x140011e1e  push    r15
0x140011e20  sub     rsp, 250h
0x140011e27  mov     rax, cs:__security_cookie
0x140011e2e  xor     rax, rsp
0x140011e31  mov     [rsp+278h+var_38], rax
0x140011e39  mov     rbx, r8
0x140011e3c  mov     rsi, rdx
0x140011e3f  mov     r14, rcx
0x140011e42  xor     r15d, r15d
0x140011e45  test    rdx, rdx
0x140011e48  jz      loc_1400120A1
0x140011e4e  test    rcx, rcx
0x140011e51  jz      loc_1400120A1
0x140011e57  mov     [rcx], r15w
0x140011e5b  mov     rax, cs:g_pfnResultLoggingCallback
0x140011e62  test    rax, rax
0x140011e65  jz      short loc_140011E88
0x140011e67  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140011e6e  jz      short loc_140011E88
0x140011e70  mov     r8, rdx
0x140011e73  mov     rdx, rcx
0x140011e76  mov     rcx, rbx
0x140011e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011e7e  cmp     [r14], r15w
0x140011e82  jnz     loc_1400120A1
0x140011e88  mov     ecx, [rbx]
0x140011e8a  mov     bpl, 8
0x140011e8d  test    ecx, ecx
0x140011e8f  jz      short loc_140011EDA
0x140011e91  sub     ecx, 1
0x140011e94  jz      short loc_140011EC2
0x140011e96  sub     ecx, 1
0x140011e99  jz      short loc_140011EB2
0x140011e9b  cmp     ecx, 1
0x140011e9e  jz      short loc_140011EA9
0x140011ea0  lea     rdi, qword_140021870
0x140011ea7  jmp     short loc_140011EE1
0x140011ea9  lea     rdi, aFailfast; "FailFast"
0x140011eb0  jmp     short loc_140011EE1
0x140011eb2  lea     rax, aLoghr; "LogHr"
0x140011eb9  lea     rdi, aLognt; "LogNt"
0x140011ec0  jmp     short loc_140011ED0
0x140011ec2  lea     rax, aReturnhr; "ReturnHr"
0x140011ec9  lea     rdi, aReturnnt; "ReturnNt"
0x140011ed0  test    [rbx+4], bpl
0x140011ed4  cmovz   rdi, rax
0x140011ed8  jmp     short loc_140011EE1
0x140011eda  lea     rdi, aException; "Exception"
0x140011ee1  xor     edx, edx; Val
0x140011ee3  mov     r8d, 200h; Size
0x140011ee9  lea     rcx, [rsp+278h+Buffer]; void *
0x140011eee  call    memset_0
0x140011ef3  test    [rbx+4], bpl
0x140011ef7  jz      short loc_140011F1C
0x140011ef9  mov     ebp, [rbx+0Ch]
0x140011efc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140011f03  test    rax, rax
0x140011f06  jz      short loc_140011F4C
0x140011f08  mov     r8d, 100h
0x140011f0e  lea     rdx, [rsp+278h+Buffer]
0x140011f13  mov     ecx, ebp
0x140011f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011f1a  jmp     short loc_140011F4C
0x140011f1c  mov     ebp, [rbx+8]
0x140011f1f  mov     [rsp+278h+Arguments], r15; Arguments
0x140011f24  mov     [rsp+278h+nSize], 100h; nSize
0x140011f2c  lea     rax, [rsp+278h+Buffer]
0x140011f31  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140011f36  mov     r9d, 400h; dwLanguageId
0x140011f3c  mov     r8d, ebp; dwMessageId
0x140011f3f  xor     edx, edx; lpSource
0x140011f41  mov     ecx, 1200h; dwFlags
0x140011f46  call    cs:__imp_FormatMessageW
0x140011f4c  lea     rsi, [r14+rsi*2]
0x140011f50  mov     r9, [rbx+38h]; unsigned __int16 *
0x140011f54  mov     rax, [rbx+88h]
0x140011f5b  mov     rcx, [rbx+80h]
0x140011f62  mov     rdx, rsi; unsigned __int16 *
0x140011f65  test    r9, r9
0x140011f68  jz      short loc_140011F8C
0x140011f6a  mov     [rsp+278h+Arguments], rax
0x140011f6f  mov     qword ptr [rsp+278h+nSize], rcx
0x140011f74  mov     eax, [rbx+40h]
0x140011f77  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140011f7b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140011f82  mov     rcx, r14; this
0x140011f85  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140011f8a  jmp     short loc_140011FA3
0x140011f8c  mov     [rsp+278h+lpBuffer], rax
0x140011f91  mov     r9, rcx; unsigned __int16 *
0x140011f94  lea     r8, aHsP; "%hs!%p: "
0x140011f9b  mov     rcx, r14; this
0x140011f9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140011fa3  mov     r14, rax
0x140011fa6  mov     r9, [rbx+90h]; unsigned __int16 *
0x140011fad  test    r9, r9
0x140011fb0  jz      short loc_140011FC7
0x140011fb2  lea     r8, aCallerP; "(caller: %p) "
0x140011fb9  mov     rdx, rsi; unsigned __int16 *
0x140011fbc  mov     rcx, rax; this
0x140011fbf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140011fc4  mov     r14, rax
0x140011fc7  call    cs:__imp_GetCurrentThreadId
0x140011fcd  lea     rcx, [rsp+278h+Buffer]
0x140011fd2  mov     [rsp+278h+var_240], rcx
0x140011fd7  mov     dword ptr [rsp+278h+Arguments], ebp
0x140011fdb  mov     [rsp+278h+nSize], eax
0x140011fdf  mov     eax, [rbx+44h]
0x140011fe2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140011fe6  mov     r9, rdi; unsigned __int16 *
0x140011fe9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140011ff0  mov     rdx, rsi; unsigned __int16 *
0x140011ff3  mov     rcx, r14; this
0x140011ff6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140011ffb  cmp     [rbx+18h], r15
0x140011fff  jnz     short loc_140012011
0x140012001  cmp     [rbx+48h], r15
0x140012005  jnz     short loc_140012011
0x140012007  cmp     [rbx+30h], r15
0x14001200b  jz      loc_1400120A1
0x140012011  lea     r8, asc_140021A18; "    "
0x140012018  mov     rdx, rsi; unsigned __int16 *
0x14001201b  mov     rcx, rax; this
0x14001201e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140012023  mov     r9, [rbx+18h]; unsigned __int16 *
0x140012027  test    r9, r9
0x14001202a  jz      short loc_14001203E
0x14001202c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140012033  mov     rdx, rsi; unsigned __int16 *
0x140012036  mov     rcx, rax; this
0x140012039  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14001203e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140012042  test    r9, r9
0x140012045  jz      short loc_140012059
0x140012047  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14001204e  mov     rdx, rsi; unsigned __int16 *
0x140012051  mov     rcx, rax; this
0x140012054  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140012059  mov     rcx, [rbx+28h]
0x14001205d  mov     r9, [rbx+30h]; unsigned __int16 *
0x140012061  mov     rdx, rsi; unsigned __int16 *
0x140012064  test    rcx, rcx
0x140012067  jz      short loc_14001207F
0x140012069  mov     [rsp+278h+lpBuffer], rcx
0x14001206e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140012075  mov     rcx, rax; this
0x140012078  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14001207d  jmp     short loc_1400120A1
0x14001207f  mov     rcx, rax; this
0x140012082  test    r9, r9
0x140012085  jz      short loc_140012095
0x140012087  lea     r8, aHs; "[%hs]\n"
0x14001208e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140012093  jmp     short loc_1400120A1
0x140012095  lea     r8, asc_140021A90; "\n"
0x14001209c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400120a1  xor     eax, eax
0x1400120a3  mov     rcx, [rsp+278h+var_38]
0x1400120ab  xor     rcx, rsp; StackCookie
0x1400120ae  call    __security_check_cookie
0x1400120b3  mov     rbx, [rsp+278h+arg_18]
0x1400120bb  add     rsp, 250h
0x1400120c2  pop     r15
0x1400120c4  pop     r14
0x1400120c6  pop     rdi
0x1400120c7  pop     rsi
0x1400120c8  pop     rbp
0x1400120c9  retn
```
