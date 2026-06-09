# CLock::~CLock(void)

- ea: `0x180009f50`
- end: `0x180009f57`
- name: `??1CLock@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180007a38`
- `0x180008314`
- `0x180008d54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009f50`

## pseudocode

```c
// attributes: thunk
void __stdcall CLock::~CLock(LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180009f50  jmp     cs:__imp_DeleteCriticalSection
```
