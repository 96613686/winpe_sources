# IsClientAppContainer(void)

- ea: `0x180018b04`
- end: `0x180018bb4`
- name: `?IsClientAppContainer@@YAHXZ`
- size: `176`
- prototype: `_BOOL8(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e574`
- `0x1800188d8`

## callees

- `0x180018b04`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x180018b8e`
- `ADVAPI32!GetTokenInformation` at `0x180018b8e`
- `ADVAPI32!OpenThreadToken` at `0x180018b2c`
- `ADVAPI32!OpenThreadToken` at `0x180018b2c`
- `ADVAPI32!OpenProcessToken` at `0x180018b47`
- `ADVAPI32!OpenProcessToken` at `0x180018b47`
- `KERNEL32!GetLastError` at `0x180018b51`
- `KERNEL32!GetLastError` at `0x180018b51`
- `KERNEL32!CloseHandle` at `0x180018ba6`
- `KERNEL32!CloseHandle` at `0x180018ba6`
- `KERNEL32!GetCurrentThread` at `0x180018b18`
- `KERNEL32!GetCurrentThread` at `0x180018b18`
- `KERNEL32!GetCurrentProcess` at `0x180018b36`
- `KERNEL32!GetCurrentProcess` at `0x180018b36`

## pseudocode

```c
_BOOL8 IsClientAppContainer(void)
{
  BOOL v0; // ebx
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  int TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  HANDLE TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  v0 = 1;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle)
    || (CurrentProcess = GetCurrentProcess(), OpenProcessToken(CurrentProcess, 8u, &TokenHandle))
    || !GetLastError() )
  {
    if ( TokenHandle )
    {
      ReturnLength = 0;
      TokenInformation = 0;
      if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
        v0 = TokenInformation != 0;
      CloseHandle(TokenHandle);
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180018b04  push    rbx
0x180018b06  sub     rsp, 30h
0x180018b0a  mov     ebx, 1
0x180018b0f  mov     [rsp+38h+TokenHandle], 0
0x180018b18  call    cs:__imp_GetCurrentThread
0x180018b1e  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180018b23  mov     r8d, ebx; OpenAsSelf
0x180018b26  mov     rcx, rax; ThreadHandle
0x180018b29  lea     edx, [rbx+7]; DesiredAccess
0x180018b2c  call    cs:__imp_OpenThreadToken
0x180018b32  test    eax, eax
0x180018b34  jnz     short loc_180018B5B
0x180018b36  call    cs:__imp_GetCurrentProcess
0x180018b3c  mov     rcx, rax; ProcessHandle
0x180018b3f  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180018b44  lea     edx, [rbx+7]; DesiredAccess
0x180018b47  call    cs:__imp_OpenProcessToken
0x180018b4d  test    eax, eax
0x180018b4f  jnz     short loc_180018B5B
0x180018b51  call    cs:__imp_GetLastError
0x180018b57  test    eax, eax
0x180018b59  jnz     short loc_180018BAC
0x180018b5b  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180018b60  test    rcx, rcx
0x180018b63  jz      short loc_180018BAC
0x180018b65  mov     r9d, 4; TokenInformationLength
0x180018b6b  mov     [rsp+38h+arg_8], 0
0x180018b73  lea     rax, [rsp+38h+arg_8]
0x180018b78  mov     [rsp+38h+TokenInformation], 0
0x180018b80  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180018b85  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180018b8a  lea     edx, [r9+19h]; TokenInformationClass
0x180018b8e  call    cs:__imp_GetTokenInformation
0x180018b94  test    eax, eax
0x180018b96  jz      short loc_180018BA1
0x180018b98  xor     ebx, ebx
0x180018b9a  cmp     [rsp+38h+TokenInformation], ebx
0x180018b9e  setnz   bl
0x180018ba1  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180018ba6  call    cs:__imp_CloseHandle
0x180018bac  mov     eax, ebx
0x180018bae  add     rsp, 30h
0x180018bb2  pop     rbx
0x180018bb3  retn
```
