# CLock::Release(void)

- ea: `0x180009f70`
- end: `0x180009f77`
- name: `?Release@CLock@@QEAAXXZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `27`
- callee_count: `0`
- tags: ``

## callers

- `0x180007b10`
- `0x180007b74`
- `0x180007c2c`
- `0x180007d0c`
- `0x1800083e8`
- `0x1800086b8`
- `0x1800087f0`
- `0x180008970`
- `0x180008b00`
- `0x180008b38`
- `0x180008c10`
- `0x180008dfc`
- `0x180009028`
- `0x180009094`
- `0x180009190`
- `0x1800091e0`
- `0x1800092a8`
- `0x1800093a4`
- `0x1800093f8`
- `0x180009468`
- `0x1800094b8`
- `0x180009518`
- `0x1800095fc`
- `0x1800096f0`
- `0x1800097dc`
- `0x180009944`
- `0x1800099d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009f70`

## pseudocode

```c
// attributes: thunk
void __stdcall CLock::Release(LPCRITICAL_SECTION lpCriticalSection)
{
  LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180009f70  jmp     cs:__imp_LeaveCriticalSection
```
