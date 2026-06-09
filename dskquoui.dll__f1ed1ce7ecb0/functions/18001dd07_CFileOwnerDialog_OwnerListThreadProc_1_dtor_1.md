# _CFileOwnerDialog::OwnerListThreadProc_::_1_::dtor$1

- ea: `0x18001dd07`
- end: `0x18001dd13`
- name: `_CFileOwnerDialog::OwnerListThreadProc_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800077dc`

## pseudocode

```c
void __fastcall CFileOwnerDialog::OwnerListThreadProc_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  AutoLockCs::~AutoLockCs((AutoLockCs *)(a2 + 64));
}

```

## disassembly

```asm
0x18001dd07  lea     rcx, [rdx+40h]; this
0x18001dd0e  jmp     ??1AutoLockCs@@QEAA@XZ; AutoLockCs::~AutoLockCs(void)
```
