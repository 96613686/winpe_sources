# SetRecursiceAclsOnDirectory

- ea: `0x18005fa78`
- end: `0x18005fbed`
- name: `SetRecursiceAclsOnDirectory`
- size: `373`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, LPCWSTR StringSecurityDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18007e5ac`

## callees

- `0x18005f94c`
- `0x18005fa78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fadc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fadc`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18005fafd`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18005fafd`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18005fb45`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18005fb45`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18005fb29`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18005fb29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005fbd3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005fbd3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005facc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005facc`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18005fb85`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18005fbbc`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18005fb85`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18005fbbc`

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
0x18005fa78  mov     [rsp-8+arg_0], rbx
0x18005fa7d  mov     [rsp-8+bDaclDefaulted], r8d
0x18005fa82  push    rbp
0x18005fa83  mov     rbp, rsp
0x18005fa86  sub     rsp, 60h
0x18005fa8a  mov     rax, rdx
0x18005fa8d  mov     [rbp+bDaclDefaulted], 0
0x18005fa94  xor     r9d, r9d; SecurityDescriptorSize
0x18005fa97  mov     [rbp+pDacl], 0
0x18005fa9f  mov     rbx, rcx
0x18005faa2  mov     [rbp+SecurityDescriptor], 0
0x18005faaa  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18005faae  mov     [rbp+pOwner], 0
0x18005fab6  mov     rcx, rax; StringSecurityDescriptor
0x18005fab9  mov     [rbp+pGroup], 0
0x18005fac1  lea     edx, [r9+1]; StringSDRevision
0x18005fac5  mov     [rbp+bDaclPresent], 0
0x18005facc  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18005fad3  nop     dword ptr [rax+rax+00h]
0x18005fad8  test    eax, eax
0x18005fada  jnz     short loc_18005FAED
0x18005fadc  call    cs:__imp_GetLastError
0x18005fae3  nop     dword ptr [rax+rax+00h]
0x18005fae8  jmp     loc_18005FBC8
0x18005faed  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18005faf1  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18005faf5  lea     r8, [rbp+pDacl]; pDacl
0x18005faf9  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18005fafd  call    cs:__imp_GetSecurityDescriptorDacl
0x18005fb04  nop     dword ptr [rax+rax+00h]
0x18005fb09  test    eax, eax
0x18005fb0b  jz      short loc_18005FADC
0x18005fb0d  cmp     [rbp+bDaclPresent], 0
0x18005fb11  jnz     short loc_18005FB1D
0x18005fb13  mov     ebx, 53Ah
0x18005fb18  jmp     loc_18005FBCA
0x18005fb1d  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18005fb21  lea     r8, [rbp+bDaclDefaulted]; lpbOwnerDefaulted
0x18005fb25  lea     rdx, [rbp+pOwner]; pOwner
0x18005fb29  call    cs:__imp_GetSecurityDescriptorOwner
0x18005fb30  nop     dword ptr [rax+rax+00h]
0x18005fb35  test    eax, eax
0x18005fb37  jz      short loc_18005FADC
0x18005fb39  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18005fb3d  lea     r8, [rbp+bDaclDefaulted]; lpbGroupDefaulted
0x18005fb41  lea     rdx, [rbp+pGroup]; pGroup
0x18005fb45  call    cs:__imp_GetSecurityDescriptorGroup
0x18005fb4c  nop     dword ptr [rax+rax+00h]
0x18005fb51  test    eax, eax
0x18005fb53  jz      short loc_18005FADC
0x18005fb55  call    SetPrivilege
0x18005fb5a  mov     rax, [rbp+pGroup]
0x18005fb5e  mov     edx, 1; ObjectType
0x18005fb63  mov     r9, [rbp+pOwner]; psidOwner
0x18005fb67  mov     rcx, rbx; pObjectName
0x18005fb6a  mov     [rsp+60h+pSacl], 0; pSacl
0x18005fb73  mov     [rsp+60h+var_38], 0; pDacl
0x18005fb7c  lea     r8d, [rdx+2]; SecurityInfo
0x18005fb80  mov     [rsp+60h+psidGroup], rax; psidGroup
0x18005fb85  call    cs:__imp_SetNamedSecurityInfoW
0x18005fb8c  nop     dword ptr [rax+rax+00h]
0x18005fb91  mov     rax, [rbp+pDacl]
0x18005fb95  xor     r9d, r9d; psidOwner
0x18005fb98  mov     [rsp+60h+pSacl], 0; pSacl
0x18005fba1  mov     r8d, 80000004h; SecurityInfo
0x18005fba7  mov     [rsp+60h+var_38], rax; pDacl
0x18005fbac  mov     rcx, rbx; pObjectName
0x18005fbaf  mov     [rsp+60h+psidGroup], 0; psidGroup
0x18005fbb8  lea     edx, [r9+1]; ObjectType
0x18005fbbc  call    cs:__imp_SetNamedSecurityInfoW
0x18005fbc3  nop     dword ptr [rax+rax+00h]
0x18005fbc8  mov     ebx, eax
0x18005fbca  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18005fbce  test    rcx, rcx
0x18005fbd1  jz      short loc_18005FBDF
0x18005fbd3  call    cs:__imp_LocalFree
0x18005fbda  nop     dword ptr [rax+rax+00h]
0x18005fbdf  mov     eax, ebx
0x18005fbe1  mov     rbx, [rsp+60h+arg_0]
0x18005fbe6  add     rsp, 60h
0x18005fbea  pop     rbp
0x18005fbeb  retn
```
