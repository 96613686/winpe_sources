# DhcpAddServiceAceToDir

- ea: `0x18009c43c`
- end: `0x18009c5bd`
- name: `DhcpAddServiceAceToDir`
- size: `385`
- prototype: `__int64 __fastcall(LPWSTR pObjectName)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180003298`
- `0x18002f890`
- `0x18004d330`

## callees

- `0x18009c43c`

## import_xrefs

- `ADVAPI32!SetNamedSecurityInfoW` at `0x18009c562`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18009c562`
- `ADVAPI32!SetEntriesInAclW` at `0x18009c528`
- `ADVAPI32!SetEntriesInAclW` at `0x18009c528`
- `ADVAPI32!ConvertStringSidToSidW` at `0x18009c494`
- `ADVAPI32!ConvertStringSidToSidW` at `0x18009c494`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18009c4e7`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18009c4e7`
- `KERNEL32!GetLastError` at `0x18009c4a4`
- `KERNEL32!GetLastError` at `0x18009c4a4`
- `KERNEL32!LocalFree` at `0x18009c579`
- `KERNEL32!LocalFree` at `0x18009c58e`
- `KERNEL32!LocalFree` at `0x18009c5a3`
- `KERNEL32!LocalFree` at `0x18009c579`
- `KERNEL32!LocalFree` at `0x18009c58e`
- `KERNEL32!LocalFree` at `0x18009c5a3`

## pseudocode

```c
DWORD __fastcall DhcpAddServiceAceToDir(LPWSTR pObjectName)
{
  DWORD NamedSecurityInfoW; // ebx
  PSECURITY_DESCRIPTOR hMem; // [rsp+40h] [rbp-40h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+48h] [rbp-38h] BYREF
  PACL NewAcl; // [rsp+A0h] [rbp+20h] BYREF
  PSID Sid; // [rsp+B0h] [rbp+30h] BYREF
  PACL OldAcl; // [rsp+B8h] [rbp+38h] BYREF

  OldAcl = 0;
  NewAcl = 0;
  hMem = 0;
  Sid = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  if ( !pObjectName )
    return 87;
  if ( !ConvertStringSidToSidW(L"S-1-5-80-3273805168-4048181553-3172130058-210131473-390205191", &Sid) )
    return GetLastError();
  NamedSecurityInfoW = GetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, &OldAcl, 0, &hMem);
  if ( !NamedSecurityInfoW )
  {
    pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
    pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)Sid;
    pListOfExplicitEntries.grfAccessPermissions = 0x10000000;
    pListOfExplicitEntries.grfAccessMode = SET_ACCESS;
    pListOfExplicitEntries.grfInheritance = 3;
    NamedSecurityInfoW = SetEntriesInAclW(1u, &pListOfExplicitEntries, OldAcl, &NewAcl);
    if ( !NamedSecurityInfoW )
      NamedSecurityInfoW = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, NewAcl, 0);
  }
  if ( hMem )
    LocalFree(hMem);
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( Sid )
    LocalFree(Sid);
  return NamedSecurityInfoW;
}

```

## disassembly

```asm
0x18009c43c  push    rbp
0x18009c43e  push    rbx
0x18009c43f  push    rdi
0x18009c440  mov     rbp, rsp
0x18009c443  sub     rsp, 80h
0x18009c44a  mov     [rbp+OldAcl], 0
0x18009c452  xorps   xmm0, xmm0
0x18009c455  mov     [rbp+NewAcl], 0
0x18009c45d  mov     rdi, rcx
0x18009c460  mov     [rbp+hMem], 0
0x18009c468  mov     [rbp+Sid], 0
0x18009c470  movups  xmmword ptr [rbp+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18009c474  movups  xmmword ptr [rbp+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x18009c478  movups  xmmword ptr [rbp+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x18009c47c  test    rcx, rcx
0x18009c47f  jnz     short loc_18009C489
0x18009c481  lea     eax, [rcx+57h]
0x18009c484  jmp     loc_18009C5B1
0x18009c489  lea     rdx, [rbp+Sid]; Sid
0x18009c48d  lea     rcx, StringSid; "S-1-5-80-3273805168-4048181553-31721300"...
0x18009c494  call    cs:__imp_ConvertStringSidToSidW
0x18009c49b  nop     dword ptr [rax+rax+00h]
0x18009c4a0  test    eax, eax
0x18009c4a2  jnz     short loc_18009C4B5
0x18009c4a4  call    cs:__imp_GetLastError
0x18009c4ab  nop     dword ptr [rax+rax+00h]
0x18009c4b0  jmp     loc_18009C5B1
0x18009c4b5  xor     r9d, r9d; ppsidOwner
0x18009c4b8  lea     rax, [rbp+hMem]
0x18009c4bc  mov     [rsp+80h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18009c4c1  mov     rcx, rdi; pObjectName
0x18009c4c4  lea     rax, [rbp+OldAcl]
0x18009c4c8  mov     [rsp+80h+ppSacl], 0; ppSacl
0x18009c4d1  mov     [rsp+80h+ppDacl], rax; ppDacl
0x18009c4d6  lea     edx, [r9+1]; ObjectType
0x18009c4da  mov     [rsp+80h+ppsidGroup], 0; ppsidGroup
0x18009c4e3  lea     r8d, [r9+4]; SecurityInfo
0x18009c4e7  call    cs:__imp_GetNamedSecurityInfoW
0x18009c4ee  nop     dword ptr [rax+rax+00h]
0x18009c4f3  mov     ebx, eax
0x18009c4f5  test    eax, eax
0x18009c4f7  jnz     short loc_18009C570
0x18009c4f9  mov     r8, [rbp+OldAcl]; OldAcl
0x18009c4fd  lea     r9, [rbp+NewAcl]; NewAcl
0x18009c501  mov     [rbp+pListOfExplicitEntries.Trustee.TrusteeForm], eax
0x18009c504  lea     rdx, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x18009c508  mov     rax, [rbp+Sid]
0x18009c50c  lea     ecx, [rbx+1]; cCountOfExplicitEntries
0x18009c50f  mov     [rbp+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18009c513  mov     [rbp+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x18009c51a  mov     [rbp+pListOfExplicitEntries.grfAccessMode], 2
0x18009c521  mov     [rbp+pListOfExplicitEntries.grfInheritance], 3
0x18009c528  call    cs:__imp_SetEntriesInAclW
0x18009c52f  nop     dword ptr [rax+rax+00h]
0x18009c534  mov     ebx, eax
0x18009c536  test    eax, eax
0x18009c538  jnz     short loc_18009C570
0x18009c53a  mov     rax, [rbp+NewAcl]
0x18009c53e  lea     edx, [rbx+1]; ObjectType
0x18009c541  mov     [rsp+80h+ppSacl], 0; pSacl
0x18009c54a  lea     r8d, [rbx+4]; SecurityInfo
0x18009c54e  mov     [rsp+80h+ppDacl], rax; pDacl
0x18009c553  xor     r9d, r9d; psidOwner
0x18009c556  mov     rcx, rdi; pObjectName
0x18009c559  mov     [rsp+80h+ppsidGroup], 0; psidGroup
0x18009c562  call    cs:__imp_SetNamedSecurityInfoW
0x18009c569  nop     dword ptr [rax+rax+00h]
0x18009c56e  mov     ebx, eax
0x18009c570  mov     rcx, [rbp+hMem]; hMem
0x18009c574  test    rcx, rcx
0x18009c577  jz      short loc_18009C585
0x18009c579  call    cs:__imp_LocalFree
0x18009c580  nop     dword ptr [rax+rax+00h]
0x18009c585  mov     rcx, [rbp+NewAcl]; hMem
0x18009c589  test    rcx, rcx
0x18009c58c  jz      short loc_18009C59A
0x18009c58e  call    cs:__imp_LocalFree
0x18009c595  nop     dword ptr [rax+rax+00h]
0x18009c59a  mov     rcx, [rbp+Sid]; hMem
0x18009c59e  test    rcx, rcx
0x18009c5a1  jz      short loc_18009C5AF
0x18009c5a3  call    cs:__imp_LocalFree
0x18009c5aa  nop     dword ptr [rax+rax+00h]
0x18009c5af  mov     eax, ebx
0x18009c5b1  add     rsp, 80h
0x18009c5b8  pop     rdi
0x18009c5b9  pop     rbx
0x18009c5ba  pop     rbp
0x18009c5bb  retn
```
