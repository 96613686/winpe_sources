# UlSetSecurity

- ea: `0x1401308c8`
- end: `0x140130992`
- name: `UlSetSecurity`
- size: `202`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR *ObjectsSecurityDescriptor, PSECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR ModificationDescriptor)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400cd848`

## callees

- `0x1401308c8`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140130916`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140130916`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14013095e`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14013095e`
- `ntoskrnl!SeDeassignSecurity` at `0x140130973`
- `ntoskrnl!SeDeassignSecurity` at `0x140130973`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14013094d`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14013094d`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x14013093a`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x14013093a`
- `ntoskrnl!SeLockSubjectContext` at `0x14013090a`
- `ntoskrnl!SeLockSubjectContext` at `0x14013090a`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1401308f9`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1401308f9`

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
0x1401308c8  mov     rax, rsp
0x1401308cb  mov     [rax+10h], rbx
0x1401308cf  mov     [rax+18h], rsi
0x1401308d3  push    rdi
0x1401308d4  sub     rsp, 50h
0x1401308d8  xorps   xmm0, xmm0
0x1401308db  mov     rbx, rcx
0x1401308de  movups  xmmword ptr [rax-28h], xmm0
0x1401308e2  mov     rdi, r8
0x1401308e5  mov     rsi, rdx
0x1401308e8  movups  xmmword ptr [rax-18h], xmm0
0x1401308ec  mov     rax, [rcx]
0x1401308ef  lea     rcx, [rsp+58h+SubjectContext]; SubjectContext
0x1401308f4  mov     [rsp+58h+SecurityDescriptor], rax
0x1401308f9  call    cs:__imp_SeCaptureSubjectContext
0x140130900  nop     dword ptr [rax+rax+00h]
0x140130905  lea     rcx, [rsp+58h+SubjectContext]; SubjectContext
0x14013090a  call    cs:__imp_SeLockSubjectContext
0x140130911  nop     dword ptr [rax+rax+00h]
0x140130916  call    cs:__imp_IoGetFileObjectGenericMapping
0x14013091d  nop     dword ptr [rax+rax+00h]
0x140130922  mov     [rsp+58h+GenericMapping], rax; GenericMapping
0x140130927  mov     r9, rbx; ObjectsSecurityDescriptor
0x14013092a  mov     r8, rdi; ModificationDescriptor
0x14013092d  mov     [rsp+58h+PoolType], 1; PoolType
0x140130935  mov     rdx, rsi; SecurityInformation
0x140130938  xor     ecx, ecx; Object
0x14013093a  call    cs:__imp_SeSetSecurityDescriptorInfo
0x140130941  nop     dword ptr [rax+rax+00h]
0x140130946  lea     rcx, [rsp+58h+SubjectContext]; SubjectContext
0x14013094b  mov     ebx, eax
0x14013094d  call    cs:__imp_SeUnlockSubjectContext
0x140130954  nop     dword ptr [rax+rax+00h]
0x140130959  lea     rcx, [rsp+58h+SubjectContext]; SubjectContext
0x14013095e  call    cs:__imp_SeReleaseSubjectContext
0x140130965  nop     dword ptr [rax+rax+00h]
0x14013096a  test    ebx, ebx
0x14013096c  js      short loc_14013097F
0x14013096e  lea     rcx, [rsp+58h+SecurityDescriptor]; SecurityDescriptor
0x140130973  call    cs:__imp_SeDeassignSecurity
0x14013097a  nop     dword ptr [rax+rax+00h]
0x14013097f  mov     rsi, [rsp+58h+arg_10]
0x140130984  mov     eax, ebx
0x140130986  mov     rbx, [rsp+58h+arg_8]
0x14013098b  add     rsp, 50h
0x14013098f  pop     rdi
0x140130990  retn
```
