# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18001c9a4`
- end: `0x18001cc5a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18001cfec`
- `0x18001d398`
- `0x18001ddf0`

## callees

- `0x180016090`
- `0x180016a66`
- `0x18001c9a4`
- `0x18001d2ec`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001cb57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001cb57`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001cad6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001cad6`

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
      g_pfnResultLoggingCallback(a3, this, a2, a4);
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
          v7 = (const char *)&qword_180028808;
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
0x18001c9a4  mov     [rsp+arg_18], rbx
0x18001c9a9  push    rbp
0x18001c9aa  push    rsi
0x18001c9ab  push    rdi
0x18001c9ac  push    r14
0x18001c9ae  push    r15
0x18001c9b0  sub     rsp, 250h
0x18001c9b7  mov     rax, cs:__security_cookie
0x18001c9be  xor     rax, rsp
0x18001c9c1  mov     [rsp+278h+var_38], rax
0x18001c9c9  mov     rbx, r8
0x18001c9cc  mov     rsi, rdx
0x18001c9cf  mov     r14, rcx
0x18001c9d2  xor     r15d, r15d
0x18001c9d5  test    rdx, rdx
0x18001c9d8  jz      loc_18001CC31
0x18001c9de  test    rcx, rcx
0x18001c9e1  jz      loc_18001CC31
0x18001c9e7  mov     [rcx], r15w
0x18001c9eb  mov     rax, cs:g_pfnResultLoggingCallback
0x18001c9f2  test    rax, rax
0x18001c9f5  jz      short loc_18001CA18
0x18001c9f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001c9fe  jz      short loc_18001CA18
0x18001ca00  mov     r8, rdx
0x18001ca03  mov     rdx, rcx
0x18001ca06  mov     rcx, rbx
0x18001ca09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca0e  cmp     [r14], r15w
0x18001ca12  jnz     loc_18001CC31
0x18001ca18  mov     ecx, [rbx]
0x18001ca1a  mov     bpl, 8
0x18001ca1d  test    ecx, ecx
0x18001ca1f  jz      short loc_18001CA6A
0x18001ca21  sub     ecx, 1
0x18001ca24  jz      short loc_18001CA52
0x18001ca26  sub     ecx, 1
0x18001ca29  jz      short loc_18001CA42
0x18001ca2b  cmp     ecx, 1
0x18001ca2e  jz      short loc_18001CA39
0x18001ca30  lea     rdi, qword_180028808
0x18001ca37  jmp     short loc_18001CA71
0x18001ca39  lea     rdi, aFailfast; "FailFast"
0x18001ca40  jmp     short loc_18001CA71
0x18001ca42  lea     rax, aLoghr; "LogHr"
0x18001ca49  lea     rdi, aLognt; "LogNt"
0x18001ca50  jmp     short loc_18001CA60
0x18001ca52  lea     rax, aReturnhr; "ReturnHr"
0x18001ca59  lea     rdi, aReturnnt; "ReturnNt"
0x18001ca60  test    [rbx+4], bpl
0x18001ca64  cmovz   rdi, rax
0x18001ca68  jmp     short loc_18001CA71
0x18001ca6a  lea     rdi, aException; "Exception"
0x18001ca71  xor     edx, edx; Val
0x18001ca73  mov     r8d, 200h; Size
0x18001ca79  lea     rcx, [rsp+278h+Buffer]; void *
0x18001ca7e  call    memset_0
0x18001ca83  test    [rbx+4], bpl
0x18001ca87  jz      short loc_18001CAAC
0x18001ca89  mov     ebp, [rbx+0Ch]
0x18001ca8c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18001ca93  test    rax, rax
0x18001ca96  jz      short loc_18001CADC
0x18001ca98  mov     r8d, 100h
0x18001ca9e  lea     rdx, [rsp+278h+Buffer]
0x18001caa3  mov     ecx, ebp
0x18001caa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001caaa  jmp     short loc_18001CADC
0x18001caac  mov     ebp, [rbx+8]
0x18001caaf  mov     [rsp+278h+Arguments], r15; Arguments
0x18001cab4  mov     [rsp+278h+nSize], 100h; nSize
0x18001cabc  lea     rax, [rsp+278h+Buffer]
0x18001cac1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18001cac6  mov     r9d, 400h; dwLanguageId
0x18001cacc  mov     r8d, ebp; dwMessageId
0x18001cacf  xor     edx, edx; lpSource
0x18001cad1  mov     ecx, 1200h; dwFlags
0x18001cad6  call    cs:__imp_FormatMessageW
0x18001cadc  lea     rsi, [r14+rsi*2]
0x18001cae0  mov     r9, [rbx+38h]; unsigned __int16 *
0x18001cae4  mov     rax, [rbx+88h]
0x18001caeb  mov     rcx, [rbx+80h]
0x18001caf2  mov     rdx, rsi; unsigned __int16 *
0x18001caf5  test    r9, r9
0x18001caf8  jz      short loc_18001CB1C
0x18001cafa  mov     [rsp+278h+Arguments], rax
0x18001caff  mov     qword ptr [rsp+278h+nSize], rcx
0x18001cb04  mov     eax, [rbx+40h]
0x18001cb07  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001cb0b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18001cb12  mov     rcx, r14; this
0x18001cb15  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001cb1a  jmp     short loc_18001CB33
0x18001cb1c  mov     [rsp+278h+lpBuffer], rax
0x18001cb21  mov     r9, rcx; unsigned __int16 *
0x18001cb24  lea     r8, aHsP; "%hs!%p: "
0x18001cb2b  mov     rcx, r14; this
0x18001cb2e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001cb33  mov     r14, rax
0x18001cb36  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001cb3d  test    r9, r9
0x18001cb40  jz      short loc_18001CB57
0x18001cb42  lea     r8, aCallerP; "(caller: %p) "
0x18001cb49  mov     rdx, rsi; unsigned __int16 *
0x18001cb4c  mov     rcx, rax; this
0x18001cb4f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001cb54  mov     r14, rax
0x18001cb57  call    cs:__imp_GetCurrentThreadId
0x18001cb5d  lea     rcx, [rsp+278h+Buffer]
0x18001cb62  mov     [rsp+278h+var_240], rcx
0x18001cb67  mov     dword ptr [rsp+278h+Arguments], ebp
0x18001cb6b  mov     [rsp+278h+nSize], eax
0x18001cb6f  mov     eax, [rbx+44h]
0x18001cb72  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001cb76  mov     r9, rdi; unsigned __int16 *
0x18001cb79  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18001cb80  mov     rdx, rsi; unsigned __int16 *
0x18001cb83  mov     rcx, r14; this
0x18001cb86  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001cb8b  cmp     [rbx+18h], r15
0x18001cb8f  jnz     short loc_18001CBA1
0x18001cb91  cmp     [rbx+48h], r15
0x18001cb95  jnz     short loc_18001CBA1
0x18001cb97  cmp     [rbx+30h], r15
0x18001cb9b  jz      loc_18001CC31
0x18001cba1  lea     r8, asc_1800288F8; "    "
0x18001cba8  mov     rdx, rsi; unsigned __int16 *
0x18001cbab  mov     rcx, rax; this
0x18001cbae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001cbb3  mov     r9, [rbx+18h]; unsigned __int16 *
0x18001cbb7  test    r9, r9
0x18001cbba  jz      short loc_18001CBCE
0x18001cbbc  lea     r8, aMsgWs; "Msg:[%ws] "
0x18001cbc3  mov     rdx, rsi; unsigned __int16 *
0x18001cbc6  mov     rcx, rax; this
0x18001cbc9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001cbce  mov     r9, [rbx+48h]; unsigned __int16 *
0x18001cbd2  test    r9, r9
0x18001cbd5  jz      short loc_18001CBE9
0x18001cbd7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001cbde  mov     rdx, rsi; unsigned __int16 *
0x18001cbe1  mov     rcx, rax; this
0x18001cbe4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001cbe9  mov     rcx, [rbx+28h]
0x18001cbed  mov     r9, [rbx+30h]; unsigned __int16 *
0x18001cbf1  mov     rdx, rsi; unsigned __int16 *
0x18001cbf4  test    rcx, rcx
0x18001cbf7  jz      short loc_18001CC0F
0x18001cbf9  mov     [rsp+278h+lpBuffer], rcx
0x18001cbfe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18001cc05  mov     rcx, rax; this
0x18001cc08  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001cc0d  jmp     short loc_18001CC31
0x18001cc0f  mov     rcx, rax; this
0x18001cc12  test    r9, r9
0x18001cc15  jz      short loc_18001CC25
0x18001cc17  lea     r8, aHs; "[%hs]\n"
0x18001cc1e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001cc23  jmp     short loc_18001CC31
0x18001cc25  lea     r8, asc_180028970; "\n"
0x18001cc2c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001cc31  xor     eax, eax
0x18001cc33  mov     rcx, [rsp+278h+var_38]
0x18001cc3b  xor     rcx, rsp; StackCookie
0x18001cc3e  call    __security_check_cookie
0x18001cc43  mov     rbx, [rsp+278h+arg_18]
0x18001cc4b  add     rsp, 250h
0x18001cc52  pop     r15
0x18001cc54  pop     r14
0x18001cc56  pop     rdi
0x18001cc57  pop     rsi
0x18001cc58  pop     rbp
0x18001cc59  retn
```
