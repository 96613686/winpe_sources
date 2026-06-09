# AddSidToDevice(_DEVICE_OBJECT *,void *)

- ea: `0x18000d5a8`
- end: `0x18000da48`
- name: `?AddSidToDevice@@YAJPEAU_DEVICE_OBJECT@@PEAX@Z`
- size: `1184`
- prototype: `__int64 __fastcall(PVOID Object, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004dccc`

## callees

- `0x18000d5a8`
- `0x18000e740`
- `0x18001a000`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18000da1e`
- `ntoskrnl!ZwClose` at `0x18000da1e`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x18000d966`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x18000d966`
- `ntoskrnl!ObOpenObjectByPointer` at `0x18000d638`
- `ntoskrnl!ObOpenObjectByPointer` at `0x18000d638`
- `ntoskrnl!RtlLengthSid` at `0x18000d601`
- `ntoskrnl!RtlLengthSid` at `0x18000d601`
- `ntoskrnl!ZwQuerySecurityObject` at `0x18000d665`
- `ntoskrnl!ZwQuerySecurityObject` at `0x18000d6ea`
- `ntoskrnl!ZwQuerySecurityObject` at `0x18000d665`
- `ntoskrnl!ZwQuerySecurityObject` at `0x18000d6ea`
- `ntoskrnl!ZwSetSecurityObject` at `0x18000d984`
- `ntoskrnl!ZwSetSecurityObject` at `0x18000d984`
- `ntoskrnl!RtlSelfRelativeToAbsoluteSD` at `0x18000d73f`
- `ntoskrnl!RtlSelfRelativeToAbsoluteSD` at `0x18000d920`
- `ntoskrnl!RtlSelfRelativeToAbsoluteSD` at `0x18000d73f`
- `ntoskrnl!RtlSelfRelativeToAbsoluteSD` at `0x18000d920`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000d997`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000d9b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000d9c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000d9dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000d9f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000da09`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000d997`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000d9b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000d9c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000d9dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000d9f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000da09`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18000d691`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18000d769`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18000d7d5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18000d80c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18000d846`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18000d880`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18000d8ba`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18000d691`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18000d769`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18000d7d5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18000d80c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18000d846`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18000d880`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18000d8ba`

## pseudocode

```c
__int64 __fastcall AddSidToDevice(PVOID Object, PSID Sid)
{
  NTSTATUS v3; // ebx
  ULONG v4; // ebx
  PVOID PoolWithTag; // rax
  void *v6; // r13
  struct _ACL *v7; // rdi
  struct _ACL *v8; // r15
  void *Owner; // r14
  void *PrimaryGroup; // rsi
  PVOID v11; // rax
  void *v12; // r12
  struct _ACL *v13; // rax
  struct _ACL *v14; // rcx
  size_t v15; // r8
  struct _ACL *v16; // rax
  struct _ACL *v17; // rax
  PVOID v18; // rax
  PVOID v19; // rax
  unsigned int *v20; // r8
  ULONG PrimaryGroupSize; // [rsp+60h] [rbp-9h] BYREF
  ULONG OwnerSize; // [rsp+64h] [rbp-5h] BYREF
  ULONG SaclSize; // [rsp+68h] [rbp-1h] BYREF
  ULONG AbsoluteSecurityDescriptorSize; // [rsp+6Ch] [rbp+3h] BYREF
  ULONG v26; // [rsp+70h] [rbp+7h]
  HANDLE Handle; // [rsp+78h] [rbp+Fh] BYREF
  size_t Size; // [rsp+80h] [rbp+17h]
  ULONG DaclSize; // [rsp+E0h] [rbp+77h] BYREF
  ULONG LengthNeeded; // [rsp+E8h] [rbp+7Fh] BYREF

  Handle = 0;
  LengthNeeded = 0;
  AbsoluteSecurityDescriptorSize = 0;
  DaclSize = 0;
  SaclSize = 0;
  OwnerSize = 0;
  PrimaryGroupSize = 0;
  v26 = RtlLengthSid(Sid);
  v3 = ObOpenObjectByPointer(Object, 0x200u, 0, 0x40000u, 0, 0, &Handle);
  if ( v3 < 0 )
    goto LABEL_42;
  v3 = ZwQuerySecurityObject(Handle, 4u, 0, 0, &LengthNeeded);
  if ( v3 != -1073741789 )
    goto LABEL_42;
  v4 = LengthNeeded;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, LengthNeeded, 0x6573534Bu);
  v6 = PoolWithTag;
  if ( ExPoolZeroingNativelySupported )
  {
    if ( PoolWithTag )
      goto LABEL_6;
LABEL_12:
    v3 = -1073741670;
    goto LABEL_42;
  }
  if ( !PoolWithTag )
    goto LABEL_12;
  memset(PoolWithTag, 0, v4);
LABEL_6:
  v7 = 0;
  Size = 0;
  v8 = 0;
  Owner = 0;
  PrimaryGroup = 0;
  v3 = ZwQuerySecurityObject(Handle, 4u, v6, LengthNeeded, &LengthNeeded);
  if ( v3 < 0 )
    goto LABEL_32;
  v3 = RtlSelfRelativeToAbsoluteSD(
         v6,
         0,
         &AbsoluteSecurityDescriptorSize,
         0,
         &DaclSize,
         0,
         &SaclSize,
         0,
         &OwnerSize,
         0,
         &PrimaryGroupSize);
  if ( v3 != -1073741789 )
    goto LABEL_32;
  Size = AbsoluteSecurityDescriptorSize;
  v11 = ExAllocatePoolWithTag((POOL_TYPE)1025, AbsoluteSecurityDescriptorSize, 0x6573534Bu);
  v12 = v11;
  if ( ExPoolZeroingNativelySupported || !v11 )
  {
    Size = (size_t)v11;
    if ( !v11 )
      goto LABEL_32;
  }
  else
  {
    memset(v11, 0, Size);
    Size = (size_t)v12;
  }
  if ( DaclSize )
  {
    v13 = (struct _ACL *)ExAllocatePoolWithTag(PagedPool, v26 + 12 + DaclSize, 0x6573534Bu);
    v7 = v13;
    if ( !v13 )
      goto LABEL_32;
    v14 = v13;
    v15 = DaclSize + 12 + v26;
  }
  else
  {
    DaclSize = v26 + 20;
    v16 = (struct _ACL *)ExAllocatePoolWithTag(PagedPool, v26 + 20, 0x6573534Bu);
    v7 = v16;
    if ( !v16 )
      goto LABEL_32;
    v15 = DaclSize;
    v14 = v16;
  }
  memset(v14, 0, v15);
  if ( SaclSize )
  {
    v17 = (struct _ACL *)ExAllocatePoolWithTag(PagedPool, SaclSize, 0x6573534Bu);
    v8 = v17;
    if ( !v17 )
      goto LABEL_32;
    memset(v17, 0, SaclSize);
  }
  if ( OwnerSize )
  {
    v18 = ExAllocatePoolWithTag(PagedPool, OwnerSize, 0x6573534Bu);
    Owner = v18;
    if ( !v18 )
      goto LABEL_32;
    memset(v18, 0, OwnerSize);
  }
  if ( !PrimaryGroupSize )
  {
LABEL_28:
    v3 = RtlSelfRelativeToAbsoluteSD(
           v6,
           v12,
           &AbsoluteSecurityDescriptorSize,
           v7,
           &DaclSize,
           v8,
           &SaclSize,
           Owner,
           &OwnerSize,
           PrimaryGroup,
           &PrimaryGroupSize);
    if ( v3 >= 0 && !IsAcePresent(v7, Sid, v20) )
    {
      v7->AclSize += v26 + 12;
      v3 = RtlAddAccessAllowedAceEx(v7, 2u, 0, 0x10000000u, Sid);
      if ( v3 >= 0 )
        v3 = ZwSetSecurityObject(Handle, 4u, v12);
    }
    goto LABEL_32;
  }
  v19 = ExAllocatePoolWithTag(PagedPool, PrimaryGroupSize, 0x6573534Bu);
  PrimaryGroup = v19;
  if ( v19 )
  {
    memset(v19, 0, PrimaryGroupSize);
    goto LABEL_28;
  }
LABEL_32:
  ExFreePoolWithTag(v6, 0);
  if ( Size )
    ExFreePoolWithTag((PVOID)Size, 0);
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  if ( v8 )
    ExFreePoolWithTag(v8, 0);
  if ( Owner )
    ExFreePoolWithTag(Owner, 0);
  if ( PrimaryGroup )
    ExFreePoolWithTag(PrimaryGroup, 0);
LABEL_42:
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000d5a8  mov     [rsp-8+arg_0], rbx
0x18000d5ad  mov     [rsp-8+Sid], rdx
0x18000d5b2  push    rbp
0x18000d5b3  push    rsi
0x18000d5b4  push    rdi
0x18000d5b5  push    r12
0x18000d5b7  push    r13
0x18000d5b9  push    r14
0x18000d5bb  push    r15
0x18000d5bd  lea     rbp, [rsp-27h]
0x18000d5c2  sub     rsp, 90h
0x18000d5c9  mov     rbx, rcx
0x18000d5cc  mov     [rbp+57h+var_48], 0
0x18000d5d4  mov     rcx, rdx; Sid
0x18000d5d7  mov     [rbp+57h+LengthNeeded], 0
0x18000d5de  mov     [rbp+57h+AbsoluteSecurityDescriptorSize], 0
0x18000d5e5  mov     [rbp+57h+DaclSize], 0
0x18000d5ec  mov     [rbp+57h+SaclSize], 0
0x18000d5f3  mov     [rbp+57h+var_5C], 0
0x18000d5fa  mov     [rbp+57h+var_60], 0
0x18000d601  call    cs:__imp_RtlLengthSid
0x18000d608  nop     dword ptr [rax+rax+00h]
0x18000d60d  mov     [rbp+57h+var_50], eax
0x18000d610  mov     r9d, 40000h; DesiredAccess
0x18000d616  lea     rax, [rbp+57h+var_48]
0x18000d61a  xor     r8d, r8d; PassedAccessState
0x18000d61d  mov     [rsp+0C0h+Handle], rax; Handle
0x18000d622  mov     edx, 200h; HandleAttributes
0x18000d627  mov     [rsp+0C0h+AccessMode], 0; AccessMode
0x18000d62c  mov     rcx, rbx; Object
0x18000d62f  mov     [rsp+0C0h+ObjectType], 0; ObjectType
0x18000d638  call    cs:__imp_ObOpenObjectByPointer
0x18000d63f  nop     dword ptr [rax+rax+00h]
0x18000d644  mov     ebx, eax
0x18000d646  test    eax, eax
0x18000d648  js      loc_18000DA15
0x18000d64e  mov     rcx, [rbp+57h+var_48]; Handle
0x18000d652  lea     rax, [rbp+57h+LengthNeeded]
0x18000d656  xor     r9d, r9d; Length
0x18000d659  mov     [rsp+0C0h+ObjectType], rax; LengthNeeded
0x18000d65e  xor     r8d, r8d; SecurityDescriptor
0x18000d661  lea     edx, [r9+4]; SecurityInformation
0x18000d665  call    cs:__imp_ZwQuerySecurityObject
0x18000d66c  nop     dword ptr [rax+rax+00h]
0x18000d671  mov     ebx, eax
0x18000d673  cmp     eax, 0C0000023h
0x18000d678  jnz     loc_18000DA15
0x18000d67e  mov     ebx, [rbp+57h+LengthNeeded]
0x18000d681  mov     r12d, 6573534Bh
0x18000d687  mov     r8d, r12d; Tag
0x18000d68a  mov     edx, ebx; NumberOfBytes
0x18000d68c  mov     ecx, 401h; PoolType
0x18000d691  call    cs:__imp_ExAllocatePoolWithTag
0x18000d698  nop     dword ptr [rax+rax+00h]
0x18000d69d  cmp     cs:ExPoolZeroingNativelySupported, 0
0x18000d6a4  mov     r13, rax
0x18000d6a7  jnz     loc_18000D79A
0x18000d6ad  test    rax, rax
0x18000d6b0  jz      loc_18000D7A3
0x18000d6b6  mov     r8d, ebx; Size
0x18000d6b9  xor     edx, edx; Val
0x18000d6bb  mov     rcx, rax; void *
0x18000d6be  call    memset
0x18000d6c3  mov     r9d, [rbp+57h+LengthNeeded]; Length
0x18000d6c7  xor     eax, eax
0x18000d6c9  mov     rcx, [rbp+57h+var_48]; Handle
0x18000d6cd  xor     edi, edi
0x18000d6cf  mov     [rbp+57h+Size], rax
0x18000d6d3  mov     r8, r13; SecurityDescriptor
0x18000d6d6  lea     rax, [rbp+57h+LengthNeeded]
0x18000d6da  xor     r15d, r15d
0x18000d6dd  xor     r14d, r14d
0x18000d6e0  mov     [rsp+0C0h+ObjectType], rax; LengthNeeded
0x18000d6e5  lea     edx, [rdi+4]; SecurityInformation
0x18000d6e8  xor     esi, esi
0x18000d6ea  call    cs:__imp_ZwQuerySecurityObject
0x18000d6f1  nop     dword ptr [rax+rax+00h]
0x18000d6f6  mov     ebx, eax
0x18000d6f8  test    eax, eax
0x18000d6fa  js      loc_18000D992
0x18000d700  lea     rax, [rbp+57h+var_60]
0x18000d704  xor     r9d, r9d; Dacl
0x18000d707  mov     [rsp+0C0h+PrimaryGroupSize], rax; PrimaryGroupSize
0x18000d70c  lea     r8, [rbp+57h+AbsoluteSecurityDescriptorSize]; AbsoluteSecurityDescriptorSize
0x18000d710  mov     [rsp+0C0h+PrimaryGroup], rsi; PrimaryGroup
0x18000d715  lea     rax, [rbp+57h+var_5C]
0x18000d719  mov     [rsp+0C0h+OwnerSize], rax; OwnerSize
0x18000d71e  xor     edx, edx; AbsoluteSecurityDescriptor
0x18000d720  mov     [rsp+0C0h+Owner], rsi; Owner
0x18000d725  lea     rax, [rbp+57h+SaclSize]
0x18000d729  mov     [rsp+0C0h+Handle], rax; SaclSize
0x18000d72e  mov     rcx, r13; SelfRelativeSecurityDescriptor
0x18000d731  lea     rax, [rbp+57h+DaclSize]
0x18000d735  mov     qword ptr [rsp+0C0h+AccessMode], rsi; Sacl
0x18000d73a  mov     [rsp+0C0h+ObjectType], rax; DaclSize
0x18000d73f  call    cs:__imp_RtlSelfRelativeToAbsoluteSD
0x18000d746  nop     dword ptr [rax+rax+00h]
0x18000d74b  mov     ebx, eax
0x18000d74d  cmp     eax, 0C0000023h
0x18000d752  jnz     loc_18000D992
0x18000d758  mov     eax, [rbp+57h+AbsoluteSecurityDescriptorSize]
0x18000d75b  mov     r8d, r12d; Tag
0x18000d75e  mov     edx, eax; NumberOfBytes
0x18000d760  mov     [rbp+57h+Size], rax
0x18000d764  mov     ecx, 401h; PoolType
0x18000d769  call    cs:__imp_ExAllocatePoolWithTag
0x18000d770  nop     dword ptr [rax+rax+00h]
0x18000d775  cmp     cs:ExPoolZeroingNativelySupported, sil
0x18000d77c  mov     r12, rax
0x18000d77f  jnz     short loc_18000D7AD
0x18000d781  test    rax, rax
0x18000d784  jz      short loc_18000D7AD
0x18000d786  mov     r8, [rbp+57h+Size]; Size
0x18000d78a  xor     edx, edx; Val
0x18000d78c  mov     rcx, rax; void *
0x18000d78f  call    memset
0x18000d794  mov     [rbp+57h+Size], r12
0x18000d798  jmp     short loc_18000D7BA
0x18000d79a  test    r13, r13
0x18000d79d  jnz     loc_18000D6C3
0x18000d7a3  mov     ebx, 0C000009Ah
0x18000d7a8  jmp     loc_18000DA15
0x18000d7ad  mov     [rbp+57h+Size], r12
0x18000d7b1  test    r12, r12
0x18000d7b4  jz      loc_18000D992
0x18000d7ba  mov     ecx, [rbp+57h+var_50]
0x18000d7bd  mov     r8d, 6573534Bh; Tag
0x18000d7c3  mov     eax, [rbp+57h+DaclSize]
0x18000d7c6  add     ecx, 0Ch
0x18000d7c9  test    eax, eax
0x18000d7cb  jz      short loc_18000D7FF
0x18000d7cd  lea     edx, [rcx+rax]; NumberOfBytes
0x18000d7d0  mov     ecx, 1; PoolType
0x18000d7d5  call    cs:__imp_ExAllocatePoolWithTag
0x18000d7dc  nop     dword ptr [rax+rax+00h]
0x18000d7e1  mov     rdi, rax
0x18000d7e4  test    rax, rax
0x18000d7e7  jz      loc_18000D992
0x18000d7ed  mov     eax, [rbp+57h+DaclSize]
0x18000d7f0  mov     rcx, rdi
0x18000d7f3  mov     r8d, [rbp+57h+var_50]
0x18000d7f7  add     eax, 0Ch
0x18000d7fa  add     r8d, eax
0x18000d7fd  jmp     short loc_18000D82B
0x18000d7ff  lea     eax, [rcx+8]
0x18000d802  mov     ecx, 1; PoolType
0x18000d807  mov     edx, eax; NumberOfBytes
0x18000d809  mov     [rbp+57h+DaclSize], eax
0x18000d80c  call    cs:__imp_ExAllocatePoolWithTag
0x18000d813  nop     dword ptr [rax+rax+00h]
0x18000d818  mov     rdi, rax
0x18000d81b  test    rax, rax
0x18000d81e  jz      loc_18000D992
0x18000d824  mov     r8d, [rbp+57h+DaclSize]; Size
0x18000d828  mov     rcx, rax; void *
0x18000d82b  xor     edx, edx; Val
0x18000d82d  call    memset
0x18000d832  mov     eax, [rbp+57h+SaclSize]
0x18000d835  test    eax, eax
0x18000d837  jz      short loc_18000D86C
0x18000d839  mov     edx, eax; NumberOfBytes
0x18000d83b  mov     ecx, 1; PoolType
0x18000d840  mov     r8d, 6573534Bh; Tag
0x18000d846  call    cs:__imp_ExAllocatePoolWithTag
0x18000d84d  nop     dword ptr [rax+rax+00h]
0x18000d852  mov     r15, rax
0x18000d855  test    rax, rax
0x18000d858  jz      loc_18000D992
0x18000d85e  mov     r8d, [rbp+57h+SaclSize]; Size
0x18000d862  xor     edx, edx; Val
0x18000d864  mov     rcx, rax; void *
0x18000d867  call    memset
0x18000d86c  mov     eax, [rbp+57h+var_5C]
0x18000d86f  test    eax, eax
0x18000d871  jz      short loc_18000D8A6
0x18000d873  mov     edx, eax; NumberOfBytes
0x18000d875  mov     ecx, 1; PoolType
0x18000d87a  mov     r8d, 6573534Bh; Tag
0x18000d880  call    cs:__imp_ExAllocatePoolWithTag
0x18000d887  nop     dword ptr [rax+rax+00h]
0x18000d88c  mov     r14, rax
0x18000d88f  test    rax, rax
0x18000d892  jz      loc_18000D992
0x18000d898  mov     r8d, [rbp+57h+var_5C]; Size
0x18000d89c  xor     edx, edx; Val
0x18000d89e  mov     rcx, rax; void *
0x18000d8a1  call    memset
0x18000d8a6  mov     eax, [rbp+57h+var_60]
0x18000d8a9  test    eax, eax
0x18000d8ab  jz      short loc_18000D8E0
0x18000d8ad  mov     edx, eax; NumberOfBytes
0x18000d8af  mov     ecx, 1; PoolType
0x18000d8b4  mov     r8d, 6573534Bh; Tag
0x18000d8ba  call    cs:__imp_ExAllocatePoolWithTag
0x18000d8c1  nop     dword ptr [rax+rax+00h]
0x18000d8c6  mov     rsi, rax
0x18000d8c9  test    rax, rax
0x18000d8cc  jz      loc_18000D992
0x18000d8d2  mov     r8d, [rbp+57h+var_60]; Size
0x18000d8d6  xor     edx, edx; Val
0x18000d8d8  mov     rcx, rax; void *
0x18000d8db  call    memset
0x18000d8e0  lea     rax, [rbp+57h+var_60]
0x18000d8e4  mov     r9, rdi; Dacl
0x18000d8e7  mov     [rsp+0C0h+PrimaryGroupSize], rax; PrimaryGroupSize
0x18000d8ec  lea     r8, [rbp+57h+AbsoluteSecurityDescriptorSize]; AbsoluteSecurityDescriptorSize
0x18000d8f0  mov     [rsp+0C0h+PrimaryGroup], rsi; PrimaryGroup
0x18000d8f5  lea     rax, [rbp+57h+var_5C]
0x18000d8f9  mov     [rsp+0C0h+OwnerSize], rax; OwnerSize
0x18000d8fe  mov     rdx, r12; AbsoluteSecurityDescriptor
0x18000d901  mov     [rsp+0C0h+Owner], r14; Owner
0x18000d906  lea     rax, [rbp+57h+SaclSize]
0x18000d90a  mov     [rsp+0C0h+Handle], rax; SaclSize
0x18000d90f  mov     rcx, r13; SelfRelativeSecurityDescriptor
0x18000d912  lea     rax, [rbp+57h+DaclSize]
0x18000d916  mov     qword ptr [rsp+0C0h+AccessMode], r15; Sacl
0x18000d91b  mov     [rsp+0C0h+ObjectType], rax; DaclSize
0x18000d920  call    cs:__imp_RtlSelfRelativeToAbsoluteSD
0x18000d927  nop     dword ptr [rax+rax+00h]
0x18000d92c  mov     ebx, eax
0x18000d92e  test    eax, eax
0x18000d930  js      short loc_18000D992
0x18000d932  mov     rdx, [rbp+57h+Sid]; void *
0x18000d936  mov     rcx, rdi; struct _ACL *
0x18000d939  call    ?IsAcePresent@@YAPEAXPEAU_ACL@@PEAXPEAK@Z; IsAcePresent(_ACL *,void *,ulong *)
0x18000d93e  test    rax, rax
0x18000d941  jnz     short loc_18000D992
0x18000d943  mov     eax, [rbp+57h+var_50]
0x18000d946  xor     r8d, r8d; AceFlags
0x18000d949  add     eax, 0Ch
0x18000d94c  mov     r9d, 10000000h; AccessMask
0x18000d952  add     [rdi+2], ax
0x18000d956  mov     rcx, rdi; Acl
0x18000d959  mov     rax, [rbp+57h+Sid]
0x18000d95d  lea     edx, [r8+2]; AceRevision
0x18000d961  mov     [rsp+0C0h+ObjectType], rax; Sid
0x18000d966  call    cs:__imp_RtlAddAccessAllowedAceEx
0x18000d96d  nop     dword ptr [rax+rax+00h]
0x18000d972  mov     ebx, eax
0x18000d974  test    eax, eax
0x18000d976  js      short loc_18000D992
0x18000d978  mov     rcx, [rbp+57h+var_48]; Handle
0x18000d97c  mov     r8, r12; SecurityDescriptor
0x18000d97f  mov     edx, 4; SecurityInformation
0x18000d984  call    cs:__imp_ZwSetSecurityObject
0x18000d98b  nop     dword ptr [rax+rax+00h]
0x18000d990  mov     ebx, eax
0x18000d992  xor     edx, edx; Tag
0x18000d994  mov     rcx, r13; P
0x18000d997  call    cs:__imp_ExFreePoolWithTag
0x18000d99e  nop     dword ptr [rax+rax+00h]
0x18000d9a3  mov     rax, [rbp+57h+Size]
0x18000d9a7  test    rax, rax
0x18000d9aa  jz      short loc_18000D9BD
0x18000d9ac  xor     edx, edx; Tag
0x18000d9ae  mov     rcx, rax; P
0x18000d9b1  call    cs:__imp_ExFreePoolWithTag
0x18000d9b8  nop     dword ptr [rax+rax+00h]
0x18000d9bd  test    rdi, rdi
0x18000d9c0  jz      short loc_18000D9D3
0x18000d9c2  xor     edx, edx; Tag
0x18000d9c4  mov     rcx, rdi; P
0x18000d9c7  call    cs:__imp_ExFreePoolWithTag
0x18000d9ce  nop     dword ptr [rax+rax+00h]
0x18000d9d3  test    r15, r15
0x18000d9d6  jz      short loc_18000D9E9
0x18000d9d8  xor     edx, edx; Tag
0x18000d9da  mov     rcx, r15; P
0x18000d9dd  call    cs:__imp_ExFreePoolWithTag
0x18000d9e4  nop     dword ptr [rax+rax+00h]
0x18000d9e9  test    r14, r14
0x18000d9ec  jz      short loc_18000D9FF
0x18000d9ee  xor     edx, edx; Tag
0x18000d9f0  mov     rcx, r14; P
0x18000d9f3  call    cs:__imp_ExFreePoolWithTag
0x18000d9fa  nop     dword ptr [rax+rax+00h]
0x18000d9ff  test    rsi, rsi
0x18000da02  jz      short loc_18000DA15
0x18000da04  xor     edx, edx; Tag
0x18000da06  mov     rcx, rsi; P
0x18000da09  call    cs:__imp_ExFreePoolWithTag
0x18000da10  nop     dword ptr [rax+rax+00h]
0x18000da15  mov     rcx, [rbp+57h+var_48]; Handle
0x18000da19  test    rcx, rcx
0x18000da1c  jz      short loc_18000DA2A
0x18000da1e  call    cs:__imp_ZwClose
0x18000da25  nop     dword ptr [rax+rax+00h]
0x18000da2a  mov     eax, ebx
0x18000da2c  mov     rbx, [rsp+0C0h+arg_0]
0x18000da34  add     rsp, 90h
0x18000da3b  pop     r15
0x18000da3d  pop     r14
0x18000da3f  pop     r13
0x18000da41  pop     r12
0x18000da43  pop     rdi
0x18000da44  pop     rsi
0x18000da45  pop     rbp
0x18000da46  retn
```
