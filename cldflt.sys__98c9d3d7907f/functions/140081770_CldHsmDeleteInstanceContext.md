# CldHsmDeleteInstanceContext

- ea: `0x140081770`
- end: `0x1400817af`
- name: `CldHsmDeleteInstanceContext`
- size: `63`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400817b8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14008179c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008179c`
- `ntoskrnl!ExDeleteResourceLite` at `0x140081780`
- `ntoskrnl!ExDeleteResourceLite` at `0x140081780`

## pseudocode

```c
void __fastcall CldHsmDeleteInstanceContext(char *P)
{
  ExDeleteResourceLite((PERESOURCE)(P + 272));
  CldSyncCleanup((struct _UNICODE_PREFIX_TABLE *)P);
  ExFreePoolWithTag(P, 0x63496C43u);
}

```

## disassembly

```asm
0x140081770  push    rbx
0x140081772  sub     rsp, 20h
0x140081776  mov     rbx, rcx
0x140081779  add     rcx, 110h; Resource
0x140081780  call    cs:__imp_ExDeleteResourceLite
0x140081787  nop     dword ptr [rax+rax+00h]
0x14008178c  mov     rcx, rbx
0x14008178f  call    CldSyncCleanup
0x140081794  mov     edx, 63496C43h; Tag
0x140081799  mov     rcx, rbx; P
0x14008179c  call    cs:__imp_ExFreePoolWithTag
0x1400817a3  nop     dword ptr [rax+rax+00h]
0x1400817a8  add     rsp, 20h
0x1400817ac  pop     rbx
0x1400817ad  retn
```
