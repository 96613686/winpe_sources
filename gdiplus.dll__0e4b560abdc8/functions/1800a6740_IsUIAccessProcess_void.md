# IsUIAccessProcess(void)

- ea: `0x1800a6740`
- end: `0x1800a67cd`
- name: `?IsUIAccessProcess@@YAHXZ`
- size: `141`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a62e4`

## callees

- `0x1800a6740`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a6759`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a6759`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a6770`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a6770`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a67b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a67b8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a679c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a679c`

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
0x1800a6740  push    rbx
0x1800a6742  sub     rsp, 30h
0x1800a6746  xor     ebx, ebx
0x1800a6748  mov     [rsp+38h+TokenInformationLength], 4
0x1800a6750  mov     [rsp+38h+TokenInformation], ebx
0x1800a6754  mov     [rsp+38h+TokenHandle], rbx
0x1800a6759  call    cs:__imp_GetCurrentProcess
0x1800a6760  nop     dword ptr [rax+rax+00h]
0x1800a6765  mov     rcx, rax; ProcessHandle
0x1800a6768  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1800a676d  lea     edx, [rbx+8]; DesiredAccess
0x1800a6770  call    cs:__imp_OpenProcessToken
0x1800a6777  nop     dword ptr [rax+rax+00h]
0x1800a677c  test    eax, eax
0x1800a677e  jz      short loc_1800A67C4
0x1800a6780  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800a6785  lea     rax, [rsp+38h+TokenInformationLength]
0x1800a678a  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800a678f  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1800a6794  lea     edx, [rbx+1Ah]; TokenInformationClass
0x1800a6797  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800a679c  call    cs:__imp_GetTokenInformation
0x1800a67a3  nop     dword ptr [rax+rax+00h]
0x1800a67a8  test    eax, eax
0x1800a67aa  jz      short loc_1800A67B3
0x1800a67ac  cmp     [rsp+38h+TokenInformation], ebx
0x1800a67b0  setnz   bl
0x1800a67b3  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800a67b8  call    cs:__imp_CloseHandle
0x1800a67bf  nop     dword ptr [rax+rax+00h]
0x1800a67c4  mov     eax, ebx
0x1800a67c6  add     rsp, 30h
0x1800a67ca  pop     rbx
0x1800a67cb  retn
```
