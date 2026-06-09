# _CClassFactory::CreateInstance_::_1_::dtor$12

- ea: `0x18001d0cd`
- end: `0x18001d0dd`
- name: `_CClassFactory::CreateInstance_::_1_::dtor$12`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008674`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance_::_1_::dtor_12(__int64 a1, __int64 a2)
{
  return ComPtr<IAepDevnode>::~ComPtr<IAepDevnode>((__int64 *)(*(_QWORD *)(a2 + 32) + 16LL));
}

```

## disassembly

```asm
0x18001d0cd  mov     rcx, [rdx+20h]
0x18001d0d4  add     rcx, 10h
0x18001d0d8  jmp     ??1?$ComPtr@UIAepDevnode@@@@QEAA@XZ; ComPtr<IAepDevnode>::~ComPtr<IAepDevnode>(void)
```
