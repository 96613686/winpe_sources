# _dynamic_atexit_destructor_for__g_TraceFileLock__

- ea: `0x1400072d0`
- end: `0x1400072f5`
- name: `_dynamic_atexit_destructor_for__g_TraceFileLock__`
- size: `37`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400072e9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400072e9`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_TraceFileLock__()
{
  g_TraceFileLock = &CSemExclusive::`vftable';
  DeleteCriticalSection(&stru_140010720);
}

```

## disassembly

```asm
0x1400072d0  sub     rsp, 28h
0x1400072d4  lea     rax, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x1400072db  mov     cs:?g_TraceFileLock@@3VCSemExclusive@@A, rax; CSemExclusive g_TraceFileLock
0x1400072e2  lea     rcx, stru_140010720; lpCriticalSection
0x1400072e9  call    cs:__imp_DeleteCriticalSection
0x1400072ef  nop
0x1400072f0  add     rsp, 28h
0x1400072f4  retn
```
