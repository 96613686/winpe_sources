# wil::critical_section::~critical_section(void)

- ea: `0x180016ef0`
- end: `0x180016f00`
- name: `??1critical_section@wil@@QEAA@XZ`
- size: `16`
- prototype: `void __fastcall(wil::critical_section *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18003f3ed`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016ef4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016ef4`

## pseudocode

```c
void __fastcall wil::critical_section::~critical_section(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180016ef0  sub     rsp, 28h
0x180016ef4  call    cs:__imp_DeleteCriticalSection
0x180016efa  nop
0x180016efb  add     rsp, 28h
0x180016eff  retn
```
