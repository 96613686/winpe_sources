# _guard_dispatch_icall_nop

- ea: `0x1800027a0`
- end: `0x1800027a2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001e10`
- `0x180002084`
- `0x1800027d0`
- `0x180002800`

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
0x1800027a0  jmp     rax
```
