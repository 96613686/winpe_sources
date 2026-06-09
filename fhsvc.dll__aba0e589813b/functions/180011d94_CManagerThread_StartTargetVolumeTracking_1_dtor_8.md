# _CManagerThread::StartTargetVolumeTracking_::_1_::dtor$8

- ea: `0x180011d94`
- end: `0x180011da0`
- name: `_CManagerThread::StartTargetVolumeTracking_::_1_::dtor$8`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180009ab8`

## pseudocode

```c
void __fastcall CManagerThread::StartTargetVolumeTracking_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  CCriticalResource::~CCriticalResource((CCriticalResource *)(a2 + 120));
}

```

## disassembly

```asm
0x180011d94  lea     rcx, [rdx+78h]; this
0x180011d9b  jmp     ??1CCriticalResource@@QEAA@XZ; CCriticalResource::~CCriticalResource(void)
```
