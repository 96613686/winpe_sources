# _DockCache::LivenessUnknown_::_1_::dtor$1

- ea: `0x18001d413`
- end: `0x18001d41f`
- name: `_DockCache::LivenessUnknown_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800112b4`

## pseudocode

```c
void __fastcall DockCache::LivenessUnknown_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  Dock::~Dock((Dock *)(a2 + 112));
}

```

## disassembly

```asm
0x18001d413  lea     rcx, [rdx+70h]; this
0x18001d41a  jmp     ??1Dock@@QEAA@XZ; Dock::~Dock(void)
```
