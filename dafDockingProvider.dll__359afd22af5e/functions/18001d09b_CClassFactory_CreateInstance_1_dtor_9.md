# _CClassFactory::CreateInstance_::_1_::dtor$9

- ea: `0x18001d09b`
- end: `0x18001d0ae`
- name: `_CClassFactory::CreateInstance_::_1_::dtor$9`
- size: `19`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800086a4`

## pseudocode

```c
void __fastcall CClassFactory::CreateInstance_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  ComPtr<DockCache>::~ComPtr<DockCache>((volatile signed __int32 **)(*(_QWORD *)(a2 + 32) + 624LL));
}

```

## disassembly

```asm
0x18001d09b  mov     rcx, [rdx+20h]
0x18001d0a2  add     rcx, 270h
0x18001d0a9  jmp     ??1?$ComPtr@VDockCache@@@@QEAA@XZ; ComPtr<DockCache>::~ComPtr<DockCache>(void)
```
