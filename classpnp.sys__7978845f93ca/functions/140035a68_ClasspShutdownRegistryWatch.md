# ClasspShutdownRegistryWatch

- ea: `0x140035a68`
- end: `0x140035b0c`
- name: `ClasspShutdownRegistryWatch`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140026590`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140035a79`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140035a79`
- `ntoskrnl!KeWaitForSingleObject` at `0x140035ae5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140035ae5`
- `ntoskrnl!ZwClose` at `0x140035a9e`
- `ntoskrnl!ZwClose` at `0x140035a9e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140035ac1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140035ac1`
- `ntoskrnl!ExDeleteResourceLite` at `0x140035af4`
- `ntoskrnl!ExDeleteResourceLite` at `0x140035af4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140035a8e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140035a8e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140035ab5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140035ab5`

## pseudocode

```c
NTSTATUS ClasspShutdownRegistryWatch()
{
  char *v0; // rbx

  v0 = (char *)RegWatchContext;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)(v0 + 24), 1u);
  ZwClose(*((HANDLE *)v0 + 2));
  *((_QWORD *)v0 + 2) = 0;
  ExReleaseResourceLite((PERESOURCE)(v0 + 24));
  KeLeaveCriticalRegion();
  KeWaitForSingleObject(v0 + 160, Executive, 0, 0, 0);
  return ExDeleteResourceLite((PERESOURCE)(v0 + 24));
}

```

## disassembly

```asm
0x140035a68  mov     [rsp+arg_0], rbx
0x140035a6d  push    rdi
0x140035a6e  sub     rsp, 30h
0x140035a72  mov     rbx, cs:RegWatchContext
0x140035a79  call    cs:__imp_KeEnterCriticalRegion
0x140035a80  nop     dword ptr [rax+rax+00h]
0x140035a85  lea     rdi, [rbx+18h]
0x140035a89  mov     dl, 1; Wait
0x140035a8b  mov     rcx, rdi; Resource
0x140035a8e  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140035a95  nop     dword ptr [rax+rax+00h]
0x140035a9a  mov     rcx, [rbx+10h]; Handle
0x140035a9e  call    cs:__imp_ZwClose
0x140035aa5  nop     dword ptr [rax+rax+00h]
0x140035aaa  mov     rcx, rdi; Resource
0x140035aad  mov     qword ptr [rbx+10h], 0
0x140035ab5  call    cs:__imp_ExReleaseResourceLite
0x140035abc  nop     dword ptr [rax+rax+00h]
0x140035ac1  call    cs:__imp_KeLeaveCriticalRegion
0x140035ac8  nop     dword ptr [rax+rax+00h]
0x140035acd  lea     rcx, [rbx+0A0h]; Object
0x140035ad4  mov     [rsp+38h+Timeout], 0; Timeout
0x140035add  xor     r9d, r9d; Alertable
0x140035ae0  xor     r8d, r8d; WaitMode
0x140035ae3  xor     edx, edx; WaitReason
0x140035ae5  call    cs:__imp_KeWaitForSingleObject
0x140035aec  nop     dword ptr [rax+rax+00h]
0x140035af1  mov     rcx, rdi; Resource
0x140035af4  call    cs:__imp_ExDeleteResourceLite
0x140035afb  nop     dword ptr [rax+rax+00h]
0x140035b00  mov     rbx, [rsp+38h+arg_0]
0x140035b05  add     rsp, 30h
0x140035b09  pop     rdi
0x140035b0a  retn
```
