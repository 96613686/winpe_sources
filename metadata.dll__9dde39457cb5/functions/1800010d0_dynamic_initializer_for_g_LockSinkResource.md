# _dynamic_initializer_for__g_LockSinkResource__

- ea: `0x1800010d0`
- end: `0x1800010f1`
- name: `_dynamic_initializer_for__g_LockSinkResource__`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008f84`

## import_xrefs

- `IisRTL!??0CReaderWriterLock3@@QEAA@XZ` at `0x1800010db`
- `IisRTL!??0CReaderWriterLock3@@QEAA@XZ` at `0x1800010db`

## pseudocode

```c
int dynamic_initializer_for__g_LockSinkResource__()
{
  CReaderWriterLock3::CReaderWriterLock3((CReaderWriterLock3 *)&g_LockSinkResource);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_LockSinkResource__);
}

```

## disassembly

```asm
0x1800010d0  sub     rsp, 28h
0x1800010d4  lea     rcx, ?g_LockSinkResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockSinkResource
0x1800010db  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x1800010e1  lea     rcx, _dynamic_atexit_destructor_for__g_LockSinkResource__
0x1800010e8  add     rsp, 28h
0x1800010ec  jmp     atexit
```
