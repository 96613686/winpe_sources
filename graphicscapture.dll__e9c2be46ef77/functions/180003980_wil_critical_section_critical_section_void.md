# wil::critical_section::~critical_section(void)

- ea: `0x180003980`
- end: `0x180003987`
- name: `??1critical_section@wil@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180025feb`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003980`

## pseudocode

```c
// attributes: thunk
void __stdcall wil::critical_section::~critical_section(LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180003980  jmp     cs:__imp_DeleteCriticalSection
```
