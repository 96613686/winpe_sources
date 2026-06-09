# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004534`
- end: `0x1800047ea`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180002ab4`
- `0x180002d24`
- `0x180004fe0`
- `0x1800076d0`

## callees

- `0x180001be0`
- `0x180002612`
- `0x180004534`
- `0x1800052e0`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800046e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800046e7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004666`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004666`

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
          v7 = (const char *)&byte_18000A8A5;
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
0x180004534  mov     [rsp+arg_18], rbx
0x180004539  push    rbp
0x18000453a  push    rsi
0x18000453b  push    rdi
0x18000453c  push    r14
0x18000453e  push    r15
0x180004540  sub     rsp, 250h
0x180004547  mov     rax, cs:__security_cookie
0x18000454e  xor     rax, rsp
0x180004551  mov     [rsp+278h+var_38], rax
0x180004559  mov     rbx, r8
0x18000455c  mov     rsi, rdx
0x18000455f  mov     r14, rcx
0x180004562  xor     r15d, r15d
0x180004565  test    rdx, rdx
0x180004568  jz      loc_1800047C1
0x18000456e  test    rcx, rcx
0x180004571  jz      loc_1800047C1
0x180004577  mov     [rcx], r15w
0x18000457b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004582  test    rax, rax
0x180004585  jz      short loc_1800045A8
0x180004587  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000458e  jz      short loc_1800045A8
0x180004590  mov     r8, rdx
0x180004593  mov     rdx, rcx
0x180004596  mov     rcx, rbx
0x180004599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000459e  cmp     [r14], r15w
0x1800045a2  jnz     loc_1800047C1
0x1800045a8  mov     ecx, [rbx]
0x1800045aa  mov     bpl, 8
0x1800045ad  test    ecx, ecx
0x1800045af  jz      short loc_1800045FA
0x1800045b1  sub     ecx, 1
0x1800045b4  jz      short loc_1800045E2
0x1800045b6  sub     ecx, 1
0x1800045b9  jz      short loc_1800045D2
0x1800045bb  cmp     ecx, 1
0x1800045be  jz      short loc_1800045C9
0x1800045c0  lea     rdi, byte_18000A8A5
0x1800045c7  jmp     short loc_180004601
0x1800045c9  lea     rdi, aFailfast; "FailFast"
0x1800045d0  jmp     short loc_180004601
0x1800045d2  lea     rax, aLoghr; "LogHr"
0x1800045d9  lea     rdi, aLognt; "LogNt"
0x1800045e0  jmp     short loc_1800045F0
0x1800045e2  lea     rax, aReturnhr; "ReturnHr"
0x1800045e9  lea     rdi, aReturnnt; "ReturnNt"
0x1800045f0  test    [rbx+4], bpl
0x1800045f4  cmovz   rdi, rax
0x1800045f8  jmp     short loc_180004601
0x1800045fa  lea     rdi, aException; "Exception"
0x180004601  xor     edx, edx; Val
0x180004603  mov     r8d, 200h; Size
0x180004609  lea     rcx, [rsp+278h+Buffer]; void *
0x18000460e  call    memset_0
0x180004613  test    [rbx+4], bpl
0x180004617  jz      short loc_18000463C
0x180004619  mov     ebp, [rbx+0Ch]
0x18000461c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004623  test    rax, rax
0x180004626  jz      short loc_18000466C
0x180004628  mov     r8d, 100h
0x18000462e  lea     rdx, [rsp+278h+Buffer]
0x180004633  mov     ecx, ebp
0x180004635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000463a  jmp     short loc_18000466C
0x18000463c  mov     ebp, [rbx+8]
0x18000463f  mov     [rsp+278h+Arguments], r15; Arguments
0x180004644  mov     [rsp+278h+nSize], 100h; nSize
0x18000464c  lea     rax, [rsp+278h+Buffer]
0x180004651  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004656  mov     r9d, 400h; dwLanguageId
0x18000465c  mov     r8d, ebp; dwMessageId
0x18000465f  xor     edx, edx; lpSource
0x180004661  mov     ecx, 1200h; dwFlags
0x180004666  call    cs:__imp_FormatMessageW
0x18000466c  lea     rsi, [r14+rsi*2]
0x180004670  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004674  mov     rax, [rbx+88h]
0x18000467b  mov     rcx, [rbx+80h]
0x180004682  mov     rdx, rsi; unsigned __int16 *
0x180004685  test    r9, r9
0x180004688  jz      short loc_1800046AC
0x18000468a  mov     [rsp+278h+Arguments], rax
0x18000468f  mov     qword ptr [rsp+278h+nSize], rcx
0x180004694  mov     eax, [rbx+40h]
0x180004697  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000469b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800046a2  mov     rcx, r14; this
0x1800046a5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800046aa  jmp     short loc_1800046C3
0x1800046ac  mov     [rsp+278h+lpBuffer], rax
0x1800046b1  mov     r9, rcx; unsigned __int16 *
0x1800046b4  lea     r8, aHsP; "%hs!%p: "
0x1800046bb  mov     rcx, r14; this
0x1800046be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800046c3  mov     r14, rax
0x1800046c6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800046cd  test    r9, r9
0x1800046d0  jz      short loc_1800046E7
0x1800046d2  lea     r8, aCallerP; "(caller: %p) "
0x1800046d9  mov     rdx, rsi; unsigned __int16 *
0x1800046dc  mov     rcx, rax; this
0x1800046df  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800046e4  mov     r14, rax
0x1800046e7  call    cs:__imp_GetCurrentThreadId
0x1800046ed  lea     rcx, [rsp+278h+Buffer]
0x1800046f2  mov     [rsp+278h+var_240], rcx
0x1800046f7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800046fb  mov     [rsp+278h+nSize], eax
0x1800046ff  mov     eax, [rbx+44h]
0x180004702  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004706  mov     r9, rdi; unsigned __int16 *
0x180004709  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004710  mov     rdx, rsi; unsigned __int16 *
0x180004713  mov     rcx, r14; this
0x180004716  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000471b  cmp     [rbx+18h], r15
0x18000471f  jnz     short loc_180004731
0x180004721  cmp     [rbx+48h], r15
0x180004725  jnz     short loc_180004731
0x180004727  cmp     [rbx+30h], r15
0x18000472b  jz      loc_1800047C1
0x180004731  lea     r8, asc_18000A9B0; "    "
0x180004738  mov     rdx, rsi; unsigned __int16 *
0x18000473b  mov     rcx, rax; this
0x18000473e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004743  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004747  test    r9, r9
0x18000474a  jz      short loc_18000475E
0x18000474c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004753  mov     rdx, rsi; unsigned __int16 *
0x180004756  mov     rcx, rax; this
0x180004759  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000475e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004762  test    r9, r9
0x180004765  jz      short loc_180004779
0x180004767  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000476e  mov     rdx, rsi; unsigned __int16 *
0x180004771  mov     rcx, rax; this
0x180004774  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004779  mov     rcx, [rbx+28h]
0x18000477d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004781  mov     rdx, rsi; unsigned __int16 *
0x180004784  test    rcx, rcx
0x180004787  jz      short loc_18000479F
0x180004789  mov     [rsp+278h+lpBuffer], rcx
0x18000478e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004795  mov     rcx, rax; this
0x180004798  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000479d  jmp     short loc_1800047C1
0x18000479f  mov     rcx, rax; this
0x1800047a2  test    r9, r9
0x1800047a5  jz      short loc_1800047B5
0x1800047a7  lea     r8, aHs; "[%hs]\n"
0x1800047ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800047b3  jmp     short loc_1800047C1
0x1800047b5  lea     r8, asc_18000AA28; "\n"
0x1800047bc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800047c1  xor     eax, eax
0x1800047c3  mov     rcx, [rsp+278h+var_38]
0x1800047cb  xor     rcx, rsp; StackCookie
0x1800047ce  call    __security_check_cookie
0x1800047d3  mov     rbx, [rsp+278h+arg_18]
0x1800047db  add     rsp, 250h
0x1800047e2  pop     r15
0x1800047e4  pop     r14
0x1800047e6  pop     rdi
0x1800047e7  pop     rsi
0x1800047e8  pop     rbp
0x1800047e9  retn
```
