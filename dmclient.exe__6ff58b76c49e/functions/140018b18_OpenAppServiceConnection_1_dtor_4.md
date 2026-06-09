# _OpenAppServiceConnection_::_1_::dtor$4

- ea: `0x140018b18`
- end: `0x140018b24`
- name: `_OpenAppServiceConnection_::_1_::dtor$4`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140004810`

## pseudocode

```c
void __fastcall OpenAppServiceConnection_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 136));
}

```

## disassembly

```asm
0x140018b18  lea     rcx, [rdx+88h]; this
0x140018b1f  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
