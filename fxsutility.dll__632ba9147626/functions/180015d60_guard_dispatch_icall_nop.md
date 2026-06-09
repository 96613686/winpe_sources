# _guard_dispatch_icall_nop

- ea: `0x180015d60`
- end: `0x180015d62`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800013a0`
- `0x180001614`
- `0x180001af4`
- `0x180015d30`
- `0x180015d90`

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
0x180015d60  jmp     rax
```
