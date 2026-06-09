# _guard_dispatch_icall_nop

- ea: `0x140018850`
- end: `0x140018852`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140002420`
- `0x140002620`
- `0x140018820`
- `0x140018880`

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
0x140018850  jmp     rax
```
