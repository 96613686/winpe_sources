# AppContainerRegisterSid

- ea: `0x1800068b0`
- end: `0x1800068b6`
- name: `AppContainerRegisterSid`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `KERNELBASE!AppContainerRegisterSid` at `0x1800068b0`

## pseudocode

```c
// attributes: thunk
__int64 AppContainerRegisterSid()
{
  return __imp_AppContainerRegisterSid();
}

```

## disassembly

```asm
0x1800068b0  jmp     cs:__imp_AppContainerRegisterSid
```
