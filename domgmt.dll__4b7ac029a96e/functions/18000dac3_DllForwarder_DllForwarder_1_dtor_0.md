# _DllForwarder::DllForwarder_::_1_::dtor$0

- ea: `0x18000dac3`
- end: `0x18000dacf`
- name: `_DllForwarder::DllForwarder_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008e50`

## pseudocode

```c
__int64 __fastcall DllForwarder::DllForwarder_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::unique_ptr<uus::Session>::~unique_ptr<uus::Session>(*(__int64 (__fastcall *****)(_QWORD, __int64))(a2 + 32));
}

```

## disassembly

```asm
0x18000dac3  mov     rcx, [rdx+20h]
0x18000daca  jmp     ??1?$unique_ptr@USession@uus@@U?$default_delete@USession@uus@@@std@@@std@@QEAA@XZ; std::unique_ptr<uus::Session>::~unique_ptr<uus::Session>(void)
```
