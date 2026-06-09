# _IMSMQTriggersConfig::GetTriggerStoreMachineName_::_1_::dtor$1

- ea: `0x14001e54c`
- end: `0x14001e558`
- name: `_IMSMQTriggersConfig::GetTriggerStoreMachineName_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callees

- `0x140002e1c`

## pseudocode

```c
void __fastcall IMSMQTriggersConfig::GetTriggerStoreMachineName_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 80));
}

```

## disassembly

```asm
0x14001e54c  mov     rcx, [rdx+50h]; void *
0x14001e553  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
