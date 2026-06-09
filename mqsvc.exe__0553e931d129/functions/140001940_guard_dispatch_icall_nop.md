# _guard_dispatch_icall_nop

- ea: `0x140001940`
- end: `0x140001942`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1400011c0`
- `0x1400016b0`
- `0x140001970`

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
0x140001940  jmp     rax
```
