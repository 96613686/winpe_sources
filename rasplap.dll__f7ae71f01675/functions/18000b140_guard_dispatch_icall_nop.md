# _guard_dispatch_icall_nop

- ea: `0x18000b140`
- end: `0x18000b142`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180002a00`
- `0x180002c74`
- `0x18000b170`
- `0x18000b1a0`

## pseudocode

```c
__int64 __fastcall guard_dispatch_icall_nop()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x18000b140  jmp     rax
```
