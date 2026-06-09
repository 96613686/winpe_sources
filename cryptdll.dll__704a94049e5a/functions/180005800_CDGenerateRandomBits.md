# CDGenerateRandomBits

- ea: `0x180005800`
- end: `0x18000581c`
- name: `CDGenerateRandomBits`
- size: `28`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180005d80`
- `0x1800064e4`
- `0x180007250`
- `0x1800074e4`
- `0x180007870`
- `0x180007cf0`

## callees

- `0x180009010`

## pseudocode

```c
__int64 CDGenerateRandomBits()
{
  return ((__int64 (*)(void))qword_18000EC10[3 * (unsigned int)(cRngs - 1)])();
}

```

## disassembly

```asm
0x180005800  mov     eax, cs:cRngs
0x180005806  lea     r8, qword_18000EC10
0x18000580d  dec     eax
0x18000580f  lea     rax, [rax+rax*2]
0x180005813  mov     rax, [r8+rax*8]
0x180005817  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
