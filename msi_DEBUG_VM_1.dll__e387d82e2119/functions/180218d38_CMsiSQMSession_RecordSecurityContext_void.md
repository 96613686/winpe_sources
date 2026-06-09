# CMsiSQMSession::RecordSecurityContext(void)

- ea: `0x180218d38`
- end: `0x180218e4b`
- name: `?RecordSecurityContext@CMsiSQMSession@@QEAAXXZ`
- size: `275`
- prototype: `void __fastcall(CMsiSQMSession *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180111d80`

## callees

- `0x18021896c`
- `0x180218d38`

## import_xrefs

- `ADVAPI32!GetSidSubAuthorityCount` at `0x180218de9`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x180218de9`
- `ADVAPI32!GetSidSubAuthority` at `0x180218dfe`
- `ADVAPI32!GetSidSubAuthority` at `0x180218dfe`
- `ADVAPI32!GetTokenInformation` at `0x180218d99`
- `ADVAPI32!GetTokenInformation` at `0x180218ddc`
- `ADVAPI32!GetTokenInformation` at `0x180218d99`
- `ADVAPI32!GetTokenInformation` at `0x180218ddc`
- `ADVAPI32!OpenProcessToken` at `0x180218d73`
- `ADVAPI32!OpenProcessToken` at `0x180218d73`
- `KERNEL32!CloseHandle` at `0x180218e25`
- `KERNEL32!CloseHandle` at `0x180218e25`
- `KERNEL32!GetLastError` at `0x180218da3`
- `KERNEL32!GetLastError` at `0x180218da3`
- `KERNEL32!GetCurrentProcess` at `0x180218d62`
- `KERNEL32!GetCurrentProcess` at `0x180218d62`
- `KERNEL32!LocalFree` at `0x180218e1a`
- `KERNEL32!LocalFree` at `0x180218e1a`
- `KERNEL32!LocalAlloc` at `0x180218db4`
- `KERNEL32!LocalAlloc` at `0x180218db4`

## pseudocode

```c
void __fastcall CMsiSQMSession::RecordSecurityContext(CMsiSQMSession *this)
{
  unsigned int v2; // ebx
  HANDLE CurrentProcess; // rax
  PSID *v4; // rdi
  PUCHAR SidSubAuthorityCount; // rax
  PDWORD SidSubAuthority; // rax
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+10h] BYREF

  if ( *(_QWORD *)this )
  {
    v2 = 0;
    TokenHandle = 0;
    TokenInformationLength = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x18u, &TokenHandle) )
    {
      if ( !GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength)
        && GetLastError() == 122 )
      {
        v4 = (PSID *)LocalAlloc(0, TokenInformationLength);
        if ( v4 )
        {
          if ( GetTokenInformation(
                 TokenHandle,
                 TokenIntegrityLevel,
                 v4,
                 TokenInformationLength,
                 &TokenInformationLength) )
          {
            SidSubAuthorityCount = GetSidSubAuthorityCount(*v4);
            v2 = 1;
            SidSubAuthority = GetSidSubAuthority(*v4, (unsigned __int8)(*SidSubAuthorityCount - 1));
            if ( *SidSubAuthority >= 0x2000 )
              v2 = 3 - (*SidSubAuthority < 0x3000);
          }
          LocalFree(v4);
        }
      }
      CloseHandle(TokenHandle);
    }
    CMsiSQMSession::RecordDWORD(this, 0xE26u, v2);
  }
}

```

## disassembly

```asm
0x180218d38  mov     rax, rsp
0x180218d3b  mov     [rax+18h], rbx
0x180218d3f  mov     [rax+20h], rsi
0x180218d43  push    rdi
0x180218d44  sub     rsp, 30h
0x180218d48  cmp     qword ptr [rcx], 0
0x180218d4c  mov     rsi, rcx
0x180218d4f  jz      loc_180218E3B
0x180218d55  xor     ebx, ebx
0x180218d57  mov     qword ptr [rax+10h], 0
0x180218d5f  mov     [rax+8], ebx
0x180218d62  call    cs:__imp_GetCurrentProcess
0x180218d68  mov     rcx, rax; ProcessHandle
0x180218d6b  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180218d70  lea     edx, [rbx+18h]; DesiredAccess
0x180218d73  call    cs:__imp_OpenProcessToken
0x180218d79  test    eax, eax
0x180218d7b  jz      loc_180218E2B
0x180218d81  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180218d86  lea     rax, [rsp+38h+TokenInformationLength]
0x180218d8b  xor     r9d, r9d; TokenInformationLength
0x180218d8e  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180218d93  xor     r8d, r8d; TokenInformation
0x180218d96  lea     edx, [rbx+19h]; TokenInformationClass
0x180218d99  call    cs:__imp_GetTokenInformation
0x180218d9f  test    eax, eax
0x180218da1  jnz     short loc_180218E20
0x180218da3  call    cs:__imp_GetLastError
0x180218da9  cmp     eax, 7Ah ; 'z'
0x180218dac  jnz     short loc_180218E20
0x180218dae  mov     edx, [rsp+38h+TokenInformationLength]; uBytes
0x180218db2  xor     ecx, ecx; uFlags
0x180218db4  call    cs:__imp_LocalAlloc
0x180218dba  mov     rdi, rax
0x180218dbd  test    rax, rax
0x180218dc0  jz      short loc_180218E20
0x180218dc2  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180218dc7  lea     rax, [rsp+38h+TokenInformationLength]
0x180218dcc  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180218dd1  lea     edx, [rbx+19h]; TokenInformationClass
0x180218dd4  mov     r8, rdi; TokenInformation
0x180218dd7  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180218ddc  call    cs:__imp_GetTokenInformation
0x180218de2  test    eax, eax
0x180218de4  jz      short loc_180218E17
0x180218de6  mov     rcx, [rdi]; pSid
0x180218de9  call    cs:__imp_GetSidSubAuthorityCount
0x180218def  mov     ebx, 1
0x180218df4  mov     cl, [rax]
0x180218df6  sub     cl, bl
0x180218df8  movzx   edx, cl; nSubAuthority
0x180218dfb  mov     rcx, [rdi]; pSid
0x180218dfe  call    cs:__imp_GetSidSubAuthority
0x180218e04  cmp     dword ptr [rax], 2000h
0x180218e0a  jb      short loc_180218E17
0x180218e0c  cmp     dword ptr [rax], 3000h
0x180218e12  sbb     ebx, ebx
0x180218e14  add     ebx, 3
0x180218e17  mov     rcx, rdi; hMem
0x180218e1a  call    cs:__imp_LocalFree
0x180218e20  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180218e25  call    cs:__imp_CloseHandle
0x180218e2b  mov     r8d, ebx; unsigned int
0x180218e2e  mov     edx, 0E26h; unsigned int
0x180218e33  mov     rcx, rsi; this
0x180218e36  call    ?RecordDWORD@CMsiSQMSession@@QEAAXKK@Z; CMsiSQMSession::RecordDWORD(ulong,ulong)
0x180218e3b  mov     rbx, [rsp+38h+arg_10]
0x180218e40  mov     rsi, [rsp+38h+arg_18]
0x180218e45  add     rsp, 30h
0x180218e49  pop     rdi
0x180218e4a  retn
```
