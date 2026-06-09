# __dynamic_initializer_for__Dfdll::CSubscription::_criticalSection___::_1_::dtor$0

- ea: `0x18001f212`
- end: `0x18001f21e`
- name: `__dynamic_initializer_for__Dfdll::CSubscription::_criticalSection___::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008fd0`

## pseudocode

```c
void _dynamic_initializer_for__Dfdll::CSubscription::_criticalSection___::_1_::dtor_0()
{
  Dfdll::CSynchronizationObject::~CSynchronizationObject((Dfdll::CSynchronizationObject *)&Dfdll::CSubscription::_criticalSection);
}

```

## disassembly

```asm
0x18001f212  lea     rcx, ?_criticalSection@CSubscription@Dfdll@@1VCCriticialSection@2@A; this
0x18001f219  jmp     ??1CSynchronizationObject@Dfdll@@UEAA@XZ
```
