# _CFileOwnerDialog::OwnerListThreadProc_::_1_::dtor$0

- ea: `0x18001deed`
- end: `0x18001def9`
- name: `_CFileOwnerDialog::OwnerListThreadProc_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180011e58`

## pseudocode

```c
void __fastcall CFileOwnerDialog::OwnerListThreadProc_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CNtHandle::~CNtHandle((CNtHandle *)(a2 + 136));
}

```

## disassembly

```asm
0x18001deed  lea     rcx, [rdx+88h]; this
0x18001def4  jmp     ??1CNtHandle@@QEAA@XZ; CNtHandle::~CNtHandle(void)
```
