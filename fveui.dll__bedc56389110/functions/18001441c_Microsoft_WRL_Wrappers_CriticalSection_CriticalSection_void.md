# Microsoft::WRL::Wrappers::CriticalSection::~CriticalSection(void)

- ea: `0x18001441c`
- end: `0x180014423`
- name: `??1CriticalSection@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18002c90d`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001441c`

## pseudocode

```c
// attributes: thunk
void __stdcall Microsoft::WRL::Wrappers::CriticalSection::~CriticalSection(LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18001441c  jmp     cs:__imp_DeleteCriticalSection
```
