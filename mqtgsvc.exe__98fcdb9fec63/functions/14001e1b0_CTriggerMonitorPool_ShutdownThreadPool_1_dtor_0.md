# _CTriggerMonitorPool::ShutdownThreadPool_::_1_::dtor$0

- ea: `0x14001e1b0`
- end: `0x14001e1bc`
- name: `_CTriggerMonitorPool::ShutdownThreadPool_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140005f00`

## pseudocode

```c
void __fastcall CTriggerMonitorPool::ShutdownThreadPool_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CS::~CS((CS *)(a2 + 48));
}

```

## disassembly

```asm
0x14001e1b0  lea     rcx, [rdx+30h]; this
0x14001e1b7  jmp     ??1CS@@QEAA@XZ; CS::~CS(void)
```
