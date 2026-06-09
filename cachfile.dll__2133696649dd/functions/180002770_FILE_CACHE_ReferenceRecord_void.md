# FILE_CACHE::ReferenceRecord(void *)

- ea: `0x180002770`
- end: `0x18000277f`
- name: `?ReferenceRecord@FILE_CACHE@@UEAAXPEAX@Z`
- size: `15`
- prototype: `void __fastcall(FILE_CACHE *__hidden this, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004010`

## pseudocode

```c
void __fastcall FILE_CACHE::ReferenceRecord(FILE_CACHE *this, void *a2)
{
  (*(void (__fastcall **)(void *))(*(_QWORD *)a2 + 8LL))(a2);
}

```

## disassembly

```asm
0x180002770  mov     rax, [rdx]
0x180002773  mov     rcx, rdx
0x180002776  mov     rax, [rax+8]
0x18000277a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
