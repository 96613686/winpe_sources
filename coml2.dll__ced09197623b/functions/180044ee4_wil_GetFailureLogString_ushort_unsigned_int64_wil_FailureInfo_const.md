# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180044ee4`
- end: `0x18004519a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180043c40`
- `0x1800458d4`

## callees

- `0x180042800`
- `0x180043100`
- `0x180044ee4`
- `0x180045bd4`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180045016`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180045016`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180045097`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180045097`

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
          v8 = (const char *)&word_18006727E;
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
0x180044ee4  mov     [rsp+arg_18], rbx
0x180044ee9  push    rbp
0x180044eea  push    rsi
0x180044eeb  push    rdi
0x180044eec  push    r14
0x180044eee  push    r15
0x180044ef0  sub     rsp, 250h
0x180044ef7  mov     rax, cs:__security_cookie
0x180044efe  xor     rax, rsp
0x180044f01  mov     [rsp+278h+var_38], rax
0x180044f09  xor     r15d, r15d
0x180044f0c  mov     rbx, r8
0x180044f0f  mov     rsi, rdx
0x180044f12  mov     r14, rcx
0x180044f15  test    rdx, rdx
0x180044f18  jz      loc_180045171
0x180044f1e  test    rcx, rcx
0x180044f21  jz      loc_180045171
0x180044f27  mov     rax, cs:g_pfnResultLoggingCallback
0x180044f2e  mov     [rcx], r15w
0x180044f32  test    rax, rax
0x180044f35  jz      short loc_180044F58
0x180044f37  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180044f3e  jz      short loc_180044F58
0x180044f40  mov     r8, rdx
0x180044f43  mov     rdx, rcx
0x180044f46  mov     rcx, rbx
0x180044f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f4e  cmp     [r14], r15w
0x180044f52  jnz     loc_180045171
0x180044f58  mov     ecx, [rbx]
0x180044f5a  mov     bpl, 8
0x180044f5d  test    ecx, ecx
0x180044f5f  jz      short loc_180044FAA
0x180044f61  sub     ecx, 1
0x180044f64  jz      short loc_180044F92
0x180044f66  sub     ecx, 1
0x180044f69  jz      short loc_180044F82
0x180044f6b  cmp     ecx, 1
0x180044f6e  jz      short loc_180044F79
0x180044f70  lea     rdi, word_18006727E
0x180044f77  jmp     short loc_180044FB1
0x180044f79  lea     rdi, aFailfast; "FailFast"
0x180044f80  jmp     short loc_180044FB1
0x180044f82  lea     rax, aLoghr; "LogHr"
0x180044f89  lea     rdi, aLognt; "LogNt"
0x180044f90  jmp     short loc_180044FA0
0x180044f92  lea     rax, aReturnhr; "ReturnHr"
0x180044f99  lea     rdi, aReturnnt; "ReturnNt"
0x180044fa0  test    [rbx+4], bpl
0x180044fa4  cmovz   rdi, rax
0x180044fa8  jmp     short loc_180044FB1
0x180044faa  lea     rdi, aException; "Exception"
0x180044fb1  xor     edx, edx; Val
0x180044fb3  lea     rcx, [rsp+278h+Buffer]; void *
0x180044fb8  mov     r8d, 200h; Size
0x180044fbe  call    memset_0
0x180044fc3  test    [rbx+4], bpl
0x180044fc7  jz      short loc_180044FEC
0x180044fc9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180044fd0  mov     ebp, [rbx+0Ch]
0x180044fd3  test    rax, rax
0x180044fd6  jz      short loc_18004501C
0x180044fd8  mov     r8d, 100h
0x180044fde  lea     rdx, [rsp+278h+Buffer]
0x180044fe3  mov     ecx, ebp
0x180044fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044fea  jmp     short loc_18004501C
0x180044fec  mov     ebp, [rbx+8]
0x180044fef  lea     rax, [rsp+278h+Buffer]
0x180044ff4  mov     [rsp+278h+Arguments], r15; Arguments
0x180044ff9  mov     r8d, ebp; dwMessageId
0x180044ffc  mov     [rsp+278h+nSize], 100h; nSize
0x180045004  mov     r9d, 400h; dwLanguageId
0x18004500a  xor     edx, edx; lpSource
0x18004500c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180045011  mov     ecx, 1200h; dwFlags
0x180045016  call    cs:__imp_FormatMessageW
0x18004501c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180045020  lea     rsi, [r14+rsi*2]
0x180045024  mov     rax, [rbx+88h]
0x18004502b  mov     rdx, rsi; unsigned __int16 *
0x18004502e  mov     rcx, [rbx+80h]
0x180045035  test    r9, r9
0x180045038  jz      short loc_18004505C
0x18004503a  mov     [rsp+278h+Arguments], rax
0x18004503f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180045046  mov     eax, [rbx+40h]
0x180045049  mov     qword ptr [rsp+278h+nSize], rcx
0x18004504e  mov     rcx, r14; this
0x180045051  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180045055  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004505a  jmp     short loc_180045073
0x18004505c  mov     r9, rcx; unsigned __int16 *
0x18004505f  mov     [rsp+278h+lpBuffer], rax
0x180045064  mov     rcx, r14; this
0x180045067  lea     r8, aHsP; "%hs!%p: "
0x18004506e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180045073  mov     r9, [rbx+90h]; unsigned __int16 *
0x18004507a  mov     r14, rax
0x18004507d  test    r9, r9
0x180045080  jz      short loc_180045097
0x180045082  lea     r8, aCallerP; "(caller: %p) "
0x180045089  mov     rdx, rsi; unsigned __int16 *
0x18004508c  mov     rcx, rax; this
0x18004508f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180045094  mov     r14, rax
0x180045097  call    cs:__imp_GetCurrentThreadId
0x18004509d  lea     rcx, [rsp+278h+Buffer]
0x1800450a2  mov     r9, rdi; unsigned __int16 *
0x1800450a5  mov     [rsp+278h+var_240], rcx
0x1800450aa  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800450b1  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800450b5  mov     rdx, rsi; unsigned __int16 *
0x1800450b8  mov     [rsp+278h+nSize], eax
0x1800450bc  mov     rcx, r14; this
0x1800450bf  mov     eax, [rbx+44h]
0x1800450c2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800450c6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800450cb  cmp     [rbx+18h], r15
0x1800450cf  jnz     short loc_1800450E1
0x1800450d1  cmp     [rbx+48h], r15
0x1800450d5  jnz     short loc_1800450E1
0x1800450d7  cmp     [rbx+30h], r15
0x1800450db  jz      loc_180045171
0x1800450e1  lea     r8, asc_180067368; "    "
0x1800450e8  mov     rdx, rsi; unsigned __int16 *
0x1800450eb  mov     rcx, rax; this
0x1800450ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800450f3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800450f7  test    r9, r9
0x1800450fa  jz      short loc_18004510E
0x1800450fc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180045103  mov     rdx, rsi; unsigned __int16 *
0x180045106  mov     rcx, rax; this
0x180045109  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004510e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180045112  test    r9, r9
0x180045115  jz      short loc_180045129
0x180045117  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18004511e  mov     rdx, rsi; unsigned __int16 *
0x180045121  mov     rcx, rax; this
0x180045124  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180045129  mov     rcx, [rbx+28h]
0x18004512d  mov     rdx, rsi; unsigned __int16 *
0x180045130  mov     r9, [rbx+30h]; unsigned __int16 *
0x180045134  test    rcx, rcx
0x180045137  jz      short loc_18004514F
0x180045139  mov     [rsp+278h+lpBuffer], rcx
0x18004513e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180045145  mov     rcx, rax; this
0x180045148  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004514d  jmp     short loc_180045171
0x18004514f  mov     rcx, rax; this
0x180045152  test    r9, r9
0x180045155  jz      short loc_180045165
0x180045157  lea     r8, aHs; "[%hs]\n"
0x18004515e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180045163  jmp     short loc_180045171
0x180045165  lea     r8, asc_1800673E0; "\n"
0x18004516c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180045171  xor     eax, eax
0x180045173  mov     rcx, [rsp+278h+var_38]
0x18004517b  xor     rcx, rsp; StackCookie
0x18004517e  call    __security_check_cookie
0x180045183  mov     rbx, [rsp+278h+arg_18]
0x18004518b  add     rsp, 250h
0x180045192  pop     r15
0x180045194  pop     r14
0x180045196  pop     rdi
0x180045197  pop     rsi
0x180045198  pop     rbp
0x180045199  retn
```
