# _CWiGigDAFProviderQuery::ShouldUpdate_::_1_::dtor$0

- ea: `0x18001df38`
- end: `0x18001df44`
- name: `_CWiGigDAFProviderQuery::ShouldUpdate_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800184f8`

## pseudocode

```c
void __fastcall CWiGigDAFProviderQuery::ShouldUpdate_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  VisibleDock::~VisibleDock((VisibleDock *)(a2 + 96));
}

```

## disassembly

```asm
0x18001df38  lea     rcx, [rdx+60h]; this
0x18001df3f  jmp     ??1VisibleDock@@QEAA@XZ; VisibleDock::~VisibleDock(void)
```
