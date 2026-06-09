# _guard_dispatch_icall_nop

- ea: `0x180013720`
- end: `0x180013722`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800015c0`
- `0x180001834`
- `0x180001a68`
- `0x1800136f0`
- `0x180013750`

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
0x180013720  jmp     rax
```
