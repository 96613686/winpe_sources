# __dynamic_initializer_for__g_serviceCallbacks___::_1_::dtor$0

- ea: `0x18000cbd3`
- end: `0x18000cbe3`
- name: `__dynamic_initializer_for__g_serviceCallbacks___::_1_::dtor$0`
- size: `16`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a3d4`

## pseudocode

```c
void _dynamic_initializer_for__g_serviceCallbacks___::_1_::dtor_0()
{
  Microsoft::WRL::Wrappers::CriticalSection::~CriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x18000cbd3  lea     rcx, off_1800180A0
0x18000cbda  add     rcx, 10h; lpCriticalSection
0x18000cbde  jmp     ??1CriticalSection@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::CriticalSection::~CriticalSection(void)
```
