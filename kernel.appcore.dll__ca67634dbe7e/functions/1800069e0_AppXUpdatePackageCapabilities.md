# AppXUpdatePackageCapabilities

- ea: `0x1800069e0`
- end: `0x1800069e6`
- name: `AppXUpdatePackageCapabilities`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `KERNELBASE!AppXUpdatePackageCapabilities` at `0x1800069e0`

## pseudocode

```c
// attributes: thunk
__int64 AppXUpdatePackageCapabilities()
{
  return __imp_AppXUpdatePackageCapabilities();
}

```

## disassembly

```asm
0x1800069e0  jmp     cs:__imp_AppXUpdatePackageCapabilities
```
