# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000ebd4`
- end: `0x18000ee95`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000d4bc`
- `0x18000f5d4`
- `0x18000fa30`
- `0x180012230`

## callees

- `0x18000be40`
- `0x18000c7e8`
- `0x18000ebd4`
- `0x18000f8dc`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ed92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ed92`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000ed11`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000ed11`

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
  LPWSTR lpBuffer; // [rsp+20h] [rbp-268h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-268h]
  DWORD nSize[2]; // [rsp+28h] [rbp-260h]
  va_list *Arguments; // [rsp+30h] [rbp-258h]
  WCHAR Buffer[256]; // [rsp+50h] [rbp-238h] BYREF

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
          v7 = (const char *)&qword_180025650;
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
                          Buffer,
                          -2);
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
0x18000ebd4  mov     rax, rsp
0x18000ebd7  push    rbp
0x18000ebd8  push    rsi
0x18000ebd9  push    rdi
0x18000ebda  push    r14
0x18000ebdc  push    r15
0x18000ebde  sub     rsp, 260h
0x18000ebe5  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x18000ebee  mov     [rax+20h], rbx
0x18000ebf2  mov     rax, cs:__security_cookie
0x18000ebf9  xor     rax, rsp
0x18000ebfc  mov     [rsp+288h+var_38], rax
0x18000ec04  mov     rbx, r8
0x18000ec07  mov     rsi, rdx
0x18000ec0a  mov     r14, rcx
0x18000ec0d  xor     r15d, r15d
0x18000ec10  test    rdx, rdx
0x18000ec13  jz      loc_18000EE6C
0x18000ec19  test    rcx, rcx
0x18000ec1c  jz      loc_18000EE6C
0x18000ec22  mov     [rcx], r15w
0x18000ec26  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ec2d  test    rax, rax
0x18000ec30  jz      short loc_18000EC53
0x18000ec32  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000ec39  jz      short loc_18000EC53
0x18000ec3b  mov     r8, rdx
0x18000ec3e  mov     rdx, rcx
0x18000ec41  mov     rcx, rbx
0x18000ec44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec49  cmp     [r14], r15w
0x18000ec4d  jnz     loc_18000EE6C
0x18000ec53  mov     ecx, [rbx]
0x18000ec55  mov     bpl, 8
0x18000ec58  test    ecx, ecx
0x18000ec5a  jz      short loc_18000ECA5
0x18000ec5c  sub     ecx, 1
0x18000ec5f  jz      short loc_18000EC8D
0x18000ec61  sub     ecx, 1
0x18000ec64  jz      short loc_18000EC7D
0x18000ec66  cmp     ecx, 1
0x18000ec69  jz      short loc_18000EC74
0x18000ec6b  lea     rdi, qword_180025650
0x18000ec72  jmp     short loc_18000ECAC
0x18000ec74  lea     rdi, aFailfast; "FailFast"
0x18000ec7b  jmp     short loc_18000ECAC
0x18000ec7d  lea     rax, aLoghr; "LogHr"
0x18000ec84  lea     rdi, aLognt; "LogNt"
0x18000ec8b  jmp     short loc_18000EC9B
0x18000ec8d  lea     rax, aReturnhr; "ReturnHr"
0x18000ec94  lea     rdi, aReturnnt; "ReturnNt"
0x18000ec9b  test    [rbx+4], bpl
0x18000ec9f  cmovz   rdi, rax
0x18000eca3  jmp     short loc_18000ECAC
0x18000eca5  lea     rdi, aException; "Exception"
0x18000ecac  xor     edx, edx; Val
0x18000ecae  mov     r8d, 200h; Size
0x18000ecb4  lea     rcx, [rsp+288h+Buffer]; void *
0x18000ecb9  call    memset_0
0x18000ecbe  test    [rbx+4], bpl
0x18000ecc2  jz      short loc_18000ECE7
0x18000ecc4  mov     ebp, [rbx+0Ch]
0x18000ecc7  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000ecce  test    rax, rax
0x18000ecd1  jz      short loc_18000ED17
0x18000ecd3  mov     r8d, 100h
0x18000ecd9  lea     rdx, [rsp+288h+Buffer]
0x18000ecde  mov     ecx, ebp
0x18000ece0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ece5  jmp     short loc_18000ED17
0x18000ece7  mov     ebp, [rbx+8]
0x18000ecea  mov     [rsp+288h+Arguments], r15; Arguments
0x18000ecef  mov     [rsp+288h+nSize], 100h; nSize
0x18000ecf7  lea     rax, [rsp+288h+Buffer]
0x18000ecfc  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x18000ed01  mov     r9d, 400h; dwLanguageId
0x18000ed07  mov     r8d, ebp; dwMessageId
0x18000ed0a  xor     edx, edx; lpSource
0x18000ed0c  mov     ecx, 1200h; dwFlags
0x18000ed11  call    cs:__imp_FormatMessageW
0x18000ed17  lea     rsi, [r14+rsi*2]
0x18000ed1b  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000ed1f  mov     rax, [rbx+88h]
0x18000ed26  mov     rcx, [rbx+80h]
0x18000ed2d  mov     rdx, rsi; unsigned __int16 *
0x18000ed30  test    r9, r9
0x18000ed33  jz      short loc_18000ED57
0x18000ed35  mov     [rsp+288h+Arguments], rax
0x18000ed3a  mov     qword ptr [rsp+288h+nSize], rcx
0x18000ed3f  mov     eax, [rbx+40h]
0x18000ed42  mov     dword ptr [rsp+288h+lpBuffer], eax
0x18000ed46  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000ed4d  mov     rcx, r14; this
0x18000ed50  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ed55  jmp     short loc_18000ED6E
0x18000ed57  mov     [rsp+288h+lpBuffer], rax
0x18000ed5c  mov     r9, rcx; unsigned __int16 *
0x18000ed5f  lea     r8, aHsP; "%hs!%p: "
0x18000ed66  mov     rcx, r14; this
0x18000ed69  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ed6e  mov     r14, rax
0x18000ed71  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000ed78  test    r9, r9
0x18000ed7b  jz      short loc_18000ED92
0x18000ed7d  lea     r8, aCallerP; "(caller: %p) "
0x18000ed84  mov     rdx, rsi; unsigned __int16 *
0x18000ed87  mov     rcx, rax; this
0x18000ed8a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ed8f  mov     r14, rax
0x18000ed92  call    cs:__imp_GetCurrentThreadId
0x18000ed98  lea     rcx, [rsp+288h+Buffer]
0x18000ed9d  mov     [rsp+288h+var_250], rcx
0x18000eda2  mov     dword ptr [rsp+288h+Arguments], ebp
0x18000eda6  mov     [rsp+288h+nSize], eax
0x18000edaa  mov     eax, [rbx+44h]
0x18000edad  mov     dword ptr [rsp+288h+lpBuffer], eax
0x18000edb1  mov     r9, rdi; unsigned __int16 *
0x18000edb4  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000edbb  mov     rdx, rsi; unsigned __int16 *
0x18000edbe  mov     rcx, r14; this
0x18000edc1  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000edc6  cmp     [rbx+18h], r15
0x18000edca  jnz     short loc_18000EDDC
0x18000edcc  cmp     [rbx+48h], r15
0x18000edd0  jnz     short loc_18000EDDC
0x18000edd2  cmp     [rbx+30h], r15
0x18000edd6  jz      loc_18000EE6C
0x18000eddc  lea     r8, asc_180025758; "    "
0x18000ede3  mov     rdx, rsi; unsigned __int16 *
0x18000ede6  mov     rcx, rax; this
0x18000ede9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000edee  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000edf2  test    r9, r9
0x18000edf5  jz      short loc_18000EE09
0x18000edf7  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000edfe  mov     rdx, rsi; unsigned __int16 *
0x18000ee01  mov     rcx, rax; this
0x18000ee04  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ee09  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000ee0d  test    r9, r9
0x18000ee10  jz      short loc_18000EE24
0x18000ee12  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000ee19  mov     rdx, rsi; unsigned __int16 *
0x18000ee1c  mov     rcx, rax; this
0x18000ee1f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ee24  mov     rcx, [rbx+28h]
0x18000ee28  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000ee2c  mov     rdx, rsi; unsigned __int16 *
0x18000ee2f  test    rcx, rcx
0x18000ee32  jz      short loc_18000EE4A
0x18000ee34  mov     [rsp+288h+lpBuffer], rcx
0x18000ee39  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000ee40  mov     rcx, rax; this
0x18000ee43  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ee48  jmp     short loc_18000EE6C
0x18000ee4a  mov     rcx, rax; this
0x18000ee4d  test    r9, r9
0x18000ee50  jz      short loc_18000EE60
0x18000ee52  lea     r8, aHs; "[%hs]\n"
0x18000ee59  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ee5e  jmp     short loc_18000EE6C
0x18000ee60  lea     r8, asc_1800257D0; "\n"
0x18000ee67  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ee6c  xor     eax, eax
0x18000ee6e  mov     rcx, [rsp+288h+var_38]
0x18000ee76  xor     rcx, rsp; StackCookie
0x18000ee79  call    __security_check_cookie
0x18000ee7e  mov     rbx, [rsp+288h+arg_18]
0x18000ee86  add     rsp, 260h
0x18000ee8d  pop     r15
0x18000ee8f  pop     r14
0x18000ee91  pop     rdi
0x18000ee92  pop     rsi
0x18000ee93  pop     rbp
0x18000ee94  retn
```
