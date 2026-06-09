# _guard_dispatch_icall_nop

- ea: `0x180009a70`
- end: `0x180009a72`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001370`
- `0x1800015e4`
- `0x180001c08`
- `0x180009a40`
- `0x180009aa0`

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
0x180009a70  jmp     rax
```
