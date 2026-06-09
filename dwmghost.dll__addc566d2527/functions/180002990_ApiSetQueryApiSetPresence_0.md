# ApiSetQueryApiSetPresence_0

- ea: `0x180002990`
- end: `0x180002996`
- name: `ApiSetQueryApiSetPresence_0`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002840`
- `0x180002894`
- `0x1800028e8`
- `0x18000293c`

## import_xrefs

- `api-ms-win-core-apiquery-l1-1-0!ApiSetQueryApiSetPresence` at `0x180002990`

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
0x180002990  jmp     cs:__imp_ApiSetQueryApiSetPresence
```
