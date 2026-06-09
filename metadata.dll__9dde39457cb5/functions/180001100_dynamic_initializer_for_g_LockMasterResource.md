# _dynamic_initializer_for__g_LockMasterResource__

- ea: `0x180001100`
- end: `0x180001121`
- name: `_dynamic_initializer_for__g_LockMasterResource__`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008f84`

## import_xrefs

- `IisRTL!??0CReaderWriterLock3@@QEAA@XZ` at `0x18000110b`
- `IisRTL!??0CReaderWriterLock3@@QEAA@XZ` at `0x18000110b`

## pseudocode

```c
int dynamic_initializer_for__g_LockMasterResource__()
{
  CReaderWriterLock3::CReaderWriterLock3((CReaderWriterLock3 *)&g_LockMasterResource);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_LockMasterResource__);
}

```

## disassembly

```asm
0x180001100  sub     rsp, 28h
0x180001104  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18000110b  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x180001111  lea     rcx, _dynamic_atexit_destructor_for__g_LockMasterResource__
0x180001118  add     rsp, 28h
0x18000111c  jmp     atexit
```
