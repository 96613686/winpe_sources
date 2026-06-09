# _CClassFactory::CreateInstance_::_1_::dtor$6

- ea: `0x18001d050`
- end: `0x18001d063`
- name: `_CClassFactory::CreateInstance_::_1_::dtor$6`
- size: `19`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008674`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  return ComPtr<IAepDevnode>::~ComPtr<IAepDevnode>((__int64 *)(*(_QWORD *)(a2 + 32) + 600LL));
}

```

## disassembly

```asm
0x18001d050  mov     rcx, [rdx+20h]
0x18001d057  add     rcx, 258h
0x18001d05e  jmp     ??1?$ComPtr@UIAepDevnode@@@@QEAA@XZ; ComPtr<IAepDevnode>::~ComPtr<IAepDevnode>(void)
```
