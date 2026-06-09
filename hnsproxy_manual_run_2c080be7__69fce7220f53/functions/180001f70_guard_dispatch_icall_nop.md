# _guard_dispatch_icall_nop

- ea: `0x180001f70`
- end: `0x180001f72`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001f50`
- `0x180001f90`

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
0x180001f70  jmp     rax
```
