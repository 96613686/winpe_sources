# CdpReferenceObjectClose

- ea: `0x14000c370`
- end: `0x14000c3c2`
- name: `CdpReferenceObjectClose`
- size: `82`
- prototype: `__int64 __fastcall(PVOID P, PIRP Irp)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000b020`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000c38e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c38e`
- `ntoskrnl!IofCompleteRequest` at `0x14000c3a8`
- `ntoskrnl!IofCompleteRequest` at `0x14000c3a8`

## pseudocode

```c
__int64 __fastcall CdpReferenceObjectClose(char **P, PIRP Irp)
{
  CdDereferenceServer(P[1]);
  ExFreePoolWithTag(P, 0);
  Irp->IoStatus.Status = 0;
  Irp->IoStatus.Information = 0;
  IofCompleteRequest(Irp, 0);
  return 0;
}

```

## disassembly

```asm
0x14000c370  mov     [rsp+arg_0], rbx
0x14000c375  push    rdi
0x14000c376  sub     rsp, 20h
0x14000c37a  mov     rbx, rcx
0x14000c37d  mov     rdi, rdx
0x14000c380  mov     rcx, [rcx+8]; P
0x14000c384  call    CdDereferenceServer
0x14000c389  xor     edx, edx; Tag
0x14000c38b  mov     rcx, rbx; P
0x14000c38e  call    cs:__imp_ExFreePoolWithTag
0x14000c395  nop     dword ptr [rax+rax+00h]
0x14000c39a  xor     eax, eax
0x14000c39c  xor     edx, edx; PriorityBoost
0x14000c39e  mov     rcx, rdi; Irp
0x14000c3a1  mov     [rdi+30h], eax
0x14000c3a4  mov     [rdi+38h], rax
0x14000c3a8  call    cs:__imp_IofCompleteRequest
0x14000c3af  nop     dword ptr [rax+rax+00h]
0x14000c3b4  mov     rbx, [rsp+28h+arg_0]
0x14000c3b9  xor     eax, eax
0x14000c3bb  add     rsp, 20h
0x14000c3bf  pop     rdi
0x14000c3c0  retn
```
