# _CEnhancedStorageActEnumerator::GetEnhancedStorageDiskDevicePath_::_1_::dtor$1

- ea: `0x18000cadb`
- end: `0x18000cae7`
- name: `_CEnhancedStorageActEnumerator::GetEnhancedStorageDiskDevicePath_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003ed0`

## pseudocode

```c
void __fastcall CEnhancedStorageActEnumerator::GetEnhancedStorageDiskDevicePath_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CESTTrackFn::~CESTTrackFn((CESTTrackFn *)(a2 + 224));
}

```

## disassembly

```asm
0x18000cadb  lea     rcx, [rdx+0E0h]; this
0x18000cae2  jmp     ??1CESTTrackFn@@QEAA@XZ; CESTTrackFn::~CESTTrackFn(void)
```
