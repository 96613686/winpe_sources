# _dynamic_atexit_destructor_for__g_semDumpOnce__

- ea: `0x1400071c0`
- end: `0x1400071e5`
- name: `_dynamic_atexit_destructor_for__g_semDumpOnce__`
- size: `37`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400071d9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400071d9`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_semDumpOnce__()
{
  qword_140010648 = &CSemExclusive::`vftable';
  DeleteCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x1400071c0  sub     rsp, 28h
0x1400071c4  lea     rax, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x1400071cb  mov     cs:qword_140010648, rax
0x1400071d2  lea     rcx, CriticalSection; lpCriticalSection
0x1400071d9  call    cs:__imp_DeleteCriticalSection
0x1400071df  nop
0x1400071e0  add     rsp, 28h
0x1400071e4  retn
```
