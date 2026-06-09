# _guard_dispatch_icall_nop

- ea: `0x180005fd0`
- end: `0x180005fd2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800054f0`
- `0x180005764`
- `0x180006000`
- `0x180006090`

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
0x180005fd0  jmp     rax
```
