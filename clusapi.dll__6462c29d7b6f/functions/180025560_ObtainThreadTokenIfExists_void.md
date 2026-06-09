# ObtainThreadTokenIfExists(void * *)

- ea: `0x180025560`
- end: `0x180025647`
- name: `?ObtainThreadTokenIfExists@@YAKPEAPEAX@Z`
- size: `231`
- prototype: `unsigned int __fastcall(PHANDLE DuplicateTokenHandle)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022508`
- `0x180025650`
- `0x180026f30`

## callees

- `0x180025560`
- `0x18006f910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002559a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800255f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002559a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800255f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002557b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002557b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180025590`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180025590`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002562f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002562f`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800255e9`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800255e9`

## string_xrefs

- `0x1800255b9`: `Handle Impersonation - Failed to obtain thread token for handle - %d`
- `0x1800255c6`: `ObtainThreadTokenIfExists`
- `0x180025604`: `ObtainThreadTokenIfExists`
- `0x18002560b`: `Handle Impersonation - Failed to duplicate the token - %d`

## pseudocode

```c
__int64 __fastcall ObtainThreadTokenIfExists(PHANDLE DuplicateTokenHandle)
{
  HANDLE CurrentThread; // rax
  DWORD v3; // eax
  DWORD LastError; // ebx
  void *TokenHandle; // [rsp+48h] [rbp+10h] BYREF

  TokenHandle = (void *)-1LL;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 6u, 1, &TokenHandle) )
  {
    LastError = 0;
    if ( !DuplicateToken(TokenHandle, SecurityImpersonation, DuplicateTokenHandle) )
    {
      *DuplicateTokenHandle = (void *)-1LL;
      LastError = GetLastError();
      TraceMsg(
        2,
        0,
        L"ObtainThreadTokenIfExists",
        8683,
        L"Handle Impersonation - Failed to duplicate the token - %d",
        LastError);
    }
    if ( TokenHandle != (void *)-1LL )
      CloseHandle(TokenHandle);
  }
  else
  {
    v3 = GetLastError();
    *DuplicateTokenHandle = (void *)-1LL;
    LastError = v3;
    if ( v3 == 1008 )
      return 0;
    TraceMsg(
      2,
      0,
      L"ObtainThreadTokenIfExists",
      8674,
      L"Handle Impersonation - Failed to obtain thread token for handle - %d",
      v3);
  }
  return LastError;
}

```

## disassembly

```asm
0x180025560  mov     [rsp+arg_0], rbx
0x180025565  mov     [rsp+arg_10], rsi
0x18002556a  push    rdi
0x18002556b  sub     rsp, 30h
0x18002556f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180025573  mov     rdi, rcx
0x180025576  mov     [rsp+38h+TokenHandle], rsi
0x18002557b  call    cs:__imp_GetCurrentThread
0x180025581  mov     rcx, rax; ThreadHandle
0x180025584  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180025589  lea     edx, [rsi+7]; DesiredAccess
0x18002558c  lea     r8d, [rsi+2]; OpenAsSelf
0x180025590  call    cs:__imp_OpenThreadToken
0x180025596  test    eax, eax
0x180025598  jnz     short loc_1800255DC
0x18002559a  call    cs:__imp_GetLastError
0x1800255a0  mov     [rdi], rsi
0x1800255a3  mov     ebx, eax
0x1800255a5  cmp     eax, 3F0h
0x1800255aa  jnz     short loc_1800255B3
0x1800255ac  xor     eax, eax
0x1800255ae  jmp     loc_180025637
0x1800255b3  xor     edx, edx
0x1800255b5  mov     [rsp+38h+var_10], ebx
0x1800255b9  lea     rax, aHandleImperson_3; "Handle Impersonation - Failed to obtain"...
0x1800255c0  mov     r9d, 21E2h
0x1800255c6  lea     r8, aObtainthreadto; "ObtainThreadTokenIfExists"
0x1800255cd  mov     [rsp+38h+var_18], rax
0x1800255d2  lea     ecx, [rdx+2]
0x1800255d5  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800255da  jmp     short loc_180025635
0x1800255dc  mov     rcx, [rsp+38h+TokenHandle]; ExistingTokenHandle
0x1800255e1  xor     ebx, ebx
0x1800255e3  mov     r8, rdi; DuplicateTokenHandle
0x1800255e6  lea     edx, [rbx+2]; ImpersonationLevel
0x1800255e9  call    cs:__imp_DuplicateToken
0x1800255ef  test    eax, eax
0x1800255f1  jnz     short loc_180025625
0x1800255f3  mov     [rdi], rsi
0x1800255f6  call    cs:__imp_GetLastError
0x1800255fc  mov     [rsp+38h+var_10], eax
0x180025600  xor     edx, edx
0x180025602  mov     ebx, eax
0x180025604  lea     r8, aObtainthreadto; "ObtainThreadTokenIfExists"
0x18002560b  lea     rax, aHandleImperson_4; "Handle Impersonation - Failed to duplic"...
0x180025612  mov     r9d, 21EBh
0x180025618  mov     [rsp+38h+var_18], rax
0x18002561d  lea     ecx, [rdx+2]
0x180025620  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180025625  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18002562a  cmp     rcx, rsi
0x18002562d  jz      short loc_180025635
0x18002562f  call    cs:__imp_CloseHandle
0x180025635  mov     eax, ebx
0x180025637  mov     rbx, [rsp+38h+arg_0]
0x18002563c  mov     rsi, [rsp+38h+arg_10]
0x180025641  add     rsp, 30h
0x180025645  pop     rdi
0x180025646  retn
```
