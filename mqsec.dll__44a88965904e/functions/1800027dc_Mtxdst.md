# _Mtxdst

- ea: `0x1800027dc`
- end: `0x1800027e3`
- name: `_Mtxdst`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180001a20`
- `0x180001af4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800027dc`

## pseudocode

```c
// attributes: thunk
void __stdcall Mtxdst(LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x1800027dc  jmp     cs:__imp_DeleteCriticalSection
```
