# _CEnhancedStorageSilo::CreateClientInformation_::_1_::dtor$0

- ea: `0x18000caed`
- end: `0x18000caf9`
- name: `_CEnhancedStorageSilo::CreateClientInformation_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003ed0`

## pseudocode

```c
void __fastcall CEnhancedStorageSilo::CreateClientInformation_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CESTTrackFn::~CESTTrackFn((CESTTrackFn *)(a2 + 96));
}

```

## disassembly

```asm
0x18000caed  lea     rcx, [rdx+60h]; this
0x18000caf4  jmp     ??1CESTTrackFn@@QEAA@XZ; CESTTrackFn::~CESTTrackFn(void)
```
