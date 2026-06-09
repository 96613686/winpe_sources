# LuafvInitializeSecurity

- ea: `0x14002965c`
- end: `0x14002977c`
- name: `LuafvInitializeSecurity`
- size: `288`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400291a8`

## callees

- `0x140016d94`
- `0x14001b6a0`
- `0x14001dd90`
- `0x14002965c`

## import_xrefs

- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140029672`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140029672`
- `ntoskrnl!RtlCreateAcl` at `0x1400296d4`
- `ntoskrnl!RtlCreateAcl` at `0x1400296d4`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140029703`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140029703`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140029724`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140029724`
- `ntoskrnl!RtlLengthSid` at `0x140029699`
- `ntoskrnl!RtlLengthSid` at `0x140029699`
- `ntoskrnl!SeExports` at `0x140029688`
- `ntoskrnl!SeExports` at `0x1400296e6`

## pseudocode

```c
__int64 LuafvInitializeSecurity()
{
  int SecurityDescriptor; // ebx
  unsigned int v1; // ebx
  struct _ACL *Pool; // rax
  struct _ACL *v3; // rdi

  SecurityDescriptor = RtlCreateSecurityDescriptor(&LuafvInteractiveDescriptor, 1u);
  if ( SecurityDescriptor >= 0 )
  {
    v1 = RtlLengthSid(SeExports->SeInteractiveSid) + 20;
    Pool = (struct _ACL *)LuafvAllocatePool(1, v1, 5);
    v3 = Pool;
    if ( Pool )
    {
      SecurityDescriptor = RtlCreateAcl(Pool, v1, 2u);
      if ( SecurityDescriptor < 0
        || (SecurityDescriptor = RtlAddAccessAllowedAce(v3, 2u, 1u, SeExports->SeInteractiveSid), SecurityDescriptor < 0)
        || (SecurityDescriptor = RtlSetDaclSecurityDescriptor(&LuafvInteractiveDescriptor, 1u, v3, 0),
            SecurityDescriptor < 0)
        || (SecurityDescriptor = LuafvCreateTrustedInstallerSid((char **)&Sid1), SecurityDescriptor < 0) )
      {
        LuafvFreePool((__int64)v3);
        LuafvInteractiveDescriptor = 0;
        qword_14000E8C0 = 0;
        xmmword_14000E8B0 = 0;
      }
      else
      {
        return 0;
      }
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x14002965c  mov     [rsp+arg_0], rbx
0x140029661  push    rdi
0x140029662  sub     rsp, 20h
0x140029666  mov     edx, 1; Revision
0x14002966b  lea     rcx, LuafvInteractiveDescriptor; SecurityDescriptor
0x140029672  call    cs:__imp_RtlCreateSecurityDescriptor
0x140029679  nop     dword ptr [rax+rax+00h]
0x14002967e  mov     ebx, eax
0x140029680  test    eax, eax
0x140029682  js      loc_14002976E
0x140029688  mov     rax, cs:__imp_SeExports
0x14002968f  mov     rcx, [rax]
0x140029692  mov     rcx, [rcx+100h]; Sid
0x140029699  call    cs:__imp_RtlLengthSid
0x1400296a0  nop     dword ptr [rax+rax+00h]
0x1400296a5  mov     r8b, 5
0x1400296a8  mov     ecx, 1
0x1400296ad  lea     ebx, [rax+14h]
0x1400296b0  mov     edx, ebx
0x1400296b2  call    LuafvAllocatePool
0x1400296b7  mov     rdi, rax
0x1400296ba  test    rax, rax
0x1400296bd  jnz     short loc_1400296C9
0x1400296bf  mov     ebx, 0C000009Ah
0x1400296c4  jmp     loc_14002976E
0x1400296c9  mov     r8d, 2; AclRevision
0x1400296cf  mov     edx, ebx; AclLength
0x1400296d1  mov     rcx, rdi; Acl
0x1400296d4  call    cs:__imp_RtlCreateAcl
0x1400296db  nop     dword ptr [rax+rax+00h]
0x1400296e0  mov     ebx, eax
0x1400296e2  test    eax, eax
0x1400296e4  js      short loc_14002974C
0x1400296e6  mov     rax, cs:__imp_SeExports
0x1400296ed  mov     edx, 2; AceRevision
0x1400296f2  mov     rcx, rdi; Acl
0x1400296f5  mov     r9, [rax]
0x1400296f8  lea     r8d, [rdx-1]; AccessMask
0x1400296fc  mov     r9, [r9+100h]; Sid
0x140029703  call    cs:__imp_RtlAddAccessAllowedAce
0x14002970a  nop     dword ptr [rax+rax+00h]
0x14002970f  mov     ebx, eax
0x140029711  test    eax, eax
0x140029713  js      short loc_14002974C
0x140029715  xor     r9d, r9d; DaclDefaulted
0x140029718  lea     rcx, LuafvInteractiveDescriptor; SecurityDescriptor
0x14002971f  mov     r8, rdi; Dacl
0x140029722  mov     dl, 1; DaclPresent
0x140029724  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14002972b  nop     dword ptr [rax+rax+00h]
0x140029730  mov     ebx, eax
0x140029732  test    eax, eax
0x140029734  js      short loc_14002974C
0x140029736  lea     rcx, Sid1
0x14002973d  call    LuafvCreateTrustedInstallerSid
0x140029742  mov     ebx, eax
0x140029744  test    eax, eax
0x140029746  js      short loc_14002974C
0x140029748  xor     ebx, ebx
0x14002974a  jmp     short loc_14002976E
0x14002974c  mov     rcx, rdi
0x14002974f  call    LuafvFreePool
0x140029754  xorps   xmm0, xmm0
0x140029757  xor     eax, eax
0x140029759  movups  cs:LuafvInteractiveDescriptor, xmm0
0x140029760  mov     cs:qword_14000E8C0, rax
0x140029767  movups  cs:xmmword_14000E8B0, xmm0
0x14002976e  mov     eax, ebx
0x140029770  mov     rbx, [rsp+28h+arg_0]
0x140029775  add     rsp, 20h
0x140029779  pop     rdi
0x14002977a  retn
```
