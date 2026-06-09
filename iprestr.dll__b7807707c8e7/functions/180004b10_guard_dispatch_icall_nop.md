# _guard_dispatch_icall_nop

- ea: `0x180004b10`
- end: `0x180004b12`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001120`
- `0x180001394`
- `0x1800015a8`
- `0x180004b40`
- `0x180004b70`

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
0x180004b10  jmp     rax
```
