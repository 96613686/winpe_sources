# ATL::CSecurityDescriptor::Attach(void *)

- ea: `0x18003acc0`
- end: `0x18003af3e`
- name: `?Attach@CSecurityDescriptor@ATL@@QEAAJPEAX@Z`
- size: `638`
- prototype: `__int64 __fastcall(ATL::CSecurityDescriptor *__hidden this, PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18003f8f8`

## callees

- `0x180004740`
- `0x1800070c4`
- `0x18003acc0`
- `0x18003c6a0`
- `0x18003fbac`
- `0x18004537c`
- `0x18004548c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003aefb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003af0e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003aefb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003af0e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003ad51`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003ae08`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003ad51`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003ae08`
- `ADVAPI32!IsValidAcl` at `0x18003ada4`
- `ADVAPI32!IsValidAcl` at `0x18003ae55`
- `ADVAPI32!IsValidAcl` at `0x18003ada4`
- `ADVAPI32!IsValidAcl` at `0x18003ae55`
- `ADVAPI32!SetSecurityDescriptorSacl` at `0x18003ae77`
- `ADVAPI32!SetSecurityDescriptorSacl` at `0x18003ae77`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x18003ae8c`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x18003ae8c`
- `ADVAPI32!InitializeAcl` at `0x18003ad7b`
- `ADVAPI32!InitializeAcl` at `0x18003ae2c`
- `ADVAPI32!InitializeAcl` at `0x18003ad7b`
- `ADVAPI32!InitializeAcl` at `0x18003ae2c`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x18003ade3`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x18003ade3`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18003adc6`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18003adc6`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18003ad2c`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18003ad2c`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x18003aeb5`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x18003aeb5`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18003acff`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18003aed6`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18003acff`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18003aed6`

## pseudocode

```c
__int64 __fastcall ATL::CSecurityDescriptor::Attach(PACL *this, PSECURITY_DESCRIPTOR pSecurityDescriptor)
{
  __int64 result; // rax
  ACL *v5; // rax
  int Error; // edi
  ACL *v7; // rax
  PACL v8; // rcx
  PACL v9; // rcx
  PACL pDacl; // [rsp+20h] [rbp-20h] BYREF
  PACL pSacl; // [rsp+28h] [rbp-18h] BYREF
  PSID pOwner; // [rsp+30h] [rbp-10h] BYREF
  PSID pGroup; // [rsp+38h] [rbp-8h] BYREF
  BOOL bDaclDefaulted; // [rsp+78h] [rbp+38h] BYREF
  BOOL bDaclPresent; // [rsp+80h] [rbp+40h] BYREF
  BOOL bSaclPresent; // [rsp+88h] [rbp+48h] BYREF

  pDacl = 0;
  pSacl = 0;
  bDaclPresent = 0;
  bSaclPresent = 0;
  bDaclDefaulted = 0;
  pOwner = 0;
  pGroup = 0;
  if ( !pSecurityDescriptor || !IsValidSecurityDescriptor(pSecurityDescriptor) )
    return 2147942487LL;
  result = ATL::CSecurityDescriptor::Initialize((ATL::CSecurityDescriptor *)this);
  if ( (int)result < 0 )
    return result;
  if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    goto LABEL_28;
  if ( !bDaclPresent )
  {
LABEL_13:
    if ( GetSecurityDescriptorSacl(pSecurityDescriptor, &bSaclPresent, &pSacl, &bDaclDefaulted) )
    {
      if ( !bSaclPresent )
        goto LABEL_24;
      if ( !pSacl )
        goto LABEL_39;
      v7 = (ACL *)malloc(pSacl->AclSize);
      this[4] = v7;
      if ( !v7 )
        goto LABEL_8;
      if ( InitializeAcl(v7, pSacl->AclSize, 2u) )
      {
        Error = ATL::CSecurityDescriptor::CopyACL(this[4], pSacl);
        if ( Error < 0 )
          goto LABEL_29;
        if ( IsValidAcl(this[4]) )
        {
LABEL_39:
          if ( SetSecurityDescriptorSacl(*this, this[4] != 0, this[4], bDaclDefaulted) )
          {
LABEL_24:
            if ( GetSecurityDescriptorOwner(pSecurityDescriptor, &pOwner, &bDaclDefaulted)
              && ATL::CSecurityDescriptor::SetOwner((ATL::CSecurityDescriptor *)this, pOwner, bDaclDefaulted) >= 0
              && GetSecurityDescriptorGroup(pSecurityDescriptor, &pGroup, &bDaclDefaulted)
              && ATL::CSecurityDescriptor::SetGroup((ATL::CSecurityDescriptor *)this, pGroup, bDaclDefaulted) >= 0 )
            {
              if ( IsValidSecurityDescriptor(*this) )
                return 0;
              Error = -2147467259;
              goto LABEL_29;
            }
          }
        }
      }
    }
LABEL_28:
    Error = ATL::AtlHresultFromLastError();
    goto LABEL_29;
  }
  if ( !pDacl )
  {
LABEL_12:
    if ( !SetSecurityDescriptorDacl(*this, this[3] != 0, this[3], bDaclDefaulted) )
      goto LABEL_28;
    goto LABEL_13;
  }
  v5 = (ACL *)malloc(pDacl->AclSize);
  this[3] = v5;
  if ( v5 )
  {
    if ( !InitializeAcl(v5, pDacl->AclSize, 2u) )
      goto LABEL_28;
    Error = ATL::CSecurityDescriptor::CopyACL(this[3], pDacl);
    if ( Error < 0 )
      goto LABEL_29;
    if ( !IsValidAcl(this[3]) )
      goto LABEL_28;
    goto LABEL_12;
  }
LABEL_8:
  Error = -2147024882;
LABEL_29:
  v8 = this[3];
  if ( v8 )
  {
    free(v8);
    this[3] = 0;
  }
  v9 = this[4];
  if ( v9 )
  {
    free(v9);
    this[4] = 0;
  }
  if ( *this )
  {
    operator delete(*this, 0);
    *this = 0;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18003acc0  push    rbp
0x18003acc2  push    rbx
0x18003acc3  push    rsi
0x18003acc4  push    rdi
0x18003acc5  push    r14
0x18003acc7  mov     rbp, rsp
0x18003acca  sub     rsp, 40h
0x18003acce  xor     r14d, r14d
0x18003acd1  mov     rsi, rdx
0x18003acd4  mov     [rbp+pDacl], r14
0x18003acd8  mov     rbx, rcx
0x18003acdb  mov     [rbp+pSacl], r14
0x18003acdf  mov     [rbp+bDaclPresent], r14d
0x18003ace3  mov     [rbp+bSaclPresent], r14d
0x18003ace7  mov     [rbp+bDaclDefaulted], r14d
0x18003aceb  mov     [rbp+pOwner], r14
0x18003acef  mov     [rbp+pGroup], r14
0x18003acf3  test    rdx, rdx
0x18003acf6  jz      loc_18003AF2E
0x18003acfc  mov     rcx, rdx; pSecurityDescriptor
0x18003acff  call    cs:__imp_IsValidSecurityDescriptor
0x18003ad05  test    eax, eax
0x18003ad07  jz      loc_18003AF2E
0x18003ad0d  mov     rcx, rbx; this
0x18003ad10  call    ?Initialize@CSecurityDescriptor@ATL@@QEAAJXZ; ATL::CSecurityDescriptor::Initialize(void)
0x18003ad15  test    eax, eax
0x18003ad17  js      loc_18003AF33
0x18003ad1d  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18003ad21  mov     rcx, rsi; pSecurityDescriptor
0x18003ad24  lea     r8, [rbp+pDacl]; pDacl
0x18003ad28  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18003ad2c  call    cs:__imp_GetSecurityDescriptorDacl
0x18003ad32  test    eax, eax
0x18003ad34  jz      loc_18003AEEB
0x18003ad3a  cmp     [rbp+bDaclPresent], r14d
0x18003ad3e  jz      loc_18003ADD4
0x18003ad44  mov     rax, [rbp+pDacl]
0x18003ad48  test    rax, rax
0x18003ad4b  jz      short loc_18003ADB2
0x18003ad4d  movzx   ecx, word ptr [rax+2]; Size
0x18003ad51  call    cs:__imp_malloc
0x18003ad57  mov     [rbx+18h], rax
0x18003ad5b  mov     rcx, rax; pAcl
0x18003ad5e  test    rax, rax
0x18003ad61  jnz     short loc_18003AD6D
0x18003ad63  mov     edi, 8007000Eh
0x18003ad68  jmp     loc_18003AEF2
0x18003ad6d  mov     rax, [rbp+pDacl]
0x18003ad71  mov     r8d, 2; dwAclRevision
0x18003ad77  movzx   edx, word ptr [rax+2]; nAclLength
0x18003ad7b  call    cs:__imp_InitializeAcl
0x18003ad81  test    eax, eax
0x18003ad83  jz      loc_18003AEEB
0x18003ad89  mov     rdx, [rbp+pDacl]; PACL
0x18003ad8d  mov     rcx, [rbx+18h]; pAcl
0x18003ad91  call    ?CopyACL@CSecurityDescriptor@ATL@@SAJPEAU_ACL@@0@Z; ATL::CSecurityDescriptor::CopyACL(_ACL *,_ACL *)
0x18003ad96  mov     edi, eax
0x18003ad98  test    eax, eax
0x18003ad9a  js      loc_18003AEF2
0x18003ada0  mov     rcx, [rbx+18h]; pAcl
0x18003ada4  call    cs:__imp_IsValidAcl
0x18003adaa  test    eax, eax
0x18003adac  jz      loc_18003AEEB
0x18003adb2  mov     r8, [rbx+18h]; pDacl
0x18003adb6  mov     edx, r14d
0x18003adb9  mov     r9d, [rbp+bDaclDefaulted]; bDaclDefaulted
0x18003adbd  test    r8, r8
0x18003adc0  mov     rcx, [rbx]; pSecurityDescriptor
0x18003adc3  setnz   dl; bDaclPresent
0x18003adc6  call    cs:__imp_SetSecurityDescriptorDacl
0x18003adcc  test    eax, eax
0x18003adce  jz      loc_18003AEEB
0x18003add4  lea     r9, [rbp+bDaclDefaulted]; lpbSaclDefaulted
0x18003add8  mov     rcx, rsi; pSecurityDescriptor
0x18003addb  lea     r8, [rbp+pSacl]; pSacl
0x18003addf  lea     rdx, [rbp+bSaclPresent]; lpbSaclPresent
0x18003ade3  call    cs:__imp_GetSecurityDescriptorSacl
0x18003ade9  test    eax, eax
0x18003adeb  jz      loc_18003AEEB
0x18003adf1  cmp     [rbp+bSaclPresent], r14d
0x18003adf5  jz      loc_18003AE81
0x18003adfb  mov     rax, [rbp+pSacl]
0x18003adff  test    rax, rax
0x18003ae02  jz      short loc_18003AE63
0x18003ae04  movzx   ecx, word ptr [rax+2]; Size
0x18003ae08  call    cs:__imp_malloc
0x18003ae0e  mov     [rbx+20h], rax
0x18003ae12  mov     rcx, rax; pAcl
0x18003ae15  test    rax, rax
0x18003ae18  jz      loc_18003AD63
0x18003ae1e  mov     rax, [rbp+pSacl]
0x18003ae22  mov     r8d, 2; dwAclRevision
0x18003ae28  movzx   edx, word ptr [rax+2]; nAclLength
0x18003ae2c  call    cs:__imp_InitializeAcl
0x18003ae32  test    eax, eax
0x18003ae34  jz      loc_18003AEEB
0x18003ae3a  mov     rdx, [rbp+pSacl]; PACL
0x18003ae3e  mov     rcx, [rbx+20h]; pAcl
0x18003ae42  call    ?CopyACL@CSecurityDescriptor@ATL@@SAJPEAU_ACL@@0@Z; ATL::CSecurityDescriptor::CopyACL(_ACL *,_ACL *)
0x18003ae47  mov     edi, eax
0x18003ae49  test    eax, eax
0x18003ae4b  js      loc_18003AEF2
0x18003ae51  mov     rcx, [rbx+20h]; pAcl
0x18003ae55  call    cs:__imp_IsValidAcl
0x18003ae5b  test    eax, eax
0x18003ae5d  jz      loc_18003AEEB
0x18003ae63  mov     r8, [rbx+20h]; pSacl
0x18003ae67  mov     edx, r14d
0x18003ae6a  mov     r9d, [rbp+bDaclDefaulted]; bSaclDefaulted
0x18003ae6e  test    r8, r8
0x18003ae71  mov     rcx, [rbx]; pSecurityDescriptor
0x18003ae74  setnz   dl; bSaclPresent
0x18003ae77  call    cs:__imp_SetSecurityDescriptorSacl
0x18003ae7d  test    eax, eax
0x18003ae7f  jz      short loc_18003AEEB
0x18003ae81  lea     r8, [rbp+bDaclDefaulted]; lpbOwnerDefaulted
0x18003ae85  mov     rcx, rsi; pSecurityDescriptor
0x18003ae88  lea     rdx, [rbp+pOwner]; pOwner
0x18003ae8c  call    cs:__imp_GetSecurityDescriptorOwner
0x18003ae92  test    eax, eax
0x18003ae94  jz      short loc_18003AEEB
0x18003ae96  mov     r8d, [rbp+bDaclDefaulted]; int
0x18003ae9a  mov     rcx, rbx; this
0x18003ae9d  mov     rdx, [rbp+pOwner]; void *
0x18003aea1  call    ?SetOwner@CSecurityDescriptor@ATL@@QEAAJPEAXH@Z; ATL::CSecurityDescriptor::SetOwner(void *,int)
0x18003aea6  test    eax, eax
0x18003aea8  js      short loc_18003AEEB
0x18003aeaa  lea     r8, [rbp+bDaclDefaulted]; lpbGroupDefaulted
0x18003aeae  mov     rcx, rsi; pSecurityDescriptor
0x18003aeb1  lea     rdx, [rbp+pGroup]; pGroup
0x18003aeb5  call    cs:__imp_GetSecurityDescriptorGroup
0x18003aebb  test    eax, eax
0x18003aebd  jz      short loc_18003AEEB
0x18003aebf  mov     r8d, [rbp+bDaclDefaulted]; int
0x18003aec3  mov     rcx, rbx; this
0x18003aec6  mov     rdx, [rbp+pGroup]; void *
0x18003aeca  call    ?SetGroup@CSecurityDescriptor@ATL@@QEAAJPEAXH@Z; ATL::CSecurityDescriptor::SetGroup(void *,int)
0x18003aecf  test    eax, eax
0x18003aed1  js      short loc_18003AEEB
0x18003aed3  mov     rcx, [rbx]; pSecurityDescriptor
0x18003aed6  call    cs:__imp_IsValidSecurityDescriptor
0x18003aedc  test    eax, eax
0x18003aede  jnz     short loc_18003AEE7
0x18003aee0  mov     edi, 80004005h
0x18003aee5  jmp     short loc_18003AEF2
0x18003aee7  xor     eax, eax
0x18003aee9  jmp     short loc_18003AF33
0x18003aeeb  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18003aef0  mov     edi, eax
0x18003aef2  mov     rcx, [rbx+18h]; Block
0x18003aef6  test    rcx, rcx
0x18003aef9  jz      short loc_18003AF05
0x18003aefb  call    cs:__imp_free
0x18003af01  mov     [rbx+18h], r14
0x18003af05  mov     rcx, [rbx+20h]; Block
0x18003af09  test    rcx, rcx
0x18003af0c  jz      short loc_18003AF18
0x18003af0e  call    cs:__imp_free
0x18003af14  mov     [rbx+20h], r14
0x18003af18  mov     rcx, [rbx]; void *
0x18003af1b  test    rcx, rcx
0x18003af1e  jz      short loc_18003AF2A
0x18003af20  xor     edx, edx; unsigned __int64
0x18003af22  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003af27  mov     [rbx], r14
0x18003af2a  mov     eax, edi
0x18003af2c  jmp     short loc_18003AF33
0x18003af2e  mov     eax, 80070057h
0x18003af33  add     rsp, 40h
0x18003af37  pop     r14
0x18003af39  pop     rdi
0x18003af3a  pop     rsi
0x18003af3b  pop     rbx
0x18003af3c  pop     rbp
0x18003af3d  retn
```
