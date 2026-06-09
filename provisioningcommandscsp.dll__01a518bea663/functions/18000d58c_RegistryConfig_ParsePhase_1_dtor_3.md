# _RegistryConfig::ParsePhase_::_1_::dtor$3

- ea: `0x18000d58c`
- end: `0x18000d598`
- name: `_RegistryConfig::ParsePhase_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a010`

## pseudocode

```c
void __fastcall RegistryConfig::ParsePhase_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  CommandSet::~CommandSet((CommandSet *)(a2 + 160));
}

```

## disassembly

```asm
0x18000d58c  lea     rcx, [rdx+0A0h]; this
0x18000d593  jmp     ??1CommandSet@@QEAA@XZ; CommandSet::~CommandSet(void)
```
