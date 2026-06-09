# OpenStateExplicitForUserSidString

- ea: `0x1800072a0`
- end: `0x1800072a6`
- name: `OpenStateExplicitForUserSidString`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `KERNELBASE!OpenStateExplicitForUserSidString` at `0x1800072a0`

## pseudocode

```c
// attributes: thunk
__int64 OpenStateExplicitForUserSidString()
{
  return __imp_OpenStateExplicitForUserSidString();
}

```

## disassembly

```asm
0x1800072a0  jmp     cs:__imp_OpenStateExplicitForUserSidString
```
