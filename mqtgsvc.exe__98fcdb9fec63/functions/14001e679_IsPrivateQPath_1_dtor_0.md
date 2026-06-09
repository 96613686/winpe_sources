# _IsPrivateQPath_::_1_::dtor$0

- ea: `0x14001e679`
- end: `0x14001e685`
- name: `_IsPrivateQPath_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003c10`

## pseudocode

```c
__int64 __fastcall IsPrivateQPath_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(*(_QWORD *)(a2 + 40));
}

```

## disassembly

```asm
0x14001e679  mov     rcx, [rdx+28h]
0x14001e680  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
