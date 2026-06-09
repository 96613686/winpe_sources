# _AdapterCacheUpdate::AdapterCacheUpdate_::_1_::dtor$4

- ea: `0x1400115e4`
- end: `0x1400115f4`
- name: `_AdapterCacheUpdate::AdapterCacheUpdate_::_1_::dtor$4`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140006334`

## pseudocode

```c
__int64 __fastcall AdapterCacheUpdate::AdapterCacheUpdate_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(*(_QWORD *)(a2 + 176) + 72LL));
}

```

## disassembly

```asm
0x1400115e4  mov     rcx, [rdx+0B0h]
0x1400115eb  add     rcx, 48h ; 'H'
0x1400115ef  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
