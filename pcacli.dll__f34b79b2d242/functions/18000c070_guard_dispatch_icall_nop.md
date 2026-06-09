# _guard_dispatch_icall_nop

- ea: `0x18000c070`
- end: `0x18000c072`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180007870`
- `0x180007ae4`
- `0x18000c0a0`
- `0x18000c130`

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
0x18000c070  jmp     rax
```
