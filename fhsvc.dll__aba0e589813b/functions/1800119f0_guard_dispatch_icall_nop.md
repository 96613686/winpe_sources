# _guard_dispatch_icall_nop

- ea: `0x1800119f0`
- end: `0x1800119f2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x18000cbb0`
- `0x18000ce24`
- `0x18000d14c`
- `0x1800119c0`
- `0x180011a20`

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
0x1800119f0  jmp     rax
```
