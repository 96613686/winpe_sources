# CriticalSection::~CriticalSection(void)

- ea: `0x100186f0`
- end: `0x100186fa`
- name: `??1CriticalSection@@QAE@XZ`
- size: `10`
- prototype: `void __thiscall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x10018700`
- `0x1001f440`
- `0x1004e3a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x100186f3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x100186f3`

## pseudocode

```c
void __thiscall CriticalSection::~CriticalSection(LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x100186f0  mov     edi, edi
0x100186f2  push    ecx; lpCriticalSection
0x100186f3  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x100186f9  retn
```
