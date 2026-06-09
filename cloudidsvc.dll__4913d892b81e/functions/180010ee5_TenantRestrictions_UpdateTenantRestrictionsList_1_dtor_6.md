# _TenantRestrictions::UpdateTenantRestrictionsList_::_1_::dtor$6

- ea: `0x180010ee5`
- end: `0x180010ef1`
- name: `_TenantRestrictions::UpdateTenantRestrictionsList_::_1_::dtor$6`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000a9b0`

## pseudocode

```c
void __fastcall TenantRestrictions::UpdateTenantRestrictionsList_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  TenantRestrictionsHelpers::TenantRestrictionsData::~TenantRestrictionsData((TenantRestrictionsHelpers::TenantRestrictionsData *)(a2 + 64));
}

```

## disassembly

```asm
0x180010ee5  lea     rcx, [rdx+40h]; this
0x180010eec  jmp     ??1TenantRestrictionsData@TenantRestrictionsHelpers@@QEAA@XZ; TenantRestrictionsHelpers::TenantRestrictionsData::~TenantRestrictionsData(void)
```
