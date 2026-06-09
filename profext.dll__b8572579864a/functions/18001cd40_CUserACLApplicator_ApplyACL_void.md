# CUserACLApplicator::ApplyACL(void *)

- ea: `0x18001cd40`
- end: `0x18001cda5`
- name: `?ApplyACL@CUserACLApplicator@@UEBAJPEAX@Z`
- size: `101`
- prototype: `int(CUserACLApplicator *__hidden this, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x18001cd40`
- `0x18001d388`

## import_xrefs

- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18001cd70`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18001cd70`

## string_xrefs

- `0x18001cd85`: `onecore\ds\security\gina\profile\profext\DirJuncHelper.h`

## pseudocode

```c
int __fastcall CUserACLApplicator::ApplyACL(PACL *this, void *a2, __int64 a3, __int64 a4, unsigned int a5)
{
  DWORD v5; // eax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v5 = SetSecurityInfo(a2, SE_FILE_OBJECT, 4u, 0, 0, this[1], 0);
  if ( v5 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x9D,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\DirJuncHelper.h",
             (const char *)v5,
             a5);
  else
    return 0;
}

```

## disassembly

```asm
0x18001cd40  sub     rsp, 48h
0x18001cd44  mov     rax, [rcx+8]
0x18001cd48  xor     r9d, r9d; psidOwner
0x18001cd4b  mov     r10, rdx
0x18001cd4e  mov     [rsp+48h+pSacl], 0; pSacl
0x18001cd57  mov     [rsp+48h+pDacl], rax; pDacl
0x18001cd5c  mov     rcx, r10; handle
0x18001cd5f  mov     [rsp+48h+psidGroup], 0; psidGroup
0x18001cd68  lea     edx, [r9+1]; ObjectType
0x18001cd6c  lea     r8d, [r9+4]; SecurityInfo
0x18001cd70  call    cs:__imp_SetSecurityInfo
0x18001cd77  nop     dword ptr [rax+rax+00h]
0x18001cd7c  test    eax, eax
0x18001cd7e  jz      short loc_18001CD9D
0x18001cd80  mov     rcx, [rsp+48h]; this
0x18001cd85  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001cd8c  mov     r9d, eax; char *
0x18001cd8f  mov     edx, 9Dh; void *
0x18001cd94  add     rsp, 48h
0x18001cd98  jmp     ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001cd9d  xor     eax, eax
0x18001cd9f  add     rsp, 48h
0x18001cda3  retn
```
