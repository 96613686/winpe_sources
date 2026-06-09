# wil::critical_section::~critical_section(void)

- ea: `0x18000aeec`
- end: `0x18000aef3`
- name: `??1critical_section@wil@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180018d10`
- `0x180018d52`
- `0x180018d81`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000aeec`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
// attributes: thunk
void __stdcall wil::critical_section::~critical_section(LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18000aeec  jmp     cs:__imp_DeleteCriticalSection
```
