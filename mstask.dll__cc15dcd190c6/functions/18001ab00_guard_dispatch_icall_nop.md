# _guard_dispatch_icall_nop

- ea: `0x18001ab00`
- end: `0x18001ab02`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180009f90`
- `0x18000a204`
- `0x18001ab30`
- `0x18001abc0`

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
0x18001ab00  jmp     rax
```
