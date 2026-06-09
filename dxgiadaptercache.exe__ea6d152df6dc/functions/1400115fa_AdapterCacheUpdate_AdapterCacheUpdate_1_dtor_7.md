# _AdapterCacheUpdate::AdapterCacheUpdate_::_1_::dtor$7

- ea: `0x1400115fa`
- end: `0x140011606`
- name: `_AdapterCacheUpdate::AdapterCacheUpdate_::_1_::dtor$7`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140006700`

## pseudocode

```c
void __fastcall AdapterCacheUpdate::AdapterCacheUpdate_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  CachedAdapterInformation::~CachedAdapterInformation((char **)(a2 + 224));
}

```

## disassembly

```asm
0x1400115fa  lea     rcx, [rdx+0E0h]; this
0x140011601  jmp     ??1CachedAdapterInformation@@QEAA@XZ; CachedAdapterInformation::~CachedAdapterInformation(void)
```
