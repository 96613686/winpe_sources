# _PEvtInitService_::_1_::dtor$9

- ea: `0x180013fe8`
- end: `0x180013ff4`
- name: `_PEvtInitService_::_1_::dtor$9`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180008b44`

## pseudocode

```c
__int64 __fastcall PEvtInitService_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  return std::vector<bool>::~vector<bool>(a2 + 32);
}

```

## disassembly

```asm
0x180013fe8  lea     rcx, [rdx+20h]
0x180013fef  jmp     ??1?$vector@_NV?$allocator@_N@std@@@std@@QEAA@XZ; std::vector<bool>::~vector<bool>(void)
```
