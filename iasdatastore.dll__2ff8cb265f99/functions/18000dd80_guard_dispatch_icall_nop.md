# _guard_dispatch_icall_nop

- ea: `0x18000dd80`
- end: `0x18000dd82`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800011d0`
- `0x180001444`
- `0x180001a64`
- `0x18000dd50`
- `0x18000ddb0`

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
0x18000dd80  jmp     rax
```
