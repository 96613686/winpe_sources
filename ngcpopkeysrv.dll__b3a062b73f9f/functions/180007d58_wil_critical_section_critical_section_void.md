# wil::critical_section::~critical_section(void)

- ea: `0x180007d58`
- end: `0x180007d68`
- name: `??1critical_section@wil@@QEAA@XZ`
- size: `16`
- prototype: `void __fastcall(wil::critical_section *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180024205`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007d5c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007d5c`

## pseudocode

```c
void __fastcall wil::critical_section::~critical_section(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180007d58  sub     rsp, 28h
0x180007d5c  call    cs:__imp_DeleteCriticalSection
0x180007d62  nop
0x180007d63  add     rsp, 28h
0x180007d67  retn
```
