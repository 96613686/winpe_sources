# PcpSetDeviceSecurityDescriptor

- ea: `0x14001e4dc`
- end: `0x14001e800`
- name: `PcpSetDeviceSecurityDescriptor`
- size: `804`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001e2dc`

## callees

- `0x14000eb54`
- `0x14000f48c`
- `0x14000fe04`
- `0x140013110`
- `0x140013300`
- `0x14001e00c`
- `0x14001e4dc`

## import_xrefs

- `ntoskrnl!ObGetObjectSecurity` at `0x14001e567`
- `ntoskrnl!ObGetObjectSecurity` at `0x14001e567`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14001e660`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14001e660`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e773`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e78a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e7a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e773`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e78a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e7a3`
- `ntoskrnl!ExAllocatePool2` at `0x14001e67c`
- `ntoskrnl!ExAllocatePool2` at `0x14001e67c`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14001e637`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14001e637`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x14001e6fd`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x14001e6fd`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14001e759`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14001e759`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14001e744`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14001e744`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14001e6d6`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14001e6d6`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14001e650`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14001e650`

## pseudocode

```c
__int64 PcpSetDeviceSecurityDescriptor()
{
  NTSTATUS ObjectSecurity; // eax
  int v1; // edx
  int v2; // r8d
  int v3; // r9d
  unsigned int v4; // ebx
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // rdx
  int v7; // eax
  PSECURITY_DESCRIPTOR v8; // rdi
  size_t v9; // r14
  void *Pool2; // rax
  struct _GENERIC_MAPPING *GenericMapping; // rax
  NTSTATUS v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  PSECURITY_DESCRIPTOR v15; // rcx
  unsigned __int8 MemoryAllocated[4]; // [rsp+30h] [rbp-29h] BYREF
  DWORD SecurityInformation; // [rsp+34h] [rbp-25h] BYREF
  PSECURITY_DESCRIPTOR ObjectsSecurityDescriptor; // [rsp+38h] [rbp-21h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-19h] BYREF
  PACL Dacl; // [rsp+48h] [rbp-11h] BYREF
  _BYTE ModificationDescriptor[40]; // [rsp+50h] [rbp-9h] BYREF

  Dacl = 0;
  MemoryAllocated[0] = 0;
  SecurityDescriptor = 0;
  ObjectsSecurityDescriptor = 0;
  SecurityInformation = 4;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xBu) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_0a0383b750aa364b280d5887b3b80ddf_Traceguids);
  }
  ObjectSecurity = ObGetObjectSecurity(WPP_MAIN_CB.Queue.ListEntry.Blink, &SecurityDescriptor, MemoryAllocated);
  v4 = ObjectSecurity;
  if ( ObjectSecurity >= 0 )
  {
    v7 = PcpBuildDeviceAcl(&Dacl, v1, v2, v3);
    v4 = v7;
    if ( v7 >= 0 )
    {
      RtlCreateSecurityDescriptor(ModificationDescriptor, 1u);
      RtlSetDaclSecurityDescriptor(ModificationDescriptor, 1u, Dacl, 0);
      v9 = RtlLengthSecurityDescriptor(SecurityDescriptor);
      Pool2 = (void *)ExAllocatePool2(256, v9, 1701274448);
      ObjectsSecurityDescriptor = Pool2;
      v8 = Pool2;
      if ( Pool2 )
      {
        memmove(Pool2, SecurityDescriptor, v9);
        GenericMapping = IoGetFileObjectGenericMapping();
        v12 = SeSetSecurityDescriptorInfo(
                0,
                &SecurityInformation,
                ModificationDescriptor,
                &ObjectsSecurityDescriptor,
                (POOL_TYPE)512,
                GenericMapping);
        v4 = v12;
        if ( v12 >= 0 )
        {
          v4 = ObSetSecurityObjectByPointer(
                 WPP_MAIN_CB.Queue.ListEntry.Blink,
                 SecurityInformation,
                 ObjectsSecurityDescriptor);
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
               && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xBu) )
        {
          WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, v13, v14, (unsigned int)v12);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xBu) )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_0a0383b750aa364b280d5887b3b80ddf_Traceguids);
        }
        v8 = 0;
      }
    }
    else
    {
      v8 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xBu) )
      {
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          WPP_0a0383b750aa364b280d5887b3b80ddf_Traceguids,
          (unsigned int)v7);
      }
    }
    ObReleaseObjectSecurity(SecurityDescriptor, MemoryAllocated[0]);
    v15 = ObjectsSecurityDescriptor;
    if ( ObjectsSecurityDescriptor != v8 )
    {
      ExFreePoolWithTag(v8, 0);
      v15 = ObjectsSecurityDescriptor;
    }
    if ( v15 )
      ExFreePoolWithTag(v15, 0);
    if ( Dacl )
      ExFreePoolWithTag(Dacl, 0);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xBu) )
    {
      v6 = 18;
      goto LABEL_41;
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xBu) )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        WPP_0a0383b750aa364b280d5887b3b80ddf_Traceguids,
        (unsigned int)ObjectSecurity);
    }
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xBu) )
    {
      v6 = 14;
LABEL_41:
      WPP_SF_D(v5->AttachedDevice, v6, WPP_0a0383b750aa364b280d5887b3b80ddf_Traceguids, v4);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14001e4dc  push    rbp
0x14001e4de  push    rbx
0x14001e4df  push    rdi
0x14001e4e0  push    r12
0x14001e4e2  push    r13
0x14001e4e4  push    r14
0x14001e4e6  lea     rbp, [rsp-2Fh]
0x14001e4eb  sub     rsp, 88h
0x14001e4f2  mov     rax, cs:__security_cookie
0x14001e4f9  xor     rax, rsp
0x14001e4fc  mov     [rbp+57h+var_38], rax
0x14001e500  mov     [rbp+57h+Dacl], 0
0x14001e508  mov     [rbp+57h+MemoryAllocated], 0
0x14001e50c  mov     [rbp+57h+SecurityDescriptor], 0
0x14001e514  mov     [rbp+57h+ObjectsSecurityDescriptor], 0
0x14001e51c  mov     [rbp+57h+SecurityInformation], 4
0x14001e523  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e52a  lea     r13, WPP_GLOBAL_Control
0x14001e531  cmp     rcx, r13
0x14001e534  jz      short loc_14001E558
0x14001e536  cmp     byte ptr [rcx+29h], 6
0x14001e53a  jb      short loc_14001E558
0x14001e53c  bt      dword ptr [rcx+2Ch], 0Bh
0x14001e541  jnb     short loc_14001E558
0x14001e543  mov     rcx, [rcx+18h]
0x14001e547  lea     r8, WPP_0a0383b750aa364b280d5887b3b80ddf_Traceguids
0x14001e54e  mov     edx, 0Ch
0x14001e553  call    WPP_SF_
0x14001e558  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8; Object
0x14001e55f  lea     r8, [rbp+57h+MemoryAllocated]; MemoryAllocated
0x14001e563  lea     rdx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14001e567  call    cs:__imp_ObGetObjectSecurity
0x14001e56e  nop     dword ptr [rax+rax+00h]
0x14001e573  mov     ebx, eax
0x14001e575  test    eax, eax
0x14001e577  jns     short loc_14001E5DD
0x14001e579  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e580  cmp     rcx, r13
0x14001e583  jz      loc_14001E7E0
0x14001e589  cmp     byte ptr [rcx+29h], 2
0x14001e58d  jb      short loc_14001E5AE
0x14001e58f  bt      dword ptr [rcx+2Ch], 0Bh
0x14001e594  jnb     short loc_14001E5AE
0x14001e596  mov     rcx, [rcx+18h]
0x14001e59a  lea     r8, WPP_0a0383b750aa364b280d5887b3b80ddf_Traceguids
0x14001e5a1  mov     edx, 0Dh
0x14001e5a6  mov     r9d, eax
0x14001e5a9  call    WPP_SF_D
0x14001e5ae  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e5b5  cmp     rcx, r13
0x14001e5b8  jz      loc_14001E7E0
0x14001e5be  cmp     byte ptr [rcx+29h], 2
0x14001e5c2  jb      loc_14001E7E0
0x14001e5c8  bt      dword ptr [rcx+2Ch], 0Bh
0x14001e5cd  jnb     loc_14001E7E0
0x14001e5d3  mov     edx, 0Eh
0x14001e5d8  jmp     loc_14001E7CD
0x14001e5dd  lea     rcx, [rbp+57h+Dacl]
0x14001e5e1  call    PcpBuildDeviceAcl
0x14001e5e6  mov     ebx, eax
0x14001e5e8  test    eax, eax
0x14001e5ea  jns     short loc_14001E62E
0x14001e5ec  xor     edi, edi
0x14001e5ee  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e5f5  cmp     rcx, r13
0x14001e5f8  jz      loc_14001E752
0x14001e5fe  cmp     byte ptr [rcx+29h], 2
0x14001e602  jb      loc_14001E752
0x14001e608  bt      dword ptr [rcx+2Ch], 0Bh
0x14001e60d  jnb     loc_14001E752
0x14001e613  mov     rcx, [rcx+18h]
0x14001e617  lea     edx, [rdi+0Fh]
0x14001e61a  mov     r9d, eax
0x14001e61d  lea     r8, WPP_0a0383b750aa364b280d5887b3b80ddf_Traceguids
0x14001e624  call    WPP_SF_D
0x14001e629  jmp     loc_14001E752
0x14001e62e  mov     edx, 1; Revision
0x14001e633  lea     rcx, [rbp+57h+ModificationDescriptor]; SecurityDescriptor
0x14001e637  call    cs:__imp_RtlCreateSecurityDescriptor
0x14001e63e  nop     dword ptr [rax+rax+00h]
0x14001e643  mov     r8, [rbp+57h+Dacl]; Dacl
0x14001e647  lea     rcx, [rbp+57h+ModificationDescriptor]; SecurityDescriptor
0x14001e64b  xor     r9d, r9d; DaclDefaulted
0x14001e64e  mov     dl, 1; DaclPresent
0x14001e650  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14001e657  nop     dword ptr [rax+rax+00h]
0x14001e65c  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14001e660  call    cs:__imp_RtlLengthSecurityDescriptor
0x14001e667  nop     dword ptr [rax+rax+00h]
0x14001e66c  mov     edx, eax
0x14001e66e  mov     r8d, 65676350h
0x14001e674  mov     ecx, 100h
0x14001e679  mov     r14d, eax
0x14001e67c  call    cs:__imp_ExAllocatePool2
0x14001e683  nop     dword ptr [rax+rax+00h]
0x14001e688  mov     [rbp+57h+ObjectsSecurityDescriptor], rax
0x14001e68c  mov     rdi, rax
0x14001e68f  test    rax, rax
0x14001e692  jnz     short loc_14001E6C7
0x14001e694  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e69b  cmp     rcx, r13
0x14001e69e  jz      short loc_14001E6C0
0x14001e6a0  cmp     byte ptr [rcx+29h], 2
0x14001e6a4  jb      short loc_14001E6C0
0x14001e6a6  bt      dword ptr [rcx+2Ch], 0Bh
0x14001e6ab  jnb     short loc_14001E6C0
0x14001e6ad  mov     rcx, [rcx+18h]
0x14001e6b1  lea     edx, [rax+10h]
0x14001e6b4  lea     r8, WPP_0a0383b750aa364b280d5887b3b80ddf_Traceguids
0x14001e6bb  call    WPP_SF_
0x14001e6c0  xor     edi, edi
0x14001e6c2  jmp     loc_14001E752
0x14001e6c7  mov     rdx, [rbp+57h+SecurityDescriptor]; Src
0x14001e6cb  mov     r8, r14; Size
0x14001e6ce  mov     rcx, rax; void *
0x14001e6d1  call    memmove
0x14001e6d6  call    cs:__imp_IoGetFileObjectGenericMapping
0x14001e6dd  nop     dword ptr [rax+rax+00h]
0x14001e6e2  mov     [rsp+0B0h+GenericMapping], rax; GenericMapping
0x14001e6e7  lea     r9, [rbp+57h+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x14001e6eb  xor     ecx, ecx; Object
0x14001e6ed  mov     [rsp+0B0h+PoolType], 200h; PoolType
0x14001e6f5  lea     r8, [rbp+57h+ModificationDescriptor]; ModificationDescriptor
0x14001e6f9  lea     rdx, [rbp+57h+SecurityInformation]; SecurityInformation
0x14001e6fd  call    cs:__imp_SeSetSecurityDescriptorInfo
0x14001e704  nop     dword ptr [rax+rax+00h]
0x14001e709  mov     ebx, eax
0x14001e70b  test    eax, eax
0x14001e70d  jns     short loc_14001E736
0x14001e70f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e716  cmp     rcx, r13
0x14001e719  jz      short loc_14001E752
0x14001e71b  cmp     byte ptr [rcx+29h], 2
0x14001e71f  jb      short loc_14001E752
0x14001e721  bt      dword ptr [rcx+2Ch], 0Bh
0x14001e726  jnb     short loc_14001E752
0x14001e728  mov     rcx, [rcx+18h]
0x14001e72c  mov     r9d, eax
0x14001e72f  call    WPP_SF_L
0x14001e734  jmp     short loc_14001E752
0x14001e736  mov     r8, [rbp+57h+ObjectsSecurityDescriptor]
0x14001e73a  mov     edx, [rbp+57h+SecurityInformation]
0x14001e73d  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14001e744  call    cs:__imp_ObSetSecurityObjectByPointer
0x14001e74b  nop     dword ptr [rax+rax+00h]
0x14001e750  mov     ebx, eax
0x14001e752  mov     dl, [rbp+57h+MemoryAllocated]; MemoryAllocated
0x14001e755  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14001e759  call    cs:__imp_ObReleaseObjectSecurity
0x14001e760  nop     dword ptr [rax+rax+00h]
0x14001e765  mov     rcx, [rbp+57h+ObjectsSecurityDescriptor]
0x14001e769  cmp     rcx, rdi
0x14001e76c  jz      short loc_14001E783
0x14001e76e  xor     edx, edx; Tag
0x14001e770  mov     rcx, rdi; P
0x14001e773  call    cs:__imp_ExFreePoolWithTag
0x14001e77a  nop     dword ptr [rax+rax+00h]
0x14001e77f  mov     rcx, [rbp+57h+ObjectsSecurityDescriptor]; P
0x14001e783  test    rcx, rcx
0x14001e786  jz      short loc_14001E796
0x14001e788  xor     edx, edx; Tag
0x14001e78a  call    cs:__imp_ExFreePoolWithTag
0x14001e791  nop     dword ptr [rax+rax+00h]
0x14001e796  cmp     [rbp+57h+Dacl], 0
0x14001e79b  jz      short loc_14001E7AF
0x14001e79d  mov     rcx, [rbp+57h+Dacl]; P
0x14001e7a1  xor     edx, edx; Tag
0x14001e7a3  call    cs:__imp_ExFreePoolWithTag
0x14001e7aa  nop     dword ptr [rax+rax+00h]
0x14001e7af  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e7b6  cmp     rcx, r13
0x14001e7b9  jz      short loc_14001E7E0
0x14001e7bb  cmp     byte ptr [rcx+29h], 6
0x14001e7bf  jb      short loc_14001E7E0
0x14001e7c1  bt      dword ptr [rcx+2Ch], 0Bh
0x14001e7c6  jnb     short loc_14001E7E0
0x14001e7c8  mov     edx, 12h
0x14001e7cd  mov     rcx, [rcx+18h]
0x14001e7d1  lea     r8, WPP_0a0383b750aa364b280d5887b3b80ddf_Traceguids
0x14001e7d8  mov     r9d, ebx
0x14001e7db  call    WPP_SF_D
0x14001e7e0  mov     eax, ebx
0x14001e7e2  mov     rcx, [rbp+57h+var_38]
0x14001e7e6  xor     rcx, rsp; StackCookie
0x14001e7e9  call    __security_check_cookie
0x14001e7ee  add     rsp, 88h
0x14001e7f5  pop     r14
0x14001e7f7  pop     r13
0x14001e7f9  pop     r12
0x14001e7fb  pop     rdi
0x14001e7fc  pop     rbx
0x14001e7fd  pop     rbp
0x14001e7fe  retn
```
