# _CEnhancedStorageActEnumerator::GetDiskDevicePnpPathFromVolumePath_::_1_::dtor$0

- ea: `0x18000ca57`
- end: `0x18000ca63`
- name: `_CEnhancedStorageActEnumerator::GetDiskDevicePnpPathFromVolumePath_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003ed0`

## pseudocode

```c
void __fastcall CEnhancedStorageActEnumerator::GetDiskDevicePnpPathFromVolumePath_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CESTTrackFn::~CESTTrackFn((CESTTrackFn *)(a2 + 208));
}

```

## disassembly

```asm
0x18000ca57  lea     rcx, [rdx+0D0h]; this
0x18000ca5e  jmp     ??1CESTTrackFn@@QEAA@XZ; CESTTrackFn::~CESTTrackFn(void)
```
