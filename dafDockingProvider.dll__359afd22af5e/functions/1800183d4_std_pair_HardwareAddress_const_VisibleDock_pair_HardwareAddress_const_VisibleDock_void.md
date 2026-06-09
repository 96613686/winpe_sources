# std::pair<HardwareAddress const,VisibleDock>::~pair<HardwareAddress const,VisibleDock>(void)

- ea: `0x1800183d4`
- end: `0x1800183dd`
- name: `??1?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@QEAA@XZ`
- size: `9`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001dd11`

## callees

- `0x1800184f8`

## pseudocode

```c
void __fastcall std::pair<HardwareAddress const,VisibleDock>::~pair<HardwareAddress const,VisibleDock>(__int64 a1)
{
  VisibleDock::~VisibleDock((VisibleDock *)(a1 + 16));
}

```

## disassembly

```asm
0x1800183d4  add     rcx, 10h; this
0x1800183d8  jmp     ??1VisibleDock@@QEAA@XZ; VisibleDock::~VisibleDock(void)
```
