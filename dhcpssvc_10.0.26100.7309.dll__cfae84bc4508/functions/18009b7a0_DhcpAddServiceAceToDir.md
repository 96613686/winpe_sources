# DhcpAddServiceAceToDir

- ea: `0x18009b7a0`
- end: `0x18009b916`
- name: `DhcpAddServiceAceToDir`
- size: `374`
- prototype: `__int64 __fastcall(LPWSTR pObjectName)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800032a4`
- `0x1800302a0`
- `0x18004d6f0`

## callees

- `0x18009b7a0`

## import_xrefs

- `ADVAPI32!SetNamedSecurityInfoW` at `0x18009b8bb`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18009b8bb`
- `ADVAPI32!SetEntriesInAclW` at `0x18009b887`
- `ADVAPI32!SetEntriesInAclW` at `0x18009b887`
- `ADVAPI32!ConvertStringSidToSidW` at `0x18009b7ec`
- `ADVAPI32!ConvertStringSidToSidW` at `0x18009b7ec`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18009b839`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18009b839`
- `KERNEL32!GetLastError` at `0x18009b7fc`
- `KERNEL32!GetLastError` at `0x18009b7fc`
- `KERNEL32!LocalFree` at `0x18009b8d2`
- `KERNEL32!LocalFree` at `0x18009b8e7`
- `KERNEL32!LocalFree` at `0x18009b8fc`
- `KERNEL32!LocalFree` at `0x18009b8d2`
- `KERNEL32!LocalFree` at `0x18009b8e7`
- `KERNEL32!LocalFree` at `0x18009b8fc`

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
    pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)Sid;
    memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 28);
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
0x18009b7a0  push    rbp
0x18009b7a2  push    rbx
0x18009b7a3  push    rdi
0x18009b7a4  mov     rbp, rsp
0x18009b7a7  sub     rsp, 80h
0x18009b7ae  and     [rbp+OldAcl], 0
0x18009b7b3  xorps   xmm0, xmm0
0x18009b7b6  and     [rbp+NewAcl], 0
0x18009b7bb  mov     rdi, rcx
0x18009b7be  and     [rbp+hMem], 0
0x18009b7c3  and     [rbp+Sid], 0
0x18009b7c8  movups  xmmword ptr [rbp+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18009b7cc  movups  xmmword ptr [rbp+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x18009b7d0  movups  xmmword ptr [rbp+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x18009b7d4  test    rcx, rcx
0x18009b7d7  jnz     short loc_18009B7E1
0x18009b7d9  lea     eax, [rcx+57h]
0x18009b7dc  jmp     loc_18009B90A
0x18009b7e1  lea     rdx, [rbp+Sid]; Sid
0x18009b7e5  lea     rcx, StringSid; "S-1-5-80-3273805168-4048181553-31721300"...
0x18009b7ec  call    cs:__imp_ConvertStringSidToSidW
0x18009b7f3  nop     dword ptr [rax+rax+00h]
0x18009b7f8  test    eax, eax
0x18009b7fa  jnz     short loc_18009B80D
0x18009b7fc  call    cs:__imp_GetLastError
0x18009b803  nop     dword ptr [rax+rax+00h]
0x18009b808  jmp     loc_18009B90A
0x18009b80d  xor     r9d, r9d; ppsidOwner
0x18009b810  lea     rax, [rbp+hMem]
0x18009b814  mov     [rsp+80h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18009b819  mov     rcx, rdi; pObjectName
0x18009b81c  and     [rsp+80h+var_50], 0
0x18009b822  lea     rax, [rbp+OldAcl]
0x18009b826  mov     [rsp+80h+ppDacl], rax; ppDacl
0x18009b82b  and     [rsp+80h+var_60], 0
0x18009b831  lea     edx, [r9+1]; ObjectType
0x18009b835  lea     r8d, [r9+4]; SecurityInfo
0x18009b839  call    cs:__imp_GetNamedSecurityInfoW
0x18009b840  nop     dword ptr [rax+rax+00h]
0x18009b845  mov     ebx, eax
0x18009b847  test    eax, eax
0x18009b849  jnz     short loc_18009B8C9
0x18009b84b  and     [rbp+pListOfExplicitEntries.Trustee.TrusteeForm], eax
0x18009b84e  lea     r9, [rbp+NewAcl]; NewAcl
0x18009b852  mov     rax, [rbp+Sid]
0x18009b856  lea     rdx, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x18009b85a  mov     r8, [rbp+OldAcl]; OldAcl
0x18009b85e  lea     ecx, [rbx+1]; cCountOfExplicitEntries
0x18009b861  and     qword ptr [rbp+pListOfExplicitEntries.Trustee.TrusteeType], 0
0x18009b866  xorps   xmm0, xmm0
0x18009b869  mov     [rbp+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18009b86d  movdqu  xmmword ptr [rbp+pListOfExplicitEntries+0Ch], xmm0
0x18009b872  mov     [rbp+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x18009b879  mov     [rbp+pListOfExplicitEntries.grfAccessMode], 2
0x18009b880  mov     [rbp+pListOfExplicitEntries.grfInheritance], 3
0x18009b887  call    cs:__imp_SetEntriesInAclW
0x18009b88e  nop     dword ptr [rax+rax+00h]
0x18009b893  mov     ebx, eax
0x18009b895  test    eax, eax
0x18009b897  jnz     short loc_18009B8C9
0x18009b899  and     [rsp+80h+var_50], 0
0x18009b89f  lea     edx, [rbx+1]; ObjectType
0x18009b8a2  mov     rax, [rbp+NewAcl]
0x18009b8a6  lea     r8d, [rbx+4]; SecurityInfo
0x18009b8aa  mov     [rsp+80h+ppDacl], rax; pDacl
0x18009b8af  xor     r9d, r9d; psidOwner
0x18009b8b2  and     [rsp+80h+var_60], 0
0x18009b8b8  mov     rcx, rdi; pObjectName
0x18009b8bb  call    cs:__imp_SetNamedSecurityInfoW
0x18009b8c2  nop     dword ptr [rax+rax+00h]
0x18009b8c7  mov     ebx, eax
0x18009b8c9  mov     rcx, [rbp+hMem]; hMem
0x18009b8cd  test    rcx, rcx
0x18009b8d0  jz      short loc_18009B8DE
0x18009b8d2  call    cs:__imp_LocalFree
0x18009b8d9  nop     dword ptr [rax+rax+00h]
0x18009b8de  mov     rcx, [rbp+NewAcl]; hMem
0x18009b8e2  test    rcx, rcx
0x18009b8e5  jz      short loc_18009B8F3
0x18009b8e7  call    cs:__imp_LocalFree
0x18009b8ee  nop     dword ptr [rax+rax+00h]
0x18009b8f3  mov     rcx, [rbp+Sid]; hMem
0x18009b8f7  test    rcx, rcx
0x18009b8fa  jz      short loc_18009B908
0x18009b8fc  call    cs:__imp_LocalFree
0x18009b903  nop     dword ptr [rax+rax+00h]
0x18009b908  mov     eax, ebx
0x18009b90a  add     rsp, 80h
0x18009b911  pop     rdi
0x18009b912  pop     rbx
0x18009b913  pop     rbp
0x18009b914  retn
```
