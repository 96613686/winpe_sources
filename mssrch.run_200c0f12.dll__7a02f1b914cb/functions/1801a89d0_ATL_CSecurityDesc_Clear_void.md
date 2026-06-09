# ATL::CSecurityDesc::Clear(void)

- ea: `0x1801a89d0`
- end: `0x1801a8ad9`
- name: `?Clear@CSecurityDesc@ATL@@MEAAXXZ`
- size: `265`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800e7c80`
- `0x1801a83d0`
- `0x1801a83ec`
- `0x1801a8760`

## callees

- `0x1801a89d0`
- `0x1801a9358`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801a8a52`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801a8a6e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801a8a94`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801a8aba`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801a8ac4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801a8a52`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801a8a6e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801a8a94`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801a8aba`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801a8ac4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1801a8aaa`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1801a8aaa`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1801a8a84`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1801a8a84`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1801a8a64`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1801a8a64`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1801a8a48`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1801a8a48`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::Clear(ATL::CSecurityDesc *this)
{
  void *v2; // rcx
  PSID pGroup; // [rsp+20h] [rbp-28h] BYREF
  PACL pDacl; // [rsp+28h] [rbp-20h] BYREF
  PACL pSacl; // [rsp+30h] [rbp-18h] BYREF
  unsigned __int16 v6; // [rsp+60h] [rbp+18h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+68h] [rbp+20h] BYREF
  WINBOOL bDaclPresent; // [rsp+70h] [rbp+28h] BYREF
  PSID pOwner; // [rsp+78h] [rbp+30h] BYREF

  if ( *((_QWORD *)this + 1) )
  {
    v6 = 0;
    if ( ATL::CSecurityDesc::GetControl(this, &v6) && (v6 & 0x8000u) == 0 )
    {
      v2 = (void *)*((_QWORD *)this + 1);
      pOwner = 0;
      pGroup = 0;
      pDacl = 0;
      pSacl = 0;
      bOwnerDefaulted = 0;
      bDaclPresent = 0;
      GetSecurityDescriptorOwner(v2, &pOwner, &bOwnerDefaulted);
      free(pOwner);
      GetSecurityDescriptorGroup(*((PSECURITY_DESCRIPTOR *)this + 1), &pGroup, &bOwnerDefaulted);
      free(pGroup);
      GetSecurityDescriptorDacl(*((PSECURITY_DESCRIPTOR *)this + 1), &bDaclPresent, &pDacl, &bOwnerDefaulted);
      if ( bDaclPresent )
        free(pDacl);
      GetSecurityDescriptorSacl(*((PSECURITY_DESCRIPTOR *)this + 1), &bDaclPresent, &pSacl, &bOwnerDefaulted);
      if ( bDaclPresent )
        free(pSacl);
    }
    free(*((void **)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x1801a89d0  push    rbp
0x1801a89d2  push    rbx
0x1801a89d3  mov     rbp, rsp
0x1801a89d6  sub     rsp, 48h
0x1801a89da  cmp     qword ptr [rcx+8], 0
0x1801a89df  mov     rbx, rcx
0x1801a89e2  jz      loc_1801A8AD2
0x1801a89e8  xor     eax, eax
0x1801a89ea  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x1801a89ee  mov     [rbp+arg_0], ax
0x1801a89f2  call    ?GetControl@CSecurityDesc@ATL@@QEBA_NPEAG@Z; ATL::CSecurityDesc::GetControl(ushort *)
0x1801a89f7  test    al, al
0x1801a89f9  jz      loc_1801A8AC0
0x1801a89ff  mov     eax, 8000h
0x1801a8a04  test    [rbp+arg_0], ax
0x1801a8a08  jnz     loc_1801A8AC0
0x1801a8a0e  mov     rcx, [rbx+8]; pSecurityDescriptor
0x1801a8a12  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x1801a8a16  lea     rdx, [rbp+pOwner]; pOwner
0x1801a8a1a  mov     [rbp+pOwner], 0
0x1801a8a22  mov     [rbp+pGroup], 0
0x1801a8a2a  mov     [rbp+pDacl], 0
0x1801a8a32  mov     [rbp+pSacl], 0
0x1801a8a3a  mov     [rbp+bOwnerDefaulted], 0
0x1801a8a41  mov     [rbp+bDaclPresent], 0
0x1801a8a48  call    cs:__imp_GetSecurityDescriptorOwner
0x1801a8a4e  mov     rcx, [rbp+pOwner]; Block
0x1801a8a52  call    cs:__imp_free
0x1801a8a58  mov     rcx, [rbx+8]; pSecurityDescriptor
0x1801a8a5c  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x1801a8a60  lea     rdx, [rbp+pGroup]; pGroup
0x1801a8a64  call    cs:__imp_GetSecurityDescriptorGroup
0x1801a8a6a  mov     rcx, [rbp+pGroup]; Block
0x1801a8a6e  call    cs:__imp_free
0x1801a8a74  mov     rcx, [rbx+8]; pSecurityDescriptor
0x1801a8a78  lea     r9, [rbp+bOwnerDefaulted]; lpbDaclDefaulted
0x1801a8a7c  lea     r8, [rbp+pDacl]; pDacl
0x1801a8a80  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x1801a8a84  call    cs:__imp_GetSecurityDescriptorDacl
0x1801a8a8a  cmp     [rbp+bDaclPresent], 0
0x1801a8a8e  jz      short loc_1801A8A9A
0x1801a8a90  mov     rcx, [rbp+pDacl]; Block
0x1801a8a94  call    cs:__imp_free
0x1801a8a9a  mov     rcx, [rbx+8]; pSecurityDescriptor
0x1801a8a9e  lea     r9, [rbp+bOwnerDefaulted]; lpbSaclDefaulted
0x1801a8aa2  lea     r8, [rbp+pSacl]; pSacl
0x1801a8aa6  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x1801a8aaa  call    cs:__imp_GetSecurityDescriptorSacl
0x1801a8ab0  cmp     [rbp+bDaclPresent], 0
0x1801a8ab4  jz      short loc_1801A8AC0
0x1801a8ab6  mov     rcx, [rbp+pSacl]; Block
0x1801a8aba  call    cs:__imp_free
0x1801a8ac0  mov     rcx, [rbx+8]; Block
0x1801a8ac4  call    cs:__imp_free
0x1801a8aca  mov     qword ptr [rbx+8], 0
0x1801a8ad2  add     rsp, 48h
0x1801a8ad6  pop     rbx
0x1801a8ad7  pop     rbp
0x1801a8ad8  retn
```
