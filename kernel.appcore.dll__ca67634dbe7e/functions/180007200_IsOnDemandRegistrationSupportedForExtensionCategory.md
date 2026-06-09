# IsOnDemandRegistrationSupportedForExtensionCategory

- ea: `0x180007200`
- end: `0x180007206`
- name: `IsOnDemandRegistrationSupportedForExtensionCategory`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `KERNELBASE!IsOnDemandRegistrationSupportedForExtensionCategory` at `0x180007200`

## pseudocode

```c
// attributes: thunk
__int64 IsOnDemandRegistrationSupportedForExtensionCategory()
{
  return __imp_IsOnDemandRegistrationSupportedForExtensionCategory();
}

```

## disassembly

```asm
0x180007200  jmp     cs:__imp_IsOnDemandRegistrationSupportedForExtensionCategory
```
