# fpoConstructSd

- ea: `0x180129df4`
- end: `0x18012a012`
- name: `fpoConstructSd`
- size: `542`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18012a018`

## callees

- `0x180006330`
- `0x1800067d0`
- `0x18000dc7c`
- `0x18001e090`
- `0x180105bb4`
- `0x180129df4`
- `0x18016a988`
- `0x180172b30`
- `0x1803e4440`
- `0x1803e4500`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180129efb`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180129efb`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180129f1e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180129f1e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180129ff6`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180129ff6`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180129ea6`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180129ea6`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180129ebf`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180129ebf`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180129ed8`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180129ed8`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180129f36`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180129f66`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180129f36`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180129f66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180129f8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180129f99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a004`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180129f8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180129f99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a004`

## pseudocode

```c
__int64 __fastcall fpoConstructSd(__int64 a1, unsigned int a2, DWORD *a3, PSECURITY_DESCRIPTOR *a4)
{
  __int64 v7; // r9
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rbx
  struct _ACL *Dacl; // rax
  struct _ACL *Sacl; // rax
  DWORD v13; // ebx
  void *v14; // rax
  int v15; // r8d
  int v16; // r9d
  DWORD LastError; // eax
  DWORD cbSid; // [rsp+30h] [rbp-79h] BYREF
  void *Src; // [rsp+38h] [rbp-71h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+40h] [rbp-69h] BYREF
  __int64 v22; // [rsp+60h] [rbp-49h]
  _BYTE v23[8]; // [rsp+68h] [rbp-41h] BYREF
  _BYTE pOwner[80]; // [rsp+70h] [rbp-39h] BYREF

  cbSid = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v22 = 0;
  if ( *(_DWORD *)gfADAM )
  {
    Src = 0;
    if ( (unsigned int)NCLGetSID(a2, 0, v23, &Src) )
    {
      v7 = 53085947;
      v8 = 0;
      v9 = 8430;
      return (unsigned int)DoSetSvcError(5012, v9, v8, v7);
    }
    MakeSid(Src);
  }
  else
  {
    cbSid = 72;
    if ( !CreateWellKnownSid(WinAccountDomainAdminsSid, (char *)qword_18052B2C0 + 24, pOwner, &cbSid) )
    {
      LastError = GetLastError();
      v7 = 53085962;
      goto LABEL_16;
    }
  }
  v10 = *(_QWORD *)(SCGetClassById(a1, 655436) + 24);
  if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
  {
    if ( SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, 0) )
    {
      if ( SetSecurityDescriptorGroup(pSecurityDescriptor, pOwner, 0) )
      {
        Dacl = (struct _ACL *)GetDacl(v10);
        if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, Dacl, 0) )
        {
          Sacl = (struct _ACL *)GetSacl(v10);
          if ( SetSecurityDescriptorSacl(pSecurityDescriptor, 1, Sacl, 0) )
          {
            v13 = 0;
            *a3 = 0;
            MakeSelfRelativeSD(pSecurityDescriptor, *a4, a3);
            v14 = (void *)THAlloc_(a1, 1, *a3, 1, 0, 53085982);
            *a4 = v14;
            if ( MakeSelfRelativeSD(pSecurityDescriptor, v14, a3) )
              return v13;
            if ( *a4 )
              THFreeAux(a1, (unsigned int)*a4, v15, v16, 53085984);
            *a4 = 0;
            *a3 = 0;
          }
        }
      }
    }
  }
  v13 = GetLastError();
  if ( v13 )
  {
    LastError = GetLastError();
    v7 = 53085999;
LABEL_16:
    v9 = 8431;
    v8 = LastError;
    return (unsigned int)DoSetSvcError(5012, v9, v8, v7);
  }
  return v13;
}

```

## disassembly

```asm
0x180129df4  push    rbp
0x180129df6  push    rbx
0x180129df7  push    rsi
0x180129df8  push    rdi
0x180129df9  push    r12
0x180129dfb  push    r14
0x180129dfd  lea     rbp, [rsp-2Fh]
0x180129e02  sub     rsp, 0D8h
0x180129e09  mov     rax, cs:__security_cookie
0x180129e10  xor     rax, rsp
0x180129e13  mov     [rbp+57h+var_40], rax
0x180129e17  xorps   xmm0, xmm0
0x180129e1a  mov     [rbp+57h+cbSid], 0
0x180129e21  mov     r14, rcx
0x180129e24  mov     rdi, r9
0x180129e27  xor     ecx, ecx
0x180129e29  mov     rsi, r8
0x180129e2c  cmp     cs:gfADAM, ecx
0x180129e32  mov     eax, edx
0x180129e34  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x180129e38  mov     [rbp+57h+var_A0], rcx
0x180129e3c  movups  [rbp+57h+var_B0], xmm0
0x180129e40  jz      loc_180129FD7
0x180129e46  mov     [rbp+57h+Src], rcx
0x180129e4a  lea     r9, [rbp+57h+Src]
0x180129e4e  mov     ecx, eax
0x180129e50  lea     r8, [rbp+57h+var_98]
0x180129e54  xor     edx, edx
0x180129e56  call    NCLGetSID
0x180129e5b  test    eax, eax
0x180129e5d  jz      short loc_180129E72
0x180129e5f  mov     r9d, 32A06FBh
0x180129e65  xor     r8d, r8d
0x180129e68  mov     edx, 20EEh
0x180129e6d  jmp     loc_180129FAD
0x180129e72  mov     rcx, [rbp+57h+Src]; Src
0x180129e76  lea     r9, [rbp+57h+cbSid]
0x180129e7a  lea     r8, [rbp+57h+pOwner]
0x180129e7e  mov     edx, 200h
0x180129e83  call    MakeSid
0x180129e88  mov     edx, 0A004Ch
0x180129e8d  mov     rcx, r14
0x180129e90  call    SCGetClassById
0x180129e95  mov     r12d, 1
0x180129e9b  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180129e9f  mov     edx, r12d; dwRevision
0x180129ea2  mov     rbx, [rax+18h]
0x180129ea6  call    cs:__imp_InitializeSecurityDescriptor
0x180129eac  test    eax, eax
0x180129eae  jz      loc_180129F8D
0x180129eb4  xor     r8d, r8d; bOwnerDefaulted
0x180129eb7  lea     rdx, [rbp+57h+pOwner]; pOwner
0x180129ebb  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180129ebf  call    cs:__imp_SetSecurityDescriptorOwner
0x180129ec5  test    eax, eax
0x180129ec7  jz      loc_180129F8D
0x180129ecd  xor     r8d, r8d; bGroupDefaulted
0x180129ed0  lea     rdx, [rbp+57h+pOwner]; pGroup
0x180129ed4  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180129ed8  call    cs:__imp_SetSecurityDescriptorGroup
0x180129ede  test    eax, eax
0x180129ee0  jz      loc_180129F8D
0x180129ee6  mov     rcx, rbx
0x180129ee9  call    GetDacl
0x180129eee  mov     r8, rax; pDacl
0x180129ef1  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180129ef5  xor     r9d, r9d; bDaclDefaulted
0x180129ef8  mov     edx, r12d; bDaclPresent
0x180129efb  call    cs:__imp_SetSecurityDescriptorDacl
0x180129f01  test    eax, eax
0x180129f03  jz      loc_180129F8D
0x180129f09  mov     rcx, rbx
0x180129f0c  call    GetSacl
0x180129f11  mov     r8, rax; pSacl
0x180129f14  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180129f18  xor     r9d, r9d; bSaclDefaulted
0x180129f1b  mov     edx, r12d; bSaclPresent
0x180129f1e  call    cs:__imp_SetSecurityDescriptorSacl
0x180129f24  test    eax, eax
0x180129f26  jz      short loc_180129F8D
0x180129f28  xor     ebx, ebx
0x180129f2a  lea     rcx, [rbp+57h+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x180129f2e  mov     [rsi], ebx
0x180129f30  mov     r8, rsi; lpdwBufferLength
0x180129f33  mov     rdx, [rdi]; pSelfRelativeSecurityDescriptor
0x180129f36  call    cs:__imp_MakeSelfRelativeSD
0x180129f3c  mov     r8d, [rsi]
0x180129f3f  mov     r9d, r12d
0x180129f42  mov     edx, r12d
0x180129f45  mov     [rsp+100h+var_D8], 32A071Eh
0x180129f4d  mov     rcx, r14
0x180129f50  mov     [rsp+100h+var_E0], ebx
0x180129f54  call    THAlloc_
0x180129f59  mov     r8, rsi; lpdwBufferLength
0x180129f5c  mov     [rdi], rax
0x180129f5f  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x180129f62  lea     rcx, [rbp+57h+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x180129f66  call    cs:__imp_MakeSelfRelativeSD
0x180129f6c  test    eax, eax
0x180129f6e  jnz     short loc_180129FB9
0x180129f70  mov     rdx, [rdi]
0x180129f73  test    rdx, rdx
0x180129f76  jz      short loc_180129F88
0x180129f78  mov     rcx, r14
0x180129f7b  mov     [rsp+100h+var_E0], 32A0720h
0x180129f83  call    THFreeAux
0x180129f88  mov     [rdi], rbx
0x180129f8b  mov     [rsi], ebx
0x180129f8d  call    cs:__imp_GetLastError
0x180129f93  mov     ebx, eax
0x180129f95  test    eax, eax
0x180129f97  jz      short loc_180129FB9
0x180129f99  call    cs:__imp_GetLastError
0x180129f9f  mov     r9d, 32A072Fh
0x180129fa5  mov     edx, 20EFh
0x180129faa  mov     r8d, eax
0x180129fad  mov     ecx, 1394h
0x180129fb2  call    DoSetSvcError
0x180129fb7  mov     ebx, eax
0x180129fb9  mov     eax, ebx
0x180129fbb  mov     rcx, [rbp+57h+var_40]
0x180129fbf  xor     rcx, rsp; StackCookie
0x180129fc2  call    __security_check_cookie
0x180129fc7  add     rsp, 0D8h
0x180129fce  pop     r14
0x180129fd0  pop     r12
0x180129fd2  pop     rdi
0x180129fd3  pop     rsi
0x180129fd4  pop     rbx
0x180129fd5  pop     rbp
0x180129fd6  retn
0x180129fd7  mov     rdx, cs:qword_18052B2C0
0x180129fde  lea     r9, [rbp+57h+cbSid]; cbSid
0x180129fe2  add     rdx, 18h; DomainSid
0x180129fe6  mov     [rbp+57h+cbSid], 48h ; 'H'
0x180129fed  lea     r8, [rbp+57h+pOwner]; pSid
0x180129ff1  mov     ecx, 29h ; ')'; WellKnownSidType
0x180129ff6  call    cs:__imp_CreateWellKnownSid
0x180129ffc  test    eax, eax
0x180129ffe  jnz     loc_180129E88
0x18012a004  call    cs:__imp_GetLastError
0x18012a00a  mov     r9d, 32A070Ah
0x18012a010  jmp     short loc_180129FA5
```
