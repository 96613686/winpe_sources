# DeleteCriticalSection

- ea: `0x180003b10`
- end: `0x180003b17`
- name: `DeleteCriticalSection`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003b10`

## pseudocode

```c
// attributes: thunk
void __stdcall DeleteCriticalSection(LPCRITICAL_SECTION lpCriticalSection)
{
  __imp_DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180003b10  jmp     cs:__imp_DeleteCriticalSection
```
