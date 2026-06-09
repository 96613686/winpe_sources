# DfsReadRegistryStringSD

- ea: `0x140059f0c`
- end: `0x140059f7a`
- name: `DfsReadRegistryStringSD`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140020be8`

## callees

- `0x14002a780`
- `0x140059e6c`
- `0x140059f0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059f54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059f54`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x140059f44`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x140059f44`

## pseudocode

```c
__int64 __fastcall DfsReadRegistryStringSD(HKEY a1, LPWSTR *a2)
{
  DWORD LastError; // ebx
  __int64 v4; // rdx
  __int64 v5; // r8
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp+18h] BYREF

  SecurityDescriptor = 0;
  LastError = DfsReadRegistrySecurityInfo(a1, &SecurityDescriptor);
  if ( !LastError )
  {
    if ( !ConvertSecurityDescriptorToStringSecurityDescriptorW(SecurityDescriptor, 1u, 4u, a2, 0) )
      LastError = GetLastError();
    SHashFree(SecurityDescriptor, v4, v5);
  }
  return LastError;
}

```

## disassembly

```asm
0x140059f0c  mov     [rsp+arg_0], rbx
0x140059f11  push    rdi
0x140059f12  sub     rsp, 30h
0x140059f16  and     [rsp+38h+SecurityDescriptor], 0
0x140059f1c  mov     rdi, rdx
0x140059f1f  lea     rdx, [rsp+38h+SecurityDescriptor]
0x140059f24  call    DfsReadRegistrySecurityInfo
0x140059f29  mov     ebx, eax
0x140059f2b  test    eax, eax
0x140059f2d  jnz     short loc_140059F6C
0x140059f2f  mov     rcx, [rsp+38h+SecurityDescriptor]; SecurityDescriptor
0x140059f34  lea     edx, [rax+1]; RequestedStringSDRevision
0x140059f37  and     [rsp+38h+var_18], 0
0x140059f3d  lea     r8d, [rax+4]; SecurityInformation
0x140059f41  mov     r9, rdi; StringSecurityDescriptor
0x140059f44  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x140059f4b  nop     dword ptr [rax+rax+00h]
0x140059f50  test    eax, eax
0x140059f52  jnz     short loc_140059F62
0x140059f54  call    cs:__imp_GetLastError
0x140059f5b  nop     dword ptr [rax+rax+00h]
0x140059f60  mov     ebx, eax
0x140059f62  mov     rcx, [rsp+38h+SecurityDescriptor]
0x140059f67  call    SHashFree
0x140059f6c  mov     eax, ebx
0x140059f6e  mov     rbx, [rsp+38h+arg_0]
0x140059f73  add     rsp, 30h
0x140059f77  pop     rdi
0x140059f78  retn
```
