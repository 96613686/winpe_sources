# FontVariationAllocation::operator delete(void *)

- ea: `0x140064088`
- end: `0x140064098`
- name: `??3FontVariationAllocation@@SAXPEAX@Z`
- size: `16`
- prototype: `void __fastcall(void *)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1400318d4`
- `0x140035de4`
- `0x140039070`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x14006408c`
- `KERNEL32!GlobalFree` at `0x14006408c`

## pseudocode

```c
void __fastcall FontVariationAllocation::operator delete(void *a1)
{
  GlobalFree(a1);
}

```

## disassembly

```asm
0x140064088  sub     rsp, 28h
0x14006408c  call    cs:__imp_GlobalFree
0x140064092  nop
0x140064093  add     rsp, 28h
0x140064097  retn
```
