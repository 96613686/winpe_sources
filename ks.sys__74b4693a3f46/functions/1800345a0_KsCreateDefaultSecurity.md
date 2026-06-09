# KsCreateDefaultSecurity

- ea: `0x1800345a0`
- end: `0x180034628`
- name: `KsCreateDefaultSecurity`
- size: `136`
- prototype: `NTSTATUS __stdcall(PSECURITY_DESCRIPTOR ParentSecurity, PSECURITY_DESCRIPTOR *DefaultSecurity)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!SeAssignSecurity` at `0x1800345fb`
- `ntoskrnl!SeAssignSecurity` at `0x1800345fb`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18003460e`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18003460e`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1800345c1`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1800345c1`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1800345cd`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1800345cd`

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
0x1800345a0  mov     rax, rsp
0x1800345a3  mov     [rax+8], rbx
0x1800345a7  push    rdi
0x1800345a8  sub     rsp, 60h
0x1800345ac  xorps   xmm0, xmm0
0x1800345af  mov     rdi, rcx
0x1800345b2  lea     rcx, [rax-28h]; SubjectContext
0x1800345b6  mov     rbx, rdx
0x1800345b9  movups  xmmword ptr [rax-28h], xmm0
0x1800345bd  movups  xmmword ptr [rax-18h], xmm0
0x1800345c1  call    cs:__imp_SeCaptureSubjectContext
0x1800345c8  nop     dword ptr [rax+rax+00h]
0x1800345cd  call    cs:__imp_IoGetFileObjectGenericMapping
0x1800345d4  nop     dword ptr [rax+rax+00h]
0x1800345d9  mov     [rsp+68h+PoolType], 200h; PoolType
0x1800345e1  xor     r9d, r9d; IsDirectoryObject
0x1800345e4  mov     [rsp+68h+GenericMapping], rax; GenericMapping
0x1800345e9  mov     r8, rbx; NewDescriptor
0x1800345ec  lea     rax, [rsp+68h+var_28]
0x1800345f1  xor     edx, edx; ExplicitDescriptor
0x1800345f3  mov     rcx, rdi; ParentDescriptor
0x1800345f6  mov     [rsp+68h+SubjectContext], rax; SubjectContext
0x1800345fb  call    cs:__imp_SeAssignSecurity
0x180034602  nop     dword ptr [rax+rax+00h]
0x180034607  lea     rcx, [rsp+68h+var_28]; SubjectContext
0x18003460c  mov     ebx, eax
0x18003460e  call    cs:__imp_SeReleaseSubjectContext
0x180034615  nop     dword ptr [rax+rax+00h]
0x18003461a  mov     eax, ebx
0x18003461c  mov     rbx, [rsp+68h+arg_0]
0x180034621  add     rsp, 60h
0x180034625  pop     rdi
0x180034626  retn
```
