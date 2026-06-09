# _CSnapinThreadTable::CreateInstance_::_1_::dtor$0

- ea: `0x18001bd3f`
- end: `0x18001bd4b`
- name: `_CSnapinThreadTable::CreateInstance_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18000d0e4`

## pseudocode

```c
void __fastcall CSnapinThreadTable::CreateInstance_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ItemHandleTable::operator delete(*(CHeapFactory **)(a2 + 112));
}

```

## disassembly

```asm
0x18001bd3f  mov     rcx, [rdx+70h]; void *
0x18001bd46  jmp     ??3ItemHandleTable@@SAXPEAX@Z; ItemHandleTable::operator delete(void *)
```
