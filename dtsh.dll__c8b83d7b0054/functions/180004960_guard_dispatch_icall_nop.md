# _guard_dispatch_icall_nop

- ea: `0x180004960`
- end: `0x180004962`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001170`
- `0x1800013e4`
- `0x180001628`
- `0x180004990`
- `0x1800049c0`

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
0x180004960  jmp     rax
```
