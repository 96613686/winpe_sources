# _Microsoft::HostGuardian::Client::HgService::HgService_::_1_::dtor$0

- ea: `0x180015880`
- end: `0x18001588c`
- name: `_Microsoft::HostGuardian::Client::HgService::HgService_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004274`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgService::HgService_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(*(char ***)(a2 + 104));
}

```

## disassembly

```asm
0x180015880  mov     rcx, [rdx+68h]
0x180015887  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
