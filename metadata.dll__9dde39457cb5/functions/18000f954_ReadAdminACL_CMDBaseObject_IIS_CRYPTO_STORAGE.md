# ReadAdminACL(CMDBaseObject *,IIS_CRYPTO_STORAGE *)

- ea: `0x18000f954`
- end: `0x18000fbda`
- name: `?ReadAdminACL@@YAJPEAVCMDBaseObject@@PEAVIIS_CRYPTO_STORAGE@@@Z`
- size: `646`
- prototype: `__int64 __fastcall(struct CMDBaseObject *this, struct IIS_CRYPTO_STORAGE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021c40`

## callees

- `0x18000f740`
- `0x18000f954`
- `0x18002267c`

## import_xrefs

- `ADVAPI32!InitializeAcl` at `0x18000fa5a`
- `ADVAPI32!InitializeAcl` at `0x18000fa5a`
- `ADVAPI32!FreeSid` at `0x18000fb95`
- `ADVAPI32!FreeSid` at `0x18000fba4`
- `ADVAPI32!FreeSid` at `0x18000fb95`
- `ADVAPI32!FreeSid` at `0x18000fba4`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x18000fb65`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x18000fb65`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18000fae0`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18000fb0a`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18000fae0`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18000fb0a`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x18000facd`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x18000facd`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x18000fab9`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x18000fab9`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18000fa96`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18000fa96`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18000f9d4`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18000f9d4`
- `ADVAPI32!GetLengthSid` at `0x18000fa20`
- `ADVAPI32!GetLengthSid` at `0x18000fa2c`
- `ADVAPI32!GetLengthSid` at `0x18000fa20`
- `ADVAPI32!GetLengthSid` at `0x18000fa2c`
- `ADVAPI32!AddAccessAllowedAce` at `0x18000fa6f`
- `ADVAPI32!AddAccessAllowedAce` at `0x18000fa84`
- `ADVAPI32!AddAccessAllowedAce` at `0x18000fa6f`
- `ADVAPI32!AddAccessAllowedAce` at `0x18000fa84`
- `KERNEL32!LocalFree` at `0x18000fbb2`
- `KERNEL32!LocalFree` at `0x18000fbc0`
- `KERNEL32!LocalFree` at `0x18000fbb2`
- `KERNEL32!LocalFree` at `0x18000fbc0`
- `KERNEL32!GlobalFree` at `0x18000fb86`
- `KERNEL32!GlobalFree` at `0x18000fb86`
- `KERNEL32!GlobalAlloc` at `0x18000faee`
- `KERNEL32!GlobalAlloc` at `0x18000faee`
- `KERNEL32!LocalAlloc` at `0x18000f9b6`
- `KERNEL32!LocalAlloc` at `0x18000fa3b`
- `KERNEL32!LocalAlloc` at `0x18000f9b6`
- `KERNEL32!LocalAlloc` at `0x18000fa3b`
- `KERNEL32!GetLastError` at `0x18000faa0`
- `KERNEL32!GetLastError` at `0x18000fb14`
- `KERNEL32!GetLastError` at `0x18000faa0`
- `KERNEL32!GetLastError` at `0x18000fb14`

## pseudocode

```c
__int64 __fastcall ReadAdminACL(struct CMDBaseObject *this, struct IIS_CRYPTO_STORAGE *a2)
{
  struct _ACL *v2; // r14
  HLOCAL v4; // rax
  void *v5; // rdi
  unsigned int DataObject; // ebx
  signed int PrincipalSID; // eax
  bool v8; // cc
  DWORD LengthSid; // ebx
  DWORD v10; // ebx
  struct _ACL *v11; // rax
  HGLOBAL v12; // rax
  void *v13; // rsi
  signed int LastError; // eax
  int v16; // [rsp+20h] [rbp-89h]
  PSID pOwner; // [rsp+30h] [rbp-79h] BYREF
  PSID pSid; // [rsp+38h] [rbp-71h] BYREF
  int v19; // [rsp+40h] [rbp-69h] BYREF
  int v20; // [rsp+44h] [rbp-65h] BYREF
  int v21; // [rsp+48h] [rbp-61h] BYREF
  void *v22[10]; // [rsp+50h] [rbp-59h] BYREF
  unsigned int v23[24]; // [rsp+A0h] [rbp-9h] BYREF
  DWORD dwBufferLength; // [rsp+118h] [rbp+6Fh] BYREF
  int v25; // [rsp+11Ch] [rbp+73h]
  int v26; // [rsp+120h] [rbp+77h] BYREF
  int v27; // [rsp+128h] [rbp+7Fh] BYREF

  v25 = HIDWORD(a2);
  v2 = 0;
  dwBufferLength = 0;
  pOwner = 0;
  pSid = 0;
  v26 = 0;
  v27 = 6027;
  v19 = 13;
  v21 = 3;
  v20 = 1;
  v22[7] = 0;
  v22[8] = 0;
  v4 = LocalAlloc(0x40u, 0x28u);
  v5 = v4;
  if ( !v4 )
    goto LABEL_2;
  InitializeSecurityDescriptor(v4, 1u);
  PrincipalSID = GetPrincipalSID((wchar_t *)L"Administrators", &pOwner, &v26);
  DataObject = PrincipalSID;
  v8 = PrincipalSID <= 0;
  if ( PrincipalSID )
    goto LABEL_4;
  GetPrincipalSID((wchar_t *)L"Everyone", &pSid, &v26);
  LengthSid = GetLengthSid(pSid);
  v10 = GetLengthSid(pOwner) + 24 + LengthSid;
  v11 = (struct _ACL *)LocalAlloc(0x40u, v10);
  v2 = v11;
  if ( !v11 )
    goto LABEL_2;
  InitializeAcl(v11, v10, 2u);
  AddAccessAllowedAce(v2, 2u, 0x1201BFu, pOwner);
  AddAccessAllowedAce(v2, 2u, 0x120089u, pSid);
  if ( !SetSecurityDescriptorDacl(v5, 1, v2, 0)
    || !SetSecurityDescriptorOwner(v5, pOwner, 1)
    || !SetSecurityDescriptorGroup(v5, pOwner, 1) )
  {
    PrincipalSID = GetLastError();
    DataObject = PrincipalSID;
    v8 = PrincipalSID <= 0;
LABEL_4:
    if ( !v8 )
      DataObject = (unsigned __int16)PrincipalSID | 0x80070000;
    goto LABEL_17;
  }
  MakeSelfRelativeSD(v5, 0, &dwBufferLength);
  v12 = GlobalAlloc(0x40u, dwBufferLength);
  v13 = v12;
  if ( !v12 )
  {
LABEL_2:
    DataObject = -2147024882;
    goto LABEL_17;
  }
  if ( MakeSelfRelativeSD(v5, v12, &dwBufferLength) )
  {
    v22[0] = 0;
    v22[4] = (void *)L"/Schema";
    v22[3] = v13;
    v22[5] = &v27;
    v22[2] = &v19;
    v22[6] = &v20;
    v22[1] = &v21;
    v23[3] = GetSecurityDescriptorLength(v13);
    DataObject = ReadDataObject(this, v22, v23, 0, v16);
  }
  else
  {
    LastError = GetLastError();
    DataObject = LastError;
    if ( LastError > 0 )
      DataObject = (unsigned __int16)LastError | 0x80070000;
  }
  GlobalFree(v13);
LABEL_17:
  if ( pOwner )
    FreeSid(pOwner);
  if ( pSid )
    FreeSid(pSid);
  if ( v5 )
    LocalFree(v5);
  if ( v2 )
    LocalFree(v2);
  return DataObject;
}

```

## disassembly

```asm
0x18000f954  mov     qword ptr [rsp-8+dwBufferLength], rdx
0x18000f959  push    rbp
0x18000f95a  push    rbx
0x18000f95b  push    rsi
0x18000f95c  push    rdi
0x18000f95d  push    r13
0x18000f95f  push    r14
0x18000f961  push    r15
0x18000f963  lea     rbp, [rsp-27h]
0x18000f968  sub     rsp, 0D0h
0x18000f96f  xor     r14d, r14d
0x18000f972  mov     [rbp+57h+dwBufferLength], 0
0x18000f979  mov     r15, rcx
0x18000f97c  mov     [rbp+57h+pOwner], r14
0x18000f980  mov     [rbp+57h+pSid], r14
0x18000f984  mov     [rbp+57h+arg_10], r14d
0x18000f988  lea     edx, [r14+28h]; uBytes
0x18000f98c  mov     [rbp+57h+arg_18], 178Bh
0x18000f993  lea     esi, [rdx+18h]
0x18000f996  mov     [rbp+57h+var_C0], 0Dh
0x18000f99d  lea     r13d, [r14+1]
0x18000f9a1  mov     [rbp+57h+var_B8], 3
0x18000f9a8  mov     ecx, esi; uFlags
0x18000f9aa  mov     [rbp+57h+var_BC], r13d
0x18000f9ae  mov     [rbp+57h+var_78], r14
0x18000f9b2  mov     [rbp+57h+var_70], r14
0x18000f9b6  call    cs:__imp_LocalAlloc
0x18000f9bc  mov     rdi, rax
0x18000f9bf  test    rax, rax
0x18000f9c2  jnz     short loc_18000F9CE
0x18000f9c4  mov     ebx, 8007000Eh
0x18000f9c9  jmp     loc_18000FB8C
0x18000f9ce  mov     edx, r13d; dwRevision
0x18000f9d1  mov     rcx, rdi; pSecurityDescriptor
0x18000f9d4  call    cs:__imp_InitializeSecurityDescriptor
0x18000f9da  lea     r8, [rbp+57h+arg_10]; int *
0x18000f9de  lea     rdx, [rbp+57h+pOwner]; pSid
0x18000f9e2  lea     rcx, aAdministrators; "Administrators"
0x18000f9e9  call    ?GetPrincipalSID@@YAKPEAGPEAPEAXPEAH@Z; GetPrincipalSID(ushort *,void * *,int *)
0x18000f9ee  mov     ebx, eax
0x18000f9f0  test    eax, eax
0x18000f9f2  jz      short loc_18000FA08
0x18000f9f4  jle     loc_18000FB8C
0x18000f9fa  movzx   ebx, ax
0x18000f9fd  or      ebx, 80070000h
0x18000fa03  jmp     loc_18000FB8C
0x18000fa08  lea     r8, [rbp+57h+arg_10]; int *
0x18000fa0c  lea     rdx, [rbp+57h+pSid]; pSid
0x18000fa10  lea     rcx, aEveryone; "Everyone"
0x18000fa17  call    ?GetPrincipalSID@@YAKPEAGPEAPEAXPEAH@Z; GetPrincipalSID(ushort *,void * *,int *)
0x18000fa1c  mov     rcx, [rbp+57h+pSid]; pSid
0x18000fa20  call    cs:__imp_GetLengthSid
0x18000fa26  mov     rcx, [rbp+57h+pOwner]; pSid
0x18000fa2a  mov     ebx, eax
0x18000fa2c  call    cs:__imp_GetLengthSid
0x18000fa32  add     eax, 18h
0x18000fa35  mov     ecx, esi; uFlags
0x18000fa37  add     ebx, eax
0x18000fa39  mov     edx, ebx; uBytes
0x18000fa3b  call    cs:__imp_LocalAlloc
0x18000fa41  mov     r14, rax
0x18000fa44  test    rax, rax
0x18000fa47  jz      loc_18000F9C4
0x18000fa4d  mov     esi, 2
0x18000fa52  mov     edx, ebx; nAclLength
0x18000fa54  mov     r8d, esi; dwAclRevision
0x18000fa57  mov     rcx, rax; pAcl
0x18000fa5a  call    cs:__imp_InitializeAcl
0x18000fa60  mov     r9, [rbp+57h+pOwner]; pSid
0x18000fa64  mov     r8d, 1201BFh; AccessMask
0x18000fa6a  mov     edx, esi; dwAceRevision
0x18000fa6c  mov     rcx, r14; pAcl
0x18000fa6f  call    cs:__imp_AddAccessAllowedAce
0x18000fa75  mov     r9, [rbp+57h+pSid]; pSid
0x18000fa79  mov     r8d, 120089h; AccessMask
0x18000fa7f  mov     edx, esi; dwAceRevision
0x18000fa81  mov     rcx, r14; pAcl
0x18000fa84  call    cs:__imp_AddAccessAllowedAce
0x18000fa8a  xor     r9d, r9d; bDaclDefaulted
0x18000fa8d  mov     r8, r14; pDacl
0x18000fa90  mov     edx, r13d; bDaclPresent
0x18000fa93  mov     rcx, rdi; pSecurityDescriptor
0x18000fa96  call    cs:__imp_SetSecurityDescriptorDacl
0x18000fa9c  test    eax, eax
0x18000fa9e  jnz     short loc_18000FAAF
0x18000faa0  call    cs:__imp_GetLastError
0x18000faa6  mov     ebx, eax
0x18000faa8  test    eax, eax
0x18000faaa  jmp     loc_18000F9F4
0x18000faaf  mov     rdx, [rbp+57h+pOwner]; pOwner
0x18000fab3  mov     r8d, r13d; bOwnerDefaulted
0x18000fab6  mov     rcx, rdi; pSecurityDescriptor
0x18000fab9  call    cs:__imp_SetSecurityDescriptorOwner
0x18000fabf  test    eax, eax
0x18000fac1  jz      short loc_18000FAA0
0x18000fac3  mov     rdx, [rbp+57h+pOwner]; pGroup
0x18000fac7  mov     r8d, r13d; bGroupDefaulted
0x18000faca  mov     rcx, rdi; pSecurityDescriptor
0x18000facd  call    cs:__imp_SetSecurityDescriptorGroup
0x18000fad3  test    eax, eax
0x18000fad5  jz      short loc_18000FAA0
0x18000fad7  lea     r8, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x18000fadb  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x18000fadd  mov     rcx, rdi; pAbsoluteSecurityDescriptor
0x18000fae0  call    cs:__imp_MakeSelfRelativeSD
0x18000fae6  mov     edx, [rbp+57h+dwBufferLength]; dwBytes
0x18000fae9  mov     ecx, 40h ; '@'; uFlags
0x18000faee  call    cs:__imp_GlobalAlloc
0x18000faf4  mov     rsi, rax
0x18000faf7  test    rax, rax
0x18000fafa  jz      loc_18000F9C4
0x18000fb00  lea     r8, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x18000fb04  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x18000fb07  mov     rcx, rdi; pAbsoluteSecurityDescriptor
0x18000fb0a  call    cs:__imp_MakeSelfRelativeSD
0x18000fb10  test    eax, eax
0x18000fb12  jnz     short loc_18000FB2B
0x18000fb14  call    cs:__imp_GetLastError
0x18000fb1a  mov     ebx, eax
0x18000fb1c  test    eax, eax
0x18000fb1e  jle     short loc_18000FB83
0x18000fb20  movzx   ebx, ax
0x18000fb23  or      ebx, 80070000h
0x18000fb29  jmp     short loc_18000FB83
0x18000fb2b  lea     rax, aSchema_3; "/Schema"
0x18000fb32  mov     [rbp+57h+var_B0], 0
0x18000fb3a  mov     [rbp+57h+var_90], rax
0x18000fb3e  mov     rcx, rsi; pSecurityDescriptor
0x18000fb41  lea     rax, [rbp+57h+arg_18]
0x18000fb45  mov     [rbp+57h+var_98], rsi
0x18000fb49  mov     [rbp+57h+var_88], rax
0x18000fb4d  lea     rax, [rbp+57h+var_C0]
0x18000fb51  mov     [rbp+57h+var_A0], rax
0x18000fb55  lea     rax, [rbp+57h+var_BC]
0x18000fb59  mov     [rbp+57h+var_80], rax
0x18000fb5d  lea     rax, [rbp+57h+var_B8]
0x18000fb61  mov     [rbp+57h+var_A8], rax
0x18000fb65  call    cs:__imp_GetSecurityDescriptorLength
0x18000fb6b  xor     r9d, r9d; struct IIS_CRYPTO_STORAGE *
0x18000fb6e  lea     r8, [rbp+57h+var_60]; unsigned int *
0x18000fb72  lea     rdx, [rbp+57h+var_B0]; void **
0x18000fb76  mov     [rbp+57h+var_54], eax
0x18000fb79  mov     rcx, r15; this
0x18000fb7c  call    ?ReadDataObject@@YAJPEAVCMDBaseObject@@PEAPEAXPEAKPEAVIIS_CRYPTO_STORAGE@@H@Z; ReadDataObject(CMDBaseObject *,void * *,ulong *,IIS_CRYPTO_STORAGE *,int)
0x18000fb81  mov     ebx, eax
0x18000fb83  mov     rcx, rsi; hMem
0x18000fb86  call    cs:__imp_GlobalFree
0x18000fb8c  mov     rcx, [rbp+57h+pOwner]; pSid
0x18000fb90  test    rcx, rcx
0x18000fb93  jz      short loc_18000FB9B
0x18000fb95  call    cs:__imp_FreeSid
0x18000fb9b  mov     rcx, [rbp+57h+pSid]; pSid
0x18000fb9f  test    rcx, rcx
0x18000fba2  jz      short loc_18000FBAA
0x18000fba4  call    cs:__imp_FreeSid
0x18000fbaa  test    rdi, rdi
0x18000fbad  jz      short loc_18000FBB8
0x18000fbaf  mov     rcx, rdi; hMem
0x18000fbb2  call    cs:__imp_LocalFree
0x18000fbb8  test    r14, r14
0x18000fbbb  jz      short loc_18000FBC6
0x18000fbbd  mov     rcx, r14; hMem
0x18000fbc0  call    cs:__imp_LocalFree
0x18000fbc6  mov     eax, ebx
0x18000fbc8  add     rsp, 0D0h
0x18000fbcf  pop     r15
0x18000fbd1  pop     r14
0x18000fbd3  pop     r13
0x18000fbd5  pop     rdi
0x18000fbd6  pop     rsi
0x18000fbd7  pop     rbx
0x18000fbd8  pop     rbp
0x18000fbd9  retn
```
