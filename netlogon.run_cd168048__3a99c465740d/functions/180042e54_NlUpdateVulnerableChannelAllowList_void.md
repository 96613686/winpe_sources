# NlUpdateVulnerableChannelAllowList(void)

- ea: `0x180042e54`
- end: `0x180042f2b`
- name: `?NlUpdateVulnerableChannelAllowList@@YAXXZ`
- size: `215`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800423a4`
- `0x18005179c`

## callees

- `0x180007518`
- `0x180042e54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180042f04`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180042f04`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180042ede`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180042ede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042e98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042e98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042ec2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042f18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042ec2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042f18`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180042e88`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180042e88`

## pseudocode

```c
void NlUpdateVulnerableChannelAllowList(void)
{
  DWORD LastError; // eax
  HLOCAL v1; // rbx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp+8h] BYREF

  SecurityDescriptor = 0;
  if ( !NlGlobalMemberWorkstation )
  {
    if ( qword_1800F8230 )
    {
      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(qword_1800F8230, 1u, &SecurityDescriptor, 0) )
      {
        LastError = GetLastError();
        NlPrintRoutine(
          0x100u,
          L"The following error was encountered when processing VulnerableChannelAllowList SDDL: %#x\n",
          LastError);
        if ( SecurityDescriptor )
        {
          LocalFree(SecurityDescriptor);
          SecurityDescriptor = 0;
        }
      }
    }
    AcquireSRWLockExclusive(&stru_1800F7F58);
    v1 = NlGlobalVulnerableChannelAllowList;
    NlGlobalVulnerableChannelAllowList = SecurityDescriptor;
    ReleaseSRWLockExclusive(&stru_1800F7F58);
    if ( v1 )
      LocalFree(v1);
  }
}

```

## disassembly

```asm
0x180042e54  push    rbx
0x180042e56  sub     rsp, 20h
0x180042e5a  cmp     cs:?NlGlobalMemberWorkstation@@3HA, 0; int NlGlobalMemberWorkstation
0x180042e61  mov     [rsp+28h+SecurityDescriptor], 0
0x180042e6a  jnz     loc_180042F24
0x180042e70  mov     rcx, cs:qword_1800F8230; StringSecurityDescriptor
0x180042e77  test    rcx, rcx
0x180042e7a  jz      short loc_180042ED7
0x180042e7c  xor     r9d, r9d; SecurityDescriptorSize
0x180042e7f  lea     r8, [rsp+28h+SecurityDescriptor]; SecurityDescriptor
0x180042e84  lea     edx, [r9+1]; StringSDRevision
0x180042e88  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180042e8f  nop     dword ptr [rax+rax+00h]
0x180042e94  test    eax, eax
0x180042e96  jnz     short loc_180042ED7
0x180042e98  call    cs:__imp_GetLastError
0x180042e9f  nop     dword ptr [rax+rax+00h]
0x180042ea4  lea     rdx, aTheFollowingEr_0; "The following error was encountered whe"...
0x180042eab  mov     ecx, 100h; unsigned int
0x180042eb0  mov     r8d, eax
0x180042eb3  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180042eb8  mov     rcx, [rsp+28h+SecurityDescriptor]; hMem
0x180042ebd  test    rcx, rcx
0x180042ec0  jz      short loc_180042ED7
0x180042ec2  call    cs:__imp_LocalFree
0x180042ec9  nop     dword ptr [rax+rax+00h]
0x180042ece  mov     [rsp+28h+SecurityDescriptor], 0
0x180042ed7  lea     rcx, stru_1800F7F58; SRWLock
0x180042ede  call    cs:__imp_AcquireSRWLockExclusive
0x180042ee5  nop     dword ptr [rax+rax+00h]
0x180042eea  mov     rax, [rsp+28h+SecurityDescriptor]
0x180042eef  lea     rcx, stru_1800F7F58; SRWLock
0x180042ef6  mov     rbx, cs:?NlGlobalVulnerableChannelAllowList@@3U_SafeSecurityDescriptor@@A; _SafeSecurityDescriptor NlGlobalVulnerableChannelAllowList
0x180042efd  mov     cs:?NlGlobalVulnerableChannelAllowList@@3U_SafeSecurityDescriptor@@A, rax; _SafeSecurityDescriptor NlGlobalVulnerableChannelAllowList
0x180042f04  call    cs:__imp_ReleaseSRWLockExclusive
0x180042f0b  nop     dword ptr [rax+rax+00h]
0x180042f10  test    rbx, rbx
0x180042f13  jz      short loc_180042F24
0x180042f15  mov     rcx, rbx; hMem
0x180042f18  call    cs:__imp_LocalFree
0x180042f1f  nop     dword ptr [rax+rax+00h]
0x180042f24  add     rsp, 20h
0x180042f28  pop     rbx
0x180042f29  retn
```
