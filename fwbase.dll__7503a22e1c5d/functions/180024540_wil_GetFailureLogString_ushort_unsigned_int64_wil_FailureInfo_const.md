# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180024540`
- end: `0x1800247f3`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `691`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180021b20`
- `0x180021db0`
- `0x1800254a0`
- `0x1800298b0`

## callees

- `0x18001e1d0`
- `0x18001eb54`
- `0x180024540`
- `0x1800257b0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800246f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800246f6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180024675`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180024675`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  __int64 result; // rax
  const char *v8; // rdi
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

  result = 0;
  if ( a2 && this )
  {
    *(_WORD *)this = 0;
    if ( !g_pfnResultLoggingCallback
      || !wil::details::g_resultMessageCallbackSet
      || (g_pfnResultLoggingCallback(a3, this, a2), !*(_WORD *)this) )
    {
      if ( *(_DWORD *)a3 )
      {
        switch ( *(_DWORD *)a3 )
        {
          case 1:
            v8 = "ReturnNt";
            if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
              v8 = "ReturnHr";
            break;
          case 2:
            v8 = "LogNt";
            if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
              v8 = "LogHr";
            break;
          case 3:
            v8 = "FailFast";
            break;
          default:
            v8 = (const char *)&word_1800341DA;
            break;
        }
      }
      else
      {
        v8 = "Exception";
      }
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
                              (const unsigned __int16 *)v8,
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
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180024540  push    rbx
0x180024542  push    rbp
0x180024543  push    rsi
0x180024544  push    rdi
0x180024545  push    r14
0x180024547  sub     rsp, 250h
0x18002454e  mov     rax, cs:__security_cookie
0x180024555  xor     rax, rsp
0x180024558  mov     [rsp+278h+var_38], rax
0x180024560  mov     rbx, r8
0x180024563  mov     rsi, rdx
0x180024566  mov     r14, rcx
0x180024569  xor     eax, eax
0x18002456b  test    rdx, rdx
0x18002456e  jz      loc_1800247D5
0x180024574  test    rcx, rcx
0x180024577  jz      loc_1800247D5
0x18002457d  mov     [rcx], ax
0x180024580  mov     rax, cs:g_pfnResultLoggingCallback
0x180024587  test    rax, rax
0x18002458a  jz      short loc_1800245AE
0x18002458c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x180024593  jz      short loc_1800245AE
0x180024595  mov     r8, rdx
0x180024598  mov     rdx, rcx
0x18002459b  mov     rcx, rbx
0x18002459e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245a3  cmp     word ptr [r14], 0
0x1800245a8  jnz     loc_1800247D3
0x1800245ae  mov     ecx, [rbx]
0x1800245b0  test    ecx, ecx
0x1800245b2  jz      short loc_180024605
0x1800245b4  sub     ecx, 1
0x1800245b7  jz      short loc_1800245ED
0x1800245b9  sub     ecx, 1
0x1800245bc  jz      short loc_1800245D5
0x1800245be  cmp     ecx, 1
0x1800245c1  jz      short loc_1800245CC
0x1800245c3  lea     rdi, word_1800341DA
0x1800245ca  jmp     short loc_18002460C
0x1800245cc  lea     rdi, aFailfast; "FailFast"
0x1800245d3  jmp     short loc_18002460C
0x1800245d5  test    byte ptr [rbx+4], 8
0x1800245d9  lea     rax, aLoghr; "LogHr"
0x1800245e0  lea     rdi, aLognt; "LogNt"
0x1800245e7  cmovz   rdi, rax
0x1800245eb  jmp     short loc_18002460C
0x1800245ed  test    byte ptr [rbx+4], 8
0x1800245f1  lea     rax, aReturnhr; "ReturnHr"
0x1800245f8  lea     rdi, aReturnnt; "ReturnNt"
0x1800245ff  cmovz   rdi, rax
0x180024603  jmp     short loc_18002460C
0x180024605  lea     rdi, aException; "Exception"
0x18002460c  xor     edx, edx; Val
0x18002460e  mov     r8d, 200h; Size
0x180024614  lea     rcx, [rsp+278h+Buffer]; void *
0x180024619  call    memset_0
0x18002461e  test    byte ptr [rbx+4], 8
0x180024622  jz      short loc_180024647
0x180024624  mov     ebp, [rbx+0Ch]
0x180024627  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18002462e  test    rax, rax
0x180024631  jz      short loc_18002467B
0x180024633  mov     r8d, 100h
0x180024639  lea     rdx, [rsp+278h+Buffer]
0x18002463e  mov     ecx, ebp
0x180024640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024645  jmp     short loc_18002467B
0x180024647  mov     ebp, [rbx+8]
0x18002464a  mov     [rsp+278h+Arguments], 0; Arguments
0x180024653  mov     [rsp+278h+nSize], 100h; nSize
0x18002465b  lea     rax, [rsp+278h+Buffer]
0x180024660  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180024665  mov     r9d, 400h; dwLanguageId
0x18002466b  mov     r8d, ebp; dwMessageId
0x18002466e  xor     edx, edx; lpSource
0x180024670  mov     ecx, 1200h; dwFlags
0x180024675  call    cs:__imp_FormatMessageW
0x18002467b  lea     rsi, [r14+rsi*2]
0x18002467f  mov     r9, [rbx+38h]; unsigned __int16 *
0x180024683  mov     rax, [rbx+88h]
0x18002468a  mov     rcx, [rbx+80h]
0x180024691  mov     rdx, rsi; unsigned __int16 *
0x180024694  test    r9, r9
0x180024697  jz      short loc_1800246BB
0x180024699  mov     [rsp+278h+Arguments], rax
0x18002469e  mov     qword ptr [rsp+278h+nSize], rcx
0x1800246a3  mov     eax, [rbx+40h]
0x1800246a6  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800246aa  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800246b1  mov     rcx, r14; this
0x1800246b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800246b9  jmp     short loc_1800246D2
0x1800246bb  mov     [rsp+278h+lpBuffer], rax
0x1800246c0  mov     r9, rcx; unsigned __int16 *
0x1800246c3  lea     r8, aHsP; "%hs!%p: "
0x1800246ca  mov     rcx, r14; this
0x1800246cd  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800246d2  mov     r14, rax
0x1800246d5  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800246dc  test    r9, r9
0x1800246df  jz      short loc_1800246F6
0x1800246e1  lea     r8, aCallerP; "(caller: %p) "
0x1800246e8  mov     rdx, rsi; unsigned __int16 *
0x1800246eb  mov     rcx, rax; this
0x1800246ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800246f3  mov     r14, rax
0x1800246f6  call    cs:__imp_GetCurrentThreadId
0x1800246fc  lea     rcx, [rsp+278h+Buffer]
0x180024701  mov     [rsp+278h+var_240], rcx
0x180024706  mov     dword ptr [rsp+278h+Arguments], ebp
0x18002470a  mov     [rsp+278h+nSize], eax
0x18002470e  mov     eax, [rbx+44h]
0x180024711  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180024715  mov     r9, rdi; unsigned __int16 *
0x180024718  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18002471f  mov     rdx, rsi; unsigned __int16 *
0x180024722  mov     rcx, r14; this
0x180024725  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002472a  cmp     qword ptr [rbx+18h], 0
0x18002472f  jnz     short loc_180024743
0x180024731  cmp     qword ptr [rbx+48h], 0
0x180024736  jnz     short loc_180024743
0x180024738  cmp     qword ptr [rbx+30h], 0
0x18002473d  jz      loc_1800247D3
0x180024743  lea     r8, asc_1800342E0; "    "
0x18002474a  mov     rdx, rsi; unsigned __int16 *
0x18002474d  mov     rcx, rax; this
0x180024750  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024755  mov     r9, [rbx+18h]; unsigned __int16 *
0x180024759  test    r9, r9
0x18002475c  jz      short loc_180024770
0x18002475e  lea     r8, aMsgWs; "Msg:[%ws] "
0x180024765  mov     rdx, rsi; unsigned __int16 *
0x180024768  mov     rcx, rax; this
0x18002476b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024770  mov     r9, [rbx+48h]; unsigned __int16 *
0x180024774  test    r9, r9
0x180024777  jz      short loc_18002478B
0x180024779  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180024780  mov     rdx, rsi; unsigned __int16 *
0x180024783  mov     rcx, rax; this
0x180024786  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002478b  mov     rcx, [rbx+28h]
0x18002478f  mov     r9, [rbx+30h]; unsigned __int16 *
0x180024793  mov     rdx, rsi; unsigned __int16 *
0x180024796  test    rcx, rcx
0x180024799  jz      short loc_1800247B1
0x18002479b  mov     [rsp+278h+lpBuffer], rcx
0x1800247a0  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800247a7  mov     rcx, rax; this
0x1800247aa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800247af  jmp     short loc_1800247D3
0x1800247b1  mov     rcx, rax; this
0x1800247b4  test    r9, r9
0x1800247b7  jz      short loc_1800247C7
0x1800247b9  lea     r8, aHs; "[%hs]\n"
0x1800247c0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800247c5  jmp     short loc_1800247D3
0x1800247c7  lea     r8, asc_180034358; "\n"
0x1800247ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800247d3  xor     eax, eax
0x1800247d5  mov     rcx, [rsp+278h+var_38]
0x1800247dd  xor     rcx, rsp; StackCookie
0x1800247e0  call    __security_check_cookie
0x1800247e5  add     rsp, 250h
0x1800247ec  pop     r14
0x1800247ee  pop     rdi
0x1800247ef  pop     rsi
0x1800247f0  pop     rbp
0x1800247f1  pop     rbx
0x1800247f2  retn
```
