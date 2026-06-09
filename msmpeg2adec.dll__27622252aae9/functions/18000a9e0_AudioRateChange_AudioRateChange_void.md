# AudioRateChange::~AudioRateChange(void)

- ea: `0x18000a9e0`
- end: `0x18000a9eb`
- name: `??1AudioRateChange@@QEAA@XZ`
- size: `11`
- prototype: `void __fastcall(AudioRateChange *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180088890`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a9e4`

## pseudocode

```c
void __fastcall AudioRateChange::~AudioRateChange(AudioRateChange *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x18000a9e0  add     rcx, 8
0x18000a9e4  jmp     cs:__imp_DeleteCriticalSection
```
