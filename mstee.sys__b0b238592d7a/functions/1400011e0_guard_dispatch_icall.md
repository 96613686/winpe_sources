# _guard_dispatch_icall

- ea: `0x1400011e0`
- end: `0x1400011e6`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140002010`
- `0x1400082a0`

## callees

- `0x140001210`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x1400011e0  jmp     cs:__guard_dispatch_icall_fptr
```
