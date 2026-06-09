# ApiSetQueryApiSetPresence_0

- ea: `0x180007acd`
- end: `0x180007ad3`
- name: `ApiSetQueryApiSetPresence_0`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000772c`
- `0x180007820`

## import_xrefs

- `api-ms-win-core-apiquery-l1-1-0!ApiSetQueryApiSetPresence` at `0x180007acd`

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
0x180007acd  jmp     cs:__imp_ApiSetQueryApiSetPresence
```
