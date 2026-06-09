# _AdapterCacheUpdate::AdapterCacheUpdate_::_1_::dtor$3

- ea: `0x1400115ce`
- end: `0x1400115de`
- name: `_AdapterCacheUpdate::AdapterCacheUpdate_::_1_::dtor$3`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140006640`

## pseudocode

```c
__int64 __fastcall AdapterCacheUpdate::AdapterCacheUpdate_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return std::vector<unsigned char>::~vector<unsigned char>(*(_QWORD *)(a2 + 176) + 48LL);
}

```

## disassembly

```asm
0x1400115ce  mov     rcx, [rdx+0B0h]
0x1400115d5  add     rcx, 30h ; '0'
0x1400115d9  jmp     ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
```
