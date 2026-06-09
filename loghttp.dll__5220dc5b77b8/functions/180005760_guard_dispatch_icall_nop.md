# _guard_dispatch_icall_nop

- ea: `0x180005760`
- end: `0x180005762`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180002640`
- `0x1800028b4`
- `0x180002ad4`
- `0x180005790`
- `0x1800057c0`

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
0x180005760  jmp     rax
```
