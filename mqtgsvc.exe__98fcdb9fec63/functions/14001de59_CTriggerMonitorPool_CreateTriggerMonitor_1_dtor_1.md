# _CTriggerMonitorPool::CreateTriggerMonitor_::_1_::dtor$1

- ea: `0x14001de59`
- end: `0x14001de65`
- name: `_CTriggerMonitorPool::CreateTriggerMonitor_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000ab78`

## pseudocode

```c
__int64 __fastcall CTriggerMonitorPool::CreateTriggerMonitor_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return R<CTriggerMonitor>::~R<CTriggerMonitor>(a2 + 64);
}

```

## disassembly

```asm
0x14001de59  lea     rcx, [rdx+40h]
0x14001de60  jmp     ??1?$R@VCTriggerMonitor@@@@QEAA@XZ; R<CTriggerMonitor>::~R<CTriggerMonitor>(void)
```
