# _CAudioTimeCompression::SetInputProperty_::_1_::dtor$0

- ea: `0x180088b80`
- end: `0x180088b8c`
- name: `_CAudioTimeCompression::SetInputProperty_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000aa00`

## pseudocode

```c
void __fastcall CAudioTimeCompression::SetInputProperty_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CAutoLock::~CAutoLock((CAutoLock *)(a2 + 64));
}

```

## disassembly

```asm
0x180088b80  lea     rcx, [rdx+40h]; this
0x180088b87  jmp     ??1CAutoLock@@QEAA@XZ; CAutoLock::~CAutoLock(void)
```
