# _CClassFactory::CreateInstance_::_1_::dtor$8

- ea: `0x18001d082`
- end: `0x18001d095`
- name: `_CClassFactory::CreateInstance_::_1_::dtor$8`
- size: `19`
- prototype: `unsigned int __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800086f0`

## pseudocode

```c
unsigned int __fastcall CClassFactory::CreateInstance_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  return ComPtr<DockingProviders>::~ComPtr<DockingProviders>((DockingProviders **)(*(_QWORD *)(a2 + 32) + 616LL));
}

```

## disassembly

```asm
0x18001d082  mov     rcx, [rdx+20h]
0x18001d089  add     rcx, 268h
0x18001d090  jmp     ??1?$ComPtr@VDockingProviders@@@@QEAA@XZ; ComPtr<DockingProviders>::~ComPtr<DockingProviders>(void)
```
