# _CEnhancedStorageSilo::InvokeExternalCommand_::_1_::dtor$1

- ea: `0x18000cc8d`
- end: `0x18000cc99`
- name: `_CEnhancedStorageSilo::InvokeExternalCommand_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003ed0`

## pseudocode

```c
void __fastcall CEnhancedStorageSilo::InvokeExternalCommand_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CESTTrackFn::~CESTTrackFn((CESTTrackFn *)(a2 + 272));
}

```

## disassembly

```asm
0x18000cc8d  lea     rcx, [rdx+110h]; this
0x18000cc94  jmp     ??1CESTTrackFn@@QEAA@XZ; CESTTrackFn::~CESTTrackFn(void)
```
