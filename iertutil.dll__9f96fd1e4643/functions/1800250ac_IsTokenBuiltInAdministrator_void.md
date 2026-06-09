# IsTokenBuiltInAdministrator(void)

- ea: `0x1800250ac`
- end: `0x18002516c`
- name: `?IsTokenBuiltInAdministrator@@YAHXZ`
- size: `192`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023d98`
- `0x180064f64`

## callees

- `0x1800250ac`
- `0x180083c10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800250d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800250d6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800250e7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800250e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002511d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002511d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002514b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002514b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002515b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002515b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002510e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002510e`

## pseudocode

```c
_BOOL8 IsTokenBuiltInAdministrator(void)
{
  BOOL v0; // ebx
  HANDLE CurrentProcess; // rax
  PUCHAR SidSubAuthorityCount; // rax
  DWORD ReturnLength; // [rsp+30h] [rbp-88h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-80h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-78h] BYREF

  v0 = 0;
  ReturnLength = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength) )
    {
      SidSubAuthorityCount = GetSidSubAuthorityCount(TokenInformation[0]);
      v0 = *GetSidSubAuthority(TokenInformation[0], (unsigned int)*SidSubAuthorityCount - 1) == 500;
    }
    CloseHandle(TokenHandle);
  }
  return v0;
}

```

## disassembly

```asm
0x1800250ac  mov     [rsp+arg_0], rbx
0x1800250b1  push    rdi
0x1800250b2  sub     rsp, 0B0h
0x1800250b9  mov     rax, cs:__security_cookie
0x1800250c0  xor     rax, rsp
0x1800250c3  mov     [rsp+0B8h+var_18], rax
0x1800250cb  xor     ebx, ebx
0x1800250cd  mov     [rsp+0B8h+var_88], ebx
0x1800250d1  mov     [rsp+0B8h+TokenHandle], rbx
0x1800250d6  call    cs:__imp_GetCurrentProcess
0x1800250dc  mov     rcx, rax; ProcessHandle
0x1800250df  lea     r8, [rsp+0B8h+TokenHandle]; TokenHandle
0x1800250e4  lea     edx, [rbx+8]; DesiredAccess
0x1800250e7  call    cs:__imp_OpenProcessToken
0x1800250ed  test    eax, eax
0x1800250ef  jz      short loc_180025123
0x1800250f1  mov     rcx, [rsp+0B8h+TokenHandle]; TokenHandle
0x1800250f6  lea     rax, [rsp+0B8h+var_88]
0x1800250fb  lea     edi, [rbx+1]
0x1800250fe  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x180025103  mov     edx, edi; TokenInformationClass
0x180025105  lea     r9d, [rbx+58h]; TokenInformationLength
0x180025109  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x18002510e  call    cs:__imp_GetTokenInformation
0x180025114  test    eax, eax
0x180025116  jnz     short loc_180025146
0x180025118  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x18002511d  call    cs:__imp_CloseHandle
0x180025123  mov     eax, ebx
0x180025125  mov     rcx, [rsp+0B8h+var_18]
0x18002512d  xor     rcx, rsp; StackCookie
0x180025130  call    __security_check_cookie
0x180025135  mov     rbx, [rsp+0B8h+arg_0]
0x18002513d  add     rsp, 0B0h
0x180025144  pop     rdi
0x180025145  retn
0x180025146  mov     rcx, [rsp+0B8h+TokenInformation]; pSid
0x18002514b  call    cs:__imp_GetSidSubAuthorityCount
0x180025151  mov     rcx, [rsp+0B8h+TokenInformation]; pSid
0x180025156  movzx   edx, byte ptr [rax]
0x180025159  sub     edx, edi; nSubAuthority
0x18002515b  call    cs:__imp_GetSidSubAuthority
0x180025161  cmp     dword ptr [rax], 1F4h
0x180025167  cmovz   ebx, edi
0x18002516a  jmp     short loc_180025118
```
