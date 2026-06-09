# j_j__guard_dispatch_icall_nop

- ea: `0x180139010`
- end: `0x180139015`
- name: `j_j__guard_dispatch_icall_nop`
- size: `5`
- prototype: ``
- caller_count: `17`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800cbac8`
- `0x1800cbc54`
- `0x1800cbef0`
- `0x1800cc030`
- `0x1800cc18c`
- `0x1800cc470`
- `0x1800cc65c`
- `0x1800cc6a0`
- `0x1800cca08`
- `0x1800cca64`
- `0x1800cd7b0`
- `0x1800cd960`
- `0x1800cdc78`
- `0x1800ce130`
- `0x1800ce300`
- `0x1800cf964`
- `0x1800cfb78`

## callees

- `0x1801367f0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall j_j__guard_dispatch_icall_nop()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x180139010  jmp     j__guard_dispatch_icall_nop
```
