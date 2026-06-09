# _guard_dispatch_icall_nop

- ea: `0x18003d080`
- end: `0x18003d082`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x18001cbd0`
- `0x18001ce44`
- `0x18003d0b0`
- `0x18003d0e0`

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
0x18003d080  jmp     rax
```
