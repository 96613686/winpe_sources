# _guard_dispatch_icall_nop

- ea: `0x180012080`
- end: `0x180012082`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001a10`
- `0x180001c84`
- `0x180001e98`
- `0x1800120b0`
- `0x180012140`

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
0x180012080  jmp     rax
```
