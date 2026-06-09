# CsvtaskHandler::Worker(void)

- ea: `0x180002530`
- end: `0x18000254e`
- name: `?Worker@CsvtaskHandler@@EEAAJXZ`
- size: `30`
- prototype: `__int64 __fastcall(CsvtaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001e98`
- `0x180002530`

## pseudocode

```c
__int64 __fastcall CsvtaskHandler::Worker(CsvtaskHandler *this)
{
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 9, 1, 1) != 1 )
    CsvtaskHandler::FindAndScan(this);
  return 0;
}

```

## disassembly

```asm
0x180002530  sub     rsp, 28h
0x180002534  mov     edx, 1
0x180002539  mov     eax, edx
0x18000253b  lock cmpxchg [rcx+24h], edx
0x180002540  jz      short loc_180002547
0x180002542  call    ?FindAndScan@CsvtaskHandler@@AEAAXXZ; CsvtaskHandler::FindAndScan(void)
0x180002547  xor     eax, eax
0x180002549  add     rsp, 28h
0x18000254d  retn
```
