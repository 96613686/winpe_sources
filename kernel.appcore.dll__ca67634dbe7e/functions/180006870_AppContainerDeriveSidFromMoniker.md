# AppContainerDeriveSidFromMoniker

- ea: `0x180006870`
- end: `0x180006876`
- name: `AppContainerDeriveSidFromMoniker`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `KERNELBASE!AppContainerDeriveSidFromMoniker` at `0x180006870`

## pseudocode

```c
// attributes: thunk
__int64 AppContainerDeriveSidFromMoniker()
{
  return __imp_AppContainerDeriveSidFromMoniker();
}

```

## disassembly

```asm
0x180006870  jmp     cs:__imp_AppContainerDeriveSidFromMoniker
```
