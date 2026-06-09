# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x14000866c`
- end: `0x14000892f`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x140005e30`
- `0x1400060c4`
- `0x14000912c`
- `0x14000d290`
- `0x140013df4`
- `0x14006609f`
- `0x1400661d3`

## callees

- `0x140003450`
- `0x140003eb4`
- `0x14000866c`
- `0x140009440`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008825`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008825`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000879e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000879e`

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
      g_pfnResultLoggingCallback(a3, this, a2, a4);
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
          v7 = (const char *)&qword_14006D230;
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
0x14000866c  mov     [rsp+arg_18], rbx
0x140008671  push    rbp
0x140008672  push    rsi
0x140008673  push    rdi
0x140008674  push    r14
0x140008676  push    r15
0x140008678  sub     rsp, 250h
0x14000867f  mov     rax, cs:__security_cookie
0x140008686  xor     rax, rsp
0x140008689  mov     [rsp+278h+var_38], rax
0x140008691  mov     rbx, r8
0x140008694  mov     rsi, rdx
0x140008697  mov     r14, rcx
0x14000869a  xor     r15d, r15d
0x14000869d  test    rdx, rdx
0x1400086a0  jz      loc_140008905
0x1400086a6  test    rcx, rcx
0x1400086a9  jz      loc_140008905
0x1400086af  mov     [rcx], r15w
0x1400086b3  mov     rax, cs:g_pfnResultLoggingCallback
0x1400086ba  test    rax, rax
0x1400086bd  jz      short loc_1400086E0
0x1400086bf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400086c6  jz      short loc_1400086E0
0x1400086c8  mov     r8, rdx
0x1400086cb  mov     rdx, rcx
0x1400086ce  mov     rcx, rbx
0x1400086d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400086d6  cmp     [r14], r15w
0x1400086da  jnz     loc_140008905
0x1400086e0  mov     ecx, [rbx]
0x1400086e2  mov     bpl, 8
0x1400086e5  test    ecx, ecx
0x1400086e7  jz      short loc_140008732
0x1400086e9  sub     ecx, 1
0x1400086ec  jz      short loc_14000871A
0x1400086ee  sub     ecx, 1
0x1400086f1  jz      short loc_14000870A
0x1400086f3  cmp     ecx, 1
0x1400086f6  jz      short loc_140008701
0x1400086f8  lea     rdi, qword_14006D230
0x1400086ff  jmp     short loc_140008739
0x140008701  lea     rdi, aFailfast; "FailFast"
0x140008708  jmp     short loc_140008739
0x14000870a  lea     rax, aLoghr; "LogHr"
0x140008711  lea     rdi, aLognt; "LogNt"
0x140008718  jmp     short loc_140008728
0x14000871a  lea     rax, aReturnhr; "ReturnHr"
0x140008721  lea     rdi, aReturnnt; "ReturnNt"
0x140008728  test    [rbx+4], bpl
0x14000872c  cmovz   rdi, rax
0x140008730  jmp     short loc_140008739
0x140008732  lea     rdi, aException; "Exception"
0x140008739  xor     edx, edx; Val
0x14000873b  mov     r8d, 200h; Size
0x140008741  lea     rcx, [rsp+278h+Buffer]; void *
0x140008746  call    memset_0
0x14000874b  test    [rbx+4], bpl
0x14000874f  jz      short loc_140008774
0x140008751  mov     ebp, [rbx+0Ch]
0x140008754  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x14000875b  test    rax, rax
0x14000875e  jz      short loc_1400087AA
0x140008760  mov     r8d, 100h
0x140008766  lea     rdx, [rsp+278h+Buffer]
0x14000876b  mov     ecx, ebp
0x14000876d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008772  jmp     short loc_1400087AA
0x140008774  mov     ebp, [rbx+8]
0x140008777  mov     [rsp+278h+Arguments], r15; Arguments
0x14000877c  mov     [rsp+278h+nSize], 100h; nSize
0x140008784  lea     rax, [rsp+278h+Buffer]
0x140008789  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x14000878e  mov     r9d, 400h; dwLanguageId
0x140008794  mov     r8d, ebp; dwMessageId
0x140008797  xor     edx, edx; lpSource
0x140008799  mov     ecx, 1200h; dwFlags
0x14000879e  call    cs:__imp_FormatMessageW
0x1400087a5  nop     dword ptr [rax+rax+00h]
0x1400087aa  lea     rsi, [r14+rsi*2]
0x1400087ae  mov     r9, [rbx+38h]; unsigned __int16 *
0x1400087b2  mov     rax, [rbx+88h]
0x1400087b9  mov     rcx, [rbx+80h]
0x1400087c0  mov     rdx, rsi; unsigned __int16 *
0x1400087c3  test    r9, r9
0x1400087c6  jz      short loc_1400087EA
0x1400087c8  mov     [rsp+278h+Arguments], rax
0x1400087cd  mov     qword ptr [rsp+278h+nSize], rcx
0x1400087d2  mov     eax, [rbx+40h]
0x1400087d5  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400087d9  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1400087e0  mov     rcx, r14; this
0x1400087e3  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400087e8  jmp     short loc_140008801
0x1400087ea  mov     [rsp+278h+lpBuffer], rax
0x1400087ef  mov     r9, rcx; unsigned __int16 *
0x1400087f2  lea     r8, aHsP; "%hs!%p: "
0x1400087f9  mov     rcx, r14; this
0x1400087fc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140008801  mov     r14, rax
0x140008804  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000880b  test    r9, r9
0x14000880e  jz      short loc_140008825
0x140008810  lea     r8, aCallerP; "(caller: %p) "
0x140008817  mov     rdx, rsi; unsigned __int16 *
0x14000881a  mov     rcx, rax; this
0x14000881d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140008822  mov     r14, rax
0x140008825  call    cs:__imp_GetCurrentThreadId
0x14000882c  nop     dword ptr [rax+rax+00h]
0x140008831  lea     rcx, [rsp+278h+Buffer]
0x140008836  mov     [rsp+278h+var_240], rcx
0x14000883b  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000883f  mov     [rsp+278h+nSize], eax
0x140008843  mov     eax, [rbx+44h]
0x140008846  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000884a  mov     r9, rdi; unsigned __int16 *
0x14000884d  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140008854  mov     rdx, rsi; unsigned __int16 *
0x140008857  mov     rcx, r14; this
0x14000885a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000885f  cmp     [rbx+18h], r15
0x140008863  jnz     short loc_140008875
0x140008865  cmp     [rbx+48h], r15
0x140008869  jnz     short loc_140008875
0x14000886b  cmp     [rbx+30h], r15
0x14000886f  jz      loc_140008905
0x140008875  lea     r8, asc_14006D480; "    "
0x14000887c  mov     rdx, rsi; unsigned __int16 *
0x14000887f  mov     rcx, rax; this
0x140008882  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140008887  mov     r9, [rbx+18h]; unsigned __int16 *
0x14000888b  test    r9, r9
0x14000888e  jz      short loc_1400088A2
0x140008890  lea     r8, aMsgWs; "Msg:[%ws] "
0x140008897  mov     rdx, rsi; unsigned __int16 *
0x14000889a  mov     rcx, rax; this
0x14000889d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400088a2  mov     r9, [rbx+48h]; unsigned __int16 *
0x1400088a6  test    r9, r9
0x1400088a9  jz      short loc_1400088BD
0x1400088ab  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1400088b2  mov     rdx, rsi; unsigned __int16 *
0x1400088b5  mov     rcx, rax; this
0x1400088b8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400088bd  mov     rcx, [rbx+28h]
0x1400088c1  mov     r9, [rbx+30h]; unsigned __int16 *
0x1400088c5  mov     rdx, rsi; unsigned __int16 *
0x1400088c8  test    rcx, rcx
0x1400088cb  jz      short loc_1400088E3
0x1400088cd  mov     [rsp+278h+lpBuffer], rcx
0x1400088d2  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1400088d9  mov     rcx, rax; this
0x1400088dc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400088e1  jmp     short loc_140008905
0x1400088e3  mov     rcx, rax; this
0x1400088e6  test    r9, r9
0x1400088e9  jz      short loc_1400088F9
0x1400088eb  lea     r8, aHs; "[%hs]\n"
0x1400088f2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400088f7  jmp     short loc_140008905
0x1400088f9  lea     r8, asc_14006D4F8; "\n"
0x140008900  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140008905  xor     eax, eax
0x140008907  mov     rcx, [rsp+278h+var_38]
0x14000890f  xor     rcx, rsp; StackCookie
0x140008912  call    __security_check_cookie
0x140008917  mov     rbx, [rsp+278h+arg_18]
0x14000891f  add     rsp, 250h
0x140008926  pop     r15
0x140008928  pop     r14
0x14000892a  pop     rdi
0x14000892b  pop     rsi
0x14000892c  pop     rbp
0x14000892d  retn
```
