# IsSystemProcess

- ea: `0x18001953c`
- end: `0x18001960d`
- name: `IsSystemProcess`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18001923c`

## callees

- `0x18001953c`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x180019568`
- `ADVAPI32!OpenProcessToken` at `0x180019568`
- `ADVAPI32!CheckTokenMembership` at `0x1800195e5`
- `ADVAPI32!CheckTokenMembership` at `0x1800195e5`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800195c9`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800195c9`
- `ADVAPI32!FreeSid` at `0x1800195f0`
- `ADVAPI32!FreeSid` at `0x1800195f0`
- `KERNEL32!GetCurrentProcess` at `0x180019552`
- `KERNEL32!GetCurrentProcess` at `0x180019552`
- `KERNEL32!CloseHandle` at `0x1800195fe`
- `KERNEL32!CloseHandle` at `0x1800195fe`

## pseudocode

```c
__int64 IsSystemProcess()
{
  HANDLE CurrentProcess; // rax
  WINBOOL IsMember; // [rsp+70h] [rbp+8h] BYREF
  PSID SidToCheck; // [rsp+78h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp+18h] BYREF

  IsMember = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    SidToCheck = 0;
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
    {
      CheckTokenMembership(TokenHandle, SidToCheck, &IsMember);
      FreeSid(SidToCheck);
    }
    CloseHandle(TokenHandle);
  }
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x18001953c  mov     rax, rsp
0x18001953f  sub     rsp, 68h
0x180019543  mov     dword ptr [rax+8], 0
0x18001954a  mov     qword ptr [rax+18h], 0
0x180019552  call    cs:__imp_GetCurrentProcess
0x180019558  lea     r8, [rsp+68h+TokenHandle]; TokenHandle
0x180019560  mov     edx, 8; DesiredAccess
0x180019565  mov     rcx, rax; ProcessHandle
0x180019568  call    cs:__imp_OpenProcessToken
0x18001956e  test    eax, eax
0x180019570  jz      loc_180019604
0x180019576  lea     rax, [rsp+68h+SidToCheck]
0x18001957b  mov     [rsp+68h+SidToCheck], 0
0x180019584  mov     [rsp+68h+pSid], rax; pSid
0x180019589  lea     rcx, pIdentifierAuthority; pIdentifierAuthority
0x180019590  mov     [rsp+68h+nSubAuthority7], 0; nSubAuthority7
0x180019598  xor     r9d, r9d; nSubAuthority1
0x18001959b  mov     [rsp+68h+nSubAuthority6], 0; nSubAuthority6
0x1800195a3  mov     dl, 1; nSubAuthorityCount
0x1800195a5  mov     [rsp+68h+nSubAuthority5], 0; nSubAuthority5
0x1800195ad  mov     [rsp+68h+nSubAuthority4], 0; nSubAuthority4
0x1800195b5  mov     [rsp+68h+nSubAuthority3], 0; nSubAuthority3
0x1800195bd  lea     r8d, [r9+12h]; nSubAuthority0
0x1800195c1  mov     [rsp+68h+nSubAuthority2], 0; nSubAuthority2
0x1800195c9  call    cs:__imp_AllocateAndInitializeSid
0x1800195cf  test    eax, eax
0x1800195d1  jz      short loc_1800195F6
0x1800195d3  mov     rdx, [rsp+68h+SidToCheck]; SidToCheck
0x1800195d8  lea     r8, [rsp+68h+IsMember]; IsMember
0x1800195dd  mov     rcx, [rsp+68h+TokenHandle]; TokenHandle
0x1800195e5  call    cs:__imp_CheckTokenMembership
0x1800195eb  mov     rcx, [rsp+68h+SidToCheck]; pSid
0x1800195f0  call    cs:__imp_FreeSid
0x1800195f6  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x1800195fe  call    cs:__imp_CloseHandle
0x180019604  mov     eax, [rsp+68h+IsMember]
0x180019608  add     rsp, 68h
0x18001960c  retn
```
