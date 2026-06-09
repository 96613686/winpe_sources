# ApiSetQueryApiSetPresence_0

- ea: `0x180001a38`
- end: `0x180001a3e`
- name: `ApiSetQueryApiSetPresence_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800019e4`

## import_xrefs

- `api-ms-win-core-apiquery-l1-1-0!ApiSetQueryApiSetPresence` at `0x180001a38`

## pseudocode

```c
// attributes: thunk
__int64 ApiSetQueryApiSetPresence_0()
{
  return ApiSetQueryApiSetPresence();
}

```

## disassembly

```asm
0x180001a38  jmp     cs:__imp_ApiSetQueryApiSetPresence
```
