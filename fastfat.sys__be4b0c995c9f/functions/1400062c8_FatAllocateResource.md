# FatAllocateResource

- ea: `0x1400062c8`
- end: `0x1400062fd`
- name: `FatAllocateResource`
- size: `53`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x14004763c`
- `0x140047960`
- `0x140047e34`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x1400062e7`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400062e7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400062d5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400062d5`

## pseudocode

```c
struct _ERESOURCE *__fastcall FatAllocateResource()
{
  struct _ERESOURCE *v0; // rbx

  v0 = (struct _ERESOURCE *)ExAllocateFromNPagedLookasideList(&FatEResourceLookasideList);
  ExInitializeResourceLite(v0);
  return v0;
}

```

## disassembly

```asm
0x1400062c8  push    rbx
0x1400062ca  sub     rsp, 20h
0x1400062ce  lea     rcx, FatEResourceLookasideList; Lookaside
0x1400062d5  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400062dc  nop     dword ptr [rax+rax+00h]
0x1400062e1  mov     rcx, rax; Resource
0x1400062e4  mov     rbx, rax
0x1400062e7  call    cs:__imp_ExInitializeResourceLite
0x1400062ee  nop     dword ptr [rax+rax+00h]
0x1400062f3  mov     rax, rbx
0x1400062f6  add     rsp, 20h
0x1400062fa  pop     rbx
0x1400062fb  retn
```
