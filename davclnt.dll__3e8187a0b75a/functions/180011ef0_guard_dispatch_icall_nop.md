# _guard_dispatch_icall_nop

- ea: `0x180011ef0`
- end: `0x180011ef2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x18000a040`
- `0x18000a2b4`
- `0x180011f20`
- `0x180011f50`

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
0x180011ef0  jmp     rax
```
