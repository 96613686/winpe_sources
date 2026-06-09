# _blue2th::Migrator::CanImpersonate_::_1_::dtor$0

- ea: `0x18001f24d`
- end: `0x18001f259`
- name: `_blue2th::Migrator::CanImpersonate_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180007720`

## pseudocode

```c
void __fastcall blue2th::Migrator::CanImpersonate_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  std::wstring::~wstring((char **)(a2 + 56));
}

```

## disassembly

```asm
0x18001f24d  lea     rcx, [rdx+38h]; void *
0x18001f254  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
