# _guard_dispatch_icall_nop

- ea: `0x180009e80`
- end: `0x180009e82`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180005050`
- `0x1800052c4`
- `0x1800056f0`
- `0x180009eb0`
- `0x180009f40`

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
0x180009e80  jmp     rax
```
