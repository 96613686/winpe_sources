# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004494`
- end: `0x18000474a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180005cc0`
- `0x180006ae4`
- `0x180006d64`
- `0x180008e5c`
- `0x18000b758`
- `0x180043bef`
- `0x180043d23`

## callees

- `0x180004494`
- `0x180004b08`
- `0x18004371a`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004647`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004647`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800045c6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800045c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
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
          v7 = (const char *)&qword_180049F28;
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
0x180004494  mov     [rsp+arg_18], rbx
0x180004499  push    rbp
0x18000449a  push    rsi
0x18000449b  push    rdi
0x18000449c  push    r14
0x18000449e  push    r15
0x1800044a0  sub     rsp, 250h
0x1800044a7  mov     rax, cs:__security_cookie
0x1800044ae  xor     rax, rsp
0x1800044b1  mov     [rsp+278h+var_38], rax
0x1800044b9  mov     rbx, r8
0x1800044bc  mov     rsi, rdx
0x1800044bf  mov     r14, rcx
0x1800044c2  xor     r15d, r15d
0x1800044c5  test    rdx, rdx
0x1800044c8  jz      loc_180004721
0x1800044ce  test    rcx, rcx
0x1800044d1  jz      loc_180004721
0x1800044d7  mov     [rcx], r15w
0x1800044db  mov     rax, cs:g_pfnResultLoggingCallback
0x1800044e2  test    rax, rax
0x1800044e5  jz      short loc_180004508
0x1800044e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800044ee  jz      short loc_180004508
0x1800044f0  mov     r8, rdx
0x1800044f3  mov     rdx, rcx
0x1800044f6  mov     rcx, rbx
0x1800044f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044fe  cmp     [r14], r15w
0x180004502  jnz     loc_180004721
0x180004508  mov     ecx, [rbx]
0x18000450a  mov     bpl, 8
0x18000450d  test    ecx, ecx
0x18000450f  jz      short loc_18000455A
0x180004511  sub     ecx, 1
0x180004514  jz      short loc_180004542
0x180004516  sub     ecx, 1
0x180004519  jz      short loc_180004532
0x18000451b  cmp     ecx, 1
0x18000451e  jz      short loc_180004529
0x180004520  lea     rdi, qword_180049F28
0x180004527  jmp     short loc_180004561
0x180004529  lea     rdi, aFailfast; "FailFast"
0x180004530  jmp     short loc_180004561
0x180004532  lea     rax, aLoghr; "LogHr"
0x180004539  lea     rdi, aLognt; "LogNt"
0x180004540  jmp     short loc_180004550
0x180004542  lea     rax, aReturnhr; "ReturnHr"
0x180004549  lea     rdi, aReturnnt; "ReturnNt"
0x180004550  test    [rbx+4], bpl
0x180004554  cmovz   rdi, rax
0x180004558  jmp     short loc_180004561
0x18000455a  lea     rdi, aException; "Exception"
0x180004561  xor     edx, edx; Val
0x180004563  mov     r8d, 200h; Size
0x180004569  lea     rcx, [rsp+278h+Buffer]; void *
0x18000456e  call    memset_0
0x180004573  test    [rbx+4], bpl
0x180004577  jz      short loc_18000459C
0x180004579  mov     ebp, [rbx+0Ch]
0x18000457c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004583  test    rax, rax
0x180004586  jz      short loc_1800045CC
0x180004588  mov     r8d, 100h
0x18000458e  lea     rdx, [rsp+278h+Buffer]
0x180004593  mov     ecx, ebp
0x180004595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000459a  jmp     short loc_1800045CC
0x18000459c  mov     ebp, [rbx+8]
0x18000459f  mov     [rsp+278h+Arguments], r15; Arguments
0x1800045a4  mov     [rsp+278h+nSize], 100h; nSize
0x1800045ac  lea     rax, [rsp+278h+Buffer]
0x1800045b1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800045b6  mov     r9d, 400h; dwLanguageId
0x1800045bc  mov     r8d, ebp; dwMessageId
0x1800045bf  xor     edx, edx; lpSource
0x1800045c1  mov     ecx, 1200h; dwFlags
0x1800045c6  call    cs:__imp_FormatMessageW
0x1800045cc  lea     rsi, [r14+rsi*2]
0x1800045d0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800045d4  mov     rax, [rbx+88h]
0x1800045db  mov     rcx, [rbx+80h]
0x1800045e2  mov     rdx, rsi; unsigned __int16 *
0x1800045e5  test    r9, r9
0x1800045e8  jz      short loc_18000460C
0x1800045ea  mov     [rsp+278h+Arguments], rax
0x1800045ef  mov     qword ptr [rsp+278h+nSize], rcx
0x1800045f4  mov     eax, [rbx+40h]
0x1800045f7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800045fb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004602  mov     rcx, r14; this
0x180004605  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000460a  jmp     short loc_180004623
0x18000460c  mov     [rsp+278h+lpBuffer], rax
0x180004611  mov     r9, rcx; unsigned __int16 *
0x180004614  lea     r8, aHsP; "%hs!%p: "
0x18000461b  mov     rcx, r14; this
0x18000461e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004623  mov     r14, rax
0x180004626  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000462d  test    r9, r9
0x180004630  jz      short loc_180004647
0x180004632  lea     r8, aCallerP; "(caller: %p) "
0x180004639  mov     rdx, rsi; unsigned __int16 *
0x18000463c  mov     rcx, rax; this
0x18000463f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004644  mov     r14, rax
0x180004647  call    cs:__imp_GetCurrentThreadId
0x18000464d  lea     rcx, [rsp+278h+Buffer]
0x180004652  mov     [rsp+278h+var_240], rcx
0x180004657  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000465b  mov     [rsp+278h+nSize], eax
0x18000465f  mov     eax, [rbx+44h]
0x180004662  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004666  mov     r9, rdi; unsigned __int16 *
0x180004669  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004670  mov     rdx, rsi; unsigned __int16 *
0x180004673  mov     rcx, r14; this
0x180004676  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000467b  cmp     [rbx+18h], r15
0x18000467f  jnz     short loc_180004691
0x180004681  cmp     [rbx+48h], r15
0x180004685  jnz     short loc_180004691
0x180004687  cmp     [rbx+30h], r15
0x18000468b  jz      loc_180004721
0x180004691  lea     r8, asc_18004A068; "    "
0x180004698  mov     rdx, rsi; unsigned __int16 *
0x18000469b  mov     rcx, rax; this
0x18000469e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800046a3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800046a7  test    r9, r9
0x1800046aa  jz      short loc_1800046BE
0x1800046ac  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800046b3  mov     rdx, rsi; unsigned __int16 *
0x1800046b6  mov     rcx, rax; this
0x1800046b9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800046be  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800046c2  test    r9, r9
0x1800046c5  jz      short loc_1800046D9
0x1800046c7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800046ce  mov     rdx, rsi; unsigned __int16 *
0x1800046d1  mov     rcx, rax; this
0x1800046d4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800046d9  mov     rcx, [rbx+28h]
0x1800046dd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800046e1  mov     rdx, rsi; unsigned __int16 *
0x1800046e4  test    rcx, rcx
0x1800046e7  jz      short loc_1800046FF
0x1800046e9  mov     [rsp+278h+lpBuffer], rcx
0x1800046ee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800046f5  mov     rcx, rax; this
0x1800046f8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800046fd  jmp     short loc_180004721
0x1800046ff  mov     rcx, rax; this
0x180004702  test    r9, r9
0x180004705  jz      short loc_180004715
0x180004707  lea     r8, aHs; "[%hs]\n"
0x18000470e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004713  jmp     short loc_180004721
0x180004715  lea     r8, asc_18004A0E0; "\n"
0x18000471c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004721  xor     eax, eax
0x180004723  mov     rcx, [rsp+278h+var_38]
0x18000472b  xor     rcx, rsp; StackCookie
0x18000472e  call    __security_check_cookie
0x180004733  mov     rbx, [rsp+278h+arg_18]
0x18000473b  add     rsp, 250h
0x180004742  pop     r15
0x180004744  pop     r14
0x180004746  pop     rdi
0x180004747  pop     rsi
0x180004748  pop     rbp
0x180004749  retn
```
