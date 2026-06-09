# _AdapterCacheUpdate::UpdateGlobalFeatureLevelInfo_::_1_::dtor$1

- ea: `0x140011aac`
- end: `0x140011ab8`
- name: `_AdapterCacheUpdate::UpdateGlobalFeatureLevelInfo_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x14000658c`

## pseudocode

```c
__int64 __fastcall AdapterCacheUpdate::UpdateGlobalFeatureLevelInfo_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return wil::unique_call<void (*)(void),&void CoUninitialize(void),1>::~unique_call<void (*)(void),&void CoUninitialize(void),1>(a2 + 160);
}

```

## disassembly

```asm
0x140011aac  lea     rcx, [rdx+0A0h]
0x140011ab3  jmp     ??1?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@wil@@QEAA@XZ; wil::unique_call<void (*)(void),&CoUninitialize(void),1>::~unique_call<void (*)(void),&CoUninitialize(void),1>(void)
```
