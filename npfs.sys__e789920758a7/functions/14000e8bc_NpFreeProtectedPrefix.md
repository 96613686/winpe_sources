# NpFreeProtectedPrefix

- ea: `0x14000e8bc`
- end: `0x14000e913`
- name: `NpFreeProtectedPrefix`
- size: `87`
- prototype: `void __fastcall(FSRTL_ADVANCED_FCB_HEADER *P)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000e640`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000e8d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e900`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e8d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e900`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000e8ef`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000e8ef`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x14000e8c5`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x14000e8c5`

## pseudocode

```c
void __fastcall NpFreeProtectedPrefix(FSRTL_ADVANCED_FCB_HEADER *P)
{
  FsRtlTeardownPerStreamContexts(P);
  ExFreePoolWithTag(P->FastMutex, 0);
  ObDereferenceSecurityDescriptor(P[1].FilterContexts.Blink, 1);
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x14000e8bc  push    rbx
0x14000e8be  sub     rsp, 20h
0x14000e8c2  mov     rbx, rcx
0x14000e8c5  call    cs:__imp_FsRtlTeardownPerStreamContexts
0x14000e8cc  nop     dword ptr [rax+rax+00h]
0x14000e8d1  mov     rcx, [rbx+30h]; P
0x14000e8d5  xor     edx, edx; Tag
0x14000e8d7  call    cs:__imp_ExFreePoolWithTag
0x14000e8de  nop     dword ptr [rax+rax+00h]
0x14000e8e3  mov     rcx, [rbx+98h]
0x14000e8ea  mov     edx, 1
0x14000e8ef  call    cs:__imp_ObDereferenceSecurityDescriptor
0x14000e8f6  nop     dword ptr [rax+rax+00h]
0x14000e8fb  xor     edx, edx; Tag
0x14000e8fd  mov     rcx, rbx; P
0x14000e900  call    cs:__imp_ExFreePoolWithTag
0x14000e907  nop     dword ptr [rax+rax+00h]
0x14000e90c  add     rsp, 20h
0x14000e910  pop     rbx
0x14000e911  retn
```
