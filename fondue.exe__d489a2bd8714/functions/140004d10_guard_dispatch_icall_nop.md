# _guard_dispatch_icall_nop

- ea: `0x140004d10`
- end: `0x140004d12`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140001220`
- `0x1400017cc`
- `0x140004d40`
- `0x140004dd0`

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
0x140004d10  jmp     rax
```
