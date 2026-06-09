# _std::list_CDockInterface::Listener_std::allocator_CDockInterface::Listener___::remove_::_1_::dtor$1

- ea: `0x18001e35b`
- end: `0x18001e367`
- name: `_std::list_CDockInterface::Listener_std::allocator_CDockInterface::Listener___::remove_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008674`

## pseudocode

```c
__int64 __fastcall std::list_CDockInterface::Listener_std::allocator_CDockInterface::Listener___::remove_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  return ComPtr<IAepDevnode>::~ComPtr<IAepDevnode>((__int64 *)(a2 + 64));
}

```

## disassembly

```asm
0x18001e35b  lea     rcx, [rdx+40h]
0x18001e362  jmp     ??1?$ComPtr@UIAepDevnode@@@@QEAA@XZ; ComPtr<IAepDevnode>::~ComPtr<IAepDevnode>(void)
```
