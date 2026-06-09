# GetPublisherCacheFolder

- ea: `0x180007030`
- end: `0x180007036`
- name: `GetPublisherCacheFolder`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!GetPublisherCacheFolder` at `0x180007030`

## pseudocode

```c
// attributes: thunk
__int64 GetPublisherCacheFolder()
{
  return __imp_GetPublisherCacheFolder();
}

```

## disassembly

```asm
0x180007030  jmp     cs:__imp_GetPublisherCacheFolder
```
