# _guard_dispatch_icall_nop

- ea: `0x1800113b0`
- end: `0x1800113b2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001bf0`
- `0x180001e64`
- `0x180002534`
- `0x180011380`
- `0x1800113e0`

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
0x1800113b0  jmp     rax
```
