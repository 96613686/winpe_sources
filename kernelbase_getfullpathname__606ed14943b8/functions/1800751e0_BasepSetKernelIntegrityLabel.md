# BasepSetKernelIntegrityLabel

- ea: `0x1800751e0`
- end: `0x180075398`
- name: `BasepSetKernelIntegrityLabel`
- size: `440`
- prototype: `__int64 __fastcall(HANDLE SourceHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180073a2c`

## callees

- `0x1800751e0`
- `0x180194f10`

## import_xrefs

- `ntdll!NtClose` at `0x180075352`
- `ntdll!NtClose` at `0x180075352`
- `ntdll!NtDuplicateObject` at `0x18007524e`
- `ntdll!NtDuplicateObject` at `0x18007524e`
- `ntdll!RtlFreeSid` at `0x180075368`
- `ntdll!RtlFreeSid` at `0x180075368`
- `ntdll!RtlCreateAcl` at `0x1800752d2`
- `ntdll!RtlCreateAcl` at `0x1800752d2`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800752b1`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800752b1`
- `ntdll!NtSetSecurityObject` at `0x18007533f`
- `ntdll!NtSetSecurityObject` at `0x18007533f`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180075293`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180075293`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x180075320`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x180075320`
- `ntdll!RtlAddMandatoryAce` at `0x180075300`
- `ntdll!RtlAddMandatoryAce` at `0x180075300`

## pseudocode

```c
NTSTATUS __fastcall BasepSetKernelIntegrityLabel(HANDLE SourceHandle)
{
  NTSTATUS result; // eax
  NTSTATUS v2; // ebx
  void *HandleAttributes; // [rsp+28h] [rbp-D8h]
  HANDLE TargetHandle; // [rsp+60h] [rbp-A0h] BYREF
  PSID Sid; // [rsp+68h] [rbp-98h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v7; // [rsp+90h] [rbp-70h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+98h] [rbp-68h] BYREF
  ACL Acl; // [rsp+A0h] [rbp-60h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 4096;
  v7 = 0;
  Sid = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  TargetHandle = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  result = NtDuplicateObject(
             (HANDLE)0xFFFFFFFFFFFFFFFFLL,
             SourceHandle,
             (HANDLE)0xFFFFFFFFFFFFFFFFLL,
             &TargetHandle,
             0xF000Fu,
             0,
             0);
  if ( result >= 0 )
  {
    v2 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x1000u, 0, 0, 0, 0, 0, 0, 0, &Sid);
    if ( v2 >= 0 )
    {
      v2 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
      if ( v2 >= 0 )
      {
        v2 = RtlCreateAcl(&Acl, 0x58u, 2u);
        if ( v2 >= 0 )
        {
          LODWORD(HandleAttributes) = 1;
          v2 = RtlAddMandatoryAce(&Acl, 2u, 0, (ULONG)Sid, 0x11u, HandleAttributes);
          if ( v2 >= 0 )
          {
            v2 = RtlSetSaclSecurityDescriptor(SecurityDescriptor, 1u, &Acl, 0);
            if ( v2 >= 0 )
              v2 = NtSetSecurityObject(TargetHandle, 0x10u, SecurityDescriptor);
          }
        }
      }
    }
    NtClose(TargetHandle);
    if ( Sid )
      RtlFreeSid(Sid);
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x1800751e0  mov     [rsp-8+arg_8], rbx
0x1800751e5  mov     [rsp-8+arg_10], rdi
0x1800751ea  push    rbp
0x1800751eb  lea     rbp, [rsp-10h]
0x1800751f0  sub     rsp, 110h
0x1800751f7  mov     rax, cs:__security_cookie
0x1800751fe  xor     rax, rsp
0x180075201  mov     [rbp+10h+var_10], rax
0x180075205  xor     edi, edi
0x180075207  mov     word ptr [rbp+10h+IdentifierAuthority.Value+4], 1000h
0x18007520d  xor     eax, eax
0x18007520f  mov     [rsp+110h+Options], edi; Options
0x180075213  xorps   xmm0, xmm0
0x180075216  mov     [rbp+10h+var_80], rax
0x18007521a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007521e  mov     dword ptr [rsp+110h+HandleAttributes], edi; HandleAttributes
0x180075222  mov     rdx, rcx; SourceHandle
0x180075225  mov     [rsp+110h+var_A8], rdi
0x18007522a  mov     r8, rax; TargetProcessHandle
0x18007522d  mov     dword ptr [rbp+10h+IdentifierAuthority.Value], edi
0x180075230  mov     rcx, rax; SourceProcessHandle
0x180075233  mov     [rsp+110h+TargetHandle], rdi
0x180075238  lea     r9, [rsp+110h+TargetHandle]; TargetHandle
0x18007523d  mov     [rsp+110h+DesiredAccess], 0F000Fh; DesiredAccess
0x180075245  movups  [rsp+110h+SecurityDescriptor], xmm0
0x18007524a  movups  [rbp+10h+var_90], xmm0
0x18007524e  call    cs:__imp_NtDuplicateObject
0x180075255  nop     dword ptr [rax+rax+00h]
0x18007525a  test    eax, eax
0x18007525c  js      loc_180075376
0x180075262  lea     rax, [rsp+110h+var_A8]
0x180075267  xor     r9d, r9d; SubAuthority1
0x18007526a  mov     [rsp+110h+Sid], rax; Sid
0x18007526f  lea     rcx, [rbp+10h+IdentifierAuthority]; IdentifierAuthority
0x180075273  mov     [rsp+110h+SubAuthority7], edi; SubAuthority7
0x180075277  mov     r8d, 1000h; SubAuthority0
0x18007527d  mov     [rsp+110h+SubAuthority6], edi; SubAuthority6
0x180075281  mov     dl, 1; SubAuthorityCount
0x180075283  mov     [rsp+110h+SubAuthority5], edi; SubAuthority5
0x180075287  mov     [rsp+110h+Options], edi; SubAuthority4
0x18007528b  mov     dword ptr [rsp+110h+HandleAttributes], edi; SubAuthority3
0x18007528f  mov     [rsp+110h+DesiredAccess], edi; SubAuthority2
0x180075293  call    cs:__imp_RtlAllocateAndInitializeSid
0x18007529a  nop     dword ptr [rax+rax+00h]
0x18007529f  mov     ebx, eax
0x1800752a1  test    eax, eax
0x1800752a3  js      loc_18007534D
0x1800752a9  lea     edx, [rdi+1]; Revision
0x1800752ac  lea     rcx, [rsp+110h+SecurityDescriptor]; SecurityDescriptor
0x1800752b1  call    cs:__imp_RtlCreateSecurityDescriptor
0x1800752b8  nop     dword ptr [rax+rax+00h]
0x1800752bd  mov     ebx, eax
0x1800752bf  test    eax, eax
0x1800752c1  js      loc_18007534D
0x1800752c7  lea     edx, [rdi+58h]; AclSize
0x1800752ca  lea     r8d, [rdi+2]; AclRevision
0x1800752ce  lea     rcx, [rbp+10h+Acl]; Acl
0x1800752d2  call    cs:__imp_RtlCreateAcl
0x1800752d9  nop     dword ptr [rax+rax+00h]
0x1800752de  mov     ebx, eax
0x1800752e0  test    eax, eax
0x1800752e2  js      short loc_18007534D
0x1800752e4  mov     r9, [rsp+110h+var_A8]; MandatoryFlags
0x1800752e9  lea     edx, [rdi+2]; Revision
0x1800752ec  mov     dword ptr [rsp+110h+HandleAttributes], 1; LabelSid
0x1800752f4  lea     rcx, [rbp+10h+Acl]; Acl
0x1800752f8  xor     r8d, r8d; Flags
0x1800752fb  mov     byte ptr [rsp+110h+DesiredAccess], 11h; AceType
0x180075300  call    cs:__imp_RtlAddMandatoryAce
0x180075307  nop     dword ptr [rax+rax+00h]
0x18007530c  mov     ebx, eax
0x18007530e  test    eax, eax
0x180075310  js      short loc_18007534D
0x180075312  xor     r9d, r9d; SaclDefaulted
0x180075315  lea     r8, [rbp+10h+Acl]; Sacl
0x180075319  mov     dl, 1; SaclPresent
0x18007531b  lea     rcx, [rsp+110h+SecurityDescriptor]; SecurityDescriptor
0x180075320  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x180075327  nop     dword ptr [rax+rax+00h]
0x18007532c  mov     ebx, eax
0x18007532e  test    eax, eax
0x180075330  js      short loc_18007534D
0x180075332  mov     rcx, [rsp+110h+TargetHandle]; Handle
0x180075337  lea     r8, [rsp+110h+SecurityDescriptor]; SecurityDescriptor
0x18007533c  lea     edx, [rdi+10h]; SecurityInformation
0x18007533f  call    cs:__imp_NtSetSecurityObject
0x180075346  nop     dword ptr [rax+rax+00h]
0x18007534b  mov     ebx, eax
0x18007534d  mov     rcx, [rsp+110h+TargetHandle]; Handle
0x180075352  call    cs:__imp_NtClose
0x180075359  nop     dword ptr [rax+rax+00h]
0x18007535e  mov     rcx, [rsp+110h+var_A8]; Sid
0x180075363  test    rcx, rcx
0x180075366  jz      short loc_180075374
0x180075368  call    cs:__imp_RtlFreeSid
0x18007536f  nop     dword ptr [rax+rax+00h]
0x180075374  mov     eax, ebx
0x180075376  mov     rcx, [rbp+10h+var_10]
0x18007537a  xor     rcx, rsp; StackCookie
0x18007537d  call    __security_check_cookie
0x180075382  lea     r11, [rsp+110h+var_s0]
0x18007538a  mov     rbx, [r11+18h]
0x18007538e  mov     rdi, [r11+20h]
0x180075392  mov     rsp, r11
0x180075395  pop     rbp
0x180075396  retn
```
