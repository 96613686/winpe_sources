# _dynamic_atexit_destructor_for__g_semDumpOnce__

- ea: `0x180014470`
- end: `0x180014495`
- name: `_dynamic_atexit_destructor_for__g_semDumpOnce__`
- size: `37`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014489`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014489`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_semDumpOnce__()
{
  qword_18001F908 = &CSemExclusive::`vftable';
  DeleteCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x180014470  sub     rsp, 28h
0x180014474  lea     rax, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x18001447b  mov     cs:qword_18001F908, rax
0x180014482  lea     rcx, CriticalSection; lpCriticalSection
0x180014489  call    cs:__imp_DeleteCriticalSection
0x18001448f  nop
0x180014490  add     rsp, 28h
0x180014494  retn
```
