# _IsPrivateQPath_::_1_::dtor$1

- ea: `0x14001e667`
- end: `0x14001e673`
- name: `_IsPrivateQPath_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003bbc`

## pseudocode

```c
void __fastcall IsPrivateQPath_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  AP<char>::~AP<char>((void **)(a2 + 32));
}

```

## disassembly

```asm
0x14001e667  lea     rcx, [rdx+20h]
0x14001e66e  jmp     ??1?$AP@D@@QEAA@XZ; AP<char>::~AP<char>(void)
```
