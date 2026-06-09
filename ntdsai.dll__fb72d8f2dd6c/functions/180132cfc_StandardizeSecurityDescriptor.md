# StandardizeSecurityDescriptor

- ea: `0x180132cfc`
- end: `0x180133024`
- name: `StandardizeSecurityDescriptor`
- size: `808`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003f8c8`
- `0x18005a0c4`
- `0x1800c279c`
- `0x1803a37fc`

## callees

- `0x180021aaf`
- `0x1801329d4`
- `0x180132ac8`
- `0x180132be4`
- `0x180132cfc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180132d9b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180132d9b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180132d6d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180132d6d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180132d86`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180132d86`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x180132db0`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x180132db0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180132ded`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180132ded`
- `ntdll!RtlAllocateHeap` at `0x180132ee5`
- `ntdll!RtlAllocateHeap` at `0x180132ee5`
- `ntdll!RtlFreeHeap` at `0x180133014`
- `ntdll!RtlFreeHeap` at `0x180133014`
- `ntdll!RtlLengthSid` at `0x180132fb4`
- `ntdll!RtlLengthSid` at `0x180132fdd`
- `ntdll!RtlLengthSid` at `0x180132fb4`
- `ntdll!RtlLengthSid` at `0x180132fdd`

## pseudocode

```c
__int64 __fastcall StandardizeSecurityDescriptor(__int16 *pSecurityDescriptor, _DWORD *a2, _DWORD *a3)
{
  unsigned int v3; // edi
  unsigned int v6; // r15d
  unsigned int v7; // r13d
  PACL v8; // rax
  DWORD v9; // ecx
  bool v11; // cc
  BOOL v12; // r12d
  unsigned int v13; // r14d
  PVOID Heap; // r14
  PACL v15; // rdi
  _DWORD *v16; // rdi
  ULONG v17; // eax
  PSID v18; // rcx
  ULONG v19; // eax
  unsigned int v20; // [rsp+40h] [rbp-29h] BYREF
  unsigned int v21; // [rsp+44h] [rbp-25h] BYREF
  int v22; // [rsp+48h] [rbp-21h]
  int v23; // [rsp+4Ch] [rbp-1Dh] BYREF
  int v24; // [rsp+50h] [rbp-19h] BYREF
  PACL pSacl; // [rsp+58h] [rbp-11h] BYREF
  PACL pDacl; // [rsp+60h] [rbp-9h] BYREF
  PSID pOwner; // [rsp+68h] [rbp-1h] BYREF
  PSID pGroup; // [rsp+70h] [rbp+7h] BYREF
  int v29; // [rsp+78h] [rbp+Fh] BYREF
  int v30; // [rsp+7Ch] [rbp+13h] BYREF
  WINBOOL bDaclPresent; // [rsp+D0h] [rbp+67h] BYREF
  _DWORD *v32; // [rsp+D8h] [rbp+6Fh]
  struct _ACL v33; // [rsp+E0h] [rbp+77h] BYREF
  unsigned int v34; // [rsp+E8h] [rbp+7Fh] BYREF

  v32 = a2;
  v3 = 0;
  *a2 = 0;
  *a3 = 0;
  v6 = 0;
  v7 = 0;
  pDacl = 0;
  pSacl = 0;
  pOwner = 0;
  pGroup = 0;
  bDaclPresent = 0;
  v23 = 0;
  v24 = 0;
  v34 = 0;
  v20 = 0;
  v29 = 0;
  v30 = 0;
  *(_DWORD *)&v33.AclRevision = 0;
  v21 = 0;
  if ( pSecurityDescriptor[1] >= 0 )
    goto LABEL_12;
  if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclPresent)
    || !GetSecurityDescriptorSacl(pSecurityDescriptor, &bDaclPresent, &pSacl, &bDaclPresent)
    || !GetSecurityDescriptorOwner(pSecurityDescriptor, &pOwner, &bDaclPresent)
    || !GetSecurityDescriptorGroup(pSecurityDescriptor, &pGroup, &bDaclPresent) )
  {
    return 0;
  }
  if ( !pOwner || !pGroup || pGroup <= pOwner )
    goto LABEL_12;
  v8 = pSacl;
  if ( pSacl )
  {
    if ( !pDacl )
    {
      v11 = pOwner <= pSacl;
      goto LABEL_18;
    }
    if ( pDacl <= pSacl )
    {
LABEL_12:
      v9 = 87;
LABEL_13:
      SetLastError(v9);
      return 0;
    }
  }
  else if ( !pDacl )
  {
    goto LABEL_19;
  }
  v11 = pOwner <= pDacl;
LABEL_18:
  if ( v11 )
    goto LABEL_12;
LABEL_19:
  v12 = 0;
  v13 = 0;
  if ( pDacl && pDacl->AceCount > 1u )
  {
    if ( !(unsigned int)ComputeAclInfo(
                          (_DWORD)pDacl,
                          (unsigned int)&v24,
                          (unsigned int)&v23,
                          (unsigned int)&v20,
                          (__int64)&v34) )
      return 0;
    v13 = v34;
    v3 = v20;
    v8 = pSacl;
    v12 = v20 > 1;
  }
  v22 = 0;
  if ( v8 && v8->AceCount > 1u )
  {
    if ( !(unsigned int)ComputeAclInfo(
                          (_DWORD)v8,
                          (unsigned int)&v30,
                          (unsigned int)&v29,
                          (unsigned int)&v21,
                          (__int64)&v33) )
      return 0;
    v7 = v21;
    v6 = *(_DWORD *)&v33.AclRevision;
    if ( v21 > 1 )
    {
      v22 = 1;
      if ( v13 < *(_DWORD *)&v33.AclRevision )
        v13 = *(_DWORD *)&v33.AclRevision;
      if ( v3 < v21 )
        v3 = v21;
    }
  }
  if ( v3 <= 1 )
    return 1;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, ((v13 + 7LL) & 0xFFFFFFFFFFFFFFF8uLL) + 8LL * v3);
  if ( !Heap )
  {
    v9 = 8;
    goto LABEL_13;
  }
  if ( v22 )
  {
    v15 = pSacl;
    v33 = *pSacl;
    StandardizeAcl(pSacl, &pSacl[1], v7, v6, Heap, &pSacl[1], a3);
    if ( *a3 )
    {
      if ( v33.AclSize - (unsigned __int64)v6 != 8 )
        memmove_0(
          (char *)&v15[1] + v6 - (unsigned __int64)(unsigned int)*a3,
          (char *)&v15[1] + v6,
          v33.AclSize - (unsigned __int64)v6 - 8);
    }
  }
  if ( v12 || *a3 )
  {
    v16 = v32;
    StandardizeDacl((_DWORD)pDacl, v24, v23, v20, v34, (__int64)Heap, (__int64)pDacl - (unsigned int)*a3, (__int64)v32);
    if ( *a3 )
      *((_DWORD *)pSecurityDescriptor + 4) -= *a3;
  }
  else
  {
    v16 = v32;
  }
  if ( *a3 + *v16 )
  {
    v17 = RtlLengthSid(pOwner);
    memmove_0((char *)pOwner - (unsigned int)(*a3 + *v16), pOwner, v17);
    v18 = pGroup;
    *((_DWORD *)pSecurityDescriptor + 1) -= *a3 + *v16;
    v19 = RtlLengthSid(v18);
    memmove_0((char *)pGroup - (unsigned int)(*a3 + *v16), pGroup, v19);
    *((_DWORD *)pSecurityDescriptor + 2) -= *a3 + *v16;
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return 1;
}

```

## disassembly

```asm
0x180132cfc  mov     [rsp-8+arg_8], rdx
0x180132d01  push    rbp
0x180132d02  push    rbx
0x180132d03  push    rsi
0x180132d04  push    rdi
0x180132d05  push    r12
0x180132d07  push    r13
0x180132d09  push    r14
0x180132d0b  push    r15
0x180132d0d  lea     rbp, [rsp-1Fh]
0x180132d12  sub     rsp, 88h
0x180132d19  xor     edi, edi
0x180132d1b  mov     rsi, r8
0x180132d1e  mov     [rdx], edi
0x180132d20  mov     rbx, rcx
0x180132d23  mov     [r8], edi
0x180132d26  mov     r15d, edi
0x180132d29  mov     r13d, edi
0x180132d2c  mov     [rbp+57h+pDacl], rdi
0x180132d30  mov     [rbp+57h+pSacl], rdi
0x180132d34  mov     [rbp+57h+pOwner], rdi
0x180132d38  mov     [rbp+57h+pGroup], rdi
0x180132d3c  mov     [rbp+57h+bDaclPresent], edi
0x180132d3f  mov     [rbp+57h+var_74], edi
0x180132d42  mov     [rbp+57h+var_70], edi
0x180132d45  mov     [rbp+57h+arg_18], edi
0x180132d48  mov     [rbp+57h+var_80], edi
0x180132d4b  mov     [rbp+57h+var_48], edi
0x180132d4e  mov     [rbp+57h+var_44], edi
0x180132d51  mov     dword ptr [rbp+57h+arg_10], edi
0x180132d54  mov     [rbp+57h+var_7C], edi
0x180132d57  cmp     [rcx+2], di
0x180132d5b  jge     loc_180132DE8
0x180132d61  lea     r9, [rbp+57h+bDaclPresent]; lpbDaclDefaulted
0x180132d65  lea     r8, [rbp+57h+pDacl]; pDacl
0x180132d69  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180132d6d  call    cs:__imp_GetSecurityDescriptorDacl
0x180132d73  test    eax, eax
0x180132d75  jz      short loc_180132DF3
0x180132d77  lea     r9, [rbp+57h+bDaclPresent]; lpbSaclDefaulted
0x180132d7b  mov     rcx, rbx; pSecurityDescriptor
0x180132d7e  lea     r8, [rbp+57h+pSacl]; pSacl
0x180132d82  lea     rdx, [rbp+57h+bDaclPresent]; lpbSaclPresent
0x180132d86  call    cs:__imp_GetSecurityDescriptorSacl
0x180132d8c  test    eax, eax
0x180132d8e  jz      short loc_180132DF3
0x180132d90  lea     r8, [rbp+57h+bDaclPresent]; lpbOwnerDefaulted
0x180132d94  mov     rcx, rbx; pSecurityDescriptor
0x180132d97  lea     rdx, [rbp+57h+pOwner]; pOwner
0x180132d9b  call    cs:__imp_GetSecurityDescriptorOwner
0x180132da1  test    eax, eax
0x180132da3  jz      short loc_180132DF3
0x180132da5  lea     r8, [rbp+57h+bDaclPresent]; lpbGroupDefaulted
0x180132da9  mov     rcx, rbx; pSecurityDescriptor
0x180132dac  lea     rdx, [rbp+57h+pGroup]; pGroup
0x180132db0  call    cs:__imp_GetSecurityDescriptorGroup
0x180132db6  test    eax, eax
0x180132db8  jz      short loc_180132DF3
0x180132dba  mov     rdx, [rbp+57h+pOwner]
0x180132dbe  test    rdx, rdx
0x180132dc1  jz      short loc_180132DE8
0x180132dc3  mov     rax, [rbp+57h+pGroup]
0x180132dc7  test    rax, rax
0x180132dca  jz      short loc_180132DE8
0x180132dcc  cmp     rax, rdx
0x180132dcf  jbe     short loc_180132DE8
0x180132dd1  mov     rax, [rbp+57h+pSacl]
0x180132dd5  mov     rcx, [rbp+57h+pDacl]
0x180132dd9  test    rax, rax
0x180132ddc  jz      short loc_180132E0E
0x180132dde  test    rcx, rcx
0x180132de1  jz      short loc_180132E09
0x180132de3  cmp     rcx, rax
0x180132de6  ja      short loc_180132E13
0x180132de8  mov     ecx, 57h ; 'W'; dwErrCode
0x180132ded  call    cs:__imp_SetLastError
0x180132df3  xor     eax, eax
0x180132df5  add     rsp, 88h
0x180132dfc  pop     r15
0x180132dfe  pop     r14
0x180132e00  pop     r13
0x180132e02  pop     r12
0x180132e04  pop     rdi
0x180132e05  pop     rsi
0x180132e06  pop     rbx
0x180132e07  pop     rbp
0x180132e08  retn
0x180132e09  cmp     rdx, rax
0x180132e0c  jmp     short loc_180132E16
0x180132e0e  test    rcx, rcx
0x180132e11  jz      short loc_180132E18
0x180132e13  cmp     rdx, rcx
0x180132e16  jbe     short loc_180132DE8
0x180132e18  mov     r12d, edi
0x180132e1b  mov     r14d, edi
0x180132e1e  mov     edx, 1
0x180132e23  test    rcx, rcx
0x180132e26  jz      short loc_180132E63
0x180132e28  cmp     [rcx+4], dx
0x180132e2c  jbe     short loc_180132E63
0x180132e2e  lea     rax, [rbp+57h+arg_18]
0x180132e32  lea     r9, [rbp+57h+var_80]
0x180132e36  mov     [rsp+0C0h+var_A0], rax
0x180132e3b  lea     r8, [rbp+57h+var_74]
0x180132e3f  lea     rdx, [rbp+57h+var_70]
0x180132e43  call    ComputeAclInfo
0x180132e48  test    eax, eax
0x180132e4a  jz      short loc_180132DF3
0x180132e4c  mov     r14d, [rbp+57h+arg_18]
0x180132e50  mov     edx, 1
0x180132e55  cmp     [rbp+57h+var_80], edx
0x180132e58  mov     edi, [rbp+57h+var_80]
0x180132e5b  mov     rax, [rbp+57h+pSacl]
0x180132e5f  cmova   r12d, edx
0x180132e63  mov     [rbp+57h+var_78], r13d
0x180132e67  test    rax, rax
0x180132e6a  jz      short loc_180132EBA
0x180132e6c  cmp     [rax+4], dx
0x180132e70  jbe     short loc_180132EBA
0x180132e72  lea     rcx, [rbp+57h+arg_10]
0x180132e76  mov     [rsp+0C0h+var_A0], rcx
0x180132e7b  lea     r9, [rbp+57h+var_7C]
0x180132e7f  mov     rcx, rax
0x180132e82  lea     r8, [rbp+57h+var_48]
0x180132e86  lea     rdx, [rbp+57h+var_44]
0x180132e8a  call    ComputeAclInfo
0x180132e8f  test    eax, eax
0x180132e91  jz      loc_180132DF3
0x180132e97  mov     r13d, [rbp+57h+var_7C]
0x180132e9b  mov     edx, 1
0x180132ea0  mov     r15d, dword ptr [rbp+57h+arg_10]
0x180132ea4  cmp     r13d, edx
0x180132ea7  jbe     short loc_180132EBA
0x180132ea9  cmp     r14d, r15d
0x180132eac  mov     [rbp+57h+var_78], edx
0x180132eaf  cmovb   r14d, r15d
0x180132eb3  cmp     edi, r13d
0x180132eb6  cmovb   edi, r13d
0x180132eba  cmp     edi, edx
0x180132ebc  ja      short loc_180132EC5
0x180132ebe  mov     eax, edx
0x180132ec0  jmp     loc_180132DF5
0x180132ec5  mov     eax, edi
0x180132ec7  xor     edx, edx; Flags
0x180132ec9  mov     ecx, r14d
0x180132ecc  add     rcx, 7
0x180132ed0  and     rcx, 0FFFFFFFFFFFFFFF8h
0x180132ed4  lea     r8, [rcx+rax*8]; Size
0x180132ed8  mov     rcx, gs:60h
0x180132ee1  mov     rcx, [rcx+30h]; HeapHandle
0x180132ee5  call    cs:__imp_RtlAllocateHeap
0x180132eeb  mov     r14, rax
0x180132eee  test    rax, rax
0x180132ef1  jnz     short loc_180132EFB
0x180132ef3  lea     ecx, [rax+8]
0x180132ef6  jmp     loc_180132DED
0x180132efb  cmp     [rbp+57h+var_78], 0
0x180132eff  jz      short loc_180132F5B
0x180132f01  mov     rdi, [rbp+57h+pSacl]
0x180132f05  mov     r9d, r15d
0x180132f08  mov     [rsp+0C0h+var_90], rsi
0x180132f0d  mov     r8d, r13d
0x180132f10  mov     rcx, rdi
0x180132f13  mov     rax, [rdi]
0x180132f16  lea     rdx, [rdi+8]
0x180132f1a  mov     [rsp+0C0h+var_98], rdx
0x180132f1f  mov     [rsp+0C0h+var_A0], r14
0x180132f24  mov     [rbp+57h+arg_10], rax
0x180132f28  call    StandardizeAcl
0x180132f2d  cmp     dword ptr [rsi], 0
0x180132f30  jz      short loc_180132F5B
0x180132f32  movzx   r8d, word ptr [rbp+57h+arg_10+2]
0x180132f37  mov     ecx, r15d
0x180132f3a  sub     r8, rcx
0x180132f3d  add     r8, 0FFFFFFFFFFFFFFF8h; Size
0x180132f41  jz      short loc_180132F5B
0x180132f43  mov     eax, [rsi]
0x180132f45  lea     rdx, [rdi+8]
0x180132f49  add     rdx, rcx; Src
0x180132f4c  sub     rcx, rax
0x180132f4f  add     rcx, 8
0x180132f53  add     rcx, rdi; void *
0x180132f56  call    memmove_0
0x180132f5b  test    r12d, r12d
0x180132f5e  jnz     short loc_180132F65
0x180132f60  cmp     [rsi], r12d
0x180132f63  jz      short loc_180132FA6
0x180132f65  mov     eax, [rsi]
0x180132f67  mov     rcx, [rbp+57h+pDacl]
0x180132f6b  mov     rdi, [rbp+57h+arg_8]
0x180132f6f  mov     r10, rcx
0x180132f72  mov     r9d, [rbp+57h+var_80]
0x180132f76  sub     r10, rax
0x180132f79  mov     eax, [rbp+57h+arg_18]
0x180132f7c  mov     r8d, [rbp+57h+var_74]
0x180132f80  mov     edx, [rbp+57h+var_70]
0x180132f83  mov     [rsp+0C0h+var_88], rdi
0x180132f88  mov     [rsp+0C0h+var_90], r10
0x180132f8d  mov     [rsp+0C0h+var_98], r14
0x180132f92  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180132f96  call    StandardizeDacl
0x180132f9b  mov     eax, [rsi]
0x180132f9d  test    eax, eax
0x180132f9f  jz      short loc_180132FAA
0x180132fa1  sub     [rbx+10h], eax
0x180132fa4  jmp     short loc_180132FAA
0x180132fa6  mov     rdi, [rbp+57h+arg_8]
0x180132faa  mov     eax, [rdi]
0x180132fac  add     eax, [rsi]
0x180132fae  jz      short loc_180133002
0x180132fb0  mov     rcx, [rbp+57h+pOwner]; Sid
0x180132fb4  call    cs:__imp_RtlLengthSid
0x180132fba  mov     r9d, [rdi]
0x180132fbd  mov     rdx, [rbp+57h+pOwner]; Src
0x180132fc1  add     r9d, [rsi]
0x180132fc4  mov     rcx, rdx
0x180132fc7  sub     rcx, r9; void *
0x180132fca  mov     r8d, eax; Size
0x180132fcd  call    memmove_0
0x180132fd2  mov     eax, [rdi]
0x180132fd4  add     eax, [rsi]
0x180132fd6  mov     rcx, [rbp+57h+pGroup]; Sid
0x180132fda  sub     [rbx+4], eax
0x180132fdd  call    cs:__imp_RtlLengthSid
0x180132fe3  mov     r9d, [rdi]
0x180132fe6  mov     rdx, [rbp+57h+pGroup]; Src
0x180132fea  add     r9d, [rsi]
0x180132fed  mov     rcx, rdx
0x180132ff0  sub     rcx, r9; void *
0x180132ff3  mov     r8d, eax; Size
0x180132ff6  call    memmove_0
0x180132ffb  mov     eax, [rdi]
0x180132ffd  add     eax, [rsi]
0x180132fff  sub     [rbx+8], eax
0x180133002  mov     rcx, gs:60h
0x18013300b  mov     r8, r14; P
0x18013300e  xor     edx, edx; Flags
0x180133010  mov     rcx, [rcx+30h]; HeapHandle
0x180133014  call    cs:__imp_RtlFreeHeap
0x18013301a  mov     eax, 1
0x18013301f  jmp     loc_180132DF5
```
