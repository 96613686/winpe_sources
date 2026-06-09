# _TenantRestrictions::UpdateTenantRestrictionsList_::_1_::dtor$9

- ea: `0x180010ef7`
- end: `0x180010f03`
- name: `_TenantRestrictions::UpdateTenantRestrictionsList_::_1_::dtor$9`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000a9b0`

## pseudocode

```c
void __fastcall TenantRestrictions::UpdateTenantRestrictionsList_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  TenantRestrictionsHelpers::TenantRestrictionsData::~TenantRestrictionsData((TenantRestrictionsHelpers::TenantRestrictionsData *)(a2 + 176));
}

```

## disassembly

```asm
0x180010ef7  lea     rcx, [rdx+0B0h]; this
0x180010efe  jmp     ??1TenantRestrictionsData@TenantRestrictionsHelpers@@QEAA@XZ; TenantRestrictionsHelpers::TenantRestrictionsData::~TenantRestrictionsData(void)
```
