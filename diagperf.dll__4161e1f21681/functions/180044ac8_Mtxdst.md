# _Mtxdst

- ea: `0x180044ac8`
- end: `0x180044acf`
- name: `_Mtxdst`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180056e48`
- `0x1800d20d6`
- `0x1800d4d92`
- `0x1800d4da8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180044ac8`

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
0x180044ac8  jmp     cs:__imp_DeleteCriticalSection
```
