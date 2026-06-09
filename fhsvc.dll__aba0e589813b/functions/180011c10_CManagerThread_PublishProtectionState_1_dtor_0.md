# _CManagerThread::PublishProtectionState_::_1_::dtor$0

- ea: `0x180011c10`
- end: `0x180011c1c`
- name: `_CManagerThread::PublishProtectionState_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000b5f8`

## pseudocode

```c
__int64 __fastcall CManagerThread::PublishProtectionState_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return SmartPtr<CConfigDescriptor>::~SmartPtr<CConfigDescriptor>(*(__int64 **)(a2 + 80));
}

```

## disassembly

```asm
0x180011c10  mov     rcx, [rdx+50h]
0x180011c17  jmp     ??1?$SmartPtr@VCConfigDescriptor@@@@QEAA@XZ; SmartPtr<CConfigDescriptor>::~SmartPtr<CConfigDescriptor>(void)
```
