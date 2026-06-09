# ApiSetQueryApiSetPresence_0

- ea: `0x18000ac86`
- end: `0x18000ac8c`
- name: `ApiSetQueryApiSetPresence_0`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180009fec`
- `0x18000a250`
- `0x18000a52c`
- `0x18000a580`

## import_xrefs

- `api-ms-win-core-apiquery-l1-1-0!ApiSetQueryApiSetPresence` at `0x18000ac86`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ApiSetQueryApiSetPresence_0(__int64 a1, __int64 a2)
{
  return ApiSetQueryApiSetPresence(a1, a2);
}

```

## disassembly

```asm
0x18000ac86  jmp     cs:__imp_ApiSetQueryApiSetPresence
```
