# GrantFileAccess

- ea: `0x18005ed80`
- end: `0x18005eec4`
- name: `GrantFileAccess`
- size: `324`
- prototype: `__int64 __fastcall(HANDLE handle)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180054640`

## callees

- `0x18005ed80`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ee90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005eea5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ee90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005eea5`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18005ee3f`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18005ee3f`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18005ee79`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18005ee79`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18005edf8`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18005edf8`

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
0x18005ed80  mov     [rsp-18h+arg_8], rbx
0x18005ed85  push    rbp
0x18005ed86  push    rsi
0x18005ed87  push    rdi
0x18005ed88  mov     rbp, rsp
0x18005ed8b  sub     rsp, 70h
0x18005ed8f  mov     [rbp+OldAcl], 0
0x18005ed97  xorps   xmm0, xmm0
0x18005ed9a  mov     [rbp+NewAcl], 0
0x18005eda2  mov     rsi, rdx
0x18005eda5  mov     [rbp+hMem], 0
0x18005edad  mov     rdi, rcx
0x18005edb0  movups  xmmword ptr [rbp+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18005edb4  movups  xmmword ptr [rbp+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x18005edb8  movups  xmmword ptr [rbp+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x18005edbc  test    rcx, rcx
0x18005edbf  jnz     short loc_18005EDC9
0x18005edc1  lea     eax, [rcx+57h]
0x18005edc4  jmp     loc_18005EEB3
0x18005edc9  xor     r9d, r9d; ppsidOwner
0x18005edcc  lea     rax, [rbp+hMem]
0x18005edd0  mov     [rsp+70h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18005edd5  lea     rax, [rbp+OldAcl]
0x18005edd9  mov     [rsp+70h+ppSacl], 0; ppSacl
0x18005ede2  mov     [rsp+70h+ppDacl], rax; ppDacl
0x18005ede7  lea     edx, [r9+1]; ObjectType
0x18005edeb  mov     [rsp+70h+ppsidGroup], 0; ppsidGroup
0x18005edf4  lea     r8d, [r9+4]; SecurityInfo
0x18005edf8  call    cs:__imp_GetSecurityInfo
0x18005edff  nop     dword ptr [rax+rax+00h]
0x18005ee04  mov     ebx, eax
0x18005ee06  test    eax, eax
0x18005ee08  jnz     short loc_18005EE87
0x18005ee0a  mov     r8, [rbp+OldAcl]; OldAcl
0x18005ee0e  lea     r9, [rbp+NewAcl]; NewAcl
0x18005ee12  xorps   xmm0, xmm0
0x18005ee15  mov     qword ptr [rbp+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x18005ee1d  lea     rdx, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x18005ee21  mov     [rbp+pListOfExplicitEntries.grfAccessPermissions], 80000000h
0x18005ee28  lea     ecx, [rax+1]; cCountOfExplicitEntries
0x18005ee2b  mov     qword ptr [rbp+pListOfExplicitEntries.grfAccessMode], 1
0x18005ee33  movdqu  xmmword ptr [rbp+pListOfExplicitEntries+0Ch], xmm0
0x18005ee38  mov     [rbp+pListOfExplicitEntries.Trustee.TrusteeForm], eax
0x18005ee3b  mov     [rbp+pListOfExplicitEntries.Trustee.ptstrName], rsi
0x18005ee3f  call    cs:__imp_SetEntriesInAclW
0x18005ee46  nop     dword ptr [rax+rax+00h]
0x18005ee4b  mov     ebx, eax
0x18005ee4d  test    eax, eax
0x18005ee4f  jnz     short loc_18005EE87
0x18005ee51  mov     rax, [rbp+NewAcl]
0x18005ee55  lea     edx, [rbx+1]; ObjectType
0x18005ee58  mov     [rsp+70h+ppSacl], 0; pSacl
0x18005ee61  lea     r8d, [rbx+4]; SecurityInfo
0x18005ee65  mov     [rsp+70h+ppDacl], rax; pDacl
0x18005ee6a  xor     r9d, r9d; psidOwner
0x18005ee6d  mov     rcx, rdi; handle
0x18005ee70  mov     [rsp+70h+ppsidGroup], 0; psidGroup
0x18005ee79  call    cs:__imp_SetSecurityInfo
0x18005ee80  nop     dword ptr [rax+rax+00h]
0x18005ee85  mov     ebx, eax
0x18005ee87  mov     rcx, [rbp+hMem]; hMem
0x18005ee8b  test    rcx, rcx
0x18005ee8e  jz      short loc_18005EE9C
0x18005ee90  call    cs:__imp_LocalFree
0x18005ee97  nop     dword ptr [rax+rax+00h]
0x18005ee9c  mov     rcx, [rbp+NewAcl]; hMem
0x18005eea0  test    rcx, rcx
0x18005eea3  jz      short loc_18005EEB1
0x18005eea5  call    cs:__imp_LocalFree
0x18005eeac  nop     dword ptr [rax+rax+00h]
0x18005eeb1  mov     eax, ebx
0x18005eeb3  mov     rbx, [rsp+70h+arg_8]
0x18005eebb  add     rsp, 70h
0x18005eebf  pop     rdi
0x18005eec0  pop     rsi
0x18005eec1  pop     rbp
0x18005eec2  retn
```
