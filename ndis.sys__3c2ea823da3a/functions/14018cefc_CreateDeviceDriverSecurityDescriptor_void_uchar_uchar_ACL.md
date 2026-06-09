# CreateDeviceDriverSecurityDescriptor(void *,uchar,uchar,_ACL *)

- ea: `0x14018cefc`
- end: `0x14018d1fd`
- name: `?CreateDeviceDriverSecurityDescriptor@@YAJPEAXEEPEAU_ACL@@@Z`
- size: `769`
- prototype: `int(void *, unsigned __int8, unsigned __int8, struct _ACL *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14018ca88`

## callees

- `0x14018cc98`
- `0x14018cefc`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x14018d077`
- `ntoskrnl!RtlLengthSid` at `0x14018d0eb`
- `ntoskrnl!RtlLengthSid` at `0x14018d077`
- `ntoskrnl!RtlLengthSid` at `0x14018d0eb`
- `ntoskrnl!ObGetObjectSecurity` at `0x14018cf49`
- `ntoskrnl!ObGetObjectSecurity` at `0x14018cf49`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14018cf6d`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14018cf6d`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x14018d054`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x14018d054`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14018d092`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14018d092`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x14018d0b8`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x14018d0b8`
- `ntoskrnl!RtlSelfRelativeToAbsoluteSD` at `0x14018d147`
- `ntoskrnl!RtlSelfRelativeToAbsoluteSD` at `0x14018d147`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14018d164`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14018d164`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14018d17f`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14018d17f`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14018d1cc`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14018d1cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018d192`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018d1a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018d1b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018d192`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018d1a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018d1b9`
- `ntoskrnl!ExAllocatePool2` at `0x14018d008`
- `ntoskrnl!ExAllocatePool2` at `0x14018d030`
- `ntoskrnl!ExAllocatePool2` at `0x14018d008`
- `ntoskrnl!ExAllocatePool2` at `0x14018d030`

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
0x14018cefc  mov     rax, rsp
0x14018ceff  mov     [rax+8], rbx
0x14018cf03  mov     [rax+20h], r9
0x14018cf07  mov     [rax+10h], dl
0x14018cf0a  push    rbp
0x14018cf0b  push    rsi
0x14018cf0c  push    rdi
0x14018cf0d  push    r12
0x14018cf0f  push    r13
0x14018cf11  push    r14
0x14018cf13  push    r15
0x14018cf15  lea     rbp, [rax-5Fh]
0x14018cf19  sub     rsp, 0B0h
0x14018cf20  xor     r13d, r13d
0x14018cf23  lea     rdx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14018cf27  mov     dil, r8b
0x14018cf2a  mov     [rbp+57h+MemoryAllocated], r13b
0x14018cf2e  lea     r8, [rbp+57h+MemoryAllocated]; MemoryAllocated
0x14018cf32  mov     [rbp+57h+SecurityDescriptor], r13
0x14018cf36  mov     [rbp+57h+Dacl], r13
0x14018cf3a  mov     r12, rcx
0x14018cf3d  mov     [rbp+57h+DaclPresent], r13b
0x14018cf41  mov     [rbp+57h+DaclDefaulted], r13b
0x14018cf45  mov     [rbp+57h+SaclPresent], r13
0x14018cf49  call    cs:__imp_ObGetObjectSecurity
0x14018cf50  nop     dword ptr [rax+rax+00h]
0x14018cf55  test    eax, eax
0x14018cf57  js      loc_14018D1DA
0x14018cf5d  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14018cf61  lea     r9, [rbp+57h+DaclDefaulted]; DaclDefaulted
0x14018cf65  lea     r8, [rbp+57h+Dacl]; Dacl
0x14018cf69  lea     rdx, [rbp+57h+DaclPresent]; DaclPresent
0x14018cf6d  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x14018cf74  nop     dword ptr [rax+rax+00h]
0x14018cf79  mov     ebx, eax
0x14018cf7b  test    eax, eax
0x14018cf7d  js      loc_14018D1C5
0x14018cf83  cmp     [rbp+57h+DaclPresent], r13b
0x14018cf87  jz      loc_14018D1C5
0x14018cf8d  mov     rcx, [rbp+57h+Dacl]; Acl
0x14018cf91  test    rcx, rcx
0x14018cf94  jz      loc_14018D1F6
0x14018cf9a  lea     r9, [rbp+57h+SaclPresent]; struct _ACL **
0x14018cf9e  mov     r8b, dil; unsigned __int8
0x14018cfa1  call    ?AddAces@@YAJPEAU_ACL@@EEPEAPEAU1@@Z; AddAces(_ACL *,uchar,uchar,_ACL * *)
0x14018cfa6  mov     ebx, eax
0x14018cfa8  test    eax, eax
0x14018cfaa  js      loc_14018D1C5
0x14018cfb0  mov     rdi, [rbp+57h+SaclPresent]
0x14018cfb4  test    rdi, rdi
0x14018cfb7  jz      loc_14018D1C5
0x14018cfbd  mov     [rbp+57h+AbsoluteSecurityDescriptorSize], r13d
0x14018cfc1  mov     r14d, 100h
0x14018cfc7  mov     [rbp+57h+var_64], r13d
0x14018cfcb  mov     r8d, 6473444Eh
0x14018cfd1  mov     [rbp+57h+Sacl], r13
0x14018cfd5  mov     ecx, r14d
0x14018cfd8  mov     [rbp+57h+var_68], r13d
0x14018cfdc  mov     [rbp+57h+Owner], r13
0x14018cfe0  mov     [rbp+57h+var_6C], r13d
0x14018cfe4  mov     [rbp+57h+Group], r13
0x14018cfe8  mov     [rbp+57h+PrimaryGroupSize], r13d
0x14018cfec  mov     [rbp+57h+OwnerDefaulted], r13b
0x14018cff0  mov     [rbp+57h+GroupDefaulted], r13b
0x14018cff4  mov     byte ptr [rbp+57h+SaclPresent], r13b
0x14018cff8  mov     [rbp+57h+SaclDefaulted], r13b
0x14018cffc  movzx   eax, word ptr [rdi+2]
0x14018d000  add     eax, 28h ; '('
0x14018d003  mov     edx, eax
0x14018d005  mov     [rbp+57h+AbsoluteSecurityDescriptorSize], eax
0x14018d008  call    cs:__imp_ExAllocatePool2
0x14018d00f  nop     dword ptr [rax+rax+00h]
0x14018d014  mov     rsi, rax
0x14018d017  test    rax, rax
0x14018d01a  jz      loc_14018D1B4
0x14018d020  movzx   edx, word ptr [rdi+2]
0x14018d024  mov     r8d, 6164444Eh
0x14018d02a  mov     ecx, r14d
0x14018d02d  mov     [rbp+57h+var_64], edx
0x14018d030  call    cs:__imp_ExAllocatePool2
0x14018d037  nop     dword ptr [rax+rax+00h]
0x14018d03c  mov     r14, rax
0x14018d03f  test    rax, rax
0x14018d042  jz      loc_14018D18D
0x14018d048  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14018d04c  lea     r8, [rbp+57h+OwnerDefaulted]; OwnerDefaulted
0x14018d050  lea     rdx, [rbp+57h+Owner]; Owner
0x14018d054  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x14018d05b  nop     dword ptr [rax+rax+00h]
0x14018d060  mov     ebx, eax
0x14018d062  test    eax, eax
0x14018d064  js      loc_14018D18D
0x14018d06a  mov     rcx, [rbp+57h+Owner]; Sid
0x14018d06e  test    rcx, rcx
0x14018d071  jz      loc_14018D18D
0x14018d077  call    cs:__imp_RtlLengthSid
0x14018d07e  nop     dword ptr [rax+rax+00h]
0x14018d083  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14018d087  lea     r8, [rbp+57h+GroupDefaulted]; GroupDefaulted
0x14018d08b  lea     rdx, [rbp+57h+Group]; Group
0x14018d08f  mov     [rbp+57h+var_6C], eax
0x14018d092  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x14018d099  nop     dword ptr [rax+rax+00h]
0x14018d09e  mov     ebx, eax
0x14018d0a0  test    eax, eax
0x14018d0a2  js      loc_14018D18D
0x14018d0a8  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14018d0ac  lea     r9, [rbp+57h+SaclDefaulted]; SaclDefaulted
0x14018d0b0  lea     r8, [rbp+57h+Sacl]; Sacl
0x14018d0b4  lea     rdx, [rbp+57h+SaclPresent]; SaclPresent
0x14018d0b8  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x14018d0bf  nop     dword ptr [rax+rax+00h]
0x14018d0c4  mov     ebx, eax
0x14018d0c6  test    eax, eax
0x14018d0c8  js      loc_14018D18D
0x14018d0ce  lea     r15d, [r13+7]
0x14018d0d2  cmp     byte ptr [rbp+57h+SaclPresent], r13b
0x14018d0d6  jz      short loc_14018D0E7
0x14018d0d8  mov     rax, [rbp+57h+Sacl]
0x14018d0dc  lea     r15d, [r13+0Fh]
0x14018d0e0  movzx   ecx, word ptr [rax+2]
0x14018d0e4  mov     [rbp+57h+var_68], ecx
0x14018d0e7  mov     rcx, [rbp+57h+Group]; Sid
0x14018d0eb  call    cs:__imp_RtlLengthSid
0x14018d0f2  nop     dword ptr [rax+rax+00h]
0x14018d0f7  mov     rcx, [rbp+57h+SecurityDescriptor]; SelfRelativeSecurityDescriptor
0x14018d0fb  lea     r8, [rbp+57h+AbsoluteSecurityDescriptorSize]; AbsoluteSecurityDescriptorSize
0x14018d0ff  mov     [rbp+57h+PrimaryGroupSize], eax
0x14018d102  mov     r9, r14; Dacl
0x14018d105  lea     rax, [rbp+57h+PrimaryGroupSize]
0x14018d109  mov     rdx, rsi; AbsoluteSecurityDescriptor
0x14018d10c  mov     [rsp+50h], rax; PrimaryGroupSize
0x14018d111  mov     rax, [rbp+57h+Group]
0x14018d115  mov     [rsp+0E0h+PrimaryGroup], rax; PrimaryGroup
0x14018d11a  lea     rax, [rbp+57h+var_6C]
0x14018d11e  mov     [rsp+0E0h+OwnerSize], rax; OwnerSize
0x14018d123  mov     rax, [rbp+57h+Owner]
0x14018d127  mov     [rsp+0E0h+var_A8], rax; Owner
0x14018d12c  lea     rax, [rbp+57h+var_68]
0x14018d130  mov     [rsp+0E0h+SaclSize], rax; SaclSize
0x14018d135  mov     rax, [rbp+57h+Sacl]
0x14018d139  mov     [rsp+0E0h+var_B8], rax; Sacl
0x14018d13e  lea     rax, [rbp+57h+var_64]
0x14018d142  mov     [rsp+0E0h+DaclSize], rax; DaclSize
0x14018d147  call    cs:__imp_RtlSelfRelativeToAbsoluteSD
0x14018d14e  nop     dword ptr [rax+rax+00h]
0x14018d153  mov     ebx, eax
0x14018d155  test    eax, eax
0x14018d157  js      short loc_14018D18D
0x14018d159  xor     r9d, r9d; DaclDefaulted
0x14018d15c  mov     r8, rdi; Dacl
0x14018d15f  mov     dl, 1; DaclPresent
0x14018d161  mov     rcx, rsi; SecurityDescriptor
0x14018d164  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14018d16b  nop     dword ptr [rax+rax+00h]
0x14018d170  mov     ebx, eax
0x14018d172  test    eax, eax
0x14018d174  js      short loc_14018D18D
0x14018d176  mov     r8, rsi
0x14018d179  mov     edx, r15d
0x14018d17c  mov     rcx, r12
0x14018d17f  call    cs:__imp_ObSetSecurityObjectByPointer
0x14018d186  nop     dword ptr [rax+rax+00h]
0x14018d18b  mov     ebx, eax
0x14018d18d  xor     edx, edx; Tag
0x14018d18f  mov     rcx, rsi; P
0x14018d192  call    cs:__imp_ExFreePoolWithTag
0x14018d199  nop     dword ptr [rax+rax+00h]
0x14018d19e  test    r14, r14
0x14018d1a1  jz      short loc_14018D1B4
0x14018d1a3  xor     edx, edx; Tag
0x14018d1a5  mov     rcx, r14; P
0x14018d1a8  call    cs:__imp_ExFreePoolWithTag
0x14018d1af  nop     dword ptr [rax+rax+00h]
0x14018d1b4  xor     edx, edx; Tag
0x14018d1b6  mov     rcx, rdi; P
0x14018d1b9  call    cs:__imp_ExFreePoolWithTag
0x14018d1c0  nop     dword ptr [rax+rax+00h]
0x14018d1c5  mov     dl, [rbp+57h+MemoryAllocated]; MemoryAllocated
0x14018d1c8  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14018d1cc  call    cs:__imp_ObReleaseObjectSecurity
0x14018d1d3  nop     dword ptr [rax+rax+00h]
0x14018d1d8  mov     eax, ebx
0x14018d1da  mov     rbx, [rsp+0E0h+arg_0]
0x14018d1e2  add     rsp, 0B0h
0x14018d1e9  pop     r15
0x14018d1eb  pop     r14
0x14018d1ed  pop     r13
0x14018d1ef  pop     r12
0x14018d1f1  pop     rdi
0x14018d1f2  pop     rsi
0x14018d1f3  pop     rbp
0x14018d1f4  retn
0x14018d1f6  mov     eax, 0C0000001h
0x14018d1fb  jmp     short loc_14018D1DA
```
