# ApiSetQueryApiSetPresence_0

- ea: `0x14000309c`
- end: `0x1400030a2`
- name: `ApiSetQueryApiSetPresence_0`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140002e50`
- `0x140002eb8`
- `0x140003024`
- `0x140003270`

## import_xrefs

- `api-ms-win-core-apiquery-l1-1-0!ApiSetQueryApiSetPresence` at `0x14000309c`

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
0x14000309c  jmp     cs:__imp_ApiSetQueryApiSetPresence
```
