# LockRegkeyFromUserAccess(HKEY__ *,_TOKEN_USER *)

- ea: `0x180082bb8`
- end: `0x180082e13`
- name: `?LockRegkeyFromUserAccess@@YAXPEAUHKEY__@@PEAU_TOKEN_USER@@@Z`
- size: `603`
- prototype: `void __fastcall(HKEY handle, struct _TOKEN_USER *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180055e70`
- `0x180055f10`

## callees

- `0x1800580e6`
- `0x1800597b0`
- `0x180082bb8`
- `0x180083bc2`
- `0x180083c10`

## import_xrefs

- `msvcrt!_errno` at `0x180082d19`
- `msvcrt!_errno` at `0x180082d19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180082dd7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180082de6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180082dd7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180082de6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180082cc3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180082cc3`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180082d6b`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180082d6b`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180082d3e`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180082d8b`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180082d3e`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180082d8b`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180082c5c`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180082c83`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180082c5c`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180082c83`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180082cdd`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180082cdd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180082c96`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180082c96`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180082c2a`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180082c2a`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180082dce`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180082dce`

## pseudocode

```c
void __fastcall LockRegkeyFromUserAccess(HKEY handle, struct _TOKEN_USER *a2)
{
  HKEY v3; // r12
  int v4; // ebx
  DWORD v5; // r14d
  DWORD LengthSid; // r13d
  DWORD v7; // esi
  __int64 v8; // rdi
  struct _ACL *v9; // rax
  struct _ACL *v10; // rbx
  _WORD *v11; // rdi
  void *v12; // rcx
  int v13; // esi
  DWORD v14; // edi
  DWORD dwAclRevision; // [rsp+40h] [rbp-40h] BYREF
  PACL pAcl; // [rsp+48h] [rbp-38h] BYREF
  LPVOID pAce; // [rsp+50h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+58h] [rbp-28h] BYREF
  HKEY v19; // [rsp+60h] [rbp-20h]
  __int64 pAclInformation; // [rsp+68h] [rbp-18h] BYREF
  int v21; // [rsp+70h] [rbp-10h]

  v19 = handle;
  hMem = 0;
  pAcl = 0;
  v3 = handle;
  if ( !GetSecurityInfo(handle, SE_REGISTRY_KEY, 4u, 0, 0, &pAcl, 0, &hMem) )
  {
    if ( pAcl )
    {
      pAclInformation = 0;
      v21 = 0;
      if ( GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation) )
      {
        v4 = HIDWORD(pAclInformation);
        dwAclRevision = 0;
        v5 = 2;
        if ( GetAclInformation(pAcl, &dwAclRevision, 4u, AclRevisionInformation) )
          v5 = dwAclRevision;
        LengthSid = GetLengthSid(a2->User.Sid);
        v7 = LengthSid + 8;
        if ( LengthSid + 8 <= 0xFFFF )
        {
          v8 = v7 + v4;
          if ( (unsigned int)v8 <= 0xFFFF )
          {
            v9 = (struct _ACL *)LocalAlloc(0x40u, (unsigned int)v8 + v7);
            v10 = v9;
            if ( v9 )
            {
              InitializeAcl(v9, v8, v5);
              v11 = (_WORD *)((char *)v10 + v8);
              *(_BYTE *)v11 = 1;
              v11[1] = v7;
              *((_DWORD *)v11 + 1) = 2;
              if ( !LengthSid )
                goto LABEL_15;
              v12 = v11 + 4;
              if ( v11 != (_WORD *)-8LL )
              {
                if ( a2->User.Sid )
                {
                  memcpy_0(v12, a2->User.Sid, LengthSid);
LABEL_15:
                  if ( AddAce(v10, v5, 0xFFFFFFFF, v11, LengthSid + 8) )
                  {
                    v13 = 0;
                    v14 = 0;
                    if ( !(_DWORD)pAclInformation )
                      goto LABEL_22;
                    do
                    {
                      pAce = 0;
                      if ( GetAce(pAcl, v14, &pAce)
                        && !AddAce(v10, v5, 0xFFFFFFFF, pAce, *((unsigned __int16 *)pAce + 1)) )
                      {
                        v13 = 1;
                      }
                      ++v14;
                    }
                    while ( v14 < (unsigned int)pAclInformation );
                    v3 = v19;
                    if ( !v13 )
LABEL_22:
                      SetSecurityInfo(v3, SE_REGISTRY_KEY, 0x20000004u, 0, 0, v10, 0);
                  }
                  LocalFree(v10);
                  goto LABEL_24;
                }
                memset_0(v12, 0, LengthSid);
              }
              *_errno() = 22;
              invalid_parameter_noinfo();
            }
          }
        }
      }
    }
  }
LABEL_24:
  if ( hMem )
    LocalFree(hMem);
}

```

## disassembly

```asm
0x180082bb8  mov     [rsp-38h+arg_10], rbx
0x180082bbd  push    rbp
0x180082bbe  push    rsi
0x180082bbf  push    rdi
0x180082bc0  push    r12
0x180082bc2  push    r13
0x180082bc4  push    r14
0x180082bc6  push    r15
0x180082bc8  mov     rbp, rsp
0x180082bcb  sub     rsp, 80h
0x180082bd2  mov     rax, cs:__security_cookie
0x180082bd9  xor     rax, rsp
0x180082bdc  mov     [rbp+var_8], rax
0x180082be0  xor     r9d, r9d; ppsidOwner
0x180082be3  mov     [rbp+var_20], rcx
0x180082be7  lea     rax, [rbp+hMem]
0x180082beb  mov     [rbp+hMem], 0
0x180082bf3  mov     [rsp+80h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180082bf8  mov     r15, rdx
0x180082bfb  lea     rax, [rbp+pAcl]
0x180082bff  mov     [rsp+80h+ppSacl], 0; ppSacl
0x180082c08  lea     esi, [r9+4]
0x180082c0c  mov     [rsp+80h+ppDacl], rax; ppDacl
0x180082c11  mov     r8d, esi; SecurityInfo
0x180082c14  mov     [rbp+pAcl], 0
0x180082c1c  mov     edx, esi; ObjectType
0x180082c1e  mov     [rsp+80h+ppsidGroup], 0; ppsidGroup
0x180082c27  mov     r12, rcx
0x180082c2a  call    cs:__imp_GetSecurityInfo
0x180082c30  test    eax, eax
0x180082c32  jnz     loc_180082DDD
0x180082c38  mov     rcx, [rbp+pAcl]; pAcl
0x180082c3c  test    rcx, rcx
0x180082c3f  jz      loc_180082DDD
0x180082c45  xor     eax, eax
0x180082c47  lea     edi, [rsi-2]
0x180082c4a  mov     r9d, edi; dwAclInformationClass
0x180082c4d  mov     [rbp+pAclInformation], rax
0x180082c51  lea     r8d, [rsi+8]; nAclInformationLength
0x180082c55  mov     [rbp+var_10], eax
0x180082c58  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x180082c5c  call    cs:__imp_GetAclInformation
0x180082c62  test    eax, eax
0x180082c64  jz      loc_180082DDD
0x180082c6a  mov     rcx, [rbp+pAcl]; pAcl
0x180082c6e  lea     r9d, [rsi-3]; dwAclInformationClass
0x180082c72  mov     ebx, dword ptr [rbp+pAclInformation+4]
0x180082c75  lea     rdx, [rbp+dwAclRevision]; pAclInformation
0x180082c79  mov     r8d, esi; nAclInformationLength
0x180082c7c  mov     [rbp+dwAclRevision], 0
0x180082c83  call    cs:__imp_GetAclInformation
0x180082c89  mov     rcx, [r15]; pSid
0x180082c8c  mov     r14d, edi
0x180082c8f  test    eax, eax
0x180082c91  cmovnz  r14d, [rbp+dwAclRevision]
0x180082c96  call    cs:__imp_GetLengthSid
0x180082c9c  mov     r13d, eax
0x180082c9f  mov     eax, 0FFFFh
0x180082ca4  lea     esi, [r13+8]
0x180082ca8  cmp     esi, eax
0x180082caa  ja      loc_180082DDD
0x180082cb0  lea     edi, [rsi+rbx]
0x180082cb3  cmp     edi, eax
0x180082cb5  ja      loc_180082DDD
0x180082cbb  lea     edx, [rdi+rsi]; uBytes
0x180082cbe  mov     ecx, 40h ; '@'; uFlags
0x180082cc3  call    cs:__imp_LocalAlloc
0x180082cc9  mov     rbx, rax
0x180082ccc  test    rax, rax
0x180082ccf  jz      loc_180082DDD
0x180082cd5  mov     r8d, r14d; dwAclRevision
0x180082cd8  mov     edx, edi; nAclLength
0x180082cda  mov     rcx, rax; pAcl
0x180082cdd  call    cs:__imp_InitializeAcl
0x180082ce3  add     rdi, rbx
0x180082ce6  mov     r8d, r13d; Size
0x180082ce9  mov     byte ptr [rdi], 1
0x180082cec  mov     [rdi+2], si
0x180082cf0  mov     dword ptr [rdi+4], 2
0x180082cf7  test    r13d, r13d
0x180082cfa  jz      short loc_180082D2A
0x180082cfc  lea     rcx, [rdi+8]; void *
0x180082d00  test    rcx, rcx
0x180082d03  jz      short loc_180082D19
0x180082d05  mov     rdx, [r15]; Val
0x180082d08  test    rdx, rdx
0x180082d0b  jz      short loc_180082D14
0x180082d0d  call    memcpy_0
0x180082d12  jmp     short loc_180082D2A
0x180082d14  call    memset_0
0x180082d19  call    cs:__imp__errno
0x180082d1f  mov     dword ptr [rax], 16h
0x180082d25  call    _invalid_parameter_noinfo
0x180082d2a  or      r15d, 0FFFFFFFFh
0x180082d2e  mov     dword ptr [rsp+80h+ppsidGroup], esi; nAceListLength
0x180082d32  mov     r8d, r15d; dwStartingAceIndex
0x180082d35  mov     r9, rdi; pAceList
0x180082d38  mov     edx, r14d; dwAceRevision
0x180082d3b  mov     rcx, rbx; pAcl
0x180082d3e  call    cs:__imp_AddAce
0x180082d44  test    eax, eax
0x180082d46  jz      loc_180082DD4
0x180082d4c  xor     esi, esi
0x180082d4e  xor     edi, edi
0x180082d50  cmp     dword ptr [rbp+pAclInformation], esi
0x180082d53  jbe     short loc_180082DA7
0x180082d55  lea     r12d, [rsi+1]
0x180082d59  mov     rcx, [rbp+pAcl]; pAcl
0x180082d5d  lea     r8, [rbp+pAce]; pAce
0x180082d61  mov     edx, edi; dwAceIndex
0x180082d63  mov     [rbp+pAce], 0
0x180082d6b  call    cs:__imp_GetAce
0x180082d71  test    eax, eax
0x180082d73  jz      short loc_180082D97
0x180082d75  mov     r9, [rbp+pAce]; pAceList
0x180082d79  mov     r8d, r15d; dwStartingAceIndex
0x180082d7c  mov     edx, r14d; dwAceRevision
0x180082d7f  mov     rcx, rbx; pAcl
0x180082d82  movzx   eax, word ptr [r9+2]
0x180082d87  mov     dword ptr [rsp+80h+ppsidGroup], eax; nAceListLength
0x180082d8b  call    cs:__imp_AddAce
0x180082d91  test    eax, eax
0x180082d93  cmovz   esi, r12d
0x180082d97  add     edi, r12d
0x180082d9a  cmp     edi, dword ptr [rbp+pAclInformation]
0x180082d9d  jb      short loc_180082D59
0x180082d9f  mov     r12, [rbp+var_20]
0x180082da3  test    esi, esi
0x180082da5  jnz     short loc_180082DD4
0x180082da7  xor     r9d, r9d; psidOwner
0x180082daa  mov     [rsp+80h+ppSacl], 0; pSacl
0x180082db3  mov     [rsp+80h+ppDacl], rbx; pDacl
0x180082db8  mov     r8d, 20000004h; SecurityInfo
0x180082dbe  mov     rcx, r12; handle
0x180082dc1  mov     [rsp+80h+ppsidGroup], 0; psidGroup
0x180082dca  lea     edx, [r9+4]; ObjectType
0x180082dce  call    cs:__imp_SetSecurityInfo
0x180082dd4  mov     rcx, rbx; hMem
0x180082dd7  call    cs:__imp_LocalFree
0x180082ddd  mov     rcx, [rbp+hMem]; hMem
0x180082de1  test    rcx, rcx
0x180082de4  jz      short loc_180082DEC
0x180082de6  call    cs:__imp_LocalFree
0x180082dec  mov     rcx, [rbp+var_8]
0x180082df0  xor     rcx, rsp; StackCookie
0x180082df3  call    __security_check_cookie
0x180082df8  mov     rbx, [rsp+80h+arg_10]
0x180082e00  add     rsp, 80h
0x180082e07  pop     r15
0x180082e09  pop     r14
0x180082e0b  pop     r13
0x180082e0d  pop     r12
0x180082e0f  pop     rdi
0x180082e10  pop     rsi
0x180082e11  pop     rbp
0x180082e12  retn
```
