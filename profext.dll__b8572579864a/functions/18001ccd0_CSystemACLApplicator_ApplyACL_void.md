# CSystemACLApplicator::ApplyACL(void *)

- ea: `0x18001ccd0`
- end: `0x18001cd37`
- name: `?ApplyACL@CSystemACLApplicator@@UEBAJPEAX@Z`
- size: `103`
- prototype: `int(CSystemACLApplicator *__hidden this, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x18001ccd0`
- `0x18001d388`

## import_xrefs

- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18001cd02`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18001cd02`

## string_xrefs

- `0x18001cd17`: `onecore\ds\security\gina\profile\profext\dirjunc.cpp`

## pseudocode

```c
int __fastcall CSystemACLApplicator::ApplyACL(PACL *this, void *a2, __int64 a3, __int64 a4, unsigned int a5)
{
  DWORD v5; // eax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v5 = SetSecurityInfo(a2, SE_FILE_OBJECT, 0x80000004, 0, 0, this[1], 0);
  if ( v5 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x9B,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\dirjunc.cpp",
             (const char *)v5,
             a5);
  else
    return 0;
}

```

## disassembly

```asm
0x18001ccd0  sub     rsp, 48h
0x18001ccd4  mov     rax, [rcx+8]
0x18001ccd8  mov     r10, rdx
0x18001ccdb  xor     r9d, r9d; psidOwner
0x18001ccde  mov     [rsp+48h+pSacl], 0; pSacl
0x18001cce7  mov     [rsp+48h+pDacl], rax; pDacl
0x18001ccec  mov     r8d, 80000004h; SecurityInfo
0x18001ccf2  mov     rcx, r10; handle
0x18001ccf5  mov     [rsp+48h+psidGroup], 0; psidGroup
0x18001ccfe  lea     edx, [r9+1]; ObjectType
0x18001cd02  call    cs:__imp_SetSecurityInfo
0x18001cd09  nop     dword ptr [rax+rax+00h]
0x18001cd0e  test    eax, eax
0x18001cd10  jz      short loc_18001CD2F
0x18001cd12  mov     rcx, [rsp+48h]; this
0x18001cd17  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001cd1e  mov     r9d, eax; char *
0x18001cd21  mov     edx, 9Bh; void *
0x18001cd26  add     rsp, 48h
0x18001cd2a  jmp     ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001cd2f  xor     eax, eax
0x18001cd31  add     rsp, 48h
0x18001cd35  retn
```
