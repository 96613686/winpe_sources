# _dynamic_atexit_destructor_for__Log::csList__

- ea: `0x14002fa00`
- end: `0x14002fa0e`
- name: `_dynamic_atexit_destructor_for__Log::csList__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14002fa07`

## pseudocode

```c
void dynamic_atexit_destructor_for__Log::csList__()
{
  DeleteCriticalSection(&Log::csList);
}

```

## disassembly

```asm
0x14002fa00  lea     rcx, ?csList@Log@@0VCCriticalSection@ATL@@A; ATL::CCriticalSection Log::csList
0x14002fa07  jmp     cs:__imp_DeleteCriticalSection
```
