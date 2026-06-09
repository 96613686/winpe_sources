# _guard_dispatch_icall_nop

- ea: `0x180014b20`
- end: `0x180014b22`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001cf0`
- `0x180001f64`
- `0x180014b50`
- `0x180014be0`

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
0x180014b20  jmp     rax
```
