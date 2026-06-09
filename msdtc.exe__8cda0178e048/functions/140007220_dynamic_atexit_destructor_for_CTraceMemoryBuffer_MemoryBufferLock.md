# _dynamic_atexit_destructor_for__CTraceMemoryBuffer::MemoryBufferLock__

- ea: `0x140007220`
- end: `0x140007245`
- name: `_dynamic_atexit_destructor_for__CTraceMemoryBuffer::MemoryBufferLock__`
- size: `37`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140007239`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140007239`

## pseudocode

```c
void dynamic_atexit_destructor_for__CTraceMemoryBuffer::MemoryBufferLock__()
{
  CTraceMemoryBuffer::MemoryBufferLock = &CSemExclusive::`vftable';
  DeleteCriticalSection(&stru_140010758);
}

```

## disassembly

```asm
0x140007220  sub     rsp, 28h
0x140007224  lea     rax, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x14000722b  mov     cs:?MemoryBufferLock@CTraceMemoryBuffer@@0VCSemExclusive@@A, rax; CSemExclusive CTraceMemoryBuffer::MemoryBufferLock
0x140007232  lea     rcx, stru_140010758; lpCriticalSection
0x140007239  call    cs:__imp_DeleteCriticalSection
0x14000723f  nop
0x140007240  add     rsp, 28h
0x140007244  retn
```
