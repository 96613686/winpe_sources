# GetExtensionApplicationUserModelId

- ea: `0x180006d40`
- end: `0x180006d46`
- name: `GetExtensionApplicationUserModelId`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `KERNELBASE!GetExtensionApplicationUserModelId` at `0x180006d40`

## pseudocode

```c
// attributes: thunk
__int64 GetExtensionApplicationUserModelId()
{
  return __imp_GetExtensionApplicationUserModelId();
}

```

## disassembly

```asm
0x180006d40  jmp     cs:__imp_GetExtensionApplicationUserModelId
```
