# _guard_dispatch_icall_nop

- ea: `0x180004c50`
- end: `0x180004c52`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800042a0`
- `0x180004514`
- `0x180004c80`
- `0x180004cb0`

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
0x180004c50  jmp     rax
```
