# _guard_dispatch_icall_nop

- ea: `0x180019260`
- end: `0x180019262`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001ec0`
- `0x180002134`
- `0x1800026a0`
- `0x180019230`
- `0x180019290`

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
0x180019260  jmp     rax
```
