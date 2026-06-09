# _AdapterCacheUpdate::UpdateGlobalFeatureLevelInfo_::_1_::dtor$0

- ea: `0x140011a9a`
- end: `0x140011aa6`
- name: `_AdapterCacheUpdate::UpdateGlobalFeatureLevelInfo_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140006334`

## pseudocode

```c
__int64 __fastcall AdapterCacheUpdate::UpdateGlobalFeatureLevelInfo_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 560));
}

```

## disassembly

```asm
0x140011a9a  lea     rcx, [rdx+230h]
0x140011aa1  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
