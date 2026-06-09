# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800098cc`
- end: `0x180009b82`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800087e4`
- `0x180008a54`
- `0x18000a0fc`

## callees

- `0x1800098cc`
- `0x18000a3fc`
- `0x18000c392`
- `0x18000c3c0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009a7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009a7f`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800099fe`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800099fe`

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
          v8 = (const char *)&dword_18001324C;
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
0x1800098cc  mov     [rsp+arg_18], rbx
0x1800098d1  push    rbp
0x1800098d2  push    rsi
0x1800098d3  push    rdi
0x1800098d4  push    r14
0x1800098d6  push    r15
0x1800098d8  sub     rsp, 250h
0x1800098df  mov     rax, cs:__security_cookie
0x1800098e6  xor     rax, rsp
0x1800098e9  mov     [rsp+278h+var_38], rax
0x1800098f1  xor     r15d, r15d
0x1800098f4  mov     rbx, r8
0x1800098f7  mov     rsi, rdx
0x1800098fa  mov     r14, rcx
0x1800098fd  test    rdx, rdx
0x180009900  jz      loc_180009B59
0x180009906  test    rcx, rcx
0x180009909  jz      loc_180009B59
0x18000990f  mov     rax, cs:g_pfnResultLoggingCallback
0x180009916  mov     [rcx], r15w
0x18000991a  test    rax, rax
0x18000991d  jz      short loc_180009940
0x18000991f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180009926  jz      short loc_180009940
0x180009928  mov     r8, rdx
0x18000992b  mov     rdx, rcx
0x18000992e  mov     rcx, rbx
0x180009931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009936  cmp     [r14], r15w
0x18000993a  jnz     loc_180009B59
0x180009940  mov     ecx, [rbx]
0x180009942  mov     bpl, 8
0x180009945  test    ecx, ecx
0x180009947  jz      short loc_180009992
0x180009949  sub     ecx, 1
0x18000994c  jz      short loc_18000997A
0x18000994e  sub     ecx, 1
0x180009951  jz      short loc_18000996A
0x180009953  cmp     ecx, 1
0x180009956  jz      short loc_180009961
0x180009958  lea     rdi, dword_18001324C
0x18000995f  jmp     short loc_180009999
0x180009961  lea     rdi, aFailfast; "FailFast"
0x180009968  jmp     short loc_180009999
0x18000996a  lea     rax, aLoghr; "LogHr"
0x180009971  lea     rdi, aLognt; "LogNt"
0x180009978  jmp     short loc_180009988
0x18000997a  lea     rax, aReturnhr; "ReturnHr"
0x180009981  lea     rdi, aReturnnt; "ReturnNt"
0x180009988  test    [rbx+4], bpl
0x18000998c  cmovz   rdi, rax
0x180009990  jmp     short loc_180009999
0x180009992  lea     rdi, aException; "Exception"
0x180009999  xor     edx, edx; Val
0x18000999b  lea     rcx, [rsp+278h+Buffer]; void *
0x1800099a0  mov     r8d, 200h; Size
0x1800099a6  call    memset_0
0x1800099ab  test    [rbx+4], bpl
0x1800099af  jz      short loc_1800099D4
0x1800099b1  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800099b8  mov     ebp, [rbx+0Ch]
0x1800099bb  test    rax, rax
0x1800099be  jz      short loc_180009A04
0x1800099c0  mov     r8d, 100h
0x1800099c6  lea     rdx, [rsp+278h+Buffer]
0x1800099cb  mov     ecx, ebp
0x1800099cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099d2  jmp     short loc_180009A04
0x1800099d4  mov     ebp, [rbx+8]
0x1800099d7  lea     rax, [rsp+278h+Buffer]
0x1800099dc  mov     [rsp+278h+Arguments], r15; Arguments
0x1800099e1  mov     r8d, ebp; dwMessageId
0x1800099e4  mov     [rsp+278h+nSize], 100h; nSize
0x1800099ec  mov     r9d, 400h; dwLanguageId
0x1800099f2  xor     edx, edx; lpSource
0x1800099f4  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800099f9  mov     ecx, 1200h; dwFlags
0x1800099fe  call    cs:__imp_FormatMessageW
0x180009a04  mov     r9, [rbx+38h]; unsigned __int16 *
0x180009a08  lea     rsi, [r14+rsi*2]
0x180009a0c  mov     rax, [rbx+88h]
0x180009a13  mov     rdx, rsi; unsigned __int16 *
0x180009a16  mov     rcx, [rbx+80h]
0x180009a1d  test    r9, r9
0x180009a20  jz      short loc_180009A44
0x180009a22  mov     [rsp+278h+Arguments], rax
0x180009a27  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180009a2e  mov     eax, [rbx+40h]
0x180009a31  mov     qword ptr [rsp+278h+nSize], rcx
0x180009a36  mov     rcx, r14; this
0x180009a39  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009a3d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009a42  jmp     short loc_180009A5B
0x180009a44  mov     r9, rcx; unsigned __int16 *
0x180009a47  mov     [rsp+278h+lpBuffer], rax
0x180009a4c  mov     rcx, r14; this
0x180009a4f  lea     r8, aHsP; "%hs!%p: "
0x180009a56  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009a5b  mov     r9, [rbx+90h]; unsigned __int16 *
0x180009a62  mov     r14, rax
0x180009a65  test    r9, r9
0x180009a68  jz      short loc_180009A7F
0x180009a6a  lea     r8, aCallerP; "(caller: %p) "
0x180009a71  mov     rdx, rsi; unsigned __int16 *
0x180009a74  mov     rcx, rax; this
0x180009a77  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009a7c  mov     r14, rax
0x180009a7f  call    cs:__imp_GetCurrentThreadId
0x180009a85  lea     rcx, [rsp+278h+Buffer]
0x180009a8a  mov     r9, rdi; unsigned __int16 *
0x180009a8d  mov     [rsp+278h+var_240], rcx
0x180009a92  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180009a99  mov     dword ptr [rsp+278h+Arguments], ebp
0x180009a9d  mov     rdx, rsi; unsigned __int16 *
0x180009aa0  mov     [rsp+278h+nSize], eax
0x180009aa4  mov     rcx, r14; this
0x180009aa7  mov     eax, [rbx+44h]
0x180009aaa  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009aae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009ab3  cmp     [rbx+18h], r15
0x180009ab7  jnz     short loc_180009AC9
0x180009ab9  cmp     [rbx+48h], r15
0x180009abd  jnz     short loc_180009AC9
0x180009abf  cmp     [rbx+30h], r15
0x180009ac3  jz      loc_180009B59
0x180009ac9  lea     r8, asc_180013338; "    "
0x180009ad0  mov     rdx, rsi; unsigned __int16 *
0x180009ad3  mov     rcx, rax; this
0x180009ad6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009adb  mov     r9, [rbx+18h]; unsigned __int16 *
0x180009adf  test    r9, r9
0x180009ae2  jz      short loc_180009AF6
0x180009ae4  lea     r8, aMsgWs; "Msg:[%ws] "
0x180009aeb  mov     rdx, rsi; unsigned __int16 *
0x180009aee  mov     rcx, rax; this
0x180009af1  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009af6  mov     r9, [rbx+48h]; unsigned __int16 *
0x180009afa  test    r9, r9
0x180009afd  jz      short loc_180009B11
0x180009aff  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180009b06  mov     rdx, rsi; unsigned __int16 *
0x180009b09  mov     rcx, rax; this
0x180009b0c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009b11  mov     rcx, [rbx+28h]
0x180009b15  mov     rdx, rsi; unsigned __int16 *
0x180009b18  mov     r9, [rbx+30h]; unsigned __int16 *
0x180009b1c  test    rcx, rcx
0x180009b1f  jz      short loc_180009B37
0x180009b21  mov     [rsp+278h+lpBuffer], rcx
0x180009b26  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180009b2d  mov     rcx, rax; this
0x180009b30  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009b35  jmp     short loc_180009B59
0x180009b37  mov     rcx, rax; this
0x180009b3a  test    r9, r9
0x180009b3d  jz      short loc_180009B4D
0x180009b3f  lea     r8, aHs; "[%hs]\n"
0x180009b46  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009b4b  jmp     short loc_180009B59
0x180009b4d  lea     r8, asc_1800133B0; "\n"
0x180009b54  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009b59  xor     eax, eax
0x180009b5b  mov     rcx, [rsp+278h+var_38]
0x180009b63  xor     rcx, rsp; StackCookie
0x180009b66  call    __security_check_cookie
0x180009b6b  mov     rbx, [rsp+278h+arg_18]
0x180009b73  add     rsp, 250h
0x180009b7a  pop     r15
0x180009b7c  pop     r14
0x180009b7e  pop     rdi
0x180009b7f  pop     rsi
0x180009b80  pop     rbp
0x180009b81  retn
```
