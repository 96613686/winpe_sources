# _guard_dispatch_icall_nop

- ea: `0x1800094d0`
- end: `0x1800094d2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180006900`
- `0x180006b74`
- `0x180009500`
- `0x180009530`

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
0x1800094d0  jmp     rax
```
