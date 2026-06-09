# GmsapFreeStringRoutine

- ea: `0x180003500`
- end: `0x180003507`
- name: `GmsapFreeStringRoutine`
- size: `7`
- prototype: `HLOCAL __stdcall(HLOCAL hMem)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800036c0`
- `0x18000461c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003500`

## pseudocode

```c
// attributes: thunk
HLOCAL __stdcall GmsapFreeStringRoutine(HLOCAL hMem)
{
  return LocalFree(hMem);
}

```

## disassembly

```asm
0x180003500  jmp     cs:__imp_LocalFree
```
