# wil::critical_section::~critical_section(void)

- ea: `0x180023724`
- end: `0x180023734`
- name: `??1critical_section@wil@@QEAA@XZ`
- size: `16`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800394c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023728`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023728`

## pseudocode

```c
void __fastcall wil::critical_section::~critical_section(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180023724  sub     rsp, 28h
0x180023728  call    cs:__imp_DeleteCriticalSection
0x18002372e  nop
0x18002372f  add     rsp, 28h
0x180023733  retn
```
