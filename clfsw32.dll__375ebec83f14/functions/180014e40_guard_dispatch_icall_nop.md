# _guard_dispatch_icall_nop

- ea: `0x180014e40`
- end: `0x180014e42`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001310`
- `0x180001584`
- `0x1800017a8`
- `0x180014e70`
- `0x180014ea0`

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
0x180014e40  jmp     rax
```
