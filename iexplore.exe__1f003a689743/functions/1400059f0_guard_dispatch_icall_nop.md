# _guard_dispatch_icall_nop

- ea: `0x1400059f0`
- end: `0x1400059f2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140001970`
- `0x140001c08`
- `0x140005a20`
- `0x140005ab0`

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
0x1400059f0  jmp     rax
```
