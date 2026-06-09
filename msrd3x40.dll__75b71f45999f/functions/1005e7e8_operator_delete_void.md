# operator delete[](void *)

- ea: `0x1005e7e8`
- end: `0x1005e7ed`
- name: `??_V@YAXPAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `426`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1000dac0`
- `0x1000f750`
- `0x1000f7f0`
- `0x1000f890`
- `0x1000faa0`
- `0x1000fc30`
- `0x1000fde0`
- `0x1000ffb0`
- `0x10010120`
- `0x10010290`
- `0x100106b0`
- `0x10010790`
- `0x10010810`
- `0x100109e0`
- `0x10010d60`
- `0x10010f50`
- `0x10011160`
- `0x10011400`
- `0x10011540`
- `0x10011f50`
- `0x10012190`
- `0x100125e0`
- `0x100128e0`
- `0x10012b50`
- `0x10012db0`
- `0x10012dd0`
- `0x100130b0`
- `0x10013120`
- `0x10013190`
- `0x10013200`
- `0x10013730`
- `0x10014150`
- `0x100143e0`
- `0x10014470`
- `0x10014520`
- `0x10014850`
- `0x10014b40`
- `0x10014bd0`
- `0x10014c80`
- `0x10014f80`
- `0x10015010`
- `0x100150e0`
- `0x10015390`
- `0x10015420`
- `0x10015660`
- `0x100156f0`
- `0x10015990`
- `0x10015a20`
- `0x10015d00`
- `0x10015d90`

## callees

- `0x1005ef05`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete[](void *Block)
{
  operator delete(Block);
}

```

## disassembly

```asm
0x1005e7e8  jmp     ??3@YAXPAX@Z; operator delete(void *)
```
