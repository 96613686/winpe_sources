# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140003784`
- end: `0x140003a3a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140002280`
- `0x140002568`
- `0x1400040e4`
- `0x1400058c0`

## callees

- `0x140001460`
- `0x140001e56`
- `0x140003784`
- `0x1400043e4`
- `0x140006010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400038b6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400038b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003937`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003937`

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
          v7 = (const char *)&qword_1400075A0;
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
0x140003784  mov     [rsp+arg_18], rbx
0x140003789  push    rbp
0x14000378a  push    rsi
0x14000378b  push    rdi
0x14000378c  push    r14
0x14000378e  push    r15
0x140003790  sub     rsp, 250h
0x140003797  mov     rax, cs:__security_cookie
0x14000379e  xor     rax, rsp
0x1400037a1  mov     [rsp+278h+var_38], rax
0x1400037a9  mov     rbx, r8
0x1400037ac  mov     rsi, rdx
0x1400037af  mov     r14, rcx
0x1400037b2  xor     r15d, r15d
0x1400037b5  test    rdx, rdx
0x1400037b8  jz      loc_140003A11
0x1400037be  test    rcx, rcx
0x1400037c1  jz      loc_140003A11
0x1400037c7  mov     [rcx], r15w
0x1400037cb  mov     rax, cs:g_pfnResultLoggingCallback
0x1400037d2  test    rax, rax
0x1400037d5  jz      short loc_1400037F8
0x1400037d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400037de  jz      short loc_1400037F8
0x1400037e0  mov     r8, rdx
0x1400037e3  mov     rdx, rcx
0x1400037e6  mov     rcx, rbx
0x1400037e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037ee  cmp     [r14], r15w
0x1400037f2  jnz     loc_140003A11
0x1400037f8  mov     ecx, [rbx]
0x1400037fa  mov     bpl, 8
0x1400037fd  test    ecx, ecx
0x1400037ff  jz      short loc_14000384A
0x140003801  sub     ecx, 1
0x140003804  jz      short loc_140003832
0x140003806  sub     ecx, 1
0x140003809  jz      short loc_140003822
0x14000380b  cmp     ecx, 1
0x14000380e  jz      short loc_140003819
0x140003810  lea     rdi, qword_1400075A0
0x140003817  jmp     short loc_140003851
0x140003819  lea     rdi, aFailfast; "FailFast"
0x140003820  jmp     short loc_140003851
0x140003822  lea     rax, aLoghr; "LogHr"
0x140003829  lea     rdi, aLognt; "LogNt"
0x140003830  jmp     short loc_140003840
0x140003832  lea     rax, aReturnhr; "ReturnHr"
0x140003839  lea     rdi, aReturnnt; "ReturnNt"
0x140003840  test    [rbx+4], bpl
0x140003844  cmovz   rdi, rax
0x140003848  jmp     short loc_140003851
0x14000384a  lea     rdi, aException; "Exception"
0x140003851  xor     edx, edx; Val
0x140003853  mov     r8d, 200h; Size
0x140003859  lea     rcx, [rsp+278h+Buffer]; void *
0x14000385e  call    memset_0
0x140003863  test    [rbx+4], bpl
0x140003867  jz      short loc_14000388C
0x140003869  mov     ebp, [rbx+0Ch]
0x14000386c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140003873  test    rax, rax
0x140003876  jz      short loc_1400038BC
0x140003878  mov     r8d, 100h
0x14000387e  lea     rdx, [rsp+278h+Buffer]
0x140003883  mov     ecx, ebp
0x140003885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000388a  jmp     short loc_1400038BC
0x14000388c  mov     ebp, [rbx+8]
0x14000388f  mov     [rsp+278h+Arguments], r15; Arguments
0x140003894  mov     [rsp+278h+nSize], 100h; nSize
0x14000389c  lea     rax, [rsp+278h+Buffer]
0x1400038a1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1400038a6  mov     r9d, 400h; dwLanguageId
0x1400038ac  mov     r8d, ebp; dwMessageId
0x1400038af  xor     edx, edx; lpSource
0x1400038b1  mov     ecx, 1200h; dwFlags
0x1400038b6  call    cs:__imp_FormatMessageW
0x1400038bc  lea     rsi, [r14+rsi*2]
0x1400038c0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1400038c4  mov     rax, [rbx+88h]
0x1400038cb  mov     rcx, [rbx+80h]
0x1400038d2  mov     rdx, rsi; unsigned __int16 *
0x1400038d5  test    r9, r9
0x1400038d8  jz      short loc_1400038FC
0x1400038da  mov     [rsp+278h+Arguments], rax
0x1400038df  mov     qword ptr [rsp+278h+nSize], rcx
0x1400038e4  mov     eax, [rbx+40h]
0x1400038e7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400038eb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1400038f2  mov     rcx, r14; this
0x1400038f5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400038fa  jmp     short loc_140003913
0x1400038fc  mov     [rsp+278h+lpBuffer], rax
0x140003901  mov     r9, rcx; unsigned __int16 *
0x140003904  lea     r8, aHsP; "%hs!%p: "
0x14000390b  mov     rcx, r14; this
0x14000390e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003913  mov     r14, rax
0x140003916  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000391d  test    r9, r9
0x140003920  jz      short loc_140003937
0x140003922  lea     r8, aCallerP; "(caller: %p) "
0x140003929  mov     rdx, rsi; unsigned __int16 *
0x14000392c  mov     rcx, rax; this
0x14000392f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003934  mov     r14, rax
0x140003937  call    cs:__imp_GetCurrentThreadId
0x14000393d  lea     rcx, [rsp+278h+Buffer]
0x140003942  mov     [rsp+278h+var_240], rcx
0x140003947  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000394b  mov     [rsp+278h+nSize], eax
0x14000394f  mov     eax, [rbx+44h]
0x140003952  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140003956  mov     r9, rdi; unsigned __int16 *
0x140003959  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140003960  mov     rdx, rsi; unsigned __int16 *
0x140003963  mov     rcx, r14; this
0x140003966  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000396b  cmp     [rbx+18h], r15
0x14000396f  jnz     short loc_140003981
0x140003971  cmp     [rbx+48h], r15
0x140003975  jnz     short loc_140003981
0x140003977  cmp     [rbx+30h], r15
0x14000397b  jz      loc_140003A11
0x140003981  lea     r8, asc_1400076A8; "    "
0x140003988  mov     rdx, rsi; unsigned __int16 *
0x14000398b  mov     rcx, rax; this
0x14000398e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003993  mov     r9, [rbx+18h]; unsigned __int16 *
0x140003997  test    r9, r9
0x14000399a  jz      short loc_1400039AE
0x14000399c  lea     r8, aMsgWs; "Msg:[%ws] "
0x1400039a3  mov     rdx, rsi; unsigned __int16 *
0x1400039a6  mov     rcx, rax; this
0x1400039a9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400039ae  mov     r9, [rbx+48h]; unsigned __int16 *
0x1400039b2  test    r9, r9
0x1400039b5  jz      short loc_1400039C9
0x1400039b7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1400039be  mov     rdx, rsi; unsigned __int16 *
0x1400039c1  mov     rcx, rax; this
0x1400039c4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400039c9  mov     rcx, [rbx+28h]
0x1400039cd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1400039d1  mov     rdx, rsi; unsigned __int16 *
0x1400039d4  test    rcx, rcx
0x1400039d7  jz      short loc_1400039EF
0x1400039d9  mov     [rsp+278h+lpBuffer], rcx
0x1400039de  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1400039e5  mov     rcx, rax; this
0x1400039e8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400039ed  jmp     short loc_140003A11
0x1400039ef  mov     rcx, rax; this
0x1400039f2  test    r9, r9
0x1400039f5  jz      short loc_140003A05
0x1400039f7  lea     r8, aHs; "[%hs]\n"
0x1400039fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003a03  jmp     short loc_140003A11
0x140003a05  lea     r8, asc_140007720; "\n"
0x140003a0c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003a11  xor     eax, eax
0x140003a13  mov     rcx, [rsp+278h+var_38]
0x140003a1b  xor     rcx, rsp; StackCookie
0x140003a1e  call    __security_check_cookie
0x140003a23  mov     rbx, [rsp+278h+arg_18]
0x140003a2b  add     rsp, 250h
0x140003a32  pop     r15
0x140003a34  pop     r14
0x140003a36  pop     rdi
0x140003a37  pop     rsi
0x140003a38  pop     rbp
0x140003a39  retn
```
