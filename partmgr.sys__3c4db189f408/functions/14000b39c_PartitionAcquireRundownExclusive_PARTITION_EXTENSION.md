# PartitionAcquireRundownExclusive(_PARTITION_EXTENSION *)

- ea: `0x14000b39c`
- end: `0x14000b3f6`
- name: `?PartitionAcquireRundownExclusive@@YAXPEAU_PARTITION_EXTENSION@@@Z`
- size: `90`
- prototype: `void __fastcall(struct _PARTITION_EXTENSION *)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x14000c47c`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000b3bd`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000b3bd`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14000b3e3`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14000b3e3`
- `ntoskrnl!KeClearEvent` at `0x14000b3d0`
- `ntoskrnl!KeClearEvent` at `0x14000b3d0`

## pseudocode

```c
void __fastcall PartitionAcquireRundownExclusive(struct _PARTITION_EXTENSION *a1)
{
  KeWaitForSingleObject((char *)a1 + 344, Executive, 0, 0, 0);
  KeClearEvent((PRKEVENT)a1 + 17);
  ExWaitForRundownProtectionReleaseCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)a1 + 50));
}

```

## disassembly

```asm
0x14000b39c  push    rbx
0x14000b39e  sub     rsp, 30h
0x14000b3a2  mov     rbx, rcx
0x14000b3a5  mov     [rsp+38h+Timeout], 0; Timeout
0x14000b3ae  add     rcx, 158h; Object
0x14000b3b5  xor     r9d, r9d; Alertable
0x14000b3b8  xor     r8d, r8d; WaitMode
0x14000b3bb  xor     edx, edx; WaitReason
0x14000b3bd  call    cs:__imp_KeWaitForSingleObject
0x14000b3c4  nop     dword ptr [rax+rax+00h]
0x14000b3c9  lea     rcx, [rbx+198h]; Event
0x14000b3d0  call    cs:__imp_KeClearEvent
0x14000b3d7  nop     dword ptr [rax+rax+00h]
0x14000b3dc  mov     rcx, [rbx+190h]; RunRef
0x14000b3e3  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x14000b3ea  nop     dword ptr [rax+rax+00h]
0x14000b3ef  add     rsp, 30h
0x14000b3f3  pop     rbx
0x14000b3f4  retn
```
