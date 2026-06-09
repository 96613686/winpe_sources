# CreateUserFontsSecurityDescriptor(ushort const *,_ACL * *,void * *)

- ea: `0x1800132e4`
- end: `0x1800134d2`
- name: `?CreateUserFontsSecurityDescriptor@@YAKPEBGPEAPEAU_ACL@@PEAPEAX@Z`
- size: `494`
- prototype: `unsigned int __fastcall(LPCWSTR pObjectName, struct _ACL **, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180013658`

## callees

- `0x1800132e4`
- `0x18003104a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013460`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013460`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180013456`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180013456`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001343f`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001343f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001339f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001339f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013471`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013480`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001348f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800134ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800134bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013471`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013480`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001348f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800134ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800134bc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013377`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013427`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013377`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013427`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800133b8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800133b8`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180013415`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180013415`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180013360`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180013360`

## pseudocode

```c
__int64 __fastcall CreateUserFontsSecurityDescriptor(LPCWSTR pObjectName, struct _ACL **a2, void **a3)
{
  void *v6; // rdi
  DWORD NamedSecurityInfoW; // ebx
  HLOCAL v8; // rax
  unsigned int v9; // r8d
  __int64 v10; // rax
  __int64 v11; // rdx
  PSID v12; // rax
  HLOCAL v13; // rax
  PSECURITY_DESCRIPTOR hMem; // [rsp+40h] [rbp-49h] BYREF
  PSID Sid[3]; // [rsp+48h] [rbp-41h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+60h] [rbp-29h] BYREF
  DWORD cbSid; // [rsp+F8h] [rbp+6Fh] BYREF
  PACL NewAcl; // [rsp+100h] [rbp+77h] BYREF
  PACL OldAcl; // [rsp+108h] [rbp+7Fh] BYREF

  OldAcl = 0;
  hMem = 0;
  NewAcl = 0;
  v6 = 0;
  memset_0(&pListOfExplicitEntries, 0, 0x60u);
  *a2 = 0;
  *a3 = 0;
  *(_OWORD *)Sid = 0;
  NamedSecurityInfoW = GetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, &OldAcl, 0, &hMem);
  if ( !NamedSecurityInfoW )
  {
    v8 = LocalAlloc(0, 0x44u);
    Sid[0] = v8;
    if ( !v8 )
    {
LABEL_3:
      NamedSecurityInfoW = 8;
      goto LABEL_13;
    }
    cbSid = 68;
    if ( !CreateWellKnownSid(WinBuiltinAnyPackageSid, 0, v8, &cbSid) || !ConvertStringSidToSidW(L"S-1-15-2-2", &Sid[1]) )
      goto LABEL_12;
    v9 = 0;
    do
    {
      v10 = (int)v9++;
      v11 = 3 * v10;
      v12 = Sid[v10];
      v11 *= 2;
      *(&pListOfExplicitEntries.grfAccessPermissions + 2 * v11) = 1179817;
      *((_DWORD *)&pListOfExplicitEntries.grfAccessMode + 2 * v11) = 2;
      *(&pListOfExplicitEntries.grfInheritance + 2 * v11) = 3;
      *((_DWORD *)&pListOfExplicitEntries.Trustee.TrusteeForm + 2 * v11) = 0;
      *((_DWORD *)&pListOfExplicitEntries.Trustee.TrusteeType + 2 * v11) = 5;
      *((_QWORD *)&pListOfExplicitEntries.Trustee.ptstrName + v11) = v12;
    }
    while ( v9 < 2 );
    NamedSecurityInfoW = SetEntriesInAclW(2u, &pListOfExplicitEntries, OldAcl, &NewAcl);
    if ( !NamedSecurityInfoW )
    {
      v13 = LocalAlloc(0x40u, 0x28u);
      v6 = v13;
      if ( !v13 )
        goto LABEL_3;
      if ( !InitializeSecurityDescriptor(v13, 1u) || !SetSecurityDescriptorDacl(v6, 1, NewAcl, 0) )
LABEL_12:
        NamedSecurityInfoW = GetLastError();
    }
  }
LABEL_13:
  if ( hMem )
    LocalFree(hMem);
  if ( Sid[0] )
    LocalFree(Sid[0]);
  if ( Sid[1] )
    LocalFree(Sid[1]);
  if ( NamedSecurityInfoW )
  {
    if ( NewAcl )
      LocalFree(NewAcl);
    if ( v6 )
      LocalFree(v6);
  }
  else
  {
    *a2 = NewAcl;
    *a3 = v6;
  }
  return NamedSecurityInfoW;
}

```

## disassembly

```asm
0x1800132e4  push    rbp
0x1800132e6  push    rbx
0x1800132e7  push    rsi
0x1800132e8  push    rdi
0x1800132e9  push    r14
0x1800132eb  lea     rbp, [rsp-37h]
0x1800132f0  sub     rsp, 0C0h
0x1800132f7  mov     rsi, r8
0x1800132fa  mov     [rbp+57h+OldAcl], 0
0x180013302  mov     r14, rdx
0x180013305  mov     [rbp+57h+hMem], 0
0x18001330d  mov     rbx, rcx
0x180013310  mov     [rbp+57h+NewAcl], 0
0x180013318  xor     edi, edi
0x18001331a  lea     rcx, [rbp+57h+pListOfExplicitEntries]; void *
0x18001331e  xor     edx, edx; Val
0x180013320  lea     r8d, [rdi+60h]; Size
0x180013324  call    memset_0
0x180013329  lea     rax, [rbp+57h+hMem]
0x18001332d  mov     [r14], rdi
0x180013330  mov     [rsp+0E0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180013335  lea     edx, [rdi+1]; ObjectType
0x180013338  lea     rax, [rbp+57h+OldAcl]
0x18001333c  mov     [rsp+0E0h+ppSacl], rdi; ppSacl
0x180013341  xorps   xmm0, xmm0
0x180013344  mov     [rsp+0E0h+ppDacl], rax; ppDacl
0x180013349  xor     r9d, r9d; ppsidOwner
0x18001334c  mov     [rsp+0E0h+ppsidGroup], rdi; ppsidGroup
0x180013351  lea     r8d, [rdi+4]; SecurityInfo
0x180013355  mov     [rsi], rdi
0x180013358  mov     rcx, rbx; pObjectName
0x18001335b  movdqu  xmmword ptr [rbp+57h+Sid], xmm0
0x180013360  call    cs:__imp_GetNamedSecurityInfoW
0x180013366  mov     ebx, eax
0x180013368  test    eax, eax
0x18001336a  jnz     loc_180013468
0x180013370  lea     ebx, [rdi+44h]
0x180013373  xor     ecx, ecx; uFlags
0x180013375  mov     edx, ebx; uBytes
0x180013377  call    cs:__imp_LocalAlloc
0x18001337d  mov     [rbp+57h+Sid], rax
0x180013381  test    rax, rax
0x180013384  jnz     short loc_180013390
0x180013386  mov     ebx, 8
0x18001338b  jmp     loc_180013468
0x180013390  xor     edx, edx; DomainSid
0x180013392  mov     [rbp+57h+cbSid], ebx
0x180013395  lea     r9, [rbp+57h+cbSid]; cbSid
0x180013399  mov     r8, rax; pSid
0x18001339c  lea     ecx, [rdx+54h]; WellKnownSidType
0x18001339f  call    cs:__imp_CreateWellKnownSid
0x1800133a5  test    eax, eax
0x1800133a7  jz      loc_180013460
0x1800133ad  lea     rdx, [rbp+57h+Sid+8]; Sid
0x1800133b1  lea     rcx, StringSid; "S-1-15-2-2"
0x1800133b8  call    cs:__imp_ConvertStringSidToSidW
0x1800133be  test    eax, eax
0x1800133c0  jz      loc_180013460
0x1800133c6  xor     r8d, r8d
0x1800133c9  lea     ecx, [r8+2]; cCountOfExplicitEntries
0x1800133cd  movsxd  rax, r8d
0x1800133d0  inc     r8d
0x1800133d3  lea     rdx, [rax+rax*2]
0x1800133d7  mov     rax, [rbp+rax*8+57h+Sid]
0x1800133dc  add     rdx, rdx
0x1800133df  mov     [rbp+rdx*8+57h+pListOfExplicitEntries.grfAccessPermissions], 1200A9h
0x1800133e7  mov     [rbp+rdx*8+57h+pListOfExplicitEntries.grfAccessMode], ecx
0x1800133eb  mov     [rbp+rdx*8+57h+pListOfExplicitEntries.grfInheritance], 3
0x1800133f3  mov     [rbp+rdx*8+57h+pListOfExplicitEntries.Trustee.TrusteeForm], edi
0x1800133f7  mov     [rbp+rdx*8+57h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x1800133ff  mov     [rbp+rdx*8+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180013404  cmp     r8d, ecx
0x180013407  jb      short loc_1800133CD
0x180013409  mov     r8, [rbp+57h+OldAcl]; OldAcl
0x18001340d  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x180013411  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180013415  call    cs:__imp_SetEntriesInAclW
0x18001341b  mov     ebx, eax
0x18001341d  test    eax, eax
0x18001341f  jnz     short loc_180013468
0x180013421  lea     edx, [rax+28h]; uBytes
0x180013424  lea     ecx, [rax+40h]; uFlags
0x180013427  call    cs:__imp_LocalAlloc
0x18001342d  mov     rdi, rax
0x180013430  test    rax, rax
0x180013433  jz      loc_180013386
0x180013439  lea     edx, [rbx+1]; dwRevision
0x18001343c  mov     rcx, rax; pSecurityDescriptor
0x18001343f  call    cs:__imp_InitializeSecurityDescriptor
0x180013445  test    eax, eax
0x180013447  jz      short loc_180013460
0x180013449  mov     r8, [rbp+57h+NewAcl]; pDacl
0x18001344d  lea     edx, [rbx+1]; bDaclPresent
0x180013450  xor     r9d, r9d; bDaclDefaulted
0x180013453  mov     rcx, rdi; pSecurityDescriptor
0x180013456  call    cs:__imp_SetSecurityDescriptorDacl
0x18001345c  test    eax, eax
0x18001345e  jnz     short loc_180013468
0x180013460  call    cs:__imp_GetLastError
0x180013466  mov     ebx, eax
0x180013468  mov     rcx, [rbp+57h+hMem]; hMem
0x18001346c  test    rcx, rcx
0x18001346f  jz      short loc_180013477
0x180013471  call    cs:__imp_LocalFree
0x180013477  mov     rcx, [rbp+57h+Sid]; hMem
0x18001347b  test    rcx, rcx
0x18001347e  jz      short loc_180013486
0x180013480  call    cs:__imp_LocalFree
0x180013486  mov     rcx, [rbp+57h+Sid+8]; hMem
0x18001348a  test    rcx, rcx
0x18001348d  jz      short loc_180013495
0x18001348f  call    cs:__imp_LocalFree
0x180013495  test    ebx, ebx
0x180013497  jnz     short loc_1800134A5
0x180013499  mov     rax, [rbp+57h+NewAcl]
0x18001349d  mov     [r14], rax
0x1800134a0  mov     [rsi], rdi
0x1800134a3  jmp     short loc_1800134C2
0x1800134a5  mov     rcx, [rbp+57h+NewAcl]; hMem
0x1800134a9  test    rcx, rcx
0x1800134ac  jz      short loc_1800134B4
0x1800134ae  call    cs:__imp_LocalFree
0x1800134b4  test    rdi, rdi
0x1800134b7  jz      short loc_1800134C2
0x1800134b9  mov     rcx, rdi; hMem
0x1800134bc  call    cs:__imp_LocalFree
0x1800134c2  mov     eax, ebx
0x1800134c4  add     rsp, 0C0h
0x1800134cb  pop     r14
0x1800134cd  pop     rdi
0x1800134ce  pop     rsi
0x1800134cf  pop     rbx
0x1800134d0  pop     rbp
0x1800134d1  retn
```
