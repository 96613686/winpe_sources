# CreateDeviceDriverSecurityDescriptor(void *,uchar,uchar,_ACL *)

- ea: `0x140192f0c`
- end: `0x14019320d`
- name: `?CreateDeviceDriverSecurityDescriptor@@YAJPEAXEEPEAU_ACL@@@Z`
- size: `769`
- prototype: `int(void *, unsigned __int8, unsigned __int8, struct _ACL *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140192a98`

## callees

- `0x140192ca8`
- `0x140192f0c`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x140193087`
- `ntoskrnl!RtlLengthSid` at `0x1401930fb`
- `ntoskrnl!RtlLengthSid` at `0x140193087`
- `ntoskrnl!RtlLengthSid` at `0x1401930fb`
- `ntoskrnl!ObGetObjectSecurity` at `0x140192f59`
- `ntoskrnl!ObGetObjectSecurity` at `0x140192f59`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140192f7d`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140192f7d`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140193064`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140193064`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x1401930a2`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x1401930a2`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1401930c8`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1401930c8`
- `ntoskrnl!RtlSelfRelativeToAbsoluteSD` at `0x140193157`
- `ntoskrnl!RtlSelfRelativeToAbsoluteSD` at `0x140193157`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140193174`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140193174`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14019318f`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14019318f`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x1401931dc`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x1401931dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401931a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401931b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401931c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401931a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401931b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401931c9`
- `ntoskrnl!ExAllocatePool2` at `0x140193018`
- `ntoskrnl!ExAllocatePool2` at `0x140193040`
- `ntoskrnl!ExAllocatePool2` at `0x140193018`
- `ntoskrnl!ExAllocatePool2` at `0x140193040`

## pseudocode

```c
NTSTATUS __fastcall CreateDeviceDriverSecurityDescriptor(void *a1, __int64 a2, unsigned __int8 a3, struct _ACL *a4)
{
  NTSTATUS result; // eax
  unsigned __int8 v7; // dl
  NTSTATUS DaclSecurityDescriptor; // ebx
  struct _ACL *v9; // rdi
  void *Pool2; // rsi
  __int64 AclSize; // rdx
  struct _ACL *v12; // r14
  unsigned int v13; // r15d
  unsigned __int8 MemoryAllocated; // [rsp+68h] [rbp-29h] BYREF
  unsigned __int8 DaclDefaulted; // [rsp+69h] [rbp-28h] BYREF
  unsigned __int8 OwnerDefaulted; // [rsp+6Ah] [rbp-27h] BYREF
  unsigned __int8 GroupDefaulted; // [rsp+6Bh] [rbp-26h] BYREF
  unsigned __int8 SaclDefaulted[4]; // [rsp+6Ch] [rbp-25h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp-21h] BYREF
  ULONG PrimaryGroupSize; // [rsp+78h] [rbp-19h] BYREF
  ULONG OwnerSize; // [rsp+7Ch] [rbp-15h] BYREF
  ULONG SaclSize; // [rsp+80h] [rbp-11h] BYREF
  ULONG DaclSize; // [rsp+84h] [rbp-Dh] BYREF
  ULONG AbsoluteSecurityDescriptorSize; // [rsp+88h] [rbp-9h] BYREF
  PSID Group; // [rsp+90h] [rbp-1h] BYREF
  PSID Owner; // [rsp+98h] [rbp+7h] BYREF
  PACL Sacl; // [rsp+A0h] [rbp+Fh] BYREF
  PACL Dacl; // [rsp+A8h] [rbp+17h] BYREF
  unsigned __int8 DaclPresent; // [rsp+100h] [rbp+6Fh] BYREF
  struct _ACL *SaclPresent; // [rsp+110h] [rbp+7Fh] BYREF

  MemoryAllocated = 0;
  SecurityDescriptor = 0;
  Dacl = 0;
  DaclPresent = 0;
  DaclDefaulted = 0;
  SaclPresent = 0;
  result = ObGetObjectSecurity(a1, &SecurityDescriptor, &MemoryAllocated);
  if ( result >= 0 )
  {
    DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(SecurityDescriptor, &DaclPresent, &Dacl, &DaclDefaulted);
    if ( DaclSecurityDescriptor >= 0 && DaclPresent )
    {
      if ( !Dacl )
        return -1073741823;
      DaclSecurityDescriptor = AddAces(Dacl, v7, a3, &SaclPresent);
      if ( DaclSecurityDescriptor >= 0 )
      {
        v9 = SaclPresent;
        if ( SaclPresent )
        {
          AbsoluteSecurityDescriptorSize = 0;
          DaclSize = 0;
          Sacl = 0;
          SaclSize = 0;
          Owner = 0;
          OwnerSize = 0;
          Group = 0;
          PrimaryGroupSize = 0;
          OwnerDefaulted = 0;
          GroupDefaulted = 0;
          LOBYTE(SaclPresent) = 0;
          SaclDefaulted[0] = 0;
          AbsoluteSecurityDescriptorSize = v9->AclSize + 40;
          Pool2 = (void *)ExAllocatePool2(256, AbsoluteSecurityDescriptorSize, 1685275726);
          if ( Pool2 )
          {
            AclSize = v9->AclSize;
            DaclSize = v9->AclSize;
            v12 = (struct _ACL *)ExAllocatePool2(256, AclSize, 1633961038);
            if ( v12 )
            {
              DaclSecurityDescriptor = RtlGetOwnerSecurityDescriptor(SecurityDescriptor, &Owner, &OwnerDefaulted);
              if ( DaclSecurityDescriptor >= 0 )
              {
                if ( Owner )
                {
                  OwnerSize = RtlLengthSid(Owner);
                  DaclSecurityDescriptor = RtlGetGroupSecurityDescriptor(SecurityDescriptor, &Group, &GroupDefaulted);
                  if ( DaclSecurityDescriptor >= 0 )
                  {
                    DaclSecurityDescriptor = RtlGetSaclSecurityDescriptor(
                                               SecurityDescriptor,
                                               (PBOOLEAN)&SaclPresent,
                                               &Sacl,
                                               SaclDefaulted);
                    if ( DaclSecurityDescriptor >= 0 )
                    {
                      v13 = 7;
                      if ( (_BYTE)SaclPresent )
                      {
                        v13 = 15;
                        SaclSize = Sacl->AclSize;
                      }
                      PrimaryGroupSize = RtlLengthSid(Group);
                      DaclSecurityDescriptor = RtlSelfRelativeToAbsoluteSD(
                                                 SecurityDescriptor,
                                                 Pool2,
                                                 &AbsoluteSecurityDescriptorSize,
                                                 v12,
                                                 &DaclSize,
                                                 Sacl,
                                                 &SaclSize,
                                                 Owner,
                                                 &OwnerSize,
                                                 Group,
                                                 &PrimaryGroupSize);
                      if ( DaclSecurityDescriptor >= 0 )
                      {
                        DaclSecurityDescriptor = RtlSetDaclSecurityDescriptor(Pool2, 1u, v9, 0);
                        if ( DaclSecurityDescriptor >= 0 )
                          DaclSecurityDescriptor = ObSetSecurityObjectByPointer(a1, v13, Pool2);
                      }
                    }
                  }
                }
              }
            }
            ExFreePoolWithTag(Pool2, 0);
            if ( v12 )
              ExFreePoolWithTag(v12, 0);
          }
          ExFreePoolWithTag(v9, 0);
        }
      }
    }
    ObReleaseObjectSecurity(SecurityDescriptor, MemoryAllocated);
    return DaclSecurityDescriptor;
  }
  return result;
}

```

## disassembly

```asm
0x140192f0c  mov     rax, rsp
0x140192f0f  mov     [rax+8], rbx
0x140192f13  mov     [rax+20h], r9
0x140192f17  mov     [rax+10h], dl
0x140192f1a  push    rbp
0x140192f1b  push    rsi
0x140192f1c  push    rdi
0x140192f1d  push    r12
0x140192f1f  push    r13
0x140192f21  push    r14
0x140192f23  push    r15
0x140192f25  lea     rbp, [rax-5Fh]
0x140192f29  sub     rsp, 0B0h
0x140192f30  xor     r13d, r13d
0x140192f33  lea     rdx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140192f37  mov     dil, r8b
0x140192f3a  mov     [rbp+57h+MemoryAllocated], r13b
0x140192f3e  lea     r8, [rbp+57h+MemoryAllocated]; MemoryAllocated
0x140192f42  mov     [rbp+57h+SecurityDescriptor], r13
0x140192f46  mov     [rbp+57h+Dacl], r13
0x140192f4a  mov     r12, rcx
0x140192f4d  mov     [rbp+57h+DaclPresent], r13b
0x140192f51  mov     [rbp+57h+DaclDefaulted], r13b
0x140192f55  mov     [rbp+57h+SaclPresent], r13
0x140192f59  call    cs:__imp_ObGetObjectSecurity
0x140192f60  nop     dword ptr [rax+rax+00h]
0x140192f65  test    eax, eax
0x140192f67  js      loc_1401931EA
0x140192f6d  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140192f71  lea     r9, [rbp+57h+DaclDefaulted]; DaclDefaulted
0x140192f75  lea     r8, [rbp+57h+Dacl]; Dacl
0x140192f79  lea     rdx, [rbp+57h+DaclPresent]; DaclPresent
0x140192f7d  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x140192f84  nop     dword ptr [rax+rax+00h]
0x140192f89  mov     ebx, eax
0x140192f8b  test    eax, eax
0x140192f8d  js      loc_1401931D5
0x140192f93  cmp     [rbp+57h+DaclPresent], r13b
0x140192f97  jz      loc_1401931D5
0x140192f9d  mov     rcx, [rbp+57h+Dacl]; Acl
0x140192fa1  test    rcx, rcx
0x140192fa4  jz      loc_140193206
0x140192faa  lea     r9, [rbp+57h+SaclPresent]; struct _ACL **
0x140192fae  mov     r8b, dil; unsigned __int8
0x140192fb1  call    ?AddAces@@YAJPEAU_ACL@@EEPEAPEAU1@@Z; AddAces(_ACL *,uchar,uchar,_ACL * *)
0x140192fb6  mov     ebx, eax
0x140192fb8  test    eax, eax
0x140192fba  js      loc_1401931D5
0x140192fc0  mov     rdi, [rbp+57h+SaclPresent]
0x140192fc4  test    rdi, rdi
0x140192fc7  jz      loc_1401931D5
0x140192fcd  mov     [rbp+57h+AbsoluteSecurityDescriptorSize], r13d
0x140192fd1  mov     r14d, 100h
0x140192fd7  mov     [rbp+57h+var_64], r13d
0x140192fdb  mov     r8d, 6473444Eh
0x140192fe1  mov     [rbp+57h+Sacl], r13
0x140192fe5  mov     ecx, r14d
0x140192fe8  mov     [rbp+57h+var_68], r13d
0x140192fec  mov     [rbp+57h+Owner], r13
0x140192ff0  mov     [rbp+57h+var_6C], r13d
0x140192ff4  mov     [rbp+57h+Group], r13
0x140192ff8  mov     [rbp+57h+PrimaryGroupSize], r13d
0x140192ffc  mov     [rbp+57h+OwnerDefaulted], r13b
0x140193000  mov     [rbp+57h+GroupDefaulted], r13b
0x140193004  mov     byte ptr [rbp+57h+SaclPresent], r13b
0x140193008  mov     [rbp+57h+SaclDefaulted], r13b
0x14019300c  movzx   eax, word ptr [rdi+2]
0x140193010  add     eax, 28h ; '('
0x140193013  mov     edx, eax
0x140193015  mov     [rbp+57h+AbsoluteSecurityDescriptorSize], eax
0x140193018  call    cs:__imp_ExAllocatePool2
0x14019301f  nop     dword ptr [rax+rax+00h]
0x140193024  mov     rsi, rax
0x140193027  test    rax, rax
0x14019302a  jz      loc_1401931C4
0x140193030  movzx   edx, word ptr [rdi+2]
0x140193034  mov     r8d, 6164444Eh
0x14019303a  mov     ecx, r14d
0x14019303d  mov     [rbp+57h+var_64], edx
0x140193040  call    cs:__imp_ExAllocatePool2
0x140193047  nop     dword ptr [rax+rax+00h]
0x14019304c  mov     r14, rax
0x14019304f  test    rax, rax
0x140193052  jz      loc_14019319D
0x140193058  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14019305c  lea     r8, [rbp+57h+OwnerDefaulted]; OwnerDefaulted
0x140193060  lea     rdx, [rbp+57h+Owner]; Owner
0x140193064  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x14019306b  nop     dword ptr [rax+rax+00h]
0x140193070  mov     ebx, eax
0x140193072  test    eax, eax
0x140193074  js      loc_14019319D
0x14019307a  mov     rcx, [rbp+57h+Owner]; Sid
0x14019307e  test    rcx, rcx
0x140193081  jz      loc_14019319D
0x140193087  call    cs:__imp_RtlLengthSid
0x14019308e  nop     dword ptr [rax+rax+00h]
0x140193093  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140193097  lea     r8, [rbp+57h+GroupDefaulted]; GroupDefaulted
0x14019309b  lea     rdx, [rbp+57h+Group]; Group
0x14019309f  mov     [rbp+57h+var_6C], eax
0x1401930a2  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x1401930a9  nop     dword ptr [rax+rax+00h]
0x1401930ae  mov     ebx, eax
0x1401930b0  test    eax, eax
0x1401930b2  js      loc_14019319D
0x1401930b8  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1401930bc  lea     r9, [rbp+57h+SaclDefaulted]; SaclDefaulted
0x1401930c0  lea     r8, [rbp+57h+Sacl]; Sacl
0x1401930c4  lea     rdx, [rbp+57h+SaclPresent]; SaclPresent
0x1401930c8  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x1401930cf  nop     dword ptr [rax+rax+00h]
0x1401930d4  mov     ebx, eax
0x1401930d6  test    eax, eax
0x1401930d8  js      loc_14019319D
0x1401930de  lea     r15d, [r13+7]
0x1401930e2  cmp     byte ptr [rbp+57h+SaclPresent], r13b
0x1401930e6  jz      short loc_1401930F7
0x1401930e8  mov     rax, [rbp+57h+Sacl]
0x1401930ec  lea     r15d, [r13+0Fh]
0x1401930f0  movzx   ecx, word ptr [rax+2]
0x1401930f4  mov     [rbp+57h+var_68], ecx
0x1401930f7  mov     rcx, [rbp+57h+Group]; Sid
0x1401930fb  call    cs:__imp_RtlLengthSid
0x140193102  nop     dword ptr [rax+rax+00h]
0x140193107  mov     rcx, [rbp+57h+SecurityDescriptor]; SelfRelativeSecurityDescriptor
0x14019310b  lea     r8, [rbp+57h+AbsoluteSecurityDescriptorSize]; AbsoluteSecurityDescriptorSize
0x14019310f  mov     [rbp+57h+PrimaryGroupSize], eax
0x140193112  mov     r9, r14; Dacl
0x140193115  lea     rax, [rbp+57h+PrimaryGroupSize]
0x140193119  mov     rdx, rsi; AbsoluteSecurityDescriptor
0x14019311c  mov     [rsp+50h], rax; PrimaryGroupSize
0x140193121  mov     rax, [rbp+57h+Group]
0x140193125  mov     [rsp+0E0h+PrimaryGroup], rax; PrimaryGroup
0x14019312a  lea     rax, [rbp+57h+var_6C]
0x14019312e  mov     [rsp+0E0h+OwnerSize], rax; OwnerSize
0x140193133  mov     rax, [rbp+57h+Owner]
0x140193137  mov     [rsp+0E0h+var_A8], rax; Owner
0x14019313c  lea     rax, [rbp+57h+var_68]
0x140193140  mov     [rsp+0E0h+SaclSize], rax; SaclSize
0x140193145  mov     rax, [rbp+57h+Sacl]
0x140193149  mov     [rsp+0E0h+var_B8], rax; Sacl
0x14019314e  lea     rax, [rbp+57h+var_64]
0x140193152  mov     [rsp+0E0h+DaclSize], rax; DaclSize
0x140193157  call    cs:__imp_RtlSelfRelativeToAbsoluteSD
0x14019315e  nop     dword ptr [rax+rax+00h]
0x140193163  mov     ebx, eax
0x140193165  test    eax, eax
0x140193167  js      short loc_14019319D
0x140193169  xor     r9d, r9d; DaclDefaulted
0x14019316c  mov     r8, rdi; Dacl
0x14019316f  mov     dl, 1; DaclPresent
0x140193171  mov     rcx, rsi; SecurityDescriptor
0x140193174  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14019317b  nop     dword ptr [rax+rax+00h]
0x140193180  mov     ebx, eax
0x140193182  test    eax, eax
0x140193184  js      short loc_14019319D
0x140193186  mov     r8, rsi
0x140193189  mov     edx, r15d
0x14019318c  mov     rcx, r12
0x14019318f  call    cs:__imp_ObSetSecurityObjectByPointer
0x140193196  nop     dword ptr [rax+rax+00h]
0x14019319b  mov     ebx, eax
0x14019319d  xor     edx, edx; Tag
0x14019319f  mov     rcx, rsi; P
0x1401931a2  call    cs:__imp_ExFreePoolWithTag
0x1401931a9  nop     dword ptr [rax+rax+00h]
0x1401931ae  test    r14, r14
0x1401931b1  jz      short loc_1401931C4
0x1401931b3  xor     edx, edx; Tag
0x1401931b5  mov     rcx, r14; P
0x1401931b8  call    cs:__imp_ExFreePoolWithTag
0x1401931bf  nop     dword ptr [rax+rax+00h]
0x1401931c4  xor     edx, edx; Tag
0x1401931c6  mov     rcx, rdi; P
0x1401931c9  call    cs:__imp_ExFreePoolWithTag
0x1401931d0  nop     dword ptr [rax+rax+00h]
0x1401931d5  mov     dl, [rbp+57h+MemoryAllocated]; MemoryAllocated
0x1401931d8  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1401931dc  call    cs:__imp_ObReleaseObjectSecurity
0x1401931e3  nop     dword ptr [rax+rax+00h]
0x1401931e8  mov     eax, ebx
0x1401931ea  mov     rbx, [rsp+0E0h+arg_0]
0x1401931f2  add     rsp, 0B0h
0x1401931f9  pop     r15
0x1401931fb  pop     r14
0x1401931fd  pop     r13
0x1401931ff  pop     r12
0x140193201  pop     rdi
0x140193202  pop     rsi
0x140193203  pop     rbp
0x140193204  retn
0x140193206  mov     eax, 0C0000001h
0x14019320b  jmp     short loc_1401931EA
```
