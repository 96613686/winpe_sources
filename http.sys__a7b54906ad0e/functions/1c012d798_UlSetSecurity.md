# UlSetSecurity

- ea: `0x1c012d798`
- end: `0x1c012d862`
- name: `UlSetSecurity`
- size: `202`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR *ObjectsSecurityDescriptor, PSECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR ModificationDescriptor)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c0101c44`

## callees

- `0x1c012d798`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c012d7e6`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c012d7e6`
- `ntoskrnl!SeLockSubjectContext` at `0x1c012d7da`
- `ntoskrnl!SeLockSubjectContext` at `0x1c012d7da`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1c012d81d`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1c012d81d`
- `ntoskrnl!SeDeassignSecurity` at `0x1c012d843`
- `ntoskrnl!SeDeassignSecurity` at `0x1c012d843`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1c012d7c9`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1c012d7c9`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x1c012d80a`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x1c012d80a`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1c012d82e`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1c012d82e`

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
0x1c012d798  mov     rax, rsp
0x1c012d79b  mov     [rax+10h], rbx
0x1c012d79f  mov     [rax+18h], rsi
0x1c012d7a3  push    rdi
0x1c012d7a4  sub     rsp, 50h
0x1c012d7a8  xorps   xmm0, xmm0
0x1c012d7ab  mov     rbx, rcx
0x1c012d7ae  movups  xmmword ptr [rax-28h], xmm0
0x1c012d7b2  mov     rdi, r8
0x1c012d7b5  mov     rsi, rdx
0x1c012d7b8  movups  xmmword ptr [rax-18h], xmm0
0x1c012d7bc  mov     rax, [rcx]
0x1c012d7bf  lea     rcx, [rsp+58h+SubjectContext]; SubjectContext
0x1c012d7c4  mov     [rsp+58h+SecurityDescriptor], rax
0x1c012d7c9  call    cs:__imp_SeCaptureSubjectContext
0x1c012d7d0  nop     dword ptr [rax+rax+00h]
0x1c012d7d5  lea     rcx, [rsp+58h+SubjectContext]; SubjectContext
0x1c012d7da  call    cs:__imp_SeLockSubjectContext
0x1c012d7e1  nop     dword ptr [rax+rax+00h]
0x1c012d7e6  call    cs:__imp_IoGetFileObjectGenericMapping
0x1c012d7ed  nop     dword ptr [rax+rax+00h]
0x1c012d7f2  mov     [rsp+58h+GenericMapping], rax; GenericMapping
0x1c012d7f7  mov     r9, rbx; ObjectsSecurityDescriptor
0x1c012d7fa  mov     r8, rdi; ModificationDescriptor
0x1c012d7fd  mov     [rsp+58h+PoolType], 1; PoolType
0x1c012d805  mov     rdx, rsi; SecurityInformation
0x1c012d808  xor     ecx, ecx; Object
0x1c012d80a  call    cs:__imp_SeSetSecurityDescriptorInfo
0x1c012d811  nop     dword ptr [rax+rax+00h]
0x1c012d816  lea     rcx, [rsp+58h+SubjectContext]; SubjectContext
0x1c012d81b  mov     ebx, eax
0x1c012d81d  call    cs:__imp_SeUnlockSubjectContext
0x1c012d824  nop     dword ptr [rax+rax+00h]
0x1c012d829  lea     rcx, [rsp+58h+SubjectContext]; SubjectContext
0x1c012d82e  call    cs:__imp_SeReleaseSubjectContext
0x1c012d835  nop     dword ptr [rax+rax+00h]
0x1c012d83a  test    ebx, ebx
0x1c012d83c  js      short loc_1C012D84F
0x1c012d83e  lea     rcx, [rsp+58h+SecurityDescriptor]; SecurityDescriptor
0x1c012d843  call    cs:__imp_SeDeassignSecurity
0x1c012d84a  nop     dword ptr [rax+rax+00h]
0x1c012d84f  mov     rsi, [rsp+58h+arg_10]
0x1c012d854  mov     eax, ebx
0x1c012d856  mov     rbx, [rsp+58h+arg_8]
0x1c012d85b  add     rsp, 50h
0x1c012d85f  pop     rdi
0x1c012d860  retn
```
