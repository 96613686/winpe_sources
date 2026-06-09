# _guard_dispatch_icall_nop

- ea: `0x1800078b0`
- end: `0x1800078b2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180002080`
- `0x1800022f4`
- `0x1800078e0`
- `0x180007910`

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
0x1800078b0  jmp     rax
```
