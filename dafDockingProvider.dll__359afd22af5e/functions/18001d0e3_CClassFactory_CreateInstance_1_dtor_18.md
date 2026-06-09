# _CClassFactory::CreateInstance_::_1_::dtor$18

- ea: `0x18001d0e3`
- end: `0x18001d0f3`
- name: `_CClassFactory::CreateInstance_::_1_::dtor$18`
- size: `16`
- prototype: `unsigned int __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800086f0`

## pseudocode

```c
unsigned int __fastcall CClassFactory::CreateInstance_::_1_::dtor_18(__int64 a1, __int64 a2)
{
  return ComPtr<DockingProviders>::~ComPtr<DockingProviders>((DockingProviders **)(*(_QWORD *)(a2 + 32) + 16LL));
}

```

## disassembly

```asm
0x18001d0e3  mov     rcx, [rdx+20h]
0x18001d0ea  add     rcx, 10h
0x18001d0ee  jmp     ??1?$ComPtr@VDockingProviders@@@@QEAA@XZ; ComPtr<DockingProviders>::~ComPtr<DockingProviders>(void)
```
