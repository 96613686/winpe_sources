# _guard_dispatch_icall_nop

- ea: `0x180008e70`
- end: `0x180008e72`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800011f0`
- `0x180001464`
- `0x180001868`
- `0x180008ea0`
- `0x180008ed0`

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
0x180008e70  jmp     rax
```
