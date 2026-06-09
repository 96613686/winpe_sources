# CommonGetImpersonationToken

- ea: `0x18000e740`
- end: `0x18000e7af`
- name: `CommonGetImpersonationToken`
- size: `111`
- prototype: `__int64 __fastcall(ULONG, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001af6c`

## callees

- `0x18000e740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e78a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e78a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e79c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e79c`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000e780`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000e780`
- `WTSAPI32!WTSQueryUserToken` at `0x18000e75b`
- `WTSAPI32!WTSQueryUserToken` at `0x18000e75b`

## pseudocode

```c
__int64 __fastcall CommonGetImpersonationToken(ULONG a1, void **a2)
{
  DWORD LastError; // ebx
  void *phToken; // [rsp+50h] [rbp+18h] BYREF

  phToken = 0;
  if ( !WTSQueryUserToken(a1, &phToken)
    || (LastError = 0, !DuplicateTokenEx(phToken, 0xEu, 0, SecurityImpersonation, TokenImpersonation, a2)) )
  {
    LastError = GetLastError();
  }
  if ( phToken )
    CloseHandle(phToken);
  return LastError;
}

```

## disassembly

```asm
0x18000e740  mov     [rsp+arg_0], rbx
0x18000e745  push    rdi
0x18000e746  sub     rsp, 30h
0x18000e74a  mov     rdi, rdx
0x18000e74d  mov     [rsp+38h+phToken], 0
0x18000e756  lea     rdx, [rsp+38h+phToken]; phToken
0x18000e75b  call    cs:__imp_WTSQueryUserToken
0x18000e761  test    eax, eax
0x18000e763  jz      short loc_18000E78A
0x18000e765  mov     rcx, [rsp+38h+phToken]; hExistingToken
0x18000e76a  xor     ebx, ebx
0x18000e76c  mov     [rsp+38h+phNewToken], rdi; phNewToken
0x18000e771  xor     r8d, r8d; lpTokenAttributes
0x18000e774  lea     r9d, [rbx+2]; ImpersonationLevel
0x18000e778  lea     edx, [rbx+0Eh]; dwDesiredAccess
0x18000e77b  mov     [rsp+38h+TokenType], r9d; TokenType
0x18000e780  call    cs:__imp_DuplicateTokenEx
0x18000e786  test    eax, eax
0x18000e788  jnz     short loc_18000E792
0x18000e78a  call    cs:__imp_GetLastError
0x18000e790  mov     ebx, eax
0x18000e792  mov     rcx, [rsp+38h+phToken]; hObject
0x18000e797  test    rcx, rcx
0x18000e79a  jz      short loc_18000E7A2
0x18000e79c  call    cs:__imp_CloseHandle
0x18000e7a2  mov     eax, ebx
0x18000e7a4  mov     rbx, [rsp+38h+arg_0]
0x18000e7a9  add     rsp, 30h
0x18000e7ad  pop     rdi
0x18000e7ae  retn
```
