# _DeleteSystemRestorePoints_::_1_::dtor$0

- ea: `0x140017807`
- end: `0x140017813`
- name: `_DeleteSystemRestorePoints_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000b8ec`

## pseudocode

```c
void __fastcall DeleteSystemRestorePoints_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CAutoSnapPointer::~CAutoSnapPointer((CAutoSnapPointer *)(a2 + 96));
}

```

## disassembly

```asm
0x140017807  lea     rcx, [rdx+60h]; this
0x14001780e  jmp     ??1CAutoSnapPointer@@QEAA@XZ; CAutoSnapPointer::~CAutoSnapPointer(void)
```
