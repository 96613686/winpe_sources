# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800046f4`
- end: `0x1800049aa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x1800032e8`
- `0x180003568`
- `0x180005060`
- `0x1800068b0`
- `0x1800070d0`
- `0x18000d790`
- `0x18000d8c4`

## callees

- `0x180001ba0`
- `0x18000296c`
- `0x1800046f4`
- `0x180005360`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048a7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004826`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004826`

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
          v7 = (const char *)&qword_180010428;
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
0x1800046f4  mov     [rsp+arg_18], rbx
0x1800046f9  push    rbp
0x1800046fa  push    rsi
0x1800046fb  push    rdi
0x1800046fc  push    r14
0x1800046fe  push    r15
0x180004700  sub     rsp, 250h
0x180004707  mov     rax, cs:__security_cookie
0x18000470e  xor     rax, rsp
0x180004711  mov     [rsp+278h+var_38], rax
0x180004719  mov     rbx, r8
0x18000471c  mov     rsi, rdx
0x18000471f  mov     r14, rcx
0x180004722  xor     r15d, r15d
0x180004725  test    rdx, rdx
0x180004728  jz      loc_180004981
0x18000472e  test    rcx, rcx
0x180004731  jz      loc_180004981
0x180004737  mov     [rcx], r15w
0x18000473b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004742  test    rax, rax
0x180004745  jz      short loc_180004768
0x180004747  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000474e  jz      short loc_180004768
0x180004750  mov     r8, rdx
0x180004753  mov     rdx, rcx
0x180004756  mov     rcx, rbx
0x180004759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000475e  cmp     [r14], r15w
0x180004762  jnz     loc_180004981
0x180004768  mov     ecx, [rbx]
0x18000476a  mov     bpl, 8
0x18000476d  test    ecx, ecx
0x18000476f  jz      short loc_1800047BA
0x180004771  sub     ecx, 1
0x180004774  jz      short loc_1800047A2
0x180004776  sub     ecx, 1
0x180004779  jz      short loc_180004792
0x18000477b  cmp     ecx, 1
0x18000477e  jz      short loc_180004789
0x180004780  lea     rdi, qword_180010428
0x180004787  jmp     short loc_1800047C1
0x180004789  lea     rdi, aFailfast; "FailFast"
0x180004790  jmp     short loc_1800047C1
0x180004792  lea     rax, aLoghr; "LogHr"
0x180004799  lea     rdi, aLognt; "LogNt"
0x1800047a0  jmp     short loc_1800047B0
0x1800047a2  lea     rax, aReturnhr; "ReturnHr"
0x1800047a9  lea     rdi, aReturnnt; "ReturnNt"
0x1800047b0  test    [rbx+4], bpl
0x1800047b4  cmovz   rdi, rax
0x1800047b8  jmp     short loc_1800047C1
0x1800047ba  lea     rdi, aException; "Exception"
0x1800047c1  xor     edx, edx; Val
0x1800047c3  mov     r8d, 200h; Size
0x1800047c9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800047ce  call    memset_0
0x1800047d3  test    [rbx+4], bpl
0x1800047d7  jz      short loc_1800047FC
0x1800047d9  mov     ebp, [rbx+0Ch]
0x1800047dc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800047e3  test    rax, rax
0x1800047e6  jz      short loc_18000482C
0x1800047e8  mov     r8d, 100h
0x1800047ee  lea     rdx, [rsp+278h+Buffer]
0x1800047f3  mov     ecx, ebp
0x1800047f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047fa  jmp     short loc_18000482C
0x1800047fc  mov     ebp, [rbx+8]
0x1800047ff  mov     [rsp+278h+Arguments], r15; Arguments
0x180004804  mov     [rsp+278h+nSize], 100h; nSize
0x18000480c  lea     rax, [rsp+278h+Buffer]
0x180004811  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004816  mov     r9d, 400h; dwLanguageId
0x18000481c  mov     r8d, ebp; dwMessageId
0x18000481f  xor     edx, edx; lpSource
0x180004821  mov     ecx, 1200h; dwFlags
0x180004826  call    cs:__imp_FormatMessageW
0x18000482c  lea     rsi, [r14+rsi*2]
0x180004830  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004834  mov     rax, [rbx+88h]
0x18000483b  mov     rcx, [rbx+80h]
0x180004842  mov     rdx, rsi; unsigned __int16 *
0x180004845  test    r9, r9
0x180004848  jz      short loc_18000486C
0x18000484a  mov     [rsp+278h+Arguments], rax
0x18000484f  mov     qword ptr [rsp+278h+nSize], rcx
0x180004854  mov     eax, [rbx+40h]
0x180004857  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000485b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004862  mov     rcx, r14; this
0x180004865  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000486a  jmp     short loc_180004883
0x18000486c  mov     [rsp+278h+lpBuffer], rax
0x180004871  mov     r9, rcx; unsigned __int16 *
0x180004874  lea     r8, aHsP; "%hs!%p: "
0x18000487b  mov     rcx, r14; this
0x18000487e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004883  mov     r14, rax
0x180004886  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000488d  test    r9, r9
0x180004890  jz      short loc_1800048A7
0x180004892  lea     r8, aCallerP; "(caller: %p) "
0x180004899  mov     rdx, rsi; unsigned __int16 *
0x18000489c  mov     rcx, rax; this
0x18000489f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800048a4  mov     r14, rax
0x1800048a7  call    cs:__imp_GetCurrentThreadId
0x1800048ad  lea     rcx, [rsp+278h+Buffer]
0x1800048b2  mov     [rsp+278h+var_240], rcx
0x1800048b7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800048bb  mov     [rsp+278h+nSize], eax
0x1800048bf  mov     eax, [rbx+44h]
0x1800048c2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800048c6  mov     r9, rdi; unsigned __int16 *
0x1800048c9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800048d0  mov     rdx, rsi; unsigned __int16 *
0x1800048d3  mov     rcx, r14; this
0x1800048d6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800048db  cmp     [rbx+18h], r15
0x1800048df  jnz     short loc_1800048F1
0x1800048e1  cmp     [rbx+48h], r15
0x1800048e5  jnz     short loc_1800048F1
0x1800048e7  cmp     [rbx+30h], r15
0x1800048eb  jz      loc_180004981
0x1800048f1  lea     r8, asc_180010530; "    "
0x1800048f8  mov     rdx, rsi; unsigned __int16 *
0x1800048fb  mov     rcx, rax; this
0x1800048fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004903  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004907  test    r9, r9
0x18000490a  jz      short loc_18000491E
0x18000490c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004913  mov     rdx, rsi; unsigned __int16 *
0x180004916  mov     rcx, rax; this
0x180004919  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000491e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004922  test    r9, r9
0x180004925  jz      short loc_180004939
0x180004927  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000492e  mov     rdx, rsi; unsigned __int16 *
0x180004931  mov     rcx, rax; this
0x180004934  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004939  mov     rcx, [rbx+28h]
0x18000493d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004941  mov     rdx, rsi; unsigned __int16 *
0x180004944  test    rcx, rcx
0x180004947  jz      short loc_18000495F
0x180004949  mov     [rsp+278h+lpBuffer], rcx
0x18000494e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004955  mov     rcx, rax; this
0x180004958  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000495d  jmp     short loc_180004981
0x18000495f  mov     rcx, rax; this
0x180004962  test    r9, r9
0x180004965  jz      short loc_180004975
0x180004967  lea     r8, aHs; "[%hs]\n"
0x18000496e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004973  jmp     short loc_180004981
0x180004975  lea     r8, asc_1800105A8; "\n"
0x18000497c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004981  xor     eax, eax
0x180004983  mov     rcx, [rsp+278h+var_38]
0x18000498b  xor     rcx, rsp; StackCookie
0x18000498e  call    __security_check_cookie
0x180004993  mov     rbx, [rsp+278h+arg_18]
0x18000499b  add     rsp, 250h
0x1800049a2  pop     r15
0x1800049a4  pop     r14
0x1800049a6  pop     rdi
0x1800049a7  pop     rsi
0x1800049a8  pop     rbp
0x1800049a9  retn
```
