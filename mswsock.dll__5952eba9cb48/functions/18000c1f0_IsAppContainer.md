# IsAppContainer

- ea: `0x18000c1f0`
- end: `0x18000c2a8`
- name: `IsAppContainer`
- size: `184`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a6b0`
- `0x18000d000`

## callees

- `0x18000c1f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c213`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c213`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000c22c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000c22c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c297`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c297`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c26a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c26a`

## pseudocode

```c
char IsAppContainer()
{
  HANDLE CurrentProcess; // rax
  signed __int32 v2[8]; // [rsp+0h] [rbp-38h] BYREF
  int TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  if ( !SockIsAppContainerCheckDone )
  {
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      TokenInformation = 0;
      ReturnLength = 0;
      if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
      {
        SockIsAppContainer = TokenInformation != 0;
        _InterlockedOr(v2, 0);
        SockIsAppContainerCheckDone = 1;
      }
      CloseHandle(TokenHandle);
    }
  }
  return SockIsAppContainer;
}

```

## disassembly

```asm
0x18000c1f0  sub     rsp, 38h
0x18000c1f4  mov     al, cs:SockIsAppContainerCheckDone
0x18000c1fa  test    al, al
0x18000c1fc  jz      short loc_18000C20A
0x18000c1fe  mov     al, cs:SockIsAppContainer
0x18000c204  add     rsp, 38h
0x18000c208  retn
0x18000c20a  mov     [rsp+38h+TokenHandle], 0
0x18000c213  call    cs:__imp_GetCurrentProcess
0x18000c21a  nop     dword ptr [rax+rax+00h]
0x18000c21f  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18000c224  mov     edx, 8; DesiredAccess
0x18000c229  mov     rcx, rax; ProcessHandle
0x18000c22c  call    cs:__imp_OpenProcessToken
0x18000c233  nop     dword ptr [rax+rax+00h]
0x18000c238  test    eax, eax
0x18000c23a  jz      short loc_18000C1FE
0x18000c23c  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18000c241  lea     rax, [rsp+38h+arg_8]
0x18000c246  mov     r9d, 4; TokenInformationLength
0x18000c24c  mov     [rsp+38h+TokenInformation], 0
0x18000c254  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18000c259  mov     [rsp+38h+arg_8], 0
0x18000c261  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18000c266  lea     edx, [r9+19h]; TokenInformationClass
0x18000c26a  call    cs:__imp_GetTokenInformation
0x18000c271  nop     dword ptr [rax+rax+00h]
0x18000c276  test    eax, eax
0x18000c278  jz      short loc_18000C292
0x18000c27a  cmp     [rsp+38h+TokenInformation], 0
0x18000c27f  setnz   cs:SockIsAppContainer
0x18000c286  lock or [rsp+38h+var_38], 0
0x18000c28b  mov     cs:SockIsAppContainerCheckDone, 1
0x18000c292  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18000c297  call    cs:__imp_CloseHandle
0x18000c29e  nop     dword ptr [rax+rax+00h]
0x18000c2a3  jmp     loc_18000C1FE
```
