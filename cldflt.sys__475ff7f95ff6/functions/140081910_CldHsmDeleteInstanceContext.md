# CldHsmDeleteInstanceContext

- ea: `0x140081910`
- end: `0x14008194f`
- name: `CldHsmDeleteInstanceContext`
- size: `63`
- prototype: `void __fastcall(char *P)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140081958`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14008193c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008193c`
- `ntoskrnl!ExDeleteResourceLite` at `0x140081920`
- `ntoskrnl!ExDeleteResourceLite` at `0x140081920`

## pseudocode

```c
void __fastcall CldHsmDeleteInstanceContext(char *P)
{
  ExDeleteResourceLite((PERESOURCE)(P + 272));
  CldSyncCleanup(P);
  ExFreePoolWithTag(P, 0x63496C43u);
}

```

## disassembly

```asm
0x140081910  push    rbx
0x140081912  sub     rsp, 20h
0x140081916  mov     rbx, rcx
0x140081919  add     rcx, 110h; Resource
0x140081920  call    cs:__imp_ExDeleteResourceLite
0x140081927  nop     dword ptr [rax+rax+00h]
0x14008192c  mov     rcx, rbx
0x14008192f  call    CldSyncCleanup
0x140081934  mov     edx, 63496C43h; Tag
0x140081939  mov     rcx, rbx; P
0x14008193c  call    cs:__imp_ExFreePoolWithTag
0x140081943  nop     dword ptr [rax+rax+00h]
0x140081948  add     rsp, 20h
0x14008194c  pop     rbx
0x14008194d  retn
```
