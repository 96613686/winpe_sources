# GrantFileAccess

- ea: `0x18005eda0`
- end: `0x18005eee4`
- name: `GrantFileAccess`
- size: `324`
- prototype: `__int64 __fastcall(HANDLE handle, WCHAR *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180054660`

## callees

- `0x18005eda0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005eeb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005eec5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005eeb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005eec5`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18005ee5f`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18005ee5f`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18005ee99`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18005ee99`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18005ee18`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18005ee18`

## pseudocode

```c
__int64 __fastcall GrantFileAccess(HANDLE handle, WCHAR *a2)
{
  DWORD SecurityInfo; // ebx
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+40h] [rbp-30h] BYREF
  PACL NewAcl; // [rsp+90h] [rbp+20h] BYREF
  PACL OldAcl; // [rsp+A0h] [rbp+30h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+A8h] [rbp+38h] BYREF

  OldAcl = 0;
  NewAcl = 0;
  hMem = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  if ( !handle )
    return 87;
  SecurityInfo = GetSecurityInfo(handle, SE_FILE_OBJECT, 4u, 0, 0, &OldAcl, 0, &hMem);
  if ( !SecurityInfo )
  {
    *(_QWORD *)&pListOfExplicitEntries.Trustee.TrusteeType = 5;
    pListOfExplicitEntries.grfAccessPermissions = 0x80000000;
    *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 1;
    memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 20);
    pListOfExplicitEntries.Trustee.ptstrName = a2;
    SecurityInfo = SetEntriesInAclW(1u, &pListOfExplicitEntries, OldAcl, &NewAcl);
    if ( !SecurityInfo )
      SecurityInfo = SetSecurityInfo(handle, SE_FILE_OBJECT, 4u, 0, 0, NewAcl, 0);
  }
  if ( hMem )
    LocalFree(hMem);
  if ( NewAcl )
    LocalFree(NewAcl);
  return SecurityInfo;
}

```

## disassembly

```asm
0x18005eda0  mov     [rsp-18h+arg_8], rbx
0x18005eda5  push    rbp
0x18005eda6  push    rsi
0x18005eda7  push    rdi
0x18005eda8  mov     rbp, rsp
0x18005edab  sub     rsp, 70h
0x18005edaf  mov     [rbp+OldAcl], 0
0x18005edb7  xorps   xmm0, xmm0
0x18005edba  mov     [rbp+NewAcl], 0
0x18005edc2  mov     rsi, rdx
0x18005edc5  mov     [rbp+hMem], 0
0x18005edcd  mov     rdi, rcx
0x18005edd0  movups  xmmword ptr [rbp+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18005edd4  movups  xmmword ptr [rbp+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x18005edd8  movups  xmmword ptr [rbp+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x18005eddc  test    rcx, rcx
0x18005eddf  jnz     short loc_18005EDE9
0x18005ede1  lea     eax, [rcx+57h]
0x18005ede4  jmp     loc_18005EED3
0x18005ede9  xor     r9d, r9d; ppsidOwner
0x18005edec  lea     rax, [rbp+hMem]
0x18005edf0  mov     [rsp+70h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18005edf5  lea     rax, [rbp+OldAcl]
0x18005edf9  mov     [rsp+70h+ppSacl], 0; ppSacl
0x18005ee02  mov     [rsp+70h+ppDacl], rax; ppDacl
0x18005ee07  lea     edx, [r9+1]; ObjectType
0x18005ee0b  mov     [rsp+70h+ppsidGroup], 0; ppsidGroup
0x18005ee14  lea     r8d, [r9+4]; SecurityInfo
0x18005ee18  call    cs:__imp_GetSecurityInfo
0x18005ee1f  nop     dword ptr [rax+rax+00h]
0x18005ee24  mov     ebx, eax
0x18005ee26  test    eax, eax
0x18005ee28  jnz     short loc_18005EEA7
0x18005ee2a  mov     r8, [rbp+OldAcl]; OldAcl
0x18005ee2e  lea     r9, [rbp+NewAcl]; NewAcl
0x18005ee32  xorps   xmm0, xmm0
0x18005ee35  mov     qword ptr [rbp+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x18005ee3d  lea     rdx, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x18005ee41  mov     [rbp+pListOfExplicitEntries.grfAccessPermissions], 80000000h
0x18005ee48  lea     ecx, [rax+1]; cCountOfExplicitEntries
0x18005ee4b  mov     qword ptr [rbp+pListOfExplicitEntries.grfAccessMode], 1
0x18005ee53  movdqu  xmmword ptr [rbp+pListOfExplicitEntries+0Ch], xmm0
0x18005ee58  mov     [rbp+pListOfExplicitEntries.Trustee.TrusteeForm], eax
0x18005ee5b  mov     [rbp+pListOfExplicitEntries.Trustee.ptstrName], rsi
0x18005ee5f  call    cs:__imp_SetEntriesInAclW
0x18005ee66  nop     dword ptr [rax+rax+00h]
0x18005ee6b  mov     ebx, eax
0x18005ee6d  test    eax, eax
0x18005ee6f  jnz     short loc_18005EEA7
0x18005ee71  mov     rax, [rbp+NewAcl]
0x18005ee75  lea     edx, [rbx+1]; ObjectType
0x18005ee78  mov     [rsp+70h+ppSacl], 0; pSacl
0x18005ee81  lea     r8d, [rbx+4]; SecurityInfo
0x18005ee85  mov     [rsp+70h+ppDacl], rax; pDacl
0x18005ee8a  xor     r9d, r9d; psidOwner
0x18005ee8d  mov     rcx, rdi; handle
0x18005ee90  mov     [rsp+70h+ppsidGroup], 0; psidGroup
0x18005ee99  call    cs:__imp_SetSecurityInfo
0x18005eea0  nop     dword ptr [rax+rax+00h]
0x18005eea5  mov     ebx, eax
0x18005eea7  mov     rcx, [rbp+hMem]; hMem
0x18005eeab  test    rcx, rcx
0x18005eeae  jz      short loc_18005EEBC
0x18005eeb0  call    cs:__imp_LocalFree
0x18005eeb7  nop     dword ptr [rax+rax+00h]
0x18005eebc  mov     rcx, [rbp+NewAcl]; hMem
0x18005eec0  test    rcx, rcx
0x18005eec3  jz      short loc_18005EED1
0x18005eec5  call    cs:__imp_LocalFree
0x18005eecc  nop     dword ptr [rax+rax+00h]
0x18005eed1  mov     eax, ebx
0x18005eed3  mov     rbx, [rsp+70h+arg_8]
0x18005eedb  add     rsp, 70h
0x18005eedf  pop     rdi
0x18005eee0  pop     rsi
0x18005eee1  pop     rbp
0x18005eee2  retn
```
