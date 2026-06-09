# _UpdateTenantRestrictionsListTimerRoutine_::_1_::dtor$0

- ea: `0x180010ba6`
- end: `0x180010bb2`
- name: `_UpdateTenantRestrictionsListTimerRoutine_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180004518`

## pseudocode

```c
void __fastcall UpdateTenantRestrictionsListTimerRoutine_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  TenantRestrictionsLoggers::AutoMeasureLogger::~AutoMeasureLogger((TenantRestrictionsLoggers::AutoMeasureLogger *)(a2 + 64));
}

```

## disassembly

```asm
0x180010ba6  lea     rcx, [rdx+40h]; this
0x180010bad  jmp     ??1AutoMeasureLogger@TenantRestrictionsLoggers@@UEAA@XZ; TenantRestrictionsLoggers::AutoMeasureLogger::~AutoMeasureLogger(void)
```
