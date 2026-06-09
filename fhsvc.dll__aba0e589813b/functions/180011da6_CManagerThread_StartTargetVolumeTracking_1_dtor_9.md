# _CManagerThread::StartTargetVolumeTracking_::_1_::dtor$9

- ea: `0x180011da6`
- end: `0x180011db2`
- name: `_CManagerThread::StartTargetVolumeTracking_::_1_::dtor$9`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000be90`

## pseudocode

```c
__int64 __fastcall CManagerThread::StartTargetVolumeTracking_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  return SmartPtr<CVolumeTrackingDescriptor>::~SmartPtr<CVolumeTrackingDescriptor>((_QWORD *)(a2 + 64));
}

```

## disassembly

```asm
0x180011da6  lea     rcx, [rdx+40h]
0x180011dad  jmp     ??1?$SmartPtr@VCVolumeTrackingDescriptor@@@@QEAA@XZ; SmartPtr<CVolumeTrackingDescriptor>::~SmartPtr<CVolumeTrackingDescriptor>(void)
```
