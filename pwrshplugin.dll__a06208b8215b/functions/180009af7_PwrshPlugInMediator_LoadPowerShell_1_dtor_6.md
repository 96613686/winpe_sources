# _PwrshPlugInMediator::LoadPowerShell_::_1_::dtor$6

- ea: `0x180009af7`
- end: `0x180009b03`
- name: `_PwrshPlugInMediator::LoadPowerShell_::_1_::dtor$6`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800051c8`

## pseudocode

```c
__int64 __fastcall PwrshPlugInMediator::LoadPowerShell_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 192);
}

```

## disassembly

```asm
0x180009af7  lea     rcx, [rdx+0C0h]
0x180009afe  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
