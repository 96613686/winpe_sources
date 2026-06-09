# _D3D12CreateDeviceImpl_::_1_::dtor$0

- ea: `0x180013d94`
- end: `0x180013da0`
- name: `_D3D12CreateDeviceImpl_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000953c`

## pseudocode

```c
__int64 __fastcall D3D12CreateDeviceImpl_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(a2 + 64);
}

```

## disassembly

```asm
0x180013d94  lea     rcx, [rdx+40h]
0x180013d9b  jmp     ??1?$shared_lock@Vshared_mutex@std@@@std@@QEAA@XZ; std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(void)
```
