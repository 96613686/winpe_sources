# UlSetSecurity

- ea: `0x1401309b8`
- end: `0x140130a82`
- name: `UlSetSecurity`
- size: `202`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR *ObjectsSecurityDescriptor, PSECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR ModificationDescriptor)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400cd768`

## callees

- `0x1401309b8`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140130a06`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140130a06`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140130a4e`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140130a4e`
- `ntoskrnl!SeDeassignSecurity` at `0x140130a63`
- `ntoskrnl!SeDeassignSecurity` at `0x140130a63`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140130a3d`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140130a3d`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x140130a2a`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x140130a2a`
- `ntoskrnl!SeLockSubjectContext` at `0x1401309fa`
- `ntoskrnl!SeLockSubjectContext` at `0x1401309fa`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1401309e9`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1401309e9`

## pseudocode

```c
__int64 __fastcall UlSetSecurity(
        PSECURITY_DESCRIPTOR *ObjectsSecurityDescriptor,
        PSECURITY_INFORMATION SecurityInformation,
        PSECURITY_DESCRIPTOR ModificationDescriptor)
{
  struct _GENERIC_MAPPING *GenericMapping; // rax
  NTSTATUS v7; // ebx
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+30h] [rbp-28h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp+8h] BYREF

  memset(&SubjectContext, 0, sizeof(SubjectContext));
  SecurityDescriptor = *ObjectsSecurityDescriptor;
  SeCaptureSubjectContext(&SubjectContext);
  SeLockSubjectContext(&SubjectContext);
  GenericMapping = IoGetFileObjectGenericMapping();
  v7 = SeSetSecurityDescriptorInfo(
         0,
         SecurityInformation,
         ModificationDescriptor,
         ObjectsSecurityDescriptor,
         PagedPool,
         GenericMapping);
  SeUnlockSubjectContext(&SubjectContext);
  SeReleaseSubjectContext(&SubjectContext);
  if ( v7 >= 0 )
    SeDeassignSecurity(&SecurityDescriptor);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1401309b8  mov     rax, rsp
0x1401309bb  mov     [rax+10h], rbx
0x1401309bf  mov     [rax+18h], rsi
0x1401309c3  push    rdi
0x1401309c4  sub     rsp, 50h
0x1401309c8  xorps   xmm0, xmm0
0x1401309cb  mov     rbx, rcx
0x1401309ce  movups  xmmword ptr [rax-28h], xmm0
0x1401309d2  mov     rdi, r8
0x1401309d5  mov     rsi, rdx
0x1401309d8  movups  xmmword ptr [rax-18h], xmm0
0x1401309dc  mov     rax, [rcx]
0x1401309df  lea     rcx, [rsp+58h+SubjectContext]; SubjectContext
0x1401309e4  mov     [rsp+58h+SecurityDescriptor], rax
0x1401309e9  call    cs:__imp_SeCaptureSubjectContext
0x1401309f0  nop     dword ptr [rax+rax+00h]
0x1401309f5  lea     rcx, [rsp+58h+SubjectContext]; SubjectContext
0x1401309fa  call    cs:__imp_SeLockSubjectContext
0x140130a01  nop     dword ptr [rax+rax+00h]
0x140130a06  call    cs:__imp_IoGetFileObjectGenericMapping
0x140130a0d  nop     dword ptr [rax+rax+00h]
0x140130a12  mov     [rsp+58h+GenericMapping], rax; GenericMapping
0x140130a17  mov     r9, rbx; ObjectsSecurityDescriptor
0x140130a1a  mov     r8, rdi; ModificationDescriptor
0x140130a1d  mov     [rsp+58h+PoolType], 1; PoolType
0x140130a25  mov     rdx, rsi; SecurityInformation
0x140130a28  xor     ecx, ecx; Object
0x140130a2a  call    cs:__imp_SeSetSecurityDescriptorInfo
0x140130a31  nop     dword ptr [rax+rax+00h]
0x140130a36  lea     rcx, [rsp+58h+SubjectContext]; SubjectContext
0x140130a3b  mov     ebx, eax
0x140130a3d  call    cs:__imp_SeUnlockSubjectContext
0x140130a44  nop     dword ptr [rax+rax+00h]
0x140130a49  lea     rcx, [rsp+58h+SubjectContext]; SubjectContext
0x140130a4e  call    cs:__imp_SeReleaseSubjectContext
0x140130a55  nop     dword ptr [rax+rax+00h]
0x140130a5a  test    ebx, ebx
0x140130a5c  js      short loc_140130A6F
0x140130a5e  lea     rcx, [rsp+58h+SecurityDescriptor]; SecurityDescriptor
0x140130a63  call    cs:__imp_SeDeassignSecurity
0x140130a6a  nop     dword ptr [rax+rax+00h]
0x140130a6f  mov     rsi, [rsp+58h+arg_10]
0x140130a74  mov     eax, ebx
0x140130a76  mov     rbx, [rsp+58h+arg_8]
0x140130a7b  add     rsp, 50h
0x140130a7f  pop     rdi
0x140130a80  retn
```
