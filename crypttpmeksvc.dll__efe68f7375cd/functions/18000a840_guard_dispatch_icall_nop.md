# _guard_dispatch_icall_nop

- ea: `0x18000a840`
- end: `0x18000a842`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180006510`
- `0x180006784`
- `0x18000a870`
- `0x18000a900`

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
0x18000a840  jmp     rax
```
