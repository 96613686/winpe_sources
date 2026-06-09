# AdjustTokenIntegrityLevel(void *)

- ea: `0x180024290`
- end: `0x180024374`
- name: `?AdjustTokenIntegrityLevel@@YAJPEAX@Z`
- size: `228`
- prototype: `signed int __fastcall(HANDLE handle)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180024290`
- `0x18002e560`

## import_xrefs

- `ntdll!RtlAddMandatoryAce` at `0x1800242f8`
- `ntdll!RtlAddMandatoryAce` at `0x1800242f8`
- `ntdll!RtlCreateAcl` at `0x1800242cc`
- `ntdll!RtlCreateAcl` at `0x1800242cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002433e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002433e`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18002432e`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18002432e`

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
0x180024290  push    rbx
0x180024292  sub     rsp, 0B0h
0x180024299  mov     rax, cs:__security_cookie
0x1800242a0  xor     rax, rsp
0x1800242a3  mov     [rsp+0B8h+var_18], rax
0x1800242ab  cmp     cs:?g_dwProcessIntegrityRid@@3KA, 4000h; ulong g_dwProcessIntegrityRid
0x1800242b5  mov     rbx, rcx
0x1800242b8  jnb     loc_180024358
0x1800242be  mov     edx, 58h ; 'X'; AclSize
0x1800242c3  lea     rcx, [rsp+0B8h+Acl]; Acl
0x1800242c8  lea     r8d, [rdx-56h]; AclRevision
0x1800242cc  call    cs:__imp_RtlCreateAcl
0x1800242d3  nop     dword ptr [rax+rax+00h]
0x1800242d8  mov     r9, cs:?g_pTokenIntegritySid@@3PEAXEA; MandatoryFlags
0x1800242df  lea     rcx, [rsp+0B8h+Acl]; Acl
0x1800242e4  xor     r8d, r8d; Flags
0x1800242e7  mov     dword ptr [rsp+0B8h+LabelSid], 1; LabelSid
0x1800242ef  mov     [rsp+0B8h+AceType], 11h; AceType
0x1800242f4  lea     edx, [r8+2]; Revision
0x1800242f8  call    cs:__imp_RtlAddMandatoryAce
0x1800242ff  nop     dword ptr [rax+rax+00h]
0x180024304  xor     r9d, r9d; psidOwner
0x180024307  lea     rax, [rsp+0B8h+Acl]
0x18002430c  mov     [rsp+0B8h+pSacl], rax; pSacl
0x180024311  mov     rcx, rbx; handle
0x180024314  mov     [rsp+0B8h+LabelSid], 0; pDacl
0x18002431d  mov     qword ptr [rsp+0B8h+AceType], 0; psidGroup
0x180024326  lea     edx, [r9+6]; ObjectType
0x18002432a  lea     r8d, [r9+10h]; SecurityInfo
0x18002432e  call    cs:__imp_SetSecurityInfo
0x180024335  nop     dword ptr [rax+rax+00h]
0x18002433a  test    eax, eax
0x18002433c  jz      short loc_180024358
0x18002433e  call    cs:__imp_GetLastError
0x180024345  nop     dword ptr [rax+rax+00h]
0x18002434a  test    eax, eax
0x18002434c  jle     short loc_18002435A
0x18002434e  movzx   eax, ax
0x180024351  or      eax, 80070000h
0x180024356  jmp     short loc_18002435A
0x180024358  xor     eax, eax
0x18002435a  mov     rcx, [rsp+0B8h+var_18]
0x180024362  xor     rcx, rsp; StackCookie
0x180024365  call    __security_check_cookie
0x18002436a  add     rsp, 0B0h
0x180024371  pop     rbx
0x180024372  retn
```
