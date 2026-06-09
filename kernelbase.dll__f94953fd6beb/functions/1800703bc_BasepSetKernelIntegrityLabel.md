# BasepSetKernelIntegrityLabel

- ea: `0x1800703bc`
- end: `0x180070539`
- name: `BasepSetKernelIntegrityLabel`
- size: `381`
- prototype: `__int64 __fastcall(HANDLE SourceHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006ee28`

## callees

- `0x1800703bc`
- `0x180188f10`

## import_xrefs

- `ntdll!NtClose` at `0x180070500`
- `ntdll!NtClose` at `0x180070500`
- `ntdll!NtDuplicateObject` at `0x18007042a`
- `ntdll!NtDuplicateObject` at `0x18007042a`
- `ntdll!RtlFreeSid` at `0x180070510`
- `ntdll!RtlFreeSid` at `0x180070510`
- `ntdll!RtlCreateAcl` at `0x180070498`
- `ntdll!RtlCreateAcl` at `0x180070498`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180070481`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180070481`
- `ntdll!NtSetSecurityObject` at `0x1800704f3`
- `ntdll!NtSetSecurityObject` at `0x1800704f3`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180070469`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180070469`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x1800704da`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x1800704da`
- `ntdll!RtlAddMandatoryAce` at `0x1800704c0`
- `ntdll!RtlAddMandatoryAce` at `0x1800704c0`

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
0x1800703bc  mov     [rsp-8+arg_8], rbx
0x1800703c1  mov     [rsp-8+arg_10], rdi
0x1800703c6  push    rbp
0x1800703c7  lea     rbp, [rsp-10h]
0x1800703cc  sub     rsp, 110h
0x1800703d3  mov     rax, cs:__security_cookie
0x1800703da  xor     rax, rsp
0x1800703dd  mov     [rbp+10h+var_10], rax
0x1800703e1  xor     edi, edi
0x1800703e3  mov     word ptr [rbp+10h+IdentifierAuthority.Value+4], 1000h
0x1800703e9  xor     eax, eax
0x1800703eb  mov     [rsp+110h+Options], edi; Options
0x1800703ef  xorps   xmm0, xmm0
0x1800703f2  mov     [rbp+10h+var_80], rax
0x1800703f6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800703fa  mov     dword ptr [rsp+110h+HandleAttributes], edi; HandleAttributes
0x1800703fe  mov     rdx, rcx; SourceHandle
0x180070401  mov     [rsp+110h+var_A8], rdi
0x180070406  mov     r8, rax; TargetProcessHandle
0x180070409  mov     dword ptr [rbp+10h+IdentifierAuthority.Value], edi
0x18007040c  mov     rcx, rax; SourceProcessHandle
0x18007040f  mov     [rsp+110h+TargetHandle], rdi
0x180070414  lea     r9, [rsp+110h+TargetHandle]; TargetHandle
0x180070419  mov     [rsp+110h+DesiredAccess], 0F000Fh; DesiredAccess
0x180070421  movups  [rsp+110h+SecurityDescriptor], xmm0
0x180070426  movups  [rbp+10h+var_90], xmm0
0x18007042a  call    cs:__imp_NtDuplicateObject
0x180070430  test    eax, eax
0x180070432  js      loc_180070518
0x180070438  lea     rax, [rsp+110h+var_A8]
0x18007043d  xor     r9d, r9d; SubAuthority1
0x180070440  mov     [rsp+110h+Sid], rax; Sid
0x180070445  lea     rcx, [rbp+10h+IdentifierAuthority]; IdentifierAuthority
0x180070449  mov     [rsp+110h+SubAuthority7], edi; SubAuthority7
0x18007044d  mov     r8d, 1000h; SubAuthority0
0x180070453  mov     [rsp+110h+SubAuthority6], edi; SubAuthority6
0x180070457  mov     dl, 1; SubAuthorityCount
0x180070459  mov     [rsp+110h+SubAuthority5], edi; SubAuthority5
0x18007045d  mov     [rsp+110h+Options], edi; SubAuthority4
0x180070461  mov     dword ptr [rsp+110h+HandleAttributes], edi; SubAuthority3
0x180070465  mov     [rsp+110h+DesiredAccess], edi; SubAuthority2
0x180070469  call    cs:__imp_RtlAllocateAndInitializeSid
0x18007046f  mov     ebx, eax
0x180070471  test    eax, eax
0x180070473  js      loc_1800704FB
0x180070479  lea     edx, [rdi+1]; Revision
0x18007047c  lea     rcx, [rsp+110h+SecurityDescriptor]; SecurityDescriptor
0x180070481  call    cs:__imp_RtlCreateSecurityDescriptor
0x180070487  mov     ebx, eax
0x180070489  test    eax, eax
0x18007048b  js      short loc_1800704FB
0x18007048d  lea     edx, [rdi+58h]; AclSize
0x180070490  lea     r8d, [rdi+2]; AclRevision
0x180070494  lea     rcx, [rbp+10h+Acl]; Acl
0x180070498  call    cs:__imp_RtlCreateAcl
0x18007049e  mov     ebx, eax
0x1800704a0  test    eax, eax
0x1800704a2  js      short loc_1800704FB
0x1800704a4  mov     r9, [rsp+110h+var_A8]; MandatoryFlags
0x1800704a9  lea     edx, [rdi+2]; Revision
0x1800704ac  mov     dword ptr [rsp+110h+HandleAttributes], 1; LabelSid
0x1800704b4  lea     rcx, [rbp+10h+Acl]; Acl
0x1800704b8  xor     r8d, r8d; Flags
0x1800704bb  mov     byte ptr [rsp+110h+DesiredAccess], 11h; AceType
0x1800704c0  call    cs:__imp_RtlAddMandatoryAce
0x1800704c6  mov     ebx, eax
0x1800704c8  test    eax, eax
0x1800704ca  js      short loc_1800704FB
0x1800704cc  xor     r9d, r9d; SaclDefaulted
0x1800704cf  lea     r8, [rbp+10h+Acl]; Sacl
0x1800704d3  mov     dl, 1; SaclPresent
0x1800704d5  lea     rcx, [rsp+110h+SecurityDescriptor]; SecurityDescriptor
0x1800704da  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x1800704e0  mov     ebx, eax
0x1800704e2  test    eax, eax
0x1800704e4  js      short loc_1800704FB
0x1800704e6  mov     rcx, [rsp+110h+TargetHandle]; Handle
0x1800704eb  lea     r8, [rsp+110h+SecurityDescriptor]; SecurityDescriptor
0x1800704f0  lea     edx, [rdi+10h]; SecurityInformation
0x1800704f3  call    cs:__imp_NtSetSecurityObject
0x1800704f9  mov     ebx, eax
0x1800704fb  mov     rcx, [rsp+110h+TargetHandle]; Handle
0x180070500  call    cs:__imp_NtClose
0x180070506  mov     rcx, [rsp+110h+var_A8]; Sid
0x18007050b  test    rcx, rcx
0x18007050e  jz      short loc_180070516
0x180070510  call    cs:__imp_RtlFreeSid
0x180070516  mov     eax, ebx
0x180070518  mov     rcx, [rbp+10h+var_10]
0x18007051c  xor     rcx, rsp; StackCookie
0x18007051f  call    __security_check_cookie
0x180070524  lea     r11, [rsp+110h+var_s0]
0x18007052c  mov     rbx, [r11+18h]
0x180070530  mov     rdi, [r11+20h]
0x180070534  mov     rsp, r11
0x180070537  pop     rbp
0x180070538  retn
```
