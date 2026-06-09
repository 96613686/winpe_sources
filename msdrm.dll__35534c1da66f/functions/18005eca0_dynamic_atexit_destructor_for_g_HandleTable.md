# _dynamic_atexit_destructor_for__g_HandleTable__

- ea: `0x18005eca0`
- end: `0x18005ecc1`
- name: `_dynamic_atexit_destructor_for__g_HandleTable__`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800191e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005ecab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005ecab`

## pseudocode

```c
__int64 dynamic_atexit_destructor_for__g_HandleTable__()
{
  DeleteCriticalSection(&CriticalSection);
  return CPubSet<DRMCInt>::~CPubSet<DRMCInt>(&g_HandleTable);
}

```

## disassembly

```asm
0x18005eca0  sub     rsp, 28h
0x18005eca4  lea     rcx, CriticalSection; lpCriticalSection
0x18005ecab  call    cs:__imp_DeleteCriticalSection
0x18005ecb1  lea     rcx, ?g_HandleTable@@3VCHandleTable@@A; CHandleTable g_HandleTable
0x18005ecb8  add     rsp, 28h
0x18005ecbc  jmp     ??1?$CPubSet@UDRMCInt@@@@QEAA@XZ; CPubSet<DRMCInt>::~CPubSet<DRMCInt>(void)
```
