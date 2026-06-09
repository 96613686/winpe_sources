# GetServiceWaitTimeout

- ea: `0x1800572ec`
- end: `0x18005740b`
- name: `GetServiceWaitTimeout`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180057150`

## callees

- `0x1800572ec`
- `0x1800bec20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180057331`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180057331`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180057320`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180057320`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800573d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800573d5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180057370`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180057370`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800573aa`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800573aa`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800573ca`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800573ca`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800573bd`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800573bd`

## pseudocode

```c
__int64 GetServiceWaitTimeout()
{
  BOOL v0; // ebx
  HANDLE CurrentProcess; // rax
  DWORD ReturnLength; // [rsp+60h] [rbp-A0h] BYREF
  PSID pSid1; // [rsp+68h] [rbp-98h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp-90h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+78h] [rbp-88h] BYREF
  PSID TokenInformation[64]; // [rsp+80h] [rbp-80h] BYREF

  TokenHandle = 0;
  v0 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    ReturnLength = 512;
    *(_DWORD *)pIdentifierAuthority.Value = 0;
    *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
    pSid1 = 0;
    if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x200u, &ReturnLength)
      && AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid1) )
    {
      v0 = EqualSid(pSid1, TokenInformation[0]);
      FreeSid(pSid1);
    }
    CloseHandle(TokenHandle);
  }
  return v0 ? 900 : 120;
}

```

## disassembly

```asm
0x1800572ec  mov     [rsp-8+arg_0], rbx
0x1800572f1  mov     [rsp-8+arg_8], rdi
0x1800572f6  push    rbp
0x1800572f7  lea     rbp, [rsp-190h]
0x1800572ff  sub     rsp, 290h
0x180057306  mov     rax, cs:__security_cookie
0x18005730d  xor     rax, rsp
0x180057310  mov     [rbp+190h+var_10], rax
0x180057317  xor     edi, edi
0x180057319  mov     [rsp+290h+TokenHandle], rdi
0x18005731e  mov     ebx, edi
0x180057320  call    cs:__imp_GetCurrentProcess
0x180057326  mov     rcx, rax; ProcessHandle
0x180057329  lea     r8, [rsp+290h+TokenHandle]; TokenHandle
0x18005732e  lea     edx, [rdi+8]; DesiredAccess
0x180057331  call    cs:__imp_OpenProcessToken
0x180057337  test    eax, eax
0x180057339  jz      loc_1800573DB
0x18005733f  mov     rcx, [rsp+290h+TokenHandle]; TokenHandle
0x180057344  lea     rax, [rsp+290h+var_230]
0x180057349  mov     r9d, 200h; TokenInformationLength
0x18005734f  mov     [rsp+290h+ReturnLength], rax; ReturnLength
0x180057354  lea     r8, [rbp+190h+TokenInformation]; TokenInformation
0x180057358  mov     [rsp+290h+var_230], r9d
0x18005735d  lea     edx, [rdi+1]; TokenInformationClass
0x180057360  mov     dword ptr [rsp+290h+pIdentifierAuthority.Value], edi
0x180057364  mov     word ptr [rsp+290h+pIdentifierAuthority.Value+4], 500h
0x18005736b  mov     [rsp+290h+pSid1], rdi
0x180057370  call    cs:__imp_GetTokenInformation
0x180057376  test    eax, eax
0x180057378  jz      short loc_1800573D0
0x18005737a  lea     rax, [rsp+290h+pSid1]
0x18005737f  xor     r9d, r9d; nSubAuthority1
0x180057382  mov     [rsp+290h+pSid], rax; pSid
0x180057387  lea     r8d, [rdi+12h]; nSubAuthority0
0x18005738b  mov     [rsp+290h+nSubAuthority7], edi; nSubAuthority7
0x18005738f  lea     rcx, [rsp+290h+pIdentifierAuthority]; pIdentifierAuthority
0x180057394  mov     [rsp+290h+nSubAuthority6], edi; nSubAuthority6
0x180057398  mov     dl, 1; nSubAuthorityCount
0x18005739a  mov     [rsp+290h+nSubAuthority5], edi; nSubAuthority5
0x18005739e  mov     [rsp+290h+nSubAuthority4], edi; nSubAuthority4
0x1800573a2  mov     [rsp+290h+nSubAuthority3], edi; nSubAuthority3
0x1800573a6  mov     dword ptr [rsp+290h+ReturnLength], edi; nSubAuthority2
0x1800573aa  call    cs:__imp_AllocateAndInitializeSid
0x1800573b0  test    eax, eax
0x1800573b2  jz      short loc_1800573D0
0x1800573b4  mov     rdx, [rbp+190h+TokenInformation]; pSid2
0x1800573b8  mov     rcx, [rsp+290h+pSid1]; pSid1
0x1800573bd  call    cs:__imp_EqualSid
0x1800573c3  mov     rcx, [rsp+290h+pSid1]; pSid
0x1800573c8  mov     ebx, eax
0x1800573ca  call    cs:__imp_FreeSid
0x1800573d0  mov     rcx, [rsp+290h+TokenHandle]; hObject
0x1800573d5  call    cs:__imp_CloseHandle
0x1800573db  neg     ebx
0x1800573dd  sbb     eax, eax
0x1800573df  and     eax, 30Ch
0x1800573e4  add     eax, 78h ; 'x'
0x1800573e7  mov     rcx, [rbp+190h+var_10]
0x1800573ee  xor     rcx, rsp; StackCookie
0x1800573f1  call    __security_check_cookie
0x1800573f6  lea     r11, [rsp+290h+var_s0]
0x1800573fe  mov     rbx, [r11+10h]
0x180057402  mov     rdi, [r11+18h]
0x180057406  mov     rsp, r11
0x180057409  pop     rbp
0x18005740a  retn
```
