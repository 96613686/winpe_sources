# QueryProcessIntegrityLevel(void)

- ea: `0x180022770`
- end: `0x180022864`
- name: `?QueryProcessIntegrityLevel@@YAJXZ`
- size: `244`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800224a8`

## callees

- `0x180022770`
- `0x18002286c`
- `0x18002c4c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800227b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800227b5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800227ab`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800227ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022793`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022793`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800227e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800227e8`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180022833`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180022833`

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
0x180022770  mov     [rsp-8+arg_0], rbx
0x180022775  mov     [rsp-8+arg_8], rdi
0x18002277a  push    rbp
0x18002277b  mov     rbp, rsp
0x18002277e  sub     rsp, 80h
0x180022785  mov     rax, cs:__security_cookie
0x18002278c  xor     rax, rsp
0x18002278f  mov     [rbp+var_10], rax
0x180022793  call    cs:__imp_GetCurrentProcess
0x180022799  xor     edi, edi
0x18002279b  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18002279f  mov     rcx, rax; ProcessHandle
0x1800227a2  mov     [rbp+TokenHandle], rdi
0x1800227a6  mov     edx, 20008h; DesiredAccess
0x1800227ab  call    cs:__imp_OpenProcessToken
0x1800227b1  test    eax, eax
0x1800227b3  jnz     short loc_1800227CD
0x1800227b5  call    cs:__imp_GetLastError
0x1800227bb  test    eax, eax
0x1800227bd  jle     loc_180022843
0x1800227c3  movzx   eax, ax
0x1800227c6  or      eax, 80070000h
0x1800227cb  jmp     short loc_180022843
0x1800227cd  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800227d1  lea     rdx, [rbp+pIdentifierAuthority]; unsigned int *
0x1800227d5  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x1800227d8  call    ?QueryTokenIntegrityLevel@@YAJPEAXPEAK@Z; QueryTokenIntegrityLevel(void *,ulong *)
0x1800227dd  mov     rcx, [rbp+TokenHandle]; hObject
0x1800227e1  mov     ebx, eax
0x1800227e3  test    rcx, rcx
0x1800227e6  jz      short loc_1800227EE
0x1800227e8  call    cs:__imp_CloseHandle
0x1800227ee  test    ebx, ebx
0x1800227f0  js      short loc_180022841
0x1800227f2  mov     r8d, dword ptr [rbp+pIdentifierAuthority.Value]; nSubAuthority0
0x1800227f6  lea     rax, ?g_pTokenIntegritySid@@3PEAXEA; void * g_pTokenIntegritySid
0x1800227fd  mov     [rsp+80h+pSid], rax; pSid
0x180022802  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180022806  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x18002280a  xor     r9d, r9d; nSubAuthority1
0x18002280d  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x180022811  mov     dl, 1; nSubAuthorityCount
0x180022813  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x180022817  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x18002281b  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x18002281f  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x180022823  mov     cs:?g_dwProcessIntegrityRid@@3KA, r8d; ulong g_dwProcessIntegrityRid
0x18002282a  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x18002282d  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 1000h
0x180022833  call    cs:__imp_AllocateAndInitializeSid
0x180022839  test    eax, eax
0x18002283b  jz      loc_1800227B5
0x180022841  mov     eax, ebx
0x180022843  mov     rcx, [rbp+var_10]
0x180022847  xor     rcx, rsp; StackCookie
0x18002284a  call    __security_check_cookie
0x18002284f  lea     r11, [rsp+80h+var_s0]
0x180022857  mov     rbx, [r11+10h]
0x18002285b  mov     rdi, [r11+18h]
0x18002285f  mov     rsp, r11
0x180022862  pop     rbp
0x180022863  retn
```
