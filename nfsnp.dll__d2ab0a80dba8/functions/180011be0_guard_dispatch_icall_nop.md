# _guard_dispatch_icall_nop

- ea: `0x180011be0`
- end: `0x180011be2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001050`
- `0x1800012c4`
- `0x180011c10`

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
0x180011be0  jmp     rax
```
