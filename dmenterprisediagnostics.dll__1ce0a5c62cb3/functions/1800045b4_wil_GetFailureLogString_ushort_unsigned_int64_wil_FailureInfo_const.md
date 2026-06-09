# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800045b4`
- end: `0x18000486a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180002f08`
- `0x180004f84`
- `0x18000541c`
- `0x1800074c0`

## callees

- `0x1800017e0`
- `0x1800023c0`
- `0x1800045b4`
- `0x180005284`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004767`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004767`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800046e6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800046e6`

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
          v7 = (const char *)&qword_180029440;
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
0x1800045b4  mov     [rsp+arg_18], rbx
0x1800045b9  push    rbp
0x1800045ba  push    rsi
0x1800045bb  push    rdi
0x1800045bc  push    r14
0x1800045be  push    r15
0x1800045c0  sub     rsp, 250h
0x1800045c7  mov     rax, cs:__security_cookie
0x1800045ce  xor     rax, rsp
0x1800045d1  mov     [rsp+278h+var_38], rax
0x1800045d9  mov     rbx, r8
0x1800045dc  mov     rsi, rdx
0x1800045df  mov     r14, rcx
0x1800045e2  xor     r15d, r15d
0x1800045e5  test    rdx, rdx
0x1800045e8  jz      loc_180004841
0x1800045ee  test    rcx, rcx
0x1800045f1  jz      loc_180004841
0x1800045f7  mov     [rcx], r15w
0x1800045fb  mov     rax, cs:g_pfnResultLoggingCallback
0x180004602  test    rax, rax
0x180004605  jz      short loc_180004628
0x180004607  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000460e  jz      short loc_180004628
0x180004610  mov     r8, rdx
0x180004613  mov     rdx, rcx
0x180004616  mov     rcx, rbx
0x180004619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000461e  cmp     [r14], r15w
0x180004622  jnz     loc_180004841
0x180004628  mov     ecx, [rbx]
0x18000462a  mov     bpl, 8
0x18000462d  test    ecx, ecx
0x18000462f  jz      short loc_18000467A
0x180004631  sub     ecx, 1
0x180004634  jz      short loc_180004662
0x180004636  sub     ecx, 1
0x180004639  jz      short loc_180004652
0x18000463b  cmp     ecx, 1
0x18000463e  jz      short loc_180004649
0x180004640  lea     rdi, qword_180029440
0x180004647  jmp     short loc_180004681
0x180004649  lea     rdi, aFailfast; "FailFast"
0x180004650  jmp     short loc_180004681
0x180004652  lea     rax, aLoghr; "LogHr"
0x180004659  lea     rdi, aLognt; "LogNt"
0x180004660  jmp     short loc_180004670
0x180004662  lea     rax, aReturnhr; "ReturnHr"
0x180004669  lea     rdi, aReturnnt; "ReturnNt"
0x180004670  test    [rbx+4], bpl
0x180004674  cmovz   rdi, rax
0x180004678  jmp     short loc_180004681
0x18000467a  lea     rdi, aException; "Exception"
0x180004681  xor     edx, edx; Val
0x180004683  mov     r8d, 200h; Size
0x180004689  lea     rcx, [rsp+278h+Buffer]; void *
0x18000468e  call    memset_0
0x180004693  test    [rbx+4], bpl
0x180004697  jz      short loc_1800046BC
0x180004699  mov     ebp, [rbx+0Ch]
0x18000469c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800046a3  test    rax, rax
0x1800046a6  jz      short loc_1800046EC
0x1800046a8  mov     r8d, 100h
0x1800046ae  lea     rdx, [rsp+278h+Buffer]
0x1800046b3  mov     ecx, ebp
0x1800046b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046ba  jmp     short loc_1800046EC
0x1800046bc  mov     ebp, [rbx+8]
0x1800046bf  mov     [rsp+278h+Arguments], r15; Arguments
0x1800046c4  mov     [rsp+278h+nSize], 100h; nSize
0x1800046cc  lea     rax, [rsp+278h+Buffer]
0x1800046d1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800046d6  mov     r9d, 400h; dwLanguageId
0x1800046dc  mov     r8d, ebp; dwMessageId
0x1800046df  xor     edx, edx; lpSource
0x1800046e1  mov     ecx, 1200h; dwFlags
0x1800046e6  call    cs:__imp_FormatMessageW
0x1800046ec  lea     rsi, [r14+rsi*2]
0x1800046f0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800046f4  mov     rax, [rbx+88h]
0x1800046fb  mov     rcx, [rbx+80h]
0x180004702  mov     rdx, rsi; unsigned __int16 *
0x180004705  test    r9, r9
0x180004708  jz      short loc_18000472C
0x18000470a  mov     [rsp+278h+Arguments], rax
0x18000470f  mov     qword ptr [rsp+278h+nSize], rcx
0x180004714  mov     eax, [rbx+40h]
0x180004717  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000471b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004722  mov     rcx, r14; this
0x180004725  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000472a  jmp     short loc_180004743
0x18000472c  mov     [rsp+278h+lpBuffer], rax
0x180004731  mov     r9, rcx; unsigned __int16 *
0x180004734  lea     r8, aHsP; "%hs!%p: "
0x18000473b  mov     rcx, r14; this
0x18000473e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004743  mov     r14, rax
0x180004746  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000474d  test    r9, r9
0x180004750  jz      short loc_180004767
0x180004752  lea     r8, aCallerP; "(caller: %p) "
0x180004759  mov     rdx, rsi; unsigned __int16 *
0x18000475c  mov     rcx, rax; this
0x18000475f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004764  mov     r14, rax
0x180004767  call    cs:__imp_GetCurrentThreadId
0x18000476d  lea     rcx, [rsp+278h+Buffer]
0x180004772  mov     [rsp+278h+var_240], rcx
0x180004777  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000477b  mov     [rsp+278h+nSize], eax
0x18000477f  mov     eax, [rbx+44h]
0x180004782  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004786  mov     r9, rdi; unsigned __int16 *
0x180004789  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004790  mov     rdx, rsi; unsigned __int16 *
0x180004793  mov     rcx, r14; this
0x180004796  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000479b  cmp     [rbx+18h], r15
0x18000479f  jnz     short loc_1800047B1
0x1800047a1  cmp     [rbx+48h], r15
0x1800047a5  jnz     short loc_1800047B1
0x1800047a7  cmp     [rbx+30h], r15
0x1800047ab  jz      loc_180004841
0x1800047b1  lea     r8, asc_180029530; "    "
0x1800047b8  mov     rdx, rsi; unsigned __int16 *
0x1800047bb  mov     rcx, rax; this
0x1800047be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800047c3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800047c7  test    r9, r9
0x1800047ca  jz      short loc_1800047DE
0x1800047cc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800047d3  mov     rdx, rsi; unsigned __int16 *
0x1800047d6  mov     rcx, rax; this
0x1800047d9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800047de  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800047e2  test    r9, r9
0x1800047e5  jz      short loc_1800047F9
0x1800047e7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800047ee  mov     rdx, rsi; unsigned __int16 *
0x1800047f1  mov     rcx, rax; this
0x1800047f4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800047f9  mov     rcx, [rbx+28h]
0x1800047fd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004801  mov     rdx, rsi; unsigned __int16 *
0x180004804  test    rcx, rcx
0x180004807  jz      short loc_18000481F
0x180004809  mov     [rsp+278h+lpBuffer], rcx
0x18000480e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004815  mov     rcx, rax; this
0x180004818  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000481d  jmp     short loc_180004841
0x18000481f  mov     rcx, rax; this
0x180004822  test    r9, r9
0x180004825  jz      short loc_180004835
0x180004827  lea     r8, aHs; "[%hs]\n"
0x18000482e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004833  jmp     short loc_180004841
0x180004835  lea     r8, asc_1800295A8; "\n"
0x18000483c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004841  xor     eax, eax
0x180004843  mov     rcx, [rsp+278h+var_38]
0x18000484b  xor     rcx, rsp; StackCookie
0x18000484e  call    __security_check_cookie
0x180004853  mov     rbx, [rsp+278h+arg_18]
0x18000485b  add     rsp, 250h
0x180004862  pop     r15
0x180004864  pop     r14
0x180004866  pop     rdi
0x180004867  pop     rsi
0x180004868  pop     rbp
0x180004869  retn
```
