# _MigrateWmiAppInstallJob_::_1_::dtor$2

- ea: `0x18001f686`
- end: `0x18001f692`
- name: `_MigrateWmiAppInstallJob_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180007720`

## pseudocode

```c
void __fastcall MigrateWmiAppInstallJob_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  std::wstring::~wstring((char **)(a2 + 144));
}

```

## disassembly

```asm
0x18001f686  lea     rcx, [rdx+90h]; void *
0x18001f68d  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
