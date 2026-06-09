# IP_RESTRICTION_LIST_ENTRY::~IP_RESTRICTION_LIST_ENTRY(void)

- ea: `0x180002ee4`
- end: `0x180002eef`
- name: `??1IP_RESTRICTION_LIST_ENTRY@@QEAA@XZ`
- size: `11`
- prototype: `void __fastcall(IP_RESTRICTION_LIST_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180002e78`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180002ee8`

## pseudocode

```c
void __fastcall IP_RESTRICTION_LIST_ENTRY::~IP_RESTRICTION_LIST_ENTRY(IP_RESTRICTION_LIST_ENTRY *this)
{
  STRU::~STRU((IP_RESTRICTION_LIST_ENTRY *)((char *)this + 72));
}

```

## disassembly

```asm
0x180002ee4  add     rcx, 48h ; 'H'
0x180002ee8  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
