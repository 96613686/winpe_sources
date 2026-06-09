# operator delete(void *)

- ea: `0x1800010a4`
- end: `0x1800010a9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `19`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800010b0`
- `0x1800021e4`
- `0x180003590`
- `0x1800042bc`
- `0x180007c20`
- `0x180008430`
- `0x1800084a0`
- `0x180008614`
- `0x180009920`
- `0x180009ef0`
- `0x18000a6c0`
- `0x18000bddc`
- `0x18000c140`
- `0x18000c550`
- `0x18000c9a0`
- `0x18000ca70`
- `0x18000d520`
- `0x18000d570`
- `0x18000de40`

## callees

- `0x180001836`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free_0(Block);
}

```

## disassembly

```asm
0x1800010a4  jmp     free_0
```
