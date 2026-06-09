# _CClassFactory::CreateInstance_::_1_::dtor$0

- ea: `0x18001d019`
- end: `0x18001d025`
- name: `_CClassFactory::CreateInstance_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008674`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ComPtr<IAepDevnode>::~ComPtr<IAepDevnode>((__int64 *)(a2 + 168));
}

```

## disassembly

```asm
0x18001d019  lea     rcx, [rdx+0A8h]
0x18001d020  jmp     ??1?$ComPtr@UIAepDevnode@@@@QEAA@XZ; ComPtr<IAepDevnode>::~ComPtr<IAepDevnode>(void)
```
