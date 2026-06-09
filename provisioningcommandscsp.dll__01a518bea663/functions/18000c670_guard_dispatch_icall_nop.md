# _guard_dispatch_icall_nop

- ea: `0x18000c670`
- end: `0x18000c672`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001720`
- `0x180001994`
- `0x180001c80`
- `0x18000c640`
- `0x18000c6a0`

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
0x18000c670  jmp     rax
```
