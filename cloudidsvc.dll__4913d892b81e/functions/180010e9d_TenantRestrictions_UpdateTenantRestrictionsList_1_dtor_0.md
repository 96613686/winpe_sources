# _TenantRestrictions::UpdateTenantRestrictionsList_::_1_::dtor$0

- ea: `0x180010e9d`
- end: `0x180010ea9`
- name: `_TenantRestrictions::UpdateTenantRestrictionsList_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180004518`

## pseudocode

```c
void __fastcall TenantRestrictions::UpdateTenantRestrictionsList_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  TenantRestrictionsLoggers::AutoMeasureLogger::~AutoMeasureLogger((TenantRestrictionsLoggers::AutoMeasureLogger *)(a2 + 240));
}

```

## disassembly

```asm
0x180010e9d  lea     rcx, [rdx+0F0h]; this
0x180010ea4  jmp     ??1AutoMeasureLogger@TenantRestrictionsLoggers@@UEAA@XZ; TenantRestrictionsLoggers::AutoMeasureLogger::~AutoMeasureLogger(void)
```
