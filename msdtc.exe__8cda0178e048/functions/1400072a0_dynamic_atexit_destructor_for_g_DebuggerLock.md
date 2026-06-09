# _dynamic_atexit_destructor_for__g_DebuggerLock__

- ea: `0x1400072a0`
- end: `0x1400072c5`
- name: `_dynamic_atexit_destructor_for__g_DebuggerLock__`
- size: `37`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400072b9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400072b9`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_DebuggerLock__()
{
  g_DebuggerLock = &CSemExclusive::`vftable';
  DeleteCriticalSection(&stru_1400106E8);
}

```

## disassembly

```asm
0x1400072a0  sub     rsp, 28h
0x1400072a4  lea     rax, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x1400072ab  mov     cs:?g_DebuggerLock@@3VCSemExclusive@@A, rax; CSemExclusive g_DebuggerLock
0x1400072b2  lea     rcx, stru_1400106E8; lpCriticalSection
0x1400072b9  call    cs:__imp_DeleteCriticalSection
0x1400072bf  nop
0x1400072c0  add     rsp, 28h
0x1400072c4  retn
```
