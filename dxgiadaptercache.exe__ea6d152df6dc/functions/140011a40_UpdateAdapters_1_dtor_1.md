# _UpdateAdapters_::_1_::dtor$1

- ea: `0x140011a40`
- end: `0x140011a4c`
- name: `_UpdateAdapters_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1400066ac`

## pseudocode

```c
void __fastcall UpdateAdapters_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  AdapterCacheUpdate::~AdapterCacheUpdate((AdapterCacheUpdate *)(a2 + 176));
}

```

## disassembly

```asm
0x140011a40  lea     rcx, [rdx+0B0h]; this
0x140011a47  jmp     ??1AdapterCacheUpdate@@QEAA@XZ; AdapterCacheUpdate::~AdapterCacheUpdate(void)
```
