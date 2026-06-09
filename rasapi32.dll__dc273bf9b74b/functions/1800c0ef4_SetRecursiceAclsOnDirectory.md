# SetRecursiceAclsOnDirectory

- ea: `0x1800c0ef4`
- end: `0x1800c1038`
- name: `SetRecursiceAclsOnDirectory`
- size: `324`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, LPCWSTR StringSecurityDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800cf300`

## callees

- `0x1800c0df0`
- `0x1800c0ef4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c1025`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c1025`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800c0f6d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800c0f6d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1800c0fa9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1800c0fa9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800c0f93`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800c0f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0f52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0f52`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800c0f48`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800c0f48`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800c0fe3`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800c1014`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800c0fe3`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800c1014`

## pseudocode

```c
__int64 __fastcall SetRecursiceAclsOnDirectory(LPWSTR pObjectName, LPCWSTR StringSecurityDescriptor)
{
  DWORD LastError; // eax
  unsigned int v4; // ebx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-20h] BYREF
  PSID pGroup; // [rsp+48h] [rbp-18h] BYREF
  PSID pOwner; // [rsp+50h] [rbp-10h] BYREF
  PACL pDacl; // [rsp+58h] [rbp-8h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+80h] [rbp+20h] BYREF
  WINBOOL bDaclPresent; // [rsp+88h] [rbp+28h] BYREF

  bDaclDefaulted = 0;
  pDacl = 0;
  SecurityDescriptor = 0;
  pOwner = 0;
  pGroup = 0;
  bDaclPresent = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0)
    || !GetSecurityDescriptorDacl(SecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    goto LABEL_2;
  }
  if ( !bDaclPresent )
  {
    v4 = 1338;
    goto LABEL_10;
  }
  if ( GetSecurityDescriptorOwner(SecurityDescriptor, &pOwner, &bDaclDefaulted)
    && GetSecurityDescriptorGroup(SecurityDescriptor, &pGroup, &bDaclDefaulted) )
  {
    SetPrivilege();
    SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 3u, pOwner, pGroup, 0, 0);
    LastError = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 0x80000004, 0, 0, pDacl, 0);
  }
  else
  {
LABEL_2:
    LastError = GetLastError();
  }
  v4 = LastError;
LABEL_10:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return v4;
}

```

## disassembly

```asm
0x1800c0ef4  mov     [rsp-8+arg_0], rbx
0x1800c0ef9  mov     [rsp-8+bDaclDefaulted], r8d
0x1800c0efe  push    rbp
0x1800c0eff  mov     rbp, rsp
0x1800c0f02  sub     rsp, 60h
0x1800c0f06  mov     rax, rdx
0x1800c0f09  mov     [rbp+bDaclDefaulted], 0
0x1800c0f10  xor     r9d, r9d; SecurityDescriptorSize
0x1800c0f13  mov     [rbp+pDacl], 0
0x1800c0f1b  mov     rbx, rcx
0x1800c0f1e  mov     [rbp+SecurityDescriptor], 0
0x1800c0f26  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800c0f2a  mov     [rbp+pOwner], 0
0x1800c0f32  mov     rcx, rax; StringSecurityDescriptor
0x1800c0f35  mov     [rbp+pGroup], 0
0x1800c0f3d  lea     edx, [r9+1]; StringSDRevision
0x1800c0f41  mov     [rbp+bDaclPresent], 0
0x1800c0f48  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800c0f4e  test    eax, eax
0x1800c0f50  jnz     short loc_1800C0F5D
0x1800c0f52  call    cs:__imp_GetLastError
0x1800c0f58  jmp     loc_1800C101A
0x1800c0f5d  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x1800c0f61  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x1800c0f65  lea     r8, [rbp+pDacl]; pDacl
0x1800c0f69  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x1800c0f6d  call    cs:__imp_GetSecurityDescriptorDacl
0x1800c0f73  test    eax, eax
0x1800c0f75  jz      short loc_1800C0F52
0x1800c0f77  cmp     [rbp+bDaclPresent], 0
0x1800c0f7b  jnz     short loc_1800C0F87
0x1800c0f7d  mov     ebx, 53Ah
0x1800c0f82  jmp     loc_1800C101C
0x1800c0f87  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x1800c0f8b  lea     r8, [rbp+bDaclDefaulted]; lpbOwnerDefaulted
0x1800c0f8f  lea     rdx, [rbp+pOwner]; pOwner
0x1800c0f93  call    cs:__imp_GetSecurityDescriptorOwner
0x1800c0f99  test    eax, eax
0x1800c0f9b  jz      short loc_1800C0F52
0x1800c0f9d  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x1800c0fa1  lea     r8, [rbp+bDaclDefaulted]; lpbGroupDefaulted
0x1800c0fa5  lea     rdx, [rbp+pGroup]; pGroup
0x1800c0fa9  call    cs:__imp_GetSecurityDescriptorGroup
0x1800c0faf  test    eax, eax
0x1800c0fb1  jz      short loc_1800C0F52
0x1800c0fb3  call    SetPrivilege
0x1800c0fb8  mov     rax, [rbp+pGroup]
0x1800c0fbc  mov     edx, 1; ObjectType
0x1800c0fc1  mov     r9, [rbp+pOwner]; psidOwner
0x1800c0fc5  mov     rcx, rbx; pObjectName
0x1800c0fc8  mov     [rsp+60h+pSacl], 0; pSacl
0x1800c0fd1  mov     [rsp+60h+var_38], 0; pDacl
0x1800c0fda  lea     r8d, [rdx+2]; SecurityInfo
0x1800c0fde  mov     [rsp+60h+psidGroup], rax; psidGroup
0x1800c0fe3  call    cs:__imp_SetNamedSecurityInfoW
0x1800c0fe9  mov     rax, [rbp+pDacl]
0x1800c0fed  xor     r9d, r9d; psidOwner
0x1800c0ff0  mov     [rsp+60h+pSacl], 0; pSacl
0x1800c0ff9  mov     r8d, 80000004h; SecurityInfo
0x1800c0fff  mov     [rsp+60h+var_38], rax; pDacl
0x1800c1004  mov     rcx, rbx; pObjectName
0x1800c1007  mov     [rsp+60h+psidGroup], 0; psidGroup
0x1800c1010  lea     edx, [r9+1]; ObjectType
0x1800c1014  call    cs:__imp_SetNamedSecurityInfoW
0x1800c101a  mov     ebx, eax
0x1800c101c  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x1800c1020  test    rcx, rcx
0x1800c1023  jz      short loc_1800C102B
0x1800c1025  call    cs:__imp_LocalFree
0x1800c102b  mov     eax, ebx
0x1800c102d  mov     rbx, [rsp+60h+arg_0]
0x1800c1032  add     rsp, 60h
0x1800c1036  pop     rbp
0x1800c1037  retn
```
