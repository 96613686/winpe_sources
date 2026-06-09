# KsCreateDefaultSecurity

- ea: `0x1800345f0`
- end: `0x180034678`
- name: `KsCreateDefaultSecurity`
- size: `136`
- prototype: `NTSTATUS __stdcall(PSECURITY_DESCRIPTOR ParentSecurity, PSECURITY_DESCRIPTOR *DefaultSecurity)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x18003461d`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x18003461d`
- `ntoskrnl!SeAssignSecurity` at `0x18003464b`
- `ntoskrnl!SeAssignSecurity` at `0x18003464b`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18003465e`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18003465e`
- `ntoskrnl!SeCaptureSubjectContext` at `0x180034611`
- `ntoskrnl!SeCaptureSubjectContext` at `0x180034611`

## pseudocode

```c
NTSTATUS __stdcall KsCreateDefaultSecurity(PSECURITY_DESCRIPTOR ParentSecurity, PSECURITY_DESCRIPTOR *DefaultSecurity)
{
  struct _GENERIC_MAPPING *GenericMapping; // rax
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+40h] [rbp-28h] BYREF

  memset(&SubjectContext, 0, sizeof(SubjectContext));
  SeCaptureSubjectContext(&SubjectContext);
  GenericMapping = IoGetFileObjectGenericMapping();
  LODWORD(DefaultSecurity) = SeAssignSecurity(
                               ParentSecurity,
                               0,
                               DefaultSecurity,
                               0,
                               &SubjectContext,
                               GenericMapping,
                               NonPagedPoolNx);
  SeReleaseSubjectContext(&SubjectContext);
  return (int)DefaultSecurity;
}

```

## disassembly

```asm
0x1800345f0  mov     rax, rsp
0x1800345f3  mov     [rax+8], rbx
0x1800345f7  push    rdi
0x1800345f8  sub     rsp, 60h
0x1800345fc  xorps   xmm0, xmm0
0x1800345ff  mov     rdi, rcx
0x180034602  lea     rcx, [rax-28h]; SubjectContext
0x180034606  mov     rbx, rdx
0x180034609  movups  xmmword ptr [rax-28h], xmm0
0x18003460d  movups  xmmword ptr [rax-18h], xmm0
0x180034611  call    cs:__imp_SeCaptureSubjectContext
0x180034618  nop     dword ptr [rax+rax+00h]
0x18003461d  call    cs:__imp_IoGetFileObjectGenericMapping
0x180034624  nop     dword ptr [rax+rax+00h]
0x180034629  mov     [rsp+68h+PoolType], 200h; PoolType
0x180034631  xor     r9d, r9d; IsDirectoryObject
0x180034634  mov     [rsp+68h+GenericMapping], rax; GenericMapping
0x180034639  mov     r8, rbx; NewDescriptor
0x18003463c  lea     rax, [rsp+68h+var_28]
0x180034641  xor     edx, edx; ExplicitDescriptor
0x180034643  mov     rcx, rdi; ParentDescriptor
0x180034646  mov     [rsp+68h+SubjectContext], rax; SubjectContext
0x18003464b  call    cs:__imp_SeAssignSecurity
0x180034652  nop     dword ptr [rax+rax+00h]
0x180034657  lea     rcx, [rsp+68h+var_28]; SubjectContext
0x18003465c  mov     ebx, eax
0x18003465e  call    cs:__imp_SeReleaseSubjectContext
0x180034665  nop     dword ptr [rax+rax+00h]
0x18003466a  mov     eax, ebx
0x18003466c  mov     rbx, [rsp+68h+arg_0]
0x180034671  add     rsp, 60h
0x180034675  pop     rdi
0x180034676  retn
```
