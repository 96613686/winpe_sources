# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180010254`
- end: `0x18001050a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000f530`
- `0x180011184`

## callees

- `0x18000ab30`
- `0x18000b468`
- `0x180010254`
- `0x180011484`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010407`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010407`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180010386`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180010386`

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
          v8 = (const char *)&byte_18002FC3F;
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
0x180010254  mov     [rsp+arg_18], rbx
0x180010259  push    rbp
0x18001025a  push    rsi
0x18001025b  push    rdi
0x18001025c  push    r14
0x18001025e  push    r15
0x180010260  sub     rsp, 250h
0x180010267  mov     rax, cs:__security_cookie
0x18001026e  xor     rax, rsp
0x180010271  mov     [rsp+278h+var_38], rax
0x180010279  xor     r15d, r15d
0x18001027c  mov     rbx, r8
0x18001027f  mov     rsi, rdx
0x180010282  mov     r14, rcx
0x180010285  test    rdx, rdx
0x180010288  jz      loc_1800104E1
0x18001028e  test    rcx, rcx
0x180010291  jz      loc_1800104E1
0x180010297  mov     rax, cs:g_pfnResultLoggingCallback
0x18001029e  mov     [rcx], r15w
0x1800102a2  test    rax, rax
0x1800102a5  jz      short loc_1800102C8
0x1800102a7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800102ae  jz      short loc_1800102C8
0x1800102b0  mov     r8, rdx
0x1800102b3  mov     rdx, rcx
0x1800102b6  mov     rcx, rbx
0x1800102b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102be  cmp     [r14], r15w
0x1800102c2  jnz     loc_1800104E1
0x1800102c8  mov     ecx, [rbx]
0x1800102ca  mov     bpl, 8
0x1800102cd  test    ecx, ecx
0x1800102cf  jz      short loc_18001031A
0x1800102d1  sub     ecx, 1
0x1800102d4  jz      short loc_180010302
0x1800102d6  sub     ecx, 1
0x1800102d9  jz      short loc_1800102F2
0x1800102db  cmp     ecx, 1
0x1800102de  jz      short loc_1800102E9
0x1800102e0  lea     rdi, byte_18002FC3F
0x1800102e7  jmp     short loc_180010321
0x1800102e9  lea     rdi, aFailfast; "FailFast"
0x1800102f0  jmp     short loc_180010321
0x1800102f2  lea     rax, aLoghr; "LogHr"
0x1800102f9  lea     rdi, aLognt; "LogNt"
0x180010300  jmp     short loc_180010310
0x180010302  lea     rax, aReturnhr; "ReturnHr"
0x180010309  lea     rdi, aReturnnt; "ReturnNt"
0x180010310  test    [rbx+4], bpl
0x180010314  cmovz   rdi, rax
0x180010318  jmp     short loc_180010321
0x18001031a  lea     rdi, aException; "Exception"
0x180010321  xor     edx, edx; Val
0x180010323  lea     rcx, [rsp+278h+Buffer]; void *
0x180010328  mov     r8d, 200h; Size
0x18001032e  call    memset_0
0x180010333  test    [rbx+4], bpl
0x180010337  jz      short loc_18001035C
0x180010339  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180010340  mov     ebp, [rbx+0Ch]
0x180010343  test    rax, rax
0x180010346  jz      short loc_18001038C
0x180010348  mov     r8d, 100h
0x18001034e  lea     rdx, [rsp+278h+Buffer]
0x180010353  mov     ecx, ebp
0x180010355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001035a  jmp     short loc_18001038C
0x18001035c  mov     ebp, [rbx+8]
0x18001035f  lea     rax, [rsp+278h+Buffer]
0x180010364  mov     [rsp+278h+Arguments], r15; Arguments
0x180010369  mov     r8d, ebp; dwMessageId
0x18001036c  mov     [rsp+278h+nSize], 100h; nSize
0x180010374  mov     r9d, 400h; dwLanguageId
0x18001037a  xor     edx, edx; lpSource
0x18001037c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180010381  mov     ecx, 1200h; dwFlags
0x180010386  call    cs:__imp_FormatMessageW
0x18001038c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180010390  lea     rsi, [r14+rsi*2]
0x180010394  mov     rax, [rbx+88h]
0x18001039b  mov     rdx, rsi; unsigned __int16 *
0x18001039e  mov     rcx, [rbx+80h]
0x1800103a5  test    r9, r9
0x1800103a8  jz      short loc_1800103CC
0x1800103aa  mov     [rsp+278h+Arguments], rax
0x1800103af  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800103b6  mov     eax, [rbx+40h]
0x1800103b9  mov     qword ptr [rsp+278h+nSize], rcx
0x1800103be  mov     rcx, r14; this
0x1800103c1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800103c5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800103ca  jmp     short loc_1800103E3
0x1800103cc  mov     r9, rcx; unsigned __int16 *
0x1800103cf  mov     [rsp+278h+lpBuffer], rax
0x1800103d4  mov     rcx, r14; this
0x1800103d7  lea     r8, aHsP; "%hs!%p: "
0x1800103de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800103e3  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800103ea  mov     r14, rax
0x1800103ed  test    r9, r9
0x1800103f0  jz      short loc_180010407
0x1800103f2  lea     r8, aCallerP; "(caller: %p) "
0x1800103f9  mov     rdx, rsi; unsigned __int16 *
0x1800103fc  mov     rcx, rax; this
0x1800103ff  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180010404  mov     r14, rax
0x180010407  call    cs:__imp_GetCurrentThreadId
0x18001040d  lea     rcx, [rsp+278h+Buffer]
0x180010412  mov     r9, rdi; unsigned __int16 *
0x180010415  mov     [rsp+278h+var_240], rcx
0x18001041a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180010421  mov     dword ptr [rsp+278h+Arguments], ebp
0x180010425  mov     rdx, rsi; unsigned __int16 *
0x180010428  mov     [rsp+278h+nSize], eax
0x18001042c  mov     rcx, r14; this
0x18001042f  mov     eax, [rbx+44h]
0x180010432  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180010436  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001043b  cmp     [rbx+18h], r15
0x18001043f  jnz     short loc_180010451
0x180010441  cmp     [rbx+48h], r15
0x180010445  jnz     short loc_180010451
0x180010447  cmp     [rbx+30h], r15
0x18001044b  jz      loc_1800104E1
0x180010451  lea     r8, asc_18002FE38; "    "
0x180010458  mov     rdx, rsi; unsigned __int16 *
0x18001045b  mov     rcx, rax; this
0x18001045e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180010463  mov     r9, [rbx+18h]; unsigned __int16 *
0x180010467  test    r9, r9
0x18001046a  jz      short loc_18001047E
0x18001046c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180010473  mov     rdx, rsi; unsigned __int16 *
0x180010476  mov     rcx, rax; this
0x180010479  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001047e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180010482  test    r9, r9
0x180010485  jz      short loc_180010499
0x180010487  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001048e  mov     rdx, rsi; unsigned __int16 *
0x180010491  mov     rcx, rax; this
0x180010494  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180010499  mov     rcx, [rbx+28h]
0x18001049d  mov     rdx, rsi; unsigned __int16 *
0x1800104a0  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800104a4  test    rcx, rcx
0x1800104a7  jz      short loc_1800104BF
0x1800104a9  mov     [rsp+278h+lpBuffer], rcx
0x1800104ae  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800104b5  mov     rcx, rax; this
0x1800104b8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800104bd  jmp     short loc_1800104E1
0x1800104bf  mov     rcx, rax; this
0x1800104c2  test    r9, r9
0x1800104c5  jz      short loc_1800104D5
0x1800104c7  lea     r8, aHs; "[%hs]\n"
0x1800104ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800104d3  jmp     short loc_1800104E1
0x1800104d5  lea     r8, asc_18002FEB0; "\n"
0x1800104dc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800104e1  xor     eax, eax
0x1800104e3  mov     rcx, [rsp+278h+var_38]
0x1800104eb  xor     rcx, rsp; StackCookie
0x1800104ee  call    __security_check_cookie
0x1800104f3  mov     rbx, [rsp+278h+arg_18]
0x1800104fb  add     rsp, 250h
0x180010502  pop     r15
0x180010504  pop     r14
0x180010506  pop     rdi
0x180010507  pop     rsi
0x180010508  pop     rbp
0x180010509  retn
```
