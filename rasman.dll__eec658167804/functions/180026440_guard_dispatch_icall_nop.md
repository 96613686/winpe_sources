# _guard_dispatch_icall_nop

- ea: `0x180026440`
- end: `0x180026442`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180014cd0`
- `0x180014f44`
- `0x180026470`
- `0x1800264a0`

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
0x180026440  jmp     rax
```
