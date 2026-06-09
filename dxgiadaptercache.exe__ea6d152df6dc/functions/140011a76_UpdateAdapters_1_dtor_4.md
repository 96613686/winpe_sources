# _UpdateAdapters_::_1_::dtor$4

- ea: `0x140011a76`
- end: `0x140011a82`
- name: `_UpdateAdapters_::_1_::dtor$4`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140006700`

## pseudocode

```c
void __fastcall UpdateAdapters_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  CachedAdapterInformation::~CachedAdapterInformation((char **)(a2 + 288));
}

```

## disassembly

```asm
0x140011a76  lea     rcx, [rdx+120h]; this
0x140011a7d  jmp     ??1CachedAdapterInformation@@QEAA@XZ; CachedAdapterInformation::~CachedAdapterInformation(void)
```
