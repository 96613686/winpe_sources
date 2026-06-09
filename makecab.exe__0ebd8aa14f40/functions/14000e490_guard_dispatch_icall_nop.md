# _guard_dispatch_icall_nop

- ea: `0x14000e490`
- end: `0x14000e492`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140001140`
- `0x14000e4c0`
- `0x14000e550`

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
0x14000e490  jmp     rax
```
