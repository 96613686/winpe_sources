# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140003654`
- end: `0x14000390a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140002908`
- `0x14000422c`

## callees

- `0x140001fc3`
- `0x140003654`
- `0x14000452c`
- `0x1400059b0`
- `0x140006010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x140003786`
- `KERNEL32!FormatMessageW` at `0x140003786`
- `KERNEL32!GetCurrentThreadId` at `0x140003807`
- `KERNEL32!GetCurrentThreadId` at `0x140003807`

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
          v8 = (const char *)&word_140007622;
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
0x140003654  mov     [rsp+arg_18], rbx
0x140003659  push    rbp
0x14000365a  push    rsi
0x14000365b  push    rdi
0x14000365c  push    r14
0x14000365e  push    r15
0x140003660  sub     rsp, 250h
0x140003667  mov     rax, cs:__security_cookie
0x14000366e  xor     rax, rsp
0x140003671  mov     [rsp+278h+var_38], rax
0x140003679  xor     r15d, r15d
0x14000367c  mov     rbx, r8
0x14000367f  mov     rsi, rdx
0x140003682  mov     r14, rcx
0x140003685  test    rdx, rdx
0x140003688  jz      loc_1400038E1
0x14000368e  test    rcx, rcx
0x140003691  jz      loc_1400038E1
0x140003697  mov     rax, cs:g_pfnResultLoggingCallback
0x14000369e  mov     [rcx], r15w
0x1400036a2  test    rax, rax
0x1400036a5  jz      short loc_1400036C8
0x1400036a7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400036ae  jz      short loc_1400036C8
0x1400036b0  mov     r8, rdx
0x1400036b3  mov     rdx, rcx
0x1400036b6  mov     rcx, rbx
0x1400036b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400036be  cmp     [r14], r15w
0x1400036c2  jnz     loc_1400038E1
0x1400036c8  mov     ecx, [rbx]
0x1400036ca  mov     bpl, 8
0x1400036cd  test    ecx, ecx
0x1400036cf  jz      short loc_14000371A
0x1400036d1  sub     ecx, 1
0x1400036d4  jz      short loc_140003702
0x1400036d6  sub     ecx, 1
0x1400036d9  jz      short loc_1400036F2
0x1400036db  cmp     ecx, 1
0x1400036de  jz      short loc_1400036E9
0x1400036e0  lea     rdi, word_140007622
0x1400036e7  jmp     short loc_140003721
0x1400036e9  lea     rdi, aFailfast; "FailFast"
0x1400036f0  jmp     short loc_140003721
0x1400036f2  lea     rax, aLoghr; "LogHr"
0x1400036f9  lea     rdi, aLognt; "LogNt"
0x140003700  jmp     short loc_140003710
0x140003702  lea     rax, aReturnhr; "ReturnHr"
0x140003709  lea     rdi, aReturnnt; "ReturnNt"
0x140003710  test    [rbx+4], bpl
0x140003714  cmovz   rdi, rax
0x140003718  jmp     short loc_140003721
0x14000371a  lea     rdi, aException; "Exception"
0x140003721  xor     edx, edx; Val
0x140003723  lea     rcx, [rsp+278h+Buffer]; void *
0x140003728  mov     r8d, 200h; Size
0x14000372e  call    memset_0
0x140003733  test    [rbx+4], bpl
0x140003737  jz      short loc_14000375C
0x140003739  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140003740  mov     ebp, [rbx+0Ch]
0x140003743  test    rax, rax
0x140003746  jz      short loc_14000378C
0x140003748  mov     r8d, 100h
0x14000374e  lea     rdx, [rsp+278h+Buffer]
0x140003753  mov     ecx, ebp
0x140003755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000375a  jmp     short loc_14000378C
0x14000375c  mov     ebp, [rbx+8]
0x14000375f  lea     rax, [rsp+278h+Buffer]
0x140003764  mov     [rsp+278h+Arguments], r15; Arguments
0x140003769  mov     r8d, ebp; dwMessageId
0x14000376c  mov     [rsp+278h+nSize], 100h; nSize
0x140003774  mov     r9d, 400h; dwLanguageId
0x14000377a  xor     edx, edx; lpSource
0x14000377c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140003781  mov     ecx, 1200h; dwFlags
0x140003786  call    cs:__imp_FormatMessageW
0x14000378c  mov     r9, [rbx+38h]; unsigned __int16 *
0x140003790  lea     rsi, [r14+rsi*2]
0x140003794  mov     rax, [rbx+88h]
0x14000379b  mov     rdx, rsi; unsigned __int16 *
0x14000379e  mov     rcx, [rbx+80h]
0x1400037a5  test    r9, r9
0x1400037a8  jz      short loc_1400037CC
0x1400037aa  mov     [rsp+278h+Arguments], rax
0x1400037af  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1400037b6  mov     eax, [rbx+40h]
0x1400037b9  mov     qword ptr [rsp+278h+nSize], rcx
0x1400037be  mov     rcx, r14; this
0x1400037c1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400037c5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400037ca  jmp     short loc_1400037E3
0x1400037cc  mov     r9, rcx; unsigned __int16 *
0x1400037cf  mov     [rsp+278h+lpBuffer], rax
0x1400037d4  mov     rcx, r14; this
0x1400037d7  lea     r8, aHsP; "%hs!%p: "
0x1400037de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400037e3  mov     r9, [rbx+90h]; unsigned __int16 *
0x1400037ea  mov     r14, rax
0x1400037ed  test    r9, r9
0x1400037f0  jz      short loc_140003807
0x1400037f2  lea     r8, aCallerP; "(caller: %p) "
0x1400037f9  mov     rdx, rsi; unsigned __int16 *
0x1400037fc  mov     rcx, rax; this
0x1400037ff  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003804  mov     r14, rax
0x140003807  call    cs:__imp_GetCurrentThreadId
0x14000380d  lea     rcx, [rsp+278h+Buffer]
0x140003812  mov     r9, rdi; unsigned __int16 *
0x140003815  mov     [rsp+278h+var_240], rcx
0x14000381a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140003821  mov     dword ptr [rsp+278h+Arguments], ebp
0x140003825  mov     rdx, rsi; unsigned __int16 *
0x140003828  mov     [rsp+278h+nSize], eax
0x14000382c  mov     rcx, r14; this
0x14000382f  mov     eax, [rbx+44h]
0x140003832  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140003836  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000383b  cmp     [rbx+18h], r15
0x14000383f  jnz     short loc_140003851
0x140003841  cmp     [rbx+48h], r15
0x140003845  jnz     short loc_140003851
0x140003847  cmp     [rbx+30h], r15
0x14000384b  jz      loc_1400038E1
0x140003851  lea     r8, asc_1400077B8; "    "
0x140003858  mov     rdx, rsi; unsigned __int16 *
0x14000385b  mov     rcx, rax; this
0x14000385e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003863  mov     r9, [rbx+18h]; unsigned __int16 *
0x140003867  test    r9, r9
0x14000386a  jz      short loc_14000387E
0x14000386c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140003873  mov     rdx, rsi; unsigned __int16 *
0x140003876  mov     rcx, rax; this
0x140003879  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000387e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140003882  test    r9, r9
0x140003885  jz      short loc_140003899
0x140003887  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000388e  mov     rdx, rsi; unsigned __int16 *
0x140003891  mov     rcx, rax; this
0x140003894  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003899  mov     rcx, [rbx+28h]
0x14000389d  mov     rdx, rsi; unsigned __int16 *
0x1400038a0  mov     r9, [rbx+30h]; unsigned __int16 *
0x1400038a4  test    rcx, rcx
0x1400038a7  jz      short loc_1400038BF
0x1400038a9  mov     [rsp+278h+lpBuffer], rcx
0x1400038ae  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1400038b5  mov     rcx, rax; this
0x1400038b8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400038bd  jmp     short loc_1400038E1
0x1400038bf  mov     rcx, rax; this
0x1400038c2  test    r9, r9
0x1400038c5  jz      short loc_1400038D5
0x1400038c7  lea     r8, aHs; "[%hs]\n"
0x1400038ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400038d3  jmp     short loc_1400038E1
0x1400038d5  lea     r8, asc_1400076C8; "\n"
0x1400038dc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400038e1  xor     eax, eax
0x1400038e3  mov     rcx, [rsp+278h+var_38]
0x1400038eb  xor     rcx, rsp; StackCookie
0x1400038ee  call    __security_check_cookie
0x1400038f3  mov     rbx, [rsp+278h+arg_18]
0x1400038fb  add     rsp, 250h
0x140003902  pop     r15
0x140003904  pop     r14
0x140003906  pop     rdi
0x140003907  pop     rsi
0x140003908  pop     rbp
0x140003909  retn
```
