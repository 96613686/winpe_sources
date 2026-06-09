# _DockCache::PairedDock_::_1_::dtor$1

- ea: `0x18001d221`
- end: `0x18001d22d`
- name: `_DockCache::PairedDock_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800112b4`

## pseudocode

```c
void __fastcall DockCache::PairedDock_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  Dock::~Dock((Dock *)(a2 + 96));
}

```

## disassembly

```asm
0x18001d221  lea     rcx, [rdx+60h]; this
0x18001d228  jmp     ??1Dock@@QEAA@XZ; Dock::~Dock(void)
```
