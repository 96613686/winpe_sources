# AppXGetPackageSid

- ea: `0x1800069b0`
- end: `0x1800069b6`
- name: `AppXGetPackageSid`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `KERNELBASE!AppXGetPackageSid` at `0x1800069b0`

## pseudocode

```c
// attributes: thunk
__int64 AppXGetPackageSid()
{
  return __imp_AppXGetPackageSid();
}

```

## disassembly

```asm
0x1800069b0  jmp     cs:__imp_AppXGetPackageSid
```
