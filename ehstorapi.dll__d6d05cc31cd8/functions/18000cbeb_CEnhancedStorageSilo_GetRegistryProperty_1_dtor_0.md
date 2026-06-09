# _CEnhancedStorageSilo::GetRegistryProperty_::_1_::dtor$0

- ea: `0x18000cbeb`
- end: `0x18000cbf7`
- name: `_CEnhancedStorageSilo::GetRegistryProperty_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180003ed0`

## pseudocode

```c
void __fastcall CEnhancedStorageSilo::GetRegistryProperty_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CESTTrackFn::~CESTTrackFn((CESTTrackFn *)(a2 + 144));
}

```

## disassembly

```asm
0x18000cbeb  lea     rcx, [rdx+90h]; this
0x18000cbf2  jmp     ??1CESTTrackFn@@QEAA@XZ; CESTTrackFn::~CESTTrackFn(void)
```
