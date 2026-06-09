# _guard_dispatch_icall_nop

- ea: `0x140005500`
- end: `0x140005502`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1400011a0`
- `0x140005530`
- `0x1400055c0`

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
0x140005500  jmp     rax
```
