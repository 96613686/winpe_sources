# _CDimsJobTaskHandler::Start_::_1_::dtor$0

- ea: `0x18000af30`
- end: `0x18000af3c`
- name: `_CDimsJobTaskHandler::Start_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180002e50`

## pseudocode

```c
__int64 __fastcall CDimsJobTaskHandler::Start_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return CAutoLock<_CWriter>::~CAutoLock<_CWriter>(a2 + 48);
}

```

## disassembly

```asm
0x18000af30  lea     rcx, [rdx+30h]
0x18000af37  jmp     ??1?$CAutoLock@U_CWriter@@@@QEAA@XZ; CAutoLock<_CWriter>::~CAutoLock<_CWriter>(void)
```
