# _Smtx_unlock_shared

- ea: `0x18000affc`
- end: `0x18000b003`
- name: `_Smtx_unlock_shared`
- size: `7`
- prototype: `void __cdecl(_Smtx_t *)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x180005d70`
- `0x180006060`
- `0x180006110`
- `0x18000953c`
- `0x18000ac30`
- `0x18000e980`
- `0x18000efc0`
- `0x18000f120`
- `0x18000f190`
- `0x18000f200`
- `0x18000f280`
- `0x18000f320`
- `0x18000f3c0`
- `0x1800100a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000affc`

## pseudocode

```c
// attributes: thunk
void __cdecl Smtx_unlock_shared(_Smtx_t *a1)
{
  ReleaseSRWLockShared((PSRWLOCK)a1);
}

```

## disassembly

```asm
0x18000affc  jmp     cs:__imp_ReleaseSRWLockShared
```
