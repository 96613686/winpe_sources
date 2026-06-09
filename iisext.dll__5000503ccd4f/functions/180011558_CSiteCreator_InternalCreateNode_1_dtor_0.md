# _CSiteCreator::InternalCreateNode_::_1_::dtor$0

- ea: `0x180011558`
- end: `0x180011564`
- name: `_CSiteCreator::InternalCreateNode_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800105e4`

## pseudocode

```c
void __fastcall CSiteCreator::InternalCreateNode_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CSafeLock::~CSafeLock((CSafeLock *)(a2 + 128));
}

```

## disassembly

```asm
0x180011558  lea     rcx, [rdx+80h]; this
0x18001155f  jmp     ??1CSafeLock@@QEAA@XZ; CSafeLock::~CSafeLock(void)
```
