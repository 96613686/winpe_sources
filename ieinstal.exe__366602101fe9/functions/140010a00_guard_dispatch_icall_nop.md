# _guard_dispatch_icall_nop

- ea: `0x140010a00`
- end: `0x140010a02`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1400012b0`
- `0x140001738`
- `0x140010a30`
- `0x140010a60`

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
0x140010a00  jmp     rax
```
