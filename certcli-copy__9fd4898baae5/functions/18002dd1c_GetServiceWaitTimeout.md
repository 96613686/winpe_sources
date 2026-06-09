# GetServiceWaitTimeout

- ea: `0x18002dd1c`
- end: `0x18002de4c`
- name: `GetServiceWaitTimeout`
- size: `304`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002de54`

## callees

- `0x18002dd1c`
- `0x18002e1e0`
- `0x180039740`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002de16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002de16`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002dda0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002dda0`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002ddfe`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002ddfe`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002dde5`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002dde5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002de0b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002de0b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002dd61`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002dd61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002dd50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002dd50`

## pseudocode

```c
__int64 GetServiceWaitTimeout()
{
  BOOL v0; // ebx
  HANDLE CurrentProcess; // rax
  unsigned int v2; // edx
  unsigned __int16 *v3; // rcx
  unsigned int v4; // r9d
  unsigned int v5; // r8d
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  DWORD nSubAuthority3; // [rsp+28h] [rbp-D8h]
  DWORD v9; // [rsp+60h] [rbp-A0h] BYREF
  PSID pSid1; // [rsp+68h] [rbp-98h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp-90h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+78h] [rbp-88h] BYREF
  PSID TokenInformation[64]; // [rsp+80h] [rbp-80h] BYREF

  TokenHandle = 0;
  v0 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    v9 = 512;
    *(_DWORD *)pIdentifierAuthority.Value = 0;
    *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
    pSid1 = 0;
    if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x200u, &v9) )
    {
      if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid1) )
      {
        v0 = EqualSid(pSid1, TokenInformation[0]);
        FreeSid(pSid1);
        goto LABEL_8;
      }
      v5 = 126;
    }
    else
    {
      v5 = 116;
    }
    ErrLog_LogError(v3, v2, v5, v4, ReturnLength, nSubAuthority3);
LABEL_8:
    CloseHandle(TokenHandle);
  }
  return v0 ? 900 : 120;
}

```

## disassembly

```asm
0x18002dd1c  mov     [rsp-8+arg_0], rbx
0x18002dd21  mov     [rsp-8+arg_8], rdi
0x18002dd26  push    rbp
0x18002dd27  lea     rbp, [rsp-190h]
0x18002dd2f  sub     rsp, 290h
0x18002dd36  mov     rax, cs:__security_cookie
0x18002dd3d  xor     rax, rsp
0x18002dd40  mov     [rbp+190h+var_10], rax
0x18002dd47  xor     edi, edi
0x18002dd49  mov     [rsp+290h+TokenHandle], rdi
0x18002dd4e  mov     ebx, edi
0x18002dd50  call    cs:__imp_GetCurrentProcess
0x18002dd56  mov     rcx, rax; ProcessHandle
0x18002dd59  lea     r8, [rsp+290h+TokenHandle]; TokenHandle
0x18002dd5e  lea     edx, [rdi+8]; DesiredAccess
0x18002dd61  call    cs:__imp_OpenProcessToken
0x18002dd67  test    eax, eax
0x18002dd69  jz      loc_18002DE1C
0x18002dd6f  mov     rcx, [rsp+290h+TokenHandle]; TokenHandle
0x18002dd74  lea     rax, [rsp+290h+var_230]
0x18002dd79  mov     r9d, 200h; TokenInformationLength
0x18002dd7f  mov     [rsp+290h+ReturnLength], rax; int
0x18002dd84  lea     r8, [rbp+190h+TokenInformation]; TokenInformation
0x18002dd88  mov     [rsp+290h+var_230], r9d
0x18002dd8d  lea     edx, [rdi+1]; TokenInformationClass
0x18002dd90  mov     dword ptr [rsp+290h+pIdentifierAuthority.Value], edi
0x18002dd94  mov     word ptr [rsp+290h+pIdentifierAuthority.Value+4], 500h
0x18002dd9b  mov     [rsp+290h+pSid1], rdi
0x18002dda0  call    cs:__imp_GetTokenInformation
0x18002dda6  test    eax, eax
0x18002dda8  jnz     short loc_18002DDB5
0x18002ddaa  lea     r8d, [rdi+74h]; unsigned int
0x18002ddae  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18002ddb3  jmp     short loc_18002DE11
0x18002ddb5  lea     rax, [rsp+290h+pSid1]
0x18002ddba  xor     r9d, r9d; nSubAuthority1
0x18002ddbd  mov     [rsp+290h+pSid], rax; pSid
0x18002ddc2  lea     rcx, [rsp+290h+pIdentifierAuthority]; pIdentifierAuthority
0x18002ddc7  mov     [rsp+290h+nSubAuthority7], edi; nSubAuthority7
0x18002ddcb  mov     dl, 1; nSubAuthorityCount
0x18002ddcd  mov     [rsp+290h+nSubAuthority6], edi; nSubAuthority6
0x18002ddd1  mov     [rsp+290h+nSubAuthority5], edi; nSubAuthority5
0x18002ddd5  lea     r8d, [r9+12h]; nSubAuthority0
0x18002ddd9  mov     [rsp+290h+nSubAuthority4], edi; nSubAuthority4
0x18002dddd  mov     [rsp+290h+nSubAuthority3], edi; nSubAuthority3
0x18002dde1  mov     dword ptr [rsp+290h+ReturnLength], edi; nSubAuthority2
0x18002dde5  call    cs:__imp_AllocateAndInitializeSid
0x18002ddeb  test    eax, eax
0x18002dded  jnz     short loc_18002DDF5
0x18002ddef  lea     r8d, [rax+7Eh]
0x18002ddf3  jmp     short loc_18002DDAE
0x18002ddf5  mov     rdx, [rbp+190h+TokenInformation]; pSid2
0x18002ddf9  mov     rcx, [rsp+290h+pSid1]; pSid1
0x18002ddfe  call    cs:__imp_EqualSid
0x18002de04  mov     rcx, [rsp+290h+pSid1]; pSid
0x18002de09  mov     ebx, eax
0x18002de0b  call    cs:__imp_FreeSid
0x18002de11  mov     rcx, [rsp+290h+TokenHandle]; hObject
0x18002de16  call    cs:__imp_CloseHandle
0x18002de1c  neg     ebx
0x18002de1e  sbb     eax, eax
0x18002de20  and     eax, 30Ch
0x18002de25  add     eax, 78h ; 'x'
0x18002de28  mov     rcx, [rbp+190h+var_10]
0x18002de2f  xor     rcx, rsp; StackCookie
0x18002de32  call    __security_check_cookie
0x18002de37  lea     r11, [rsp+290h+var_s0]
0x18002de3f  mov     rbx, [r11+10h]
0x18002de43  mov     rdi, [r11+18h]
0x18002de47  mov     rsp, r11
0x18002de4a  pop     rbp
0x18002de4b  retn
```
