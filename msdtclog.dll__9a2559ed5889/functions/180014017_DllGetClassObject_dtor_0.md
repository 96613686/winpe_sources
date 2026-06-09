# DllGetClassObject$dtor$0

- ea: `0x180014017`
- end: `0x180014023`
- name: `DllGetClassObject$dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x180001300`

## pseudocode

```c
void __fastcall DllGetClassObject_dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 64));
}

```

## disassembly

```asm
0x180014017  mov     rcx, [rdx+40h]; Block
0x18001401e  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
