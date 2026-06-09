# _dynamic_atexit_destructor_for__g_DebuggerLock__

- ea: `0x180014550`
- end: `0x180014575`
- name: `_dynamic_atexit_destructor_for__g_DebuggerLock__`
- size: `37`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014569`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014569`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_DebuggerLock__()
{
  g_DebuggerLock = &CSemExclusive::`vftable';
  DeleteCriticalSection(&stru_18001F9A0);
}

```

## disassembly

```asm
0x180014550  sub     rsp, 28h
0x180014554  lea     rax, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x18001455b  mov     cs:?g_DebuggerLock@@3VCSemExclusive@@A, rax; CSemExclusive g_DebuggerLock
0x180014562  lea     rcx, stru_18001F9A0; lpCriticalSection
0x180014569  call    cs:__imp_DeleteCriticalSection
0x18001456f  nop
0x180014570  add     rsp, 28h
0x180014574  retn
```
