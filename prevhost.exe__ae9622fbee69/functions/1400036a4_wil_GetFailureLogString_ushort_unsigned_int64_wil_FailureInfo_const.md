# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1400036a4`
- end: `0x14000395a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x14000215c`
- `0x1400023cc`
- `0x1400040dc`

## callees

- `0x140001470`
- `0x140001e52`
- `0x1400036a4`
- `0x1400043dc`
- `0x140006010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140003857`
- `KERNEL32!GetCurrentThreadId` at `0x140003857`
- `KERNEL32!FormatMessageW` at `0x1400037d6`
- `KERNEL32!FormatMessageW` at `0x1400037d6`

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
          v8 = (const char *)&qword_140007780;
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
0x1400036a4  mov     [rsp+arg_18], rbx
0x1400036a9  push    rbp
0x1400036aa  push    rsi
0x1400036ab  push    rdi
0x1400036ac  push    r14
0x1400036ae  push    r15
0x1400036b0  sub     rsp, 250h
0x1400036b7  mov     rax, cs:__security_cookie
0x1400036be  xor     rax, rsp
0x1400036c1  mov     [rsp+278h+var_38], rax
0x1400036c9  xor     r15d, r15d
0x1400036cc  mov     rbx, r8
0x1400036cf  mov     rsi, rdx
0x1400036d2  mov     r14, rcx
0x1400036d5  test    rdx, rdx
0x1400036d8  jz      loc_140003931
0x1400036de  test    rcx, rcx
0x1400036e1  jz      loc_140003931
0x1400036e7  mov     rax, cs:g_pfnResultLoggingCallback
0x1400036ee  mov     [rcx], r15w
0x1400036f2  test    rax, rax
0x1400036f5  jz      short loc_140003718
0x1400036f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400036fe  jz      short loc_140003718
0x140003700  mov     r8, rdx
0x140003703  mov     rdx, rcx
0x140003706  mov     rcx, rbx
0x140003709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000370e  cmp     [r14], r15w
0x140003712  jnz     loc_140003931
0x140003718  mov     ecx, [rbx]
0x14000371a  mov     bpl, 8
0x14000371d  test    ecx, ecx
0x14000371f  jz      short loc_14000376A
0x140003721  sub     ecx, 1
0x140003724  jz      short loc_140003752
0x140003726  sub     ecx, 1
0x140003729  jz      short loc_140003742
0x14000372b  cmp     ecx, 1
0x14000372e  jz      short loc_140003739
0x140003730  lea     rdi, qword_140007780
0x140003737  jmp     short loc_140003771
0x140003739  lea     rdi, aFailfast; "FailFast"
0x140003740  jmp     short loc_140003771
0x140003742  lea     rax, aLoghr; "LogHr"
0x140003749  lea     rdi, aLognt; "LogNt"
0x140003750  jmp     short loc_140003760
0x140003752  lea     rax, aReturnhr; "ReturnHr"
0x140003759  lea     rdi, aReturnnt; "ReturnNt"
0x140003760  test    [rbx+4], bpl
0x140003764  cmovz   rdi, rax
0x140003768  jmp     short loc_140003771
0x14000376a  lea     rdi, aException; "Exception"
0x140003771  xor     edx, edx; Val
0x140003773  lea     rcx, [rsp+278h+Buffer]; void *
0x140003778  mov     r8d, 200h; Size
0x14000377e  call    memset_0
0x140003783  test    [rbx+4], bpl
0x140003787  jz      short loc_1400037AC
0x140003789  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140003790  mov     ebp, [rbx+0Ch]
0x140003793  test    rax, rax
0x140003796  jz      short loc_1400037DC
0x140003798  mov     r8d, 100h
0x14000379e  lea     rdx, [rsp+278h+Buffer]
0x1400037a3  mov     ecx, ebp
0x1400037a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037aa  jmp     short loc_1400037DC
0x1400037ac  mov     ebp, [rbx+8]
0x1400037af  lea     rax, [rsp+278h+Buffer]
0x1400037b4  mov     [rsp+278h+Arguments], r15; Arguments
0x1400037b9  mov     r8d, ebp; dwMessageId
0x1400037bc  mov     [rsp+278h+nSize], 100h; nSize
0x1400037c4  mov     r9d, 400h; dwLanguageId
0x1400037ca  xor     edx, edx; lpSource
0x1400037cc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1400037d1  mov     ecx, 1200h; dwFlags
0x1400037d6  call    cs:__imp_FormatMessageW
0x1400037dc  mov     r9, [rbx+38h]; unsigned __int16 *
0x1400037e0  lea     rsi, [r14+rsi*2]
0x1400037e4  mov     rax, [rbx+88h]
0x1400037eb  mov     rdx, rsi; unsigned __int16 *
0x1400037ee  mov     rcx, [rbx+80h]
0x1400037f5  test    r9, r9
0x1400037f8  jz      short loc_14000381C
0x1400037fa  mov     [rsp+278h+Arguments], rax
0x1400037ff  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140003806  mov     eax, [rbx+40h]
0x140003809  mov     qword ptr [rsp+278h+nSize], rcx
0x14000380e  mov     rcx, r14; this
0x140003811  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140003815  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000381a  jmp     short loc_140003833
0x14000381c  mov     r9, rcx; unsigned __int16 *
0x14000381f  mov     [rsp+278h+lpBuffer], rax
0x140003824  mov     rcx, r14; this
0x140003827  lea     r8, aHsP; "%hs!%p: "
0x14000382e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003833  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000383a  mov     r14, rax
0x14000383d  test    r9, r9
0x140003840  jz      short loc_140003857
0x140003842  lea     r8, aCallerP; "(caller: %p) "
0x140003849  mov     rdx, rsi; unsigned __int16 *
0x14000384c  mov     rcx, rax; this
0x14000384f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003854  mov     r14, rax
0x140003857  call    cs:__imp_GetCurrentThreadId
0x14000385d  lea     rcx, [rsp+278h+Buffer]
0x140003862  mov     r9, rdi; unsigned __int16 *
0x140003865  mov     [rsp+278h+var_240], rcx
0x14000386a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140003871  mov     dword ptr [rsp+278h+Arguments], ebp
0x140003875  mov     rdx, rsi; unsigned __int16 *
0x140003878  mov     [rsp+278h+nSize], eax
0x14000387c  mov     rcx, r14; this
0x14000387f  mov     eax, [rbx+44h]
0x140003882  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140003886  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000388b  cmp     [rbx+18h], r15
0x14000388f  jnz     short loc_1400038A1
0x140003891  cmp     [rbx+48h], r15
0x140003895  jnz     short loc_1400038A1
0x140003897  cmp     [rbx+30h], r15
0x14000389b  jz      loc_140003931
0x1400038a1  lea     r8, asc_140007870; "    "
0x1400038a8  mov     rdx, rsi; unsigned __int16 *
0x1400038ab  mov     rcx, rax; this
0x1400038ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400038b3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1400038b7  test    r9, r9
0x1400038ba  jz      short loc_1400038CE
0x1400038bc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1400038c3  mov     rdx, rsi; unsigned __int16 *
0x1400038c6  mov     rcx, rax; this
0x1400038c9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400038ce  mov     r9, [rbx+48h]; unsigned __int16 *
0x1400038d2  test    r9, r9
0x1400038d5  jz      short loc_1400038E9
0x1400038d7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1400038de  mov     rdx, rsi; unsigned __int16 *
0x1400038e1  mov     rcx, rax; this
0x1400038e4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400038e9  mov     rcx, [rbx+28h]
0x1400038ed  mov     rdx, rsi; unsigned __int16 *
0x1400038f0  mov     r9, [rbx+30h]; unsigned __int16 *
0x1400038f4  test    rcx, rcx
0x1400038f7  jz      short loc_14000390F
0x1400038f9  mov     [rsp+278h+lpBuffer], rcx
0x1400038fe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140003905  mov     rcx, rax; this
0x140003908  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000390d  jmp     short loc_140003931
0x14000390f  mov     rcx, rax; this
0x140003912  test    r9, r9
0x140003915  jz      short loc_140003925
0x140003917  lea     r8, aHs; "[%hs]\n"
0x14000391e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003923  jmp     short loc_140003931
0x140003925  lea     r8, asc_1400078E8; "\n"
0x14000392c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003931  xor     eax, eax
0x140003933  mov     rcx, [rsp+278h+var_38]
0x14000393b  xor     rcx, rsp; StackCookie
0x14000393e  call    __security_check_cookie
0x140003943  mov     rbx, [rsp+278h+arg_18]
0x14000394b  add     rsp, 250h
0x140003952  pop     r15
0x140003954  pop     r14
0x140003956  pop     rdi
0x140003957  pop     rsi
0x140003958  pop     rbp
0x140003959  retn
```
