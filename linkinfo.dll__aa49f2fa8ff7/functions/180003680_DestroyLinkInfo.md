# DestroyLinkInfo

- ea: `0x180003680`
- end: `0x180003687`
- name: `DestroyLinkInfo`
- size: `7`
- prototype: `HLOCAL __stdcall(HLOCAL hMem)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003680`

## pseudocode

```c
// attributes: thunk
HLOCAL __stdcall DestroyLinkInfo(HLOCAL hMem)
{
  return LocalFree(hMem);
}

```

## disassembly

```asm
0x180003680  jmp     cs:__imp_LocalFree
```
