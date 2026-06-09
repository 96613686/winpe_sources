# _CClassFactory::CreateInstance_::_1_::dtor$7

- ea: `0x18001d069`
- end: `0x18001d07c`
- name: `_CClassFactory::CreateInstance_::_1_::dtor$7`
- size: `19`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008674`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  return ComPtr<IAepDevnode>::~ComPtr<IAepDevnode>((__int64 *)(*(_QWORD *)(a2 + 32) + 608LL));
}

```

## disassembly

```asm
0x18001d069  mov     rcx, [rdx+20h]
0x18001d070  add     rcx, 260h
0x18001d077  jmp     ??1?$ComPtr@UIAepDevnode@@@@QEAA@XZ; ComPtr<IAepDevnode>::~ComPtr<IAepDevnode>(void)
```
