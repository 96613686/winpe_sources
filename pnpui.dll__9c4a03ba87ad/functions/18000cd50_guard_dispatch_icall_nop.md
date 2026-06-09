# _guard_dispatch_icall_nop

- ea: `0x18000cd50`
- end: `0x18000cd52`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800012e0`
- `0x180001554`
- `0x180001778`
- `0x18000cd80`
- `0x18000ce10`

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
0x18000cd50  jmp     rax
```
