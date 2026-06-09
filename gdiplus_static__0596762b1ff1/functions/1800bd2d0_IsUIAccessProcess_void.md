# IsUIAccessProcess(void)

- ea: `0x1800bd2d0`
- end: `0x1800bd35d`
- name: `?IsUIAccessProcess@@YAHXZ`
- size: `141`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800bce0c`

## callees

- `0x1800bd2d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800bd300`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800bd300`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800bd2e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800bd2e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd348`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd348`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800bd32c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800bd32c`

## pseudocode

```c
__int64 IsUIAccessProcess(void)
{
  unsigned int v0; // ebx
  HANDLE CurrentProcess; // rax
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF
  int TokenInformation; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  v0 = 0;
  TokenInformationLength = 4;
  TokenInformation = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    if ( GetTokenInformation(
           TokenHandle,
           TokenUIAccess,
           &TokenInformation,
           TokenInformationLength,
           &TokenInformationLength) )
    {
      LOBYTE(v0) = TokenInformation != 0;
    }
    CloseHandle(TokenHandle);
  }
  return v0;
}

```

## disassembly

```asm
0x1800bd2d0  push    rbx
0x1800bd2d2  sub     rsp, 30h
0x1800bd2d6  xor     ebx, ebx
0x1800bd2d8  mov     [rsp+38h+TokenInformationLength], 4
0x1800bd2e0  mov     [rsp+38h+TokenInformation], ebx
0x1800bd2e4  mov     [rsp+38h+TokenHandle], rbx
0x1800bd2e9  call    cs:__imp_GetCurrentProcess
0x1800bd2f0  nop     dword ptr [rax+rax+00h]
0x1800bd2f5  mov     rcx, rax; ProcessHandle
0x1800bd2f8  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1800bd2fd  lea     edx, [rbx+8]; DesiredAccess
0x1800bd300  call    cs:__imp_OpenProcessToken
0x1800bd307  nop     dword ptr [rax+rax+00h]
0x1800bd30c  test    eax, eax
0x1800bd30e  jz      short loc_1800BD354
0x1800bd310  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800bd315  lea     rax, [rsp+38h+TokenInformationLength]
0x1800bd31a  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800bd31f  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1800bd324  lea     edx, [rbx+1Ah]; TokenInformationClass
0x1800bd327  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800bd32c  call    cs:__imp_GetTokenInformation
0x1800bd333  nop     dword ptr [rax+rax+00h]
0x1800bd338  test    eax, eax
0x1800bd33a  jz      short loc_1800BD343
0x1800bd33c  cmp     [rsp+38h+TokenInformation], ebx
0x1800bd340  setnz   bl
0x1800bd343  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800bd348  call    cs:__imp_CloseHandle
0x1800bd34f  nop     dword ptr [rax+rax+00h]
0x1800bd354  mov     eax, ebx
0x1800bd356  add     rsp, 30h
0x1800bd35a  pop     rbx
0x1800bd35b  retn
```
