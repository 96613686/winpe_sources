# operator delete(void *)

- ea: `0x1800032d0`
- end: `0x1800032d7`
- name: `??3@YAXPEAX@Z`
- size: `7`
- prototype: `HLOCAL __stdcall(HLOCAL hMem)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1800048a0`
- `0x18000af10`
- `0x18000af50`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800032d0`

## pseudocode

```c
// attributes: thunk
HLOCAL __stdcall operator delete(HLOCAL hMem)
{
  return LocalFree(hMem);
}

```

## disassembly

```asm
0x1800032d0  jmp     cs:__imp_LocalFree
```
