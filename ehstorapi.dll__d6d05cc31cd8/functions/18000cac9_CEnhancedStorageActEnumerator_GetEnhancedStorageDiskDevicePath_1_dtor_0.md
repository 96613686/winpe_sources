# _CEnhancedStorageActEnumerator::GetEnhancedStorageDiskDevicePath_::_1_::dtor$0

- ea: `0x18000cac9`
- end: `0x18000cad5`
- name: `_CEnhancedStorageActEnumerator::GetEnhancedStorageDiskDevicePath_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003e58`

## pseudocode

```c
__int64 __fastcall CEnhancedStorageActEnumerator::GetEnhancedStorageDiskDevicePath_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return ATL::CAtlArray<DeviceData,ATL::CElementTraits<DeviceData>>::~CAtlArray<DeviceData,ATL::CElementTraits<DeviceData>>(a2 + 80);
}

```

## disassembly

```asm
0x18000cac9  lea     rcx, [rdx+50h]
0x18000cad0  jmp     ??1?$CAtlArray@VDeviceData@@V?$CElementTraits@VDeviceData@@@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<DeviceData,ATL::CElementTraits<DeviceData>>::~CAtlArray<DeviceData,ATL::CElementTraits<DeviceData>>(void)
```
