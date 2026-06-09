# _ServiceManager_IsAnyOperationPending_::_1_::dtor$0

- ea: `0x18000cc33`
- end: `0x18000cc3f`
- name: `_ServiceManager_IsAnyOperationPending_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000a348`

## pseudocode

```c
__int64 __fastcall ServiceManager_IsAnyOperationPending_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 40));
}

```

## disassembly

```asm
0x18000cc33  lea     rcx, [rdx+28h]
0x18000cc3a  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
