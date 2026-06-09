# _InitializeTrigCOMSecurity_::_1_::dtor$2

- ea: `0x14001e4fe`
- end: `0x14001e50a`
- name: `_InitializeTrigCOMSecurity_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140003bbc`

## pseudocode

```c
void __fastcall InitializeTrigCOMSecurity_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  AP<char>::~AP<char>((void **)(a2 + 248));
}

```

## disassembly

```asm
0x14001e4fe  lea     rcx, [rdx+0F8h]
0x14001e505  jmp     ??1?$AP@D@@QEAA@XZ; AP<char>::~AP<char>(void)
```
