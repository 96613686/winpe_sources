# NlUpdateVulnerableChannelAllowList(void)

- ea: `0x1800403d0`
- end: `0x180040482`
- name: `?NlUpdateVulnerableChannelAllowList@@YAXXZ`
- size: `178`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003fa34`
- `0x18004e118`

## callees

- `0x180007278`
- `0x1800403d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040468`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040468`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180040448`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180040448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004040e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004040e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040432`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040476`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040432`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040476`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180040404`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180040404`

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
    if ( qword_1800F1230 )
    {
      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(qword_1800F1230, 1u, &SecurityDescriptor, 0) )
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
    AcquireSRWLockExclusive(&stru_1800F0F58);
    v1 = NlGlobalVulnerableChannelAllowList;
    NlGlobalVulnerableChannelAllowList = SecurityDescriptor;
    ReleaseSRWLockExclusive(&stru_1800F0F58);
    if ( v1 )
      LocalFree(v1);
  }
}

```

## disassembly

```asm
0x1800403d0  push    rbx
0x1800403d2  sub     rsp, 20h
0x1800403d6  cmp     cs:?NlGlobalMemberWorkstation@@3HA, 0; int NlGlobalMemberWorkstation
0x1800403dd  mov     [rsp+28h+SecurityDescriptor], 0
0x1800403e6  jnz     loc_18004047C
0x1800403ec  mov     rcx, cs:qword_1800F1230; StringSecurityDescriptor
0x1800403f3  test    rcx, rcx
0x1800403f6  jz      short loc_180040441
0x1800403f8  xor     r9d, r9d; SecurityDescriptorSize
0x1800403fb  lea     r8, [rsp+28h+SecurityDescriptor]; SecurityDescriptor
0x180040400  lea     edx, [r9+1]; StringSDRevision
0x180040404  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004040a  test    eax, eax
0x18004040c  jnz     short loc_180040441
0x18004040e  call    cs:__imp_GetLastError
0x180040414  lea     rdx, aTheFollowingEr_0; "The following error was encountered whe"...
0x18004041b  mov     ecx, 100h; unsigned int
0x180040420  mov     r8d, eax
0x180040423  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180040428  mov     rcx, [rsp+28h+SecurityDescriptor]; hMem
0x18004042d  test    rcx, rcx
0x180040430  jz      short loc_180040441
0x180040432  call    cs:__imp_LocalFree
0x180040438  mov     [rsp+28h+SecurityDescriptor], 0
0x180040441  lea     rcx, stru_1800F0F58; SRWLock
0x180040448  call    cs:__imp_AcquireSRWLockExclusive
0x18004044e  mov     rax, [rsp+28h+SecurityDescriptor]
0x180040453  lea     rcx, stru_1800F0F58; SRWLock
0x18004045a  mov     rbx, cs:?NlGlobalVulnerableChannelAllowList@@3U_SafeSecurityDescriptor@@A; _SafeSecurityDescriptor NlGlobalVulnerableChannelAllowList
0x180040461  mov     cs:?NlGlobalVulnerableChannelAllowList@@3U_SafeSecurityDescriptor@@A, rax; _SafeSecurityDescriptor NlGlobalVulnerableChannelAllowList
0x180040468  call    cs:__imp_ReleaseSRWLockExclusive
0x18004046e  test    rbx, rbx
0x180040471  jz      short loc_18004047C
0x180040473  mov     rcx, rbx; hMem
0x180040476  call    cs:__imp_LocalFree
0x18004047c  add     rsp, 20h
0x180040480  pop     rbx
0x180040481  retn
```
