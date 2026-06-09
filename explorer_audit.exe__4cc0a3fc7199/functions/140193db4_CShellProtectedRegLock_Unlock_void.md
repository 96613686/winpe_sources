# CShellProtectedRegLock::Unlock(void)

- ea: `0x140193db4`
- end: `0x140193ed7`
- name: `?Unlock@CShellProtectedRegLock@@QEAAXXZ`
- size: `291`
- prototype: `void __fastcall(CShellProtectedRegLock *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14018f028`

## callees

- `0x1401040e0`
- `0x140193db4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140193e36`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140193e36`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140193e5c`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140193e5c`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x140193e7b`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x140193e7b`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x140193e04`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x140193e04`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x140193ead`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x140193ead`

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
0x140193db4  mov     r11, rsp
0x140193db7  mov     [r11+10h], rbx
0x140193dbb  mov     [r11+18h], rsi
0x140193dbf  push    rdi
0x140193dc0  sub     rsp, 60h
0x140193dc4  mov     rax, cs:__security_cookie
0x140193dcb  xor     rax, rsp
0x140193dce  mov     [rsp+68h+var_10], rax
0x140193dd3  lea     rax, [rcx+18h]
0x140193dd7  xor     r9d, r9d; ppsidOwner
0x140193dda  mov     [r11-30h], rax
0x140193dde  lea     rdi, [rcx+10h]
0x140193de2  mov     qword ptr [r11-38h], 0
0x140193dea  mov     rsi, rcx
0x140193ded  mov     rcx, [rcx+8]; handle
0x140193df1  lea     edx, [r9+4]; ObjectType
0x140193df5  mov     [r11-40h], rdi
0x140193df9  mov     r8d, edx; SecurityInfo
0x140193dfc  mov     qword ptr [r11-48h], 0
0x140193e04  call    cs:__imp_GetSecurityInfo
0x140193e0a  test    eax, eax
0x140193e0c  jnz     loc_140193EB8
0x140193e12  mov     rcx, [rdi]; pAcl
0x140193e15  xor     eax, eax
0x140193e17  mov     [rsp+68h+pAclInformation], rax
0x140193e1c  mov     [rsp+68h+var_18], eax
0x140193e20  test    rcx, rcx
0x140193e23  jz      loc_140193EB8
0x140193e29  lea     r9d, [rax+2]; dwAclInformationClass
0x140193e2d  lea     r8d, [rax+0Ch]; nAclInformationLength
0x140193e31  lea     rdx, [rsp+68h+pAclInformation]; pAclInformation
0x140193e36  call    cs:__imp_GetAclInformation
0x140193e3c  test    eax, eax
0x140193e3e  jz      short loc_140193EB8
0x140193e40  mov     ebx, dword ptr [rsp+68h+pAclInformation]
0x140193e44  sub     ebx, 1
0x140193e47  js      short loc_140193EB8
0x140193e49  mov     rcx, [rdi]; pAcl
0x140193e4c  lea     r8, [rsp+68h+pAce]; pAce
0x140193e51  mov     edx, ebx; dwAceIndex
0x140193e53  mov     [rsp+68h+pAce], 0
0x140193e5c  call    cs:__imp_GetAce
0x140193e62  test    eax, eax
0x140193e64  jz      short loc_140193EB3
0x140193e66  mov     rax, [rsp+68h+pAce]
0x140193e6b  cmp     byte ptr [rax], 1
0x140193e6e  jnz     short loc_140193EB3
0x140193e70  cmp     dword ptr [rax+4], 2
0x140193e74  jnz     short loc_140193EB3
0x140193e76  mov     rcx, [rdi]; pAcl
0x140193e79  mov     edx, ebx; dwAceIndex
0x140193e7b  call    cs:__imp_DeleteAce
0x140193e81  test    eax, eax
0x140193e83  jz      short loc_140193EB3
0x140193e85  mov     rax, [rdi]
0x140193e88  xor     r9d, r9d; psidOwner
0x140193e8b  mov     rcx, [rsi+8]; handle
0x140193e8f  mov     [rsp+68h+pSacl], 0; pSacl
0x140193e98  mov     [rsp+68h+pDacl], rax; pDacl
0x140193e9d  lea     edx, [r9+4]; ObjectType
0x140193ea1  mov     [rsp+68h+psidGroup], 0; psidGroup
0x140193eaa  mov     r8d, edx; SecurityInfo
0x140193ead  call    cs:__imp_SetSecurityInfo
0x140193eb3  add     ebx, 0FFFFFFFFh
0x140193eb6  jns     short loc_140193E49
0x140193eb8  mov     rcx, [rsp+68h+var_10]
0x140193ebd  xor     rcx, rsp; StackCookie
0x140193ec0  call    __security_check_cookie
0x140193ec5  lea     r11, [rsp+68h+var_8]
0x140193eca  mov     rbx, [r11+18h]
0x140193ece  mov     rsi, [r11+20h]
0x140193ed2  mov     rsp, r11
0x140193ed5  pop     rdi
0x140193ed6  retn
```
