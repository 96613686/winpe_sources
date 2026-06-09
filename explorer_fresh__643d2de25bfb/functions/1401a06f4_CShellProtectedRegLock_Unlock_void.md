# CShellProtectedRegLock::Unlock(void)

- ea: `0x1401a06f4`
- end: `0x1401a0842`
- name: `?Unlock@CShellProtectedRegLock@@QEAAXXZ`
- size: `334`
- prototype: `void __fastcall(CShellProtectedRegLock *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14019b85c`

## callees

- `0x14010e160`
- `0x1401a06f4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x1401a07d5`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x1401a07d5`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1401a077c`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1401a077c`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1401a07b0`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1401a07b0`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1401a0744`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1401a0744`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1401a080d`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1401a080d`

## pseudocode

```c
void __fastcall CShellProtectedRegLock::Unlock(HANDLE *this)
{
  PACL *v1; // rdi
  struct _ACL *v3; // rcx
  signed int i; // ebx
  struct _ACL *v5; // rcx
  LPVOID pAce; // [rsp+40h] [rbp-28h] BYREF
  __int64 pAclInformation; // [rsp+48h] [rbp-20h] BYREF
  int v8; // [rsp+50h] [rbp-18h]

  v1 = (PACL *)(this + 2);
  if ( !GetSecurityInfo(this[1], SE_REGISTRY_KEY, 4u, 0, 0, (PACL *)this + 2, 0, this + 3) )
  {
    v3 = *v1;
    pAclInformation = 0;
    v8 = 0;
    if ( v3 )
    {
      if ( GetAclInformation(v3, &pAclInformation, 0xCu, AclSizeInformation) )
      {
        for ( i = pAclInformation - 1; i >= 0; --i )
        {
          v5 = *v1;
          pAce = 0;
          if ( GetAce(v5, i, &pAce) && *(_BYTE *)pAce == 1 && *((_DWORD *)pAce + 1) == 2 )
          {
            if ( DeleteAce(*v1, i) )
              SetSecurityInfo(this[1], SE_REGISTRY_KEY, 4u, 0, 0, *v1, 0);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1401a06f4  mov     r11, rsp
0x1401a06f7  mov     [r11+10h], rbx
0x1401a06fb  mov     [r11+18h], rsi
0x1401a06ff  push    rdi
0x1401a0700  sub     rsp, 60h
0x1401a0704  mov     rax, cs:__security_cookie
0x1401a070b  xor     rax, rsp
0x1401a070e  mov     [rsp+68h+var_10], rax
0x1401a0713  lea     rax, [rcx+18h]
0x1401a0717  xor     r9d, r9d; ppsidOwner
0x1401a071a  mov     [r11-30h], rax
0x1401a071e  lea     rdi, [rcx+10h]
0x1401a0722  mov     qword ptr [r11-38h], 0
0x1401a072a  mov     rsi, rcx
0x1401a072d  mov     rcx, [rcx+8]; handle
0x1401a0731  lea     edx, [r9+4]; ObjectType
0x1401a0735  mov     [r11-40h], rdi
0x1401a0739  mov     r8d, edx; SecurityInfo
0x1401a073c  mov     qword ptr [r11-48h], 0
0x1401a0744  call    cs:__imp_GetSecurityInfo
0x1401a074b  nop     dword ptr [rax+rax+00h]
0x1401a0750  test    eax, eax
0x1401a0752  jnz     loc_1401A0822
0x1401a0758  mov     rcx, [rdi]; pAcl
0x1401a075b  xor     eax, eax
0x1401a075d  mov     [rsp+68h+pAclInformation], rax
0x1401a0762  mov     [rsp+68h+var_18], eax
0x1401a0766  test    rcx, rcx
0x1401a0769  jz      loc_1401A0822
0x1401a076f  lea     r9d, [rax+2]; dwAclInformationClass
0x1401a0773  lea     r8d, [rax+0Ch]; nAclInformationLength
0x1401a0777  lea     rdx, [rsp+68h+pAclInformation]; pAclInformation
0x1401a077c  call    cs:__imp_GetAclInformation
0x1401a0783  nop     dword ptr [rax+rax+00h]
0x1401a0788  test    eax, eax
0x1401a078a  jz      loc_1401A0822
0x1401a0790  mov     ebx, dword ptr [rsp+68h+pAclInformation]
0x1401a0794  sub     ebx, 1
0x1401a0797  js      loc_1401A0822
0x1401a079d  mov     rcx, [rdi]; pAcl
0x1401a07a0  lea     r8, [rsp+68h+pAce]; pAce
0x1401a07a5  mov     edx, ebx; dwAceIndex
0x1401a07a7  mov     [rsp+68h+pAce], 0
0x1401a07b0  call    cs:__imp_GetAce
0x1401a07b7  nop     dword ptr [rax+rax+00h]
0x1401a07bc  test    eax, eax
0x1401a07be  jz      short loc_1401A0819
0x1401a07c0  mov     rax, [rsp+68h+pAce]
0x1401a07c5  cmp     byte ptr [rax], 1
0x1401a07c8  jnz     short loc_1401A0819
0x1401a07ca  cmp     dword ptr [rax+4], 2
0x1401a07ce  jnz     short loc_1401A0819
0x1401a07d0  mov     rcx, [rdi]; pAcl
0x1401a07d3  mov     edx, ebx; dwAceIndex
0x1401a07d5  call    cs:__imp_DeleteAce
0x1401a07dc  nop     dword ptr [rax+rax+00h]
0x1401a07e1  test    eax, eax
0x1401a07e3  jz      short loc_1401A0819
0x1401a07e5  mov     rax, [rdi]
0x1401a07e8  xor     r9d, r9d; psidOwner
0x1401a07eb  mov     rcx, [rsi+8]; handle
0x1401a07ef  mov     [rsp+68h+pSacl], 0; pSacl
0x1401a07f8  mov     [rsp+68h+pDacl], rax; pDacl
0x1401a07fd  lea     edx, [r9+4]; ObjectType
0x1401a0801  mov     [rsp+68h+psidGroup], 0; psidGroup
0x1401a080a  mov     r8d, edx; SecurityInfo
0x1401a080d  call    cs:__imp_SetSecurityInfo
0x1401a0814  nop     dword ptr [rax+rax+00h]
0x1401a0819  add     ebx, 0FFFFFFFFh
0x1401a081c  jns     loc_1401A079D
0x1401a0822  mov     rcx, [rsp+68h+var_10]
0x1401a0827  xor     rcx, rsp; StackCookie
0x1401a082a  call    __security_check_cookie
0x1401a082f  lea     r11, [rsp+68h+var_8]
0x1401a0834  mov     rbx, [r11+18h]
0x1401a0838  mov     rsi, [r11+20h]
0x1401a083c  mov     rsp, r11
0x1401a083f  pop     rdi
0x1401a0840  retn
```
