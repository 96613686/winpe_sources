# AdjustTokenIntegrityLevel(void *)

- ea: `0x180022a60`
- end: `0x180022b2b`
- name: `?AdjustTokenIntegrityLevel@@YAJPEAX@Z`
- size: `203`
- prototype: `__int64 __fastcall(HANDLE handle)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180022a60`
- `0x18002c4c0`

## import_xrefs

- `ntdll!RtlAddMandatoryAce` at `0x180022ac2`
- `ntdll!RtlAddMandatoryAce` at `0x180022ac2`
- `ntdll!RtlCreateAcl` at `0x180022a9c`
- `ntdll!RtlCreateAcl` at `0x180022a9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022afc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022afc`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180022af2`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180022af2`

## pseudocode

```c
signed int __fastcall AdjustTokenIntegrityLevel(HANDLE handle)
{
  signed int result; // eax
  PSID LabelSid; // [rsp+28h] [rbp-90h]
  struct _ACL Acl; // [rsp+40h] [rbp-78h] BYREF

  if ( g_dwProcessIntegrityRid >= 0x4000 )
    return 0;
  RtlCreateAcl(&Acl, 0x58u, 2u);
  LODWORD(LabelSid) = 1;
  RtlAddMandatoryAce(&Acl, 2u, 0, (ULONG)g_pTokenIntegritySid, 0x11u, LabelSid);
  if ( !SetSecurityInfo(handle, SE_KERNEL_OBJECT, 0x10u, 0, 0, 0, &Acl) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180022a60  push    rbx
0x180022a62  sub     rsp, 0B0h
0x180022a69  mov     rax, cs:__security_cookie
0x180022a70  xor     rax, rsp
0x180022a73  mov     [rsp+0B8h+var_18], rax
0x180022a7b  cmp     cs:?g_dwProcessIntegrityRid@@3KA, 4000h; ulong g_dwProcessIntegrityRid
0x180022a85  mov     rbx, rcx
0x180022a88  jnb     loc_180022B10
0x180022a8e  mov     edx, 58h ; 'X'; AclSize
0x180022a93  lea     rcx, [rsp+0B8h+Acl]; Acl
0x180022a98  lea     r8d, [rdx-56h]; AclRevision
0x180022a9c  call    cs:__imp_RtlCreateAcl
0x180022aa2  mov     r9, cs:?g_pTokenIntegritySid@@3PEAXEA; MandatoryFlags
0x180022aa9  lea     rcx, [rsp+0B8h+Acl]; Acl
0x180022aae  xor     r8d, r8d; Flags
0x180022ab1  mov     dword ptr [rsp+0B8h+LabelSid], 1; LabelSid
0x180022ab9  mov     [rsp+0B8h+AceType], 11h; AceType
0x180022abe  lea     edx, [r8+2]; Revision
0x180022ac2  call    cs:__imp_RtlAddMandatoryAce
0x180022ac8  xor     r9d, r9d; psidOwner
0x180022acb  lea     rax, [rsp+0B8h+Acl]
0x180022ad0  mov     [rsp+0B8h+pSacl], rax; pSacl
0x180022ad5  mov     rcx, rbx; handle
0x180022ad8  mov     [rsp+0B8h+LabelSid], 0; pDacl
0x180022ae1  mov     qword ptr [rsp+0B8h+AceType], 0; psidGroup
0x180022aea  lea     edx, [r9+6]; ObjectType
0x180022aee  lea     r8d, [r9+10h]; SecurityInfo
0x180022af2  call    cs:__imp_SetSecurityInfo
0x180022af8  test    eax, eax
0x180022afa  jz      short loc_180022B10
0x180022afc  call    cs:__imp_GetLastError
0x180022b02  test    eax, eax
0x180022b04  jle     short loc_180022B12
0x180022b06  movzx   eax, ax
0x180022b09  or      eax, 80070000h
0x180022b0e  jmp     short loc_180022B12
0x180022b10  xor     eax, eax
0x180022b12  mov     rcx, [rsp+0B8h+var_18]
0x180022b1a  xor     rcx, rsp; StackCookie
0x180022b1d  call    __security_check_cookie
0x180022b22  add     rsp, 0B0h
0x180022b29  pop     rbx
0x180022b2a  retn
```
