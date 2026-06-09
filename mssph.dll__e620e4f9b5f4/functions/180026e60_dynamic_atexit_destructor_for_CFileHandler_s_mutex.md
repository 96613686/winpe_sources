# _dynamic_atexit_destructor_for__CFileHandler::s_mutex__

- ea: `0x180026e60`
- end: `0x180026e6e`
- name: `_dynamic_atexit_destructor_for__CFileHandler::s_mutex__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026e67`

## pseudocode

```c
void dynamic_atexit_destructor_for__CFileHandler::s_mutex__()
{
  DeleteCriticalSection(&CFileHandler::s_mutex);
}

```

## disassembly

```asm
0x180026e60  lea     rcx, ?s_mutex@CFileHandler@@0VCMutexSem@@A; CMutexSem CFileHandler::s_mutex
0x180026e67  jmp     cs:__imp_DeleteCriticalSection
```
