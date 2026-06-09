# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x14002ade4`
- end: `0x14002b0a5`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14002c55c`

## callees

- `0x14002ade4`
- `0x14002c868`
- `0x14005ce3a`
- `0x14005ce70`
- `0x14005e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002af9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002af9b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14002af14`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14002af14`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        STRSAFE_LPWSTR pszDest,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, STRSAFE_LPWSTR, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rsi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rdi
  __int64 v13; // rax
  wchar_t *v14; // rax
  const unsigned __int16 *v15; // r9
  wchar_t *v16; // r14
  wchar_t *v17; // rax
  const unsigned __int16 *v18; // r9
  wchar_t *v19; // rax
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
  if ( !pszDest )
    return 0;
  v7 = (void (__fastcall *)(__int64, STRSAFE_LPWSTR, unsigned __int16 *, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
  *pszDest = 0;
  if ( v7 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      v7(a3, pszDest, a2, a4);
      if ( *pszDest )
        return 0;
    }
  }
  v8 = (const char *)&qword_140064C70;
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
        goto LABEL_17;
      }
      v9 = "LogHr";
      v8 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v8 = v9;
    goto LABEL_17;
  }
  v8 = "Exception";
LABEL_17:
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
  v12 = &pszDest[(_QWORD)a2];
  v13 = *(_QWORD *)(a3 + 136);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(pszDest, v12, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, *(_QWORD *)(a3 + 128), v13);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(pszDest, v12, L"%hs!%p: ", *(const unsigned __int16 **)(a3 + 128), v13);
  }
  v15 = *(const unsigned __int16 **)(a3 + 144);
  v16 = v14;
  if ( v15 )
    v16 = wil::details::LogStringPrintf(v14, v12, L"(caller: %p) ", v15);
  LODWORD(Arguments) = v10;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = wil::details::LogStringPrintf(
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
      v19 = wil::details::LogStringPrintf(v19, v12, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf(v19, v12, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf(v19, v12, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf(v19, v12, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf(v19, v12, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14002ade4  mov     [rsp+arg_18], rbx
0x14002ade9  push    rbp
0x14002adea  push    rsi
0x14002adeb  push    rdi
0x14002adec  push    r14
0x14002adee  push    r15
0x14002adf0  sub     rsp, 250h
0x14002adf7  mov     rax, cs:__security_cookie
0x14002adfe  xor     rax, rsp
0x14002ae01  mov     [rsp+278h+var_38], rax
0x14002ae09  xor     r15d, r15d
0x14002ae0c  mov     rbx, r8
0x14002ae0f  mov     rdi, rdx
0x14002ae12  mov     r14, rcx
0x14002ae15  test    rdx, rdx
0x14002ae18  jz      loc_14002B07B
0x14002ae1e  test    rcx, rcx
0x14002ae21  jz      loc_14002B07B
0x14002ae27  mov     rax, cs:g_pfnResultLoggingCallback
0x14002ae2e  mov     [rcx], r15w
0x14002ae32  test    rax, rax
0x14002ae35  jz      short loc_14002AE58
0x14002ae37  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14002ae3e  jz      short loc_14002AE58
0x14002ae40  mov     r8, rdx
0x14002ae43  mov     rdx, rcx
0x14002ae46  mov     rcx, rbx
0x14002ae49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ae4e  cmp     [r14], r15w
0x14002ae52  jnz     loc_14002B07B
0x14002ae58  mov     ecx, [rbx]
0x14002ae5a  lea     rsi, qword_140064C70
0x14002ae61  mov     bpl, 8
0x14002ae64  test    ecx, ecx
0x14002ae66  jz      short loc_14002AEA8
0x14002ae68  sub     ecx, 1
0x14002ae6b  jz      short loc_14002AE90
0x14002ae6d  sub     ecx, 1
0x14002ae70  jz      short loc_14002AE80
0x14002ae72  cmp     ecx, 1
0x14002ae75  jnz     short loc_14002AEAF
0x14002ae77  lea     rsi, aFailfast; "FailFast"
0x14002ae7e  jmp     short loc_14002AEAF
0x14002ae80  lea     rax, aLoghr; "LogHr"
0x14002ae87  lea     rsi, aLognt; "LogNt"
0x14002ae8e  jmp     short loc_14002AE9E
0x14002ae90  lea     rax, aReturnhr; "ReturnHr"
0x14002ae97  lea     rsi, aReturnnt; "ReturnNt"
0x14002ae9e  test    [rbx+4], bpl
0x14002aea2  cmovz   rsi, rax
0x14002aea6  jmp     short loc_14002AEAF
0x14002aea8  lea     rsi, aException; "Exception"
0x14002aeaf  xor     edx, edx; Val
0x14002aeb1  lea     rcx, [rsp+278h+Buffer]; void *
0x14002aeb6  mov     r8d, 200h; Size
0x14002aebc  call    memset_0
0x14002aec1  test    [rbx+4], bpl
0x14002aec5  jz      short loc_14002AEEA
0x14002aec7  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x14002aece  mov     ebp, [rbx+0Ch]
0x14002aed1  test    rax, rax
0x14002aed4  jz      short loc_14002AF20
0x14002aed6  mov     r8d, 100h
0x14002aedc  lea     rdx, [rsp+278h+Buffer]
0x14002aee1  mov     ecx, ebp
0x14002aee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002aee8  jmp     short loc_14002AF20
0x14002aeea  mov     ebp, [rbx+8]
0x14002aeed  lea     rax, [rsp+278h+Buffer]
0x14002aef2  mov     [rsp+278h+Arguments], r15; Arguments
0x14002aef7  mov     r8d, ebp; dwMessageId
0x14002aefa  mov     [rsp+278h+nSize], 100h; nSize
0x14002af02  mov     r9d, 400h; dwLanguageId
0x14002af08  xor     edx, edx; lpSource
0x14002af0a  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x14002af0f  mov     ecx, 1200h; dwFlags
0x14002af14  call    cs:__imp_FormatMessageW
0x14002af1b  nop     dword ptr [rax+rax+00h]
0x14002af20  mov     r9, [rbx+38h]; unsigned __int16 *
0x14002af24  lea     rdi, [r14+rdi*2]
0x14002af28  mov     rax, [rbx+88h]
0x14002af2f  mov     rdx, rdi; unsigned __int16 *
0x14002af32  mov     rcx, [rbx+80h]
0x14002af39  test    r9, r9
0x14002af3c  jz      short loc_14002AF60
0x14002af3e  mov     [rsp+278h+Arguments], rax
0x14002af43  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x14002af4a  mov     eax, [rbx+40h]
0x14002af4d  mov     qword ptr [rsp+278h+nSize], rcx
0x14002af52  mov     rcx, r14; pszDest
0x14002af55  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14002af59  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14002af5e  jmp     short loc_14002AF77
0x14002af60  mov     r9, rcx; unsigned __int16 *
0x14002af63  mov     [rsp+278h+lpBuffer], rax
0x14002af68  mov     rcx, r14; pszDest
0x14002af6b  lea     r8, aHsP; "%hs!%p: "
0x14002af72  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14002af77  mov     r9, [rbx+90h]; unsigned __int16 *
0x14002af7e  mov     r14, rax
0x14002af81  test    r9, r9
0x14002af84  jz      short loc_14002AF9B
0x14002af86  lea     r8, aCallerP; "(caller: %p) "
0x14002af8d  mov     rdx, rdi; unsigned __int16 *
0x14002af90  mov     rcx, rax; pszDest
0x14002af93  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14002af98  mov     r14, rax
0x14002af9b  call    cs:__imp_GetCurrentThreadId
0x14002afa2  nop     dword ptr [rax+rax+00h]
0x14002afa7  mov     ecx, [rbx+44h]
0x14002afaa  lea     rdx, [rsp+278h+Buffer]
0x14002afaf  mov     [rsp+278h+var_240], rdx
0x14002afb4  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x14002afbb  mov     dword ptr [rsp+278h+Arguments], ebp
0x14002afbf  mov     r9, rsi; unsigned __int16 *
0x14002afc2  mov     [rsp+278h+nSize], eax
0x14002afc6  mov     rdx, rdi; unsigned __int16 *
0x14002afc9  mov     dword ptr [rsp+278h+lpBuffer], ecx
0x14002afcd  mov     rcx, r14; pszDest
0x14002afd0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14002afd5  cmp     [rbx+18h], r15
0x14002afd9  jnz     short loc_14002AFEB
0x14002afdb  cmp     [rbx+48h], r15
0x14002afdf  jnz     short loc_14002AFEB
0x14002afe1  cmp     [rbx+30h], r15
0x14002afe5  jz      loc_14002B07B
0x14002afeb  lea     r8, asc_140064540; "    "
0x14002aff2  mov     rdx, rdi; unsigned __int16 *
0x14002aff5  mov     rcx, rax; pszDest
0x14002aff8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14002affd  mov     r9, [rbx+18h]; unsigned __int16 *
0x14002b001  test    r9, r9
0x14002b004  jz      short loc_14002B018
0x14002b006  lea     r8, aMsgWs; "Msg:[%ws] "
0x14002b00d  mov     rdx, rdi; unsigned __int16 *
0x14002b010  mov     rcx, rax; pszDest
0x14002b013  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14002b018  mov     r9, [rbx+48h]; unsigned __int16 *
0x14002b01c  test    r9, r9
0x14002b01f  jz      short loc_14002B033
0x14002b021  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14002b028  mov     rdx, rdi; unsigned __int16 *
0x14002b02b  mov     rcx, rax; pszDest
0x14002b02e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14002b033  mov     rcx, [rbx+28h]
0x14002b037  mov     rdx, rdi; unsigned __int16 *
0x14002b03a  mov     r9, [rbx+30h]; unsigned __int16 *
0x14002b03e  test    rcx, rcx
0x14002b041  jz      short loc_14002B059
0x14002b043  mov     [rsp+278h+lpBuffer], rcx
0x14002b048  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x14002b04f  mov     rcx, rax; pszDest
0x14002b052  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14002b057  jmp     short loc_14002B07B
0x14002b059  mov     rcx, rax; pszDest
0x14002b05c  test    r9, r9
0x14002b05f  jz      short loc_14002B06F
0x14002b061  lea     r8, aHs; "[%hs]\n"
0x14002b068  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14002b06d  jmp     short loc_14002B07B
0x14002b06f  lea     r8, asc_140064850; "\n"
0x14002b076  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14002b07b  xor     eax, eax
0x14002b07d  mov     rcx, [rsp+278h+var_38]
0x14002b085  xor     rcx, rsp; StackCookie
0x14002b088  call    __security_check_cookie
0x14002b08d  mov     rbx, [rsp+278h+arg_18]
0x14002b095  add     rsp, 250h
0x14002b09c  pop     r15
0x14002b09e  pop     r14
0x14002b0a0  pop     rdi
0x14002b0a1  pop     rsi
0x14002b0a2  pop     rbp
0x14002b0a3  retn
```
