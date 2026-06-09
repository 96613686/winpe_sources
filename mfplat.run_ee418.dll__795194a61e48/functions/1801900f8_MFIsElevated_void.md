# MFIsElevated(void)

- ea: `0x1801900f8`
- end: `0x180190179`
- name: `?MFIsElevated@@YA_NXZ`
- size: `129`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800e1728`

## callees

- `0x1801900f8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180190109`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180190109`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18019011c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18019011c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019016b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019016b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180190154`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180190154`

## pseudocode

```c
bool MFIsElevated(void)
{
  bool v0; // bl
  HANDLE CurrentProcess; // rax
  int TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  v0 = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
  {
    TokenInformation = 0;
    ReturnLength = 0;
    if ( GetTokenInformation(TokenHandle, TokenElevation, &TokenInformation, 4u, &ReturnLength) )
      v0 = TokenInformation != 0;
    CloseHandle(TokenHandle);
  }
  return v0;
}

```

## disassembly

```asm
0x1801900f8  push    rbx
0x1801900fa  sub     rsp, 30h
0x1801900fe  xor     bl, bl
0x180190100  mov     [rsp+38h+TokenHandle], 0
0x180190109  call    cs:__imp_GetCurrentProcess
0x18019010f  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180190114  mov     edx, 20008h; DesiredAccess
0x180190119  mov     rcx, rax; ProcessHandle
0x18019011c  call    cs:__imp_OpenProcessToken
0x180190122  test    eax, eax
0x180190124  jz      short loc_180190171
0x180190126  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18019012b  lea     rax, [rsp+38h+arg_8]
0x180190130  mov     r9d, 4; TokenInformationLength
0x180190136  mov     [rsp+38h+TokenInformation], 0
0x18019013e  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180190143  mov     [rsp+38h+arg_8], 0
0x18019014b  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180190150  lea     edx, [r9+10h]; TokenInformationClass
0x180190154  call    cs:__imp_GetTokenInformation
0x18019015a  test    eax, eax
0x18019015c  jz      short loc_180190166
0x18019015e  cmp     [rsp+38h+TokenInformation], 0
0x180190163  setnz   bl
0x180190166  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18019016b  call    cs:__imp_CloseHandle
0x180190171  mov     al, bl
0x180190173  add     rsp, 30h
0x180190177  pop     rbx
0x180190178  retn
```
