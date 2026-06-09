# CCriticalSection::~CCriticalSection(void)

- ea: `0x180007834`
- end: `0x18000783b`
- name: `??1CCriticalSection@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18001d9dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007834`

## pseudocode

```c
// attributes: thunk
void __stdcall CCriticalSection::~CCriticalSection(LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180007834  jmp     cs:__imp_DeleteCriticalSection
```
