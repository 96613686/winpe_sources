# _guard_dispatch_icall_nop

- ea: `0x180007d60`
- end: `0x180007d62`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180005380`
- `0x1800055f4`
- `0x180007d90`
- `0x180007dc0`

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
0x180007d60  jmp     rax
```
