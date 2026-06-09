# OpenStateExplicitForUserSid

- ea: `0x180007290`
- end: `0x180007296`
- name: `OpenStateExplicitForUserSid`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `KERNELBASE!OpenStateExplicitForUserSid` at `0x180007290`

## pseudocode

```c
// attributes: thunk
__int64 OpenStateExplicitForUserSid()
{
  return __imp_OpenStateExplicitForUserSid();
}

```

## disassembly

```asm
0x180007290  jmp     cs:__imp_OpenStateExplicitForUserSid
```
