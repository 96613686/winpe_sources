# QueryProcessIntegrityLevel(void)

- ea: `0x180023f3c`
- end: `0x180024052`
- name: `?QueryProcessIntegrityLevel@@YAJXZ`
- size: `278`
- prototype: `signed int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023c24`

## callees

- `0x180023f3c`
- `0x180024058`
- `0x18002e560`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f8d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180023f7d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180023f7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023f5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023f5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023fc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023fc9`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002401a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002401a`

## pseudocode

```c
signed int QueryProcessIntegrityLevel(void)
{
  HANDLE CurrentProcess; // rax
  signed int result; // eax
  int TokenIntegrityLevel; // ebx
  DWORD v3; // r8d
  void *TokenHandle; // [rsp+60h] [rbp-20h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-18h] BYREF

  CurrentProcess = GetCurrentProcess();
  TokenHandle = 0;
  if ( OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
  {
    *(_DWORD *)pIdentifierAuthority.Value = 0;
    TokenIntegrityLevel = QueryTokenIntegrityLevel(TokenHandle, (unsigned int *)pIdentifierAuthority.Value);
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    if ( TokenIntegrityLevel < 0 )
      return TokenIntegrityLevel;
    v3 = *(_DWORD *)pIdentifierAuthority.Value;
    g_dwProcessIntegrityRid = *(_DWORD *)pIdentifierAuthority.Value;
    *(_DWORD *)pIdentifierAuthority.Value = 0;
    *(_WORD *)&pIdentifierAuthority.Value[4] = 4096;
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, v3, 0, 0, 0, 0, 0, 0, 0, &g_pTokenIntegritySid) )
      return TokenIntegrityLevel;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180023f3c  mov     [rsp-8+arg_0], rbx
0x180023f41  mov     [rsp-8+arg_8], rdi
0x180023f46  push    rbp
0x180023f47  mov     rbp, rsp
0x180023f4a  sub     rsp, 80h
0x180023f51  mov     rax, cs:__security_cookie
0x180023f58  xor     rax, rsp
0x180023f5b  mov     [rbp+var_10], rax
0x180023f5f  call    cs:__imp_GetCurrentProcess
0x180023f66  nop     dword ptr [rax+rax+00h]
0x180023f6b  xor     edi, edi
0x180023f6d  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180023f71  mov     rcx, rax; ProcessHandle
0x180023f74  mov     [rbp+TokenHandle], rdi
0x180023f78  mov     edx, 20008h; DesiredAccess
0x180023f7d  call    cs:__imp_OpenProcessToken
0x180023f84  nop     dword ptr [rax+rax+00h]
0x180023f89  test    eax, eax
0x180023f8b  jnz     short loc_180023FAE
0x180023f8d  call    cs:__imp_GetLastError
0x180023f94  nop     dword ptr [rax+rax+00h]
0x180023f99  test    eax, eax
0x180023f9b  jle     loc_180024030
0x180023fa1  movzx   eax, ax
0x180023fa4  or      eax, 80070000h
0x180023fa9  jmp     loc_180024030
0x180023fae  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180023fb2  lea     rdx, [rbp+pIdentifierAuthority]; unsigned int *
0x180023fb6  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x180023fb9  call    ?QueryTokenIntegrityLevel@@YAJPEAXPEAK@Z; QueryTokenIntegrityLevel(void *,ulong *)
0x180023fbe  mov     rcx, [rbp+TokenHandle]; hObject
0x180023fc2  mov     ebx, eax
0x180023fc4  test    rcx, rcx
0x180023fc7  jz      short loc_180023FD5
0x180023fc9  call    cs:__imp_CloseHandle
0x180023fd0  nop     dword ptr [rax+rax+00h]
0x180023fd5  test    ebx, ebx
0x180023fd7  js      short loc_18002402E
0x180023fd9  mov     r8d, dword ptr [rbp+pIdentifierAuthority.Value]; nSubAuthority0
0x180023fdd  lea     rax, ?g_pTokenIntegritySid@@3PEAXEA; void * g_pTokenIntegritySid
0x180023fe4  mov     [rsp+80h+pSid], rax; pSid
0x180023fe9  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180023fed  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x180023ff1  xor     r9d, r9d; nSubAuthority1
0x180023ff4  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x180023ff8  mov     dl, 1; nSubAuthorityCount
0x180023ffa  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x180023ffe  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x180024002  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x180024006  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x18002400a  mov     cs:?g_dwProcessIntegrityRid@@3KA, r8d; ulong g_dwProcessIntegrityRid
0x180024011  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x180024014  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 1000h
0x18002401a  call    cs:__imp_AllocateAndInitializeSid
0x180024021  nop     dword ptr [rax+rax+00h]
0x180024026  test    eax, eax
0x180024028  jz      loc_180023F8D
0x18002402e  mov     eax, ebx
0x180024030  mov     rcx, [rbp+var_10]
0x180024034  xor     rcx, rsp; StackCookie
0x180024037  call    __security_check_cookie
0x18002403c  lea     r11, [rsp+80h+var_s0]
0x180024044  mov     rbx, [r11+10h]
0x180024048  mov     rdi, [r11+18h]
0x18002404c  mov     rsp, r11
0x18002404f  pop     rbp
0x180024050  retn
```
