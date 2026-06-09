# _dynamic_atexit_destructor_for__Discovery::s_CriticalSection__

- ea: `0x14002fa40`
- end: `0x14002fa4e`
- name: `_dynamic_atexit_destructor_for__Discovery::s_CriticalSection__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14002fa47`

## pseudocode

```c
void dynamic_atexit_destructor_for__Discovery::s_CriticalSection__()
{
  DeleteCriticalSection(&Discovery::s_CriticalSection);
}

```

## disassembly

```asm
0x14002fa40  lea     rcx, ?s_CriticalSection@Discovery@@0VCCriticalSection@ATL@@A; ATL::CCriticalSection Discovery::s_CriticalSection
0x14002fa47  jmp     cs:__imp_DeleteCriticalSection
```
