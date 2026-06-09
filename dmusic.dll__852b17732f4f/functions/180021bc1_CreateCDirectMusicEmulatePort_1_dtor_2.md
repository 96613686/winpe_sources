# _CreateCDirectMusicEmulatePort_::_1_::dtor$2

- ea: `0x180021bc1`
- end: `0x180021bcd`
- name: `_CreateCDirectMusicEmulatePort_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001abc8`

## pseudocode

```c
void __fastcall CreateCDirectMusicEmulatePort_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  CDirectMusicEmulatePort::~CDirectMusicEmulatePort(*(CDirectMusicEmulatePort **)(a2 + 64));
}

```

## disassembly

```asm
0x180021bc1  mov     rcx, [rdx+40h]; this
0x180021bc8  jmp     ??1CDirectMusicEmulatePort@@UEAA@XZ; CDirectMusicEmulatePort::~CDirectMusicEmulatePort(void)
```
