# AppContainerUnregisterSid

- ea: `0x1800068c0`
- end: `0x1800068c6`
- name: `AppContainerUnregisterSid`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `KERNELBASE!AppContainerUnregisterSid` at `0x1800068c0`

## pseudocode

```c
// attributes: thunk
__int64 AppContainerUnregisterSid()
{
  return __imp_AppContainerUnregisterSid();
}

```

## disassembly

```asm
0x1800068c0  jmp     cs:__imp_AppContainerUnregisterSid
```
