# _GetWmiKeysFromRegistry_::_1_::dtor$1

- ea: `0x18001f5c1`
- end: `0x18001f5cd`
- name: `_GetWmiKeysFromRegistry_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180007720`

## pseudocode

```c
void __fastcall GetWmiKeysFromRegistry_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  std::wstring::~wstring((char **)(a2 + 80));
}

```

## disassembly

```asm
0x18001f5c1  lea     rcx, [rdx+50h]; void *
0x18001f5c8  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
