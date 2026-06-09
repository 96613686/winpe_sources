# _guard_dispatch_icall_nop

- ea: `0x180009970`
- end: `0x180009972`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001440`
- `0x1800016b4`
- `0x180001ca0`
- `0x1800099a0`
- `0x1800099d0`

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
0x180009970  jmp     rax
```
