# _guard_dispatch_icall_nop

- ea: `0x180012bb0`
- end: `0x180012bb2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001650`
- `0x1800018c4`
- `0x180001e04`
- `0x180012b80`
- `0x180012be0`

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
0x180012bb0  jmp     rax
```
