# operator delete[](void *)

- ea: `0x100358db`
- end: `0x100358e0`
- name: `??_V@YAXPAX@Z`
- size: `5`
- prototype: `void __cdecl(void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x100213d0`

## callees

- `0x1001eba0`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete[](_DWORD *a1)
{
  operator delete(a1);
}

```

## disassembly

```asm
0x100358db  jmp     ??3@YAXPAX@Z; operator delete(void *)
```
