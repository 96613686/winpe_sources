# CMsiSQMSession::RecordSecurityContext(void)

- ea: `0x180222928`
- end: `0x180222a80`
- name: `?RecordSecurityContext@CMsiSQMSession@@QEAAXXZ`
- size: `344`
- prototype: `void __fastcall(CMsiSQMSession *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18004d644`

## callees

- `0x18022255c`
- `0x180222928`

## import_xrefs

- `ADVAPI32!GetSidSubAuthorityCount` at `0x180222a05`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x180222a05`
- `ADVAPI32!GetSidSubAuthority` at `0x180222a20`
- `ADVAPI32!GetSidSubAuthority` at `0x180222a20`
- `ADVAPI32!GetTokenInformation` at `0x180222995`
- `ADVAPI32!GetTokenInformation` at `0x1802229f2`
- `ADVAPI32!GetTokenInformation` at `0x180222995`
- `ADVAPI32!GetTokenInformation` at `0x1802229f2`
- `ADVAPI32!OpenProcessToken` at `0x180222969`
- `ADVAPI32!OpenProcessToken` at `0x180222969`
- `KERNEL32!CloseHandle` at `0x180222a53`
- `KERNEL32!CloseHandle` at `0x180222a53`
- `KERNEL32!GetLastError` at `0x1802229a9`
- `KERNEL32!GetLastError` at `0x1802229a9`
- `KERNEL32!GetCurrentProcess` at `0x180222952`
- `KERNEL32!GetCurrentProcess` at `0x180222952`
- `KERNEL32!LocalFree` at `0x180222a42`
- `KERNEL32!LocalFree` at `0x180222a42`
- `KERNEL32!LocalAlloc` at `0x1802229c4`
- `KERNEL32!LocalAlloc` at `0x1802229c4`

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
0x180222928  mov     rax, rsp
0x18022292b  mov     [rax+18h], rbx
0x18022292f  mov     [rax+20h], rsi
0x180222933  push    rdi
0x180222934  sub     rsp, 30h
0x180222938  cmp     qword ptr [rcx], 0
0x18022293c  mov     rsi, rcx
0x18022293f  jz      loc_180222A6F
0x180222945  xor     ebx, ebx
0x180222947  mov     qword ptr [rax+10h], 0
0x18022294f  mov     [rax+8], ebx
0x180222952  call    cs:__imp_GetCurrentProcess
0x180222959  nop     dword ptr [rax+rax+00h]
0x18022295e  mov     rcx, rax; ProcessHandle
0x180222961  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180222966  lea     edx, [rbx+18h]; DesiredAccess
0x180222969  call    cs:__imp_OpenProcessToken
0x180222970  nop     dword ptr [rax+rax+00h]
0x180222975  test    eax, eax
0x180222977  jz      loc_180222A5F
0x18022297d  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180222982  lea     rax, [rsp+38h+TokenInformationLength]
0x180222987  xor     r9d, r9d; TokenInformationLength
0x18022298a  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18022298f  xor     r8d, r8d; TokenInformation
0x180222992  lea     edx, [rbx+19h]; TokenInformationClass
0x180222995  call    cs:__imp_GetTokenInformation
0x18022299c  nop     dword ptr [rax+rax+00h]
0x1802229a1  test    eax, eax
0x1802229a3  jnz     loc_180222A4E
0x1802229a9  call    cs:__imp_GetLastError
0x1802229b0  nop     dword ptr [rax+rax+00h]
0x1802229b5  cmp     eax, 7Ah ; 'z'
0x1802229b8  jnz     loc_180222A4E
0x1802229be  mov     edx, [rsp+38h+TokenInformationLength]; uBytes
0x1802229c2  xor     ecx, ecx; uFlags
0x1802229c4  call    cs:__imp_LocalAlloc
0x1802229cb  nop     dword ptr [rax+rax+00h]
0x1802229d0  mov     rdi, rax
0x1802229d3  test    rax, rax
0x1802229d6  jz      short loc_180222A4E
0x1802229d8  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1802229dd  lea     rax, [rsp+38h+TokenInformationLength]
0x1802229e2  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1802229e7  lea     edx, [rbx+19h]; TokenInformationClass
0x1802229ea  mov     r8, rdi; TokenInformation
0x1802229ed  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1802229f2  call    cs:__imp_GetTokenInformation
0x1802229f9  nop     dword ptr [rax+rax+00h]
0x1802229fe  test    eax, eax
0x180222a00  jz      short loc_180222A3F
0x180222a02  mov     rcx, [rdi]; pSid
0x180222a05  call    cs:__imp_GetSidSubAuthorityCount
0x180222a0c  nop     dword ptr [rax+rax+00h]
0x180222a11  mov     ebx, 1
0x180222a16  mov     cl, [rax]
0x180222a18  sub     cl, bl
0x180222a1a  movzx   edx, cl; nSubAuthority
0x180222a1d  mov     rcx, [rdi]; pSid
0x180222a20  call    cs:__imp_GetSidSubAuthority
0x180222a27  nop     dword ptr [rax+rax+00h]
0x180222a2c  cmp     dword ptr [rax], 2000h
0x180222a32  jb      short loc_180222A3F
0x180222a34  cmp     dword ptr [rax], 3000h
0x180222a3a  sbb     ebx, ebx
0x180222a3c  add     ebx, 3
0x180222a3f  mov     rcx, rdi; hMem
0x180222a42  call    cs:__imp_LocalFree
0x180222a49  nop     dword ptr [rax+rax+00h]
0x180222a4e  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180222a53  call    cs:__imp_CloseHandle
0x180222a5a  nop     dword ptr [rax+rax+00h]
0x180222a5f  mov     r8d, ebx; unsigned int
0x180222a62  mov     edx, 0E26h; unsigned int
0x180222a67  mov     rcx, rsi; this
0x180222a6a  call    ?RecordDWORD@CMsiSQMSession@@QEAAXKK@Z; CMsiSQMSession::RecordDWORD(ulong,ulong)
0x180222a6f  mov     rbx, [rsp+38h+arg_10]
0x180222a74  mov     rsi, [rsp+38h+arg_18]
0x180222a79  add     rsp, 30h
0x180222a7d  pop     rdi
0x180222a7e  retn
```
