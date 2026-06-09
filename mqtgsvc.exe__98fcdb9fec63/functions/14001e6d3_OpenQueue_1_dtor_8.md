# _OpenQueue_::_1_::dtor$8

- ea: `0x14001e6d3`
- end: `0x14001e6df`
- name: `_OpenQueue_::_1_::dtor$8`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003bbc`

## pseudocode

```c
void __fastcall OpenQueue_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  AP<char>::~AP<char>((void **)(a2 + 64));
}

```

## disassembly

```asm
0x14001e6d3  lea     rcx, [rdx+40h]
0x14001e6da  jmp     ??1?$AP@D@@QEAA@XZ; AP<char>::~AP<char>(void)
```
