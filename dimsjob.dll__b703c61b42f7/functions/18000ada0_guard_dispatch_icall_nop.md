# _guard_dispatch_icall_nop

- ea: `0x18000ada0`
- end: `0x18000ada2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800043e0`
- `0x180004654`
- `0x1800048e4`
- `0x18000ad70`
- `0x18000add0`

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
0x18000ada0  jmp     rax
```
