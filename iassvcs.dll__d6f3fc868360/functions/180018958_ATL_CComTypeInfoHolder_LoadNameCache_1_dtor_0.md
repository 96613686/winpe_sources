# _ATL::CComTypeInfoHolder::LoadNameCache_::_1_::dtor$0

- ea: `0x180018958`
- end: `0x180018964`
- name: `_ATL::CComTypeInfoHolder::LoadNameCache_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000d9dc`

## pseudocode

```c
void __fastcall ATL::CComTypeInfoHolder::LoadNameCache_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 152));
}

```

## disassembly

```asm
0x180018958  mov     rcx, [rdx+98h]; Block
0x18001895f  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
