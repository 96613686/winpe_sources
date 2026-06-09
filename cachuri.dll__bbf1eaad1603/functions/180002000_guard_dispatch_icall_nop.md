# _guard_dispatch_icall_nop

- ea: `0x180002000`
- end: `0x180002002`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001520`
- `0x180001794`
- `0x180002030`
- `0x180002060`

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
0x180002000  jmp     rax
```
