# _guard_dispatch_icall

- ea: `0x140003e00`
- end: `0x140003e06`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `20`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001064`
- `0x1400011c0`
- `0x140002510`
- `0x14000292c`
- `0x140002970`
- `0x1400029cc`
- `0x140002d00`
- `0x140002d54`
- `0x140002e04`
- `0x140002ea0`
- `0x1400031d4`
- `0x140003938`
- `0x140003970`
- `0x140005010`
- `0x14000a100`
- `0x14000a1a4`
- `0x14000a238`
- `0x14000a380`
- `0x14000b1c0`
- `0x14000b5c0`

## callees

- `0x140003e30`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x140003e00  jmp     cs:__guard_dispatch_icall_fptr
```
