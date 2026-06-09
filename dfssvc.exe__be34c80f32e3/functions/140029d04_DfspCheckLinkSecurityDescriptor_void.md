# DfspCheckLinkSecurityDescriptor(void *)

- ea: `0x140029d04`
- end: `0x140029dee`
- name: `?DfspCheckLinkSecurityDescriptor@@YAKPEAX@Z`
- size: `234`
- prototype: `unsigned int __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002f5b4`

## callees

- `0x140005a94`
- `0x140029d04`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x140029d41`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x140029d41`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x140029d69`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x140029d69`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x140029d8b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x140029d8b`

## pseudocode

```c
__int64 __fastcall DfspCheckLinkSecurityDescriptor(PSECURITY_DESCRIPTOR pSecurityDescriptor)
{
  unsigned int v2; // ebx
  PSID pOwner; // [rsp+20h] [rbp-28h] BYREF
  PSID pGroup; // [rsp+28h] [rbp-20h] BYREF
  PACL pSacl; // [rsp+30h] [rbp-18h] BYREF
  WINBOOL bSaclPresent; // [rsp+60h] [rbp+18h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+68h] [rbp+20h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+70h] [rbp+28h] BYREF
  WINBOOL bGroupDefaulted; // [rsp+78h] [rbp+30h] BYREF

  pSacl = 0;
  pOwner = 0;
  pGroup = 0;
  bSaclDefaulted = 0;
  bSaclPresent = 0;
  bOwnerDefaulted = 0;
  bGroupDefaulted = 0;
  if ( pSecurityDescriptor
    && (GetSecurityDescriptorSacl(pSecurityDescriptor, &bSaclPresent, &pSacl, &bSaclDefaulted) && bSaclPresent
     || GetSecurityDescriptorOwner(pSecurityDescriptor, &pOwner, &bOwnerDefaulted) && pOwner
     || GetSecurityDescriptorGroup(pSecurityDescriptor, &pGroup, &bGroupDefaulted) && pGroup) )
  {
    v2 = 50;
  }
  else
  {
    v2 = 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)pWppControl + 2), 93, WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x140029d04  push    rbp
0x140029d06  push    rbx
0x140029d07  mov     rbp, rsp
0x140029d0a  sub     rsp, 48h
0x140029d0e  and     [rbp+pSacl], 0
0x140029d13  mov     rbx, rcx
0x140029d16  and     [rbp+pOwner], 0
0x140029d1b  and     [rbp+pGroup], 0
0x140029d20  and     [rbp+bSaclDefaulted], 0
0x140029d24  and     [rbp+bSaclPresent], 0
0x140029d28  and     [rbp+bOwnerDefaulted], 0
0x140029d2c  and     [rbp+bGroupDefaulted], 0
0x140029d30  test    rcx, rcx
0x140029d33  jz      short loc_140029DA2
0x140029d35  lea     r9, [rbp+bSaclDefaulted]; lpbSaclDefaulted
0x140029d39  lea     r8, [rbp+pSacl]; pSacl
0x140029d3d  lea     rdx, [rbp+bSaclPresent]; lpbSaclPresent
0x140029d41  call    cs:__imp_GetSecurityDescriptorSacl
0x140029d48  nop     dword ptr [rax+rax+00h]
0x140029d4d  test    eax, eax
0x140029d4f  jz      short loc_140029D5E
0x140029d51  cmp     [rbp+bSaclPresent], 0
0x140029d55  jz      short loc_140029D5E
0x140029d57  mov     ebx, 32h ; '2'
0x140029d5c  jmp     short loc_140029DA4
0x140029d5e  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x140029d62  mov     rcx, rbx; pSecurityDescriptor
0x140029d65  lea     rdx, [rbp+pOwner]; pOwner
0x140029d69  call    cs:__imp_GetSecurityDescriptorOwner
0x140029d70  nop     dword ptr [rax+rax+00h]
0x140029d75  test    eax, eax
0x140029d77  jz      short loc_140029D80
0x140029d79  cmp     [rbp+pOwner], 0
0x140029d7e  jnz     short loc_140029D57
0x140029d80  lea     r8, [rbp+bGroupDefaulted]; lpbGroupDefaulted
0x140029d84  mov     rcx, rbx; pSecurityDescriptor
0x140029d87  lea     rdx, [rbp+pGroup]; pGroup
0x140029d8b  call    cs:__imp_GetSecurityDescriptorGroup
0x140029d92  nop     dword ptr [rax+rax+00h]
0x140029d97  test    eax, eax
0x140029d99  jz      short loc_140029DA2
0x140029d9b  cmp     [rbp+pGroup], 0
0x140029da0  jnz     short loc_140029D57
0x140029da2  xor     ebx, ebx
0x140029da4  lea     rax, WPP_GLOBAL_Control
0x140029dab  cmp     cs:WPP_GLOBAL_Control, rax
0x140029db2  jz      short loc_140029DE4
0x140029db4  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140029dbb  test    rcx, rcx
0x140029dbe  jz      short loc_140029DE4
0x140029dc0  test    byte ptr [rcx+1Ch], 20h
0x140029dc4  jz      short loc_140029DE4
0x140029dc6  cmp     byte ptr [rcx+19h], 2
0x140029dca  jb      short loc_140029DE4
0x140029dcc  mov     rcx, [rcx+10h]
0x140029dd0  lea     r8, WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids
0x140029dd7  mov     edx, 5Dh ; ']'
0x140029ddc  mov     r9d, ebx
0x140029ddf  call    WPP_SF_D
0x140029de4  mov     eax, ebx
0x140029de6  add     rsp, 48h
0x140029dea  pop     rbx
0x140029deb  pop     rbp
0x140029dec  retn
```
